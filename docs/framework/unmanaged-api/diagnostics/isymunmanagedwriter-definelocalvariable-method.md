---
title: Metodo ISymUnmanagedWriter::DefineLocalVariable
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.DefineLocalVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::DefineLocalVariable
helpviewer_keywords:
- ISymUnmanagedWriter::DefineLocalVariable method [.NET Framework debugging]
- DefineLocalVariable method [.NET Framework debugging]
ms.assetid: 6fab8a58-3883-490f-8b27-64042c90f104
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d6f8b896d50bb659897291d7bf85e836482611a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="isymunmanagedwriterdefinelocalvariable-method"></a>Metodo ISymUnmanagedWriter::DefineLocalVariable
Definisce una singola variabile nell'ambito lessicale corrente. Questo metodo può essere chiamato più volte per una variabile con lo stesso nome presente in più posizioni in un ambito. In questo caso, tuttavia, i valori del `startOffset` e `endOffset` parametri non devono sovrapporsi.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT DefineLocalVariable(  
    [in] const WCHAR  *name,  
    [in] ULONG32      attributes,  
    [in] ULONG32      cSig,  
    [in, size_is(cSig)] unsigned char signature[],  
    [in] ULONG32      addrKind,  
    [in] ULONG32      addr1,  
    [in] ULONG32      addr2,  
    [in] ULONG32      addr3,  
    [in] ULONG32      startOffset,  
    [in] ULONG32      endOffset);  
```  
  
#### <a name="parameters"></a>Parametri  
 `name`  
 [in] Un puntatore a un `WCHAR` che definisce il nome della variabile locale.  
  
 `attributes`  
 [in] Attributi della variabile locale.  
  
 `cSig`  
 [in] Oggetto `ULONG32` che indica le dimensioni, in byte, del `signature` buffer.  
  
 `signature`  
 [in] La firma di variabile locale.  
  
 `addrKind`  
 [in] Il tipo di indirizzo.  
  
 `addr1`  
 [in] Il primo indirizzo per la specifica del parametro.  
  
 `addr2`  
 [in] Il secondo indirizzo per la specifica del parametro.  
  
 `addr3`  
 [in] Terzo indirizzo per la specifica del parametro.  
  
 `startOffset`  
 [in] Offset iniziale della variabile. Questo parametro è facoltativo. Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito. Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.  
  
 `endOffset`  
 [in] Offset finale della variabile. Questo parametro è facoltativo. Se il valore è 0, questo parametro viene ignorato e la variabile viene definita nell'intero ambito. Se è un valore diverso da zero, la variabile rientrerà negli offset dell'ambito corrente.  
  
## <a name="return-value"></a>Valore restituito  
 S_OK se il metodo ha esito positivo. in caso contrario, E_FAIL o un altro codice di errore.  
  
## <a name="requirements"></a>Requisiti  
 **Intestazione:** CorSym. idl, CorSym.h  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia ISymUnmanagedWriter](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)  
 [Metodo DefineGlobalVariable](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)  
 [Metodo DefineLocalVariable2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-definelocalvariable2-method.md)
