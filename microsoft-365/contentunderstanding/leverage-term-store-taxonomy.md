---
title: De taxonomie van een termenarchief gebruiken bij het maken van een extractor
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: De taxonomie van een termenarchief gebruiken bij het maken van een extractor in uw documentbegripmodel in Microsoft SharePoint Syntex.
ms.openlocfilehash: cf396d14a497981389cc336c5efd121f36392181
ms.sourcegitcommit: c0495e224f12c448bfc162ef2e4b33b82f064ac8
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/17/2020
ms.locfileid: "49709546"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="c541e-103">De taxonomie van een termenarchief gebruiken bij het maken van een extractor</span><span class="sxs-lookup"><span data-stu-id="c541e-103">Leverage term store taxonomy when creating an extractor</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GpJJ]  

</br>

<span data-ttu-id="c541e-104">Wanneer je een extractor maakt in je documentbegrippenmodel met SharePoint Syntex, kan je gebruikmaken van de globale termensets in[termenarchief](https://docs.microsoft.com/sharepoint/managed-metadata) en voorkeurstermen te bekijken voor de gegevens die je extraheert.</span><span class="sxs-lookup"><span data-stu-id="c541e-104">When you create an extractor in your document understanding model using SharePoint Syntex, you can take advantage of global term sets in the [term store](https://docs.microsoft.com/sharepoint/managed-metadata) to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="c541e-105">Bijvoorbeeld: uw model identificeert en classificeert alle **contract** documenten die worden geüpload naar de documentbibliotheek.</span><span class="sxs-lookup"><span data-stu-id="c541e-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="c541e-106">Daarnaast extraheert het model ook een waarde **contractservice** uit elk contract, die wordt weergegeven in een kolom in uw bibliotheekweergave.</span><span class="sxs-lookup"><span data-stu-id="c541e-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="c541e-107">Tussen de verschillende waarden contractservices in de contracten staan verschillende oudere waarden, die niet langer worden gebruikt in het bedrijf en die een andere naam hebben gekregen.</span><span class="sxs-lookup"><span data-stu-id="c541e-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="c541e-108">Zo moeten alle verwijzingen naar de contractservices *Ontwerp*, *Afbeeldingen* en *Topografie* nu *Creatief* worden genoemd.</span><span class="sxs-lookup"><span data-stu-id="c541e-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="c541e-109">Wanneer uw model een van de verouderde termen uit een contractdocument ophaalt, wilt u dat de huidige term (Creatief) in de bibliotheekweergave wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c541e-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="c541e-110">In het onderstaande voorbeeld ziet u dat tijdens het trainen van het model een voorbeelddocument de verouderde term *Ontwerp* bevat.</span><span class="sxs-lookup"><span data-stu-id="c541e-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Termenarchief](../media/content-understanding/design.png)</br>

## <a name="use-a-managed-metadata-column-in-your-extractor"></a><span data-ttu-id="c541e-112">Een kolom Beheerde metagegevens in uw extractor gebruiken</span><span class="sxs-lookup"><span data-stu-id="c541e-112">Use a Managed metadata column in your extractor</span></span>

<span data-ttu-id="c541e-113">Termensets worden geconfigureerd in het termenarchief Beheerde metagegevensservices (MMS) in het SharePoint-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="c541e-113">Term sets are configured in the Managed Metadata services (MMS) term store in the SharePoint admin center.</span></span> <span data-ttu-id="c541e-114">In het onderstaande voorbeeld is de [termenset](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *contractservices* geconfigureerd om een aantal termen te bevatten, waaronder *Creatief*.</span><span class="sxs-lookup"><span data-stu-id="c541e-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="c541e-115">De informatie ervoor laat zien dat de term drie synoniemen heeft (*Ontwerp*, *Afbeelding* en *Topografie*) en dat de synoniemen moeten worden omgezet naar *Creatief*.</span><span class="sxs-lookup"><span data-stu-id="c541e-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span> 

   ![Termenset](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="c541e-117">Er kunnen een aantal redenen zijn om een synoniem te gebruiken in uw termenset.</span><span class="sxs-lookup"><span data-stu-id="c541e-117">There could be a number of reasons why you might want to use a synonym in your term set.</span></span> <span data-ttu-id="c541e-118">Er kunnen bijvoorbeeld verouderde termen, hernoemde termen of variaties afkomstig van de afdelingen van uw organisatie aanwezig zijn.</span><span class="sxs-lookup"><span data-stu-id="c541e-118">For example, there could be outdated terms, renamed terms, or variations between your organizations departments on naming.</span></span>

<span data-ttu-id="c541e-119">Om het veld beheerde metagegevens beschikbaar te maken voor selectie wanneer u de extractor maakt in uw model, moet u die [toevoegen als sitekolom beheerde metagegevens](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span><span class="sxs-lookup"><span data-stu-id="c541e-119">To make the managed metadata field available for you to select when you create your extractor in your model, you need to [add it as a managed-metadata site column](https://support.microsoft.com/office/8fad9e35-a618-4400-b3c7-46f02785d27f).</span></span> <span data-ttu-id="c541e-120">Nadat u de sitekolom hebt toegevoegd, is die beschikbaar om te selecteren wanneer u de extractor voor uw model maakt.</span><span class="sxs-lookup"><span data-stu-id="c541e-120">After you add the site column, it will be available for you to select when you create the extractor for your model.</span></span>

   ![Contractservice](../media/content-understanding/contract-services.png)</br>


<span data-ttu-id="c541e-122">Na het toepassen van uw model op de documentbibliotheek, wordt bij het uploaden van documenten naar de bibliotheek in de kolom *Creatieve diensten* de voorkeursterm (*Creatief*) weergeven wanneer de extractor een van de synonieme waarden (*Ontwerp*, *Afbeelding*, en *Topografie*) vindt.</span><span class="sxs-lookup"><span data-stu-id="c541e-122">After applying your model to the document library, when documents are uploaded to library, the *Creative Services* column will display the preferred term (*Creative*) when the extractor finds any of the synonym values (*Design*, *Graphics*, and *Topography*).</span></span>

   ![Kolom contractservice](../media/content-understanding/creative.png)</br>


## <a name="see-also"></a><span data-ttu-id="c541e-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c541e-124">See Also</span></span>
[<span data-ttu-id="c541e-125">Introductie tot beheerde metagegevens</span><span class="sxs-lookup"><span data-stu-id="c541e-125">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)

[<span data-ttu-id="c541e-126">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="c541e-126">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="c541e-127">Een kolom met beheerde metagegevens maken</span><span class="sxs-lookup"><span data-stu-id="c541e-127">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)





