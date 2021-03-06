---
title: Metodo IMetaDataAssemblyImport::GetManifestResourceProps
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetManifestResourceProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetManifestResourceProps
helpviewer_keywords:
- GetManifestResourceProps method [.NET Framework metadata]
- IMetaDataAssemblyImport::GetManifestResourceProps method [.NET Framework metadata]
ms.assetid: 00be4789-ac63-4397-b2ec-1629a5c5a585
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 07237794ca45b16b1ae1ca95b1d62889f095350f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataassemblyimportgetmanifestresourceprops-method"></a>Metodo IMetaDataAssemblyImport::GetManifestResourceProps
Ottiene il set di proprietà della risorsa del manifesto con la firma dei metadati specificato.  
  
## <a name="syntax"></a>Sintassi  
  
```  
HRESULT GetManifestResourceProps (  
    [in]  mdManifestResource   mdmr,   
    [out] LPWSTR               szName,   
    [in]  ULONG                cchName,   
    [out] ULONG                *pchName,   
    [out] mdToken              *ptkImplementation,   
    [out] DWORD                *pdwOffset,   
    [out] DWORD                *pdwResourceFlags  
);  
```  
  
#### <a name="parameters"></a>Parametri  
 `mdmr`  
 [in] Un `mdManifestResource` token che rappresenta la risorsa per cui ottenere le proprietà.  
  
 `szName`  
 [out] Il nome della risorsa.  
  
 `cchName`  
 [in] La dimensione in caratteri wide, di `szName`.  
  
 `pchName`  
 [out] Un puntatore al numero di caratteri "wide" effettivamente restituiti nella `szName`.  
  
 `ptkImplementation`  
 [out] Un puntatore a un `mdFile` token o un `mdAssemblyRef` token che rappresenta i file di assembly, rispettivamente, che contiene la risorsa.  
  
 `pdwOffset`  
 [out] Un puntatore a un valore che specifica l'offset all'inizio della risorsa all'interno del file.  
  
 `pdwResourceFlags`  
 [out] Puntatore a flag che descrivono i metadati applicati a una risorsa. Il valore del flag è una combinazione di uno o più [CorManifestResourceFlags](../../../../docs/framework/unmanaged-api/metadata/cormanifestresourceflags-enumeration.md) valori.  
  
## <a name="requirements"></a>Requisiti  
 **Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Intestazione:** Cor. h  
  
 **Libreria:** usata come risorsa in Mscoree. dll  
  
 **Versioni di .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vedere anche  
 [Interfaccia IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
