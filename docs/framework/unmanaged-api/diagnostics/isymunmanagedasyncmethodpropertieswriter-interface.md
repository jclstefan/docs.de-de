---
title: ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
ms.date: 03/30/2017
ms.assetid: caa71820-8058-4b6a-93a2-25ee757d92d3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7ec66e0064a8d6e8d4664dd8c727aa87621cfd8e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33427306"
---
# <a name="isymunmanagedasyncmethodpropertieswriter-interface"></a>ISymUnmanagedAsyncMethodPropertiesWriter-Schnittstelle
Können Sie Informationen zu optionalen Async-Methode für jedes Symbol Methode definieren. Verwenden Sie immer mit einer geöffneten Methode; d. h. zwischen den Aufrufen der [OpenMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md) und [CloseMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md).  
  
## <a name="syntax"></a>Syntax  
  
```idl  
[object,uuid(FC073774-1739-4232-BD56-A027294BEC15),pointer_default(unique)]interface ISymUnmanagedAsyncMethodPropertiesWriter : IUnknown  
```  
  
## <a name="methods"></a>Methoden  
 Diese Schnittstelle enthält die folgenden Methoden:  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[DefineAsyncStepInfo-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-defineasyncstepinfo-method.md)|Definieren Sie eine Gruppe von asynchronen Vorgängen in der aktuellen Methode erwarten.<br /><br /> Jede Yield-Offset entspricht eine "await" return-Anweisung, einen potenziellen Rendite identifizieren. Jede `breakpointMethod` / `breakpointOffset` Paar identifiziert, in dem der asynchrone Vorgang fortgesetzt wird, möglicherweise in einer anderen Methode.|  
|[DefineCatchHandlerILOffset-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definecatchhandleriloffset-method.md)|Legt fest, die IL-offset für den vom Compiler generierte Catch-Handler, der eine asynchrone Methode umschließt.<br /><br /> Der IL-Offset des generierten Catch wird vom Debugger verwendet, Catch behandelt, als handele es sich um nicht-benutzerseitigen Code, obwohl es in einer Code Benutzermethode auftreten kann. Insbesondere, dient er als Antwort auf eine **CatchHandlerFound** Ausnahmeereignisses.|  
|[DefineKickoffMethod-Methode](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedasyncmethodpropertieswriter-definekickoffmethod-method.md)|Legt die Start-Methode, die den asynchronen Vorgang initiiert.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Siehe auch  
 [Diagnosesymbolspeicher-Schnittstellen](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
