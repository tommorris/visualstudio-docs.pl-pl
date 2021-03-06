---
title: Właściwości relacji domeny | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-tfs-dev14
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Domain-Specific Language, domain relationships
ms.assetid: 9ccb3dc2-b80c-4585-932f-3c5f87bafbcd
caps.latest.revision: 22
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: ff37703643dc9d1c795fe10b5f24154ee46174af
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42629413"
---
# <a name="properties-of-domain-relationships"></a>Właściwości relacji domeny
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [właściwości relacji domeny](https://docs.microsoft.com/visualstudio/modeling/properties-of-domain-relationships).  
  
W poniższej tabeli przedstawiono właściwości są skojarzone z relacją domeny. Aby uzyskać informacji na temat relacji domeny, zobacz [objaśnienie modeli, klas i relacji](../modeling/understanding-models-classes-and-relationships.md). Aby uzyskać więcej informacji o tym, jak korzystać z tych właściwości, zobacz [dostosowywanie i rozszerzanie języka specyficznego dla domeny](../modeling/customizing-and-extending-a-domain-specific-language.md).  
  
|Właściwość|Opis|Domyślny|  
|--------------|-----------------|-------------|  
|Modyfikator dostępu|Poziom dostępu relacji domeny (`public` lub `internal`).|`public`|  
|Atrybuty niestandardowe|Służy do dodawania atrybutów do klasy kodu źródłowego, która jest generowany na podstawie relacji domeny.|\<Brak >|  
|Generuje Double pochodne|Jeśli `True`, generowany jest zarówno klasy bazowej, jak i klasy częściowej (obsługuje dostosowywania przy użyciu zastąpień). Aby uzyskać więcej informacji, zobacz [zastępowanie i rozszerzanie wygenerowanych klas](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Ma konstruktora niestandardowego|Jeśli `True`, wskazuje, że Konstruktor niestandardowy znajduje się w kodzie źródłowym. Aby uzyskać więcej informacji, zobacz [zastępowanie i rozszerzanie wygenerowanych klas](../modeling/overriding-and-extending-the-generated-classes.md).|`False`|  
|Modyfikator dziedziczenia|Opisuje typ dziedziczenia klasy kodu źródłowego, która jest generowany na podstawie relacji domeny (`none`, `abstract` lub `sealed`).|\<Brak >|  
|Umożliwia tworzenie duplikatów|Jeśli `True`, może zostać utworzony duplikatów linków relacji domeny między dwoma tymi samymi elementami.|`False`|  
|Relacji podstawowych|Jeśli domena relacja jest relacją pochodną, relacja podstawowa tej relacji domeny.|\<Brak >|  
|Jest osadzania|Jeśli `True`, relacji domeny relacja osadzania. Jeśli `False`, relacja jest relacją odwołania.|\<both>|  
|Nazwa|Nazwa relacji domeny.|Bieżąca nazwa|  
|Przestrzeń nazw|Przestrzeń nazw, która jest połączona z relacji domeny.|Bieżąca przestrzeń nazw|  
|Uwagi|Uwagi informacyjne, które są skojarzone z relacji domeny.|\<Brak >|  
|Opis|Opis, który jest używany do dokumentowania kodu i jest używany w Interfejsie użytkownika wygenerowanego projektanta.|\<Brak >|  
|Nazwa wyświetlana|Nazwa która jest wyświetlana w wygenerowanym projektancie dla relacji domeny.|\<Brak >|  
|Słowo kluczowe pomocy|Opcjonalne słowo kluczowe, które jest używane do indeksowania pomocy F1 dla relacji domeny.|\<Brak >|  
  
## <a name="see-also"></a>Zobacz też  
 [Słownik narzędzi języka specyficznego dla domeny](http://msdn.microsoft.com/en-us/ca5e84cb-a315-465c-be24-76aa3df276aa)



