---
title: '&lt;dostosowania&gt; — element (Office development w programie Visual Studio)'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- <customizations> element
- customizations element
- application manifests [Office development in Visual Studio], <customizations> element
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 9ac1a78f0d35b2fac751e87874bbfe169798712a
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/06/2018
ms.locfileid: "35676183"
---
# <a name="ltcustomizationsgt-element-office-development-in-visual-studio"></a>&lt;dostosowania&gt; — element (Office development w programie Visual Studio)
  `customizations` Elementu `vstov4` przestrzeń nazw zawiera wszystkie informacje o instalowaniu i ładowanie każde z tych rozwiązań pakietu Office.  
  
## <a name="syntax-for-document-level-customizations"></a>Składnia dla dostosowywania poziomie dokumentu  
  
```xml
<customizations>  
  <customization  
    id  
    <document  
      solutionId  
    />  
  </customization>  
</customizations>  
```  
  
## <a name="syntax-for-vsto-add-ins"></a>Składnia dla dodatków narzędzi VSTO  
  
```xml
<customizations>  
  <customization  
    id  
    <appAddin  
      application  
      loadBehavior  
      keyName>  
    <friendlyName></friendlyName>  
    <description></description>  
    <formRegions></formRegions>  
  </customization>  
</customizations>  
```  
  
## <a name="elements-and-attributes"></a>Atrybuty i elementy  
 `customizations` Element zawiera szczegółowe informacje dotyczące poszczególnych rozwiązań pakietu Office. Ten element musi znajdować się w następującej przestrzeni nazw: `vstov4=urn:schemas-microsoft-com:vsto.v4`. Elementy podrzędne zestawu również musi być w tej przestrzeni nazw.  
  
 `customizations` Element nie ma żadnych atrybutów.  
  
 `customizations` Element ma następujący element podrzędny.  
  
### <a name="customization"></a>Dostosowywanie  
 Wymagane. `customization` Element `vstov4` przestrzeń nazw została zdefiniowana w [ &#60;dostosowywania&#62; elementu &#40;programowanie Office w Visual Studio&#41;](../vsto/customization-element-office-development-in-visual-studio.md).  
  
## <a name="example-of-a-document-level-customization"></a>Przykład dostosowywania poziomie dokumentu  
  
### <a name="description"></a>Opis  
 W poniższym przykładzie kodu pokazano `customizations` element dla dostosowywania poziomie dokumentu.  
  
> [!NOTE]  
>  Ten przykład kodu jest częścią większego przykładu przewidzianego w [manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
  <vstov4:customization>  
    <vstov4:document   
      solutionId="73e" />  
  </vstov4:customization>  
</vstov4:customizations>  
```  
  
## <a name="example-of-a-vsto-add-in"></a>Przykład dodatku narzędzi VSTO  
  
### <a name="description"></a>Opis  
 W poniższym przykładzie kodu pokazano `customizations` element dla dodatku narzędzi VSTO. Jest to dodatek narzędzi VSTO dla programu Outlook, która obejmuje regionów formularzy w. Ten przykład kodu jest częścią większego przykładu przewidzianego w [manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md).  
  
### <a name="code"></a>Kod  
  
```xml
<vstov4:customizations   
  xmlns:vstov4="urn:schemas-microsoft-com:vsto.v4">  
  <vstov4:customization>  
    <vstov4:appAddIn   
      application="Outlook"   
      loadBehavior="3"   
      keyName="ContosoOutlookAddIn">  
      <vstov4:friendlyName>  
        ContosoOutlookAddIn  
      </vstov4:friendlyName>  
      <vstov4:description>  
        ContosoOutlookAddIn - Outlook VSTO Add-in   
        created with Visual Studio Tools for Office  
      </vstov4:description>  
      <vstov4:formRegions>  
        <vstov4:formRegion  
            name="OutlookAddIn1.FormRegion1">  
          <vstov4:messageClass name="IPM.Note" />  
          <vstov4:messageClass name="IPM.Contact" />  
          <vstov4:messageClass name="IPM.Appointment" />  
        </vstov4:formRegion>  
      </vstov4:formRegions>  
    </vstov4:appAddIn>  
  </vstov4:customization>  
</vstov4:customizations>  
```  
  
## <a name="see-also"></a>Zobacz także  
 [Manifesty aplikacji dla rozwiązań pakietu Office](../vsto/application-manifests-for-office-solutions.md)   
 [Manifesty wdrożenia dla rozwiązań pakietu Office](../vsto/deployment-manifests-for-office-solutions.md)   
 [Manifest aplikacji ClickOnce](/visualstudio/deployment/clickonce-application-manifest)  
  
  