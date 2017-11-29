---
title: Metodo ICorRuntimeHost::CreateDomain
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorRuntimeHost.CreateDomain
api_location: mscoree.dll
api_type: COM
f1_keywords: ICorRuntimeHost::CreateDomain
helpviewer_keywords:
- CreateDomain method [.NET Framework hosting]
- ICorRuntimeHost::CreateDomain method [.NET Framework hosting]
ms.assetid: b96c5ef3-a9df-4c7c-9952-432d3272cb5c
topic_type: apiref
caps.latest.revision: "8"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 0da99f05b09d44338a5f4d695fb2a4114f0e1f30
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="icorruntimehostcreatedomain-method"></a><span data-ttu-id="8af5d-102">Metodo ICorRuntimeHost::CreateDomain</span><span class="sxs-lookup"><span data-stu-id="8af5d-102">ICorRuntimeHost::CreateDomain Method</span></span>
<span data-ttu-id="8af5d-103">Crea un dominio applicazione.</span><span class="sxs-lookup"><span data-stu-id="8af5d-103">Creates an application domain.</span></span> <span data-ttu-id="8af5d-104">Il chiamante riceve un puntatore a interfaccia di tipo <xref:System._AppDomain> a un'istanza di tipo <xref:System.AppDomain?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="8af5d-104">The caller receives an interface pointer of type <xref:System._AppDomain> to an instance of type <xref:System.AppDomain?displayProperty=nameWithType>.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8af5d-105">Sintassi</span><span class="sxs-lookup"><span data-stu-id="8af5d-105">Syntax</span></span>  
  
```  
HRESULT CreateDomain (  
    [in] LPWSTR    pwzFriendlyName,  
    [in] IUnknown* pIdentityArray,  
    [out] void   **pAppDomain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8af5d-106">Parametri</span><span class="sxs-lookup"><span data-stu-id="8af5d-106">Parameters</span></span>  
 `pwzFriendlyName`  
 <span data-ttu-id="8af5d-107">[in] Parametro facoltativo utilizzato per assegnare un nome descrittivo per il dominio.</span><span class="sxs-lookup"><span data-stu-id="8af5d-107">[in] An optional parameter used to give a friendly name to the domain.</span></span> <span data-ttu-id="8af5d-108">Questo nome descrittivo può essere visualizzato nelle interfacce utente, ad esempio i debugger per identificare il dominio.</span><span class="sxs-lookup"><span data-stu-id="8af5d-108">This friendly name can be displayed in user interfaces such as debuggers to identify the domain.</span></span>  
  
 `pIdentityArray`  
 <span data-ttu-id="8af5d-109">[in] Matrice facoltativa di puntatori a `IIdentity` istanze che rappresentano evidenze mappate tramite criteri di sicurezza per stabilire un set di autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="8af5d-109">[in] An optional array of pointers to `IIdentity` instances that represent evidence mapped through security policy to establish a  permission set.</span></span> <span data-ttu-id="8af5d-110">Un `IIdentity` oggetto può essere ottenuto chiamando il [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) metodo.</span><span class="sxs-lookup"><span data-stu-id="8af5d-110">An `IIdentity` object can be obtained by calling the [CreateEvidence](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-createevidence-method.md) method.</span></span>  
  
 `pAppDomain`  
 <span data-ttu-id="8af5d-111">[out] Un puntatore a interfaccia di tipo <xref:System._AppDomain> a un'istanza di <xref:System.AppDomain?displayProperty=nameWithType> che può essere utilizzato per controllare ulteriormente il dominio.</span><span class="sxs-lookup"><span data-stu-id="8af5d-111">[out] An interface pointer of type <xref:System._AppDomain> to an instance of <xref:System.AppDomain?displayProperty=nameWithType> that can be used to further control the domain.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8af5d-112">Valore restituito</span><span class="sxs-lookup"><span data-stu-id="8af5d-112">Return Value</span></span>  
  
|<span data-ttu-id="8af5d-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8af5d-113">HRESULT</span></span>|<span data-ttu-id="8af5d-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="8af5d-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8af5d-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="8af5d-115">S_OK</span></span>|<span data-ttu-id="8af5d-116">L'operazione è riuscita.</span><span class="sxs-lookup"><span data-stu-id="8af5d-116">The operation was successful.</span></span>|  
|<span data-ttu-id="8af5d-117">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="8af5d-117">S_FALSE</span></span>|<span data-ttu-id="8af5d-118">Impossibile completare l'operazione.</span><span class="sxs-lookup"><span data-stu-id="8af5d-118">The operation failed to complete.</span></span>|  
|<span data-ttu-id="8af5d-119">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="8af5d-119">E_FAIL</span></span>|<span data-ttu-id="8af5d-120">Si è verificato un errore irreversibile sconosciuto.</span><span class="sxs-lookup"><span data-stu-id="8af5d-120">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="8af5d-121">Se un metodo restituisce E_FAIL, common language runtime (CLR) non è più utilizzabile nel processo.</span><span class="sxs-lookup"><span data-stu-id="8af5d-121">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="8af5d-122">Le chiamate successive a qualsiasi API di hosting restituiranno HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="8af5d-122">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="8af5d-123">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="8af5d-123">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="8af5d-124">CLR non è stato caricato in un processo oppure si trova in uno stato in cui non può eseguire codice gestito o elaborare correttamente la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8af5d-124">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8af5d-125">Requisiti</span><span class="sxs-lookup"><span data-stu-id="8af5d-125">Requirements</span></span>  
 <span data-ttu-id="8af5d-126">**Piattaforme:** vedere [requisiti di sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8af5d-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8af5d-127">**Intestazione:** Mscoree. H</span><span class="sxs-lookup"><span data-stu-id="8af5d-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8af5d-128">**Libreria:** inclusa come risorsa in MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8af5d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8af5d-129">**Versioni di .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="8af5d-129">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8af5d-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8af5d-130">See Also</span></span>  
 <xref:System._AppDomain>  
 <xref:System.AppDomain>  
 [<span data-ttu-id="8af5d-131">ICorRuntimeHost (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="8af5d-131">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)