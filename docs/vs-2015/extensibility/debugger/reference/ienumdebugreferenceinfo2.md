---
title: IEnumDebugReferenceInfo2 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- IEnumDebugReferenceInfo2
helpviewer_keywords:
- IEnumDebugReferenceInfo2
ms.assetid: 7ed01441-686f-4032-8268-a4c750f19f85
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 891022c12d3fe463c165653b5bf0b054efa751d5
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42683911"
---
# <a name="ienumdebugreferenceinfo2"></a>IEnumDebugReferenceInfo2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IEnumDebugReferenceInfo2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugreferenceinfo2).  
  
Ten interfejs wylicza [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury.  
  
## <a name="syntax"></a>Składnia  
  
```  
IEnumDebugReferenceInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Aparat debugowania (DE) implementuje ten interfejs, w ramach wsparcia dla odwołania do obiektów w pamięci. Ten interfejs musi można zaimplementować tylko wtedy, gdy odwołania są obsługiwane.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Visual Studio wywołania [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md) uzyskać ten interfejs.  
  
## <a name="methods-in-vtable-order"></a>Metody w Vtable kolejności  
 W poniższej tabeli przedstawiono metody `IEnumDebugReferenceInfo2`.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-next.md)|Pobiera określoną liczbę [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktur w kolejności wyliczenia.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-skip.md)|Pomija określoną liczbę [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktur w kolejności wyliczenia.|  
|[Resetuj](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-reset.md)|Resetuje sekwencji wyliczenia na początku.|  
|[Klon](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-clone.md)|Tworzy moduł wyliczający, który zawiera ten sam stan wyliczenia jako bieżącego modułu wyliczającego.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugreferenceinfo2-getcount.md)|Pobiera liczbę [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md) struktury w moduł wyliczający.|  
  
## <a name="remarks"></a>Uwagi  
 Odwołanie jest zasadniczo typu i adres właściwości jest nazwa, typ i adres. Odwołanie będzie się powtarzać, tak długo, jak określony obiekt istnieje w pamięci. Zobacz [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) Aby uzyskać więcej informacji.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_REFERENCE_INFO](../../../extensibility/debugger/reference/debug-reference-info.md)   
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugreference2-enumchildren.md)

