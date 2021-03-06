---
title: Tworzenie edytorze podstawowych i rejestrowanie typu pliku w edytorze | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - walkthrough
ms.assetid: 24d2bffd-a35c-46db-8515-fd60b884b7fb
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3ee391ce1200cce03e83f80b6f345ead4cd03199
ms.sourcegitcommit: 9765b3fcf89375ca499afd9fc42cf4645b66a8a2
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 09/20/2018
ms.locfileid: "46495248"
---
# <a name="walkthrough-create-a-core-editor-and-registering-an-editor-file-type"></a>Przewodnik: Tworzenie edytora podstawowych i rejestrując typu pliku w edytorze
W tym instruktażu przedstawiono sposób tworzenia pakietu VSPackage, który rozpoczyna się [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] podstawowy edytor, gdy plik za pomocą *.myext* rozszerzenie nazwy pliku jest ładowany.  
  
## <a name="prerequisites"></a>Wymagania wstępne  
 Aby skorzystać z tego przewodnika, należy zainstalować program Visual Studio SDK. Aby uzyskać więcej informacji, zobacz [programu Visual Studio SDK](../extensibility/visual-studio-sdk.md).  
  
## <a name="locations-for-the-visual-studio-package-project-template"></a>Lokalizacje dla szablonu projektu pakietu Visual Studio  
 Szablon projektu pakietu Visual Studio można znaleźć w trzech różnych miejscach w **nowy projekt** okno dialogowe:  
  
1.  W obszarze **rozszerzalności programu Visual Basic**. Domyślny język projektu jest języka Visual Basic.  
  
2.  W obszarze **rozszerzalność języka C#**. Domyślny język projektu jest C#.  
  
3.  W obszarze **innych typów projektów rozszerzalności**. Domyślny język projektu jest w języku C++.  
  
### <a name="to-create-the-vspackage"></a>Do utworzenia pakietu VSPackage  
  
