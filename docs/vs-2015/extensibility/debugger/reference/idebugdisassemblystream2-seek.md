---
title: IDebugDisassemblyStream2::Seek | Dokumentacja firmy Microsoft
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
- IDebugDisassemblyStream2::Seek
helpviewer_keywords:
- IDebugDisassemblyStream2::Seek
ms.assetid: afec3008-b1e0-4803-ad24-195dbfb6497e
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b718412793271d96a8c8a22bb8c69997c3305cdc
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42685899"
---
# <a name="idebugdisassemblystream2seek"></a>IDebugDisassemblyStream2::Seek
[!INCLUDE[vs2017banner](../../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [IDebugDisassemblyStream2::Seek](https://docs.microsoft.com/visualstudio/extensibility/debugger/reference/idebugdisassemblystream2-seek).  
  
Przesuwa wskaźnik odczytu strumienia dezasemblacji daną liczbę instrukcji względem określonej pozycji.  
  
## <a name="syntax"></a>Składnia  
  
```cpp#  
HRESULT Seek(   
   SEEK_START          dwSeekStart,  
   IDebugCodeContext2* pCodeContext,  
   UINT64              uCodeLocationId,  
   INT64               iInstructions  
);  
```  
  
```csharp  
int Seek(   
   enum_SEEK_START    dwSeekStart,  
   IDebugCodeContext2 pCodeContext,  
   ulong              uCodeLocationId,  
   long               iInstructions  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `dwSeekStart`  
 [in] Wartość z zakresu od [SEEK_START](../../../extensibility/debugger/reference/seek-start.md) wyliczenie, który określa względne położenie, aby rozpocząć wyszukiwanie.  
  
 `pCodeContext`  
 [in] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) obiekt reprezentujący kontekst kodu, który operacji wyszukiwania będzie względne. Ten parametr jest używany tylko wtedy, gdy `dwSeekStart`  =  `SEEK_START_CODECONTEXT`; w przeciwnym razie ten parametr jest ignorowany i może być wartością null.  
  
 `uCodeLocationId`  
 [in] Identyfikator lokalizacji kodu operacji wyszukiwania będzie względne. Ten parametr jest używany, jeśli `dwSeekStart`  =  `SEEK_START_CODELOCID`; w przeciwnym razie ten parametr jest ignorowany i może być równa 0. Zobacz sekcję Spostrzeżenia, aby [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md) metoda opis identyfikator lokalizacji kodu.  
  
 `iInstructions`  
 [in] Liczbę instrukcji, aby przenieść względem pozycji określonej w `dwSeekStart`. Ta wartość może być ujemna na przesunąć się do tyłu.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli operacja się powiedzie, zwraca `S_OK`. Zwraca `S_FALSE` Jeśli pozycji wyszukiwania do punktu poza listy dostępnych instrukcji. W przeciwnym razie zwraca kod błędu.  
  
## <a name="remarks"></a>Uwagi  
 Jeśli do pozycji przed początkiem listy wyszukiwania, pierwsza instrukcja na liście jest równa pozycji odczytu. Jeśli Zobacz do pozycji od końca listy, pozycję odczytu ustawiono do ostatniej instrukcji na liście.  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [SEEK_START](../../../extensibility/debugger/reference/seek-start.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [GetCodeLocationId](../../../extensibility/debugger/reference/idebugdisassemblystream2-getcodelocationid.md)

