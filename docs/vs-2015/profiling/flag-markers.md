---
title: Flaga znaczniki | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.cv.markers.flag
ms.assetid: f3ec919e-63e5-484b-adbf-8f0e79342e75
caps.latest.revision: 14
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 58d366b38cfbf89052bb9bedfb8d397985680705
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680545"
---
# <a name="flag-markers"></a>Znaczniki typu flaga
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [znaczniki typu Flaga](https://docs.microsoft.com/visualstudio/profiling/flag-markers).  
  
Znacznik flagi reprezentuje coś, który wystąpił na moment w czasie w aplikacji. Flaga może reprezentować wiele rodzajów zdarzeń aplikacji. Na przykład flagę można pokazać, kiedy zostało zaplanowane danego elementu pracy, lub gdy wystąpił wyjątek. Środowiska uruchomieniowe, takich jak biblioteka zadań równoległych, można również wygenerować flag.  
  
## <a name="flag-importance"></a>Flaga znaczenie  
 Flagi są wyświetlane w różnych rozmiarach, w zależności od ich znaczenia. Podobnie jak wszelkie znacznika znaczenie może być niska, normalna, wysoką lub krytyczne.  Ta ilustracja przedstawia wygląd znaczników przez poziom ważności:  
  
 ![Niska, normalna, o wysokiej i krytyczne znaczniki znaczenie](../profiling/media/cvmarkerimportance.png "CVMarkerImportance")  
Znaczniki przedstawiający znaczenie flagi  
  
## <a name="flag-category"></a>Flaga kategorii  
 Flaga jest wyświetlany w jednej z pięciu różnych kolorach, w zależności od jego kategorii. Kolory są używane ponownie, jeśli istnieje więcej niż pięć kategorii. Nie można wybrać kolor. Podobnie jak wszelkie znacznika kategorii może być liczbą całkowitą. Następna ilustracja przedstawia kolory dla pierwszych pięć kategorii.  
  
 ![Pięć kolory znaczników kategorii](../profiling/media/cvmarkercategory.png "CVMarkerCategory")  
Znaczniki wyświetlane kategorie  
  
## <a name="alerts"></a>Alerty  
 Alert jest flagę kolorowe czerwony, która reprezentuje zdarzenie aplikacja o krytycznym znaczeniu, takich jak wyjątek.  Oto alert:  
  
 ![Znacznik alertu wizualizatora współbieżności](../profiling/media/cvmarkeralert.png "CVMarkerAlert")  
Znacznik alertu  
  
## <a name="aggregation-flags"></a>Flagi agregacji  
 Flagi wystąpić tak blisko siebie nawzajem w Wizualizatorze współbieżności, że nie można ich indywidualnie rysowania. Jeśli ten problem wystąpi, szary *flagi agregacji* czy reprezentuje flagi podstawowej jest widoczne. Po umieszczeniu wskaźnika na jednym z tych ikon etykietka narzędzia Wyświetla liczbę podstawowych flagi, które są reprezentowane. Aby wyświetlić flagi, powiększania. Jeśli powiększyć aż, a mimo to uzyskać flagi agregacji, można wyświetlić podstawowy flagi w [raport dotyczący znaczników](../profiling/markers-report.md).  
  
 Flagi agregacji są rysowane w różnych rozmiarach. Rozmiar zależy od poziomu ważności najważniejszych flagi agregacji. Poniższej ilustracji przedstawiono flagi agregacji w rosnącej kolejności ważności.  
  
 ![Wartość zagregowana flagi przedstawiający cztery poziomy ważności](../profiling/media/cvmarkeraggregate.png "CVMarkerAggregate")  
Flagi agregacji przez poziom ważności  
  
## <a name="see-also"></a>Zobacz też  
 [Znaczniki CONCURRENCY Visualizer](../profiling/concurrency-visualizer-markers.md)   
 [Zestaw SDK narzędzia Concurrency Visualizer](../profiling/concurrency-visualizer-sdk.md)



