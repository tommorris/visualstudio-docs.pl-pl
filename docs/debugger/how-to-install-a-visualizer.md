---
title: 'Porady: Instalacja programu Visualizer | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 87feaebf16168744467137fdf4af54538a316cdf
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31473780"
---
# <a name="how-to-install-a-visualizer"></a>Porady: instalacja programu Visualizer
Po utworzeniu wizualizatora, należy zainstalować wizualizatora, dzięki czemu będzie on dostępny w [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Instalowanie wizualizatora jest prosty proces.  
  
> [!NOTE]
>  W aplikacji platformy uniwersalnej systemu Windows, tylko tekstu standardowego, HTML, XML i JSON wizualizatorów są obsługiwane. Wizualizatory niestandardowe (utworzonych przez użytkownika) są nieobsługiwane.  
  
### <a name="to-install-a-visualizer"></a>Aby instalacja programu visualizer  
  
1.  Zlokalizuj biblioteki DLL zawierającej utworzonej wizualizatora.  
  
2.  Skopiuj bibliotekę DLL do jednej z następujących lokalizacji:  
  
    -   *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    -   `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3.  Jeśli chcesz użyć zarządzany Wizualizator do zdalnego debugowania, skopiuj plik DLL do tej samej ścieżki na komputerze zdalnym.  
  
4.  Uruchom ponownie sesję debugowania.  
  
## <a name="see-also"></a>Zobacz też  
 [Utwórz niestandardowe Wizualizatory](../debugger/create-custom-visualizers-of-data.md)   
 [Porady: pisanie wizualizatora](../debugger/how-to-write-a-visualizer.md)