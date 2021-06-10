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
description: In dit artikel leert u hoe u uw aanwezigheid Microsoft 365 meerdere geografische regio's kunt uitbreiden met Microsoft 365 Multi-Geo.
ms.openlocfilehash: 2805470f1a35bb5978f3d25c30aa07523ad21afb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909548"
---
# <a name="microsoft-365-multi-geo"></a><span data-ttu-id="b3caf-103">Microsoft 365 Multi-Geo</span><span class="sxs-lookup"><span data-stu-id="b3caf-103">Microsoft 365 Multi-Geo</span></span>

<span data-ttu-id="b3caf-104">Met Microsoft 365 Multi-Geo kan uw organisatie de aanwezigheid van Microsoft 365 uitbreiden naar meerdere geografische regio's en/of landen binnen uw bestaande tenant.</span><span class="sxs-lookup"><span data-stu-id="b3caf-104">With Microsoft 365 Multi-Geo, your organization can expand its Microsoft 365 presence to multiple geographic regions and/or countries within your existing tenant.</span></span> <span data-ttu-id="b3caf-105">Contact op met uw Microsoft-accountteam om uw multi-national company te registreren voor Microsoft 365 Multi-Geo.</span><span class="sxs-lookup"><span data-stu-id="b3caf-105">Reach out to your Microsoft Account Team to sign up your Multi-National Company for Microsoft 365 Multi-Geo.</span></span>
  
<span data-ttu-id="b3caf-106">Met Microsoft 365 Multi-Geo kunt u gegevens inrichten en opslaan op de geolocaties die u hebt gekozen om te voldoen aan de vereisten voor gegevensopslag en tegelijkertijd uw globale implementatie van moderne productiviteitservaringen voor uw werknemers ontgrendelen.</span><span class="sxs-lookup"><span data-stu-id="b3caf-106">With Microsoft 365 Multi-Geo, you can provision and store data at rest in the geo locations that you've chosen to meet data residency requirements, and at the same time unlock your global roll out of modern productivity experiences to your workforce.</span></span>

