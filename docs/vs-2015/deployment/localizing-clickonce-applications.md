---
title: Lokalizowanie aplikacji ClickOnce | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-deployment
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- WPF, ClickOnce applications
- ClickOnce deployment, globalization
- deploying applications [ClickOnce], localizing ClickOnce applications
- localization, ClickOnce deployment
- ClickOnce deployment, download on-demand
- ClickOnce deployment, localization
- Windows Forms, ClickOnce applications
- console applications, ClickOnce applications
ms.assetid: c92b193b-054d-4923-834b-d4226a4c7a1a
caps.latest.revision: 18
author: mikejo5000
ms.author: mikejo
manager: wpickett
ms.openlocfilehash: 285c1273114fe7f59b2ee0bb6bc612d18cbaf32e
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678921"
---
# <a name="localizing-clickonce-applications"></a>Lokalizowanie aplikacji ClickOnce
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [lokalizowanie aplikacji ClickOnce](https://docs.microsoft.com/visualstudio/deployment/localizing-clickonce-applications).  
  
Lokalizacja jest procesem tworzenia aplikacji odpowiednie dla określonej kultury. Ten proces obejmuje tłumaczenie tekstu interfejsu użytkownika na język określonego regionu, przy użyciu poprawną datę i formatowania waluty, dopasowywanie rozmiaru formantów w formularzu, a dublowania kontrolki od prawej do lewej w razie potrzeby.  
  
 Lokalizowanie wyniki aplikacji podczas tworzenia jeden lub więcej zestawów satelickich. Każdy zestaw zawiera ciągi, obrazy i inne zasoby, które są specyficzne dla danej kultury interfejsu użytkownika. (Głównego pliku wykonywalnego aplikacji zawiera ciągi dla kultury domyślnej aplikacji).  
  
 W tym temacie opisano trzy sposoby wdrożenia [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikacji dla innych języków:  
  
-   Dołącz wszystkie zestawy satelickie pojedynczego wdrożenia.  
  
-   Generowanie jedno wdrożenie dla każdej kultury za pomocą zestawu satelickiego pojedynczego uwzględnione w każdej.  
  
-   Pobieranie zestawów satelickich na żądanie.  
  
## <a name="including-all-satellite-assemblies-in-a-deployment"></a>W przypadku wdrożenia w tym wszystkie zestawy satelickie  
 Zamiast publikowanie wielu [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] wdrożenia, możesz opublikować jeden [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] wdrożenia, który zawiera wszystkie zestawy satelickie.  
  
 Ta metoda jest ustawieniem domyślnym w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Aby użyć tej metody w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], nie trzeba wykonywać żadnych dodatkowych działań.  
  
 Aby użyć tej metody za pomocą MageUI.exe, należy ustawić kulturę dla aplikacji do **neutralne** w MageUI.exe. Następnie musisz ręcznie dołączyć wszystkie zestawy satelickie w danym wdrożeniu. W MageUI.exe, można dodać zestawy satelickie przy użyciu **wypełniania** znajdujący się na **pliki** karcie manifest aplikacji.  
  
 Zaletą tego podejścia jest tworzy pojedyncze wdrożenie i upraszcza swoją historię wdrożenia zlokalizowane. W czasie wykonywania zestawu satelickiego odpowiednie będzie używany, w zależności od kultury domyślnej systemów operacyjnych Windows przez użytkownika. Wadą tego podejścia jest to, że pobiera wszystkie zestawy satelickie, zawsze wtedy, gdy aplikacja jest zainstalowane lub zaktualizowane na komputerze klienckim. Jeśli aplikacja ma dużą liczbę ciągów lub klienci mają wolne połączenie sieciowe, ten proces może wpłynąć na wydajność podczas aktualizacji aplikacji.  
  
> [!NOTE]
>  To podejście przyjęto założenie, że aplikacja Dopasowuje wysokość, szerokość i położenie kontrolki automatycznie w celu uwzględnienia rozmiarów ciąg tekstu różne w różnych kulturach. Windows Forms zawiera szereg kontroli i technologie, które pozwalają na projektowanie formularza umożliwiają łatwe możliwych do zlokalizowania, w tym <xref:System.Windows.Forms.FlowLayoutPanel> i <xref:System.Windows.Forms.TableLayoutPanel> formantów, jak również <xref:System.Windows.Forms.Control.AutoSize%2A> właściwości.  Zobacz też [porady: Obsługa lokalizacji na Windows Forms przy użyciu AutoSize i TableLayoutPanel](http://msdn.microsoft.com/library/1zkt8b33\(v=vs.110\)).  
  
## <a name="generate-one-deployment-for-each-culture"></a>Generowanie jednego wdrożenia dla każdej kultury  
 W tej strategii wdrażania możesz wygenerować wiele wdrożeń. W każdym wdrożeniu obejmują tylko zestawu satelickiego potrzebne dla określonej kultury i oznacz wdrożenia jako specyficzne dla tej kultury.  
  
 Do używania tej metody w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]ustaw **publikowania języka** właściwość **Publikuj** kartę do odpowiedniego regionu. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] automatycznie uwzględni zestawu satelickiego wymagane dla regionu, należy zaznaczyć, a spowoduje wykluczenie innych zestawów satelickich z wdrożenia.  
  
 Ten sam efekt można osiągnąć za pomocą narzędzia MageUI.exe w programie Microsoft [!INCLUDE[winsdklong](../includes/winsdklong-md.md)]. Użyj **wypełniania** znajdujący się na **pliki** karcie manifest aplikacji w taki sposób, aby wykluczyć wszystkie zestawy satelickie z katalogu aplikacji, a następnie ustaw **kultury**na **nazwa** karcie manifest wdrożenia w MageUI.exe. Kroki te obejmują nie tylko zestawu satelickiego poprawne, ale również ustawić `language` atrybutu na `assemblyIdentity` elementu w manifeście wdrożenia do odpowiednich kultury.  
  
 Po opublikowaniu aplikacji, należy powtórzyć ten krok dla każdego dodatkowego kultury Twoja aplikacja obsługuje. Należy się upewnić, opublikowanie do innego katalogu serwera sieci Web lub katalogu w udziale plików każdym razem, ponieważ każdy manifestu aplikacji będzie odwoływać się do zestawu satelickiego różnych, a każdy manifest wdrożenia będzie miał inną wartość dla `language`atrybutu.  
  
