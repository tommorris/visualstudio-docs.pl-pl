---
title: Poprawianie wydajności dodatku VSTO
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: cc1605a61d63a5d314ae1f02d864124185546ada
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34269017"
---
# <a name="improve-the-performance-of-a-vsto-add-in"></a>Poprawianie wydajności dodatku VSTO
  Można zapewnić użytkownikom lepsze środowisko optymalizując dodatków VSTO, utworzonych na potrzeby aplikacji, aby szybko rozpocząć, zamknij pakietu Office, otwórz elementów i wykonywanie innych zadań. Jeśli Twoje dodatku VSTO dla programu Outlook, można także zmniejszyć ryzyko, że dodatek VSTO zostanie wyłączona z powodu niskiej wydajności. Można zwiększyć wydajność sieci dodatku VSTO zaimplementowanie następujących strategii:  
  
-   [Załadować dodatków VSTO na żądanie](#Load).  
  
-   [Publikowanie rozwiązań pakietu Office przy użyciu Instalatora Windows](#Publish).  
  
-   [Obejście odbicia wstążki](#Bypass).  
  
-   [Wykonywanie operacji kosztowne w wątku wykonywania oddzielnych](#Perform).  
  
 Aby uzyskać więcej informacji dotyczących sposobu optymalizacji dodatku VSTO dla programu Outlook, zobacz [kryteria wydajności, aby zachować dodatków VSTO włączone](http://go.microsoft.com/fwlink/?LinkID=266503).  
  
##  <a name="Load"></a> Załadować dodatków VSTO na żądanie  
 Można skonfigurować dodatku VSTO załadować tylko w następujących okolicznościach:  
  
-   Po raz pierwszy użytkownik uruchamia aplikację po dodatku VSTO.  
  
-   Podczas pierwszego, którą użytkownik wchodzi w interakcję z dodatku VSTO po uruchomieniu aplikacji w dowolnym momencie kolejne.  
  
 Na przykład dodatek VSTO może wypełnić arkusz danych po wybraniu przycisku niestandardowego, który jest oznaczony **Pobierz Moje dane**. Aplikacja musi załadować dodatku VSTO z co najmniej jeden raz, aby **Pobierz Moje dane** przycisk może występować na Wstążce. Jednak dodatku VSTO nie załadować ponownie po uruchomieniu aplikacji następnym razem. Dodatku VSTO ładuje tylko wtedy, gdy użytkownik wybierze **Pobierz Moje dane** przycisku.  
  
### <a name="to-configure-a-clickonce-solution-to-load-vsto-add-ins-on-demand"></a>W celu skonfigurowania rozwiązania ClickOnce, aby załadować dodatków VSTO na żądanie  
  
1.  W **Eksploratora rozwiązań**, wybierz węzeł projektu.  
  
2.  Na pasku menu wybierz **widoku** > **strony właściwości**.  
  
3.  Na **publikowania** , wybierz pozycję **opcje** przycisku.  
  
4.  W **opcji publikowania** oknie dialogowym wybierz **ustawienia pakietu Office** elementu listy, wybierz **obciążenia na żądanie** opcji, a następnie wybierz pozycję **OK**przycisku.  
  
### <a name="to-configure-a-windows-installer-solution-to-load-vsto-add-ins-on-demand"></a>Aby skonfigurować rozwiązanie Instalatora Windows można załadować dodatków VSTO na żądanie  
  
1.  W rejestrze, ustaw `LoadBehavior` wpisu **_głównego_\Software\Microsoft\Office\\_ApplicationName_\Addins\\  _Identyfikator dodatku_** klucza **0x10**.  
  
     Aby uzyskać więcej informacji, zobacz [wpisy rejestru dotyczące dodatków narzędzi VSTO](../vsto/registry-entries-for-vsto-add-ins.md).  
  
### <a name="to-configure-a-solution-to-load-vsto-add-ins-on-demand-while-you-debug-the-solution"></a>Aby skonfigurować rozwiązanie załadować dodatków VSTO na żądanie, gdy debugowanie rozwiązania  
  
1.  Utwórz skrypt, który ustawia `LoadBehavior` wpisu **_głównego_\Software\Microsoft\Office\\_ApplicationName_\Addins\\  _Identyfikator dodatku_** klucza **0x10**.  
  
     Poniższy kod przedstawia przykład tego skryptu.  
  
    ```cmd/sh
    [HKEY_CURRENT_USER\Software\Microsoft\Office\Excel\Addins\MyAddIn]  
    "Description"="MyAddIn"  
    "FriendlyName"="MyAddIn"  
    "LoadBehavior"=dword:00000010  
    "Manifest"="c:\\Temp\\MyAddIn\\bin\\Debug\\MyAddIn.vsto|vstolocal"  
  
    ```  
  
2.  Utwórz zdarzenie mające miejsce po kompilacji, która aktualizuje rejestr przy użyciu skryptu.  
  
     Poniższy kod przedstawia przykład ciąg polecenia, które można dodać do zdarzenia postkompilacyjnego.  
  
    ```cmd/sh
    regedit /s "$(SolutionDir)$(SolutionName).reg"  
  
    ```  
  
     Aby uzyskać informacje o sposobie tworzenia zdarzenia postkompilacyjnego w projekcie C#, zobacz [porady: Określ zdarzenia kompilacji &#40;C&#35;&#41;](/visualstudio/ide/how-to-specify-build-events-csharp).  
  
     Aby dowiedzieć się, jak utworzyć zdarzenie mające miejsce po kompilacji w projektach Visual Basic, zobacz [porady: Określ zdarzenia kompilacji &#40;Visual Basic&#41;](/visualstudio/ide/how-to-specify-build-events-visual-basic).  
  
##  <a name="Publish"></a> Publikowanie rozwiązań pakietu Office przy użyciu Instalatora Windows  
 Rozwiązanie w przypadku publikowania za pomocą Instalatora Windows, Visual Studio 2010 Tools dla pakietu Office runtime pomija następujące kroki po załadowaniu w dodatku VSTO.  
  
-   Sprawdzanie poprawności schematu manifestu.  
  
-   Automatyczne sprawdzanie aktualizacji.  
  
-   Weryfikowanie podpisów cyfrowych w manifesty wdrożenia.  
  
    > [!NOTE]  
    >  Ta metoda nie jest konieczne, w przypadku wdrożenia z dodatku VSTO w bezpiecznej lokalizacji na komputerach użytkowników.  
  
 Aby uzyskać więcej informacji, zobacz [wdrażania rozwiązania do pakietu Office przy użyciu Instalatora Windows](../vsto/deploying-an-office-solution-by-using-windows-installer.md).  
  
##  <a name="Bypass"></a> Obejście odbicia wstążki  
 W przypadku tworzenia rozwiązania przy użyciu [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)], sprawdź, czy użytkownicy mają zainstalowany najnowszej wersji programu Visual Studio 2010 Tools dla pakietu Office runtime podczas wdrażania rozwiązania. Starsze wersje tego środowiska uruchomieniowego uwzględniane w zestawy rozwiązania, aby zlokalizować dostosowań Wstążki. Ten proces może spowodować dodatku VSTO załadować wolniej.  
  
 Alternatywnie można zapobiec za pomocą odbicia. Aby zidentyfikować dostosowań Wstążki dowolnej wersji programu Visual Studio 2010 Tools dla pakietu Office runtime. Aby użyć tej strategii, należy zastąpić `CreateRibbonExtensibility` — metoda i jawnie zwracanych obiektów wstążki. Jeśli Twoje dodatku VSTO nie zawiera żadnych dostosowań Wstążki, zwróć `null` wewnątrz metody.  
  
 Poniższy przykład zwraca obiekt wstążki na podstawie wartości pola.  
  
 [!code-vb[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/VisualBasic/trin_ribbon_choose_ribbon_4/ThisWorkbook.vb#1)]
 [!code-csharp[Trin_Ribbon_Choose_Ribbon#1](../vsto/codesnippet/CSharp/trin_ribbon_choose_ribbon_4/ThisWorkbook.cs#1)]  
  
##  <a name="Perform"></a> Wykonywanie operacji kosztowne w oddzielnych wykonanie wątku  
 Należy rozważyć przeprowadzanie (takich jak długotrwałych zadań, połączenia z bazą danych lub inne rodzaje połączeń sieciowych) w oddzielnym wątku. Aby uzyskać więcej informacji, zobacz [Obsługa wątkowości w Office](../vsto/threading-support-in-office.md).  
  
> [!NOTE]  
>  Cały kod, który odwołuje się do modelu obiektów pakietu Office musi być wykonywany w głównym wątku.  
  
## <a name="see-also"></a>Zobacz także  
 [Dodatków VSTO podczas ładowania na żądanie](http://blogs.msdn.com/b/andreww/archive/2008/07/14/demand-loading-vsto-add-ins.aspx)   
 [Opóźnienie ładowania CLR w dodatków pakietu Office](http://blogs.msdn.com/b/andreww/archive/2008/04/19/delay-loading-the-clr-in-office-add-ins.aspx)   
 [Wydajność VSTO: opóźnić ładowania i użytkownik (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/01/07/vsto-performance-delay-loading-and-you.aspx)   
 [Ulepszenia wydajności wkrótce dodatku service pack w pobliżu możesz (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/11/30/performance-improvements-coming-soon-to-a-service-pack-near-you-stephen-peters.aspx)   
 [Wydajność VSTO: wstążki odbicia (Stephen Peters)](http://blogs.msdn.com/b/vsto/archive/2010/06/03/vsto-performance-ribbon-reflection.aspx)  
  
  