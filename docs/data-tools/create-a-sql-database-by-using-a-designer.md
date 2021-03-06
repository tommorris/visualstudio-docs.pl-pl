---
title: Utwórz plik bazy danych i za pomocą projektanta tabel w programie Visual Studio
ms.date: 11/03/2017
ms.topic: conceptual
helpviewer_keywords:
- database tables, creating
- database files, creating
- table designer
ms.assetid: 99c2b06f-47aa-414e-8057-a3453712fd23
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 71d9be6ddc664d3b25c52d227e749421611f3512
ms.sourcegitcommit: 3a11feebad45a0dd4ac45efcbfdf172fce46e1de
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/07/2018
ms.locfileid: "39582375"
---
# <a name="create-a-database-and-add-tables-in-visual-studio"></a>Tworzenie bazy danych i dodawanie tabel w programie Visual Studio

Za pomocą programu Visual Studio do tworzenia i aktualizowania lokalnego pliku bazy danych w SQL Server Express LocalDB. Można również utworzyć bazę danych, wykonując instrukcje języka Transact-SQL w **Eksplorator obiektów SQL Server** okna narzędzi w programie Visual Studio. W tym temacie utworzymy *.mdf* pliku i Dodaj tabelami i kluczami przy użyciu projektanta tabel.

## <a name="prerequisites"></a>Wymagania wstępne

Do przeprowadzenia tego instruktażu, konieczne jest posiadanie opcjonalnego **przechowywanie i przetwarzanie danych** obciążenia zainstalowane w programie Visual Studio. Aby go zainstalować, otwórz **Instalatora programu Visual Studio** i wybierz polecenie **obciążeń** kartę. W obszarze **sieć Web i chmura**, wybierz **przechowywanie i przetwarzanie danych**. Wybierz **Modyfikuj** przycisk, aby dodać obciążenia do programu Visual Studio.

## <a name="create-a-project-and-a-local-database-file"></a>Tworzenie projektu i pliku lokalnej bazy danych

1.  Utwórz projekt Windows Forms o nazwie **SampleDatabaseWalkthrough**.

2.  Na pasku menu wybierz **projektu** > **Dodaj nowy element**.

3.  Na liście szablonów elementów przewiń w dół i wybierz **usługową bazę danych**.

     ![Okno dialogowe szablonów elementu](../data-tools/media/raddata-vsitemtemplates.png)

4.  Nazwij bazę danych **SampleDatabase**, a następnie wybierz pozycję **Dodaj** przycisku.

### <a name="to-add-a-data-source"></a>Aby dodać źródło danych

5.  Jeśli **źródeł danych** okno nie jest otwarte, otwórz go, wybierając **Shift**+**Alt**+**D** kluczy lub na na pasku menu, wybierz opcję **widoku** > **Windows inne** > **źródeł danych**.

6.  W **źródeł danych** wybierz **Dodaj nowe źródło danych** łącza.

    **Kreatora konfiguracji źródła danych** zostanie otwarty.

7. Na **wybierz typ źródła danych** wybierz **bazy danych** , a następnie wybierz **dalej**.

8. Na **wybierz Model bazy danych** wybierz **dalej** aby zaakceptować wartości domyślne (zestaw danych).

9. Na **wybierz połączenie danych** wybierz opcję **SampleDatabase.mdf** pliku na liście rozwijanej, a następnie wybierz **dalej**.

10. Na **Zapisz parametry połączenia do pliku konfiguracji aplikacji** wybierz **dalej**.

11. Jeden **wybierz obiekty bazy danych** stronie zostanie wyświetlony komunikat informujący, że baza danych nie zawiera żadnych obiektów. Wybierz **Zakończ**.

### <a name="to-view-properties-of-the-data-connection"></a>Aby wyświetlić właściwości połączenia danych

Możesz wyświetlić parametry połączenia dla *SampleDatabase.mdf* plików, otwierając okno właściwości połączenia danych:

-   W programie Visual Studio, wybierz **widoku** > **Eksplorator obiektów SQL Server** Jeśli to okno nie jest jeszcze otwarte. Otwórz okno właściwości, rozwijając **połączeń danych** węzła, otwierając menu skrótów dla *SampleDatabase.mdf*, a następnie wybierając **właściwości**.

-   Alternatywnie, można wybrać **widoku** > **Eksploratora serwera**, jeśli to okno nie jest jeszcze otwarte. Otwórz okno właściwości, rozwijając **połączeń danych** węzła. Otwórz menu skrótów dla *SampleDatabase.mdf*, a następnie wybierz pozycję **właściwości**.

## <a name="create-tables-and-keys-by-using-table-designer"></a>Tworzenie tabel i kluczy przy użyciu projektanta tabel

W tej sekcji utworzysz dwie tabele, klucz podstawowy w każdej tabeli i kilka wierszy przykładowych danych. Utworzysz też klucz obcy, aby określić, jak rekordy w jednej tabeli odpowiadać rekordom w drugiej tabeli.

### <a name="to-create-the-customers-table"></a>Aby utworzyć tabelę Customers

1.  W **Eksploratora serwera** lub **Eksplorator obiektów SQL Server**, rozwiń węzeł **połączeń danych** węzła, a następnie rozwiń węzeł **SampleDatabase.mdf**węzła.

