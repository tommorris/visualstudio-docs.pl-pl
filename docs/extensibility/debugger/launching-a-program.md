---
title: Uruchamianie programu | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debug engines, launching
- programs, launching
ms.assetid: 6857e9c6-e44a-468a-afa4-f7c4a0b77844
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 5c56fd1c82c02428f9f6b67c1d715f1c61588858
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231840"
---
# <a name="launch-a-program"></a>Uruchom program
Użytkownicy, którzy chcą do debugowania programu, można nacisnąć klawisz **F5** do uruchamiania debugera z poziomu środowiska IDE. Spowoduje to rozpoczęcie szereg zdarzeń, które ostatecznie powoduje IDE nawiązywania połączenia z aparatu debugowania (DE), który z kolei jest połączony, lub dołączone do programu w następujący sposób:  
  
1.  IDE najpierw wywołuje pakietu można pobrać ustawień debugowania aktywnego projektu tego rozwiązania z projektem. Ustawienia obejmują katalog początkowy, zmienne środowiskowe, portu, w którym program będzie uruchamiany i DE służące do utworzenia programu, jeśli określony. Te ustawienia są przekazywane do pakietu debugowania.  
  
2.  Jeśli określono Niemcy, DE wywołania systemu operacyjnego, aby uruchomić program. Uruchamianie programu, w wyniku ładuje środowiska czasu wykonywania programu. Na przykład jeśli program został napisany w kodzie MSIL, środowisko uruchomieniowe języka wspólnego wywoływane w celu uruchomienia programu.  
  
     —lub—  
  
     Jeśli nie określono DE, port wywołuje systemu operacyjnego, aby uruchomić program, który powoduje, że środowisko wykonawcze programu do załadowania.  
  
    > [!NOTE]
    >  Jeśli DE jest używany do uruchomienia programu, duże prawdopodobieństwo, że tego samego DE zostanie dołączony do programu.  
  
3.  W zależności od tego, czy DE lub port uruchamiany program Niemcy lub środowiska wykonawczego następnie tworzy opis programu lub węzeł i powiadamia port, na którym działa program.  
  
    > [!NOTE]
    >  Zalecane jest, środowiska wykonawczego Utwórz węzeł program ponieważ węzeł program jest uproszczone reprezentacja program, który może być debugowany. Nie ma potrzeby ładowania całego DE tak, aby utworzyć i zarejestrować węzła programu. Jeśli DE jest przeznaczony do uruchamiania w trakcie IDE, ale nie środowiska IDE jest uruchomione, musi istnieć składnik, który można dodać węzła programu do portu.  
  
 Nowo utworzony programu, oraz innych programów, związane z niezwiązanych ze sobą, uruchomić lub powiązany z tym samym środowisku IDE, tworzenia sesji debugowania.  
  
 Programistycznie, gdy użytkownik najpierw naciśnie **F5**, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]firmy debugowanie pakietu wymaga pakietu z projektem, (który jest skojarzony z typem program półtora) za pośrednictwem <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg.DebugLaunch%2A> metody, która z kolei związanej z formularzami <xref:Microsoft.VisualStudio.Shell.Interop.VsDebugTargetInfo2> struktury z ustawieniami debugowania aktywnego projektu tego rozwiązania. Ta struktura jest przekazywany z powrotem do pakietu debugowania za pomocą wywołania <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugger2.LaunchDebugTargets2%2A> metody. Debugowanie pakietu tworzy następnie Menedżer debugowania sesji (SDM), co powoduje uruchomienie programu silniki debugowania i wszystkie skojarzone debugowania.  
  
 Jeden z argumentów przekazanych do SDM jest identyfikator GUID DE ma być używany do uruchomienia programu.  
  
 Jeśli nie jest identyfikatorem GUID DE `GUID_NULL`, SDM wspólnie tworzy DE, a następnie wywołuje jego [LaunchSuspended](../../extensibility/debugger/reference/idebugenginelaunch2-launchsuspended.md) metodę, aby uruchomić program. Na przykład, jeśli program został napisany w kodzie natywnym `IDebugEngineLaunch2::LaunchSuspended` prawdopodobnie będzie wywoływać `CreateProcess` i `ResumeThread` (funkcji Win32), aby uruchomić program.  
  
 Uruchamianie programu, w wyniku środowiska wykonawczego programu jest ładowany. Następnie tworzy DE lub środowiska wykonawczego [IDebugProgramNode2](../../extensibility/debugger/reference/idebugprogramnode2.md) współpracować w celu opisania program i przekazuje tego interfejsu [AddProgramNode](../../extensibility/debugger/reference/idebugportnotify2-addprogramnode.md) powiadomić port, który program jest uruchomione.  
  
 Jeśli `GUID_NULL` jest przekazywany, a następnie port uruchamia program. Po uruchomieniu programu środowiska wykonawczego tworzy `IDebugProgramNode2` współpracować w celu opisania program i przekazuje go do `IDebugPortNotify2::AddProgramNode`. Powiadamia ten port, na którym działa program. Następnie SDM dołącza aparat debugowania do uruchomionego programu.  
  
## <a name="in-this-section"></a>W tej sekcji  
 [Powiadamianie portu](../../extensibility/debugger/notifying-the-port.md)  
 W tym artykule wyjaśniono, co się stanie po uruchomieniu programu i numer portu jest powiadamiany.  
  
 [Dołączanie po uruchomieniu](../../extensibility/debugger/attaching-after-a-launch.md)  
 Dokumenty, gdy sesja debugowania jest gotowy do dołączenia DE do programu.  
  
## <a name="related-sections"></a>Sekcje pokrewne  
 [Zadania debugowania](../../extensibility/debugger/debugging-tasks.md)  
 Zawiera łącza do różnych zadań debugowania, takie jak uruchamianie programu i wyrażeń.