---
title: Zagadnienia dotyczące zwalniania i ponownego ładowania zagnieżdżonych projektów | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- nested projects, unloading and reloading
- projects [Visual Studio SDK], unloading and reloading nested
ms.assetid: 06c3427e-c874-45b1-b9af-f68610ed016c
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c38b50f661ed7ea16c56d9a877b809d2d60dd51c
ms.sourcegitcommit: 206e738fc45ff8ec4ddac2dd484e5be37192cfbd
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/03/2018
ms.locfileid: "39513461"
---
# <a name="considerations-for-unloading-and-reloading-nested-projects"></a>Zagadnienia dotyczące zwalniania i ponownego ładowania zagnieżdżonych projektów

Podczas implementowania typów zagnieżdżonych projektów, można wykonać dodatkowe kroki, jeśli zwolnisz i ponownie Załaduj projekty. Poprawnie o rozwiązaniu zdarzenia, należy poprawnie zgłosić `OnBeforeUnloadProject` i `OnAfterLoadProject` zdarzenia.

Jest jednym z powodów wywołania tych zdarzeń do kontroli kodu źródłowego (SCC). Nie chcesz, aby SCC, aby usunąć elementy z serwera, a następnie dodać je jako *nowe* w przypadku `Get` SCC podczas operacji. W takim przypadku nowy plik będzie można załadować poza SCC. Trzeba zwolnić i załaduj ponownie wszystkie pliki w przypadku, gdy są one różne.

Kod wywołuje kontroli źródła `ReloadItem`. Implementowanie <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> interfejsu do wywołania `OnBeforeUnloadProject` i `OnAfterLoadProject` Usuń projekt i utwórz go ponownie. Po zaimplementowaniu interfejsu w ten sposób SCC jest informowany, projekt został czasowo usunięty i ponownie dodać. W związku z tym, SCC nie działa w projekcie, tak, jakby była projektu *faktycznie* usunięty i ponownie dodani.

## <a name="reload-projects"></a>Pozycja Załaduj ponownie projekty

Aby zapewnić obsługę ponownego ładowania zagnieżdżonych projektów, możesz wdrożyć <xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistHierarchyItem2.ReloadItem%2A> metody. W danej implementacji `ReloadItem`, zamknij zagnieżdżonych projektów, a następnie ponownie utwórz je.

Zwykle po załadowaniu projektu, IDE zgłasza <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnBeforeUnloadProject%2A> i <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> zdarzenia. Dla zagnieżdżonych projektów, które są usuwane i ponowne załadowanie projektu nadrzędnego inicjuje proces nie środowiska IDE. Ponieważ projekt nadrzędny nie zgłaszać zdarzenia rozwiązania oraz środowiska IDE nie ma informacji o inicjowania procesu zdarzenia nie są wywoływane.

Aby obsługiwać ten proces nadrzędny wywoływanych w projekcie `QueryInterface` na <xref:Microsoft.VisualStudio.Shell.Interop.IVsFireSolutionEvents> interfejsu. `IVsFireSolutionEvents` dostępne są funkcje, pasujących do środowiska IDE, aby podnieść `OnBeforeUnloadProject` zdarzeń można zwolnić projektu zagnieżdżonego, a następnie podnieś `OnAfterLoadProject` zdarzenie, aby ponownie załadować projekt.

## <a name="see-also"></a>Zobacz także

- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>
- [Zagnieżdżanie projektów](../../extensibility/internals/nesting-projects.md)