-   Rozpocznij [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] i utworzyć [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] pakietu VSPackage o nazwie `MyPackage`, zgodnie z opisem w [Instruktaż: utworzyć polecenie menu pakietu VSPackage](https://msdn.microsoft.com/library/d699c149-5d1e-47ff-94c7-e1222af02c32).  
  
### <a name="to-add-the-editor-factory"></a>Aby dodać fabryka edytorów  
  
1.  Kliknij prawym przyciskiem myszy **MyPackage** projekt, wskaż opcję **Dodaj**, a następnie kliknij przycisk **klasy**.  
  
2.  W **Dodaj nowy element** okna dialogowego pole, upewnij się, **klasy** zaznaczony jest szablon, typ `EditorFactory.cs` nazwę, a następnie kliknij przycisk **Dodaj** Aby dodać klasę do projektu.  
  
     *EditorFactory.cs* pliku powinno zostać automatycznie otwarte.  
  
3.  Odwołuje się do następujących zestawów w kodzie.  
  
    ```vb  
    Imports System.Runtime.InteropServices  
    Imports Microsoft.VisualStudio  
    Imports Microsoft.VisualStudio.Shell  
    Imports Microsoft.VisualStudio.Shell.Interop  
    Imports Microsoft.VisualStudio.OLE.Interop  
    Imports Microsoft.VisualStudio.TextManager.Interop  
    Imports IOleServiceProvider = Microsoft.VisualStudio.OLE.Interop.IServiceProvider  
    ```  
  
    ```csharp  
    using System.Runtime.InteropServices;  
    using Microsoft.VisualStudio;  
    using Microsoft.VisualStudio.Shell;  
    using Microsoft.VisualStudio.Shell.Interop;  
    using Microsoft.VisualStudio.OLE.Interop;  
    using Microsoft.VisualStudio.TextManager.Interop;  
    using IOleServiceProvider = Microsoft.VisualStudio.OLE.Interop.IServiceProvider;  
  
    ```  
  
4.  Dodaj identyfikator GUID, `EditorFactory` klasy, dodając `Guid` atrybut bezpośrednio przed deklaracją klasy.  
  
     Nowy identyfikator GUID można wygenerować za pomocą *guidgen.exe* program na [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] wierszu polecenia, lub przez kliknięcie przycisku **Utwórz GUID** na **narzędzia** menu. Identyfikator GUID używany w tym miejscu jest tylko przykładem; nie należy używać go w projekcie.  
  
    ```vb  
    <Guid("0eea3187-c5fa-48d4-aa72-b5eecd3b17b1")> _  
    ```  
  
    ```csharp  
    [Guid("0eea3187-c5fa-48d4-aa72-b5eecd3b17b1")]   
    ```  
  
5.  W definicji klasy Dodaj dwie zmienne prywatne pakietu podrzędnego i dostawcy usług.  
  
    ```vb  
    Class EditorFactory  
        Private parentPackage As Package  
        Private serviceProvider As IOleServiceProvider  
    ```  
  
    ```csharp  
    class EditorFactory  
    {  
        private Package parentPackage;  
        private IOleServiceProvider serviceProvider;  
    }  
  
    ```  
  
6.  Dodaj Konstruktor klasę publiczną, która przyjmuje jeden parametr typu <xref:Microsoft.VisualStudio.Shell.Package>:  
  
    ```vb  
    Public Sub New(ByVal parentPackage As Package)  
        Me.parentPackage = parentPackage  
    End Sub  
    ```  
  
    ```csharp  
    public EditorFactory(Package parentPackage)  
    {  
        this.parentPackage = parentPackage;  
    }  
    ```  
  
7.  Modyfikowanie `EditorFactory` deklaracji pochodzić od klasy <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> interfejsu.  
  
    ```vb  
    Class EditorFactory Implements IVsEditorFacto  
    ```  
  
    ```csharp  
    class EditorFactory : IVsEditorFactory  
  
    ```  
  
8.  Kliknij prawym przyciskiem myszy <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory>, kliknij przycisk **implementuj interfejs**, a następnie kliknij przycisk **implementuj interfejs jawnie**.  
  
     Ten krok powoduje dodanie czterech metod, które muszą zostać zaimplementowane w <xref:Microsoft.VisualStudio.Shell.Interop.IVsEditorFactory> interfejsu.  
  
9. Zastąp zawartość `IVsEditorFactory.Close` metoda następującym kodem.  
  
    ```vb  
    Return VSConstants.S_OK  
    ```  
  
    ```csharp  
    return VSConstants.S_OK;  
    ```  
  
10. Zastąp zawartość `IVsEditorFactory.SetSite` następującym kodem.  
  
    ```vb  
    Me.serviceProvider = psp  
    Return VSConstants.S_OK  
    ```  
  
    ```csharp  
    this.serviceProvider = psp;  
    return VSConstants.S_OK;  
    ```  
  
11. Zastąp zawartość `IVsEditorFactory.MapLogicalView` metoda następującym kodem.  
  
    ```vb  
    Dim retval As Integer = VSConstants.E_NOTIMPL  
    pbstrPhysicalView = Nothing ' We support only one view.  
    If rguidLogicalView.Equals(VSConstants.LOGVIEWID_Designer)OrElse _  
    rguidLogicalView.Equals(VSConstants.LOGVIEWID_Primary) Then  
        retval = VSConstants.S_OK  
    End If  
    Return retval  
    ```  
  
    ```csharp  
    int retval = VSConstants.E_NOTIMPL;  
    pbstrPhysicalView = null;   // We support only one view.  
    if (rguidLogicalView.Equals(VSConstants.LOGVIEWID_Designer) ||  
    rguidLogicalView.Equals(VSConstants.LOGVIEWID_Primary))  
    {  
        retval = VSConstants.S_OK;  
    }  
    return retval;  
    ```  
  
12. Zastąp zawartość `IVsEditorFactory.CreateEditorInstance` metoda następującym kodem.  
  
    ```vb  
    Dim retval As Integer = VSConstants.E_FAIL          
  
    ' Initialize these to empty to start with   
    ppunkDocView = IntPtr.Zero  
    ppunkDocData = IntPtr.Zero  
    pbstrEditorCaption = ""  
    pguidCmdUI = Guid.Empty  
    pgrfCDW = 0  
  
    If (grfCreateDoc And (VSConstants.CEF_OPENFILE Or _  
    VSConstants.CEF_SILENT)) = 0 Then  
        Throw New ArgumentException("Only Open or Silent is valid")  
    End If  
    If punkDocDataExisting <> IntPtr.Zero Then  
        Return VSConstants.VS_E_INCOMPATIBLEDOCDATA  
    End If  
  
    ' Instantiate a text buffer of type VsTextBuffer.   
    ' Note: we only need an IUnknown (object) interface for   
    ' this invocation.   
    Dim clsidTextBuffer As Guid = GetType(VsTextBufferClass).GUID  
    Dim iidTextBuffer As Guid = VSConstants.IID_IUnknown  
    Dim pTextBuffer As Object = pTextBuffer = _  
    parentPackage.CreateInstance(clsidTextBuffer, iidTextBuffer, _  
    GetType(Object))  
  
    If Not pTextBuffer Is Nothing Then  
        ' "Site" the text buffer with the service provider we were   
        ' provided.   
        Dim textBufferSite As IObjectWithSite = TryCast(pTextBuffer, _  
        IObjectWithSite)  
        If Not textBufferSite Is Nothing Then  
            textBufferSite.SetSite(Me.serviceProvider)  
        End If  
  
        ' Instantiate a code window of type IVsCodeWindow.   
        Dim clsidCodeWindow As Guid = GetType(VsCodeWindowClass).GUID  
        Dim iidCodeWindow As Guid = GetType(IVsCodeWindow).GUID  
        Dim pCodeWindow As IVsCodeWindow = _  
        CType(Me.parentPackage.CreateInstance(clsidCodeWindow, _  
        iidCodeWindow, GetType(IVsCodeWindow)), IVsCodeWindow)  
        If Not pCodeWindow Is Nothing Then  
            ' Give the text buffer to the code window.   
            ' We are giving up ownership of the text buffer!   
            pCodeWindow.SetBuffer(CType(pTextBuffer, IVsTextLines))  
  
            ' Now tell the caller about all this new stuff   
            ' that has been created.   
            ppunkDocView = Marshal.GetIUnknownForObject(pCodeWindow)  
            ppunkDocData = Marshal.GetIUnknownForObject(pTextBuffer)  
  
            ' Specify the command UI to use so keypresses are   
            ' automatically dealt with.   
            pguidCmdUI = VSConstants.GUID_TextEditorFactory  
  
            ' This caption is appended to the filename and   
            ' lets us know our invocation of the core editor   
            ' is up and running.   
            pbstrEditorCaption = " [MyPackage]"  
  
            retval = VSConstants.S_OK  
        End If  
    End If  
    Return retval  
    ```  
  
    ```csharp  
    int retval = VSConstants.E_FAIL;  
  
    // Initialize these to empty to start with  
    ppunkDocView       = IntPtr.Zero;  
    ppunkDocData       = IntPtr.Zero;  
    pbstrEditorCaption = "";  
    pguidCmdUI         = Guid.Empty;   
    pgrfCDW            = 0;  
  
    if ((grfCreateDoc & (VSConstants.CEF_OPENFILE |   
          VSConstants.CEF_SILENT)) == 0)  
    {   
        throw new ArgumentException("Only Open or Silent is valid");  
    }  
    if (punkDocDataExisting != IntPtr.Zero)  
    {  
        return VSConstants.VS_E_INCOMPATIBLEDOCDATA;  
    }  
  
    // Instantiate a text buffer of type VsTextBuffer.  
    // Note: we only need an IUnknown (object) interface for   
    // this invocation.  
    Guid clsidTextBuffer = typeof(VsTextBufferClass).GUID;  
    Guid iidTextBuffer   = VSConstants.IID_IUnknown;  
    object pTextBuffer   = pTextBuffer = parentPackage.CreateInstance(  
          ref clsidTextBuffer,  
          ref iidTextBuffer,  
          typeof(object));  
  
    if (pTextBuffer != null)  
    {  
        // "Site" the text buffer with the service provider we were  
        // provided.  
        IObjectWithSite textBufferSite = pTextBuffer as IObjectWithSite;  
        if (textBufferSite != null)  
        {  
            textBufferSite.SetSite(this.serviceProvider);  
        }  
  
        // Instantiate a code window of type IVsCodeWindow.  
        Guid clsidCodeWindow = typeof(VsCodeWindowClass).GUID;  
        Guid iidCodeWindow   = typeof(IVsCodeWindow).GUID;  
        IVsCodeWindow pCodeWindow =  
        (IVsCodeWindow)this.parentPackage.CreateInstance(   
              ref clsidCodeWindow,  
              ref iidCodeWindow,  
              typeof(IVsCodeWindow));  
        if (pCodeWindow != null)  
        {  
            // Give the text buffer to the code window.  
            // We are giving up ownership of the text buffer!  
            pCodeWindow.SetBuffer((IVsTextLines)pTextBuffer);  
  
            // Now tell the caller about all this new stuff   
            // that has been created.  
            ppunkDocView = Marshal.GetIUnknownForObject(pCodeWindow);  
            ppunkDocData = Marshal.GetIUnknownForObject(pTextBuffer);  
  
            // Specify the command UI to use so keypresses are   
            // automatically dealt with.  
            pguidCmdUI = VSConstants.GUID_TextEditorFactory;  
  
            // This caption is appended to the filename and  
            // lets us know our invocation of the core editor   
            // is up and running.  
            pbstrEditorCaption = " [MyPackage]";  
  
            retval = VSConstants.S_OK;  
        }   
    }   
    return retval;   
    ```  
  
13. Skompiluj projekt i upewnij się, że nie ma żadnych błędów.  
  
### <a name="to-register-the-editor-factory"></a>Aby zarejestrować fabryki edytora  
  
1.  W **Eksploratora rozwiązań**, kliknij dwukrotnie **Resources.resx** plik, aby otworzyć go do tabeli ciągów, w którym wpis **ciąg1 jest** wybrane.  
  
2.  Zmień nazwę identyfikator ma `IDS_EDITORNAME` i tekst, który ma **MyPackage edytora.** Ten ciąg jest wyświetlany jako nazwa edytora.  
  
3.  Otwórz **VSPackage.resx** pliku, Dodaj nowy ciąg, ustaw nazwę na **101**, a następnie ustaw wartość `IDS_EDITORNAME`. Ten krok obejmuje pakiet o identyfikatorze zasobu, do uzyskania dostępu ciąg, który został utworzony.  
  
    > [!NOTE]
    >  Jeśli **VSPackage.resx** plik zawiera inny ciąg, który `name` ustawioną wartość atrybutu **101**, zastąpić inną wartość liczbową, unikatową, w tym miejscu i w poniższych krokach.  
  
4.  W **Eksploratora rozwiązań**, otwórz **MyPackagePackage.cs** pliku.  
  
     Ten plik jest plikiem pakietu głównego.  
  
5.  Dodaj następujące atrybuty użytkownika tuż przed `Guid` atrybutu.  
  
    ```vb  
    <ProvideEditorFactoryAttribute(GetType(EditorFactory), 101)> _  
    <ProvideEditorExtensionAttribute(GetType(EditorFactory), _  
          ".myext", 32, NameResourceID:=101 )> _  
    ```  
  
    ```csharp  
    [ProvideEditorFactory(typeof(EditorFactory), 101)]  
    [ProvideEditorExtension(typeof(EditorFactory),   
          ".myext", 32, NameResourceID = 101)]   
    ```  
  
     <xref:Microsoft.VisualStudio.Shell.ProvideEditorExtensionAttribute> Atrybutu kojarzy *.myext* pliku rozszerzenie z fabryką edytora, aby w dowolnym momencie pliku, który ma, że rozszerzenie jest ładowany, fabryką edytora jest wywoływana.  
  
6.  Dodaj zmienną prywatną do `MyPackage` klasy tuż przed konstruktora i przypisz do niego typ `EditorFactory`.  
  
    ```vb  
    Private editorFactory As EditorFactory  
    ```  
  
    ```csharp  
    private EditorFactory editorFactory;  
    ```  
  
7.  Znajdź `Initialize` — metoda (może być konieczne otwarcie `Package Members` ukryty region) i Dodaj następujący kod po wywołaniu `base.Initialize()`.  
  
    ```vb  
    'Create our editor factory and register it.   
    Me.editorFactory = New EditorFactory(Me)  
    MyBase.RegisterEditorFactory(Me.editorFactory)  
    ```  
  
    ```csharp  
    // Create our editor factory and register it.  
    this.editorFactory = new EditorFactory(this);  
    base.RegisterEditorFactory(this.editorFactory);  
  
    ```  
  
8.  Skompiluj program i upewnij się, że nie ma żadnych błędów.  
  
     W tym kroku rejestruje fabryka edytora w gałęzi rejestru eksperymentalne dla [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]. Jeśli zostanie wyświetlony monit o zastąpienie *resource.h* plików, kliknij **OK**.  
  
9. Utwórz przykładowy plik o nazwie *TextFile1.myext*.  
  
10. Naciśnij klawisz **F5** do Otwórz wystąpienie eksperymentalne [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
11. W eksperymentalnym [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]na **pliku** menu wskaż **Otwórz** a następnie kliknij przycisk **pliku**.  
  
12. Znajdź **TextFile1.myext** a następnie kliknij przycisk **Otwórz**.  
  
     Teraz należy załadować plik.  
  
## <a name="robust-programming"></a>Skuteczne programowanie  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Podstawowy edytor obsługuje szeroki zakres typów plików tekstowych i działa ściśle zintegrowana z usługami języka, które zapewniają bogaty zestaw funkcji, takich jak wyróżnianie składni, parowanie nawiasów klamrowych i uzupełnianie wyrazów w technologii IntelliSense i wyświetla uzupełnianie składowych. Jeśli pracujesz z plików tekstowych, można użyć edytora podstawowych wraz z usługą języka niestandardowego, który obsługuje usługi plików określonego typu.  
  
 Można wywołać pakietu VSPackage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] edytorze podstawowych funkcji poprzez dostarczenie fabryki edytora. Ta fabryka edytora jest używana zawsze, gdy jest ładowany w pliku, który jest skojarzony z nim. Jeśli plik jest częścią projektu, podstawowy edytor jest wywoływana automatycznie, chyba że zostaną zastąpione Twojego pakietu VSPackage. Jednak jeśli plik jest ładowany poza projektem, podstawowy edytor musi być jawnie wywoływany przez Twojego pakietu VSPackage.  
  
 Aby uzyskać więcej informacji na temat podstawowy edytor zobacz [wewnątrz podstawowy edytor](../extensibility/inside-the-core-editor.md).  
  
## <a name="see-also"></a>Zobacz także  
 [W edytorze podstawowych](../extensibility/inside-the-core-editor.md)   
 [Utwórz wystąpienie podstawowy edytor przy użyciu starszej wersji interfejsu API](../extensibility/instantiating-the-core-editor-by-using-the-legacy-api.md)