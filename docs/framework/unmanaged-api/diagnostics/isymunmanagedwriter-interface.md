---
title: Interfaccia ISymUnmanagedWriter
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter
helpviewer_keywords: ISymUnmanagedWriter interface [.NET Framework debugging]
ms.assetid: 7d6733ec-f081-4166-bc17-de09e16dc304
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e74e625c911f35bdb7c20451b1babd02cdb7658
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="isymunmanagedwriter-interface"></a><span data-ttu-id="f80e5-102">Interfaccia ISymUnmanagedWriter</span><span class="sxs-lookup"><span data-stu-id="f80e5-102">ISymUnmanagedWriter Interface</span></span>
<span data-ttu-id="f80e5-103">Rappresenta un writer di simboli e fornisce metodi per definire punti di sequenza, gli ambiti lessicali, variabili e documenti.</span><span class="sxs-lookup"><span data-stu-id="f80e5-103">Represents a symbol writer, and provides methods to define documents, sequence points, lexical scopes, and variables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f80e5-104">Metodi</span><span class="sxs-lookup"><span data-stu-id="f80e5-104">Methods</span></span>  
  
|<span data-ttu-id="f80e5-105">Metodo</span><span class="sxs-lookup"><span data-stu-id="f80e5-105">Method</span></span>|<span data-ttu-id="f80e5-106">Descrizione</span><span class="sxs-lookup"><span data-stu-id="f80e5-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f80e5-107">Abort (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-107">Abort Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-abort-method.md)|<span data-ttu-id="f80e5-108">Chiude il writer di simboli senza eseguire il commit i simboli per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="f80e5-108">Closes the symbol writer without committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="f80e5-109">Close (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-109">Close Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-close-method.md)|<span data-ttu-id="f80e5-110">Chiude il writer di simboli dopo il commit i simboli per l'archivio dei simboli.</span><span class="sxs-lookup"><span data-stu-id="f80e5-110">Closes the symbol writer after committing the symbols to the symbol store.</span></span>|  
|[<span data-ttu-id="f80e5-111">CloseMethod (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-111">CloseMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closemethod-method.md)|<span data-ttu-id="f80e5-112">Chiude il metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="f80e5-112">Closes the current method.</span></span> <span data-ttu-id="f80e5-113">Dopo un metodo è stato chiuso, non vi sono ulteriori simboli possono essere definiti all'interno di esso.</span><span class="sxs-lookup"><span data-stu-id="f80e5-113">Once a method is closed, no more symbols can be defined within it.</span></span>|  
|[<span data-ttu-id="f80e5-114">CloseNamespace (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-114">CloseNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closenamespace-method.md)|<span data-ttu-id="f80e5-115">Chiude l'ultimo aperto dello spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f80e5-115">Closes the most recently opened namespace.</span></span>|  
|[<span data-ttu-id="f80e5-116">CloseScope (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-116">CloseScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-closescope-method.md)|<span data-ttu-id="f80e5-117">Chiude l'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="f80e5-117">Closes the current lexical scope.</span></span>|  
|[<span data-ttu-id="f80e5-118">DefineConstant (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-118">DefineConstant Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineconstant-method.md)|<span data-ttu-id="f80e5-119">Definisce un nome per un valore costante.</span><span class="sxs-lookup"><span data-stu-id="f80e5-119">Defines a name for a constant value.</span></span>|  
|[<span data-ttu-id="f80e5-120">DefineDocument (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-120">DefineDocument Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definedocument-method.md)|<span data-ttu-id="f80e5-121">Definisce un documento di origine.</span><span class="sxs-lookup"><span data-stu-id="f80e5-121">Defines a source document.</span></span>|  
|[<span data-ttu-id="f80e5-122">DefineField (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-122">DefineField Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definefield-method.md)|<span data-ttu-id="f80e5-123">Definisce una singola variabile che non è presente all'interno di un metodo.</span><span class="sxs-lookup"><span data-stu-id="f80e5-123">Defines a single variable that is not within a method.</span></span>|  
|[<span data-ttu-id="f80e5-124">DefineGlobalVariable (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-124">DefineGlobalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineglobalvariable-method.md)|<span data-ttu-id="f80e5-125">Definisce una singola variabile globale.</span><span class="sxs-lookup"><span data-stu-id="f80e5-125">Defines a single global variable.</span></span>|  
|[<span data-ttu-id="f80e5-126">DefineLocalVariable (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-126">DefineLocalVariable Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definelocalvariable-method.md)|<span data-ttu-id="f80e5-127">Definisce una singola variabile nell'ambito lessicale corrente.</span><span class="sxs-lookup"><span data-stu-id="f80e5-127">Defines a single variable in the current lexical scope.</span></span>|  
|[<span data-ttu-id="f80e5-128">DefineParameter (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-128">DefineParameter Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-defineparameter-method.md)|<span data-ttu-id="f80e5-129">Definisce un singolo parametro nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="f80e5-129">Defines a single parameter in the current method.</span></span>|  
|[<span data-ttu-id="f80e5-130">DefineSequencePoints (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-130">DefineSequencePoints Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-definesequencepoints-method.md)|<span data-ttu-id="f80e5-131">Definisce un gruppo di punti di sequenza nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="f80e5-131">Defines a group of sequence points within the current method.</span></span>|  
|[<span data-ttu-id="f80e5-132">GetDebugInfo (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-132">GetDebugInfo Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-getdebuginfo-method.md)|<span data-ttu-id="f80e5-133">Restituisce le informazioni necessarie per un compilatore per scrivere la voce di directory di debug nell'intestazione del file (PE) eseguibile portabile.</span><span class="sxs-lookup"><span data-stu-id="f80e5-133">Returns the information necessary for a compiler to write the debug directory entry in the portable executable (PE) file header.</span></span>|  
|[<span data-ttu-id="f80e5-134">Initialize (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-134">Initialize Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize-method.md)|<span data-ttu-id="f80e5-135">Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer e il nome del file di output in cui verranno scritti i simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="f80e5-135">Sets the metadata emitter interface with which this writer will be associated, and sets the output file name to which the debugging symbols will be written.</span></span>|  
|[<span data-ttu-id="f80e5-136">Initialize2 (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-136">Initialize2 Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-initialize2-method.md)|<span data-ttu-id="f80e5-137">Imposta l'interfaccia di emissione di metadati con il quale verrà associato questo writer, imposta il nome del file di output a cui verranno scritti i simboli di debug e la posizione finale del file di database (PDB) del programma.</span><span class="sxs-lookup"><span data-stu-id="f80e5-137">Sets the metadata emitter interface with which this writer will be associated, sets the output file name to which the debugging symbols will be written, and sets the final location of the program database (PDB) file.</span></span>|  
|[<span data-ttu-id="f80e5-138">OpenMethod (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-138">OpenMethod Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openmethod-method.md)|<span data-ttu-id="f80e5-139">Apre un metodo nel quale simbolo vengono create le informazioni.</span><span class="sxs-lookup"><span data-stu-id="f80e5-139">Opens a method into which symbol information is emitted.</span></span>|  
|[<span data-ttu-id="f80e5-140">OpenNamespace (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-140">OpenNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-opennamespace-method.md)|<span data-ttu-id="f80e5-141">Apre un nuovo spazio dei nomi.</span><span class="sxs-lookup"><span data-stu-id="f80e5-141">Opens a new namespace.</span></span>|  
|[<span data-ttu-id="f80e5-142">OpenScope (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-142">OpenScope Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-openscope-method.md)|<span data-ttu-id="f80e5-143">Apre un nuovo ambito lessicale nel metodo corrente.</span><span class="sxs-lookup"><span data-stu-id="f80e5-143">Opens a new lexical scope in the current method.</span></span>|  
|[<span data-ttu-id="f80e5-144">RemapToken (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-144">RemapToken Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-remaptoken-method.md)|<span data-ttu-id="f80e5-145">Notifica il writer di simboli che è stato rimappato un token di metadati come i metadati è stato creato.</span><span class="sxs-lookup"><span data-stu-id="f80e5-145">Notifies the symbol writer that a metadata token has been remapped as the metadata was emitted.</span></span>|  
|[<span data-ttu-id="f80e5-146">SetMethodSourceRange (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-146">SetMethodSourceRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setmethodsourcerange-method.md)|<span data-ttu-id="f80e5-147">Specifica l'inizio e fine di un metodo all'interno di un file di origine.</span><span class="sxs-lookup"><span data-stu-id="f80e5-147">Specifies the true start and end of a method within a source file.</span></span>|  
|[<span data-ttu-id="f80e5-148">SetScopeRange (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-148">SetScopeRange Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setscoperange-method.md)|<span data-ttu-id="f80e5-149">Definisce l'intervallo di offset per l'ambito lessicale specificato.</span><span class="sxs-lookup"><span data-stu-id="f80e5-149">Defines the offset range for the specified lexical scope.</span></span>|  
|[<span data-ttu-id="f80e5-150">SetSymAttribute (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-150">SetSymAttribute Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setsymattribute-method.md)|<span data-ttu-id="f80e5-151">Definisce un attributo personalizzato in base al relativo nome.</span><span class="sxs-lookup"><span data-stu-id="f80e5-151">Defines a custom attribute based upon its name.</span></span>|  
|[<span data-ttu-id="f80e5-152">SetUserEntryPoint (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-152">SetUserEntryPoint Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-setuserentrypoint-method.md)|<span data-ttu-id="f80e5-153">Specifica il metodo definito dall'utente che è il punto di ingresso per questo modulo.</span><span class="sxs-lookup"><span data-stu-id="f80e5-153">Specifies the user-defined method that is the entry point for this module.</span></span>|  
|[<span data-ttu-id="f80e5-154">UsingNamespace (metodo)</span><span class="sxs-lookup"><span data-stu-id="f80e5-154">UsingNamespace Method</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-usingnamespace-method.md)|<span data-ttu-id="f80e5-155">Specifica il nome completo dello spazio dei nomi specificato viene utilizzato all'interno dell'ambito lessicale aperto.</span><span class="sxs-lookup"><span data-stu-id="f80e5-155">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f80e5-156">Requisiti</span><span class="sxs-lookup"><span data-stu-id="f80e5-156">Requirements</span></span>  
 <span data-ttu-id="f80e5-157">**Intestazione:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="f80e5-157">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f80e5-158">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f80e5-158">See Also</span></span>  
 [<span data-ttu-id="f80e5-159">Interfacce dell'archivio dei simboli di diagnostica</span><span class="sxs-lookup"><span data-stu-id="f80e5-159">Diagnostics Symbol Store Interfaces</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)  
 [<span data-ttu-id="f80e5-160">ISymUnmanagedWriter2 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f80e5-160">ISymUnmanagedWriter2 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter2-interface.md)  
 [<span data-ttu-id="f80e5-161">ISymUnmanagedWriter3 (interfaccia)</span><span class="sxs-lookup"><span data-stu-id="f80e5-161">ISymUnmanagedWriter3 Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter3-interface.md)