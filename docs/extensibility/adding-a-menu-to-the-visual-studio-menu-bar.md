---
title: Dodawanie Menu na pasku Menu programu Visual Studio | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, creating top level
- top-level menus
ms.assetid: 58fc1a31-2aeb-441c-8e48-c7d5cbcfe501
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c95007ed5b740812ca2b1a269390fbad6ffbc2ba
ms.sourcegitcommit: 8ee7efb70a1bfebcb6dd9855b926a4ff043ecf35
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/17/2018
ms.locfileid: "39079536"
---
# <a name="add-a-menu-to-the-visual-studio-menu-bar"></a>Dodawanie menu na pasku menu programu Visual Studio
W tym instruktażu przedstawiono sposób dodawania menu na pasku menu programu Visual Studio zintegrowane środowisko programistyczne (IDE). Pasek menu IDE zawiera menu Kategorie, takie jak **pliku**, **Edytuj**, **widoku**, **okna**, i **pomocy** .  
  
 Przed dodaniem nowego menu na pasku menu programu Visual Studio, należy rozważyć, czy poleceń powinny zostać umieszczone w ramach istniejącego menu. Aby uzyskać więcej informacji na temat położenie polecenia zobacz [menu i poleceń dla programu Visual Studio](../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md).  
  
 Menu są deklarowane w *vsct* pliku projektu. Aby uzyskać więcej informacji na temat menu i *vsct* plików, zobacz [polecenia, menu i paski narzędzi](../extensibility/internals/commands-menus-and-toolbars.md).  
  
 Przez ukończenie tego instruktażu, można utworzyć menu o nazwie **TestMenu** zawierający jednego polecenia.  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 Począwszy od programu Visual Studio 2015, możesz nie należy instalować programu Visual Studio SDK z Centrum pobierania. Jest dołączony jako opcjonalna funkcja w Instalatorze programu Visual Studio. Możesz także zainstalować zestaw SDK programu VS później. Aby uzyskać więcej informacji, zobacz [instalacji programu Visual Studio SDK](../extensibility/installing-the-visual-studio-sdk.md).  
  
## <a name="create-a-vsix-project-that-has-a-custom-command-item-template"></a>Utwórz projekt VSIX, zawierający szablon elementu polecenie niestandardowe  
  
1.  Utwórz projekt VSIX, o nazwie `TopLevelMenu`. Można znaleźć szablonu projektu VSIX w **nowy projekt** , okno dialogowe **Visual C#** / **rozszerzalności**.  Aby uzyskać więcej informacji, zobacz [Tworzenie rozszerzenia za pomocą polecenia menu](../extensibility/creating-an-extension-with-a-menu-command.md).  
  
2.  Po otwarciu projektu, Dodaj polecenie niestandardowe szablon elementu o nazwie **TestCommand**. W **Eksploratora rozwiązań**, kliknij prawym przyciskiem myszy węzeł projektu i wybierz **Add / nowy element**. W **Dodaj nowy element** okno dialogowe, przejdź do **Visual C# / rozszerzalności** i wybierz **polecenia niestandardowego**. W **nazwa** u dołu okna, Zmień nazwę pliku polecenia, aby *TestCommand.cs*.  
  
## <a name="create-a-menu-on-the-ide-menu-bar"></a>Tworzenie menu na pasku menu środowiska IDE  
  
1.  W **Eksploratora rozwiązań**, otwórz *TestCommandPackage.vsct*.  
  
     Na końcu pliku istnieje \<symbole > węzeł, który zawiera kilka \<GuidSymbol > węzłów. W węźle, nazwane guidTestCommandPackageCmdSet Dodaj nowy symbol w następujący sposób:  
  
    ```xml  
    <IDSymbol name="TopLevelMenu" value="0x1021"/>  
    ```  
  
2.  Utwórz pustą \<menu > w węźle \<polecenia > węzła, tuż przed \<grupy >. W \<menu > węzła, Dodaj \<Menu > węzła, w następujący sposób:  
  
    ```xml  
    <Menus>  
          <Menu guid="guidTestCommandPackageCmdSet" id="TopLevelMenu" priority="0x700" type="Menu">  
            <Parent guid="guidSHLMainMenu"  
                    id="IDG_VS_MM_TOOLSADDINS" />  
            <Strings>  
              <ButtonText>TestMenu</ButtonText>  
              <CommandName>TestMenu</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     `guid` i `id` wartości menu określić zestaw poleceń i menu określonych w zestaw poleceń.  
  
     `guid` i `id` wartości elementu nadrzędnego pozycji menu w sekcji pasek menu programu Visual Studio, który zawiera menu Narzędzia i Add-ins.  
  
     Wartość `CommandName` ciąg Określa, że tekst powinien pojawić się w elemencie menu.  
  
3.  W \<grupy > sekcji, Znajdź \<grupy > i zmień \<nadrzędnego > elementu, aby wskazać polecenie menu, który właśnie został dodany:  
  
    ```csharp  
    <Groups>  
          <Group guid="guidTestCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
            <Parent guid="guidTestCommandPackageCmdSet" id="TopLevelMenu"/>  
          </Group>  
        </Groups>  
    ```  
  
     Dzięki temu grupy część nowego menu.  
  
4.  Znajdź `Buttons` sekcji. Należy zauważyć, że [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] został wygenerowany szablon pakietu `Button` element, który ma nadrzędnego równa `MyMenuGroup`. W wyniku tego polecenia pojawi się w menu.  
  
## <a name="build-and-test-the-extension"></a>Tworzenie i testowanie rozszerzenia  
  
1.  Skompiluj projekt, a następnie rozpocząć debugowanie. Wystąpienie doświadczalne wystąpienie powinna zostać wyświetlona.  
  
2.  Na pasku menu w eksperymentalnym wystąpieniu powinien zawierać **TestMenu** menu.  
  
3.  Na **TestMenu** menu, kliknij przycisk **Wywołaj polecenie Test**.  
  
     Okno komunikatu powinno pojawiają się i wyświetli komunikat "TestCommand pakietu wewnątrz TopLevelMenu.TestCommand.MenuItemCallback()". Oznacza to, że nowe polecenie działa.  
  
## <a name="see-also"></a>Zobacz także  
 [Polecenia, menu i paski narzędzi](../extensibility/internals/commands-menus-and-toolbars.md)