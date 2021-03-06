---
title: Model obiektu Visio ― omówienie
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Visio [Office development in Visual Studio], object model
- object models [Office development in Visual Studio], Office
- object models [Office development in Visual Studio], Visio
- objects [Office development in Visual Studio], Office object models
- Office object models
- Visio object model
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0da6dac3ffde6e6394546e78462205eb4fa08c8c
ms.sourcegitcommit: 4cd4aef53e7035d23e7d1d0f66f51ac8480622a1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 06/05/2018
ms.locfileid: "34767835"
---
# <a name="visio-object-model-overview"></a>Model obiektu Visio ― omówienie
  Do opracowywania rozwiązań pakietu Office dla programu Microsoft Office Visio, możesz użyć modelu obiektów programu Visio. Ten model obiektów składa się z klasy i interfejsy, które znajdują się w podstawowego zestawu międzyoperacyjnego dla programu Visio i są zdefiniowane w `Microsoft.Office.Interop.Visio` przestrzeni nazw.  
  
 Ten temat zawiera krótki przegląd modelu obiektów programu Visio. Aby dowiedzieć się, jak za pomocą modelu obiektów programu Visio do wykonywania zadań w projektach pakietu Office zobacz następujące tematy:  
  
-   [Praca z dokumentami Visio](../vsto/working-with-visio-documents.md)  
  
-   [Praca z kształtów Visio](../vsto/working-with-visio-shapes.md)  
  
