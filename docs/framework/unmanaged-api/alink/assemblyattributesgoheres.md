---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereS
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d68450d05f667851404a009c0984f8722253e71e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="assemblyattributesgoheres"></a>AssemblyAttributesGoHereS
Usato da ALink come segnaposto per archiviare le informazioni sugli attributi personalizzati.  
  
## <a name="syntax"></a>Sintassi  
  
```  
AssemblyAttributesGoHereS  
```  
  
## <a name="remarks"></a>Note  
 I riferimenti a questo tipo potrebbero essere incorporati in netmodule le cui origini contengono attributi personalizzati dell'assembly. Quando compila un manifesto di assembly da uno o più netmodule contenenti riferimenti a questi tipi, ALink usa le informazioni associate a tali riferimenti per generare i veri attributi personalizzati. Per questo tipo non viene pertanto mai creata un'istanza e i riferimenti a esso relativi vengono usati solo come parte del processo di compilazione e non hanno alcun ruolo nell'assembly finale.  
  
 I riferimenti a questo tipo indicano gli attributi personalizzati che sono correlati alla sicurezza e non sono multiuso.  
  
 Tali tipi sono contrassegnati come "interni" in .NET Framework e sono disponibili in <xref:System.Runtime.CompilerServices>.  
  
## <a name="requirements"></a>Requisiti  
 mscorlib.dll  
  
## <a name="see-also"></a>Vedere anche  
 [AssemblyAttributesGoHere](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)  
 [AssemblyAttributesGoHereM](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [AssemblyAttributesGoHereSM](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
