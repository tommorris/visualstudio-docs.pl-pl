---
title: Debugowanie i proces hostingu | Dokumentacja firmy Microsoft
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
helpviewer_keywords:
- debugging [Visual Studio], hosting process
- hosting process
ms.assetid: d0f0b9a6-2a6e-463d-b6ea-9518ee727933
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5cc008f12f4312df2d63f019a0d33a7b727e5ae
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631163"
---
# <a name="debugging-and-the-hosting-process"></a>Debugowanie i proces hostingu
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [debugowanie i proces hostingu](https://docs.microsoft.com/visualstudio/debugger/debugging-and-the-hosting-process).  
  
Procesu hostingu Visual Studio zwiększa wydajność debugera i włącza nowe funkcje debugera, takich jak debugowanie częściowego zaufania i Obliczanie wyrażenia czasu projektowania. Jeśli chcesz, możesz wyłączyć procesu hostingu. Aby uzyskać więcej informacji, zobacz [porady: wyłączanie procesu hostingu](../ide/how-to-disable-the-hosting-process.md). W poniższych sekcjach opisano niektóre różnice między debugowania i bez procesu hostingu.  
  
## <a name="partial-trust-debugging-and-click-once-security"></a>Częściowego zaufania, debugowania i kliknij przycisk — raz zabezpieczeń  
 Debugowanie częściowego zaufania wymaga procesu hostingu. Jeśli wyłączysz procesu hostingu, debugowanie częściowego zaufania nie będzie działać nawet, jeśli włączona jest funkcja zabezpieczeń częściowego zaufania **zabezpieczeń** strony **właściwości projektu**. Aby uzyskać więcej informacji, zobacz [porady: wyłączanie procesu hostingu](../ide/how-to-disable-the-hosting-process.md) i [porady: debugowanie aplikacji częściowej zaufania](../debugger/how-to-debug-a-partial-trust-application.md).  
  
## <a name="design-time-expression-evaluation"></a>Obliczanie wyrażenia czasu projektowania  
 Zawsze wyrażenia czasu projektowania używa procesu hostingu. Wyłączanie hostingu przetworzyć w **właściwości projektu** wyłącza Obliczanie wyrażenia czasu projektowania dla projektów biblioteki klas. Obliczanie wyrażenia czasu projektowania dla innych typów projektów nie jest wyłączone. Zamiast tego program Visual Studio uruchamia rzeczywiste pliki wykonywalne i używa go na potrzeby oceny czasu projektowania bez procesu hostingu. Różnica ta może wygenerować różne wyniki.  
  
## <a name="appdomaincurrentdomainfriendlyname-differences"></a>Różnice AppDomain.CurrentDomain.FriendlyName  
 `AppDomain.CurrentDomain.FriendlyName` Zwraca różne wyniki, w zależności od tego, czy jest włączona procesu hostingu. Jeśli wywołasz `AppDomain.CurrentDomain.FriendlyName` przy użyciu procesu hostingu włączone, zwraca *nazwa_aplikacji*`.vhost.exe`. Jeśli wywołasz ją procesu hostingu wyłączone, funkcja zwraca *nazwa_aplikacji*`.exe`.  
  
## <a name="assemblygetcallingassemblyfullname-differences"></a>Assembly.GetCallingAssembly(). Różnice imię i nazwisko  
 `Assembly.GetCallingAssembly().FullName` Zwraca różne wyniki, w zależności od tego, czy jest włączona procesu hostingu. Jeśli wywołasz `Assembly.GetCallingAssembly().FullName` przy użyciu procesu hostingu włączone, zwraca `mscorlib`. Jeśli wywołasz `Assembly.GetCallingAssembly().FullName` przy użyciu procesu hostingu wyłączone, funkcja zwraca nazwę aplikacji.  
  
## <a name="see-also"></a>Zobacz też  
 [Proces hostingu (vshost.exe)](../ide/hosting-process-vshost-exe.md)   
 [Porady: debugowanie aplikacji częściowej relacji zaufania](../debugger/how-to-debug-a-partial-trust-application.md)   
 [Instrukcje: Wyłączanie procesu hostingu](../ide/how-to-disable-the-hosting-process.md)



