---
title: ICLRTask2::EndPreventAsyncAbort-Methode
ms.date: 03/30/2017
api_name:
- ICLRTask2.EndPreventAsyncAbort
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRTask2::EndPreventAsyncAbort
helpviewer_keywords:
- EndPreventAsyncAbort method [.NET Framework hosting]
- ICLRTask2::EndPreventAsyncAbort method [.NET Framework hosting]
ms.assetid: d8013659-e3df-44b3-814f-a6b534ce62f8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8cacc96d66d5d4eb46c08c93d9c2793282627539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33438232"
---
# <a name="iclrtask2endpreventasyncabort-method"></a>ICLRTask2::EndPreventAsyncAbort-Methode
Ermöglicht, dass neue oder ausstehende Thread Abort Anforderungen zu Thread führt bricht ab, für den aktuellen Thread.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EndPreventAsyncAbort();  
```  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|HOST_E_INVALIDOPERATION|Die Methode wurde in einem Thread aufgerufen, die nicht der aktuelle Thread ist.|  
  
## <a name="remarks"></a>Hinweise  
 Aufrufen dieser Methode dekrementiert die Verzögerung Threadabbruchs Leistungsindikator für den aktuellen Thread um eins.  
  
 Aufrufe von [ICLRTask2:: BeginPreventAsyncAbort](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md) und `EndPreventAsyncAbort` können geschachtelt sein. Solange der Leistungsindikator größer als 0 (null) ist, werden Threadabbrüche für den aktuellen Thread verzögert.  
  
 Die Funktionalität, die von dieser Funktion verfügbar gemacht wird, wird intern von der virtuellen Maschine (VM) verwendet. Missbrauch dieser Methoden möglicherweise nicht definiertes Verhalten auf dem virtuellen Computer. Beispielsweise Aufrufen `EndPreventAsyncAbort` erst nach Aufrufen von `BeginPreventAsyncAbort` konnte den Zähler auf 0 festgelegt, wenn der virtuellen Computer zuvor erhöht wurde. Auf ähnliche Weise wird der interne Zähler auf Überläufe nicht überprüft. Wenn er ganzzahlige Limit überschreitet, da er vom Host und dem virtuellen Computer erhöht wird, ist das resultierende Verhalten nicht angegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [BeginPreventAsyncAbort-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-beginpreventasyncabort-method.md)  
 [ICLRTask2-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtask2-interface.md)  
 [ICLRTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md)  
 [IHostTask-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttask-interface.md)  
 [IHostTaskManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihosttaskmanager-interface.md)  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
