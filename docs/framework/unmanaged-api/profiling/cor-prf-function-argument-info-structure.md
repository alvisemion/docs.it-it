---
title: Struttura COR_PRF_FUNCTION_ARGUMENT_INFO
ms.date: 03/30/2017
api_name:
- COR_PRF_FUNCTION_ARGUMENT_INFO
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO
helpviewer_keywords:
- COR_PRF_FUNCTION_ARGUMENT_INFO structure [.NET Framework profiling]
ms.assetid: 07cf3bab-e193-4991-8205-3f41cf2d67b3
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 1fbc41ca1366b412c37d6af09e90e3f1b042ba21
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="corprffunctionargumentinfo-structure"></a>Struttura COR_PRF_FUNCTION_ARGUMENT_INFO
Rappresenta gli argomenti di una funzione, in ordine da sinistra a destra.  
  
## <a name="syntax"></a>Sintassi  
  
```  
typedef struct _COR_PRF_FUNCTION_ARGUMENT_INFO {  
    ULONG numRanges;  
    ULONG totalArgumentSize;  
    COR_PRF_FUNCTION_ARGUMENT_RANGE ranges[1];  
} COR_PRF_FUNCTION_ARGUMENT_INFO;  
```  
  
## <a name="members"></a>Membri  
  
|Membro|Descrizione|  
|------------|-----------------|  
|`numRanges`|Il numero di blocchi di argomenti. Questo valore è il numero di [COR_PRF_FUNCTION_ARGUMENT_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-function-argument-range-structure.md) strutture nel `ranges` matrice.|  
|`totalArgumentSize`|Le dimensioni totali di tutti gli argomenti. In altre parole, questo valore è la somma delle lunghezze degli argomenti.|  
|`ranges`|Matrice di `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuno dei quali rappresenta un blocco di argomenti della funzione.|  
  
## <a name="remarks"></a>Note  
 Una funzione può avere un numero di argomenti. Gli argomenti potrebbero non essere archiviati in modo contiguo nella memoria. Potrebbe essere un blocco di tre argomenti in un'unica posizione, un blocco di due argomenti in un'altra posizione e un blocco finale di un argomento in una posizione diversa. Questi argomenti sono tutti della stessa funzione; sono archiviati solo in posizioni diverse.  
  
 Il `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura rappresenta tutti gli argomenti di una singola funzione. Usa una matrice per fare riferimento a tutti i blocchi di argomenti della funzione. In tal caso, per una singola funzione, è una singola `COR_PRF_FUNCTION_ARGUMENT_INFO` struttura, a cui fa riferimento a più `COR_PRF_FUNCTION_ARGUMENT_RANGE` strutture, ognuno dei quali punta a uno o più argomenti di funzione.  
  
 Gli argomenti che vengono archiviati nei registri vengono passati in memoria per compilare le strutture.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Corprof. idl  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Strutture di profilatura](../../../../docs/framework/unmanaged-api/profiling/profiling-structures.md)
