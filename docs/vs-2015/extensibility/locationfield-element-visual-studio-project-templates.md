---
title: Locationfield — Element (szablony projektu Visual Studio) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#LocationField
helpviewer_keywords:
- LocationField element [Visual Studio project templates]
ms.assetid: 6aaaa155-6ce0-4f7f-aa50-8d63d7a7c992
caps.latest.revision: 14
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ea66808097c0e62d6c36781d7f288ed06975f6e1
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42678265"
---
# <a name="locationfield-element-visual-studio-project-templates"></a>LocationField — Element (Szablony projektu Visual Studio)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [locationfield — Element (szablony projektu Visual Studio)](https://docs.microsoft.com/visualstudio/extensibility/locationfield-element-visual-studio-project-templates).  
  
Określa, czy **lokalizacji** polu tekstowym **nowy projekt** okno dialogowe jest włączone, wyłączone lub ukryty w przypadku szablonu projektu.  
  
 \<VSTemplate>  
 \<TemplateData >  
 \<Locationfield — >  
  
## <a name="syntax"></a>Składnia  
  
```  
<LocationField> Enabled/Disabled/Hidden </LocationField>  
```  
  
## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybut, elementy podrzędne i elementy nadrzędne.  
  
### <a name="attributes"></a>Atrybuty  
 Brak.  
  
### <a name="child-elements"></a>Elementy podrzędne  
 Brak.  
  
### <a name="parent-elements"></a>Elementy nadrzędne  
  
|Element|Opis|  
|-------------|-----------------|  
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Element wymagany.<br /><br /> Klasyfikuje szablon i definiuje sposób wyświetlania albo **nowy projekt**.|  
  
## <a name="text-value"></a>Wartość tekstowa  
 Wartość tekstowa jest wymagana.  
  
 Tekst prawidłowe wartości to:  
  
-   `Enabled`, która określa, że **lokalizacji** pole **nowy projekt** okno dialogowe jest włączona.  
  
-   `Disabled`, która określa, że **lokalizacji** pole **nowy projekt** okno dialogowe jest wyłączona.  
  
-   `Hidden`, która określa, że **lokalizacji** pole **nowy projekt** okno zostanie ukryte.  
  
## <a name="remarks"></a>Uwagi  
 Wartość domyślna to `Enabled`.  
  
 **Lokalizacji** polu tekstowym **nowy projekt** okno dialogowe umożliwia użytkownikom zmianę domyślnego katalogu, w którym zapisywane są nowe projekty.  
  
 Wartość określona w `Location` element jest tylko uznawane przez okno dialogowe, jeśli podstawowy system projektu obsługuje tę funkcję.  
  
## <a name="example"></a>Przykład  
 W poniższym przykładzie pokazano metadanych [!INCLUDE[csprcs](../includes/csprcs-md.md)] szablonu.  
  
```  
<VSTemplate Type="Project" Version="3.0.0"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>My template</Name>  
        <Description>A basic template</Description>  
        <Icon>TemplateIcon.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <LocationField>Disabled</LocationField>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="MyTemplate.csproj">  
            <ProjectItem>Form1.cs<ProjectItem>  
            <ProjectItem>Form1.Designer.cs</ProjectItem>  
            <ProjectItem>Program.cs</ProjectItem>  
            <ProjectItem>Properties\AssemblyInfo.cs</ProjectItem>  
            <ProjectItem>Properties\Resources.resx</ProjectItem>  
            <ProjectItem>Properties\Resources.Designer.cs</ProjectItem>  
            <ProjectItem>Properties\Settings.settings</ProjectItem>  
            <ProjectItem>Properties\Settings.Designer.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Tworzenie szablonów projektu i elementu](../ide/creating-project-and-item-templates.md)

