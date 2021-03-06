---
title: Skróty klawiaturowe i myszy dla projektanta klas
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.classdetails.window
helpviewer_keywords:
- class diagrams, keyboard shortcuts
- class diagrams, mouse shortcuts
ms.assetid: c12d8dac-9902-4fde-b721-2a8116da53b7
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: db39f9c58c0fa2f0ea57d94cd1be404173720088
ms.sourcegitcommit: 4c0db930d9d5d8b857d3baf2530ae89823799612
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/10/2018
ms.locfileid: "33957317"
---
# <a name="keyboard-and-mouse-shortcuts-in-the-class-diagram-and-class-details-window"></a>Skróty klawiatury i myszy w oknie Diagram klas i szczegóły klasy

Klawiatury oprócz myszy można użyć do wykonania akcji nawigacji w **Projektant klas** i **szczegółów klasy** okna.

## <a name="use-the-mouse-in-class-designer"></a>Za pomocą myszy w Projektancie klas

Obsługiwane są następujące akcje myszy w diagramach klas:

|Kombinacja myszy|Kontekst|Opis|
|-----------------------|-------------|-----------------|
|Kliknij dwukrotnie|elementy kształtu|Otwiera edytora kodu.|
|Kliknij dwukrotnie|Interfejs typu lizak łącznika|Interfejs typu lizak Rozwiń/Zwiń.|
|Kliknij dwukrotnie|Interfejs typu lizak łącznika etykiety|Wywołuje **Pokaż interfejs** polecenia.|
|Kółka myszy|Diagram klas|Przewiń w pionie.|
|**SHIFT** + kółka myszy|Diagram klas|Przewijane w poziomie.|
|**CTRL** + kółka myszy|Diagram klas|Powiększenia.|
|**CTRL**+**Shift** i kliknięcia|Diagram klas|Powiększenia.|

## <a name="use-the-mouse-in-the-class-details-window"></a>Za pomocą myszy w oknie Szczegóły klasy

Za pomocą myszy, można zmienić wygląd **szczegółów klasy** okno i danych wyświetlanych w następujący sposób:

- Kliknij dowolną komórkę można edytować pozwala edytować zawartość tej komórki. Zmiany są odzwierciedlane we wszystkich miejscach, że dane są przechowywane lub wyświetlane, w tym w **właściwości** okna i w kodzie źródłowym.

- Kliknij dowolną komórkę wiersza powoduje, że **właściwości** okno, aby wyświetlić właściwości dla elementu reprezentowanego przez ten wiersz.

- Aby zmienić szerokość kolumny, przeciągnij granicę po prawej stronie nagłówka kolumny jest szerokości, który ma.

- Można rozwinąć lub zwinąć przedziału lub właściwość węzłów klikając symbole Strzałka w lewo wiersza.

- **Szczegółów klasy** okna oferuje kilka przycisków przy tworzeniu nowych elementów członkowskich w bieżącej klasy oraz przechodzenia między przedziałów członków w **szczegółów klasy** okna siatki.

## <a name="use-the-keyboard-in-class-designer"></a>Używanie klawiatury w Projektancie klas

Obsługiwane są następujące akcje klawiatury w diagramach klas:

|Key|Kontekst|Opis|
|---------|-------------|-----------------|
|**Klawisze strzałek**|Kształty typów wewnątrz|Style drzewa nawigacji na zawartość kształtu (otaczania kształt jest obsługiwane). Lewy i prawy klucze Rozwiń/Zwiń bieżący element Jeśli rozwijania i przejdź do elementu nadrzędnego Jeśli nie (zobacz nawigacji w widoku drzewa szczegółowe zachowania).|
|**Klawisze strzałek**|Kształty najwyższego poziomu|Przenoszenie kształtów na diagramie.|
|**SHIFT**+**klawiszy strzałek**|Kształty typów wewnątrz|Kompilowanie składające się z elementów kształtu, takich jak elementy członkowskie, typy zagnieżdżone lub przedziałów ciągłego zaznaczenia. Te skróty nie obsługują otaczania.|
|**Strona główna**|Kształty typów wewnątrz|Przejdź do tytułu kształtu najwyższego poziomu.|
|**Strona główna**|Kształty najwyższego poziomu|Przejdź do pierwszego kształtu na diagramie.|
|**End**|Kształty typów wewnątrz|Przejdź do ostatniego elementu widoczne wewnątrz kształtu.|
|**End**|Kształty najwyższego poziomu|Przejdź do ostatniego kształt na diagramie.|
|**SHIFT**+**strona główna**|Typ wewnątrz kształtu|Wybiera elementów wewnątrz kształtu, począwszy od bieżącego elementu, a kończąc kształtu tego samego elementu najwyższy.|
|**SHIFT**+**zakończenia**|Typ wewnątrz kształtu|Taki sam jak **Shift**+**Home** , ale w kierunku do góry do dołu.|
|**Wprowadź**|Wszystkie konteksty|Wywołuje domyślną akcję kształtu, który jest również dostępny za pośrednictwem kliknij dwukrotnie. W większości przypadków jest to widok Kod, ale niektóre elementy definiować go inaczej (lizaki, nagłówki przedziału, etykiet interfejsów typu lizak).|
|**+** I **-**|Wszystkie konteksty|W przypadku rozwijania elementem mającym aktualnie fokus, te klucze rozwiń lub Zwiń elementu.|
|**>**|Wszystkie konteksty|W przypadku elementów z elementami podrzędnymi rozszerza elementu, gdy jest zwinięty i przechodzi do pierwszego elementu podrzędnego.|
|**<**|Wszystkie konteksty|Przechodzi do elementu nadrzędnego.|
|**ALT**+**Shift**+**L**|Wewnątrz kształty typów + kształtów typu.|Przechodzi do interfejs typu lizak aktualnie wybranego kształtu, jeśli jest obecny.|
|**ALT**+**Shift**+**B**|Wewnątrz kształty typów + kształtów typu.|Jeśli listę typów podstawowych jest wyświetlany dla kształtu typu i ma więcej niż jeden element, to Przełącza stan rozszerzenia listy (Zwiń/Rozwiń).|
|**Usuwanie**|Typ i komentarza kształtów|Wywołuje **usunąć z diagramu** polecenia.|
|**Usuwanie**|Na wszystkich innych urządzeń.|Wywołuje **usunąć z kodu** polecenia (elementy członkowskie, parametry, skojarzenia, dziedziczenia, etykiet interfejsów typu lizak).|
|**CTRL**+**usunąć**|Wszystkie konteksty|Wywołuje **usunąć z kodu** polecenia wyboru.|
|**Karta**|Wszystkie konteksty|Przechodzi do następnego podrzędnych w tym samym elemencie nadrzędnym (obsługuje zawijania).|
|**SHIFT**+**kartę**|Wszystkie konteksty|Powoduje przejście do poprzedniego podrzędnych w tym samym elemencie nadrzędnym (obsługuje zawijania).|
|**SPACJA**|Wszystkie konteksty|Włącza/wyłącza wybór dla bieżącego elementu.|

