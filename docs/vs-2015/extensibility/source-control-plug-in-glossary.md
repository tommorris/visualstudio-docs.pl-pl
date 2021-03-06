---
title: Słownik wtyczki kontroli źródła | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- glossary [Visual Studio SDK]
- source control plug-ins, glossary
ms.assetid: f224bbc9-38fc-4c80-ab09-51dcc8969f8e
caps.latest.revision: 12
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 69bb35df7f03294e0ece6c7a7d4306d8cdf4f03b
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42682817"
---
# <a name="source-control-plug-in-glossary"></a>Słownik wtyczki kontroli źródła
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [słownik wtyczki kontroli źródła](https://docs.microsoft.com/visualstudio/extensibility/source-control-plug-in-glossary).  
  
Następujące przydatne terminów i definicje odnoszą się do dokumentacji zestawu SDK wtyczki kontroli źródła.  
  
## <a name="definitions"></a>Definicje  
 Ewidencjonowanie  
 Po użytkownik wprowadzi zmiany do kopii roboczej, użytkownik musi wysłać zmiany z kopii roboczej w repozytorium kontroli źródła centralnej. Spowoduje to utworzenie nowej wersji pliku, który jest dostępny dla innych użytkowników. Ten proces jest nazywany zaewidencjonowania.  
  
 Wyewidencjonuj  
 Czynność żądania jako kopia robocza zawartości z repozytorium, z informacją o tym repozytorium zgodne z zamiarami użytkownika go zmodyfikować. Kopia robocza odzwierciedla stan projektu, począwszy od tej chwili, który został wyewidencjonowany.  
  
 Klient  
 Program, który korzysta z systemu kontroli kodu źródłowego. Na potrzeby niniejszej dokumentacji jest środowiska IDE programu Visual Studio.  
  
 Komentarz  
 Komunikat opisujący zmiany, które użytkownika mogą dołączać do poprawki, gdy jest wykonywana operacja kontroli źródła.  
  
 Konflikt  
 Sytuacja, gdy dwóch użytkowników próbuje zaewidencjonować zmiany w tym samym regionie, w tym samym pliku. Zwykle muszą być wykonywane scalanie.  
  
 Katalog  
 Folder lokalny po stronie klienta jest określone jako katalog. Jest to kopia, w której użytkownik faktycznie sprawia, że zmiany. Może istnieć wiele kopii roboczych danego projektu; Zazwyczaj każdy Deweloper ma swoją kopię.  
  
 Pobierz  
 Operacja pobrania łączy użytkownika kopia robocza bądź na bieżąco z kopią repozytorium. W przeciwieństwie do wyewidencjonowania get jest wykonywane, gdy użytkownik po prostu wymaga najnowszej kopii, ale zamierza nie wprowadzaj żadnych zmian.  
  
 Historia  
 Zazwyczaj znajduje się podsumowanie wszystkich wyewidencjonowania, elementy do zaewidencjonowania, aktualizacje, tagi i wydań w repozytorium kontroli źródła.  
  
 IDE  
 Zazwyczaj odnosi się do programu Visual Studio zintegrowane środowisko projektowe. Jednakże można także zapoznać się inne środowiska klienta, które rozpoznają API wtyczki kontroli źródła.  
  
 Scal  
 Proces, podczas których źródła dwóch lub więcej plików kodu są łączone w celu utworzenia nowego pliku, który zawiera wszystkie funkcje z poprzednich plików. Takie podejście jest w kontroli wersji którym co najmniej dwóch deweloperzy pracują na plikach jednocześnie.  
  
 Projekt  
 Folder kontroli źródła jest często określane jako projekt. To nie ma żadnych relacji z projektów i rozwiązań w programie Visual Studio.  
  
 Dodatek typu plug-in  
 Biblioteka DLL, która zapewnia funkcji kontroli źródła, implementując interfejs API wtyczki kontroli źródła.  
  
 Repozytorium  
 Kopia główna, gdzie system kontroli źródła przechowuje historię pełną wersję projektu. Każdy projekt ma dokładnie jedno repozytorium.  
  
 Poprawki  
 Zatwierdzoną zmianę w historii pliku lub zestawu plików. Zmiana jest jeden migawki w projekcie stale zmieniających.  
  
## <a name="see-also"></a>Zobacz też  
 [Wtyczki kontroli źródła](../extensibility/source-control-plug-ins.md)

