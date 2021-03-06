---
title: 'Ostrzeżenie o zabezpieczeniach: Debuger musi wykonać polecenie niezaufane | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-debug
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.debug.sourceserver.securityalert
dev_langs:
- FSharp
- VB
- CSharp
- C++
ms.assetid: e5c004b3-b364-4098-ac98-770076ca9981
caps.latest.revision: 16
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b7582004372c5b3de7fdcc23398e4aacf128fcbb
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42627719"
---
# <a name="security-warning-debugger-must-execute-untrusted-command"></a>Ostrzeżenie o zabezpieczeniach: Debuger musi wykonać niezaufaną komendę
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [ostrzeżenie o zabezpieczeniach: debuger musi wykonać polecenie niezaufane](https://docs.microsoft.com/visualstudio/debugger/security-warning-debugger-must-execute-untrusted-command).  
  
To okno dialogowe ostrzeżenia pojawia się podczas korzystania z serwera źródłowego. Oznacza, że polecenie, które debugger musi wykonać, aby uzyskać kod źródłowy nie jest na liście zaufanych poleceń dla serwera źródłowego, zawartej w pliku srcsvr.ini. Jeśli jest to prawidłowe polecenie, można dodać go do pliku srcsvr.ini. W przeciwnym razie nie należy uruchamiać go. Aby uzyskać więcej informacji, zobacz [Określ symboli (.pdb) i plików źródłowych](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md).  
  
## <a name="message-text"></a>Tekst komunikatu  
 **Debuger musi wykonać następujące polecenie niezaufane, aby uzyskać kod źródłowy z serwera źródłowego.**  
  
 **Jeśli pliku symboli, debugowania (\*.pdb) jest spoza znanego i zaufanego źródła, to polecenie może być nieprawidłowe lub niebezpieczne do uruchomienia.**  
  
 **Czy chcesz uruchomić to polecenie?**  
  
## <a name="uielement-list"></a>Lista elementów UI  
 Pole tekstowe  
 Polecenie z pliku .pdb do uruchomienia.  
  
 Uruchom  
 Zezwalaj na polecenie do uruchomienia.  
  
 Nie uruchamiaj  
 Zatrzymaj wykonywanie polecenia i pobieranie plików z serwera źródłowego.  
  
## <a name="see-also"></a>Zobacz też  
 [Określ symboli (.pdb) i pliki źródłowe](../debugger/specify-symbol-dot-pdb-and-source-files-in-the-visual-studio-debugger.md)   
 [Zabezpieczenia debugera](../debugger/debugger-security.md)   
 [Serwer źródłowy](http://msdn.microsoft.com/library/windows/desktop/ms680641\(v=vs.85\).aspx)



