---
title: 'Porady: wyświetlanie dokumentów skryptu | Dokumentacja firmy Microsoft'
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
- Script Explorer
ms.assetid: 8b621e53-4508-4b4a-9995-70995b0b9ac8
caps.latest.revision: 25
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc24c5e9c2332516cbf939e14581a2df7bea44eb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42684006"
---
# <a name="how-to-view-script-documents"></a>Porady: wyświetlanie dokumentów skryptu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: wyświetlanie dokumentów skryptu](https://docs.microsoft.com/visualstudio/debugger/how-to-view-script-documents).  
  
We wcześniejszych wersjach programu [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], pliki skryptów po stronie klienta wygenerowany na podstawie skryptu po stronie serwera pojawiły się w oknie Eksplorator skryptów. Okno Eksplorator skryptów często zostało ukryte, tak, aby dostępności skryptu po stronie klienta nie jest zawsze oczywiste.  
  
 W [!INCLUDE[vs_dev11_long](../includes/vs-dev11-long-md.md)], pliki skryptu po stronie klienta wygenerowany na podstawie skryptu po stronie serwera są wyświetlane w Eksploratorze rozwiązań, który jest domyślnie widoczny. Okno Eksplorator skryptów zostały wyeliminowane.  
  
 Pliki skryptów po stronie klienta są widoczne tylko wtedy, gdy jesteś w trybie debugowania lub w trybie przerwania. Pojawiają się na **dokumenty skryptów** węzła.  
  
 Pliki skryptów po stronie serwera są zawsze widoczne. Pojawiają się na  **\<Pathname witryny sieci Web >** węzła. Nazwa węzła jest podobna do poniższego przykładu: `c:\...\Website2\`  
  
### <a name="to-view-a-server-side-script-document"></a>Aby wyświetlić dokument skryptu po stronie serwera  
  
1.  W **Eksploratora rozwiązań**, otwórz  **\<Pathname witryny sieci Web >** węzła.  
  
2.  Kliknij dwukrotnie plik skryptu, który chcesz wyświetlić.  
  
     Plik skryptu po stronie serwera, zostanie otwarty w oknie źródła.  
  
### <a name="to-view-a-client-side-script-document"></a>Aby wyświetlić dokument skryptu po stronie klienta  
  
1.  W **Eksploratora rozwiązań**, otwórz **dokumenty skryptów** węzła.  
  
2.  Kliknij dwukrotnie plik skryptu, który chcesz wyświetlić.  
  
     Plik skryptu po stronie klienta zostanie otwarty w oknie źródła.  
  
## <a name="see-also"></a>Zobacz też  
 [Wyświetlanie danych w debugerze](../debugger/viewing-data-in-the-debugger.md)


