---
title: Metody mapowania dla stosu wywołań podczas debugowania w programie Visual Studio.
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-modeling
ms.topic: conceptual
f1_keywords:
- vs.progression.debugwithcodemaps
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords:
- call stacks, code maps
- Call Stack window, mapping calls
- debugging [Visual Studio], diagramming the call stack
- call stacks, mapping
- Call Stack window, visualizing
- debugging code visually
- debugging [Visual Studio], mapping the call stack
- call stacks, visualizing
- debugging, code maps
- Call Stack window, tracing calls visually
- Call Stack window, show on code map
- debugging [Visual Studio], tracing the call stack visually
- debugging [Visual Studio], visualizing the call stack
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e9a1c98007c968f12e220c0fef841e7680f299f7
ms.sourcegitcommit: 4667e6ad223642bc4ac525f57281482c9894daf4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/20/2018
ms.locfileid: "36283197"
---
# <a name="map-methods-on-the-call-stack-while-debugging-in-visual-studio"></a>Metody mapowania dla stosu wywołań podczas debugowania w programie Visual Studio.
Utwórz mapę kodu wizualne śledzenie stosu wywołań podczas debugowania kodu. Można robić notatki na mapie, żeby śledzić, jak zachowuje się kod, przez co można skoncentrować się na wyszukiwaniu błędów.

 ![Debugowanie za pomocą stosy wywołań na mapy kodu](../debugger/media/debuggermap_overview.png)

 Potrzebne są:

-   [Visual Studio Enterprise](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)

-   Kod, który możesz debugować, takich jak Visual C#, Visual Basic, C++, JavaScript lub X ++

 Zobacz:

