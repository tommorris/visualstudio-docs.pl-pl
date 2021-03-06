---
title: '&lt;podpis&gt; (JavaScript) | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- <signature> JavaScript XML tag
- signature JavaScript XML tag
ms.assetid: 319138e7-cfbe-4b37-9643-2ddb7f9c63d4
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 5b6172609b68e1800dd71b9367d93a52596e88cf
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42631431"
---
# <a name="ltsignaturegt-javascript"></a>&lt;podpis&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [dokumentacja programu Visual Studio 2017](https://docs.microsoft.com/en-us/visualstudio/).  
  
Grupowanie zestawu powiązanych elementów dla funkcji lub metody, aby udostępnić dokumentację dla przeciążonych funkcji.  
  
## <a name="syntax"></a>Składnia  
  
```  
<signature externalid="id" externalFile="filename"  
    helpKeyword="keyword" locid="descriptionID">  
</signature>   
```  
  
#### <a name="parameters"></a>Parametry  
 `externalid`  
 Opcjonalna. Jeśli `format` atrybutu dla [ \<lokalizacja >](../ide/loc-javascript.md) element jest `vsdoc`, ten atrybut określa element członkowski identyfikator używany do zlokalizowania kodu XML, który jest skojarzony z sygnaturą. W przeciwieństwie do atrybutu `locid`, ten atrybut określa, czy wszystkie elementy w elemencie członkowskim, które mają ten identyfikator powinny być ładowane. Wszystkie skojarzone informacje opisu występujące w kodzie XML również zostaną scalone z elementami określonymi w podpisie. Dzięki temu można określić dodatkowe elementy, takie jak `<capability>`, w pliku sidecar bez określania ich w pliku źródłowym. `externalid` jest atrybutem opcjonalnym.  
  
 `externalFile`  
 Opcjonalna. Określa nazwę pliku, w którym ma znaleźć `externalid`. Atrybut ten jest ignorowany, jeśli nie występuje żaden `externalid`. Jest to atrybut opcjonalny. Wartością domyślną jest nazwa bieżącego pliku, ale z rozszerzeniem pliku .xml zamiast js. Domyślnie reguły wyszukiwania zarządzanego zasobu dla lokalizacji są używane do lokalizowania pliku.  
  
 `helpKeyword`  
 Opcjonalna. Słowo kluczowe dla pomocy F1.  
  
 `locid`  
 Opcjonalna. Identyfikator informacji o lokalizacji na temat pola. Identyfikator jest albo identyfikatorem elementu członkowskiego albo odpowiada wartości atrybutu `name` w wiązce wiadomości zdefiniowanej przez metadane OpenAjax. Identyfikator typu zależy od formatu określonego w [ \<lokalizacja >](../ide/loc-javascript.md) tagu.  
  
## <a name="remarks"></a>Uwagi  
 Należy użyć jednego elementu `<signature>` dla każdego przeciążonego opisu funkcji w pliku .js, lub użyć jednego elementu `<signature>` dla każdego określonego zewnętrznego identyfikatora elementu członkowskiego.  
  
 Element `<signature>` musi być umieszczony w ciele funkcji przed wszystkimi instrukcjami. Korzystając z [ \<podsumowania >](../ide/summary-javascript.md), [ \<param >](../ide/param-javascript.md), lub [ \<zwraca >](../ide/returns-javascript.md) elementów za pomocą `<signature>` elementu umieścić inne elementy wewnątrz `<signature>` bloku.  
  
## <a name="example"></a>Przykład  
 Poniższy kod ilustruje przykład użycia elementu `<signature>`.  
  
```javascript  
// Use of <signature> with externalid.  
// Requires use of the <loc> tag to identify the external functions.  
function illuminate(light) {  
    /// <signature externalid='M:Windows.Devices.Light.Illuminate()' />  
    /// <signature externalid='M:Windows.Devices.Light.Illuminate(System.Int32)'>  
    ///   <param name='light' type='Number' />  
    /// </signature>  
}  
  
// Use of <signature> for overloads implemented in JavaScript.  
function add(a, b) {  
    /// <signature>  
    /// <summary>function summary 1</summary>  
    /// <param name="a" type="Number">The first number</param>  
    /// <param name="b" type="Number">The second number</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 2 – differ by number of params</summary>  
    /// <param name="a" type="Number">Only 1 parameter</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 3 – differ by parameter type</summary>  
    /// <param name="a" type="Number">Number parameter</param>  
    /// <param name="b" type="String">String parameter</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 4 – differ by return type</summary>  
    /// <param name="a" type="Number">The first number</param>  
    /// <param name="b" type="Number">The second number</param>  
    /// <returns type="String" />  
    /// </signature>  
  
    return a + b;  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Komentarze dokumentacji XML](../ide/xml-documentation-comments-javascript.md)



