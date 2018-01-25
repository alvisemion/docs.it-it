---
title: Strumento Microsoft WCF Web Service Reference Provider
description: "Panoramica dello strumento Microsoft WCF Web Service Reference Provider che aggiunge funzionalità per i progetti .NET Core e ASP.NET Core, come Aggiungi riferimento al servizio per i progetti .NET Framework."
author: mlacouture
manager: wpickett
ms.author: johalex
ms.date: 01/19/2018
ms.topic: article
ms.prod: .net-core
ms.custom: mvc
ms.openlocfilehash: 210f0a9bbf393055ebcd582d3accb3d77b1c9539
ms.sourcegitcommit: 8bde7a3432f30fc771079744955c75c58c4eb393
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2018
---
# <a name="microsoft-wcf-web-service-reference-provider-tool"></a><span data-ttu-id="44aa2-103">Strumento Microsoft WCF Web Service Reference Provider</span><span class="sxs-lookup"><span data-stu-id="44aa2-103">Microsoft WCF Web Service Reference Provider Tool</span></span>

<span data-ttu-id="44aa2-104">Nel corso degli anni, molti sviluppatori di Visual Studio hanno aumentato la produttività usando lo strumento [**Aggiungi riferimento al servizio**](../../visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) quando era necessario che i progetti .NET Framework accedessero ai servizi Web.</span><span class="sxs-lookup"><span data-stu-id="44aa2-104">Over the years, many Visual Studio developers have enjoyed the productivity that the [**Add Service Reference**](../../visualstudio/data-tools/how-to-add-update-or-remove-a-wcf-data-service-reference) tool provided when their .NET Framework projects needed to access web services.</span></span>  <span data-ttu-id="44aa2-105">Lo strumento **WCF Web Service Reference Provider** è un'estensione WCF Connected Service di Visual Studio che offre esperienza simile alla funzionalità Aggiungi riferimento al servizio per i progetti .NET Core e ASP.NET Core.</span><span class="sxs-lookup"><span data-stu-id="44aa2-105">The **WCF Web Service Reference** tool is a Visual Studio connected service extension that provides an experience like the Add Service Reference functionality for .NET Core and ASP.NET Core projects.</span></span> <span data-ttu-id="44aa2-106">Questo strumento consente di recuperare metadati da un servizio Web nella soluzione corrente, in un percorso di rete o da un file WSDL e genera un file di origine compatibile con .NET Core contenente il codice del proxy client Windows Communication Foundation (WCF) che è possibile usare per accedere al servizio Web.</span><span class="sxs-lookup"><span data-stu-id="44aa2-106">This tool retrieves metadata from a web service in the current solution, on a network location, or from a WSDL file, and generates a .NET Core compatible source file containing Windows Communication Foundation (WCF) client proxy code that you can use to access the web service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44aa2-107">Si consiglia di fare riferimento solo a servizi provenienti da un'origine attendibile.</span><span class="sxs-lookup"><span data-stu-id="44aa2-107">You should only reference services from a trusted source.</span></span> <span data-ttu-id="44aa2-108">L'aggiunta di riferimenti da un'origine non attendibile può compromettere la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="44aa2-108">Adding references from an untrusted source may compromise security.</span></span> 

## <a name="how-to-use-the-extension"></a><span data-ttu-id="44aa2-109">Come usare l'estensione</span><span class="sxs-lookup"><span data-stu-id="44aa2-109">How to use the extension</span></span>

> [!NOTE]
> <span data-ttu-id="44aa2-110">L'opzione **WCF Web Service Reference** è applicabile ai progetti creati con i modelli di progetto seguenti:</span><span class="sxs-lookup"><span data-stu-id="44aa2-110">The **WCF Web Service Reference** option is applicable to projects created using the following project templates:</span></span>
> * <span data-ttu-id="44aa2-111">**Visual C#** > **.NET Core**</span><span class="sxs-lookup"><span data-stu-id="44aa2-111">**Visual C#** > **.NET Core**</span></span>
> * <span data-ttu-id="44aa2-112">**Visual C#** > **.NET Standard**</span><span class="sxs-lookup"><span data-stu-id="44aa2-112">**Visual C#** > **.NET Standard**</span></span>
> * <span data-ttu-id="44aa2-113">**Visual C#** > **Web** > **Applicazione ASP.NET Core Web**</span><span class="sxs-lookup"><span data-stu-id="44aa2-113">**Visual C#** > **Web** > **ASP.NET Core Web Application**</span></span>

<span data-ttu-id="44aa2-114">Se si usa il modello di progetto **Applicazione ASP.NET Core Web**, l'articolo illustra i passaggi per aggiungere un riferimento al servizio WFC al progetto:</span><span class="sxs-lookup"><span data-stu-id="44aa2-114">Using the **ASP.NET Core Web Application** project template as an example, this article walks you through adding a WCF service reference to the project:</span></span>

