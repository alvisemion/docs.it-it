---
title: Metodo ICorProfilerCallback::UnmanagedToManagedTransition
ms.date: 03/30/2017
api_name:
- ICorProfilerCallback.UnmanagedToManagedTransition
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition
helpviewer_keywords:
- ICorProfilerCallback::UnmanagedToManagedTransition method [.NET Framework profiling]
- UnmanagedToManagedTransition method [.NET Framework profiling]
ms.assetid: ade2cc01-9b81-4e09-a5f9-b3b9dda27e96
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: c6bd0c9796fa2c5d8eff8dfb9d3fa3f707ce4761
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="icorprofilercallbackunmanagedtomanagedtransition-method"></a>Metodo ICorProfilerCallback::UnmanagedToManagedTransition
Notifica al profiler che si è verificata una transizione da codice non gestito a codice gestito.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT UnmanagedToManagedTransition(  
    [in] FunctionID functionId,  
    [in] COR_PRF_TRANSITION_REASON reason);  
```  
  
#### <a name="parameters"></a>Parametri  
 `functionId`  
 [in] L'ID della funzione chiamata.  
  
 `reason`  
 [in] Il valore di [COR_PRF_TRANSITION_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-transition-reason-enumeration.md) enumerazione che indica se la transizione si è verificato a causa di una chiamata nel codice gestito da codice non gestito o a causa di un ritorno da una funzione non gestita chiamata da una gestito.  
  
## <a name="remarks"></a>Note  
 Se il valore di `reason` è COR_PRF_TRANSITION_RETURN e `functionId` non è null, la funzione ID è quello di funzione non gestita e non sarà mai stato compilato utilizzando il compilatore just-in-time (JIT). Le funzioni non gestite hanno alcune informazioni di base associate, ad esempio un nome e alcuni metadati.  
  
 Se il valore di `reason` è COR_PRF_TRANSITION_CALL, è possibile che la funzione chiamata (ovvero, la funzione gestita) non è ancora stato compilato tramite JIT.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** CorProf.idl, CorProf.h  
  
 **Libreria:** CorGuids. lib  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ICorProfilerCallback](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [Metodo ManagedToUnmanagedTransition](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-managedtounmanagedtransition-method.md)  
 [Uso esplicito di PInvoke in C++ (attributo DllImport)](/cpp/dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute)  
 [Uso delle funzionalità di interoperabilità C++ (PInvoke implicito)](/cpp/dotnet/using-cpp-interop-implicit-pinvoke)
