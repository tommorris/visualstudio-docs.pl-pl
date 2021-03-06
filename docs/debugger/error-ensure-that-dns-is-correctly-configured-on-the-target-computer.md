---
title: 'Błąd: Upewnij się, że usługa DNS jest poprawnie skonfigurowany na komputerze docelowym | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.callback_dns_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d2d945376f093e7df437751127c544b349458fd
ms.sourcegitcommit: 0bf2aff6abe485e3fe940f5344a62a885ad7f44e
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/27/2018
ms.locfileid: "37056101"
---
# <a name="error-ensure-that-dns-is-correctly-configured-on-the-target-computer"></a>Błąd: upewnij się, że DNS jest prawidłowo skonfigurowany na komputerze docelowym
Podczas próby czy zdalne debugowanie, może pojawić się następujący komunikat o błędzie:  
  
```cmd
Error: The Visual Studio Remote Debugger on the target computer cannot connect back to this computer. Ensure that DNS is correctly configured on the target computer.  
```  
  
 Ten błąd wystąpi, gdy komputer docelowy nie może rozpoznać nazwy komputera-hosta debugera programu Visual Studio. Sprawdź ustawienia DNS na komputerze docelowym.  
  
-   Informacje o wyświetlaniu w Windows 8.1, Vista, Windows 7, Windows Server 2012, Windows Server 2008 lub Windows Server 2008 R2, ustawienia DNS, w tym: na **Start** menu, wybierz **Pomoc i obsługa techniczna** , a następnie wyszukaj **Zmienianie ustawień protokołu TCP/IP**.  
  
-   Aby uzyskać więcej informacji, przejdź do [witryny sieci web Microsoft Windows](http://go.microsoft.com/fwlink/?LinkId=252720) i wyszukaj **Zmienianie ustawień protokołu TCP/IP**.  
  
 Jeśli nie możesz rozwiązać problemu z usługą DNS, można spróbować uruchomić zdalnego debugera przy użyciu innego konta. Ten błąd występuje tylko wtedy, gdy są uruchomienie zdalnego debugera w ramach konta Usługa sieciowa lub systemu lokalnego. Uruchomienie zdalnego debugera w ramach innego konta, może używać uwierzytelniania NTLM, które nie wymagają DNS. . Opis odpowiedniej procedury znajduje się w temacie [błąd: usługa zdalnego debugera Visual Studio na komputerze docelowym nie może połączyć się ponownie z tym komputerem](../debugger/error-the-visual-studio-remote-debugger-service-on-the-target-computer-cannot-connect-back-to-this-computer.md).
