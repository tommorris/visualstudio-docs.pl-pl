---
title: ToolTaskExtension, klasa podstawowa | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- MSBuild.ToolTask.ToolCommandFailed
dev_langs:
- VB
- CSharp
- C++
- jsharp
ms.assetid: 258ae433-f68a-49f1-b276-da20e3472e68
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd535e28c7d229aa0a0468b60ee7e68181350dba
ms.sourcegitcommit: 55f7ce2d5d2e458e35c45787f1935b237ee5c9f8
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 08/22/2018
ms.locfileid: "42679913"
---
# <a name="tooltaskextension-base-class"></a>ToolTaskExtension — Klasa podstawowa
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Najnowszą wersję tego tematu znajduje się w temacie [tooltaskextension — klasa bazowa](https://docs.microsoft.com/visualstudio/msbuild/tooltaskextension-base-class).  
  
  
Wiele zadań, o których dziedziczy <xref:Microsoft.Build.Tasks.ToolTaskExtension> klasy, która dziedziczy z <xref:Microsoft.Build.Utilities.ToolTask> klasa, która sama dziedziczy <xref:Microsoft.Build.Utilities.Task> klasy. Ten łańcuch dziedziczenia dodaje kilka parametrów do zadań, które wynikają z nich. Te parametry są wymienione w niniejszym dokumencie.  
  
## <a name="parameters"></a>Parametry  
 W poniższej tabeli opisano parametry klas bazowych.  
  
|Parametr|Opis|  
|---------------|-----------------|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>|Opcjonalnie <xref:Microsoft.Build.Framework.IBuildEngine> parametru.<br /><br /> Określa dostępne dla zadań interfejsu aparatu kompilacji. Aparat kompilacji automatycznie ustawia tego parametru, aby zezwolić na wywołania zwrotnego do niego zadań.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>|Opcjonalnie <xref:Microsoft.Build.Framework.IBuildEngine2> parametru.<br /><br /> Określa dostępne dla zadań interfejsu aparatu kompilacji. Aparat kompilacji automatycznie ustawia tego parametru, aby zezwolić na wywołania zwrotnego do niego zadań.<br /><br /> Jest to właściwość wygody, tak aby autorzy zadań dziedziczenie z tej klasy będą musieli rzutować wartości z `IBuildEngine` do `IBuildEngine2`.|  
|<xref:Microsoft.Build.Utilities.Task.BuildEngine3%2A>|Opcjonalnie <xref:Microsoft.Build.Framework.IBuildEngine3> parametru.<br /><br /> Określa interfejs aparat kompilacji, które są udostępniane przez hosta.|  
|<xref:Microsoft.Build.Utilities.ToolTask.EchoOff%2A>|Opcjonalnie `bool` parametru.<br /><br /> Po ustawieniu `true`, to zadanie przekazuje **/q** do cmd.exe taki sposób, że w wierszu polecenia nie uzyskać skopiowane do strumienia wyjściowego stdout wiersza polecenia.|  
|<xref:Microsoft.Build.Utilities.ToolTask.EnvironmentVariables%2A>|Opcjonalnie `String` tablicy parametrów.<br /><br /> Tablica par zmiennych środowiskowych, oddzielone znaku równości. Te zmienne są Powodzenie do pliku wykonywalnego zduplikowanych oprócz "lub" selektywnie nadrzędnych blok regularnych środowiska.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ExitCode%2A>|Opcjonalnie `Int32` parametr tylko do odczytu danych wyjściowych.<br /><br /> Określa kod zakończenia, dostarczone przez wykonanego polecenia. Jeśli zadanie rejestrowane wszystkie błędy, ale proces ma kod zakończenia 0 (Powodzenie), to jest ustawiona na wartość -1.|  
|<xref:Microsoft.Build.Utilities.Task.HostObject%2A>|Opcjonalnie <xref:Microsoft.Build.Framework.ITaskHost> parametru.<br /><br /> Określa wystąpienie obiektu hosta (może być null). Aparat kompilacji ustawia tę właściwość, jeśli host IDE skojarzył obiekt hosta tego konkretnego zadania.|  
|<xref:Microsoft.Build.Tasks.ToolTaskExtension.Log%2A>|Opcjonalnie <xref:Microsoft.Build.Utilities.TaskLoggingHelper> parametru tylko do odczytu.<br /><br /> Pobiera wystąpienie elementu <xref:Microsoft.Build.Tasks.TaskLoggingHelperExtension> klasę, która zawiera metody rejestrowania zadań.|  
|<xref:Microsoft.Build.Utilities.ToolTask.LogStandardErrorAsError%2A>|Opcja `bool` parametru.<br /><br /> Jeśli `true`, wszystkie komunikaty odebrane na Standardowy strumień błędów są rejestrowane jako błędy.|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardErrorImportance%2A>|Opcjonalnie `String` parametru.<br /><br /> Ważność, z którą ma zostać tekst dziennika od planu standard out strumienia.|  
|<xref:Microsoft.Build.Utilities.ToolTask.StandardOutputImportance%2A>|Opcjonalnie `String` parametru.<br /><br /> Ważność, z którą ma zostać tekst dziennika od planu standard out strumienia.|  
|<xref:Microsoft.Build.Utilities.ToolTask.Timeout%2A>|Opcjonalne wirtualnej `Int32` parametru.<br /><br /> Określa ilość czasu w milisekundach, po których zostanie zakończony wykonywalnego zadania podrzędnego. Wartość domyślna to `Int.MaxValue`, wskazujący, że nie okres limitu czasu. Limit czasu wynosi (w milisekundach).|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolExe%2A>|Opcjonalne wirtualnej `string` parametru.<br /><br /> Projekty mogą implementować ten element, aby zastąpić ToolName. Zadania mogą zastąpić ten element, aby zachować ToolName.|  
|<xref:Microsoft.Build.Utilities.ToolTask.ToolPath%2A>|Opcjonalnie `string` parametru.<br /><br /> Określa lokalizację, z którym zadanie ładowania podstawowego pliku wykonywalnego. Jeśli nie określono tego parametru, zadanie używa ścieżki instalacji zestawu SDK, odpowiadającą wersję framework, na którym działa [!INCLUDE[vstecmsbuild](../includes/vstecmsbuild-md.md)].|  
|<xref:Microsoft.Build.Utilities.ToolTask.UseCommandProcessor%2A>|Opcjonalnie `bool` parametru.<br /><br /> Po ustawieniu `true`, to zadanie tworzy plik wsadowy, w wierszu polecenia i uruchamia go przy użyciu procesora poleceń zamiast bezpośrednio wykonywania polecenia.|  
|<xref:Microsoft.Build.Utilities.ToolTask.YieldDuringToolExecution%2A>|Opcjonalnie `bool` parametru.<br /><br /> Po ustawieniu `true`, to zadanie daje węzła, gdy jego zadanie jest wykonywane.|  
  
## <a name="see-also"></a>Zobacz też  
 [Odwołanie do zadania](../msbuild/msbuild-task-reference.md)   
 [Zadania](../msbuild/msbuild-tasks.md)



