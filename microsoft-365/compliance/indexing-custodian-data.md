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
ms.openlocfilehash: f510b7e9c0fa2c5c181709c96907610066a4b1cf
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430504"
---
# <a name="advanced-indexing-of-custodian-data"></a><span data-ttu-id="37e5b-103">Geavanceerde indexering van beheerdersgegevens</span><span class="sxs-lookup"><span data-stu-id="37e5b-103">Advanced indexing of custodian data</span></span>

<span data-ttu-id="37e5b-104">Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery geval, wordt inhoud die als gedeeltelijk geïndexeerd is beschouwd of indexeringsfouten heeft gehad, opnieuw geïndexeerd om deze volledig doorzoekbaar te maken.</span><span class="sxs-lookup"><span data-stu-id="37e5b-104">When a custodian is added to an Advanced eDiscovery case, any content that was deemed as partially indexed or had indexing errors with is reindexed to make it fully searchable.</span></span>  <span data-ttu-id="37e5b-105">Dit proces voor het opnieuw indexeren wordt *Geavanceerde indexering genoemd.*</span><span class="sxs-lookup"><span data-stu-id="37e5b-105">This reindexing process is called *Advanced indexing*.</span></span> <span data-ttu-id="37e5b-106">Er zijn een aantal redenen waarom inhoud gedeeltelijk is geïndexeerd of indexeringsfouten bevat.</span><span class="sxs-lookup"><span data-stu-id="37e5b-106">There are a number of reasons that content is partially indexed or has indexing errors.</span></span> <span data-ttu-id="37e5b-107">Dit omvat afbeeldingsbestanden of de aanwezigheid van afbeeldingen in een bestand, niet-ondersteunde bestandstypen of indexeringslimieten met bestandsgrootte.</span><span class="sxs-lookup"><span data-stu-id="37e5b-107">This includes image files or the presence of images in a file, unsupported file types, or file sized indexing limits.</span></span> <span data-ttu-id="37e5b-108">Voor SharePoint worden geavanceerde indexering alleen uitgevoerd op items die zijn gemarkeerd als gedeeltelijk geïndexeerd of met indexeringsfouten.</span><span class="sxs-lookup"><span data-stu-id="37e5b-108">For SharePoint files, Advanced indexing only runs on items are marked as partially indexed or that have indexing errors.</span></span> <span data-ttu-id="37e5b-109">In Exchange worden e-mailberichten met afbeeldingsbijlagen niet gemarkeerd als gedeeltelijk geïndexeerd of met indexeringsfouten.</span><span class="sxs-lookup"><span data-stu-id="37e5b-109">In Exchange, email messages that have image attachments are not marked as partially indexed or with indexing errors.</span></span> <span data-ttu-id="37e5b-110">Dit betekent dat deze bestanden niet opnieuw worden geïndexeerd door geavanceerd indexeringsproces.</span><span class="sxs-lookup"><span data-stu-id="37e5b-110">This means that those files will not be reindexed by Advanced indexing process.</span></span>

<span data-ttu-id="37e5b-111">Zie voor meer informatie over het verwerken van ondersteuning en gedeeltelijk geïndexeerde items:</span><span class="sxs-lookup"><span data-stu-id="37e5b-111">To learn more about processing support and partially indexed items, see:</span></span>

- [<span data-ttu-id="37e5b-112">Ondersteunde bestandstypen in Advanced eDiscovery</span><span class="sxs-lookup"><span data-stu-id="37e5b-112">Supported file types in Advanced eDiscovery</span></span>](supported-filetypes-ediscovery20.md)

- [<span data-ttu-id="37e5b-113">Gedeeltelijk geïndexeerde items in Inhoud zoeken in Office 365</span><span class="sxs-lookup"><span data-stu-id="37e5b-113">Partially indexed items in Content Search in Office 365</span></span>](partially-indexed-items-in-content-search.md)

