---
title: IEnumDebugPropertyInfo2 | Dokumentacja firmy Microsoft
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
- IEnumDebugPropertyInfo2
helpviewer_keywords:
- IEnumDebugPropertyInfo2
ms.assetid: fdea8262-40b8-473e-88ba-639e4c4648e6
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 3becd764a391e3f3516886efd630b06125fc211f
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42695630"
---
# <a name="ienumdebugpropertyinfo2"></a>IEnumDebugPropertyInfo2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IEnumDebugPropertyInfo2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/ienumdebugpropertyinfo2).  
  
Ten interfejs wylicza [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury.  
  
## <a name="syntax"></a>Składnia  
  
```  
IEnumDebugPropertyInfo2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Aparat debugowania (DE) implementuje ten interfejs do przedstawiania informacji dla określonej właściwości.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Wywołaj [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md) uzyskać ten interfejs reprezentujący element podrzędny elementu określonej właściwości. Wywołaj [enumproperties —](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md) uzyskać ten interfejs reprezentujący właściwości ramki określonego stosu.  
  
## <a name="methods-in-vtable-order"></a>Metody w Vtable kolejności  
 W poniższej tabeli przedstawiono metody `IEnumDebugPropertyInfo2`.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[Next](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-next.md)|Pobiera określoną liczbę [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktur w kolejności wyliczenia.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-skip.md)|Pomija określoną liczbę [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktur w kolejności wyliczenia.|  
|[Resetuj](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-reset.md)|Resetuje sekwencji wyliczenia na początku.|  
|[Klon](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-clone.md)|Tworzy moduł wyliczający, który zawiera ten sam stan wyliczenia jako bieżącego modułu wyliczającego.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugpropertyinfo2-getcount.md)|Pobiera liczbę [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md) struktury w moduł wyliczający.|  
  
## <a name="remarks"></a>Uwagi  
 Ogólnie rzecz biorąc właściwość jest hierarchią informacje, które mogą obejmować nazwę, wartość, adresu i typ, a także inne informacje odpowiednie dla skojarzonej właściwości obiektu lub stosu ramki. Zobacz [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) Aby uzyskać więcej informacji.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)   
 [DEBUG_PROPERTY_INFO](../../../extensibility/debugger/reference/debug-property-info.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)   
 [EnumChildren](../../../extensibility/debugger/reference/idebugproperty2-enumchildren.md)   
 [Enumproperties —](../../../extensibility/debugger/reference/idebugstackframe2-enumproperties.md)