## <a name="use-the-keyboard-in-the-class-details-window"></a>Używanie klawiatury w okno Szczegóły klasy

> [!NOTE]
> Następujące powiązań klucza zostały wybrane do specjalnie, aby używane środowisko przypominało środowisko wpisywanie kodu.

Aby przejść za pomocą następujących klawiszy **szczegółów klasy** okno:

|||
|-|-|
|Key|Wynik|
|**,** (przecinek)|Jeśli kursor znajduje się w wierszu parametru, wpisz przecinek przenosi kursor do pola nazwy parametru dalej. Jeśli kursor znajduje się w ostatnim wierszu parametru metody, powoduje przeniesienie kursora prowadzącego do \<Dodaj parametr > pola, które umożliwia utworzenie nowego parametru.<br /><br /> Jeśli kursor znajduje się w innym miejscu w **szczegółów klasy** oknie dosłownie wpisując przecinek dodaje przecinka w bieżącym polu.|
|**;**  (średnik) lub **)** (nawiasu zamykającego)|Przenieś kursor do następnego wiersza elementu członkowskiego w polu nazwy **szczegółów klasy** okna siatki.|
|**Karta**|Przesuwa kursor do następnego pola, najpierw przenoszenie od lewej do prawej, a następnie góry do dołu. Jeśli kursor jest przenoszona z pola, w którym został wpisany tekst, **szczegółów klasy** przetwarza tekst i zapisuje go, jeśli nie generuje błędu.<br /><br /> Czy kursor znajduje się na puste pole takich jak \<Dodaj parametr >, Tab przenosi je do pierwszego pola następnego wiersza.|
|**SPACJA**|Przesuwa kursor do następnego pola, najpierw przenoszenie od lewej do prawej, a następnie góry do dołu. Czy kursor znajduje się na puste pole takich jak \<Dodaj parametr >, powoduje przeniesienie do pierwszego pola następnego wiersza. Należy pamiętać, że \<miejsca > wpisane natychmiast po przecinek jest ignorowana.<br /><br /> Jeśli kursor znajduje się w polu podsumowania Summary, miejsce na wpisanie dodaje znak odstępu.<br /><br /> Jeśli kursor znajduje się w kolumnie Ukryj danego wiersza, miejsce na wpisanie przełącza wartość wyboru Ukryj.|
|**CTRL**+**kartę**|Przełącz na inne okno dokumentu. Na przykład zmienić **szczegółów klasy** okno, aby otworzyć pliku kodu.|
|**ESC**|Jeśli rozpoczęto wpisać tekst w polu, naciskając klawisz ESC działa jako klucz cofania, przywrócenie zawartość pola jego poprzednią wartość. Jeśli okno Szczegóły klasy ogólne fokus, ale nie określonej komórki ma fokus, naciskając klawisz ESC przenosi fokus od **szczegółów klasy** okna.|
|**Strzałka w górę** i **Strzałka w dół**|Te klucze kursor jest wiersz po wierszu w pionie **szczegółów klasy** okna siatki.|
|**Strzałka w lewo**|Jeśli kursor znajduje się w kolumnie Nazwa, naciskając klawisz strzałki w lewo Zwija bieżący węzeł w hierarchii (jeśli jest on otwarty).|
|**Strzałka w prawo**|Jeśli kursor znajduje się w kolumnie Nazwa, naciskając klawisz strzałki w prawo rozwija bieżący węzeł w hierarchii (jeśli jest zwinięte).|

## <a name="see-also"></a>Zobacz także

- [Utworzyć i skonfigurować elementy członkowskie typu](creating-and-configuring-type-members.md)