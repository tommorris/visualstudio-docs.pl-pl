---
title: Cvwriteflag — funkcja | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- cvmarkers/CvWriteFlagExVA
- cvmarkers/CvWriteFlagExW
- cvmarkers/CvWriteFlagExVW
- cvmarkers/CvWriteFlagExA
helpviewer_keywords:
- CvWriteFlagExW method
- CvWriteFlagExVA method
- CvWriteFlagExA method
- CvWriteFlagExVW method
ms.assetid: ee9da1e2-7b34-4cba-81e2-215d25d32e4d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 417d901504eb20894b3bd3e83d286dac4e66b072
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34749375"
---
# <a name="cvwriteflag-function"></a>Cvwriteflag — funkcja
Zapisuje plik śledzenia Concurrency Visualizer flagę.  
  
## <a name="syntax"></a>Składnia  
  
```C  
HRESULT CvWriteFlagExW(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCWSTR pMessage,  
    ...  
    );  
  
HRESULT CvWriteFlagExA(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCSTR pMessage,  
    ...  
    );  
  
HRESULT CvWriteFlagExVW(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCWSTR pMessage,  
    _In_ va_list argList);  
  
HRESULT CvWriteFlagExVA(  
    _In_reads_bytes_(16) PCV_MARKERSERIES pMarkerSeries,  
    _In_ CV_IMPORTANCE level,  
    _In_ int category,  
    _In_ PCSTR pMessage,  
    _In_ va_list argList);  
```  
  
#### <a name="parameters"></a>Parametry  
 `argList`  
 Lista argumentów.  
  
 `category`  
 Kategoria.  
  
 `level`  
 Poziom ważności.  
  
 `pMarkerSeries`  
 Kontekst serii prawidłowy znacznik. Nie może mieć wartości NULL.  
  
 `pMessage`  
 Ciąg formatu wiadomości. Nie może mieć wartości NULL.  
  
## <a name="return-value"></a>Wartość zwracana  
 Wartość S_OK, gdy wiadomość zostanie pomyślnie zapisany. Kod błędu w przypadku, gdy było żadnych błędów. Użyj makra powiodło się/nie powiodło się, aby sprawdzić warunku błędu.  
  
## <a name="requirements"></a>Wymagania  
 **Nagłówek:** *cvmarkers.h*  
  
 **Unicode:** CvWriteFlagExW, CvWriteFlagExVW  
  
 **ANSI:** CvWriteFlagExA, CvWriteFlagExVA  
  
## <a name="see-also"></a>Zobacz także  
 [Odwołanie do biblioteki C++](../profiling/cpp-library-reference.md)