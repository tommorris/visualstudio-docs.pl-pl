---
title: EVALFLAGS90 | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- EVALFLAGS90 enumeration
ms.assetid: 64fb0139-8b04-4726-b52c-db2e04d65498
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 120bf38afbf05f367757de3a5e453cab8b4311b1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31102710"
---
# <a name="evalflags90"></a>EVALFLAGS90
Wylicza prawidłowe wartości dla flagi sterujące Obliczanie wyrażenia. To wyliczenie rozszerza [EVALFLAGS](../../../extensibility/debugger/reference/evalflags.md) wyliczenia.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
typedef DWORD EVALFLAGS90;  
```  
  
```csharp  
public enum enum_EVALFLAGS90  
{  
   // VS 8.0 values  
   EVAL90_RETURNVALUE                 = 0x0002,  
   EVAL90_NOSIDEEFFECTS               = 0x0004,  
   EVAL90_ALLOWBPS                    = 0x0008,  
   EVAL90_ALLOWERRORREPORT            = 0x0010,  
   EVAL90_FUNCTION_AS_ADDRESS         = 0x0040,  
   EVAL90_NOFUNCEVAL                  = 0x0080,  
   EVAL90_NOEVENTS                    = 0x1000,  
   EVAL90_DESIGN_TIME_EXPR_EVAL       = 0x2000,  
   EVAL90_ALLOW_IMPLICIT_VARS         = 0x4000,  
  
   // Values added in VS 9.0  
   EVAL90_FORCE_EVALUATION_NOW        = 0x8000  
};  
```  
  
#### <a name="parameters"></a>Parametry  
 EVAL90_RETURNVALUE  
 Określa przyjąć wartość zwracaną, jeśli istnieje.  
  
 EVAL90_NOSIDEEFFECTS  
 Określa, że efekty uboczne nie jest dozwolone.  
  
 EVAL90_ALLOWBPS  
 Określa zatrzymywania punktów przerwania.  
  
 EVAL90_ALLOWERRORREPORT  
 Określa, że raportów o błędach do hosta mogą być. Głównie używane do obliczania wyrażenia w skrypcie w programie Internet Explorer.  
  
 EVAL90_FUNCTION_AS_ADDRESS  
 Funkcje wymusza ma zostać obliczone jako adresy, zamiast wywoływania funkcji.  
  
 EVAL90_NOFUNCEVAL  
 Funkcja zapobiega oceniane. Rozważmy na przykład `int` tokenu w wyrażeniu `myExpression(int) + 10`. Ta funkcja może zostać poprawnie oceniony jako adres, ale nie jako wartość.  
  
 EVAL90_NOEVENTS  
 Flaga wskazująca, że zdarzeń występujących podczas obliczania wyrażenia nie powinny być wysyłane do menedżera sesji debugowania (SDM) lub do środowiska IDE.  
  
 EVAL90_DESIGN_TIME_EXPR_EVAL  
 Włącza Obliczanie wyrażenia czasu projektowania.  
  
 EVAL90_ALLOW_IMPLICIT_VARS  
 Zezwala na niejawne tworzenia zmiennej.  
  
 EVAL90_FORCE_EVALUATION_NOW  
 Ocena wymusza natychmiastową. Jest to przydatne, gdy obsługi żądania, takie jak żądanie użytkownika.  
  
## <a name="requirements"></a>Wymagania  
 Nagłówek: Msdbg90.h  
  
 Namespace: Microsoft.VisualStudio.Debugger.Interop  
  
 Assembly: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>Zobacz też  
 [Wyliczenia](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)