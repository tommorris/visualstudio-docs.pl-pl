---
title: IDispError::GetDescription | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IDispError.GetDescription
apilocation:
- scrobj.dll
helpviewer_keywords:
- IDispError::GetDescription
ms.assetid: 04deaea6-0265-4e34-952e-634edba0e923
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1c840dee7774ce5f056808daf98c448eac73ceb0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/27/2017
ms.locfileid: "24794422"
---
# <a name="idisperrorgetdescription"></a>IDispError::GetDescription
Zwraca tekstowy opis błędu.  
  
## <a name="syntax"></a>Składnia  
  
```  
HRESULT GetDescription(  
   BSTR*  pbstrDescription  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pbstrDescription`  
 [out] Ciąg zawierający krótki opis błędu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Metoda zwraca `HRESULT`. Przykładowe dopuszczalne wartości wymieniono w tabeli poniżej.  
  
|Wartość|Opis|  
|-----------|-----------------|  
|`S_OK`|Wykonanie metody powiodło się.|  
  
## <a name="remarks"></a>Uwagi  
 Tekst jest zwracany w języku określonym przez identyfikator ustawień regionalnych (LCID), który został przekazany do `IDispatchEx::InvokeEx` metodę, która napotkała błąd.  
  
> [!NOTE]
>  Ta metoda nie jest zaimplementowana.  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejs IDispError](../../winscript/reference/idisperror-interface.md)   
 [IDispatchEx::InvokeEx](../../winscript/reference/idispatchex-invokeex.md)