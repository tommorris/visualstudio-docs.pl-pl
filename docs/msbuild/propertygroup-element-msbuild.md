---
title: PropertyGroup — Element (MSBuild) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 03/13/2017
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/msbuild/2003#PropertyGroup
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- <PropertyGroup> element [MSBuild]
- PropertyGroup element [MSBuild]
ms.assetid: ff1e6c68-b9a1-4263-a1ce-dc3b829a64d4
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: e8c532692b7faddd90a3a67ffdd52b512511d719
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39152191"
---
# <a name="propertygroup-element-msbuild"></a>PropertyGroup — element (MSBuild)
Zawiera zestaw zdefiniowanych przez użytkownika [właściwość](../msbuild/property-element-msbuild.md) elementów. Każdy `Property` elementu używanego przy [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] projektu musi być obiektem podrzędnym obiektu `PropertyGroup` elementu.  

 \<Project>  
 \<PropertyGroup>  

## <a name="syntax"></a>Składnia  

```xml  
<PropertyGroup Condition="'String A' == 'String B'">  
    <Property1>...</Property1>  
    <Property2>...</Property2>  
</PropertyGroup>  
```  

## <a name="attributes-and-elements"></a>Atrybuty i elementy  
 W poniższych sekcjach opisano atrybuty, elementy podrzędne i elementy nadrzędne.  

### <a name="attributes"></a>Atrybuty  

|Atrybut|Opis|  
|---------------|-----------------|  
|Warunek|Atrybut opcjonalny.<br /><br /> Warunek, który ma zostać obliczone. Aby uzyskać więcej informacji, zobacz [warunki](../msbuild/msbuild-conditions.md).|  

### <a name="child-elements"></a>Elementy podrzędne  

|Element|Opis|  
|-------------|-----------------|  
|[Property](../msbuild/property-element-msbuild.md)|Element opcjonalny.<br /><br /> Właściwości zdefiniowane nazwę użytkownika, który zawiera wartość właściwości. Może wynosić zero lub więcej *właściwość* elementów w `PropertyGroup` elementu.|  

### <a name="parent-elements"></a>Elementy nadrzędne  

|Element|Opis|  
|-------------|-----------------|  
|[Project](../msbuild/project-element-msbuild.md)|Element główny wymagany [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] pliku projektu.|  

## <a name="example"></a>Przykład  
 Poniższy przykład kodu pokazuje sposób ustawiania właściwości na podstawie warunku. W tym przykładzie Jeśli wartość `CompileConfig` właściwość `DEBUG`, `Optimization`, `Obfuscate`, i `OutputPath` właściwości wewnątrz `PropertyGroup` elementu są ustawione.  

```xml  
<PropertyGroup Condition="'$(CompileConfig)' == 'DEBUG'" >  
    <Optimization>false</Optimization>  
    <Obfuscate>false</Obfuscate>  
    <OutputPath>$(OutputPath)\debug</OutputPath>  
</PropertyGroup>  
```  

## <a name="see-also"></a>Zobacz także  
 [Odwołanie do schematu pliku projektu](../msbuild/msbuild-project-file-schema-reference.md)  
 [Właściwości programu MSBuild](../msbuild/msbuild-properties.md)
