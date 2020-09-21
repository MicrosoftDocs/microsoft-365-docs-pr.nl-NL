---
title: Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: In dit artikel vindt u meer informatie over hoe u uw Microsoft 365-aanwezigheid uitbreidt naar meerdere geografische regio's met Microsoft 365 meerdere geografische regio's.
ms.openlocfilehash: 10f941549fd4899d5b3a14c97e6f301339702722
ms.sourcegitcommit: cd11588b47904c7d2ae899a9f5280f93d3850171
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/21/2020
ms.locfileid: "48171324"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="861a0-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="861a0-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="861a0-104">Met Microsoft 365 multi-geo kan uw organisatie zijn Microsoft 365-aanwezigheid uitbreiden naar meerdere geografische regio's en/of landen binnen de bestaande Tenant.</span><span class="sxs-lookup"><span data-stu-id="861a0-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="861a0-105">Neem contact op met uw Microsoft-account team om u aan te melden bij uw Microsoft-account team voor Microsoft 365-multi-geo.</span><span class="sxs-lookup"><span data-stu-id="861a0-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="861a0-106">Met Microsoft 365 in Microsoft kunt u gegevens inrichten en bewaren op de geografische locaties die u hebt gekozen om te voldoen aan de vereisten voor gegevens woonplaats, en tegelijk de wereldwijde samenvatting van de moderne productiviteitsfuncties voor uw werknemers ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="861a0-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="861a0-107">Voor een video-inleiding tot Microsoft 365 multi-geo raadpleegt [u SharePoint Online en OneDrive meerdere geografische locaties om te bepalen waar uw gegevens zich bevinden](https://www.youtube.com/watch?v=Do9U3JuROhk).</span><span class="sxs-lookup"><span data-stu-id="861a0-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="861a0-108">Meerdere geo-architecturen</span><span class="sxs-lookup"><span data-stu-id="861a0-108">Multi-Geo architecture</span></span>

<span data-ttu-id="861a0-109">In een omgeving met meerdere geografische gebieden bevat uw Microsoft 365-Tenant een centrale locatie (waarbij uw Microsoft 365-abonnement oorspronkelijk is ingericht) en een of meer satelliet locaties.</span><span class="sxs-lookup"><span data-stu-id="861a0-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="861a0-110">In een Tenant met meerdere geo-gebruikers wordt de informatie over geo-locaties, groepen en gebruikers informatie gemastereerd in azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="861a0-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="861a0-111">Omdat uw Tenant gegevens centraal zijn gemastereerd en worden gesynchroniseerd in elke geografische locatie, delen en ervaring waarbij iedereen van uw bedrijf wereldwijde informatie bevat.</span><span class="sxs-lookup"><span data-stu-id="861a0-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Schermafbeelding van een meervoudige geografische kaart in het SharePoint-Beheercentrum](../media/multi-geo-world-map.png)

<span data-ttu-id="861a0-113">Houd er rekening mee dat Microsoft 365 multi-geo niet is ontworpen voor prestatieoptimalisatie, zodat het voldoet aan de vereisten voor data woonplaats.</span><span class="sxs-lookup"><span data-stu-id="861a0-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="861a0-114">Zie [netwerk planning en prestaties optimaliseren voor Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) of neem contact op met de ondersteuningsgroep voor informatie over de prestaties optimaliseren voor microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="861a0-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="861a0-115">Terminologie</span><span class="sxs-lookup"><span data-stu-id="861a0-115">Terminology</span></span>