## <a name="understand-the-visio-object-model"></a>Zrozumienie modelu obiektów programu Visio  
 Visio zawiera wiele obiektów, które mogą prowadzić interakcję. Te obiekty są zorganizowane w hierarchii, która jest ściśle zgodna interfejsu użytkownika. W górnej części hierarchii jest [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx) obiektu. Ten obiekt reprezentuje bieżące wystąpienie programu Visio. `Microsoft.Office.Interop.Visio.Application` Zawiera obiekt `Microsoft.Office.Interop.Visio.Document` i `Microsoft.Office.Interop.Visio.Page` obiektów, jak również `Microsoft.Office.Interop.Visio.Documents` i `Microsoft.Office.Interop.Visio.Pages` kolekcji. Każdy z tych obiektów i kolekcji ma wiele metod i właściwości, do których masz dostęp do manipulowania i interakcji z nim.  
  
 Aby uzyskać więcej informacji, zobacz dokumentację referencyjną VBA, aby uzyskać [Microsoft.Office.Interop.Visio.Application](https://msdn.microsoft.com/library/office/ff766485.aspx), [Microsoft.Office.Interop.Visio.Document](https://msdn.microsoft.com/library/office/ff765575.aspx), i [ Microsoft.Office.Interop.Visio.Page](https://msdn.microsoft.com/library/office/ff767035.aspx) obiektów, a także [Microsoft.Office.Interop.Visio.Documents](https://msdn.microsoft.com/library/office/ff768812.aspx) i [Microsoft.Office.Interop.Visio.Pages](https://msdn.microsoft.com/library/office/ff766165.aspx) Kolekcje.  
  
 W poniższych sekcjach opisano krótko najwyższego poziomu obiektów i ich interakcji ze sobą. Te obiekty obejmują następujące obiekty:  
  
-   Obiekt aplikacji  
  
-   Obiekt dokumentu  
  
-   obiekt strony  
  
### <a name="application-object"></a>Obiekt aplikacji  
 Obiekt Microsoft.Office.Interop.Visio.Application reprezentuje aplikacji programu Visio i jest elementem nadrzędnym wszystkie inne obiekty. Jej elementów członkowskich się zazwyczaj do programu Visio jako całość. Można użyć właściwości i metod Microsoft.Office.Interop.Visio.Application i `Microsoft.Office.Interop.Visio.ApplicationSettings` obiekty do kontrolowania środowiska programu Visio.  
  
 W projektów dodatku VSTO uzyskujesz dostęp za pomocą obiektu Microsoft.Office.Interop.Visio.Application `Application` pole `ThisAddIn` klasy. Aby uzyskać więcej informacji, zobacz [programowania VSTO Add-Ins](../vsto/programming-vsto-add-ins.md).  
  
### <a name="document-object"></a>Obiekt dokumentu  
 Obiekt Microsoft.Office.Interop.Visio.Document jest podstawą do programowania programu Visio. Reprezentuje rysunku, wzornika lub pliku szablonu. Po otwarciu dokumentu programu Visio lub Utwórz nowy dokument, Utwórz nowy obiekt Microsoft.Office.Interop.Visio.Document, które jest dodawane do kolekcji Microsoft.Office.Interop.Visio.Documents obiektu Microsoft.Office.Interop.Visio.Application .  
  
 Dokument, który ma fokus jest wywoływana aktywny dokument. Jest reprezentowana przez `Microsoft.Office.Interop.Visio.Application.ActiveDocument` właściwości obiektu Microsoft.Office.Interop.Visio.Application.  
  
### <a name="page-object"></a>obiekt strony  
 Obiekt Microsoft.Office.Interop.Visio.Page reprezentuje obszaru rysowania strony pierwszego planu lub stroną tle. Można użyć `Microsoft.Office.Interop.Visio.Page.Background` właściwości w celu określenia, czy jest to strona pierwszego planu i tła.  
  
 Aby utworzyć kształtów, należy użyć metody, które obejmują `Microsoft.Office.Interop.Visio.Page.DrawSpline` i `Microsoft.Office.Interop.Visio.Page.DrawOval` metody. Ponadto można pobrać wzorce wzorników i umieścić kształtów na stronie za pomocą `Microsoft.Office.Interop.Visio.Page.Drop` lub `Microsoft.Office.Interop.Visio.Page.DropMany` metody.  
  
## <a name="use-the-visio-object-model-documentation"></a>Skorzystaj z dokumentacji modelu obiektów programu Visio  
 Aby uzyskać pełne informacje o modelu obiektów programu Visio mogą odwoływać się do odwołania do modelu obiektu VBA programu Visio. Odwołania do modelu obiektu VBA dokumentów modelu obiektów programu Visio, jak jest narażony na język Visual Basic dla kodu aplikacji (VBA). Aby uzyskać więcej informacji, zobacz [odwołania do modelu obiektu Visio 2010](http://go.microsoft.com/fwlink/?LinkId=199775).  
  
 Wszystkie obiekty i elementów członkowskich w odwołania do modelu obiektu VBA odpowiadają typy i składniki w podstawowy zestaw międzyoperacyjny programu Visio (PIA). Na przykład `Document` obiektu odwołania do modelu obiektu VBA odpowiada typowi Microsoft.Office.Interop.Visio.Document w PIA programu Visio. Odwołania do modelu obiektu VBA zapewnia przykłady kodu dla większości właściwości, metod i zdarzeń, jednak należy translacji kod VBA w niniejszej dokumentacji Visual Basic lub Visual C#, jeśli chcesz używać ich w projekcie dodatku narzędzi VSTO programu Visio utworzonego za pomocą Visual Studio.  
  
> [!NOTE]  
>  W tej chwili nie istnieje żadne dokumentacji dla programu Visio podstawowego zestawu międzyoperacyjnego.  
  
 Przykłady kodu powiązanego i dodatkowe narzędzia do tworzenia rozwiązań programu Visio, zobacz [zestaw Visio 2010 software development kit](http://go.microsoft.com/fwlink/?LinkId=196501).  
  
### <a name="additional-types-in-primary-interop-assemblies"></a>Dodatkowe typy w podstawowe zestawy międzyoperacyjne  
 Typów można znaleźć w podstawowe zestawy międzyoperacyjne, które nie są widoczne w VBA z powodu różnic implementacji. VBA zawiera widok modelu obiektów programu Visio, zawierający tylko te obiekty i elementów członkowskich, które mogą korzystać bezpośrednio. Podstawowe zestawy międzyoperacyjne udostępnianie tego samego modelu obiektu, ale obejmuje to też inne interfejsy, klasy i elementów członkowskich, które wykonuje obiektów w modelu obiektów COM z kodem zarządzanym. Te dodatkowe elementy nie są przeznaczone do użycia bezpośrednio w kodzie.  
  
 Aby uzyskać więcej informacji, zobacz [Przegląd klasy i interfejsy w podstawowe zestawy międzyoperacyjne pakietu Office](http://go.microsoft.com/fwlink/?LinkId=189592) i [podstawowe zestawy międzyoperacyjne pakietu Office](../vsto/office-primary-interop-assemblies.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Rozwiązania programu Visio](../vsto/visio-solutions.md)   
 [Praca z dokumentami Visio](../vsto/working-with-visio-documents.md)   
 [Praca z kształtów Visio](../vsto/working-with-visio-shapes.md)  
  
  