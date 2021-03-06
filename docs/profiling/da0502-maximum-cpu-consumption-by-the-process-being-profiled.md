---
title: 'DA0502: Maksymalne wykorzystanie CPU przez proces poddawany profilowaniu | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.performance.rules.DA0502
- vs.performance.DA0502
- vs.performance.502
ms.assetid: 1ee53df5-b0dc-4265-9d4f-527830d08725
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e7c8a9806a7a0c84b71d247527d1d6eac4c5637e
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34766366"
---
# <a name="da0502-maximum-cpu-consumption-by-the-process-being-profiled"></a>DA0502: Maksymalne wykorzystanie CPU przez proces poddawany profilowaniu
|||  
|-|-|  
|Identyfikator reguły|DA0502|  
|Kategoria|Monitorowanie zasobów|  
|Metoda profilowania|Wszystkie|  
|Komunikat|Ta reguła jest wyłącznie w celach informacyjnych. Process()\\% czasu procesora mierzy użycie Procesora przez proces, który jest profilowania. Zgłaszana wartość to maksimum zaobserwowane we wszystkich interwałach pomiarowych.|  
|Typ reguły|Informacyjny|  
  
 Gdy profilu można za pomocą próbkowania, pamięci platformy .NET lub metody kontencji zasobów, należy zebrać co najmniej 10 próbek do wyzwolenia tej reguły.  
  
## <a name="rule-description"></a>Opis reguły  
 Ten komunikat raporty maksymalny procent czasu, przez który procesor był zajęty wykonywaniem instrukcji z aplikacji. Podanej wartości jest wartość maksymalna zgłoszone wśród wszystkich interwałów pomiarowych, w których był aktywny PROFILOWANEGO procesu. Wartość procentowa może być większa niż 100% na maszynie z więcej niż jeden procesor.  
  
## <a name="how-to-use-the-rule-data"></a>Jak używać danych reguły  
 Użyj wartości reguły do porównania wydajności z różnych wersji lub kompilacji programu lub aby zrozumieć działanie aplikacji w różnych scenariuszach profilowania.