1. <span data-ttu-id="44aa2-115">In Esplora soluzioni fare doppio clic sul nodo **Servizi connessi** del progetto. Per un progetto .NET Core o .NET Standard questa opzione è disponibile facendo clic con il tasto destro del mouse sul nodo **Dipendenze** del progetto in Esplora soluzioni.</span><span class="sxs-lookup"><span data-stu-id="44aa2-115">In Solution Explorer, double-click the **Connected Services** node of the project (for a .NET Core or .NET Standard project this option is available when you right-click on the **Dependencies** node of the project in Solution Explorer).</span></span>

<span data-ttu-id="44aa2-116">Verrà visualizzata la pagina **Servizi connessi** come illustrato nell'immagine seguente:</span><span class="sxs-lookup"><span data-stu-id="44aa2-116">The **Connected Services** page appears as shown in the following image:</span></span>

![Scheda Servizi connessi](./media/wcf-web-service-reference-guide/wcfcs-ConnectedServicesPage.png)

2. <span data-ttu-id="44aa2-118">Nella pagina **Servizi connessi** fare clic su **Microsoft WCF Web Service Reference Provider**.</span><span class="sxs-lookup"><span data-stu-id="44aa2-118">On the **Connected Services** page, click **Microsoft WCF Web Service Reference Provider**.</span></span> <span data-ttu-id="44aa2-119">Verrà visualizzata la procedura guidata**Configura riferimento al servizio Web WCF**:</span><span class="sxs-lookup"><span data-stu-id="44aa2-119">This brings up the **Configure WCF Web Service Reference** wizard:</span></span>

![Scheda Endpoint di servizio](./media/wcf-web-service-reference-guide/wcfcs-ServiceEndpointPage.png)

3. <span data-ttu-id="44aa2-121">Selezionare un servizio.</span><span class="sxs-lookup"><span data-stu-id="44aa2-121">Select a service.</span></span>

    <span data-ttu-id="44aa2-122">3a.</span><span class="sxs-lookup"><span data-stu-id="44aa2-122">3a.</span></span> <span data-ttu-id="44aa2-123">Nella procedura guidata **Configura riferimento al servizio Web WCF** sono disponibili diverse opzioni di ricerca dei servizi:</span><span class="sxs-lookup"><span data-stu-id="44aa2-123">There are several services search options available within the **Configure WCF Web Service Reference** wizard:</span></span>
    
     * <span data-ttu-id="44aa2-124">Per cercare i servizi definiti nella soluzione corrente, fare clic sul pulsante **Individua**.</span><span class="sxs-lookup"><span data-stu-id="44aa2-124">To search for services defined in the current solution, click the **Discover** button.</span></span> 
     * <span data-ttu-id="44aa2-125">Per cercare i servizi ospitati all'indirizzo specificato, immettere un URL del servizio nella casella **Indirizzo** e fare clic sul pulsante **Vai**.</span><span class="sxs-lookup"><span data-stu-id="44aa2-125">To search for services hosted at a specified address, enter a service URL in the **Address** box and click the **Go** button.</span></span>
     * <span data-ttu-id="44aa2-126">Per selezionare un file WSDL contenente le informazioni sui metadati del servizio Web, fare clic sul pulsante **Sfoglia**.</span><span class="sxs-lookup"><span data-stu-id="44aa2-126">To select a WSDL file that contains the web service metadata information, click the **Browse** button.</span></span> 
     
    <span data-ttu-id="44aa2-127">3b.</span><span class="sxs-lookup"><span data-stu-id="44aa2-127">3b.</span></span> <span data-ttu-id="44aa2-128">Selezionare il servizio dall'elenco dei risultati della ricerca nella casella **Servizi**.</span><span class="sxs-lookup"><span data-stu-id="44aa2-128">Select the service from the search results list in the **Services** box.</span></span> <span data-ttu-id="44aa2-129">Se necessario, immettere lo spazio dei nomi per il codice generato nella casella di testo **Spazio dei nomi** corrispondente.</span><span class="sxs-lookup"><span data-stu-id="44aa2-129">If needed, enter the namespace for the generated code in the corresponding **Namespace** text box.</span></span>
    
    <span data-ttu-id="44aa2-130">3c.</span><span class="sxs-lookup"><span data-stu-id="44aa2-130">3c.</span></span> <span data-ttu-id="44aa2-131">Fare clic sul pulsante **Avanti** per aprire le pagine **Opzioni tipi di dati** e **Opzioni client**.</span><span class="sxs-lookup"><span data-stu-id="44aa2-131">Click the **Next** button to open the **Data Type Options** and the **Client Options** pages.</span></span> <span data-ttu-id="44aa2-132">In alternativa, fare clic sul pulsante **Fine** per usare le opzioni predefinite.</span><span class="sxs-lookup"><span data-stu-id="44aa2-132">Alternatively, click the **Finish** button to use the default options.</span></span>


4. <span data-ttu-id="44aa2-133">Il modulo **Opzioni tipi di dati** consente di ridefinire le impostazioni di configurazione del riferimento al servizio generato:</span><span class="sxs-lookup"><span data-stu-id="44aa2-133">The **Data Type Options** form enables you to refine the generated service reference configuration settings:</span></span>

