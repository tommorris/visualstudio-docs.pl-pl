---
title: IDebugArrayObject::GetElement | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugArrayObject::GetElement
helpviewer_keywords:
- IDebugArrayObject::GetElement method
ms.assetid: 08b44341-7bf1-4a8c-8b79-98ae5785b195
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e2e10eced58835044220da0650712dacb131ada3
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31109941"
---
# <a name="idebugarrayobjectgetelement"></a>IDebugArrayObject::GetElement
Pobiera element tablicy.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT GetElement(   
   DWORD          dwIndex,  
   IDebugObject** ppElement  
);  
```  
  
```csharp  
int GetElement(  
   [In] uint dwIndex,   
   out IDebugObject ppElement  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwIndex`  
 [in] Indeks elementu.  
  
 `ppElement`  
 [out] Zwraca [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) interfejs, który reprezentuje element.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca wartość S_OK; w przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Ta metoda widzi wszystkie elementy tablicy obiektów jako tablicą jednowymiarową, nawet jeśli obiekt tablicy jest wielowymiarowy. Przykładowo, podana tablicy `myarray[3][2][6]` i `dwIndex` parametru 20, ta metoda zwróci element ze `myarray[1][1][2]`, a `dwIndex` parametru 21 zwróci element ze `myarray[1][1][3]`. Użyj [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) metodę, aby określić całkowitą liczbę elementów w tablicy.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)