<span data-ttu-id="861a0-116">Dit zijn de belangrijkste voorwaarden die worden gebruikt in de basis van Microsoft 365 multi-geo:</span><span class="sxs-lookup"><span data-stu-id="861a0-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="861a0-117">**Centrale locatie** : de geografische locatie waar de Tenant oorspronkelijk werd ingericht.</span><span class="sxs-lookup"><span data-stu-id="861a0-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="861a0-118">**Geo-beheerder** : een beheerder die een of meer van de opgegeven satelliet locaties kan beheren.</span><span class="sxs-lookup"><span data-stu-id="861a0-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="861a0-119">**Geo code** : een code van drie letters voor een bepaalde geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="861a0-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="861a0-120">**Geo-locatie** : een geografische locatie die kan worden gebruikt in een Tenant met meerdere geo-hosting voor het hosten van gegevens, inclusief Exchange-postvakken en OneDrive-en SharePoint-sites.</span><span class="sxs-lookup"><span data-stu-id="861a0-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="861a0-121">**Voorkeurs gegevenslocatie (PDL)** : een gebruikerseigenschap die is ingesteld door de beheerder, die aangeeft waar de geografische locatie zich bevindt waar de gebruikers van het Exchange-postvak en de OneDrive moeten worden ingericht.</span><span class="sxs-lookup"><span data-stu-id="861a0-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="861a0-122">Met de PDL wordt ook bepaald waar SharePoint-sites die zijn gemaakt door de gebruiker, worden ingericht.</span><span class="sxs-lookup"><span data-stu-id="861a0-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="861a0-123">**Locatie van satelliet** : de geografische locaties waar het microsoft 365-werkbelasting van microsoft (SharePoint, OneDrive en Exchange) is ingeschakeld in een Tenant van meerdere geo.</span><span class="sxs-lookup"><span data-stu-id="861a0-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="861a0-124">**Tenant** : de representatie van een organisatie in microsoft 365 waaraan meestal een of meer domeinen zijn gekoppeld (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="861a0-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="861a0-125">Licenties</span><span class="sxs-lookup"><span data-stu-id="861a0-125">Licensing</span></span>

<span data-ttu-id="861a0-126">Microsoft 365 multi-geo is beschikbaar als een invoegtoepassing voor de volgende Microsoft 365-abonnementen voor EA-klanten met een minimum van 250 Microsoft 365 seats in hun Tenant, en minimaal 5% van deze stoelen met meerdere geografische versies.</span><span class="sxs-lookup"><span data-stu-id="861a0-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for EA customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="861a0-127">Neem contact op met uw Microsoft-accountteam voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="861a0-127">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="861a0-128">Microsoft 365 F1, E1, E3 of E5</span><span class="sxs-lookup"><span data-stu-id="861a0-128">Microsoft 365 F1, E1, E3, or E5</span></span>
- <span data-ttu-id="861a0-129">Exchange Online abonnement 1 of abonnement 2</span><span class="sxs-lookup"><span data-stu-id="861a0-129">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="861a0-130">OneDrive voor bedrijven abonnement 1 of abonnement 2</span><span class="sxs-lookup"><span data-stu-id="861a0-130">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="861a0-131">SharePoint Online, abonnement 1 of abonnement 2</span><span class="sxs-lookup"><span data-stu-id="861a0-131">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="861a0-132">Microsoft 365 multi-geografische beschikbaarheid</span><span class="sxs-lookup"><span data-stu-id="861a0-132">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="861a0-133">Microsoft 365 multi-geo wordt momenteel aangeboden in deze regio's en landen:</span><span class="sxs-lookup"><span data-stu-id="861a0-133">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="861a0-134">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="861a0-134">Getting started</span></span>

<span data-ttu-id="861a0-135">Voer de volgende stappen uit om aan de slag te gaan met meerdere geo:</span><span class="sxs-lookup"><span data-stu-id="861a0-135">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="861a0-136">Werk samen met uw accountteam om de mogelijkheden voor meervoudige geo toe te voegen _in Microsoft 365_ serviceplan.</span><span class="sxs-lookup"><span data-stu-id="861a0-136">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="861a0-137">U kunt nu het aantal benodigde licenties toevoegen.</span><span class="sxs-lookup"><span data-stu-id="861a0-137">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="861a0-138">Meervoudige geo-functie is beschikbaar voor EA-klanten met een minimum van een 250 Microsoft 365-abonnement.</span><span class="sxs-lookup"><span data-stu-id="861a0-138">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="861a0-139">Voordat u Microsoft 365 multi-geo kunt gaan gebruiken, moet Microsoft uw Exchange Online-Tenant configureren voor ondersteuning via meerdere geo.</span><span class="sxs-lookup"><span data-stu-id="861a0-139">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="861a0-140">Dit eenmalige configuratieproces wordt geactiveerd wanneer u de *mogelijkheden voor meerdere geografische locaties in Microsoft 365* serviceplan hebt gesorteerd en de licenties worden weergegeven in de Tenant.</span><span class="sxs-lookup"><span data-stu-id="861a0-140">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="861a0-141">U ontvangt specifieke meldingen van de werkbelasting in het [Microsoft 365-berichtencentrum](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) wanneer uw Tenant het configuratieproces voor elke werkbelasting heeft voltooid en u vervolgens de mogelijkheden van microsoft 365 multi-geo kunt configureren en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="861a0-141">You will receive workload specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="861a0-142">De tijd die nodig is voor het configureren van een Tenant voor ondersteuning met meerdere Geografischen verschilt per Tenant naar Tenant, maar de meeste tenants voltooien binnen een maand na ontvangst van de functie licenties.</span><span class="sxs-lookup"><span data-stu-id="861a0-142">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="861a0-143">Voor grotere of complexere tenants is meer tijd nodig om het configuratieproces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="861a0-143">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="861a0-144">Neem contact op met uw accountteam voor meer informatie over uw specifieke Tenant.</span><span class="sxs-lookup"><span data-stu-id="861a0-144">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="861a0-145">Lees [de omgeving voor meerdere geografische omgevingen plannen](plan-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="861a0-145">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="861a0-146">Meer informatie over het [beheren van een omgeving met meerdere geografische omgevingen](administering-a-multi-geo-environment.md) en [de manier waarop gebruikers de omgeving kunnen ervaren](multi-geo-user-experience.md).</span><span class="sxs-lookup"><span data-stu-id="861a0-146">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="861a0-147">Wanneer u klaar bent om Microsoft 365 multi-geo in te stellen, [configureert u uw Tenant voor meervoudige geo](multi-geo-tenant-configuration.md).</span><span class="sxs-lookup"><span data-stu-id="861a0-147">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="861a0-148">[Zoekopdracht instellen](configure-search-for-multi-geo.md).</span><span class="sxs-lookup"><span data-stu-id="861a0-148">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="861a0-149">Zie ook</span><span class="sxs-lookup"><span data-stu-id="861a0-149">See also</span></span>

[<span data-ttu-id="861a0-150">Meerdere geografische locaties in Exchange Online en OneDrive</span><span class="sxs-lookup"><span data-stu-id="861a0-150">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="861a0-151">Mogelijkheden voor meervoudige geo in OneDrive en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="861a0-151">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="861a0-152">Mogelijkheden voor meervoudige geo in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="861a0-152">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="861a0-153">Teams-ervaring in een omgeving met meerdere geografische locaties</span><span class="sxs-lookup"><span data-stu-id="861a0-153">Teams experience in a multi-geo environment</span></span>](https://docs.microsoft.com/microsoftteams/teams-experience-o365odb-spo-multi-geo)
