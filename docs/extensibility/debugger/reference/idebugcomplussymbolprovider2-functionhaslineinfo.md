---
title: IDebugComPlusSymbolProvider2::FunctionHasLineInfo | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- FunctionHasLineInfo
- IDebugComPlusSymbolProvider2::FunctionHasLineInfo
ms.assetid: e1b508f1-6521-492f-b110-ab957744a037
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: e8175946e7d4c01a2013e31ff39ba7d1ea4161f6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/16/2018
ms.locfileid: "31104842"
---
# <a name="idebugcomplussymbolprovider2functionhaslineinfo"></a>IDebugComPlusSymbolProvider2::FunctionHasLineInfo
Określa, czy określona metoda ma informacje dotyczące wiersza.  
  
## <a name="syntax"></a>Składnia  
  
```cpp  
HRESULT FunctionHasLineInfo(  
   IDebugAddress* pAddress  
);  
```  
  
```csharp  
int FunctionHasLineInfo(  
   IDebugAddress pAddress  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 `pAddress`  
 [in] Adres debugowania, który jest reprezentowana przez [IDebugAddress](../../../extensibility/debugger/reference/idebugaddress.md) interfejsu. Ten adres musi być METHOD_ADDRESS.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca `S_FALSE`.  
  
## <a name="example"></a>Przykład  
 Poniższy przykład przedstawia sposób zaimplementować tę metodę do **CDebugSymbolProvider** obiekt ujawniający [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md) interfejsu.  
  
```cpp  
HRESULT CDebugSymbolProvider::FunctionHasLineInfo(  
    IDebugAddress* pAddress  
)  
{  
    HRESULT hr = S_OK;  
    CDEBUG_ADDRESS address;  
    CComPtr<CModule> pModule;  
  
    METHOD_ENTRY( CDebugSymbolProvider::LoadSymbol );  
  
    IfFalseGo( pAddress, E_INVALIDARG );  
  
    IfFailGo( pAddress->GetAddress( &address ) );  
  
    ASSERT(address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD);  
    IfFalseGo( address.addr.dwKind == ADDRESS_KIND_METADATA_METHOD, S_FALSE );  
  
    IfFailGo( GetModule( address.GetModule(), &pModule) );  
  
    if (!pModule->FunctionHasLineInfo( address.addr.addr.addrMethod.tokMethod,  
                                       address.addr.addr.addrMethod.dwVersion))  
    {  
  
        // S_FALSE indicates this method does not have line info  
  
        hr = S_FALSE;  
    }  
  
Error:  
  
    METHOD_EXIT( CDebugSymbolProvider::LoadSymbol, hr );  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>Zobacz też  
 [IDebugComPlusSymbolProvider2](../../../extensibility/debugger/reference/idebugcomplussymbolprovider2.md)