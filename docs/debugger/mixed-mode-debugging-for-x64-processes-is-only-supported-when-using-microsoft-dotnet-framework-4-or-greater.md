---
title: Mieszany tryb debugowania x64 procesów jest obsługiwana tylko w przypadku korzystania z programu Microsoft.NET Framework 4 lub nowszej | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.error.interop_unsupported_x64
dev_langs:
- CSharp
- VB
- FSharp
- C++
ms.assetid: b7495655-54c0-4315-8422-43bf63b8c22e
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: a6d58713da9a4c809d5f9c3db6f7157a699a467f
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44284097"
---
# <a name="mixed-mode-debugging-for-x64-processes-is-only-supported-when-using-microsoftnet-framework-4-or-greater"></a>Debugowanie w trybie mieszanym dla procesów x64 jest obsługiwane tylko w przypadku korzystania z programu Microsoft .NET Framework 4 lub nowszej wersji
.NET framework, które wersje starsze niż 4 nie zapewniają obsługę debugowanie w trybie mieszanym x64 procesów. Oznacza to, że nie możesz wejść z kodu zarządzanego do kodu macierzystego lub kodu natywnego do zarządzanego kodu podczas debugowania.  
  
### <a name="workarounds"></a>Rozwiązania  
  
-   Zaktualizuj projekt, aby użyć programu Microsoft .NET Framework 4 lub nowszej.  
  
     —lub—  
  
     Debugowanie kodu zarządzanego i natywnego w oddzielnych sesji debugowania.  
  
     —lub—  
  
     Debugowanie kodu mieszanego jako proces 32-bitowych, zgodnie z opisem w poniższych procedurach.  
  
### <a name="to-change-the-platform-to-32-bit-visual-basic-or-c"></a>Aby zmienić platformy 32-bitowe (Visual Basic lub C#)  
  
1.  W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy projekt, a następnie kliknij przycisk **właściwości**.  
  
2.  Na stronach właściwości kliknij przycisk **skompilować** lub **debugowania** kartę.  
  
3.  Kliknij przycisk **platformy** i wybierać x86 listę platform.  
  
     Domyślnie domyślne Kompilatory języka Visual Basic i C# generuje kod wymagany do uruchomienia na dowolny procesor CPU. Na komputerze 64-bitowych te pliki binarne Uruchom jako procesów 64-bitowych. Aby uruchomić proces 32-bitowy, należy wybrać **Win32**, a nie **AnyCPU**.  
  
### <a name="to-change-the-platform-to-32-bit-cc"></a>Aby zmienić platformy 32-bitowych (C/C++)  
  
1.  W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy projekt, a następnie kliknij przycisk **właściwości**.  
  
2.  Na stronach właściwości kliknij przycisk **platformy** i wybierz listę platform systemu Win32.  
  
### <a name="to-correct-this-error"></a>Aby poprawić ten błąd  
  
-   Zobacz [Konfigurowanie debugowania SQL](/previous-versions/visualstudio/visual-studio-2010/s4sszxst(v=vs.100)).  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie aplikacji 64-bitowych](../debugger/debug-64-bit-applications.md)