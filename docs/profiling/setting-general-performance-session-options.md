---
title: Opcje sesji wydajności ogólnej ustawienie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.property.general
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 5268e6821714dc6850541c319dba450bcc04490b
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34263563"
---
# <a name="set-general-performance-session-options"></a>Ustawianie opcji sesji ogólnej wydajności

Można ustawić metod gromadzenia danych i profilowanie danych konwencje nazewnictwa dla programu Visual Studio Profiling Tools sesji wydajności na **ogólne** strony okna dialogowego właściwości sesji wydajności. Aby otworzyć to okno dialogowe z **Eksplorator wydajności**, kliknij prawym przyciskiem myszy sesję wydajności, a następnie kliknij przycisk **właściwości**.

## <a name="choosing-data-collection-methods"></a>Wybieranie metody zbierania danych

Ustawianie metody podstawowej kolekcji, wybierając jedną z opcji w obszarze **kolekcja profilowania**. Opcje zostały opisane w następujących w poniższej tabeli:

|||
|-|-|
|**Próbkowanie**. Metoda pobierania próbek zbiera informacje dotyczące profilowania w regularnych odstępach czasu. Ta metoda jest przydatna do znajdowania problemy dotyczące użycia procesora i Sugerowane metody uruchamiania większości dochodzenia wydajności.|- [Zbieranie statystyk wydajności za pomocą metody pobierania próbek](../profiling/collecting-performance-statistics-by-using-sampling.md)|
|**Instrumentacja**. Metoda Instrumentacji injects do kopii modułu profilowania kodu, który rejestruje każdy wpis, zakończenia i wywołanie funkcji funkcji w module podczas przebiegu profilowania. Ta metoda jest przydatne do zbierania czasu szczegółowe informacje o sekcji kodu i zrozumienie wpływu wejściowymi i wyjściowymi operacje na wydajność aplikacji.|- [Zbieranie szczegółowych danych o chronometrażu przy użyciu Instrumentacji](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)|
|**Współbieżność**. Metoda współbieżności zbiera dane dla każdego zdarzenia, że wykonanie bloki kodu, na przykład jeśli wątek oczekuje na zablokowany dostęp do zasobów aplikacji ma zostać zwolniony. Ta metoda jest przydatna do analizowania aplikacji wielowątkowych.|- [Zbieranie danych współbieżności procesu i wątku](../profiling/collecting-thread-and-process-concurrency-data.md)|

 Możliwość zbierania danych pamięci .NET przy użyciu metody próbkowania i instrumentacji. Wybierz typ danych w ramach **profilowania pamięci .NET**.

|||
|-|-|
|**Zbierz informacje dotyczące alokacji obiektów platformy .NET**. Domyślnie dane obejmują liczbę i rozmiar przydzielonych obiektów. Wybierz lub wyczyść to pole wyboru, aby włączyć lub wyłączyć zbieranie danych pamięci .NET. |- [Zbieranie alokacji pamięci .NET i okres istnienia obiektu](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)|
|**Zbierz również informacje dotyczące okresu istnienia obiektu platformy .NET**. Zaznacz to pole wyboru, aby dołączyć dane o generacje kolekcji garbage użytych w celu odzyskania pamięci obiektów.|- [Zbieranie alokacji pamięci .NET i okres istnienia obiektu](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)  |

 Strona sesji profilowania jest wyświetlany po rozpoczęciu do profilu aplikacji, w którym można wstrzymać, wznowić i zatrzymanie profilowania.

 ![Strona sesji profilowania](../profiling/media/prof_profilingsessionpage.png "PROF_ProfilingSessionPage")

## <a name="set-profiling-data-file-options"></a>Ustawianie opcji pliku danych profilowania

|||
|-|-|
|**Raport**. Domyślnie plik danych (Vsp) profilowania podano nazwę PROFILOWANEGO aplikacji i znajduje się w folderze rozwiązania lub projektu. Ciąg daty również jest dołączany do nazwy, a numer zwiększany jest dodawany do plików danych, które w przeciwnym razie byłyby takich samych nazwach. Te opcje można zmienić.|- [Porady: Ustawianie opcji nazwy pliku danych wydajności](../profiling/how-to-set-performance-data-file-name-options.md)|