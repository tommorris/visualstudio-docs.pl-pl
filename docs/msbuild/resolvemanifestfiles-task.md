---
title: Resolvemanifestfiles — zadanie | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- ResolveManifestFiles task [MSBuild]
- MSBuild, ResolveManifestFiles task
ms.assetid: e1e14f67-9b69-433f-94d4-a783a68676b2
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 82b265bc46e4d8edac666b4f73d5256e524f5b08
ms.sourcegitcommit: 0e5289414d90a314ca0d560c0c3fe9c88cb2217c
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/19/2018
ms.locfileid: "39151553"
---
# <a name="resolvemanifestfiles-task"></a>ResolveManifestFiles — zadanie
Jest rozpoznawana jako następujące elementy w procesie kompilacji plików do generowania manifestu: wbudowane elementy, zależności, satelity, zawartość, symbole debugowania i dokumentację.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry `ResolveManifestFiles` zadania.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|`DeploymentManifestEntryPoint`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa nazwę pliku manifestu wdrożenia.|  
|`EntryPoint`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametru.<br /><br /> Określa zestaw zarządzany lub dokumentacja manifestu ClickOnce, która jest punktem wejścia do manifestu.|  
|`ExtraFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa dodatkowe pliki.|  
|`ManagedAssemblies`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa zestawy zarządzane.|  
|`NativeAssemblies`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa zestawy natywnych.|  
|`OutputAssemblies`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Określa generowanych zestawów.|  
|`OutputDeploymentManifestEntryPoint`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametr wyjściowy.<br /><br /> Określa punkt wejścia manifestu wdrożenia danych wyjściowych.|  
|`OutputEntryPoint`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> parametr wyjściowy.<br /><br /> Określa punkt wejścia w danych wyjściowych.|  
|`OutputFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametr wyjściowy.<br /><br /> Określa pliki wyjściowe.|  
|`PublishFiles`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa pliki publikowania.|  
|`SatelliteAssemblies`|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskItem> `[]` parametru.<br /><br /> Określa, czy zestawy satelickie|  
|`SigningManifests`|Opcjonalnie `Boolean` parametru.<br /><br /> Jeśli `true`, podpisaniu manifestów.|  
|`TargetCulture`|Opcjonalnie `String` parametru.<br /><br /> Określa kulturę docelowym dla zestawów satelickich.|  
|`TargetFrameworkVersion`|Opcjonalnie `String` parametru.<br /><br /> Określa docelową wersję platformy .NET.|  
  
## <a name="remarks"></a>Uwagi  
 Oprócz parametrów, które są wymienione w tabeli, to zadanie dziedziczy parametry z <xref:Microsoft.Build.Tasks.TaskExtension> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Aby uzyskać listę tych dodatkowych parametrów i ich opisów, zobacz [taskextension — klasa bazowa](../msbuild/taskextension-base-class.md).  
  
## <a name="see-also"></a>Zobacz także  
 [Zadania](../msbuild/msbuild-tasks.md)   
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)