-   [Wideo: Wizualne debugowanie dzięki integracji debugera w mapie kodu (Channel 9)](http://go.microsoft.com/fwlink/?LinkId=293418)

-   [Mapowanie stosu wywołań](#MapStack)

-   [Wprowadź informacje o kodzie](#MakeNotes)

-   [Zaktualizuj mapy przy następnym stosu wywołań](#UpdateMap)

-   [Dodawanie kodu powiązanego do mapy](#AddRelatedCode)

-   [Znajdź usterki za pomocą mapy](#FindBugs)

-   [FUNKCJA PYTANIA I ODPOWIEDZI](#QA)

 Szczegółowe poleceń i działań można używać podczas pracy z mapy kodu, patrz [przeglądania i zmieniać code map](../modeling/browse-and-rearrange-code-maps.md).

##  <a name="MapStack"></a> Mapowanie stosu wywołań

1.  Rozpocznij debugowanie. (Klawiatury: **F5**)

2.  Po aplikacji wprowadza tryb przerwania lub wkroczyć do funkcji, wybierz **mapy kodu**. (Klawiatury: **Ctrl** + **Shift** + **`**)

     ![Wybierz mapę kodu, aby uruchomić mapowanie stosu wywołań](../debugger/media/debuggermap_choosecodemap.png)

     Bieżący stos wywołań jest wyświetlany w kolorze pomarańczowym na nowej mapie kodu:

     ![Zobacz stos wywołań w mapie kodu](../debugger/media/debuggermap_seeundocallstack.png)

     Mapy automatycznie zaktualizuje przerywając debugowania. Zobacz [zaktualizuj mapy przy następnym stosu wywołań](#UpdateMap).

##  <a name="MakeNotes"></a> Wprowadź informacje o kodzie
 Dodawanie komentarzy do śledzenia, co dzieje się w kodzie. Aby dodać nowy wiersz w komentarzu, naciśnij klawisz **Shift + Return**.

 ![Dodaj komentarz do stos wywołań w mapie kodu](../debugger/media/debuggermap_addcomment.png)

##  <a name="UpdateMap"></a> Zaktualizuj mapy przy następnym stosu wywołań
 Uruchom aplikację do następnego punktu przerwania lub wejścia do funkcji. Mapa dodaje nowy stos wywołań.

 ![Mapy kodu aktualizacji z dalej stosu wywołań](../debugger/media/debuggermap_addclearcallstack.png)

##  <a name="AddRelatedCode"></a> Dodawanie kodu powiązanego do mapy
 Teraz otrzymasz mapy — co dalej? Podczas pracy w języku C# lub Visual Basic, należy dodać elementów, takich jak pola, właściwości i innych metod, aby śledzić, co dzieje się w kodzie.

 Kliknij dwukrotnie metodę, aby wyświetlić jego definicji kodu, lub użyj menu skrótów metody. (Klawiatury: Wybierz metodę mapy, a następnie naciśnij klawisz **F12**)

 ![Przejdź do definicji kodu metody na mapie kodu](../debugger/media/debuggermap_gotocodedefinition.png)

 Dodaj elementy, które chcesz śledzić na mapie.

 ![Pokaż pola w metodach na mapie kodu stosu wywołań](../debugger/media/debuggermap_showfields.png)

> [!NOTE]
>  Domyślnie również dodawanie elementów do mapy dodaje węzłów grupy nadrzędnej, takich jak klasy, przestrzeń nazw i zestawu. Jest to przydatne, można zachować na mapie proste przez wyłączenie tej funkcji przy użyciu **obejmują nadrzędnych** przycisk na pasku narzędzi mapy lub naciskając klawisz **CTRL** podczas dodawania elementów.

 ![Pola powiązane z metody na mapie kodu stosu wywołań](../debugger/media/debuggermap_showedfields.png)

 W tym miejscu można łatwo zobaczyć, które metody wykorzystują te same pola. Ostatnio dodane elementy są wyświetlane w kolorze zielonym.

 Kontynuuj tworzenie mapy, aby zobaczyć więcej kodu.

 ![Zobacz metod korzystających z polem: mapy kodu stosu wywołań](../debugger/media/debuggermap_findallreferences.png)

 ![Metody, które używają pola na mapie kodu stosu wywołań](../debugger/media/debuggermap_foundallreferences.png)

##  <a name="FindBugs"></a> Znajdź usterki za pomocą mapy
 Wizualizacja kodu pomoże w szybszym znalezieniu błędów. Na przykład załóżmy, że w przypadku badania usterki w programie rysowania. Po narysowaniu linii, w przypadku próby cofnięcia nic się nie dzieje, aż do rysowania kolejnej linii.

 Aby ustawić punkty przerwania `clear`, `undo`, i `Repaint` metod, Rozpocznij debugowanie i utworzenia mapy podobne do następującego:

 ![Dodaj inny stos wywołań z mapą kodu](../debugger/media/debuggermap_addpaintobjectcallstack.png)

 Zwróć uwagę, że wszystkie użytkownika gestów w wywołaniu elementu map `Repaint`, z wyjątkiem `undo`. To może wyjaśnić, dlaczego `undo` nie zadziała natychmiast.

 Po naprawić błąd i kontynuować uruchamianie programu mapy dodaje nowe wywołanie z `undo` do `Repaint`:

 ![Dodawanie nowego stosu wywołaniami metody na mapie kodu](../debugger/media/debuggermap_addnewcallforrepaint.png)

##  <a name="QA"></a> FUNKCJA PYTANIA I ODPOWIEDZI

-   **Nie wszystkie wywołania widoczne na mapie. Dlaczego?**

     Domyślnie tylko z własnego kodu zostanie wyświetlone na mapie. Aby wyświetlić kod zewnętrzny, włącz ją **stos wywołań** okno:

     ![Wyświetl kod zewnętrzny, w oknie stosu wywołań](../debugger/media/debuggermap_callstackmenu.png)

     lub wyłącz **Włącz opcję tylko mój kod** w programie Visual Studio opcji debugowania:

     ![Pokaż zewnętrznego kodu za pomocą okna dialogowego Opcje](../debugger/media/debuggermap_debugoptions.png)

-   **Zmiana mapy wpływa na kod?**

     Zmiana mapy nie wpływa na kod w dowolny sposób. Możesz dowolnie zmienić nazwę, przenieść lub usunąć elementy na mapie.

-   **Co ten komunikat oznacza: "diagramu może być oparty na starszej wersji kodu"?**

     Kod mógł ulec zmianie po ostatniej aktualizacji mapy. Na przykład wywołanie mapy może już nie istnieć w kodzie. Zamknij komunikat, a następnie spróbuj odbudować rozwiązanie przed ponowną aktualizacją mapy.

-   **Metody kontrolowania mapę układu?**

     Otwórz **układu** menu na pasku narzędzi mapy:

    -   Zmiana układu domyślnego.

    -   Aby zatrzymać automatycznie zmienianie rozmieszczenia mapy, wyłącz **automatycznie układ podczas debugowania**.

    -   Aby zmienić kolejność mapy jak najmniejszy, po dodaniu elementów, należy wyłączyć **przyrostową układu**.

-   **Mapy mogą być udostępniać innym użytkownikom?**

     Można eksportować mapę, przesłać ją do innych osób, o ile posiada się Microsoft Outlook, albo zapisać jako swoje rozwiązanie, żeby można je było zaewidencjonować w kontroli wersji Team Foundation.

     ![Mapy kodu stosu wywołań udziału z innymi użytkownikami](../debugger/media/debuggermap_sharewithothers.png)

-   **Jak zatrzymać mapy automatycznie dodawał nowe stosy wywołań**

     Wybierz ![przycisk &#45; Pokaż automatycznie umieszczane w mapie kodu](../debugger/media/debuggermap_automaticupdateicon.gif) na pasku narzędzi mapy. Aby ręcznie dodać bieżącego stosu wywołań do mapy, naciśnij klawisz **Ctrl** + **Shift** + **`**.

     Mapy będzie wyróżnianie istniejących stosy wywołań na mapie podczas debugowania kodu.

-   **Co ikony elementów i strzałki oznaczają?**

     Aby uzyskać więcej informacji na temat elementu, przenieś wskaźnik myszy nad nim i przyjrzyj się do elementu tooltip. Można również sprawdzić **legendy** informacji oznacza każda z ikon.

     ![Co oznaczają ikony na mapie kodu stosu wywołań](../debugger/media/debuggermap_showlegend.png)

 Zobacz:

-   [Mapowanie stosu wywołań](#MapStack)

-   [Wprowadź informacje o kodzie](#MakeNotes)

-   [Zaktualizuj mapy przy następnym stosu wywołań](#UpdateMap)

-   [Dodawanie kodu powiązanego do mapy](#AddRelatedCode)

-   [Znajdź usterki za pomocą mapy](#FindBugs)

## <a name="see-also"></a>Zobacz też

- [Zależności mapy w ramach rozwiązań](../modeling/map-dependencies-across-your-solutions.md)
- [Używanie map kodu do debugowania aplikacji](../modeling/use-code-maps-to-debug-your-applications.md)
- [Wyszukiwanie potencjalnych problemów za pomocą analizatorów mapy kodu](../modeling/find-potential-problems-using-code-map-analyzers.md)
- [Przeglądanie i ponowne rozmieszczanie map kodu](../modeling/browse-and-rearrange-code-maps.md)
