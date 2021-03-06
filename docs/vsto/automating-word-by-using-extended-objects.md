---
title: Automatyzowanie programu Word za pomocą obiektów rozszerzonych
ms.custom: ''
ms.date: 02/02/2017
ms.technology: office-development
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Word [Office development in Visual Studio], automating
- extended objects [Office development in Visual Studio], Word
- automation [Office development in Visual Studio], Word
- host items [Office development in Visual Studio], Word
- automating Word
- controls [Office development in Visual Studio], Word host controls
- host controls, Word
- host controls [Office development in Visual Studio], Word
- Word [Office development in Visual Studio], host controls
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 8ac9c610cdc7111eaeb5204e1b9d4fe6cde27a9c
ms.sourcegitcommit: 209c2c068ff0975994ed892b62aa9b834a7f6077
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/17/2018
ms.locfileid: "34264863"
---
# <a name="automate-word-by-using-extended-objects"></a>Automatyzowanie programu Word za pomocą obiektów rozszerzonych
  Podczas opracowywania rozwiązań programu Word w Visual Studio, można użyć *hosta elementów* i *kontrolki hosta*s w ramach rozwiązań. Są to obiekty, które rozszerzają niektórych obiektów często używane w modelu obiektów programu Word (to znaczy obiektu modelu udostępnianym przez podstawowy zestaw międzyoperacyjny dla programu Word), takie jak <xref:Microsoft.Office.Interop.Word.Document> i <xref:Microsoft.Office.Interop.Word.ContentControl> obiektów. Obiekty rozszerzone przypominają obiektów programu Word, które są oparte na, ale Dodaj dodatkowe zdarzenia oraz funkcje powiązania danych do obiektów.  
  
 [!INCLUDE[appliesto_wdalldocapp](../vsto/includes/appliesto-wdalldocapp-md.md)]  
  
 Elementów hosta i formantów hosta są dostępne w zarówno dodatków VSTO i dostosowywanie na poziomie dokumentu, chociaż kontekst, w którym mogą być one używane jest różne dla każdego typu rozwiązania. Aby uzyskać więcej informacji, zobacz [elementów, a informacje o formantach](../vsto/host-items-and-host-controls-overview.md).  
  
## <a name="document-host-item"></a>Element hosta dokumentu  
 Word projektów zapewnia dostęp do <xref:Microsoft.Office.Tools.Word.Document> element hosta. <xref:Microsoft.Office.Tools.Word.Document> Element hosta działa jako kontener dla innych formantów, łącznie z formantami hosta i formantów formularzy systemu Windows i przechowuje informacje o formantach w jego powierzchnię. <xref:Microsoft.Office.Tools.Word.Document> Element hosta zawiera również większość tych samych elementów członkowskich jako <xref:Microsoft.Office.Interop.Word.Document> klasy, która jest odpowiadającą klasę w modelu obiektów programu Word.  
  
 Aby uzyskać więcej informacji, zobacz [element hosta dokumentu](../vsto/document-host-item.md).  
  
## <a name="word-host-controls"></a>kontrolki hosta programu Word  
 Istnieje kilka hosta formantów dla programu Word, które ułatwiają tworzenie, organizować i zautomatyzować dokumentów. Większość ich funkcji obejmuje importowanie, prezentacji i ochrony danych. Te kontrolki hosta podaj zdarzenia oraz funkcje wiązania danych, które nie mają ich odpowiedniki w macierzystym modelu obiektów programu Word.  
  
 W projektach na poziomie dokumentu można dodać żadnego formantu, hosta do dokumentu w czasie projektowania, lub można dodać formanty zawartości i formantów zakładek w czasie wykonywania. W projektów dodatku VSTO można dodać formanty zawartości i formantów zakładek do otwartego dokumentu w czasie wykonywania.  
  
 Aby uzyskać więcej informacji o formantach hosta można użyć w projekty programu Word, zobacz następujące tematy:  
  
-   [Formanty zawartości](../vsto/content-controls.md)  
  
-   [BOOKMARK, formant:](../vsto/bookmark-control.md)  
  
-   [Formant XMLNode](../vsto/xmlnode-control.md)  
  
-   [Formant XMLNodes](../vsto/xmlnodes-control.md)  
  
## <a name="see-also"></a>Zobacz także  
 [Porady: dodawanie formantów zawartości do dokumentów programu Word](../vsto/how-to-add-content-controls-to-word-documents.md)   
 [Porady: dodawanie formantów zakładek do dokumentów programu Word](../vsto/how-to-add-bookmark-controls-to-word-documents.md)   
 [Porady: dodawanie formantów XMLNode do dokumentów programu Word](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)   
 [Porady: dodawanie formantów XMLNodes do dokumentów programu Word](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)   
 [Porady: zmiana rozmiaru formantów zakładki](../vsto/how-to-resize-bookmark-controls.md)   
 [Wskazówki: Tworzenie szablonu za pomocą formantów zawartości](../vsto/walkthrough-creating-a-template-by-using-content-controls.md)   
 [Wskazówki: Powiązywanie formantów zawartości do niestandardowych części XML](../vsto/walkthrough-binding-content-controls-to-custom-xml-parts.md)   
 [Wskazówki: Tworzenie menu skrótów dla zakładek](../vsto/walkthrough-creating-shortcut-menus-for-bookmarks.md)   
 [Rozwiązania programu Word](../vsto/word-solutions.md)   
 [Obiekty hosta i informacje o formantach hosta](../vsto/host-items-and-host-controls-overview.md)   
 [Ograniczenia programowe elementów hosta i formantów hosta](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)   
 [Rozszerzanie dokumentów programu Word i skoroszytów programu Excel w dodatkach VSTO w czasie wykonywania](../vsto/extending-word-documents-and-excel-workbooks-in-vsto-add-ins-at-run-time.md)  
  
  