---
title: Kluczowe interfejsy ewaluatora wyrażeń | Dokumentacja firmy Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- debugging [Debugging SDK], expression evaluation
- expression evaluation, interfaces
ms.assetid: 1cac9aa3-0867-4e12-a16e-1e90abbc0fb6
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ba5affe8bd6b3e787f76863b29233b90a4ec0b72
ms.sourcegitcommit: 25a62c2db771f938e3baa658df8b1ae54a960e4f
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 07/24/2018
ms.locfileid: "39230825"
---
# <a name="key-expression-evaluator-interfaces"></a>Interfejsy ewaluatora wyrażeń klucza
> [!IMPORTANT]
>  W programie Visual Studio 2015 ten sposób implementowania ewaluatory wyrażeń jest przestarzały. Informacje o implementowaniu ewaluatory wyrażeń CLR, zobacz [ewaluatory wyrażeń CLR](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/CLR-Expression-Evaluators) i [przykładowe ewaluatora wyrażeń zarządzane](https://github.com/Microsoft/ConcordExtensibilitySamples/wiki/Managed-Expression-Evaluator-Sample).  
  
 Podczas pisania ewaluatora wyrażeń (EE) wraz z kontekstu oceny, należy zapoznać się z następujących interfejsów.  
  
## <a name="interface-descriptions"></a>Opis interfejsu  
  
-   [IDebugAddress](../../extensibility/debugger/reference/idebugaddress.md)  
  
     Zawiera jedną metodę [getaddress —](../../extensibility/debugger/reference/idebugaddress-getaddress.md), która pobiera strukturę danych, reprezentuje bieżący punkt wykonania. Ta struktura danych jest jednym z trzech argumentów, aparat debugowania (DE) przekazane przez [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) metody, można obliczyć wartości wyrażenia. Ten interfejs jest zwykle implementowany przez dostawcę symboli.  
  
-   [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md)  
  
     Ma [powiązać](../../extensibility/debugger/reference/idebugbinder-bind.md) metody, która pobiera obszaru pamięci, która zawiera bieżącą wartość symbolu. Biorąc pod uwagę zarówno metodą zawierającą, reprezentowane przez [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) obiekt i symboli, reprezentowane przez [IDebugField](../../extensibility/debugger/reference/idebugfield.md) obiektu `IDebugBinder::Bind` zwraca wartość symbolu. `IDebugBinder` Zazwyczaj jest implementowany przez DE.  
  
-   [IDebugField](../../extensibility/debugger/reference/idebugfield.md)  
  
     Reprezentuje prosty typ danych. W przypadku bardziej złożonych typów, takich jak tablice i metody, użyj pochodnej [IDebugArrayField](../../extensibility/debugger/reference/idebugarrayfield.md) i [IDebugMethodField](../../extensibility/debugger/reference/idebugmethodfield.md) interfejsy odpowiednio. [IDebugContainerField](../../extensibility/debugger/reference/idebugcontainerfield.md) jest inny ważne pochodnej interfejs, który reprezentuje symbole zawierające innych symboli, takich jak metod lub klas. `IDebugField` Interfejsu (i ich pochodne) jest zwykle implementowana przez dostawcę symboli.  
  
     `IDebugField` Obiekt może być używane, aby znaleźć nazwę i typ symbolu i wraz z [IDebugBinder](../../extensibility/debugger/reference/idebugbinder.md) obiektów, można znaleźć jego wartość.  
  
-   [IDebugObject](../../extensibility/debugger/reference/idebugobject.md)  
  
     Reprezentuje rzeczywisty bity wartość symbolu w czasie wykonywania. [Powiąż](../../extensibility/debugger/reference/idebugbinder-bind.md) przyjmuje [IDebugField](../../extensibility/debugger/reference/idebugfield.md) obiektu, który reprezentuje symbol, a następnie zwraca [IDebugObject](../../extensibility/debugger/reference/idebugobject.md) obiektu. [GetValue](../../extensibility/debugger/reference/idebugobject-getvalue.md) metoda zwraca wartość symbolu w buforze pamięci. DE zwykle implementuje ten interfejs reprezentujący wartość właściwości w pamięci.  
  
-   [IDebugExpressionEvaluator](../../extensibility/debugger/reference/idebugexpressionevaluator.md)  
  
     Ten interfejs reprezentuje ewaluatora wyrażenia, sam. Metoda klucza jest [przeanalizować](../../extensibility/debugger/reference/idebugexpressionevaluator-parse.md), co powoduje zwrócenie [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md) interfejsu.  
  
-   [IDebugParsedExpression](../../extensibility/debugger/reference/idebugparsedexpression.md)  
  
     Ten interfejs reprezentuje wyrażenie przeanalizowany, gotowy do obliczenia. Metoda klucza jest [EvaluateSync](../../extensibility/debugger/reference/idebugparsedexpression-evaluatesync.md) co powoduje zwrócenie wiadomość IDebugProperty2 reprezentujący wartość i typ wyrażenia.  
  
-   [IDebugProperty2](../../extensibility/debugger/reference/idebugproperty2.md)  
  
     Ten interfejs reprezentuje wartość, jak i jej typ i jest wynikiem oceny wyrażenia.  
  
## <a name="see-also"></a>Zobacz także  
 [Kontekst oceny](../../extensibility/debugger/evaluation-context.md)