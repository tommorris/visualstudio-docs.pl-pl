---
title: 'Porady: tworzenie. Plik Vsct z istniejącej. Dyrektor ds. technologii pliku | Dokumentacja firmy Microsoft'
ms.custom: ''
ms.date: 2018-06-30
ms.prod: visual-studio-dev14
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-csharp
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- VSCT files, creating based on a .cto file
ms.assetid: 847717c9-477d-4ac9-8b2c-2da878912478
caps.latest.revision: 11
manager: douge
ms.openlocfilehash: e77ebf34cd56cee80040009cff3ebb2fee9befac
ms.sourcegitcommit: 6944ceb7193d410a2a913ecee6f40c6e87e8a54b
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/05/2018
ms.locfileid: "43774681"
---
# <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>Porady: tworzenie. Plik Vsct z istniejącej. Plik Dyrektor ds. technologii
Można utworzyć pliku vsct oparty na składni XML z istniejącego pliku binarnego .cto. W ten sposób pozwala na korzystanie z zalet nowego formatu kompilatora tabeli poleceń. Nawet wtedy, gdy plik .cto został skompilowany z plikiem .ctc działania tego procesu. Można edytować i skompilować pliku vsct w innym pliku .cto.  
  
### <a name="to-create-a-vsct-file-from-a-cto-file"></a>Do utworzenia pliku vsct z pliku .cto  
  
1.  Uzyskaj kopię pliku .cto i jego odpowiedni plik .ctsym.  
  
2.  Umieść pliki w tym samym katalogu co kompilatora vsct.exe.  
  
3.  W Visual Studio Command Prompt, przejdź do katalogu, który zawiera pliki .cto i .ctsym.  
  
4.  Typ **vsct.exe** _ctofilename_**.cto** _vsctfilename_**vsct -S**  _symfilename_**.ctsym**.  
  
     `ctofilename` jest nazwą pliku .cto `vsctfilename` jest nazwą pliku vsct, w której chcesz utworzyć, i `symfilename` jest nazwą pliku .ctsym.  
  
     Ten proces tworzy nowy vsct polecenia tabeli kompilatora plik XML. Można edytować i skompiluj plik za pomocą vsct.exe, kompilator vsct, tak jak dowolnego innego pliku vsct.  
  
## <a name="see-also"></a>Zobacz też  
 [Porady: tworzenie. Pliku Vsct](../extensibility/internals/how-to-create-a-dot-vsct-file.md)   
 [Tabela poleceń programu Visual Studio (pliki Vsct)](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)