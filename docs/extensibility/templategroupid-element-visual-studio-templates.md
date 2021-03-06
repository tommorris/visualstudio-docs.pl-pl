---
title: TemplateGroupID — Element (szablony Visual Studio) | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-general
ms.topic: conceptual
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateGroupID
helpviewer_keywords:
- TemplateGroupID element [Visual Studio Templates]
- <TemplateGroupID> element [Visual Studio Templates]
ms.assetid: bce7b49a-90bc-4691-aff3-a87e209f6d83
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 91631975d48f6e7e13646c428cdd5b5473bbeed2
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31144440"
---
# <a name="templategroupid-element-visual-studio-templates"></a>TemplateGroupID — Element (szablony Visual Studio)
Określa, jaki rodzaj projektu szablonów elementów będą widoczne w. Ten element jest istotne, kiedy [ShowByDefault (szablony Visual Studio)](../extensibility/showbydefault-visual-studio-templates.md) ma ustawioną wartość `false`. Gdy [ShowByDefault (szablony Visual Studio)](../extensibility/showbydefault-visual-studio-templates.md) ma ustawioną wartość `true`, szablon elementu jest dostępna we wszystkich typach projektu.  
  
 \<VSTemplate>  
 \<TemplateData >  
 \<TemplateGroupID >  
  
## <a name="syntax"></a>Składnia  
  
```  
<TemplateGroupID> ... </TemplateGroupID>  
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
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|Kategoryzuje szablonu i definiuje sposób wyświetlania albo **nowy projekt** lub **Dodaj nowy element** okno dialogowe.|  
  
## <a name="text-value"></a>Wartość tekstowa  
 Wartość tekstowa jest wymagana.  
  
 Tekst Określa identyfikator kategorii szablonów elementów.  
  
## <a name="remarks"></a>Uwagi  
 `TemplateGroupID` jest elementem.  
  
 Wartość `TemplateGroupID` element jest używany wraz z rejestracji systemu projektu (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\*\<numer wersji >* \Projects\\) Szablony filtru, które pojawiają się w **Dodaj nowy element** okno dialogowe.  
  
|Visual C++ wartość|Znaczenie|  
|------------------------|-------------|  
|VC natywne|Używany dla projektów natywnych. Również domyślny, jeśli nie można określić typu projektu.|  
|Zarządzane VC|Używany do zarządzanego (/ clr) projektów|  
|VC Windows|Używane dla wszystkich projektów przeznaczonych dla platformy systemu windows (macierzysty/managed/magazyn)|  
|WinRT-Native-UAP|Używane w przypadku projektów Sklepu Windows 10|  
|CodeSharing natywne|Używane w przypadku projektów elementu Shared|  
|WinRT-Native-6.3|Używane w przypadku projektów Sklepu Windows 8.1|  
|WinRT-Native-Phone-6.3|Używane w przypadku projektów Windows Phone 8.1|  
|Natywne WinRT|Używane w przypadku projektów Sklepu Windows 8.0|  
|VC Android|Używane w przypadku projektów dla systemu Android|  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do schematu szablonu Visual Studio](../extensibility/visual-studio-template-schema-reference.md)   
 [Tworzenie szablonów projektu i elementu](../ide/creating-project-and-item-templates.md)