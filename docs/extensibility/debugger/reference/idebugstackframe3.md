---
title: IDebugStackFrame3 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IDebugStackFrame3
helpviewer_keywords:
- IDebugStackFrame3 interface
ms.assetid: 39af2f57-0a01-42b8-b093-b7fbc61e2909
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 635b53bf63eb83cc868e4bf9b7d5fbb31fe5aa08
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31120625"
---
# <a name="idebugstackframe3"></a>IDebugStackFrame3
Ten interfejs stanowi rozszerzenie [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) do obsługi wyjątków przechwycone.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugStackFrame3 : IDebugStackFrame2  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Aparat debugowania (DE) implementuje ten interfejs dla tego samego obiektu, który implementuje [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md) interfejs do obsługi wyjątków przechwycone.  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Wywołanie [QueryInterface](/cpp/atl/queryinterface) na `IDebugStackFrame2` interfejs do uzyskania tego interfejsu.  
  
## <a name="methods-in-vtable-order"></a>Metody w kolejności Vtable  
 Oprócz dziedziczone z metody [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md), `IDebugStackFrame3` udostępnia następujące metody.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md)|Obsługuje wyjątek dla bieżącej ramki stosu przed żadnych wyjątków regularne.|  
|[GetUnwindCodeContext](../../../extensibility/debugger/reference/idebugstackframe3-getunwindcodecontext.md)|Zwraca kontekst kodu, gdyby wystąpić odwijania stosu.|  
  
## <a name="remarks"></a>Uwagi  
 Wyjątek przechwycone oznacza, że debuger może przetwarzać wyjątek przed wszystkie procedury obsługi wyjątków normalne są nazywane w czasie wykonywania. Zasadniczo przechwycenia wyjątek oznacza czas uruchomienia podawać, że jest obecny, nawet wtedy, gdy nie ma obsługi wyjątków.  
  
 [InterceptCurrentException](../../../extensibility/debugger/reference/idebugstackframe3-interceptcurrentexception.md) jest wywoływana podczas wszystkich zdarzeń wywołania zwrotnego normalne wyjątków (Jedynym wyjątkiem jest, jeśli są debugowanie kodu trybu mieszanego (zarządzanych i niezarządzanych kodu), w którym to przypadku wyjątku nie może zostać przechwycone podczas Wywołanie zwrotne ostatniej szansy). Jeśli DE nie implementuje `IDebugStackFrame3`, lub DE zwraca błąd z IDebugStackFrame3::`InterceptCurrentException` (takie jak `E_NOTIMPL`), a następnie debuger będzie obsługiwać wyjątek zwykle.  
  
 Przechwycenie wyjątku, debuger może zezwolić użytkownikowi na zmianę stanu debugowanego programu i wznowienia wykonywania w momencie, gdy wyjątek został zgłoszony.  
  
> [!NOTE]
>  Przechwycone wyjątki są dozwolone tylko w kodzie zarządzanym, oznacza to, w programie, który działa w obszarze środowiska uruchomieniowego języka wspólnego (CLR).  
  
 Aparat debugowania wskazuje, że obsługuje przechwytywaniu wyjątków przez ustawienie "metricExceptions" na wartość 1 w czasie wykonywania za pomocą `SetMetric` funkcji. Aby uzyskać więcej informacji, zobacz [pomocników zestawu SDK dla debugowania](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md).  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: msdbg.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy Core](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [Pomocnicy zestawu SDK do debugowania](../../../extensibility/debugger/reference/sdk-helpers-for-debugging.md)