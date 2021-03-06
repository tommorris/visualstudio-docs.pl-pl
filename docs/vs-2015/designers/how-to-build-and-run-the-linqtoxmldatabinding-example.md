---
title: 'Porady: kompilowanie i uruchamianie elementu linqtoxmldatabinding — przykład | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3943deaf-80e2-4968-ac04-d3ef56cfad6c
caps.latest.revision: 5
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 63b82af28599683f739c98314a9d4f71ad474a25
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42696970"
---
# <a name="how-to-build-and-run-the-linqtoxmldatabinding-example"></a>Porady: kompilowanie i uruchamianie elementu linqtoxmldatabinding — przykład
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [porady: kompilowanie i uruchamianie elementu linqtoxmldatabinding — przykład](https://docs.microsoft.com/visualstudio/designers/how-to-build-and-run-the-linqtoxmldatabinding-example).  
  
W tym temacie pokazano, jak utworzyć i skompilować projekt programu Visual Studio elementu linqtoxmldatabinding — oraz jak uruchomić wynikowy program przykład elementu linqtoxmldatabinding — Windows Presentation Foundation (WPF).  
  
 Aby uzyskać więcej informacji o używaniu programu Visual Studio do tworzenia projektów, zobacz [opracowywanie aplikacji w programie Visual Studio](http://msdn.microsoft.com/en-us/97490c1b-a247-41fb-8f2c-bc4c201eff68).  
  
## <a name="creating-and-populating-the-project"></a>Tworzenie i wypełnianie projektu  
  
#### <a name="to-create-the-starting-project"></a>Do utworzenia projektu startowego  
  
1.  Uruchom program Visual Studio i utworzyć aplikację WPF w języku C# o nazwie elementu linqtoxmldatabinding —. Projekt musi używać .NET Framework 3.5 (lub nowszy).  
  
2.  Jeśli nie zrobiono, dodaj odwołania do projektu dla następujących zestawów platformy .NET:  
  
    -   System.Data  
  
    -   System.Data.DataSetExtensions  
  
    -   System.Xml  
  
    -   System.Xml.Linq  
  
3.  Skompiluj rozwiązanie, naciskając klawisz **Ctnrl + Shift + B**, uruchom ją, naciskając klawisz **F5**. Projekt, należy skompilować bez błędów i Uruchom jako ogólnego aplikacji WPF.  
  
#### <a name="to-add-custom-code-to-the-project"></a>Aby dodać niestandardowy kod do projektu  
  
1.  W Eksploratorze rozwiązań Zmień nazwę pliku źródłowego Window1.xaml L2XDBForm.xaml. Automatycznie powinien można zmienić nazwy pliku źródłowego zależne Window1.xaml.cs na L2XDBForm.xaml.cs.  
  
2.  Zastąp kod źródłowy znajdującą się w pliku L2XDBForm.xaml z sekcji kod z tematu [kod źródłowy L2DBForm.xaml](../designers/l2dbform-xaml-source-code.md). (Użyj widoku źródła XAML do pracy z tym plikiem).  
  
3.  Podobnie, Zastąp kod w źródła w L2XDBForm.xaml.cs [kod źródłowy L2DBForm.xaml.cs](../designers/l2dbform-xaml-cs-source-code.md).  
  
4.  W pliku App.xaml należy zastąpić wszystkie wystąpienia ciągu "Window1.xaml" z "L2XDBForm.xaml".  
  
5.  Tworzenie naciśnięcie rozwiązania **Ctrl + Shift + B**.  
  
## <a name="running-the-program"></a>Uruchamianie programu  
 Program elementu linqtoxmldatabinding — umożliwia użytkownikowi wyświetlanie i manipulowanie listę książek, które są przechowywane jako osadzonego elementu XML.  
  
#### <a name="to-run-the-program-and-view-the-book-list"></a>Aby uruchomić program i wyświetlić listy książek  
  
1.  Uruchamianie elementu linqtoxmldatabinding —, naciskając klawisz **F5** (**Rozpocznij debugowanie**) lub **kombinację klawiszy Ctrl + F5** (**Rozpocznij bez debugowania**). Okno programu z tytułem **powiązanie danych WPF za pomocą LINQ to XML** powinna być wyświetlana.  
  
2.  Zwróć uwagę, w górnej części interfejsu użytkownika, wyświetla nieprzetworzonych **XML** reprezentujący listy książek. Jest wyświetlana przy użyciu technologii WPF <xref:System.Windows.Controls.TextBlock> formant, który nie obsługuje interakcji za pomocą myszy lub klawiatury.  
  
3.  Druga sekcja pionowy, o nazwie **listy książek**, wyświetla Lista uporządkowana książki w postaci zwykłego tekstu. Używa ona <xref:System.Windows.Controls.ListBox> kontrolkę umożliwiającą wybór jednak myszy lub klawiatury.  
  
#### <a name="to-add-and-delete-books-from-the-list"></a>Dodawanie i usuwanie książek z listy  
  
1.  Aby usunąć istniejącej na liście, wybierz ją w **listy książek** sekcji, a następnie kliknij przycisk **usunąć wybrane książki** przycisku. Należy zauważyć, że wpis książki została usunięta z książki i raw ofert źródła XML.  
  
2.  Aby dodać nowej książki do listy, wprowadź wartości w **identyfikator** i **wartość** <xref:System.Windows.Controls.TextBox> kontrolek w ostatniej sekcji **Dodawanie nowej książki**, następnie kliknij przycisk **Dodaj Książki** przycisku. Należy pamiętać, że książki jest dołączany do listy w książce i ofert XML. Ten program nie można zweryfikować wartości wejściowych.  
  
#### <a name="to-edit-an-existing-book-entry"></a>Aby edytować istniejący wpis książki  
  
1.  Wybierz wpis książki w drugim **listy książek** sekcji. Jego bieżące wartości powinna być wyświetlana w sekcji trzeci **Edytuj wybrane książki**.  
  
2.  Edytuj wartości za pomocą klawiatury. Jak najszybciej albo <xref:System.Windows.Controls.TextBox> formant utraci fokus, zmiany są automatycznie propagowane do ofert źródła i książki XML.  
  
## <a name="see-also"></a>Zobacz też  
 [Powiązanie danych WPF za pomocą LINQ to XML — przykład](../designers/wpf-data-binding-using-linq-to-xml-example.md)   
 [Wskazówki: Elementu linqtoxmldatabinding — przykład](../designers/walkthrough-linqtoxmldatabinding-example.md)   
 [Tworzenie aplikacji w programie Visual Studio](http://msdn.microsoft.com/en-us/97490c1b-a247-41fb-8f2c-bc4c201eff68)



