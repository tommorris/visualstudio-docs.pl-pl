---
title: IDebugPortEx2 | Dokumentacja firmy Microsoft
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
- IDebugPortEx2
helpviewer_keywords:
- IDebugPortEx2 interface
ms.assetid: 144724d0-38ee-4c9b-87ca-8a504371182b
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 091cad434d4674e568afa5cf09eb05d8cb729735
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682480"
---
# <a name="idebugportex2"></a>IDebugPortEx2
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugPortEx2](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugportex2).  
  
Ten interfejs umożliwia sesji debugowanie kontrolki manager (SDM), programów i procesów uruchomionych na porcie.  
  
## <a name="syntax"></a>Składnia  
  
```  
IDebugPortEx2 : IUnknown  
```  
  
## <a name="notes-for-implementers"></a>Uwagi dotyczące implementacji  
 Dostawcy niestandardowego portu implementuje ten interfejs dla tego samego obiektu, który implementuje [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md).  
  
## <a name="notes-for-callers"></a>Uwagi dotyczące wywoływania  
 Wywołania SDM [QueryInterface](http://msdn.microsoft.com/library/62fce95e-aafa-4187-b50b-e6611b74c3b3) na `IDebugPort2` interfejsu w celu uzyskania tego interfejsu.  
  
## <a name="methods-in-vtable-order"></a>Metody w Vtable kolejności  
 W poniższej tabeli przedstawiono metody `IDebugPortEx2`.  
  
|Metoda|Opis|  
|------------|-----------------|  
|[LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md)|Uruchamia plik wykonywalny.|  
|[ResumeProcess](../../../extensibility/debugger/reference/idebugportex2-resumeprocess.md)|Wznawia wykonanie procesu.|  
|[CanTerminateProcess](../../../extensibility/debugger/reference/idebugportex2-canterminateprocess.md)|Określa, czy Proces może zostać zakończone.|  
|[TerminateProcess](../../../extensibility/debugger/reference/idebugportex2-terminateprocess.md)|Kończy proces.|  
|[GetPortProcessId](../../../extensibility/debugger/reference/idebugportex2-getportprocessid.md)|Pobiera identyfikator procesu samego portu.|  
|[GetProgram](../../../extensibility/debugger/reference/idebugportex2-getprogram.md)|Pobiera program skojarzony z węzłem programu.|  
  
## <a name="remarks"></a>Uwagi  
 Ten interfejs jest zwykle prywatnych między SDM i dostawcy numery portów.  
  
 Jeśli to konieczne, aparat debugowania (DE) można wyszukać ten interfejs [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) interfejsu przekazany do [LaunchSuspended](../../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) i użyj [LaunchSuspended](../../../extensibility/debugger/reference/idebugportex2-launchsuspended.md) do uruchomienia programu. To nie to wymagane, jednak i DE można zrobić, niezależnie od rodzaju należy ją wykonać, aby uruchomić program żądania.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: portpriv.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Interfejsy podstawowe](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)

