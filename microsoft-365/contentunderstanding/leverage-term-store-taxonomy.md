---
title: Taxonomieën voor het maken van een extractie met een termenarchief
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: De taxonomie termenarchief maken bij het maken van een extractor in uw document met een model in Microsoft SharePoint Syntex.
ms.openlocfilehash: 94f7a0389d2f06e0f8c1a60a341a02e43dfb2071
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295862"
---
# <a name="leverage-term-store-taxonomy-when-creating-an-extractor"></a><span data-ttu-id="23f45-103">Taxonomieën voor het maken van een extractie met een termenarchief</span><span class="sxs-lookup"><span data-stu-id="23f45-103">Leverage term store taxonomy when creating an extractor</span></span>


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="23f45-104">Wanneer u in uw document een Extractor maakt die het model van SharePoint Syntex, kunt u profiteren van de beheerde termenarchief met [metagegevens Services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) om de voorwaarden weer te geven voor gegevens die u extra uitpakt.</span><span class="sxs-lookup"><span data-stu-id="23f45-104">When you create an extractor in your document understanding model in SharePoint Syntex, you can take advantage of [Managed Metadata services](https://docs.microsoft.com/sharepoint/managed-metadata#terms) term store taxonomy to display preferred terms for data that you extract.</span></span>  

<span data-ttu-id="23f45-105">In het model worden alle **contract** documenten die worden geüpload naar de documentbibliotheek herkend en geclassificeerd.</span><span class="sxs-lookup"><span data-stu-id="23f45-105">As an example, your model identifies and classifies all **Contract** documents that are uploaded to the document library.</span></span>  <span data-ttu-id="23f45-106">Daarnaast wordt in het model ook een service waarde voor de **contracten** van elk contract opgehaald en wordt deze weergegeven in een kolom in de weergave van de bibliotheek.</span><span class="sxs-lookup"><span data-stu-id="23f45-106">Additionally, the model also extracts a **Contract Service** value from each contract, and will display it in a column in your library view.</span></span> <span data-ttu-id="23f45-107">Onder de verschillende contract service waarden in de contracten zijn er verschillende oudere waarden die uw bedrijf niet langer gebruikt en waarvan de naam is gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="23f45-107">Among the various Contract Services values in the contracts, there are several older values that your company no longer uses and have been renamed.</span></span> <span data-ttu-id="23f45-108">Alle verwijzingen naar het *ontwerp*, de *grafische*of de *topografieal* contractservice van de voorwaarden, worden voortaan *creatief*genoemd.</span><span class="sxs-lookup"><span data-stu-id="23f45-108">For example, all references to the terms *Design*, *Graphics*, or *Topography* contract services should now be called *Creative*.</span></span> <span data-ttu-id="23f45-109">Wanneer uw model een van de verouderde voorwaarden uit een contract document ophaalt, zoekt u in uw bibliotheek weergave de actuele term: advertentie.</span><span class="sxs-lookup"><span data-stu-id="23f45-109">Whenever your model extracts one of the outdated terms from a contract document, you want it to display the current term - Creative - in your library view.</span></span> <span data-ttu-id="23f45-110">In het onderstaande voorbeeld ziet u in het model training het model dat één voorbeelddocument de verouderde term *ontwerpt*.</span><span class="sxs-lookup"><span data-stu-id="23f45-110">In the example below, while training the model we see that one sample document contains the outdated term of *Design*.</span></span>

   ![Termenarchief](../media/content-understanding/design.png)</br>


## <a name="term-set-synonyms"></a><span data-ttu-id="23f45-112">Synoniemen voor termensets</span><span class="sxs-lookup"><span data-stu-id="23f45-112">Term set synonyms</span></span> 

<span data-ttu-id="23f45-113">Termensets worden geconfigureerd in het termenarchief beheerde metagegevens Services in het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="23f45-113">Term sets are configured in the Managed Metadata services term store in the SharePoint admin center.</span></span> <span data-ttu-id="23f45-114">In het onderstaande voorbeeld is de [termenset](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) *contract service* geconfigureerd met een aantal voorwaarden, waaronder *advertenties*.</span><span class="sxs-lookup"><span data-stu-id="23f45-114">In the the example below, the *Contract Services* [term set](https://docs.microsoft.com/sharepoint/managed-metadata#term-set) is configured to include a number of terms, including *Creative*.</span></span>  <span data-ttu-id="23f45-115">De gegevens in het voorbeeld laten zien dat de term drie synoniemen (*ontwerp*, *grafisch*en *topografie*) bevat en dat de synoniemen moeten worden omgezet in *creatief*.</span><span class="sxs-lookup"><span data-stu-id="23f45-115">The details for it show that the term has three synonyms (*Design*, *Graphics*, and *Topography*) and the synonyms should be translated to *Creative*.</span></span>

   ![Termenset](../media/content-understanding/term-store.png)</br>

<span data-ttu-id="23f45-117"><Mike, dit is waar ik niet weet hoe dit moet worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="23f45-117"><Mike, here is where I am unsure about how to describe this.</span></span>  <span data-ttu-id="23f45-118">Met welke actie wordt het model aangegeven dat wanneer ik een Extractor maak voor het extraheren en weergeven van een kolom voor contract services, wat betekent dat de kolom ' gemarkeerd ' voor het gebruik van de termenset beheerde metagegevens voor Creative Services? ></span><span class="sxs-lookup"><span data-stu-id="23f45-118">What action tells the model that when I create an extractor to extract and display a Contract Services column, how is that column "marked" to use the managed metadata term set for Creative Services?></span></span>

## <a name="configure-your-document-library-site-column-for-a-managed-metadata-field"></a><span data-ttu-id="23f45-119">De kolom met de documentbibliotheek site configureren voor een beheerd metagegevensveld</span><span class="sxs-lookup"><span data-stu-id="23f45-119">Configure your document library site column for a managed metadata field</span></span>


   ![Beheerde metagegevens maken](../media/content-understanding/creative.png)</br>

## <a name="see-also"></a><span data-ttu-id="23f45-121">Zie ook</span><span class="sxs-lookup"><span data-stu-id="23f45-121">See Also</span></span>
[<span data-ttu-id="23f45-122">Inleiding in beheerde metagegevens</span><span class="sxs-lookup"><span data-stu-id="23f45-122">Introduction to Managed Metadata</span></span>](https://docs.microsoft.com/sharepoint/managed-metadata#terms)</br>
[<span data-ttu-id="23f45-123">Een extractor maken</span><span class="sxs-lookup"><span data-stu-id="23f45-123">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="23f45-124">Een kolom met beheerde metagegevens maken</span><span class="sxs-lookup"><span data-stu-id="23f45-124">Create a managed metadata column</span></span>](https://support.microsoft.com/office/create-a-managed-metadata-column-8fad9e35-a618-4400-b3c7-46f02785d27f?redirectSourcePath=%252farticle%252fc2a06717-8105-4aea-890d-3082853ab7b7&ui=en-US&rs=en-US&ad=US)</br>





