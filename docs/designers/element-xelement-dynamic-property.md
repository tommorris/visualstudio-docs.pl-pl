---
title: Element (właściwość dynamiczna XElement)
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-designers
ms.topic: reference
apiname:
- XElement.Element
apitype: Assembly
ms.assetid: c6c25b8d-a1da-41ff-aeff-867ff1dcf749
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: bf8d964a41193d1db845a608749b0ca671dd9349
ms.sourcegitcommit: db680e8fa8066f905e7f9240342ece7ab9259308
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/09/2018
ms.locfileid: "37924056"
---
# <a name="element-xelement-dynamic-property"></a>Element (właściwość dynamiczna XElement)

Pobiera indeksatora używane do pobierania elementu podrzędnego wystąpienia elementu, który odpowiada określony rozwiniętej nazwy.

## <a name="syntax"></a>Składnia

```xaml
elem.Element[{namespaceName}localName]
```

## <a name="property-valuereturn-value"></a>Wartość właściwości/Zwracana wartość

Indeksator typu `XElement Item(String expandedName)`. Ten indeksator przyjmuje parametr rozwiniętej nazwy i zwraca odpowiedni <xref:System.Xml.Linq.XElement>, lub `null` Jeśli nie ma żadnego elementu o podanej nazwie.

## <a name="remarks"></a>Uwagi

Ta właściwość jest równoważna <xref:System.Xml.Linq.XContainer.Element%2A> metody <xref:System.Xml.Linq.XContainer?displayProperty=fullName> klasy.

## <a name="see-also"></a>Zobacz także

- <xref:System.Xml.Linq.XContainer.Element%2A?displayProperty=fullName>
- [Właściwości dynamiczne klasy XElement](../designers/xelement-class-dynamic-properties.md)
- [Elements](../designers/elements-xelement-dynamic-property.md)