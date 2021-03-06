---
title: Dodaj nowe połączenia
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 14df0183076125e487873bbb9865b2481e277a5b
ms.sourcegitcommit: ce154aee5b403d5c1c41da42302b896ad3cf8d82
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/07/2018
ms.locfileid: "34845018"
---
# <a name="add-new-connections"></a>Dodaj nowe połączenia

Testowanie połączenia z bazą danych lub usługi i Eksploruj zawartość bazy danych i schematów, za pomocą **Eksploratora serwera**, **Eksplorator chmury**, lub **Eksplorator obiektów SQL Server**. Funkcje te okna nakłada się w pewnym stopniu. Podstawowe różnice są następujące:

- Server Explorer

   Instalowany domyślnie w programie Visual Studio. Może służyć do testowania połączenia i wyświetlania baz danych programu SQL Server, innych baz danych, które mają zainstalowanego dostawcę ADO.NET i niektórych usług Azure. Zawiera także obiekty niskiego poziomu, takie jak liczniki wydajności systemu, dzienniki zdarzeń i kolejki wiadomości. Jeśli źródło danych nie ma ADO.NET dostawcy, nie będzie widoczna w tym miejscu, ale można go użyć w programie Visual Studio, nawiązując połączenie programowe.

- Eksplorator chmury

   Ręcznie zainstaluj to okno jako rozszerzenia programu Visual Studio, wybierając **narzędzia** > **rozszerzenia i aktualizacje** > **Online**  >  **Markeplace programu visual Studio**. Udostępnia funkcje specjalne dla badać i łączących się z usługami Azure.

- Eksplorator obiektów SQL Server

   Zainstalowane z programu SQL Server Data Tools i są widoczne w obszarze **widoku** menu. Jeśli nie widzisz istnieje, przejdź do **programy i funkcje** w Panelu sterowania, Znajdź Visual Studio, a następnie wybierz **zmiany** ponowne uruchomienie po zaznaczeniu pola wyboru dla programu SQL Server Data Tools Instalator. Użyj **Eksplorator obiektów SQL Server** do widoku baz danych (jeśli mają dostawcy ADO.NET), tworzenia nowych baz danych, zmodyfikuj schematów, tworzenie procedur składowanych, pobrać parametry połączenia, przeglądać dane i więcej. Bazy danych SQL, które nie usługodawcy ADO.NET zainstalowany nie będą widoczne w tym miejscu, ale można nadal nawiązać je programowo.

## <a name="add-a-connection-in-server-explorer"></a>Dodawanie połączenia w Eksploratorze serwera

Aby utworzyć połączenie z bazą danych, kliknij przycisk **Dodawanie połączenia** ikonę w **Eksploratora serwera**, lub kliknij prawym przyciskiem myszy **Eksploratora serwera** na **danych Połączenia** a następnie wybierz węzeł **Dodawanie połączenia**. W tym miejscu można nawiązać bazy danych na inny serwer, usługi programu SharePoint lub usługi Azure.

![Ikona nowego połączenia Eksploratora serwera](../data-tools/media/raddata-server-explorer-new-connection-icon.png)

Spowoduje to wyświetlenie **Dodawanie połączenia** okno dialogowe. W tym miejscu możemy wprowadzony nazwę wystąpienia bazy danych LocalDB programu SQL Server.

![Dodaj nowe połączenie](../data-tools/media/raddata-add-new-connection-dialog.png)

## <a name="change-the-provider"></a>Zmienianie dostawcy

Jeśli nie ma źródła danych, kliknij przycisk **zmiany** przycisk, aby wybrać nowe źródło danych i/lub nowego dostawcy danych ADO.NET. Nowego dostawcę może poprosić o podanie poświadczeń, w zależności od tego, jak został skonfigurowany.

![Dostawca danych AD0.NET zmiany](../data-tools/media/raddata-change-ad0.net-data-provider.png)

## <a name="test-the-connection"></a>Testuj połączenie

Po wybraniu źródła danych, kliknij przycisk **Testuj połączenie**. Jeśli to się nie powiedzie, musisz rozwiązać zgodnie z dokumentacją dostawcy.

![Połączenie testowe](../data-tools/media/raddata-test-connection.png)

Jeśli test zakończy się powodzeniem, możesz przystąpić do tworzenia *źródła danych*, czyli terminu programu Visual Studio, który oznacza w rzeczywistości *modelu danych* opartego na podstawowej bazy danych lub usługi.

## <a name="see-also"></a>Zobacz także

- [Narzędzia do obsługi danych programu Visual Studio dla platformy .NET](../data-tools/visual-studio-data-tools-for-dotnet.md)