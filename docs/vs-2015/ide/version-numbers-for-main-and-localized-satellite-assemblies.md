---
title: Numery wersji dla głównych i zlokalizowanych zestawów satelickich | Dokumentacja firmy Microsoft
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
- satellite assemblies, version numbers
- SatelliteContractVersionAttribute
- version numbers, assemblies
- assemblies [Visual Studio], version numbers
- versioning, assemblies
ms.assetid: 5489aea1-57b4-4561-9bb4-24d490269602
caps.latest.revision: 13
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 041c23c56b99ec1abba43081d6422f0f05d05e60
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42675023"
---
# <a name="version-numbers-for-main-and-localized-satellite-assemblies"></a>Numery wersji dla głównych i zlokalizowanych zestawów satelickich
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

<xref:System.Resources.SatelliteContractVersionAttribute> Klasy obsługuje przechowywanie wersji głównej zestawu, który używa zlokalizowane zasoby przy użyciu usługi resource manager. Stosowanie <xref:System.Resources.SatelliteContractVersionAttribute> do aplikacji w głównym zestawie pozwala zaktualizować i ponownie wdrożyć zestaw bez aktualizowania swoich zestawów satelickich. Na przykład, można użyć <xref:System.Resources.SatelliteContractVersionAttribute> klasy dodatku service pack, który nie wprowadzają nowych zasobów bez ponownego kompilowania lub wdrażania zestawów satelickich. Zlokalizowanych zasobów była dostępna, musi być zgodna wersja kontraktu satelickie zestawu głównego <xref:System.Reflection.AssemblyVersionAttribute> klasy zestawów satelickich. Należy określić numer wersji dokładnie w <xref:System.Resources.SatelliteContractVersionAttribute>; znaki symboli wieloznacznych, takich jak "*" nie są dozwolone. Aby uzyskać więcej informacji, zobacz [podczas pobierania zasobów](http://msdn.microsoft.com/library/eca16922-1c46-4f68-aefe-e7a12283641f).  
  
## <a name="updating-assemblies"></a>Aktualizowanie zestawów  
 <xref:System.Resources.SatelliteContractVersionAttribute> Klasy umożliwia zaktualizowanie głównym zestawie bez konieczności aktualizowania Twojego zestawu satelickiego i na odwrót. Po zaktualizowaniu zestawu głównego, jego numer wersji zestawu jest zmieniany. Jeśli chcesz kontynuować korzystanie z istniejących zestawów satelickich, należy zmienić numer wersji zestawu głównego, ale numer wersji kontraktu satelitarnej pozostaną bez zmian. Na przykład w swojej pierwszej wersji używanej wersji zestawu głównego może być 1.0.0.0. Wersja kontraktu satelitarne i wersji zestawu zestawu satelickiego będzie również 1.0.0.0. Jeśli musisz zaktualizować swojego głównego zestawu z dodatkiem Service Pack, możesz zmienić wersję zestawu do 1.0.0.1, przy jednoczesnym zachowaniu wersja kontraktu satelitarne i wersję zestawu satelickiego jako 1.0.0.0.  
  
 W razie potrzeby można zaktualizować zestawu satelickiego, ale nie głównym zestawie, zmienić <xref:System.Reflection.AssemblyVersionAttribute> zestawu satelickiego. Wraz z zestawem satelickim trzeba będzie wysłać zestaw zasad, z informacją o tym, że Twojego nowego zestawu satelickiego jest zgodna z swoje stare zestawu satelickiego. Aby uzyskać więcej informacji na temat zasad, zobacz [jak środowisko uruchomieniowe lokalizuje zestawy](http://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34).  
  
 Poniższy kod przedstawia sposób ustawiania wersja kontraktu satelity. Kod można umieścić w skrypcie kompilacji lub w pliku AssemblyInfo.vb lub AssemblyInfo.cs.  
  
```vb  
<Assembly: SatelliteContractVersionAttribute("4.3.2.1")>  
  
```  
  
```csharp  
[assembly: SatelliteContractVersionAttribute("4.3.2.1")]  
```  
  
## <a name="see-also"></a>Zobacz też  
 [Jak środowisko uruchomieniowe lokalizuje zestawy](http://msdn.microsoft.com/library/772ac6f4-64d2-4cfb-92fd-58096dcd6c34)   
 [Konfigurowanie atrybutów zestawu](http://msdn.microsoft.com/library/36a98a81-b5b5-4c19-912a-11f91eff7f4e)   
 [Zabezpieczenia a zlokalizowane zestawy satelickie](../ide/security-and-localized-satellite-assemblies.md)   
 [Lokalizowanie aplikacji](../ide/localizing-applications.md)   
 [Globalizowanie i lokalizowanie aplikacji](../ide/globalizing-and-localizing-applications.md)

