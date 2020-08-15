---
title: Prestaties van Exchange Online afstemmen
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
description: Dit artikel bevat algemene tips en koppelingen naar andere informatiebronnen over het verbeteren van de prestaties van Exchange Online.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689389"
---
# <a name="tune-exchange-online-performance"></a><span data-ttu-id="7f998-103">Prestaties van Exchange Online afstemmen</span><span class="sxs-lookup"><span data-stu-id="7f998-103">Tune Exchange Online performance</span></span>

<span data-ttu-id="7f998-104">Dit artikel bevat algemene tips en koppelingen naar andere informatiebronnen over het verbeteren van de prestaties van Exchange Online, met name vóór een migratie.</span><span class="sxs-lookup"><span data-stu-id="7f998-104">This article contains general tips and links to other resources that tell you how to improve performance of Exchange Online, particularly in front of a migration.</span></span> <span data-ttu-id="7f998-105">Dit artikel maakt deel uit van het project [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune) .</span><span class="sxs-lookup"><span data-stu-id="7f998-105">This article is part of the [Network planning and performance tuning for Office 365](https://aka.ms/tune) project.</span></span>
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a><span data-ttu-id="7f998-106">Aandachtspunten om de prestaties van Exchange Online te verbeteren</span><span class="sxs-lookup"><span data-stu-id="7f998-106">Things to consider in order to improve Exchange Online performance</span></span>

<span data-ttu-id="7f998-107">Als u de migratie snelheid wilt verbeteren en de bandbreedte beperkingen van uw organisatie voor Exchange Online wilt beperken, kunt u het volgende overwegen:</span><span class="sxs-lookup"><span data-stu-id="7f998-107">To improve the speed of migration and reduce your organization's bandwidth constraints for Exchange Online, consider the following:</span></span>
  
- <span data-ttu-id="7f998-108">**De grootte van het postvak verkleinen.**</span><span class="sxs-lookup"><span data-stu-id="7f998-108">**Reduce mailbox sizes.**</span></span> <span data-ttu-id="7f998-109">Kleinere postvakgrootte zorgt voor een betere migratie snelheid.</span><span class="sxs-lookup"><span data-stu-id="7f998-109">Smaller mailbox size improves migration speed.</span></span> 
    
- <span data-ttu-id="7f998-110">**Gebruik de mogelijkheden van Postvak verplaatsen met een hybride implementatie van Exchange.**</span><span class="sxs-lookup"><span data-stu-id="7f998-110">**Use the mailbox move capabilities with an Exchange hybrid deployment.**</span></span> <span data-ttu-id="7f998-111">Met een hybride Exchange-implementatie, offline mail (in de vorm van). De OST-bestanden zijn opnieuw te downloaden wanneer u de migratie naar Exchange Online uitvoert.</span><span class="sxs-lookup"><span data-stu-id="7f998-111">With an Exchange hybrid deployment, offline mail (in the form of .OST files) does not require re-download when migrating to Exchange Online.</span></span> <span data-ttu-id="7f998-112">Dit vermindert de vereisten voor het downloaden van de bandbreedte.</span><span class="sxs-lookup"><span data-stu-id="7f998-112">This significantly reduces your download bandwidth requirements.</span></span> 
    
- <span data-ttu-id="7f998-113">**Gepland postvak wordt verplaatst tijdens perioden van een laag Internet verkeer en een on-premises Exchange-gebruik.**</span><span class="sxs-lookup"><span data-stu-id="7f998-113">**Schedule mailbox moves to occur during periods of low Internet traffic and low on-premises Exchange use.**</span></span> <span data-ttu-id="7f998-114">Bij het plannen van verplaatsingsopdrachten worden de migratie verzoeken verzonden naar de proxy voor de Postvak replicatie en mogelijk niet onmiddellijk.</span><span class="sxs-lookup"><span data-stu-id="7f998-114">When scheduling moves, migration requests are submitted to the mailbox replication proxy and may not take place immediately.</span></span> 
    
- <span data-ttu-id="7f998-115">**De webversie van popouts gebruiken voor de webversie van Outlook.**</span><span class="sxs-lookup"><span data-stu-id="7f998-115">**Use lean popouts for Outlook on the web.**</span></span> <span data-ttu-id="7f998-116">Met popouts kunt u kleinere en minder geheugen intensiefere versies van bepaalde e-mailberichten in Microsoft Edge of Internet Explorer weergeven door sommige onderdelen op de server weer te geven.</span><span class="sxs-lookup"><span data-stu-id="7f998-116">Lean popouts provide smaller, less memory-intensive versions of certain email messages in Microsoft Edge or Internet Explorer by rendering some components on the server.</span></span> <span data-ttu-id="7f998-117">Zie voor meer informatie [het artikel Popouts gebruiken om geheugen te verminderen voor het lezen van e-mailberichten](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span><span class="sxs-lookup"><span data-stu-id="7f998-117">For more information, see [Use lean popouts to reduce memory used when reading mail messages](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).</span></span>


## <a name="general-advice"></a><span data-ttu-id="7f998-118">Algemeen advies</span><span class="sxs-lookup"><span data-stu-id="7f998-118">General advice</span></span>

- <span data-ttu-id="7f998-119">Zorg ervoor dat DNS-zoekopdracht voor outlook.office.com het MS-datacenter plaats voert op een logische invoerlocatie voor uw locatie.</span><span class="sxs-lookup"><span data-stu-id="7f998-119">Make certain that DNS lookup for outlook.office.com enters the MS-datacenter at a logical entry location for your location.</span></span>

- <span data-ttu-id="7f998-120">Onderzoek postvak cache voor onderzoek en kies de gewenste opties (opnieuw).</span><span class="sxs-lookup"><span data-stu-id="7f998-120">Research mailbox caching and choose the appropriate options (re.</span></span> <span data-ttu-id="7f998-121">cache periode, gedeelde Postvak cache, et enzovoort tot).</span><span class="sxs-lookup"><span data-stu-id="7f998-121">caching period, shared mailbox caching, et cetera).</span></span>

- <span data-ttu-id="7f998-122">Zorg dat uw Outlook-gegevens worden overgezet via VPN-verbindingen (naar een centrale Office) voordat u ze via internet plaatst.</span><span class="sxs-lookup"><span data-stu-id="7f998-122">Keep your Outlook data from passing over VPN connections (to a central office) before it goes over the Internet.</span></span>

- <span data-ttu-id="7f998-123">Zorg ervoor dat uw postvakgegevens voldoen aan de beperkingen voor de map en het item, de bedragen.</span><span class="sxs-lookup"><span data-stu-id="7f998-123">Be sure your mailbox data adheres to the limitations on folder, and item, amounts.</span></span>
    
<span data-ttu-id="7f998-124">Zie voor meer informatie over de prestaties van de Exchange-migratie de [migratie prestaties en aanbevolen procedures voor Office 365](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span><span class="sxs-lookup"><span data-stu-id="7f998-124">For more information about Exchange migration performance, see [Office 365 migration performance and best practices](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).</span></span>
  

