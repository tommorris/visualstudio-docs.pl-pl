---
title: Tworzenie i konfigurowanie zestawów danych w programie Visual Studio
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- typed datasets, creating
- datasets, creating
- datasets, configuring
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a65c1960e1648dce3bb8ff40d1dd6c50534934ff
ms.sourcegitcommit: 3a11feebad45a0dd4ac45efcbfdf172fce46e1de
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39582235"
---
# <a name="create-and-configure-datasets-in-visual-studio"></a>Tworzenie i konfigurowanie zestawów danych w programie Visual Studio

Zestaw danych to zbiór obiektów, które przechowuje dane z bazy danych w pamięci i obsługuje śledzenie zmian, aby umożliwić tworzenie, Odczyt, aktualizowanie i usuwanie operacji (CRUD) na tych danych bez konieczności zawsze być połączone z bazą danych. Zestawy danych zostały zaprojektowane dla prostej *formularzy nad danymi* aplikacji biznesowych. W przypadku nowych aplikacji należy wziąć pod uwagę przy użyciu platformy Entity Framework do przechowywania i modelowania danych w pamięci. Aby pracować z zestawami danych, należy mieć podstawową wiedzę na temat pojęć dotyczących baz danych.

Możesz utworzyć typizowany <xref:System.Data.DataSet> klasy w programie Visual Studio w czasie projektowania za pomocą **Kreatora konfiguracji źródła danych**. Aby uzyskać informacji na temat programowe tworzenie zestawów danych, zobacz [Tworzenie zestawu danych (ADO.NET)](/dotnet/framework/data/adonet/dataset-datatable-dataview/creating-a-dataset).

## <a name="create-a-new-dataset-by-using-the-data-source-configuration-wizard"></a>Utwórz nowy zestaw danych za pomocą Kreatora konfiguracji źródła danych

1.  Na **projektu** menu, kliknij przycisk **Dodaj nowe źródło danych** można uruchomić **Kreatora konfiguracji źródła danych**.

2.  Wybierz typ źródła danych, z którą będą łączyć.

     ![Kreator konfiguracji źródła danych](../data-tools/media/data-source-configuration-wizard.png)

3.  Wybierz bazę danych lub bazy danych, które będą znajdować się źródło danych dla zestawu danych.

     ![Źródła danych wybierz połączenie](../data-tools/media/data-source-choose-a-connection.png)

4.  Wybierz tabele (lub poszczególnych kolumn), procedur przechowywanych, funkcji i widoków z bazy danych, który ma być reprezentowane w zestawie danych.

     ![Wybierz obiekty bazy danych](../data-tools/media/raddata-chose-objects.png)

5.  Kliknij przycisk **Zakończ**.

6.  Zestaw danych jest widoczny jako węzeł w **Eksploratora rozwiązań**.

     ![Zestaw danych w Eksploratorze rozwiązań](../data-tools/media/dataset-in-solution-explorer.png)

     Kliknij ten węzeł, a zestaw danych jest wyświetlana w **Projektanta obiektów DataSet**. Należy pamiętać, że każda tabela w zestawie danych ma skojarzoną `TableAdapter` obiektu, który jest reprezentowany w dolnej części. Karta tabeli jest używany do wypełniania zestawu danych i, opcjonalnie, wysyłanie poleceń do bazy danych.

     ![Projektant obiektów DataSet](../data-tools/media/dataset-designer.png)

7.  Wierszy relacji, które łączą się z tabel reprezentują relacje między tabelami, zgodnie z definicją w bazie danych. Domyślnie ograniczenia klucza obcego w bazie danych są reprezentowane jako relacja tylko przy użyciu aktualizacji i usuwania reguł ustawiony na wartość none. Zazwyczaj jest to czego chcesz. Jednak można kliknąć wiersze, aby wyświetlić **relacji** okno dialogowe, w którym można zmienić zachowanie aktualizacji hierarchicznych. Aby uzyskać więcej informacji, zobacz [relacje w zestawach danych](../data-tools/relationships-in-datasets.md) i [hierarchiczna aktualizacja](../data-tools/hierarchical-update.md).

     ![Okno dialogowe Zestaw danych relacji](../data-tools/media/raddata-relation-dialog.png)

8.  Kliknij tabelę, tabeli karty lub nazwa kolumny w tabeli, aby wyświetlić jego właściwości w **właściwości** okna. Można zmodyfikować niektóre wartości w tym miejscu. Pamiętaj tylko, modyfikowania zestawu danych, a nie źródłowej bazy danych.

     ![Właściwości kolumny zestawu danych](../data-tools/media/dataset-column-properties.png)

9. Możesz dodać nowe tabele lub adapterów tabel do zestawu danych lub dodawanie nowych zapytań do istniejących adapterów tabel lub określić nowe relacje między tabelami, przeciągając tych elementów z **przybornika** kartę. Ta karta jest wyświetlana, gdy **Projektanta obiektów DataSet** jest w trybie koncentracji uwagi.

     ![Przybornik zestawu danych](../data-tools/media/raddata-dataset-toolbox.png)

10. Następnie użytkownik najprawdopodobniej wskazane będzie określenie sposobu wypełniania zestawu danych z danymi. W tym używasz **Kreator konfiguracji TableAdapter**. Aby uzyskać więcej informacji, zobacz [wypełnienia zestawów danych przy użyciu TableAdapters](../data-tools/fill-datasets-by-using-tableadapters.md).

## <a name="add-a-database-table-or-other-object-to-an-existing-dataset"></a>Dodaj tabelę bazy danych lub inny obiekt do istniejącego zestawu danych

Ta procedura pokazuje, jak dodać tabelę z tej samej bazy danych, którego użyto do utworzenia zestawu danych.

1.  Kliknij węzeł zestawu danych w **Eksploratora rozwiązań** zapewnić Projektanta obiektów dataset fokus.

2.  Kliknij przycisk **źródeł danych** kartę na lewym marginesie programu Visual Studio lub typ **źródeł danych** w **Szybkie uruchamianie** pole.

3.  Kliknij prawym przyciskiem myszy węzeł zestawu danych, a następnie wybierz pozycję **Konfigurowanie źródła danych za pomocą kreatora**.

     ![Menu kontekstowe źródła danych](../data-tools/media/data-source-context-menu.png)

4.  Użyj kreatora, aby określić, które dodatkowe tabele lub procedur składowanych lub innego obiektu bazy danych, aby dodać do zestawu danych.

## <a name="add-a-stand-alone-data-table-to-a-dataset"></a>Dodaj tabelę danych autonomicznej do zestawu danych

1.  Otwórz swój zestaw danych w **Projektanta obiektów Dataset**.

2.  Przeciągnij <xref:System.Data.DataTable> klasy z **DataSet** karcie **przybornika** na **Projektanta obiektów Dataset**.

3.  Dodawanie kolumn do definiowania tabeli danych. Kliknij prawym przyciskiem myszy w tabeli, a następnie wybierz **Dodaj** > **kolumny**. Użyj **właściwości** okna, aby ustawić typ danych kolumny i kluczem, jeśli to konieczne.

4.  Tabele autonomicznej konieczne wdrożenie `Fill` logiki w tabelach autonomicznej tak, aby wypełnić je danymi. Instrukcje dotyczące Wypełnianie tabel danych autonomicznych, zobacz [wypełnianie zestawu danych z elementu DataAdapter](/dotnet/framework/data/adonet/populating-a-dataset-from-a-dataadapter).

## <a name="see-also"></a>Zobacz także

- [Narzędzia zestawu danych w programie Visual Studio](../data-tools/dataset-tools-in-visual-studio.md)