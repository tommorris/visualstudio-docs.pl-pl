---
title: Resolvenonmsbuildprojectoutput — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- MSBuild, ResolveNonMSBuildProjectOutput task
- ResolveNonMSBuildProjectOutput task [MSBuild]
ms.assetid: a0b8fcec-8c8d-4867-85ac-5304c5108e5e
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 48a67d895c08d5966c2ea4b40140382db9157763
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42676486"
---
# <a name="resolvenonmsbuildprojectoutput-task"></a>ResolveNonMSBuildProjectOutput — Zadanie
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [resolvenonmsbuildprojectoutput — zadanie](https://docs.microsoft.com/visualstudio/msbuild/resolvenonmsbuildprojectoutput-task).  
  
  
Określa pliki wyjściowe dla odwołań do projektu niekorzystających z programu MSBuild.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `ResolveNonMSBuildProjectOutput` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`PreresolvedProjectOutputs`|Opcjonalnie `String` parametru.<br /><br /> Określa, że ciągu XML, który zawiera rozwiązane dane wyjściowe projektu.|  
|`ProjectReferences`|Wymagany parametr interfejsu <xref:Microsoft.Build.Framework.ITaskItem>`[]`.<br /><br /> Określa odwołania do projektu.|  
|`ResolvedOutputPaths`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Zawiera listę ścieżek rozpoznanych odwołań (i zachowuje oryginalne atrybutach odwołania projektu).|  
|`UnresolvedProjectReferences`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Zawiera listę elementów odniesienia projektu, których nie można rozwiązać za pomocą preresolved listy wyników.<br /><br /> Ponieważ program Visual Studio preresolves tylko projekty niekorzystających z programu MSBuild, oznacza to, że odwołania projektu na tej liście są w formacie programu MSBuild.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów, które są wymienione w tabeli, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz też  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)



