---
title: Voorwaardelijke opmaak op basis van een formule die Ja of Nee oplevert
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Dit artikel bevat algemene tips en koppelingen naar andere bronnen waarin wordt beschreven hoe u de prestaties van Exchange Online kunt verbeteren.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909440"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="3fc06-103">Voorwaardelijke opmaak op basis van een formule die Ja of Nee oplevert</span><span class="sxs-lookup"><span data-stu-id="3fc06-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="3fc06-104">Dit artikel bevat algemene tips en koppelingen naar andere bronnen waarin wordt beschreven hoe u de prestaties van Exchange Online kunt verbeteren, met name voor een migratie.</span><span class="sxs-lookup"><span data-stu-id="3fc06-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="3fc06-105">Dit artikel maakt deel uit van [de netwerkplanning en prestatieafstemming voor Office 365-project.](./network-planning-and-performance.md)</span><span class="sxs-lookup"><span data-stu-id="3fc06-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="3fc06-106">Waar u rekening mee moet houden om de prestaties van Exchange Online te verbeteren</span><span class="sxs-lookup"><span data-stu-id="3fc06-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="3fc06-107">Als u de migratiesnelheid wilt verbeteren en de bandbreedtebeperkingen van uw organisatie voor Exchange Online wilt verlagen, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="3fc06-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="3fc06-108">**Verklein de grootte van het postvak.**</span><span class="sxs-lookup"><span data-stu-id="3fc06-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="3fc06-109">Kleinere postvakken verbeteren de migratiesnelheid.</span><span class="sxs-lookup"><span data-stu-id="3fc06-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="3fc06-110">**Gebruik de mogelijkheden voor het verplaatsen van postvakken met een hybride implementatie van Exchange.**</span><span class="sxs-lookup"><span data-stu-id="3fc06-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="3fc06-111">Met een hybride Exchange-implementatie, offline-e-mail (in de vorm van . OST-bestanden) hoeft u niet opnieuw te downloaden wanneer u migreert naar Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="3fc06-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="3fc06-112">Hierdoor worden de vereisten voor downloadbandbreedte aanzienlijk verminderd.</span><span class="sxs-lookup"><span data-stu-id="3fc06-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="3fc06-113">**Plan dat postvak wordt verplaatst tijdens perioden met weinig internetverkeer en weinig on-premises Exchange-gebruik.**</span><span class="sxs-lookup"><span data-stu-id="3fc06-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="3fc06-114">Wanneer de planning wordt verplaatst, worden migratieaanvragen verzonden naar de postvakreplicatieproxy en vinden ze mogelijk niet onmiddellijk plaats.</span><span class="sxs-lookup"><span data-stu-id="3fc06-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="3fc06-115">**Gebruik lean pop-outs voor de webversie van Outlook.**</span><span class="sxs-lookup"><span data-stu-id="3fc06-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="3fc06-116">Lean pop-outs bieden kleinere, minder geheugenintensieve versies van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer door bepaalde onderdelen op de server weer te geven.</span><span class="sxs-lookup"><span data-stu-id="3fc06-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="3fc06-117">Zie Lean pop-outs gebruiken om het geheugen te verminderen dat wordt gebruikt [bij het lezen van e-mailberichten](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3fc06-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="3fc06-118">Algemeen advies</span><span class="sxs-lookup"><span data-stu-id="3fc06-118">General advice</span></span>

- <span data-ttu-id="3fc06-119">Zorg ervoor dat DNS-opzoekactie outlook.office.com het MS-datacenter binnenkomt op een logische invoerlocatie voor uw locatie.</span><span class="sxs-lookup"><span data-stu-id="3fc06-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="3fc06-120">Zoek postvak caching en kies de juiste opties (opnieuw.</span><span class="sxs-lookup"><span data-stu-id="3fc06-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="3fc06-121">caching period, shared mailbox caching, et cetera).</span><span class="sxs-lookup"><span data-stu-id="3fc06-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="3fc06-122">Zorg ervoor dat uw Outlook-gegevens niet worden overgenomen via VPN-verbindingen (naar een centraal kantoor) voordat deze via internet worden overgenomen.</span><span class="sxs-lookup"><span data-stu-id="3fc06-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="3fc06-123">Zorg ervoor dat uw postvakgegevens voldoen aan de beperkingen voor map- en itembedragen.</span><span class="sxs-lookup"><span data-stu-id="3fc06-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="3fc06-124">Zie Office 365-migratieprestaties en -best practices voor meer informatie over de prestaties van [Exchange-migratie.](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57)</span><span class="sxs-lookup"><span data-stu-id="3fc06-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
