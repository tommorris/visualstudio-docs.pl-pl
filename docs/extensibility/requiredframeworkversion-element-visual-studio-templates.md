---
title: RequiredFrameworkVersion, Element (szablony Visual Studio) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <RequiredFrameworkVersion> (Visual Studio Templates)
- RequiredFrameworkVersion (Visual Studio Templates)
ms.assetid: 08a4f609-51a5-4723-b89f-99277fb18871
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 23538e8e00553322f4f04e50414a8b3ddbd73b91
ms.sourcegitcommit: 06db1892fff22572f0b0a11994dc547c2b7e2a48
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/08/2018
ms.locfileid: "39635925"
---
# <a name="requiredframeworkversion-element-visual-studio-templates"></a>RequiredFrameworkVersion, element (szablony Visual Studio)

Określa minimalną wersję systemu .NET Framework, która jest wymagana przez szablon. Powoduje ono **wersji platformy docelowej** listy rozwijanej do wyświetlania w **nowy projekt** okna dialogowego. `RequiredFrameworkVersion` Element określa również najniższej wartości dostępne na liście rozwijanej.

> [!IMPORTANT]
> Począwszy od programu Visual Studio 2017 w wersji 15.6, **wersji platformy docelowej** listy rozwijanej nie jest już filtr dla szablonów wyświetlanych w **szablony** części **nowy projekt** okna dialogowego. Zamiast tego listy rozwijanej działa jako selektora framework, dla wybranego szablonu.

 \<VSTemplate > \<TemplateData > \<RequiredFrameworkVersion >

## <a name="syntax"></a>Składnia

```xml
<RequiredFrameworkVersion> .... </RequiredFrameworkVersion>
```

## <a name="attributes-and-elements"></a>Atrybuty i elementy
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.

### <a name="attributes"></a>Atrybuty
 Brak.

### <a name="child-elements"></a>Elementy podrzędne
 Brak.

### <a name="parent-elements"></a>Elementy nadrzędne

|Element|Opis|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Element wymagany.<br /><br /> Klasyfikuje szablon i definiuje sposób wyświetlania albo **nowy projekt** lub **Dodaj nowy element** okno dialogowe.|

## <a name="text-value"></a>Wartość tekstowa
 Wartość tekstowa jest wymagana.

 Tekst musi być minimalny numer wersji systemu .NET Framework, która jest wymagana dla szablonu.

## <a name="remarks"></a>Uwagi

`RequiredFrameworkVersion` element jest opcjonalny. Użyj tego elementu tylko wtedy, gdy szablon obsługuje określoną wersję minimalną (i nowszych wersjach, jeśli istnieje) programu .NET Framework. Jeśli określisz `RequiredFrameworkVersion` elementu i szablonu nie obsługuje określonej minimalnej wersji systemu .NET Framework **wersji platformy docelowej** Wyświetla listę rozwijaną, gdy nie ma zastosowania.

## <a name="example"></a>Przykład

W poniższym przykładzie pokazano metadanych dla standardowego [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] szablonu klasy.

```xml
<VSTemplate Type="Item" Version="3.0.0"
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">
    <TemplateData>
        <Name>MyClass</Name>
        <Description>My custom C# class template.</Description>
        <Icon>Icon.ico</Icon>
        <ProjectType>CSharp</ProjectType>
        <RequiredFrameworkVersion>3.0</RequiredFrameworkVersion>
        <MaxFrameworkVersion>4.7.1</MaxFrameworkVersion>
        <DefaultName>MyClass</DefaultName>
    </TemplateData>
    <TemplateContent>
        <ProjectItem>MyClass.cs</ProjectItem>
    </TemplateContent>
</VSTemplate>
```

W tym przykładzie minimalnej wersji systemu .NET Framework, która jest wymagana przez szablon, reprezentowane przez `RequiredFrameworkVersion`, to 3.0. Projekt, który został utworzony za pomocą tego szablonu można wskazać wersje programu .NET Framework, począwszy od 3.0.

## <a name="see-also"></a>Zobacz także

- [Odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md)
- [Tworzenie szablonów projektów i elementów](../ide/creating-project-and-item-templates.md)
- [Odwoływać się do określonej wersji środowiska .NET Framework](../ide/targeting-a-specific-dotnet-framework-version.md)
