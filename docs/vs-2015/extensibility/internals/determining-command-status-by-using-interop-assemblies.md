---
title: Określanie stanu polecenia przy użyciu zestawów międzyoperacyjnych | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- interop assemblies, determining command status
- command handling with interop assemblies, status
ms.assetid: 2f5104d1-7b4c-4ca0-a626-50530a8f7f5c
caps.latest.revision: 19
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 22648a85f8c8774896914b9519aa3d10d3dc732d
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679698"
---
# <a name="determining-command-status-by-using-interop-assemblies"></a>Określanie stanu polecenia przy użyciu zestawów międzyoperacyjnych
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Określanie polecenia stanu przez przy użyciu zestawy międzyoperacyjne](https://docs.microsoft.com/visualstudio/extensibility/internals/determining-command-status-by-using-interop-assemblies).  
  
Pakietu VSPackage musi zachować informacje o stanie poleceń, które może obsłużyć. Środowisko nie może określić, kiedy polecenie przetwarzanych w ramach Twojego pakietu VSPackage staje się włączone lub wyłączone. Jest odpowiedzialny za Twojego pakietu VSPackage poinformować środowiska o stanach polecenia, na przykład stanu Generalny polecenia, takie jak **Wytnij**, **kopiowania**, i **Wklej**.  
  
## <a name="status-notification-sources"></a>Stan powiadomienia źródeł  
 Środowisko otrzymuje informacji na temat poleceń w pakietach VSPackage <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody, która jest częścią pakietu VSPackage implementacji programu <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> interfejsu. Wywołania środowiska <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metoda pakietu VSPackage w dwóch okolicznościach:  
  
-   Gdy użytkownik otwiera menu głównego lub menu kontekstowego (na przykład przez kliknięcie prawym przyciskiem myszy), wykonuje środowiska <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> metody na wszystkich poleceń tym menu, aby określić ich stanu.  
  
-   Gdy pakietu VSPackage żąda, że środowisko aktualizacji bieżący interfejsu użytkownika (UI). Dzieje się tak jak polecenia, które są obecnie widoczne dla użytkownika, takie jak **Wytnij**, **kopiowania**, i **Wklej** grupowania na standardowym pasku narzędzi, stają się włączone i wyłączone w odpowiedzi na działania kontekstu i użytkownika.  
  
 Ponieważ powłoki hostuje wiele pakietów VSPackage, wydajności powłoki programu nieakceptowalnie może obniżyć razie zostały sondować każdego pakietu VSPackage, aby określić stan polecenia. Zamiast tego Twojego pakietu VSPackage powinny aktywnie powiadomić środowiska, zmianie jego interfejsu użytkownika w momencie zmiany. Aby uzyskać więcej informacji na temat powiadomienie o aktualizacji, zobacz [aktualizowania interfejsu użytkownika](../../extensibility/updating-the-user-interface.md).  
  
## <a name="status-notification-failure"></a>Stan: niepowodzenie powiadomień  
 Błąd usługi pakietu VSPackage powiadomić środowiska zmiany stanu polecenia można umieścić interfejsu użytkownika w stanie niespójnym. Należy pamiętać, że dowolne polecenia menu menu lub kontekst można umieścić na pasku narzędzi przez użytkownika. W związku z tym aktualizowania interfejsu użytkownika, tylko wtedy, gdy zostanie otwarte menu menu lub kontekst nie jest wystarczająca.  
  
## <a name="see-also"></a>Zobacz też  
 [Jak dodać elementy interfejsu użytkownika w pakietach VSPackage](../../extensibility/internals/how-vspackages-add-user-interface-elements.md)   
 [Implementacja](../../extensibility/internals/command-implementation.md)

