---
title: IDiaSession::findInjectedSource | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findInjectedSource method
ms.assetid: 907531b6-1ef8-4153-986d-b72611a1632d
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6f9870d1e2d14a2dcbe9f33191e0559a3e0b34f4
ms.sourcegitcommit: 3d10b93eb5b326639f3e5c19b9e6a8d1ba078de1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 04/18/2018
ms.locfileid: "31466992"
---
# <a name="idiasessionfindinjectedsource"></a>IDiaSession::findInjectedSource
Pobiera listę źródeł, który został umieszczony w magazynie symboli przez dostawców atrybut lub innych części procesu kompilacji.  
  
## <a name="syntax"></a>Składnia  
  
```C++  
HRESULT findInjectedSource (   
   LPCOLESTR                 srcFile,  
   IDiaEnumInjectedSources** ppResult  
);  
```  
  
#### <a name="parameters"></a>Parametry  
 srcFile  
 [in] Nazwa pliku źródłowego do wyszukania.  
  
 ppResult  
 [out] Zwraca [idiaenuminjectedsources —](../../debugger/debug-interface-access/idiaenuminjectedsources.md) obiekt, który zawiera listę wszystkich źródeł wprowadzony.  
  
## <a name="return-value"></a>Wartość zwracana  
 Jeśli to się powiedzie, zwraca `S_OK`; w przeciwnym razie zwraca kod błędu.  
  
## <a name="see-also"></a>Zobacz też  
 [Idiaenuminjectedsources —](../../debugger/debug-interface-access/idiaenuminjectedsources.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)