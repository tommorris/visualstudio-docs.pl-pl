---
title: Idialinenumber::get_length — | Dokumentacja firmy Microsoft
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
- C++
helpviewer_keywords:
- IDiaLineNumber::get_length method
ms.assetid: 2c55a6f7-4ef5-45fb-9fd1-d72deaaa2829
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6c2e30106b5f410e57f6dacd5cc2d91d88928588
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42680482"
---
# <a name="idialinenumbergetlength"></a>IDiaLineNumber::get_length
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [idialinenumber::get_length —](https://docs.microsoft.com/visualstudio/debugger/debug-interface-access/idialinenumber-get-length).  
  
Pobiera liczbę bajtów w bloku.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT get_length (   
   DWORD* pRetVal  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pRetVal`  
 [out] Zwraca liczbę bajtów w bloku.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`. Zwraca `S_FALSE` Jeśli ta właściwość nie jest obsługiwana. W przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Blok jest długością kodu źródłowego w wierszu, reprezentowane przez [idialinenumber —](../../debugger/debug-interface-access/idialinenumber.md) obiektu.  
  
## <a name="see-also"></a>Zobacz też  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)



