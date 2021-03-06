---
title: Analizowanie użycia pamięci w programie Visual Studio | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/02/2018
ms.technology: vs-ide-debug
ms.topic: conceptual
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3cee40dd1dab8c3a9d9b57b84e6e299651bc5fc8
ms.sourcegitcommit: db94ca7a621879f98d4c6aeefd5e27da1091a742
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/13/2018
ms.locfileid: "42623993"
---
# <a name="analyze-memory-usage"></a>Analizowanie użycia pamięci
Użyj zintegrowane z debugerem **użycie pamięci** narzędzie do diagnostyki do umożliwia znajdowanie przecieków pamięci i wykorzystania pamięci nieefektywne. Narzędzie umożliwia wykorzystanie pamięci, zapoznasz się z co najmniej jeden *migawek* sterty pamięci zarządzanego i natywnego. Można zbierać migawki .NET, Tryb natywny lub mieszany (.NET i natywny) aplikacji.  
  
-   Możesz analizować pojedynczej migawki zrozumieć konsekwencje typów obiektów na wykorzystanie pamięci i znaleźć kod w swojej aplikacji, która używa pamięci nieefektywne.  
  
-   Można również porównać (różnica) dwiema migawkami znajdowanie obszarów w kodzie aplikacji, które powodują wykorzystanie pamięci zwiększyć wraz z upływem czasu.  

Aby uzyskać szczegółowe instrukcje, zobacz [Analizowanie użycia pamięci](../profiling/memory-usage.md) samouczka. Aby Analizowanie użycia pamięci bez dołączania debugera, zobacz [użycie pamięci bez debugera](memory-usage-without-debugging2.md).

Można użyć narzędzi profilowania bez debugera, system Windows 7 lub nowszy. Windows 8 lub nowszy jest wymagany do uruchamiania narzędzi profilowania z debugerem (**narzędzia diagnostyczne** okno).
  
## <a name="blogs-and-videos"></a>Blogi i filmy wideo  

|         |         |
|---------|---------|
|  ![Ikona aparatu film wideo](../install/media/video-icon.png "Obejrzyj klip wideo")  |    [Obejrzyj film wideo](https://mva.microsoft.com/en-US/training-courses-embed/getting-started-with-visual-studio-2017-17798/Profiling-with-Diagnostics-Tools-in-Visual-Studio-2017-daHnzMD6D_9211787171) na temat korzystania z narzędzia diagnostyczne, które pokazuje, jak i analizowanie użycia pamięci i użycie procesora CPU w programie Visual Studio 2017. |

 [Analizowanie użycia Procesora i pamięci podczas debugowania](https://blogs.msdn.microsoft.com/visualstudio/2016/02/15/analyze-cpu-memory-while-debugging/)  
  
 [Blog dotyczący programu Visual C++: profilowanie pamięci w programie Visual C++ 2015](https://blogs.msdn.microsoft.com/vcblog/2015/10/21/memory-profiling-in-visual-c-2015/)  

## <a name="see-also"></a>Zobacz także
 [Profilowanie w programie Visual Studio](../profiling/index.md)  
 [Pierwsze spojrzenie na narzędziach profilowania](../profiling/profiling-feature-tour.md)