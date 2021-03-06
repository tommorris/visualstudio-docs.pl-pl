---
title: Widok linii - dane Kontencji | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
helpviewer_keywords:
- Lines view
ms.assetid: 859b02d2-eddf-4ad3-95de-0df67ee2ab03
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: ae52ad47e18a0572a883c50f43689bdaae60234d
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2018
ms.locfileid: "34843854"
---
# <a name="lines-view---contention-data"></a>Widok linii - dane kontencji
Widok linii danych kontencji wyświetla dane wydajności dla instrukcji, które były wykonywane w chwili przykłady zostały zebrane w przebiegu profilowania. W pliku źródłowym instrukcję może obejmować więcej niż jeden wiersz w pliku źródłowym, a jednym wierszu może zawierać więcej niż jedną instrukcję.  
  
 Instrukcja jest identyfikowany przez następujące dane:  
  
-   Plik źródłowy, który zawiera deklarację funkcji.  
  
-   Funkcja, która zawiera instrukcję.  
  
-   Wiersza źródłowego, w którym rozpoczyna się instrukcji.  
  
-   Po znaku wiersza źródłowego, w którym rozpoczyna się instrukcji.  
  
-   Wiersza źródłowego, w którym kończy się instrukcji.  
  
-   Po znaku wiersza źródłowego, w którym kończy się instrukcji.  
  
 Kolumna nazw wiersza zawiera sortowanie łączenia danych identyfikator.  
  
 W poniższej tabeli opisano kolumny wierszy Wyświetl raport.  
  
|Kolumny|Opis|  
|------------|-----------------|  
|**Wyłączny czasu blokowania**|Ilość czasu, w którym ta instrukcja została zablokowana wykonywanie kodu w instrukcji z powodu zdarzenia rywalizacji. Czas blokowania w funkcje, które wywołuje instrukcja nie jest włączony.|  
|**% Wyłącznego czasu blokowania**|Procent wszystkich czas blokowania w procesie, który był własny czas zablokowanych instrukcji.|  
|**Wyłączny rywalizacji**|Ile razy ta instrukcja została zablokowana wykonywanie kodu w instrukcji z powodu zdarzenia rywalizacji. Zdarzenia rywalizacji w funkcje, które wywołuje instrukcji nie są uwzględniane.|  
|**% Wyłącznego rywalizacji**|Procent wszystkich zdarzeń rywalizacji w procesie, które były wyłącznego rywalizacje dla tej instrukcji.|  
|**Adres funkcji**|Adres funkcji, która zawiera tej instrukcji.|  
|**Nazwa funkcji**|Pełna nazwa funkcji, która zawiera tej instrukcji.|  
|**Całkowity czas blokowania**|Czas blokowania w tej instrukcji i funkcje wywoływane w instrukcji.|  
|**Całkowity czas blokowania %**|Procent wszystkich czas blokowania w procesie, który był całkowity czas blokowania instrukcji.|  
|**Wraz z wartościami granicznymi rywalizacji**|Liczba ta instrukcja i funkcje, które zostały wywołane w instrukcji zostały zablokowane wykonywanie.|  
|**% Rywalizacji włącznie**|Procent wszystkich zdarzeń rywalizacji w procesie, które były włącznie rywalizacje dla tej instrukcji.|  
|**Nazwa linii**|Generowane przez profiler identyfikator wiersza. Identyfikator używa następującej składni:`SourceFile`**; [**  `LineNumberStart` **,**`CharacterStart`**] ->; [** `LineNumberEnd`**,**`CharacterEnd`**]**|  
|**Numer wiersza — funkcja**|Numer wiersza początku tej funkcji w pliku źródłowym.|  
|**Nazwa modułu**|Nazwa modułu zawiera instrukcję.|  
|**Ścieżka modułu**|Ścieżka moduł, który zawiera instrukcję.|  
|**Identyfikator procesu**|Identyfikator PID procesu PROFILOWANEGO procesu.|  
|**Nazwa procesu**|Nazwa procesu.|  
|**Rozpocznij znaków źródła**|Przesunięcie początkowy znaku w wierszu pliku źródłowego, w którym rozpoczyna się tej instrukcji.|  
|**Źródło znak końcowy**|Przesunięcie początkowy znak w wiersza pliku źródłowego, w którym kończy się w tej instrukcji.|  
|**Plik źródłowy**|Nazwa pliku źródłowego, który zawiera deklarację funkcji.|  
|**Początek wiersza źródłowego**|Numer wiersza pliku źródłowego, w którym rozpoczyna się instrukcji.|  
|**Źródło końca wiersza**|Numer wiersza w pliku źródłowym, w którym kończy się instrukcji.|  
  
## <a name="see-also"></a>Zobacz także  
 [Porady: Dostosowywanie kolumn widoku raportu](../profiling/how-to-customize-report-view-columns.md)   
 [Widok linii](../profiling/lines-view.md)   
 [Widok linii - próbkowanie](../profiling/lines-view-dotnet-memory-sampling-data.md)   
 [Widok linii](../profiling/lines-view-sampling-data.md)