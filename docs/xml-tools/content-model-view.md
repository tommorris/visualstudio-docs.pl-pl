---
title: Widok modelu zawartości projektanta schematu XML
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: reference
ms.assetid: e8db7c7d-31cf-479e-9dcc-299759891795
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 0d7f04c482149cbc063a3788dd6be44c643bae6a
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/04/2018
ms.locfileid: "34751796"
---
# <a name="content-model-view"></a>Widok modelu zawartości

Widok modelu zawartości zawiera graficzną reprezentację schematu lokalne i globalne węzłów i ich składników, w tym proste i złożone typy, elementy grupy modeli, atrybuty i grupy atrybutów. Komentarze XML i instrukcji przetwarzania nie można wyświetlić w widoku modelu zawartości. Widok modelu zawartości zawiera dwa panele: **obszaru roboczego** panelu, który zawiera listy węzłów w [roboczym projektanta schematu XML](../xml-tools/xml-schema-designer-workspace.md)i powierzchni projektu, do której możesz zobaczyć modelu zawartości schematu węzły, które są wybrane w **obszaru roboczego** panelu. Widok modelu zawartości zawiera również narzędzi Projektanta schematu XML i na pasku stron nadrzędnych.

 Na poniższej ilustracji **obszaru roboczego** panel zawiera sześciu węzłów schematu. `purchaseOrder` Jest wybrany węzeł w **obszaru roboczego** panelu i jest wyświetlany w powierzchnię projektu.

 ![Widok modelu zawartości projektanta schematu XML](../xml-tools/media/xsddesigner_contentmodelview.gif)

## <a name="workspace-panel"></a>Panel obszaru roboczego

 Po dodaniu węzły do obszaru roboczego listy węzłów pojawią się w **obszaru roboczego** panelu widoku modelu zawartości. Po wybraniu węzłów w **obszaru roboczego** panelu, będą widoczne na powierzchnię projektu widoku modelu zawartości. Usuń węzły z obszaru roboczego, użyj narzędzi Projektanta XSD, **obszaru roboczego** panel menu kontekstowego, lub **usunąć** klucza.

 Aby uzyskać informacje dotyczące dodawania węzłów, zobacz sekcję "Dodawanie węzłów do obszaru roboczego, w [roboczym projektanta schematu XML](../xml-tools/xml-schema-designer-workspace.md).

## <a name="design-surface"></a>Dzięki powierzchni projektowej

 Po wybraniu węzła w **obszaru roboczego** panelu, jest ona dodawana do powierzchni projektowej widoku modelu zawartości, której można wyświetlić szczegóły węzła.

 Model zawartości węzła jest reprezentowany przez drzewo graficznego rozwijania z elementów i atrybutów znajdujących się jako węzły drzewa. Domyślnie rozwinięte jest tylko jeden poziom. Inne informacje, takie jak kompozytory, wpisz nazwy grup i innych kontenery są umieszczane w pionowy pasek (po rozwinięciu) wzdłuż elementy i atrybuty, które należy ująć one. Po dwukrotnym kliknięciu pionowy pasek, staje się poziome i zwija drzewa. Po dwukrotnym kliknięciu poziomy pasek pionowy staje się i rozwijane w drzewie. Zaznaczenie pionowy pasek zaznaczenie wszystkich węzłów w kontenerze. Ekspanderów znajdujących pojawiają się po prawej stronie węzła, jeśli element może być rozwinięte lub zwinięte.

 Jeśli pole pozostanie puste, powierzchnię projektu edytora XML **Eksploratora schematu XML**, i znak wodny są pokazywane. *Znaku wodnego* znajduje się lista łącza do widoków projektanta XSD. Jeśli zestaw schemat zawiera błędy, na końcu listy jest wyświetlany następujący tekst: "Użyj listy błędów możesz wyświetlać i naprawiać błędy w zestawie".

## <a name="breadcrumb-bar"></a>Pasek nawigacją

 Na pasku stron nadrzędnych w dolnej części widoku modelu zawartości zawiera położenie wybranego węzła w zestawie schematów.

## <a name="context-menus"></a>Menu kontekstowe

 Po kliknięciu prawym przyciskiem myszy element na powierzchni projektu lub **obszaru roboczego** panelu, zostanie wyświetlone menu kontekstowego. W poniższej tabeli opisano opcje, które są dostępne dla warstwy projektowania widoku modelu zawartości.

|Opcja|Opis|
|------------|-----------------|
|**Pokaż w Eksploratorze schematu XML**|Umieszcza fokus na Eksploratora schematu i zaznacza węzła zestawu schematu.|
|**Pokaż w widoku wykresu**|Przełącza do widoku wykresu.|
|**Generowanie przykładowy kod XML**|Dostępne tylko dla elementów globalnego. Generuje przykładowy plik XML dla elementu globalnego.|
|**Pokaż dokumentacji**|Pokazuje lub ukrywa zawartość węzła adnotacji/dokumentacji.|
|**Eksportuj Diagram jako obraz**|Zapisuje plik XPS powierzchnię projektu.|
|**Kod widoku**|Otwiera plik, który zawiera wybrany węzeł w edytorze XML. Element, który wybrano w **Eksploratora schematu XML** jest zaznaczony w edytorze XML.|
|**Okno właściwości**|Otwiera **właściwości** okna (Jeśli nie jest jeszcze otwarty). To okno wyświetla informacje o węźle.|

 W poniższej tabeli opisano opcje, które są dostępne dla **obszaru roboczego** panelu.

