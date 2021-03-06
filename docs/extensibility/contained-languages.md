---
title: Zawiera języki | Dokumentacja firmy Microsoft
ms.date: 03/22/2018
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - contained languages
ms.assetid: b75bbb51-8e42-41b1-bece-09ab0b1f03cc
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 9edaed1eef81d493bdd29311893caef93447e6f7
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39231747"
---
# <a name="contained-languages"></a>Języki zawarte

*Zawiera języki* języków, które znajdują się w innych językach. Na przykład HTML w [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] strony mogą zawierać [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] lub [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] skryptów. Architektura podwójnego język jest wymagany dla *.aspx* redaktora pliku do zapewnienia funkcji IntelliSense, kolorowanie i przeprowadzić edycję funkcji dla kodu HTML i języka skryptów.

## <a name="implementation"></a>Implementacja

Najważniejsze interfejs, należy wdrożyć dla języków zawartych <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> interfejsu. Ten interfejs jest implementowany za pomocą dowolnego języka, który może znajdować się wewnątrz podstawowy język. Jej daje dostęp do usługi języka colorizer filtr widoku tekstu i identyfikator podstawowy język usługi. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory> Pozwala na tworzenie <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> interfejsu. Poniższe kroki pokazują, jak zaimplementować zawartej języka:

1.  Użyj `QueryService()` można pobrać języka, identyfikator usługi i identyfikator interfejsu <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory>.

2.  Aby utworzyć <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguage> interfejsu, wywołaj <xref:Microsoft.VisualStudio.TextManager.Interop.IVsContainedLanguageFactory.GetLanguage%2A> metody. Przekaż <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> interfejsu, co najmniej jeden [elementu identyfikatory](<xref:Microsoft.VisualStudio.VSConstants.VSITEMID>)i <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> interfejsu.

3.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator> Interfejs, który jest obiektem koordynatora buforu tekstu, oferuje podstawowe usługi, które są wymagane do mapowania lokalizacji w podstawowym pliku do buforu dodatkowej języka.

     Na przykład w jednym *.aspx* zawiera plik podstawowy plik ASP, HTML i cały kod, który znajduje się. Jednak dodatkowej buforu obejmuje tylko kod wraz z żadnych definicji klas zapewnienie dodatkowej buforu pliku prawidłowy kod. Koordynator buforu obsługuje pracę koordynowanie zmian z buforu do drugiego.

4.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.SetSpanMappings%2A> Koordynator buforu informuje o metodę, która jest podstawowy język, jaki tekst w ramach jego buforu jest mapowany na odpowiedni tekst w buforze dodatkowej.

     Język przekazuje tablicę <xref:Microsoft.VisualStudio.TextManager.Interop.NewSpanMapping> struktury, która obecnie zawiera tylko podstawowy i pomocniczy zakresu.

5.  <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapPrimaryToSecondarySpan%2A> Metody i <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextBufferCoordinator.MapSecondaryToPrimarySpan%2A> metoda dostarcza mapowanie z podstawowej do dodatkowej buforu i na odwrót.