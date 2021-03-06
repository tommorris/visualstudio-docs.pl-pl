---
title: Okno dialogowe Opcje, projekty i rozwiązania, skompilować i uruchomić | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- VS.ToolsOptionsPages.Projects.Build_and_Run
- VS.ToolsOptionsPag.Projects.Build_and_Run
helpviewer_keywords:
- builds [Visual Studio], setting up
- run actions
- debugger, run options
ms.assetid: c884976e-c0df-4c6d-8e3a-856ea2bd547c
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 38374893aea62af1b664065edf0ca9195f3dd301
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42689135"
---
# <a name="options-dialog-box--projects-and-solutions-build-and-run"></a>Okno dialogowe Opcje, projekty i rozwiązania, kompilowanie i uruchamianie
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [okno dialogowe Opcje, projekty i rozwiązania, kompilacji i uruchomienia](https://docs.microsoft.com/visualstudio/ide/reference/options-dialog-box-projects-and-solutions-build-and-run).  
  
  
W tym oknie można określić maksymalną liczbę projektów Visual C++ lub Visual C#, które można tworzyć w tym samym czasie, niektóre domyślne tworzenia zachowań i niektóre ustawienia dziennika kompilacji. Aby otworzyć **opcje** okna dialogowego wybierz **narzędzia**, **opcje** na pasku menu. Aby uzyskać dostęp do tego zestawu opcji, należy rozwinąć **projekty i rozwiązania**, a następnie wybierz **kompilowanie i uruchamianie**.  
  
## <a name="uielement-list"></a>Lista elementów UI  
 **Maksymalna liczba równoległych projektów kompilacji**  
 Określa maksymalną liczbę projektów Visual C++ i Visual C#, które można tworzyć w tym samym czasie. Aby zoptymalizować proces kompilacji, maksymalną liczbę równolegle kompilowanych projektów automatycznie jest równa liczbie procesorów na komputerze. Wartość maksymalna to 32.  
  
 **Tylko tworzyć projekty startowe i zależności przy uruchomieniu**  
 Tylko projekt startowy i jego zależności są tworzone, jeśli to pole wyboru jest zaznaczone, po wybraniu klawisza F5; Wybierz **debugowania**, **Start** menu paska; lub wybierz **kompilacji**, **kompilacji** na pasku menu. Wszystkie projekty, zależności i pliki rozwiązania są tworzone, jeśli to pole wyboru jest wyczyszczone po wybraniu klawisza F5; Wybierz **debugowania**, **Start** menu paska; lub wybierz **kompilacji**, **kompilacji** na pasku menu. Domyślnie ta opcja jest zaznaczona.  
  
 **Przy starcie, gdy projekty są nieaktualne**  
 > [!NOTE]
>  Ta lista dotyczy [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] wyłącznie dla projektów.  
  
 Domyślnie, pojawi się komunikat z konfiguracji projektu jest nieaktualna, kiedy wybierz klawisz F5 lub wybierz **debugowania**, **Start** na pasku menu. Można określić, czy mimo to skompilować projekt i tego, czy komunikat jest wyświetlany. Użyj tej opcji, aby określić, czy komunikat jest wyświetlany, i co zachowanie kompilacji należy wiadomość, nie są wyświetlane.  
  
 **Zawsze Kompiluj**  
 Nie jest wyświetlane okno komunikatu, a projekt jest kompilowany pomimo nieaktualne konfiguracji. Ta opcja jest ustawiona, po wybraniu **nie pokazuj więcej tego okna dialogowego** pole w wiadomości, a następnie wybierz **tak** przycisku.  
  
 **Nigdy nie Kompiluj**  
 Nie jest wyświetlane okno komunikatu, a projekt nie jest kompilowany. Ta opcja jest ustawiona, po wybraniu **nie pokazuj więcej tego okna dialogowego** pole w wiadomości, a następnie wybierz **nie** przycisku.  
  
 **Monituj o kompilacje**  
 Wyświetla okno komunikatu, ilekroć dany plik konfiguracyjny jest nieaktualna.  
  
 **Uruchom następujący skrypt, podczas kompilacji lub występują błędy związane z wdrażaniem**  
 Jeśli wystąpią błędy kompilacji podczas kompilacji z **kompilacji** menu, zostanie wyświetlony komunikat. Można określić, czy kontynuować poprzez uruchomienie aplikacji i tego, czy komunikat jest wyświetlany za każdym razem, gdy, błędy kompilacji. Użyj tej opcji, aby określić czy komunikat jest wyświetlany, i jakie zachowanie powinny być wiadomość, nie są wyświetlane.  
  
> [!NOTE]
>  Ta opcja dotyczy [!INCLUDE[vcprvc](../../includes/vcprvc-md.md)] wyłącznie dla projektów.  
  
 **Monituj o uruchomienie**  
 Wyświetla okno komunikatu, za każdym razem, gdy, błędy kompilacji wystąpić.  
  
 **Nie uruchamiaj**  
 Nie jest wyświetlane okno komunikatu, a nie jest uruchomiona aplikacja. Ta opcja jest ustawiona, po wybraniu **nie pokazuj więcej tego okna dialogowego** w oknie oknie komunikatu, a następnie wybierz **nie** przycisku.  
  
 **Uruchom starą wersję**  
 Nie jest wyświetlane okno komunikatu, a nowo utworzonej wersji aplikacji nie jest uruchomiona. Ta opcja jest ustawiona, po wybraniu **nie pokazuj więcej tego okna dialogowego** w oknie oknie komunikatu, a następnie wybierz **tak** przycisku.  
  
 **W przypadku nowych rozwiązań Użyj obecnie wybranego projektu jako projekt startowy**  
 Jeśli to pole wyboru jest zaznaczone, nowych rozwiązań Użyj obecnie wybranego projektu jako projekt startowy.  
  
 **Program MSBuild poziom szczegółowości danych wyjściowych kompilacji dla projektu**  
 Określa, ile informacji ma pojawia się w **dane wyjściowe** okna dla kompilacji.  
  
 **Poziom szczegółowości pliku dziennika MSBuild projektu kompilacji**  
 > [!NOTE]
>  Ta opcja dotyczy tylko projektów Visual C++.  
  
 Określa, ile informacji ma są zapisywane do pliku dziennika kompilacji, który znajduje się w folderze \\... \\ *ProjectName*\Debug\\*ProjectName*. log.  
  
## <a name="see-also"></a>Zobacz też  
 [Kompilowanie i tworzenie](../../ide/compiling-and-building-in-visual-studio.md)