## <a name="downloading-satellite-assemblies-on-demand"></a>Pobieranie zestawów satelickich na żądanie  
 Jeśli zdecydujesz się dołączyć wszystkie zestawy satelickie pojedyncze wdrożenie, może poprawić wydajność przy użyciu pobierania danych na żądanie, co pozwala na Oznacz zestawy jako opcjonalną. Zestawy oznaczone nie zostaną pobrane po zainstalowaniu lub zaktualizowaniu aplikacji. Możesz zainstalować zestawy, gdy ich potrzebujesz, wywołując <xref:System.Deployment.Application.ApplicationDeployment.DownloadFileGroup%2A> metody <xref:System.Deployment.Application.ApplicationDeployment> klasy.  
  
 Pobieranie zestawów satelickich na żądanie różni się nieco od innych typów zestawów na żądanie pobierania. Aby uzyskać więcej informacji i przykładów kodu o sposobie włączania tego scenariusza przy użyciu [!INCLUDE[winsdkshort](../includes/winsdkshort-md.md)] narzędzi dla [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)], zobacz [wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu interfejsu API wdrożenia ClickOnce](../deployment/walkthrough-downloading-satellite-assemblies-on-demand-with-the-clickonce-deployment-api.md).  
  
 Można również włączyć ten scenariusz w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].  Zobacz też [wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu technologii ClickOnce wdrażania interfejsu API przy użyciu narzędzia Projektant](http://msdn.microsoft.com/library/ms366788\(v=vs.110\)) lub [wskazówki: Pobieranie zestawów satelickich na żądanie przy użyciu interfejsu API wdrożenia ClickOnce Za pomocą projektanta](http://msdn.microsoft.com/library/ms366788\(v=vs.120\)).  
  
## <a name="testing-localized-clickonce-applications-before-deployment"></a>Testowanie zlokalizowanych aplikacji ClickOnce, przed przystąpieniem do wdrożenia  
 Zestawu satelickiego stosowanych w odniesieniu do Windows Forms aplikacji tylko wtedy, gdy <xref:System.Threading.Thread.CurrentUICulture%2A> wątku głównego aplikacji zostaje ustalona kultury zestawu satelickiego. Klienci na rynkach lokalnych będą prawdopodobnie już uruchomione zlokalizowanej wersji systemu Windows za pomocą jego kultury, ustaw odpowiednią wartość domyślną.  
  
 Masz trzy opcje do testowania wdrożenia zlokalizowane przed udostępnieniem aplikacji dla klientów:  
  
-   Można uruchomić usługi [!INCLUDE[ndptecclick](../includes/ndptecclick-md.md)] aplikacji odpowiednie zlokalizowane wersje systemu Windows.  
  
-   Możesz ustawić <xref:System.Threading.Thread.CurrentUICulture%2A> właściwość programowo w aplikacji. (Ta właściwość musi być ustawiona, zanim wywołasz <xref:System.Windows.Forms.Application.Run%2A> metody.)  
  
## <a name="see-also"></a>Zobacz też  
 [\<assemblyIdentity > Element](../deployment/assemblyidentity-element-clickonce-deployment.md)   
 [Wdrażania i zabezpieczeń ClickOnce](../deployment/clickonce-security-and-deployment.md)   
 [Globalizacja formularzy Windows Forms](http://msdn.microsoft.com/library/72f6cd92-83be-45ec-aa37-9cb8e3ebc3c5)



