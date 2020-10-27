---
title: Microsoft 365 SharePoint Online gegevens verwijderen
ms.author: robmazz
author: robmazz
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
ms.openlocfilehash: 888ee807e6cd4ddc435c1df86a63502a617d6cb8
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769040"
---
# <a name="sharepoint-online-data-deletion-in-microsoft-365"></a><span data-ttu-id="60d79-103">SharePoint Online-gegevensverwijdering in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="60d79-103">SharePoint Online Data Deletion in Microsoft 365</span></span>

<span data-ttu-id="60d79-104">In SharePoint Online worden objecten als een abstracte code in toepassingsdatabases opgeslagen.</span><span class="sxs-lookup"><span data-stu-id="60d79-104">SharePoint Online stores objects as abstracted code within application databases.</span></span> <span data-ttu-id="60d79-105">Wanneer een gebruiker een bestand uploadt naar SharePoint Online, wordt dit bestand ontleed en vertaald in meerdere tabellen voor meerdere databases.</span><span class="sxs-lookup"><span data-stu-id="60d79-105">When a user uploads a file to SharePoint Online, that file is disassembled and translated into application code and stored in multiple tables across multiple databases.</span></span> <span data-ttu-id="60d79-106">In SharePoint Online wordt alle inhoud die een klant uploadt, verbroken in segmenten, versleuteld (met een of meer AES 256-bits) en verspreid over het datacenter.</span><span class="sxs-lookup"><span data-stu-id="60d79-106">In SharePoint Online, all content that a customer uploads is broken into chunks, encrypted (with one or more AES 256-bit keys), and distributed across the datacenter.</span></span> 

<span data-ttu-id="60d79-107">In SharePoint Online worden items gedurende 93 dagen bewaard vanaf het moment dat u ze verwijdert van de oorspronkelijke locatie.</span><span class="sxs-lookup"><span data-stu-id="60d79-107">In SharePoint Online, items are retained for 93 days from the time you delete them from their original location.</span></span> <span data-ttu-id="60d79-108">De persoon blijft in de Prullenbak van de site het hele tijdstip verlaten, tenzij iemand deze verwijdert.</span><span class="sxs-lookup"><span data-stu-id="60d79-108">They stay in the site Recycle Bin the entire time, unless someone deletes them from there or empties that Recycle Bin.</span></span> <span data-ttu-id="60d79-109">In dat geval gaan de items naar de Prullenbak van de siteverzameling, waar ze de rest van de 93 dagen blijven.</span><span class="sxs-lookup"><span data-stu-id="60d79-109">In that case, the items go to the site collection Recycle Bin, where they stay for the remainder of the 93 days.</span></span> <span data-ttu-id="60d79-110">Zie [items in de Prullenbak van een SharePoint-site terugzetten](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) en [Verwijderde items terugzetten uit de Prullenbak voor siteverzamelingen](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b)voor informatie over het herstellen van verwijderde items.</span><span class="sxs-lookup"><span data-stu-id="60d79-110">For info about restoring deleted items, see [Restore items in the Recycle Bin of a SharePoint site](https://support.office.com/article/6df466b6-55f2-4898-8d6e-c0dff851a0be#ID0EAADAAA=Online
) and [Restore deleted items from the site collection recycle bin](https://support.office.com/article/5fa924ee-16d7-487b-9a0a-021b9062d14b).</span></span> <span data-ttu-id="60d79-111">De bewaartijd voor de prullenbak kan niet worden geconfigureerd in SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="60d79-111">The Recycle Bin retention time is not configurable in SharePoint Online.</span></span>

<span data-ttu-id="60d79-112">Wanneer u een siteverzameling verwijdert, verwijdert u ook de hiërarchie van sites in de verzameling en de inhoud ervan.</span><span class="sxs-lookup"><span data-stu-id="60d79-112">When you delete a site collection, you're also deleting the hierarchy of sites in the collection, and all content within them:</span></span>

- <span data-ttu-id="60d79-113">Documenten en documentbibliotheken</span><span class="sxs-lookup"><span data-stu-id="60d79-113">Documents and document libraries</span></span>
- <span data-ttu-id="60d79-114">Lijsten en lijstgegevens</span><span class="sxs-lookup"><span data-stu-id="60d79-114">Lists and list data</span></span>
- <span data-ttu-id="60d79-115">Configuratie-instellingen van site</span><span class="sxs-lookup"><span data-stu-id="60d79-115">Site configuration settings</span></span>
- <span data-ttu-id="60d79-116">Rollen en beveiligingsgegevens die zijn gerelateerd aan de site of de subsites</span><span class="sxs-lookup"><span data-stu-id="60d79-116">Role and security information that is related to the site or its subsites</span></span>
- <span data-ttu-id="60d79-117">Subsites van de website op het hoogste niveau, de bijbehorende inhoud en gebruikersgegevens</span><span class="sxs-lookup"><span data-stu-id="60d79-117">Subsites of the top-level website, their contents, and user information</span></span>

<span data-ttu-id="60d79-118">Als u per ongeluk een siteverzameling verwijdert, kan deze door een globale beheerder of SharePoint-beheerder worden hersteld via het SharePoint-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="60d79-118">If you accidentally delete a site collection, it can be restored by a global or SharePoint admin using the SharePoint admin center.</span></span>

<span data-ttu-id="60d79-119">Verwijderde siteverzamelingen worden gedurende 93 dagen bewaard.</span><span class="sxs-lookup"><span data-stu-id="60d79-119">Deleted site collections are retained for 93 days.</span></span> <span data-ttu-id="60d79-120">Na 93 dagen worden sites en al hun inhoud en instellingen definitief verwijderd, inclusief lijsten, bibliotheken, pagina's en subsites.</span><span class="sxs-lookup"><span data-stu-id="60d79-120">After 93 days, sites and all their content and settings are permanently deleted, including lists, libraries, pages, and any subsites.</span></span>

<span data-ttu-id="60d79-121">Permanent verwijderen wordt uitgevoerd wanneer een gebruiker de verwijderde items uit de Prullenbak van de siteverzameling verwijdert, wanneer de bewaarperiode en de back-up van de back-upperioden zijn verlopen of wanneer een beheerder de siteverzameling permanent verwijdert met behulp van de [Remove-SPODeletedSite-cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="60d79-121">Hard deletion occurs when a user purges deleted items from the site collection Recycle Bin, when the retention and backup periods expire, or when an administrator permanently deletes a site collection using the [Remove-SPODeletedSite cmdlet](/powershell/module/sharepoint-online/Remove-SPODeletedSite?view=sharepoint-ps).</span></span> <span data-ttu-id="60d79-122">Wanneer een gebruiker de inhoud permanent verwijdert (permanent verwijdert of verwijdert) uit SharePoint Online, worden alle versleutelingssleutels voor de verwijderde segmenten ook verwijderd.</span><span class="sxs-lookup"><span data-stu-id="60d79-122">When a user hard deletes (permanently deletes, or purges) content from SharePoint Online, all encryption keys for the deleted chunks are also deleted.</span></span> <span data-ttu-id="60d79-123">De blokken op de schijven die eerder de verwijderde segmenten hebben opgeslagen, zijn gemarkeerd als niet-gebruikt en beschikbaar voor hergebruik.</span><span class="sxs-lookup"><span data-stu-id="60d79-123">The blocks on the disks that previously stored the deleted chunks are marked as unused and available for re-use.</span></span>
