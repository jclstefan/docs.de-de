---
title: ICorDebugFunction::GetLocalVarSigToken-Methode
ms.date: 03/30/2017
api_name:
- ICorDebugFunction.GetLocalVarSigToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugFunction::GetLocalVarSigToken
helpviewer_keywords:
- ICorDebugFunction::GetLocalVarSigToken method [.NET Framework debugging]
- GetLocalVarSigToken method [.NET Framework debugging]
ms.assetid: 31e53494-bcc9-4981-91a4-f7e0f02cad48
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a09741ed778436f1cb35d094885bd3effa813a5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33411593"
---
# <a name="icordebugfunctiongetlocalvarsigtoken-method"></a>ICorDebugFunction::GetLocalVarSigToken-Methode
Ruft den Metadatentoken für die Signatur der lokalen Variablen der Funktion, die von dieser Instanz ICorDebugFunction dargestellt wird.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetLocalVarSigToken (  
    [out] mdSignature *pmdSig  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pmdSig`  
 [out] Ein Zeiger auf die `mdSignature` token für die lokale Variablensignatur dieser Funktion oder `mdSignatureNil`, wenn diese Funktion keine lokalen Variablen enthält.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]
