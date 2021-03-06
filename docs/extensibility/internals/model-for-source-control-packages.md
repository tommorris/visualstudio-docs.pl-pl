---
title: Dla pakietów kontroli źródła | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], model
ms.assetid: 6164b2d3-a622-4de8-bef3-a6de985e9ebd
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: fa0dcdd930412e4e53c59509848f0b7c1503c47b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31129446"
---
# <a name="model-for-source-control-packages"></a>Model pakietów kontroli źródła
Następujący model reprezentuje przykładem implementacji kontroli źródła. W modelu Zobacz interfejsy, które należy zaimplementować i usług środowiska, które należy wywołać. Podobnie jak wszystkie usługi faktycznie wywoływać metody określonego interfejsu, który można uzyskać na usługę. Nazwy klas są identyfikowane ułatwiające zobacz sposób wykonywania kontroli źródła.  
  
 ![SCC&#95;przykłady TUP](../../extensibility/internals/media/scc_tup.gif "SCC_TUP")  
Przykładowy projekt kontroli źródła  
  
## <a name="interfaces"></a>Interfejsy  
 Można zaimplementować kontroli źródła z nowych typów projektu w programie Visual Studio przy użyciu listy interfejsów, które przedstawiono w poniższej tabeli.  
  
|Interface|Zastosowanie|  
|---------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|Metoda wywoływana przez projekty i edytory przed ich Zapisz lub pliki zmiany (dirty). Ten interfejs jest dostępny przy użyciu <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> usługi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|Metoda wywoływana przez projektów, aby zażądać uprawnień do dodawania, usuwania lub zmień nazwę pliku lub katalogu. Ten interfejs jest również wywoływany przez projekty do powiadamia o zakończeniu środowiska podczas add, usuń lub zmień nazwę akcji. Jest on dostępny przy użyciu <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments> usługi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|Implementowana przez każda jednostka, która rejestruje, aby otrzymać powiadomienie, gdy projekty dodać, zmienić lub usunięcie pliku lub katalogu. Aby zarejestrować powiadomienia o zdarzeniach, należy wywołać <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|Metoda wywoływana przez projekty do rejestracji w usłudze pakiet kontroli źródła i uzyskiwania informacji na temat stan kontroli źródła. Ten interfejs jest dostępny przy użyciu <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager> usługi.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|Implementowana przez projekt odpowiadać na żądania kontroli źródła informacji na temat plików i uzyskanie źródło ustawienia wymagane do pliku projektu.|  
  
## <a name="see-also"></a>Zobacz też  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2.AdviseTrackProjectDocumentsEvents%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>   
 [Obsługa kontroli kodu źródłowego](../../extensibility/internals/supporting-source-control.md)