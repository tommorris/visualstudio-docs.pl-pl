---
title: Instrukcje stop w Visual Basic | Dokumentacja firmy Microsoft
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
- FSharp
- VB
- CSharp
- C++
- VB
helpviewer_keywords:
- End statements
- breakpoints, Stop statements
- debugging managed code, Stop statements vs breakpoints
- Stop statements, about Stop statements
- debugging [Visual Basic], Stop statements vs. breakpoints
ms.assetid: 4ad3fe5c-3dfb-4913-b2eb-a0b635751c18
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fcb4e3018dad53ef869748a4394363dba78f71c
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629497"
---
# <a name="stop-statements-in-visual-basic"></a>Instrukcje stop w Visual Basic
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [instrukcje Stop w Visual Basic](https://docs.microsoft.com/visualstudio/debugger/stop-statements-in-visual-basic).  
  
Instrukcja języka Visual Basic, Zatrzymaj zapewnia programowy alternatywa ustawienie punktu przerwania. Jeśli debuger napotka instrukcję Stop, przerywa wykonywanie programu (przejdzie do trybu przerwania). Programiści języka C# można osiągnąć ten sam efekt przy użyciu wywołania do System.Diagnostics.Debugger.Break.  
  
 Ustaw lub usuń instrukcję Stop, edytując kodu źródłowego. Nie można ustawić lub wyczyścić instrukcje Stop — przy użyciu poleceń debugera, jak w przypadku punktu przerwania.  
  
 W przeciwieństwie do instrukcji End instrukcji Stop zresetować zmiennych lub nie powrót do trybu projektowania. Kontynuuj można wybrać z menu debugowanie, aby kontynuować uruchamianie aplikacji.  
  
 Po uruchomieniu aplikacji w języku Visual Basic poza debugerem instrukcję Stop spowoduje uruchomienie debugera, jeśli Just-in-Time, debugowanie jest włączone. Jeśli Just-in-Time debugowanie nie jest włączone, instrukcja Stop zachowuje się tak, jakby był to End — instrukcja, Kończenie wykonywania. Wystąpi zdarzenie nie QueryUnload lub zwolnij, więc należy usunąć wszystkie instrukcje Stop w wersji aplikacji Visual Basic. Aby uzyskać więcej informacji, zobacz [debugowanie just in Time](../debugger/just-in-time-debugging-in-visual-studio.md).  
  
 Aby uniknąć konieczności usuwania instrukcje Stop, można użyć kompilacji warunkowej:  
  
```  
#If DEBUG Then  
   Stop  
#Else  
   ' Don't stop  
#End If  
```  
  
 Innym sposobem jest używanie instrukcji asercji zamiast instrukcji zatrzymania. Instrukcja Debug.Assert przerywa wykonywanie tylko wtedy, gdy określony warunek nie jest spełniony i zostanie automatycznie usunięta po zbudować wersję przeznaczoną do. Aby uzyskać więcej informacji, zobacz [potwierdzenia w kodzie zarządzany](../debugger/assertions-in-managed-code.md). Jeśli chcesz, aby instrukcję Assert, która zawsze przerywa wykonywanie w wersji do debugowania, można to zrobić:  
  
```  
Debug.Assert(false)  
```  
  
 Jeszcze inną alternatywą jest użycie metody Debug.Fail:  
  
```  
Debug.Fail("a clever output string goes here")  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Zabezpieczenia debugera](../debugger/debugger-security.md)   
 [C#, F # i typów projektów języka Visual Basic](../debugger/debugging-preparation-csharp-f-hash-and-visual-basic-project-types.md)   
 [Debugowanie zarządzanego kodu](../debugger/debugging-managed-code.md)



