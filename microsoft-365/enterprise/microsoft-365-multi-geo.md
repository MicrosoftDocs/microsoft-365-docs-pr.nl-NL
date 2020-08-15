---
title: Microsoft 365 multi-geografische
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: In dit artikel vindt u meer informatie over hoe u uw Microsoft 365-aanwezigheid uitbreidt naar meerdere geografische regio's met Microsoft 365 meerdere geografische regio's.
ms.openlocfilehash: a5843b98b5d64dfb3872c3d8a5d48c0e56949c02
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689376"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="74788-103">Microsoft 365 multi-geografische</span><span class="sxs-lookup"><span data-stu-id="74788-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="74788-104">Met Microsoft 365 multi-geo kan uw organisatie zijn Microsoft 365-aanwezigheid uitbreiden naar meerdere geografische regio's en/of landen binnen de bestaande Tenant.</span><span class="sxs-lookup"><span data-stu-id="74788-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="74788-105">Neem contact op met uw Microsoft-account team om u aan te melden bij uw Microsoft-account team voor Microsoft 365-multi-geo.</span><span class="sxs-lookup"><span data-stu-id="74788-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="74788-106">Met Microsoft 365 in Microsoft kunt u gegevens inrichten en bewaren op de geografische locaties die u hebt gekozen om te voldoen aan de vereisten voor gegevens woonplaats, en tegelijk de wereldwijde samenvatting van de moderne productiviteitsfuncties voor uw werknemers ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="74788-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

#### <a name="video-introducing-microsoft-365-multi-geo"></a><span data-ttu-id="74788-107">Video: Inleiding tot Microsoft 365 multi-geo</span><span class="sxs-lookup"><span data-stu-id="74788-107">Video: Introducing Microsoft 365 Multi-Geo</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1Yk6B?autoplay=false]

<span data-ttu-id="74788-108">In een omgeving met meerdere geografische gebieden bevat uw Microsoft 365-Tenant een centrale locatie (waarbij uw Microsoft 365-abonnement oorspronkelijk is ingericht) en een of meer satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="74788-108">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="74788-109">In een Tenant met meerdere geo-gebruikers wordt de informatie over geo-locaties, groepen en gebruikers informatie gemastereerd in azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="74788-109">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="74788-110">Omdat uw Tenant gegevens centraal zijn gemastereerd en worden gesynchroniseerd in elke geografische locatie, delen en ervaring waarbij iedereen van uw bedrijf wereldwijde informatie bevat.</span><span class="sxs-lookup"><span data-stu-id="74788-110">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Schermafbeelding van een meervoudige geografische kaart in het SharePoint-Beheercentrum](../media/multi-geo-world-map.png)

<span data-ttu-id="74788-112">Houd er rekening mee dat Microsoft 365 multi-geo niet is ontworpen voor prestatieoptimalisatie, zodat het voldoet aan de vereisten voor data woonplaats.</span><span class="sxs-lookup"><span data-stu-id="74788-112">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="74788-113">Zie [netwerk planning en prestaties optimaliseren voor Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) of neem contact op met de ondersteuningsgroep voor informatie over de prestaties optimaliseren voor microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="74788-113">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="74788-114">Terminologie</span><span class="sxs-lookup"><span data-stu-id="74788-114">Terminology</span></span>

