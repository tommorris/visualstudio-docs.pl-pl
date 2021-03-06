---
title: Jak można debugować funkcje API systemu Windows? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.api
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging [C++], Windows API functions
- NT symbols and debugging Windows API functions
- Windows API functions, debugging
- Windows API, debugging API functions
- APIs, debugging
ms.assetid: 7c126f57-62ab-4d94-9805-632d696ba1f0
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 7cc765c6da62973469280e97759fbab566ca6f37
ms.sourcegitcommit: 1ab675a872848c81a44d6b4bd3a49958fe673c56
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/10/2018
ms.locfileid: "44281679"
---
# <a name="how-can-i-debug-windows-api-functions"></a>Jak można debugować funkcje API systemu Windows?
Jeśli chcesz debugować funkcja interfejsu API Windows, która zawiera symbole NT załadowane, wykonaj następujące czynności.  
  
### <a name="to-set-a-breakpoint-on-a-windows-api-function-with-nt-symbols-loaded"></a>Aby ustawić punkt przerwania w funkcji Windows API z symbole NT załadowane  
  
-   Podaj nazwę funkcji wraz z nazwą biblioteki DLL, w której znajduje się funkcja. W 32-bitowego kodu formularz dekorowane nazwy funkcji. Aby ustawić punkt przerwania na **MessageBeep**, na przykład, należy wprowadzić następujące czynności.  
  
    ```cpp
    {,,USER32.DLL}_MessageBeep@4  
    ```  
  
     Aby uzyskać nazwę z atrybutami, zobacz [wyświetlania nazw Ozdobionych](https://msdn.microsoft.com/library/f79e2717-a4db-4d12-a689-69830cce2be0).  
  
## <a name="see-also"></a>Zobacz też  
 [Debugowanie kodu natywnego — często zadawane pytania](../debugger/debugging-native-code-faqs.md)   
 [Debugowanie kodu natywnego](../debugger/debugging-native-code.md)
