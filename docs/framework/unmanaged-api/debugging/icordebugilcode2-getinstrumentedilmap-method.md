---
title: Metodo ICorDebugILCode2::GetInstrumentedILMap
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugILCode2.GetInstrumentedILMap
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 7a4e3085-8f95-40ef-a4be-7d6146f47ce2
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6a712ed9e3534ca6bb2962989f1ab3750a25d539
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icordebugilcode2getinstrumentedilmap-method"></a>Metodo ICorDebugILCode2::GetInstrumentedILMap
[Supportato in .NET Framework 4.5.2 e versioni successive]  
  
 Restituisce una mappa dagli offset di linguaggio intermedio (IL) instrumentati dal profiler agli offset IL elaborati con il metodo originale per l'istanza corrente.  
  
## <a name="syntax"></a>Sintassi  
  
```cpp
HRESULT GetInstrumentedILMap(  
   [in] ULONG32 cMap,  
   [out] ULONG32 *pcMap,  
   [out, size_is(cMap), length_is(*pcMap)] COR_IL_MAP map[]  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 cMap  
 [in] Capacità di memoria della matrice `map`. Per altre informazioni, vedere la sezione Osservazioni.  
  
 pcMap  
 [out] Il numero di valori COR_IL_MAP scritti nella matrice map.  
  
 map  
 [out] Una matrice di valori COR_IL_MAP che forniscono informazioni sui mapping dal linguaggio intermedio instrumentato del profiler per il linguaggio intermedio del metodo originale.  
  
## <a name="remarks"></a>Note  
 Se il profiler imposta il mapping chiamando il [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md) metodo, il debugger può chiamare questo metodo per recuperare il mapping e utilizzare il mapping internamente durante IL calcolo degli offset per stack le tracce e durata delle variabili.  
  
 Se `cMap` è 0 e `pcMap` è non**null**, `pcMap` è impostato sul numero di valori COR_IL_MAP disponibili. Se `cMap` è diverso da zero, rappresenta la capacità di memoria della matrice `map`. Quando termina, il metodo `map` contiene un massimo di `cMap` elementi, e `pcMap` è impostato per il numero di valori COR_IL_MAP effettivamente scritti il `map` matrice.  
  
 Se il linguaggio intermedio (IL) non è instrumentato o il profiler non ha fornito un mapping, il metodo restituisce `S_OK` e imposta `pcMap` su 0.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cordebug. idl, Cordebug. H  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [ICorProfilerInfo:: SetILInstrumentedCodeMap](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-setilinstrumentedcodemap-method.md)  
 [Interfaccia ICorDebugILCode2](../../../../docs/framework/unmanaged-api/debugging/icordebugilcode2-interface.md)  
 [Interfacce di debug](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