- [<span data-ttu-id="37e5b-114">Bestandsindelingen geïndexeerd door Exchange Zoeken</span><span class="sxs-lookup"><span data-stu-id="37e5b-114">File formats indexed by Exchange Search</span></span>](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [<span data-ttu-id="37e5b-115">Standaard verkende bestandsnaamextensies en geparseerde bestandstypen in SharePoint Server</span><span class="sxs-lookup"><span data-stu-id="37e5b-115">Default crawled file name extensions and parsed file types in SharePoint Server</span></span>](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a><span data-ttu-id="37e5b-116">Geavanceerde indexeringsresultaten weergeven</span><span class="sxs-lookup"><span data-stu-id="37e5b-116">Viewing Advanced indexing results</span></span>

<span data-ttu-id="37e5b-117">Nadat het proces voor geavanceerde indexering is voltooid, kunt u inzicht krijgen in de effectiviteit van de opwerking.</span><span class="sxs-lookup"><span data-stu-id="37e5b-117">After the Advanced indexing process is completed, you can get an understanding of the effectiveness of reprocessing.</span></span>  <span data-ttu-id="37e5b-118">In de weergave Geavanceerde indexeringsresultaten op **het** tabblad Verwerking voor een zaak bevat de grafiek het aantal items dat aan de *hybride index is toegevoegd.*</span><span class="sxs-lookup"><span data-stu-id="37e5b-118">In the Advanced indexing results view on the **Processing** tab for a case, the graph lists the number of items added to the *hybrid index*.</span></span>  <span data-ttu-id="37e5b-119">De hybride index is de Advanced eDiscovery inhoud op te slaat.</span><span class="sxs-lookup"><span data-stu-id="37e5b-119">The hybrid index is where Advanced eDiscovery stores the reprocessed content.</span></span>

<span data-ttu-id="37e5b-120">Deze weergave bevat ook het aantal items waarvoor herstel nodig is en een andere grafiek met fouten per bestandstype.</span><span class="sxs-lookup"><span data-stu-id="37e5b-120">This view  also includes the number of items that require remediation and another graph of errors by file type.</span></span> <span data-ttu-id="37e5b-121">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="37e5b-121">For more information, see:</span></span>

- [<span data-ttu-id="37e5b-122">Foutherstel bij het verwerken van gegevens</span><span class="sxs-lookup"><span data-stu-id="37e5b-122">Error remediation when processing data</span></span>](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [<span data-ttu-id="37e5b-123">Foutherstel voor één item</span><span class="sxs-lookup"><span data-stu-id="37e5b-123">Single item error remediation</span></span>](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a><span data-ttu-id="37e5b-124">De geavanceerde index voor beheerders bijwerken</span><span class="sxs-lookup"><span data-stu-id="37e5b-124">Updating the Advanced index for custodians</span></span>

<span data-ttu-id="37e5b-125">Wanneer een bewaarder wordt toegevoegd aan een Advanced eDiscovery, worden alle gedeeltelijk geïndexeerde items opnieuw verwerkt.</span><span class="sxs-lookup"><span data-stu-id="37e5b-125">When a custodian is added to an Advanced eDiscovery case, all partially indexed items are reprocessed.</span></span> <span data-ttu-id="37e5b-126">Naarmate de tijd verstrijkt, kunnen echter meer gedeeltelijk geïndexeerde items worden toegevoegd aan het postvak of het OneDrive account van een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="37e5b-126">However, as time passes, more partially indexed items may be added to a user's mailbox or OneDrive account.</span></span>  <span data-ttu-id="37e5b-127">Indien nodig kunt u de index bijwerken voor specifieke bewaarders.</span><span class="sxs-lookup"><span data-stu-id="37e5b-127">If necessary, you can update the index for specific custodian.</span></span> <span data-ttu-id="37e5b-128">Zie Beheerders beheren in een Advanced eDiscovery [voor meer informatie.](manage-new-custodians.md#re-index-custodian-data)</span><span class="sxs-lookup"><span data-stu-id="37e5b-128">For more information, see [Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data).</span></span> <span data-ttu-id="37e5b-129">U kunt ook de index voor alle beheerders in een zaak bijwerken door op de **index Bijwerken** op het tabblad **Verwerking te** klikken.</span><span class="sxs-lookup"><span data-stu-id="37e5b-129">You can also update the index for all custodians in a case by clicking the **Update index** on the **Processing** tab.</span></span>

> [!NOTE]
> <span data-ttu-id="37e5b-130">Het bijwerken van beheerdersindexen is een langlopende procedure.</span><span class="sxs-lookup"><span data-stu-id="37e5b-130">Updating custodian indexes is a long running process.</span></span> <span data-ttu-id="37e5b-131">U wordt aangeraden indexen niet meer dan één keer per dag bij te werken in een zaak.</span><span class="sxs-lookup"><span data-stu-id="37e5b-131">It's recommended that you don't update indexes more than once a day in a case.</span></span>
