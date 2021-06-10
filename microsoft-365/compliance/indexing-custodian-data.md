---
title: Geavanceerde indexering van beheerdersgegevens
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery geval, wordt inhoud die als gedeeltelijk geïndexeerd is beschouwd, opnieuw verwerkt om deze volledig doorzoekbaar te maken.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161892"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="580f9-103">Geavanceerde indexering van beheerdersgegevens</span><span class="sxs-lookup"><span data-stu-id="580f9-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="580f9-104">Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery geval, wordt inhoud die als gedeeltelijk geïndexeerd is beschouwd, opnieuw verwerkt om deze volledig doorzoekbaar te maken.</span><span class="sxs-lookup"><span data-stu-id="580f9-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed is reprocessed to make it fully searchable.</span></span>  <span data-ttu-id="580f9-105">Dit proces wordt Geavanceerde *indexering genoemd.*</span><span class="sxs-lookup"><span data-stu-id="580f9-105">This process is called *Advanced indexing*.</span></span> <span data-ttu-id="580f9-106">Inhoud kan gedeeltelijk worden geïndexeerd om een aantal redenen, zoals het bestaan van afbeeldingen, niet-ondersteunde bestandstypen of wanneer limieten voor bestandsgrootte indexeren worden aangetroffen.</span><span class="sxs-lookup"><span data-stu-id="580f9-106">Content can be partially indexed for a number of reasons including the existence of images, unsupported file types or when indexing file size limits are encountered.</span></span>

<span data-ttu-id="580f9-107">Zie voor meer informatie over het verwerken van ondersteuning en gedeeltelijk geïndexeerde items:</span><span class="sxs-lookup"><span data-stu-id="580f9-107">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="580f9-108">Ondersteunde bestandstypen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="580f9-108">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="580f9-109">Gedeeltelijk geïndexeerde items in Inhoud zoeken in Office 365</span><span class="sxs-lookup"><span data-stu-id="580f9-109">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="580f9-110">Bestandsindelingen geïndexeerd door Exchange Zoeken</span><span class="sxs-lookup"><span data-stu-id="580f9-110">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="580f9-111">Standaard verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="580f9-111">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="580f9-112">Geavanceerde indexeringsresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="580f9-112">Viewing Advanced indexing results</span></span>

<span data-ttu-id="580f9-113">Nadat het proces voor geavanceerde indexering is voltooid, kunt u inzicht krijgen in de effectiviteit van de opwerking.</span><span class="sxs-lookup"><span data-stu-id="580f9-113">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="580f9-114">In de weergave Geavanceerde indexeringsresultaten op **het** tabblad Verwerking voor een zaak bevat de grafiek het aantal items dat aan de *hybride index is toegevoegd.*</span><span class="sxs-lookup"><span data-stu-id="580f9-114">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="580f9-115">De hybride index is de Advanced eDiscovery inhoud op te slaat.</span><span class="sxs-lookup"><span data-stu-id="580f9-115">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="580f9-116">Deze weergave bevat ook het aantal items waarvoor herstel nodig is en een andere grafiek met fouten per bestandstype.</span><span class="sxs-lookup"><span data-stu-id="580f9-116">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="580f9-117">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="580f9-117">For more information, see:</span></span>

- [<span data-ttu-id="580f9-118">Foutherstel bij het verwerken van gegevens</span><span class="sxs-lookup"><span data-stu-id="580f9-118">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="580f9-119">Foutherstel voor één item</span><span class="sxs-lookup"><span data-stu-id="580f9-119">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="580f9-120">De geavanceerde index voor beheerders bijwerken</span><span class="sxs-lookup"><span data-stu-id="580f9-120">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="580f9-121">Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery, worden alle gedeeltelijk geïndexeerde items opnieuw verwerkt.</span><span class="sxs-lookup"><span data-stu-id="580f9-121">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="580f9-122">Naarmate de tijd verstrijkt, kunnen echter meer gedeeltelijk geïndexeerde items worden toegevoegd aan het postvak of het OneDrive account van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="580f9-122">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="580f9-123">Indien nodig kunt u de index bijwerken voor specifieke bewaarders.</span><span class="sxs-lookup"><span data-stu-id="580f9-123">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="580f9-124">Zie Beheerders beheren in een Advanced eDiscovery [voor meer informatie.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="580f9-124">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="580f9-125">U kunt ook de index voor alle beheerders in een zaak bijwerken door op de **index Bijwerken** op het tabblad **Verwerking te** klikken.</span><span class="sxs-lookup"><span data-stu-id="580f9-125">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="580f9-126">Het bijwerken van beheerdersindexen is een langlopende procedure.</span><span class="sxs-lookup"><span data-stu-id="580f9-126">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="580f9-127">U wordt aangeraden indexen niet meer dan één keer per dag bij te werken in een zaak.</span><span class="sxs-lookup"><span data-stu-id="580f9-127">It's recommended that you don't update indexes more than once a day in a case.</span></span>