<span data-ttu-id="b3caf-107">Voor een video-inleiding tot Microsoft 365 Multi-Geo, zie SharePoint Online en OneDrive Multi-Geo om te bepalen waar uw [gegevens zich bevinden.](https://www.youtube.com/watch?v=Do9U3JuROhk)</span><span class="sxs-lookup"><span data-stu-id="b3caf-107">For a video introduction to Microsoft 365 Multi-Geo, see [SharePoint Online and OneDrive Multi-Geo to control where your data resides](https://www.youtube.com/watch?v=Do9U3JuROhk).</span></span>

## <a name="multi-geo-architecture"></a><span data-ttu-id="b3caf-108">Architectuur met meerdere geo's</span><span class="sxs-lookup"><span data-stu-id="b3caf-108">Multi-Geo architecture</span></span>

<span data-ttu-id="b3caf-109">In een Multi-Geo-omgeving bestaat Microsoft 365 tenant uit een centrale locatie (waar uw Microsoft 365-abonnement oorspronkelijk is ingericht) en een of meer satellietlocaties.</span><span class="sxs-lookup"><span data-stu-id="b3caf-109">In a Multi-Geo environment, your Microsoft 365 tenant consists of a central location (where your Microsoft 365 subscription was originally provisioned) and one or more satellite locations.</span></span> <span data-ttu-id="b3caf-110">In een multi-geo tenant wordt de informatie over geografische locaties, groepen en gebruikersgegevens beheerst in Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="b3caf-110">In a multi-geo tenant, the information about geo locations, groups, and user information, is mastered in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="b3caf-111">Omdat uw tenantgegevens centraal worden gemodelleerd en gesynchroniseerd naar elke geografische locatie, bevatten delen en ervaringen met iedereen uit uw bedrijf globale bekendheid.</span><span class="sxs-lookup"><span data-stu-id="b3caf-111">Because your tenant information is mastered centrally and synchronized into each geo location, sharing and experiences involving anyone from your company contain global awareness.</span></span>

![Schermafbeelding van multi-geomap vanuit het SharePoint beheercentrum](../media/multi-geo-world-map.png)

<span data-ttu-id="b3caf-113">Houd er rekening Microsoft 365 Multi-Geo niet is ontworpen voor prestatieoptimalisatie, maar is ontworpen om te voldoen aan de vereisten voor gegevenslocatie.</span><span class="sxs-lookup"><span data-stu-id="b3caf-113">Note that Microsoft 365 Multi-Geo is not designed for performance optimization, it is designed to meet data residency requirements.</span></span> <span data-ttu-id="b3caf-114">Zie Netwerkplanning en prestatieafstemming voor Microsoft 365 voor meer informatie over prestatieoptimalisatie voor Microsoft 365 [of](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) neem contact op met uw ondersteuningsgroep.</span><span class="sxs-lookup"><span data-stu-id="b3caf-114">For information about performance optimization for Microsoft 365, see [Network planning and performance tuning for Microsoft 365](https://support.office.com/article/e5f1228c-da3c-4654-bf16-d163daee8848) or contact your support group.</span></span>

## <a name="terminology"></a><span data-ttu-id="b3caf-115">Terminologie</span><span class="sxs-lookup"><span data-stu-id="b3caf-115">Terminology</span></span>

<span data-ttu-id="b3caf-116">Hier zijn de belangrijkste termen die worden gebruikt bij het beschrijven Microsoft 365 Multi-Geo:</span><span class="sxs-lookup"><span data-stu-id="b3caf-116">Here are the key terms used in describing Microsoft 365 Multi-Geo:</span></span>

- <span data-ttu-id="b3caf-117">**Centrale locatie:** de geografische locatie waar de tenant oorspronkelijk is ingericht.</span><span class="sxs-lookup"><span data-stu-id="b3caf-117">**Central location** - the geo location where your tenant was originally provisioned.</span></span>
- <span data-ttu-id="b3caf-118">**Geobeheerder:** een beheerder die een of meer opgegeven satellietlocaties kan beheren.</span><span class="sxs-lookup"><span data-stu-id="b3caf-118">**Geo administrator** - An administrator who can administer one or more specified satellite locations.</span></span>
- <span data-ttu-id="b3caf-119">**Geocode:** een code met drie letters voor een bepaalde geografische locatie.</span><span class="sxs-lookup"><span data-stu-id="b3caf-119">**Geo code** - a three-letter code for a given geo location.</span></span>
- <span data-ttu-id="b3caf-120">**Geografische locatie:** een geografische locatie die kan worden gebruikt in een multi-geotenator voor het hosten van gegevens, Exchange postvakken en OneDrive en SharePoint sites.</span><span class="sxs-lookup"><span data-stu-id="b3caf-120">**Geo location** – A geographic location that can be used in a multi-geo tenant to host data, including Exchange mailboxes and OneDrive and SharePoint sites.</span></span>
- <span data-ttu-id="b3caf-121">**Voorkeurslocatie voor gegevens (PDL)** : een eigenschap van de gebruiker die is ingesteld door de beheerder die aangeeft waar de geografische locatie waar de gebruikers Exchange postvak en OneDrive moeten worden ingericht.</span><span class="sxs-lookup"><span data-stu-id="b3caf-121">**Preferred Data Location (PDL)** – A user property set by the administrator that indicates where the geo location where the users Exchange mailbox and OneDrive should be provisioned.</span></span> <span data-ttu-id="b3caf-122">De PDL bepaalt ook waar SharePoint sites die door de gebruiker zijn gemaakt, zijn ingericht.</span><span class="sxs-lookup"><span data-stu-id="b3caf-122">The PDL also determines where SharePoint sites that are created by the user are provisioned.</span></span>
- <span data-ttu-id="b3caf-123">**Satellietlocatie:** de geografische locaties waar de geo-aware Microsoft 365 workloads (SharePoint, OneDrive en Exchange) zijn ingeschakeld in een multi-geoten tenant.</span><span class="sxs-lookup"><span data-stu-id="b3caf-123">**Satellite location** – The geo locations where the geo-aware Microsoft 365 workloads (SharePoint, OneDrive, and Exchange) are enabled in a multi-geo tenant.</span></span>
- <span data-ttu-id="b3caf-124">**Tenant:** de vertegenwoordiging van een organisatie in Microsoft 365 waarbij meestal een of meer domeinen aan de tenant zijn gekoppeld (bijvoorbeeld contoso.com).</span><span class="sxs-lookup"><span data-stu-id="b3caf-124">**Tenant** – An organization's representation in Microsoft 365 which typically has one or more domains associated with it (for example, contoso.com).</span></span>

## <a name="licensing"></a><span data-ttu-id="b3caf-125">Licenties</span><span class="sxs-lookup"><span data-stu-id="b3caf-125">Licensing</span></span>

<span data-ttu-id="b3caf-126">Microsoft 365 Multi-Geo is beschikbaar als invoegabonnement op de volgende Microsoft 365-abonnementen voor Enterprise Agreement-klanten met minimaal 250 Microsoft 365-seats in hun tenant, en minimaal 5% van deze seats met multi-geo.</span><span class="sxs-lookup"><span data-stu-id="b3caf-126">Microsoft 365 Multi-Geo is available as an add-on to the following Microsoft 365 subscription plans for Enterprise Agreement customers with a minimum of 250 Microsoft 365 seats in their tenant, and a minimum of 5% of those seats using multi-geo.</span></span> <span data-ttu-id="b3caf-127">Gebruikersabonnementslicenties moeten op dezelfde Enterprise Agreement als de Multi-Geo Services-licenties.</span><span class="sxs-lookup"><span data-stu-id="b3caf-127">User subscription licenses must be on the same Enterprise Agreement as the Multi-Geo Services licenses.</span></span> <span data-ttu-id="b3caf-128">Neem contact op met uw Microsoft-accountteam voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3caf-128">Please contact your Microsoft account team for details.</span></span>

- <span data-ttu-id="b3caf-129">Microsoft 365 F1, F3, E3 of E5</span><span class="sxs-lookup"><span data-stu-id="b3caf-129">Microsoft 365 F1, F3, E3, or E5</span></span>
- <span data-ttu-id="b3caf-130">Office 365 F3, E1, E3 of E5</span><span class="sxs-lookup"><span data-stu-id="b3caf-130">Office 365 F3, E1, E3, or E5</span></span>
- <span data-ttu-id="b3caf-131">Exchange Online Plan 1 of Plan 2</span><span class="sxs-lookup"><span data-stu-id="b3caf-131">Exchange Online Plan 1 or Plan 2</span></span>
- <span data-ttu-id="b3caf-132">OneDrive voor Bedrijven Plan 1 of Plan 2</span><span class="sxs-lookup"><span data-stu-id="b3caf-132">OneDrive for Business Plan 1 or Plan 2</span></span>
- <span data-ttu-id="b3caf-133">SharePoint Online abonnement 1 of Abonnement 2</span><span class="sxs-lookup"><span data-stu-id="b3caf-133">SharePoint Online Plan 1 or Plan 2</span></span>

## <a name="microsoft-365-multi-geo-availability"></a><span data-ttu-id="b3caf-134">Microsoft 365 Beschikbaarheid van meerdere geo's</span><span class="sxs-lookup"><span data-stu-id="b3caf-134">Microsoft 365 Multi-Geo availability</span></span>

<span data-ttu-id="b3caf-135">Microsoft 365 Multi-Geo wordt momenteel aangeboden in deze regio's en landen:</span><span class="sxs-lookup"><span data-stu-id="b3caf-135">Microsoft 365 Multi-Geo is currently offered in these regions and countries:</span></span>

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="getting-started"></a><span data-ttu-id="b3caf-136">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="b3caf-136">Getting started</span></span>

<span data-ttu-id="b3caf-137">Volg de volgende stappen om aan de slag te gaan met multi-geo:</span><span class="sxs-lookup"><span data-stu-id="b3caf-137">Follow these steps to get started with multi-geo:</span></span>

1. <span data-ttu-id="b3caf-138">Werk samen met uw accountteam om de _Multi-Geo-mogelijkheden toe_ te voegen in Microsoft 365 serviceplan.</span><span class="sxs-lookup"><span data-stu-id="b3caf-138">Work with your account team to add the _Multi-Geo Capabilities in Microsoft 365_ service plan.</span></span> <span data-ttu-id="b3caf-139">Ze begeleiden u bij het toevoegen van het benodigde aantal licenties.</span><span class="sxs-lookup"><span data-stu-id="b3caf-139">They will guide you to add the number of licenses needed.</span></span> <span data-ttu-id="b3caf-140">Multi-Geo-functie is beschikbaar voor EA-klanten met een minimum van 250 Microsoft 365 abonnementen.</span><span class="sxs-lookup"><span data-stu-id="b3caf-140">Multi-Geo feature is available to EA customers with a minimum of 250 Microsoft 365 subscriptions.</span></span>

   <span data-ttu-id="b3caf-141">Voordat u kunt beginnen met Microsoft 365 Multi-Geo, moet Microsoft uw Exchange Online configureren voor multi-geo-ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="b3caf-141">Before you can start using Microsoft 365 Multi-Geo, Microsoft needs to configure your Exchange Online tenant for multi-geo support.</span></span> <span data-ttu-id="b3caf-142">Dit eendimensionale configuratieproces wordt geactiveerd nadat u de *Multi-Geo Capabilities hebt* Microsoft 365 serviceplan en de licenties worden in uw tenant.</span><span class="sxs-lookup"><span data-stu-id="b3caf-142">This one-time configuration process is triggered after you order the *Multi-Geo Capabilities in Microsoft 365* service plan and the licenses show up in your tenant.</span></span> <span data-ttu-id="b3caf-143">U ontvangt werkbelastingspecifieke meldingen [](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) in het Microsoft 365-berichtencentrum zodra uw tenant het configuratieproces voor elke werkbelasting heeft voltooid en u vervolgens kunt beginnen met het configureren en gebruiken van uw Microsoft 365 Multi-Geo-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="b3caf-143">You will receive workload-specific notifications in the [Microsoft 365 message center](https://support.office.com/article/38FB3333-BFCC-4340-A37B-DEDA509C2093) once your tenant has completed the configuration process for each workload, and you then may begin configuring and using your Microsoft 365 Multi-Geo capabilities.</span></span> <span data-ttu-id="b3caf-144">De tijd die nodig is voor het configureren van een tenant voor Multi-Geo-ondersteuning verschilt per tenant, maar de meeste tenants eindigen binnen een maand na ontvangst van de functielicenties.</span><span class="sxs-lookup"><span data-stu-id="b3caf-144">The time required to configure a tenant for Multi-Geo support varies from tenant to tenant, but most tenants finish within a month after receipt of the feature licenses.</span></span> <span data-ttu-id="b3caf-145">Grotere of complexere tenants hebben mogelijk meer tijd nodig om het configuratieproces te voltooien.</span><span class="sxs-lookup"><span data-stu-id="b3caf-145">Larger or more complex tenants may require more time to complete the configuration process.</span></span> <span data-ttu-id="b3caf-146">Neem contact op met uw accountteam voor meer informatie over uw specifieke tenant indien u dit nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="b3caf-146">Please contact your account team for details on your specific tenant should you require it.</span></span>

2. <span data-ttu-id="b3caf-147">Lees [Uw multi-geo-omgeving plannen.](plan-for-multi-geo.md)</span><span class="sxs-lookup"><span data-stu-id="b3caf-147">Read [Plan your multi-geo environment](plan-for-multi-geo.md).</span></span>

3. <span data-ttu-id="b3caf-148">Meer informatie [over het beheren van een multi-geo-omgeving](administering-a-multi-geo-environment.md) en hoe uw gebruikers de omgeving zullen [ervaren.](multi-geo-user-experience.md)</span><span class="sxs-lookup"><span data-stu-id="b3caf-148">Learn about [administering a multi-geo environment](administering-a-multi-geo-environment.md) and [how your users will experience the environment](multi-geo-user-experience.md).</span></span>

4. <span data-ttu-id="b3caf-149">Wanneer u klaar bent om de Microsoft 365 Multi-Geo in te stellen, configureert u [de tenant voor multi-geo.](multi-geo-tenant-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b3caf-149">When you are ready to set up Microsoft 365 Multi-Geo, [configure your tenant for multi-geo](multi-geo-tenant-configuration.md).</span></span>

5. <span data-ttu-id="b3caf-150">[Zoekactie instellen.](configure-search-for-multi-geo.md)</span><span class="sxs-lookup"><span data-stu-id="b3caf-150">[Set up search](configure-search-for-multi-geo.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b3caf-151">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b3caf-151">See also</span></span>

[<span data-ttu-id="b3caf-152">Multi-Geo in Exchange Online en OneDrive</span><span class="sxs-lookup"><span data-stu-id="b3caf-152">Multi-Geo in Exchange Online and OneDrive</span></span>](https://Aka.ms/GoMultiGeo)

[<span data-ttu-id="b3caf-153">Multi-Geo Capabilities in OneDrive en SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="b3caf-153">Multi-Geo Capabilities in OneDrive and SharePoint Online</span></span>](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md)

[<span data-ttu-id="b3caf-154">Multi-Geo Capabilities in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b3caf-154">Multi-Geo Capabilities in Exchange Online</span></span>](multi-geo-capabilities-in-exchange-online.md)

[<span data-ttu-id="b3caf-155">Teams ervaring in een multi-geo-omgeving</span><span class="sxs-lookup"><span data-stu-id="b3caf-155">Teams experience in a multi-geo environment</span></span>](/microsoftteams/teams-experience-o365odb-spo-multi-geo)