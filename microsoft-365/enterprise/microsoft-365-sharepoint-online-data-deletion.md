---
title: Microsoft 365 SharePoint Online gegevens verwijderen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
f1.keywords:
- NOCSH
description: Meer informatie over hoe u de verwijdering van gegevens kunt gebruiken in SharePoint Online, bijvoorbeeld waar verwijderde inhoud is opgeslagen en voor hoelang.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5cea1b797d078f6ae627700b28c6fb90cc005637
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689381"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="4b841-103">SharePoint Online-gegevensverwijdering in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4b841-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="4b841-104">In SharePoint Online worden objecten als een abstracte code in toepassingsdatabases opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="4b841-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="4b841-105">Wanneer een gebruiker een bestand uploadt naar SharePoint Online, wordt dit bestand ontleed en vertaald in meerdere tabellen voor meerdere databases.</span><span class="sxs-lookup"><span data-stu-id="4b841-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="4b841-106">In SharePoint Online wordt alle inhoud die een klant uploadt, verbroken in segmenten, versleuteld (mogelijk met meerdere AES 256-bits) en over het datacenter gedistribueerd.</span><span class="sxs-lookup"><span data-stu-id="4b841-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (potentially with multiple AES 256-bit keys), and distributed across the datacenter.</span></span> <span data-ttu-id="4b841-107">Zie [versleuteling in de Microsoft-Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview)voor specifieke informatie over het proces van segmenteren en versleutelen.</span><span class="sxs-lookup"><span data-stu-id="4b841-107">For specific details about the chunking and encryption process, see [Encryption in the Microsoft Cloud](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-the-microsoft-cloud-overview).</span></span> 

<span data-ttu-id="4b841-108">In SharePoint Online worden items gedurende 93 dagen bewaard vanaf het moment dat u ze verwijdert van de oorspronkelijke locatie.</span><span class="sxs-lookup"><span data-stu-id="4b841-108">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="4b841-109">De persoon blijft in de Prullenbak van de site het hele tijdstip verlaten, tenzij iemand deze verwijdert.</span><span class="sxs-lookup"><span data-stu-id="4b841-109">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="4b841-110">In dat geval gaan de items naar de Prullenbak van de siteverzameling, waar ze de rest van de 93 dagen blijven.</span><span class="sxs-lookup"><span data-stu-id="4b841-110">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="4b841-111">Zie [items in de Prullenbak van een SharePoint-site terugzetten](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) en [Verwijderde items terugzetten uit de Prullenbak voor siteverzamelingen](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)voor informatie over het herstellen van verwijderde items.</span><span class="sxs-lookup"><span data-stu-id="4b841-111">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="4b841-112">De bewaartijd voor de prullenbak kan niet worden geconfigureerd in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="4b841-112">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="4b841-113">Wanneer u een siteverzameling verwijdert, verwijdert u ook de hiërarchie van sites in de verzameling en de inhoud ervan.</span><span class="sxs-lookup"><span data-stu-id="4b841-113">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="4b841-114">Documenten en documentbibliotheken</span><span class="sxs-lookup"><span data-stu-id="4b841-114">Documents and document libraries</span></span>
- <span data-ttu-id="4b841-115">Lijsten en lijstgegevens</span><span class="sxs-lookup"><span data-stu-id="4b841-115">Lists and list data</span></span>
- <span data-ttu-id="4b841-116">Configuratie-instellingen van site</span><span class="sxs-lookup"><span data-stu-id="4b841-116">Site configuration settings</span></span>
- <span data-ttu-id="4b841-117">Rollen en beveiligingsgegevens die zijn gerelateerd aan de site of de subsites</span><span class="sxs-lookup"><span data-stu-id="4b841-117">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="4b841-118">Subsites van de website op het hoogste niveau, de bijbehorende inhoud en gebruikersgegevens</span><span class="sxs-lookup"><span data-stu-id="4b841-118">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="4b841-119">Als u per ongeluk een siteverzameling verwijdert, kan deze door een globale beheerder of SharePoint-beheerder worden hersteld via het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="4b841-119">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="4b841-120">Verwijderde siteverzamelingen worden gedurende 93 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="4b841-120">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="4b841-121">Na 93 dagen worden sites en al hun inhoud en instellingen definitief verwijderd, inclusief lijsten, bibliotheken, pagina's en subsites.</span><span class="sxs-lookup"><span data-stu-id="4b841-121">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="4b841-122">Permanent verwijderen wordt uitgevoerd wanneer een gebruiker de verwijderde items uit de Prullenbak van de siteverzameling verwijdert, wanneer de bewaarperiode en de back-up van de back-upperioden zijn verlopen of wanneer een beheerder de siteverzameling permanent verwijdert met behulp van de [Remove-SPODeletedSite-cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="4b841-122">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="4b841-123">Wanneer een gebruiker de inhoud permanent verwijdert (permanent verwijdert of verwijdert) uit SharePoint Online, worden alle versleutelingssleutels voor de verwijderde segmenten ook verwijderd.</span><span class="sxs-lookup"><span data-stu-id="4b841-123">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="4b841-124">De blokken op de schijven die eerder de verwijderde segmenten hebben opgeslagen, zijn gemarkeerd als niet-gebruikt en beschikbaar voor hergebruik.</span><span class="sxs-lookup"><span data-stu-id="4b841-124">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