2.  Otwórz menu skrótów dla **tabel**, a następnie wybierz pozycję **Dodaj nową tabelę**.

     **Projektanta tabel** otwiera i pokazuje siatkę z jednym domyślnym wierszem, który reprezentuje pojedynczą kolumnę w tabeli, które tworzysz. Przez dodawanie wierszy do siatki dodajesz kolumny w tabeli.

3.  W siatce dodaj wiersz dla każdego z poniższych wpisów:

    |Nazwa kolumny|Typ danych|Zezwalaj na wartości null|
    |-----------------|---------------|-----------------|
    |`CustomerID`|`nchar(5)`|False (usunięty)|
    |`CompanyName`|`nvarchar(50)`|False (usunięty)|
    |`ContactName`|`nvarchar (50)`|True (wybrane)|
    |`Phone`|`nvarchar (24)`|True (wybrane)|

4.  Otwórz menu skrótów dla `CustomerID` wiersza, a następnie wybierz pozycję **Ustaw klucz podstawowy**.

5.  Otwórz menu skrótów dla domyślnego wiersza, a następnie wybierz **Usuń**.

6.  Nadaj tabeli nazwę Customers, aktualizując pierwszy wiersz w okienku skryptu, aby dopasować następujący przykład:

    ```sql
    CREATE TABLE [dbo].[Customers]
    ```

    Powinien zostać wyświetlony podobny do poniższego:

    ![Projektant tabel](../data-tools/media/raddata-table-designer.png)

7.  W lewym górnym rogu **projektanta tabel**, wybierz opcję **aktualizacji** przycisku.

8.  W **Podgląd aktualizacji bazy danych** okno dialogowe, wybierz opcję **Aktualizuj bazę danych** przycisku.

    Wprowadzone zmiany są zapisywane w lokalnym pliku bazy danych.

### <a name="to-create-the-orders-table"></a>Aby utworzyć tabelę Orders

1.  Dodaj inną tabelę, a następnie dodaj wiersz dla każdego wpisu w tabeli poniżej:

    |Nazwa kolumny|Typ danych|Zezwalaj na wartości null|
    |-----------------|---------------|-----------------|
    |`OrderID`|`int`|False (usunięty)|
    |`CustomerID`|`nchar(5)`|False (usunięty)|
    |`OrderDate`|`datetime`|True (wybrane)|
    |`OrderQuantity`|`int`|True (wybrane)|

2.  Ustaw **OrderID** jako klucz podstawowy, a następnie usuń domyślny wiersz.

3.  Nadaj tabeli nazwę Orders, aktualizując pierwszy wiersz w okienku skryptu, aby dopasować następujący przykład:

    ```sql
    CREATE TABLE [dbo].[Orders]
    ```

4.  W lewym górnym rogu **projektanta tabel**, wybierz opcję **aktualizacji** przycisku.

5.  W **Podgląd aktualizacji bazy danych** okno dialogowe, wybierz opcję **Aktualizuj bazę danych** przycisku.

    Wprowadzone zmiany są zapisywane w lokalnym pliku bazy danych.

### <a name="to-create-a-foreign-key"></a>Aby utworzyć obcy klucz

1.  W okienku kontekstowym po prawej stronie siatki, otwórz menu skrótów dla **klucze obce**, a następnie wybierz pozycję **Dodaj nowy klucz obcy**, jak pokazano na poniższej ilustracji.

     ![Dodawanie klucza obcego w Projektancie tabel](../data-tools/media/foreignkey.png)

2.  W wyświetlonym polu tekstowym Zamień **ToTable** z **klientów**.

3.  W okienku języka T-SQL zaktualizuj ostatni wiersz, aby dopasować następujący przykład:

    ```sql
    CONSTRAINT [FK_Orders_Customers] FOREIGN KEY ([CustomerID]) REFERENCES [Customers]([CustomerID])
    ```

4.  W lewym górnym rogu **projektanta tabel**, wybierz opcję **aktualizacji** przycisku.

5.  W **Podgląd aktualizacji bazy danych** okno dialogowe, wybierz opcję **Aktualizuj bazę danych** przycisku.

    Wprowadzone zmiany są zapisywane w lokalnym pliku bazy danych.

## <a name="populate-the-tables-with-data"></a>Wypełnianie tabel danymi

1.  W **Eksploratora serwera** lub **Eksplorator obiektów SQL Server**, rozwiń węzeł przykładowej bazy danych.

2.  Otwórz menu skrótów dla **tabel** węzeł **Odśwież**, a następnie rozwiń węzeł **tabel** węzła.

3.  Otwórz menu skrótów dla tabeli Customers, a następnie wybierz **Pokaż dane tabeli**.

4.  Dodaj dowolne dane, które mają dla niektórych klientów.

    Można określić dowolne pięć znaków jako identyfikatory klienta, ale należy wybrać co najmniej jeden, który można zapamiętać do użycia w dalszej części tej procedury.

5.  Otwórz menu skrótów dla tabeli zamówienia, a następnie wybierz **Pokaż dane tabeli**.

6.  Dodawanie danych dla niektórych zleceń.

    > [!IMPORTANT]
    > Upewnij się, że wszystkie identyfikatory zamówień i ilości zamówienia są liczbami całkowitymi i że każdy identyfikator klienta odpowiada wartości określonej w **CustomerID** kolumny w tabeli Klienci.

7.  Na pasku menu wybierz **pliku** > **Zapisz wszystko**.

## <a name="see-also"></a>Zobacz także

- [Uzyskiwanie dostępu do danych w programie Visual Studio](accessing-data-in-visual-studio.md)