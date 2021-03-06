---
title: Strona opcji, debugowanie — właściwości węzła | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 564cc8b2-0084-420e-b560-200cc5621a7e
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 128e4719775a4ce9d06214547936110ed88b7a14
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42628558"
---
# <a name="options-page-debugging-node-properties"></a>Strona opcji, debugowanie — Właściwości węzła
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [Strona opcji, debugowanie — właściwości węzła](https://docs.microsoft.com/visualstudio/ide/reference/options-page-debugging-node-properties).  
  
  
W poniższych tabelach opisano strony (lub kolekcje właściwości), są skojarzone z **debugowanie** kategorii `DTE.Properties("Debugging", <Property Page>)` z **opcje** okno dialogowe.  
  
## <a name="general"></a>Ogólne  
 `DTE.Properties("Debugging", "General")`  
  
|Nazwa elementu właściwości|Wartość|Opis|  
|------------------------|-----------|-----------------|  
|PromptOnBreakpointDelete|Get/Set (wartość logiczna)|Określa, czy debuger wyświetla monit o zgodę przed usunięciem wszystkich punktów przerwania w projekcie.|  
|BreakAllProcesses|Get/Set (wartość logiczna)|Określa, czy debuger przerywa wszystkie procesy gdy jeden proces przerywa.|  
|BreakAtBoundaries|Get/Set (wartość logiczna)|Określa, czy debuger przerywa wykonywanie, gdy wyjątek przecina obramowanie domen aplikacji lub między zarządzane i kodu natywnego.|  
|EnableAddressLevelDebugging|Get/Set (wartość logiczna)|Określa, czy są włączone funkcje debugowania na poziomie adresów.|  
|ShowDisassemblyIfNoSource|Get/Set (wartość logiczna)|Określa, czy debuger wyświetla kod dezasemblacji, gdy kod źródłowy jest niedostępny.|  
|EnableBreakpointFilters|Get/Set (wartość logiczna)|Określa, czy punkt przerwania filtrowanie jest włączone.|  
|EnableExceptionAssistant|Get/Set (wartość logiczna)|Określa, czy Asystent wyjątków jest używana do obsługi wyjątków zarządzanych.|  
|UnwindCallstack|Get/Set (wartość logiczna)|Określa, czy debuger rozwija stos wywołań dla nieobsługiwanego wyjątku.|  
|EnableJustMyCode|Get/Set (wartość logiczna)|Określa, czy tylko mój kod jest włączona dla języka C# i kodu języka Visual Basic.|  
|ShowAllMembers|Get/Set (wartość logiczna)|Dla obiektów niebędących użytkownikami Określa, czy debuger wyświetla wszystkie elementy członkowskie obiektu w oknach zmiennych. Ta opcja nie obowiązuje, jeśli nie włączono opcję tylko mój kod.|  
|WarnIfNoUserCode|Get/Set (wartość logiczna)|Określa, czy debuger emituje ostrzeżenie, gdy użytkownik próbuje dołączyć do procesu, który nie ma kodu użytkownika. Ta opcja nie obowiązuje, jeśli nie włączono opcję tylko mój kod.|  
|EnablePropertyEvaluation|Get/Set (wartość logiczna)|Określa, czy debuger ocenia automatycznie właściwości i niejawne funkcja wywołuje w kodzie zarządzanym.|  
|CallStringConversion|Get/Set (wartość logiczna)|Określa, czy debuger niejawnie wywołuje funkcję konwersji ciągu na obiektach w oknach zmiennych. Ta opcja dotyczy tylko kodu C# i JScript.|  
|EnableSourceServer|Get/Set (wartość logiczna)|Określa, czy debuger może kod dostępu z serwera źródłowego.|  
|PrintSourceServerDiagnostics|Get/Set (wartość logiczna)|Określa, czy w oknie danych wyjściowych zawiera komunikatów diagnostycznych związane z serwera źródłowego. Ta opcja nie obowiązuje, jeśli nie włączono dostęp do serwera źródłowego.|  
|HighlightEntireLine|Get/Set (wartość logiczna)|Określa, czy debuger wyróżnia cały wiersz dla punktów przerwania i bieżącej instrukcji.|  
|RequireSourceToMatch|Get/Set (wartość logiczna)|Określa, czy debuger wymaga plików źródłowych, aby dokładnie dopasować oryginalną wersję podczas otwierania plików do debugowania.|  
|RedirectOutputToImmediate|Get/Set (wartość logiczna)|Określa, czy dane wyjściowe z okna dane wyjściowe jest przekierowywany do okna bezpośrednie.|  
|ShowRawVariableStructure|Get/Set (wartość logiczna)|Określa, czy obiektach w oknach zmiennych są wyświetlane w postaci pierwotnej.|  
|SuppressJitOptimization|Get/Set (wartość logiczna)|Dla kodu zarządzanego Określa, czy Optymalizacja just in time jest pomijane przez debuger.|  
|WarnIfNoSymbols|Get/Set (wartość logiczna)|Określa, czy debuger wyświetla ostrzeżenie, jeśli brak symboli debugowania są dostępne w przypadku, gdy proces jest uruchamiany.|  
|WarnIfScriptDisabled|Get/Set (wartość logiczna)|Określa, czy debuger wyświetla ostrzeżenie, jeśli debugowanie skryptów jest wyłączone, gdy proces jest uruchamiany.|  
|ShowMarkersForAllThreads|Get/Set (wartość logiczna)|Określa, czy znaczniki wątku są wyświetlane przez debuger.|  
|StepOverPropertiesAndOperators|Get/Set (wartość logiczna)|Określa, czy Przekrocz nad właściwościami i operatorami w wyłącznie dla kodu zarządzanego.|  
  
## <a name="edit-and-continue"></a>Edytuj i kontynuuj  
 `DTE.Properties("Debugging", "EditAndContinue")`  
  
|Nazwa elementu właściwości|Wartość|Opis|  
|------------------------|-----------|-----------------|  
|EnableEditAndContinue|Get/Set (wartość logiczna)|Określa, czy włączono Edytuj i Kontynuuj. Ta opcja ma zastosowanie do wszystkich języków, które obsługują Edytuj i Kontynuuj.|  
|InvokedByCommands|Get/Set (wartość logiczna)|Określa, czy Edytuj i Kontynuuj automatycznie stosuje zmiany kodu, gdy użytkownik wybierze polecenie debugowania **kroku** lub **Kontynuuj**. Ta opcja dotyczy tylko kodu natywnego.|  
|InvokedByCommandsAskFirst|Get/Set (wartość logiczna)|Określa, czy Edytuj i Kontynuuj monituje użytkownika o zezwolenie na stosowanie zmian kodu, gdy użytkownik wybierze polecenie debugowania **kroku** lub **Kontynuuj**. Ta opcja dotyczy tylko kodu natywnego.|  
|WarnAboutStaleCode|Get/Set (wartość logiczna)|Określa, czy debuger generuje komunikat ostrzegawczy, gdy wykonywanie kodu nieaktualny lub nieodświeżony, spowodowałoby Edytuj i Kontynuuj. Ta opcja dotyczy tylko kodu natywnego.|  
|RelinkChangesOnStop|Get/Set (krótki)|Określa, czy program Visual Studio relinks zmian w kodzie zastosowanych przez Edytuj i Kontynuuj po zatrzymaniu wykonywania aplikacji. Ta opcja dotyczy tylko kodu natywnego.|  
|AllowPrecompiling|Get/Set (krótki)|Określa, czy może załadować prekompilowane nagłówki w tle Edytuj i Kontynuuj. Ta opcja dotyczy tylko kodu natywnego.|  
  
## <a name="just-in-time"></a>just in time  
 `DTE.Properties("Debugging", "JustInTime")`  
  
|Nazwa elementu właściwości|Wartość|Opis|  
|------------------------|-----------|-----------------|  
|JitManaged|Get/Set (wartość logiczna)|Określa, czy debugowanie just in Time jest włączone dla kodu zarządzanego.|  
|JitNative|Get/Set (wartość logiczna)|Określa, czy debugowanie just in Time jest włączone dla kodu natywnego.|  
|JitScript|Get/Set (wartość logiczna)|Określa, czy debugowanie just in Time jest włączone dla kodu skryptu.|  
  
## <a name="native"></a>Natywne  
 `DTE.Properties("Debugging", "Native")`  
  
|Nazwa elementu właściwości|Wartość|Opis|  
|------------------------|-----------|-----------------|  
|LoadDllExports|Get/Set (wartość logiczna)|Określa, czy debuger wczytuje tabel eksportu bibliotek DLL.|  
|EnableRPC|Get/Set (wartość logiczna)|Określa, czy debuger wejść do COM zdalnych wywołań procedur.|  
  
## <a name="see-also"></a>Zobacz też  
 [Kontrolowanie ustawień opcji](http://msdn.microsoft.com/library/a09ed242-7494-4cde-bbd1-7a8ec617965d)   
 [Określanie nazw elementów właściwości na stronach opcji](http://msdn.microsoft.com/library/d450422d-47c7-4eeb-9f9f-3286264bc5aa)   
 [Strona opcji, czcionki i kolory — właściwości węzła](../../ide/reference/options-page-fonts-and-colors-node-properties.md)   
 [Strona opcji, Edytor tekstu — właściwości węzła](../../ide/reference/options-page-text-editor-node-properties.md)   
 [Ogólne, debugowanie, okno dialogowe Opcje](../../debugger/general-debugging-options-dialog-box.md)   
 [Edytuj i Kontynuuj, debugowanie, opcje — Okno dialogowe](http://msdn.microsoft.com/library/009d225f-ef65-463f-a146-e4c518f86103)   
 [Just-In-Time, debugowanie, okno dialogowe Opcje](../../debugger/just-in-time-debugging-options-dialog-box.md)