![Scheda Opzioni tipi di dati](./media/wcf-web-service-reference-guide/wcfcs-DataTypesPage.png)

> [!NOTE]
> <span data-ttu-id="44aa2-135">La casella di controllo **Riutilizza tipi in assembly di riferimento** è utile quando i tipi di dati necessari per la generazione del codice del riferimento al servizio sono definiti in uno degli assembly di riferimento del progetto.</span><span class="sxs-lookup"><span data-stu-id="44aa2-135">The **Reuse types in referenced assemblies** check box option is useful when data types needed for service reference code generation are defined in one of your project's referenced assemblies.</span></span>  <span data-ttu-id="44aa2-136">È importante riusare tali tipi di dati esistenti per evitare problemi di runtime o conflitto del tipo in fase di compilazione.</span><span class="sxs-lookup"><span data-stu-id="44aa2-136">It's important to reuse those existing data types to avoid compile-time type clash or runtime issues.</span></span>

<span data-ttu-id="44aa2-137">È possibile che si verifichi un ritardo durante il caricamento delle informazioni, a seconda del numero di dipendenze del progetto e di altri fattori relativi alle prestazioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="44aa2-137">There may be a delay while type information is loaded, depending on the number of project dependencies and other system performance factors.</span></span> <span data-ttu-id="44aa2-138">Il pulsante **Fine** è disabilitato durante il caricamento, a meno che la casella di controllo **Riutilizza tipi in assembly di riferimento** non sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="44aa2-138">The **Finish** button is disabled during loading unless the **Reuse types in referenced assemblies** check box is unchecked.</span></span>

5. <span data-ttu-id="44aa2-139">Fare clic su **Fine** al termine dell'operazione.</span><span class="sxs-lookup"><span data-stu-id="44aa2-139">Click **Finish** when you are done.</span></span>


<span data-ttu-id="44aa2-140">Durante la visualizzazione dello stato, lo strumento:</span><span class="sxs-lookup"><span data-stu-id="44aa2-140">While displaying progress, the tool:</span></span>

* <span data-ttu-id="44aa2-141">Scarica i metadati dal servizio WCF.</span><span class="sxs-lookup"><span data-stu-id="44aa2-141">Downloads metadata from the WCF service.</span></span> 
* <span data-ttu-id="44aa2-142">Genera il codice del riferimento al servizio in un file denominato *reference.cs*e lo aggiunge al progetto sotto il nodo **Servizi connessi**.</span><span class="sxs-lookup"><span data-stu-id="44aa2-142">Generates the service reference code in a file named *reference.cs*, and adds it to your project under the **Connected Services** node.</span></span> 
* <span data-ttu-id="44aa2-143">Aggiorna il file di progetto con estensione csproj con i riferimenti al pacchetto NuGet necessari per la compilazione e l'esecuzione nella piattaforma di destinazione.</span><span class="sxs-lookup"><span data-stu-id="44aa2-143">Updates the project file (.csproj) with NuGet package references required to compile and run on the target platform.</span></span>

![Finestra di stato](./media/wcf-web-service-reference-guide/wcfcs-ProgressWindow.png)

<span data-ttu-id="44aa2-145">Al termine di questi processi, è possibile creare un'istanza del tipo di client WCF generato e richiamare le operazioni del servizio.</span><span class="sxs-lookup"><span data-stu-id="44aa2-145">When these processes complete, you can create an instance of the generated WCF client type and invoke the service operations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="44aa2-146">Passaggi successivi</span><span class="sxs-lookup"><span data-stu-id="44aa2-146">Next steps</span></span>

### <a name="feedback--questions"></a><span data-ttu-id="44aa2-147">Commenti, suggerimenti e domande</span><span class="sxs-lookup"><span data-stu-id="44aa2-147">Feedback & questions</span></span>
<span data-ttu-id="44aa2-148">In caso di domande o commenti e suggerimenti, [segnalare un problema in GitHub](https://github.com/dotnet/wcf/issues/new).</span><span class="sxs-lookup"><span data-stu-id="44aa2-148">If you have any questions or feedback, [open an issue on GitHub](https://github.com/dotnet/wcf/issues/new).</span></span> <span data-ttu-id="44aa2-149">È anche possibile rivedere domande o problemi esistenti [nel repository WCF in GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span><span class="sxs-lookup"><span data-stu-id="44aa2-149">You can also review any existing questions or issues [at the WCF repo on GitHub](https://github.com/dotnet/wcf/issues?utf8=%E2%9C%93&q=is:issue%20label:tooling).</span></span>

### <a name="release-notes"></a><span data-ttu-id="44aa2-150">Note sulla versione</span><span class="sxs-lookup"><span data-stu-id="44aa2-150">Release notes</span></span>
* <span data-ttu-id="44aa2-151">Fare riferimento alle [note sulla versione](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) per informazioni aggiornate sulle versioni, compresi i problemi noti.</span><span class="sxs-lookup"><span data-stu-id="44aa2-151">Refer to the [Release notes](https://github.com/dotnet/wcf/blob/master/release-notes/WCF-Web-Service-Reference-notes.md) for updated release information, including known issues.</span></span> 