|Opcja|Opis|
|------------|-----------------|
|**Pokaż w Eksploratorze schematu XML**|Umieszcza fokus na Eksploratora schematu i zaznacza węzła zestawu schematu.|
|**Pokaż w widoku wykresu**|Przełącza do widoku wykresu.|
|**Wyczyść obszaru roboczego**|Czyści obszaru roboczego i powierzchnię projektu.|
|**Usuń z obszaru roboczego**|Usuwa wybrane węzły z obszaru roboczego i powierzchnię projektu.|
|**Usuń wszystkie oprócz wybór z obszaru roboczego**|Usuwa węzły, które nie są wybrane z obszaru roboczego i powierzchnię projektu.|
|**Generowanie przykładowy kod XML**|Dostępne tylko dla elementów globalnego. Generuje przykładowy plik XML dla elementu globalnego.|
|**Zaznacz wszystko**|Wybiera wszystkie węzły w **obszaru roboczego** panelu.|
|**Kod widoku**|Otwiera plik, który zawiera wybrany węzeł w edytorze XML. Element, który wybrano w **Eksploratora schematu XML** jest zaznaczony w edytorze XML.|
|**Okno właściwości**|Otwiera **właściwości** okna (Jeśli nie jest jeszcze otwarty). To okno wyświetla informacje o węźle.|

## <a name="properties-window"></a>Okno właściwości

 Użyj menu kontekstowego, aby otworzyć początkowo **właściwości** okna. Domyślnie **właściwości** okno jest wyświetlane w prawym dolnym rogu programu Visual Studio. Po kliknięciu węzła, który jest renderowany w widoku modelu zawartości właściwości tym węźle są wyświetlane w **właściwości** okna.

## <a name="xsd-designer-toolbar"></a>Pasek narzędzi Projektanta XSD

 Następujące przyciski narzędzi Projektanta XSD są włączone, gdy widok modelu zawartości jest aktywny.

 ![Narzędzi Projektanta schematu XML](../xml-tools/media/xsdcontentmodelviewtoolbar.gif)

|Opcja|Opis|
|------------|-----------------|
|**Pokaż widok początkowy**|Przełącza do [Start widoku](../xml-tools/start-view.md). Ten widok jest możliwy za pomocą skrótu klawiaturowego: **Ctrl**+**1**.|
|**Pokaż widok modelu zawartości**|Przełącza do [widok modelu zawartości](../xml-tools/content-model-view.md). Ten widok jest możliwy za pomocą skrótu klawiaturowego: **Ctrl**+**2**.|
|**Pokaż widok wykresu**|Przełącza do [widoku wykresu](../xml-tools/graph-view.md). Ten widok jest możliwy za pomocą skrótu klawiaturowego: **Ctrl**+**3**.|
|**Wyczyść obszaru roboczego**|Czyści obszaru roboczego i powierzchnię projektu.|
|**Usuń z obszaru roboczego**|Usuwa wybrane węzły z obszaru roboczego i powierzchnię projektu.|
|**Usuń wszystkie oprócz wybór z obszaru roboczego**|Usuwa węzły, które nie są wybrane z obszaru roboczego i powierzchnię projektu.|
|**Pokaż dokumentacji**|Pokazuje lub ukrywa zawartość węzła adnotacji/dokumentacji.|

## <a name="panscroll"></a>Przesuwanie/przewijania

 Można przesuwać powierzchnię projektu za pomocą pasków przewijania lub trzymając **Ctrl** klucza podczas kliknij i przeciągnij mysz. Przesuwa powierzchnię projektu przy użyciu kliknij i przeciągnij, kursor zmienia się cztery krzyżowej strzałki w czterech kierunków.

## <a name="undoredo"></a>Cofnij/ponów

 Możliwość Cofnij/Ponów jest włączona w widoku modelu zawartości następujące akcje:

-   Dodawanie jednego węzła przy przeciągania i upuszczania.

-   Dodawanie wielu węzłów w oknie wyników wyszukiwania w Eksploratorze schematu.

-   Dodawanie węzłów z widoku startowego.

-   Usunięcie jednego lub wielu węzłów.

## <a name="zoom"></a>Powiększenie

 Powiększenia znajduje się w prawym dolnym rogu widoku modelu zawartości.

 Powiększenie mogą być kontrolowane w następujący sposób:

-   Przytrzymując **Ctrl** klucza i wirowania myszy koła, gdy wskaźnik myszy znajduje się na powierzchni widoku modelu zawartości.

-   Za pomocą suwaka. Suwak pokazuje bieżący poziom powiększenia.

Suwak powiększenia jest nieprzezroczysta podczas zaznacz go, umieść kursor nad nim lub użyj **Ctrl** kółko myszy, aby powiększyć; w innym czasie, jest niewidoczny.

## <a name="xml-editor-integration"></a>Integracja edytora XML

 Można przełączyć w obu kierunkach między **projektanta XSD** oraz edytora XML za pomocą menu kontekstowego.

 Jeśli wprowadzisz zmiany do schematu w edytorze XML zestawu zmiany są synchronizowane w widoku modelu zawartości. Aby uzyskać więcej informacji, zobacz [integracji z edytora XML](../xml-tools/integration-with-xml-editor.md).

## <a name="see-also"></a>Zobacz także

- [Obszar roboczy projektanta schematu XML](../xml-tools/xml-schema-designer-workspace.md)