<span data-ttu-id="74788-115">Dit zijn de belangrijkste voorwaarden die worden gebruikt in de basis van Microsoft 365 multi-geo:</span><span class="sxs-lookup"><span data-stu-id="74788-115">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="74788-116">**Centrale locatie** : de geografische locatie waar de Tenant oorspronkelijk werd ingericht.</span><span class="sxs-lookup"><span data-stu-id="74788-116">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="74788-117">**Geo-beheerder** : een beheerder die een of meer van de opgegeven satelliet locaties kan beheren.</span><span class="sxs-lookup"><span data-stu-id="74788-117">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="74788-118">**Geo code** : een code van drie letters voor een bepaalde geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="74788-118">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="74788-119">**Geo-locatie** : een geografische locatie die kan worden gebruikt in een Tenant met meerdere geo-hosting voor het hosten van gegevens, inclusief Exchange-postvakken en OneDrive-en SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="74788-119">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="74788-120">**Voorkeurs gegevenslocatie (PDL)** : een gebruikerseigenschap die is ingesteld door de beheerder, die aangeeft waar de geografische locatie zich bevindt waar de gebruikers van het Exchange-postvak en de OneDrive moeten worden ingericht.</span><span class="sxs-lookup"><span data-stu-id="74788-120">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="74788-121">Met de PDL wordt ook bepaald waar SharePoint-sites die zijn gemaakt door de gebruiker, worden ingericht.</span><span class="sxs-lookup"><span data-stu-id="74788-121">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="74788-122">**Locatie van satelliet** : de geografische locaties waar het microsoft 365-werkbelasting van microsoft (SharePoint, OneDrive en Exchange) is ingeschakeld in een Tenant van meerdere geo.</span><span class="sxs-lookup"><span data-stu-id="74788-122">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="74788-123">**Tenant** : de representatie van een organisatie in microsoft 365 waaraan meestal een of meer domeinen zijn gekoppeld (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="74788-123">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="74788-124">Licenties</span><span class="sxs-lookup"><span data-stu-id="74788-124">Licensing</span></span>

<span data-ttu-id="74788-125">Microsoft 365 multi-geo is beschikbaar als een invoegtoepassing voor de volgende Microsoft 365-abonnementen voor EA-klanten met een minimum van 250 Microsoft 365 seats in hun Tenant, en minimaal 5% van deze stoelen met meerdere geografische versies.</span><span class="sxs-lookup"><span data-stu-id="74788-125">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="74788-126">Neem contact op met uw Microsoft-accountteam voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="74788-126">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="74788-127">Microsoft 365 F1, E1, E3 of E5</span><span class="sxs-lookup"><span data-stu-id="74788-127">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="74788-128">Exchange Online abonnement 1 of abonnement 2</span><span class="sxs-lookup"><span data-stu-id="74788-128">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="74788-129">OneDrive voor bedrijven abonnement 1 of abonnement 2</span><span class="sxs-lookup"><span data-stu-id="74788-129">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="74788-130">SharePoint Online, abonnement 1 of abonnement 2</span><span class="sxs-lookup"><span data-stu-id="74788-130">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="74788-131">Microsoft 365 multi-geografische beschikbaarheid</span><span class="sxs-lookup"><span data-stu-id="74788-131">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="74788-132">Microsoft 365 multi-geo wordt momenteel aangeboden in deze regio's en landen:</span><span class="sxs-lookup"><span data-stu-id="74788-132">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="74788-133">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="74788-133">Getting started</span></span>

<span data-ttu-id="74788-134">Voer de volgende stappen uit om aan de slag te gaan met meerdere geo:</span><span class="sxs-lookup"><span data-stu-id="74788-134">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="74788-135">Werk samen met uw accountteam om de mogelijkheden voor meervoudige geo toe te voegen _in Microsoft 365_ serviceplan.</span><span class="sxs-lookup"><span data-stu-id="74788-135">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="74788-136">U kunt nu het aantal benodigde licenties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="74788-136">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="74788-137">Meervoudige geo-functie is beschikbaar voor EA-klanten met een minimum van een 250 Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="74788-137">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="74788-138">Voordat u Microsoft 365 multi-geo kunt gaan gebruiken, moet Microsoft uw Exchange Online-Tenant configureren voor ondersteuning via meerdere geo.</span><span class="sxs-lookup"><span data-stu-id="74788-138">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="74788-139">Dit eenmalige configuratieproces wordt geactiveerd wanneer u de *mogelijkheden voor meerdere geografische locaties in Microsoft 365* serviceplan hebt gesorteerd en de licenties worden weergegeven in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="74788-139">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="74788-140">U ontvangt een melding in het [berichtencentrum van Microsoft 365](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) wanneer u de licenties voor meerdere geografische licenties toepast en u vervolgens de mogelijkheden van microsoft 365 multi-geo kunt configureren en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="74788-140">You'll receive notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your Multi-Geo licenses are applied and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span>

2. <span data-ttu-id="74788-141">Lees [de omgeving voor meerdere geografische omgevingen plannen](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="74788-141">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="74788-142">Meer informatie over het [beheren van een omgeving met meerdere geografische omgevingen](administering-a-multi-geo-environment.md) en [de manier waarop gebruikers de omgeving kunnen ervaren](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="74788-142">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="74788-143">Wanneer u klaar bent om Microsoft 365 multi-geo in te stellen, [configureert u uw Tenant voor meervoudige geo](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="74788-143">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="74788-144">[Zoekopdracht instellen](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="74788-144">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="74788-145">Zie ook</span><span class="sxs-lookup"><span data-stu-id="74788-145">See also</span></span>

[<span data-ttu-id="74788-146">Meerdere geografische locaties in Exchange Online en OneDrive</span><span class="sxs-lookup"><span data-stu-id="74788-146">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="74788-147">Mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="74788-147">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="74788-148">Mogelijkheden voor meervoudige geo in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="74788-148">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="74788-149">Teams-ervaring in een omgeving met meerdere geografische locaties</span><span class="sxs-lookup"><span data-stu-id="74788-149">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
