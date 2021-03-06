---
title: Tworzenie raportów Profiler z poziomu wiersza polecenia | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c886f8af-2014-4fec-9b24-d98b68ecafb7
caps.latest.revision: 12
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d94a2c6c025ada73e1d43e041c2bf6e30f8b66c1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42674796"
---
# <a name="creating-profiler-reports-from-the-command-line"></a>Tworzenie raportów profilera z wiersza polecenia
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [tworzenie raportów Profiler w wierszu polecenia](https://docs.microsoft.com/visualstudio/profiling/creating-profiler-reports-from-the-command-line).  
  
**VSPerfReport** narzędzie wiersza polecenia pozwala na tworzenie XML lub raporty wartości rozdzielanych przecinkami (.csv) z pliku danych (Vsp) profilowania. Typy raportów VSPerfReport pasować widoków opartych na tabelach interfejsu dla [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]. Możesz filtrować raport, aby wyświetlić tylko Twój kod i aby pokazać tylko jeden segment plik danych profilowania. Aby uzyskać więcej informacji, zobacz [VSPerfReport](../profiling/vsperfreport.md).  
  
 Możesz również ułatwia plików danych profilowania do udostępniania, osadzając symboli plików Vsp i tworząc wstępnie przeanalizowany raport plików (.vsps), które są mniejsze i szybsze otworzyć.  
  
## <a name="common-tasks"></a>Typowe zadania  
  
|Zadanie|Powiązana zawartość|  
|----------|---------------------|  
|**Tworzenie podstawowych raportów.** Utwórz wszystkie lub podzbiór VSPerfReport typów raportów.|-   [Tworzenie podstawowych raportów](../profiling/creating-basic-profiling-reports-from-the-command-line.md)|  
|**Porównanie dwóch plików danych profilowania.** Utwórz raport "diff", który porównuje dane dotyczące wydajności w dwóch plików danych profilowania.|-   [Porady: Tworzenie raportu porównania Profiler w wierszu polecenia](../profiling/how-to-create-a-profiler-comparison-report-from-a-command-prompt.md)|  
|**Wyświetl ślad wywołania i dane zdarzeń śledzenia dla Windows (ETW).** Tworzenie raportu śledzenia wywołań, który wyświetla listę informacji chronometrażu dla każdego punktu wejścia i wyjścia do funkcji w aplikacji oraz dla każdego wywołania innych funkcji przez funkcję. Lub Utwórz uzyskać szczegółową listę wszystkich zdarzeń ETW, które zostały zebrane podczas uruchomienia profilowania.|-   [Porady: Tworzenie raportu śledzenia wywołań](../profiling/how-to-create-a-profiling-tools-call-trace-report.md)|  
|**Filtrowanie raportu.** Ogranicz raport tylko z funkcjami w kodzie lub się w określonym czasie w pliku danych profilowania.|-   [Porady: filtrowanie raportów z poziomu wiersza polecenia](../profiling/how-to-filter-reports-from-the-command-line.md)|  
|**Tworzenie przenośnych plików danych profilowania.** Aby upewnić się, udostępnianie danych ułatwia profilowania, można osadzić symbole dla profilowania do pliku Vsp. Można również utworzyć wstępnie przeanalizowany profilowania plik danych (.vsps), który jest mniejszy i szybciej otworzyć.|-   [Tworzenie przenośnych plików danych profilowania](../profiling/creating-portable-profiling-data-files-from-the-command-line.md)|



