---
title: 'Porady: debugowanie aplikacji internetowych | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- Web services, debugging
- ASP.NET Web Forms, debugging
- ASP.NET, debugging Web applications
- debugging ASP.NET Web applications, during development
ms.assetid: 6440d12e-6b29-42c5-a958-99aeaaff480f
caps.latest.revision: 40
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3dce1129282dc7273631e261bb32d313f65ce381
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42677761"
---
# <a name="how-to-debug-web-applications"></a>Porady: debugowanie aplikacji internetowych
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: debugowanie aplikacji sieci Web](https://docs.microsoft.com/visualstudio/debugger/how-to-debug-web-applications).  
  
[!INCLUDE[vstecasp](../includes/vstecasp-md.md)] jest podstawową technologię do opracowywania aplikacji sieci Web w [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] Debugera oferuje zaawansowane narzędzia do debugowania [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikacji sieci Web, lokalnie lub na serwerze zdalnym. W tym temacie opisano sposób debugowania [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] projektu podczas programowania. Aby uzyskać informacje dotyczące debugowania [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] już wdrożone na serwerze produkcyjnym aplikacji sieci Web, zobacz [debugowania wdrożonych aplikacji sieci Web](../debugger/debugging-deployed-web-applications.md).  
  
 Aby debugować [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikacji:  
  
-   Musi mieć wymagane uprawnienia. Aby uzyskać więcej informacji, zobacz [wymagania systemowe](../debugger/aspnet-debugging-system-requirements.md).  
  
-   [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] debugowanie musi zostać włączone w **właściwości projektu**.  
  
-   Plik konfiguracyjny aplikacji (Web.config) musi być ustawiony w tryb debugowania. Powoduje, że tryb debugowania [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] generuje symbole dla dynamicznie wygenerowanych plików i umożliwia debugerowi dołączenie do [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] aplikacji. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] automatycznie ustawia to podczas uruchamiania debugowania, jeśli projekt jest utworzony z szablonu projektów sieci Web.  
  
-   Aby uzyskać więcej informacji, zobacz [porady: Włączanie debugowania dla aplikacji ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md).  
  
### <a name="to-debug-a-web-application-during-development"></a>Aby debugować aplikację sieci Web podczas programowania  
  
1.  Na **debugowania** menu, kliknij przycisk **Start** aby rozpocząć debugowanie aplikacji sieci Web.  
  
     [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] tworzy projekt aplikacji sieci Web, wdraża aplikację, jeśli to konieczne, rozpoczyna się programem ASP.NET Development Server, Jeśli debugujesz lokalnie i dołącza do [!INCLUDE[vstecasp](../includes/vstecasp-md.md)] procesu roboczego.  
  
2.  Za pomocą debugera do zestawu i Wyczyść punkty przerwania, kroku i wykonywać inne operacje debugowania, tak jak w przypadku dowolnej aplikacji.  
  
     Aby uzyskać więcej informacji, zobacz [podstawy debugera](../debugger/debugger-basics.md).  
  
3.  Na **debugowania** menu, kliknij przycisk **Zatrzymaj debugowanie** -to-end sesji debugowania lub na **pliku** menu w programie Internet Explorer kliknij **Zamknij**.  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie aplikacji sieci Web i skryptu](../debugger/debugging-web-applications-and-script.md)   
 [Debugowanie aplikacji ASP.NET i AJAX](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [Porady: Włączanie debugowania dla aplikacji ASP.NET](../debugger/how-to-enable-debugging-for-aspnet-applications.md)



