---
title: Limieten voor bewaarbeleid en retentielabelbeleid
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Meer informatie over het maximum aantal beleidsregels en items per beleid voor bewaarbeleid en bewaarlabelbeleid
ms.openlocfilehash: 007ca6eec50b243e1b820938ffa67553d7882c7b
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52162868"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a><span data-ttu-id="3044b-103">Limieten voor bewaarbeleid en retentielabelbeleid</span><span class="sxs-lookup"><span data-stu-id="3044b-103">Limits for retention policies and retention label policies</span></span>

><span data-ttu-id="3044b-104">*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="3044b-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="3044b-105">Als u [bewaarbeleid en retentielabelbeleid](retention.md#retention-policies-and-retention-labels) gebruikt om gegevens automatisch te behouden of verwijderen voor uw organisatie, moet u rekening houden met deze limieten.</span><span class="sxs-lookup"><span data-stu-id="3044b-105">When you use [retention policies and retention label policies](retention.md#retention-policies-and-retention-labels) to automatically retain or delete data for your organization, there are some maximum numbers to be aware of.</span></span>

## <a name="maximum-number-of-policies-per-tenant"></a><span data-ttu-id="3044b-106">Maximaal aantal gebruikers per tenant</span><span class="sxs-lookup"><span data-stu-id="3044b-106">Maximum number of policies per tenant</span></span>

<span data-ttu-id="3044b-107">Een enkele tenant kan maximaal 10.000 beleidsregels hebben (in iedere configuratie).</span><span class="sxs-lookup"><span data-stu-id="3044b-107">A single tenant can have a maximum of 10,000 policies (any configuration).</span></span> <span data-ttu-id="3044b-108">Binnen dit maximale aantal vallen ook de verschillende beleidsregels voor retentie en andere beleidsregels voor compliance, zoals DLP-beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="3044b-108">This maximum number includes the different policies for retention and other policies for compliance, such as DLP policies.</span></span>

<span data-ttu-id="3044b-109">Maximale aantal beleidsregels voor retentie per workload:</span><span class="sxs-lookup"><span data-stu-id="3044b-109">Maximum number of policies for retention per workload:</span></span>

- <span data-ttu-id="3044b-110">Exchange Online (in iedere configuratie): 1.800</span><span class="sxs-lookup"><span data-stu-id="3044b-110">Exchange Online (any configuration): 1,800</span></span>
- <span data-ttu-id="3044b-111">SharePoint of OneDrive: (alle sites automatisch inbegrepen): 13</span><span class="sxs-lookup"><span data-stu-id="3044b-111">SharePoint or OneDrive: (all sites automatically included): 13</span></span>
- <span data-ttu-id="3044b-112">SharePoint of OneDrive (specifieke locaties inbegrepen of uitgesloten): 2.600</span><span class="sxs-lookup"><span data-stu-id="3044b-112">SharePoint or OneDrive (specific locations included or excluded): 2,600</span></span>

## <a name="maximum-number-of-items-per-policy"></a><span data-ttu-id="3044b-113">Maximale aantal items per beleidsregel</span><span class="sxs-lookup"><span data-stu-id="3044b-113">Maximum number of items per policy</span></span>

<span data-ttu-id="3044b-114">Als u de optionele configuratie gebruikt om uw bewaarinstellingen te beperken tot specifieke gebruikers, specifieke Microsoft 365-groepen, of specifieke sites, moet u rekening houden met deze limieten per beleidsregel:</span><span class="sxs-lookup"><span data-stu-id="3044b-114">If you use the optional configuration to scope your retention settings to specific users, specific Microsoft 365 groups, or specific sites, there are some limits per policy to be aware of:</span></span> 

<span data-ttu-id="3044b-115">Maximale aantal items per beleidsregel voor retentie:</span><span class="sxs-lookup"><span data-stu-id="3044b-115">Maximum numbers of items per policy for retention:</span></span>

  - <span data-ttu-id="3044b-116">1.000 postvakken (gebruikerspostvakken of groepspostvakken)</span><span class="sxs-lookup"><span data-stu-id="3044b-116">1,000 mailboxes (user mailboxes or group mailboxes)</span></span>
  - <span data-ttu-id="3044b-117">1.000 Microsoft 365-groepen</span><span class="sxs-lookup"><span data-stu-id="3044b-117">1,000 Microsoft 365 groups</span></span>
  - <span data-ttu-id="3044b-118">1.000 gebruikers voor privéchats in Teams</span><span class="sxs-lookup"><span data-stu-id="3044b-118">1,000 users for Teams private chats</span></span>
  - <span data-ttu-id="3044b-119">100 sites (OneDrive of SharePoint)</span><span class="sxs-lookup"><span data-stu-id="3044b-119">100 sites (OneDrive or SharePoint)</span></span>

<span data-ttu-id="3044b-120">Omdat deze limieten per beleid gelden, moet u mogelijk specifieke items opnemen of uitsluiten, waardoor u de limiet overschijdt. In dat geval kunt u aanvullende beleidsregels maken die dezelfde bewaarinstellingen hebben.</span><span class="sxs-lookup"><span data-stu-id="3044b-120">Because these limitations are per policy, if you need to use specific inclusions or exclusions that result in going over these numbers, you can create additional policies that have the same retention settings.</span></span> <span data-ttu-id="3044b-121">Zie de volgende sectie voor [voorbeelden van scenario's en oplossingen](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) waarin om deze reden meerdere bewaarbeleidsregels zijn gebruikt.</span><span class="sxs-lookup"><span data-stu-id="3044b-121">See the next section for some [example scenarios and solutions](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) that use multiple retention policies for this reason.</span></span>

<span data-ttu-id="3044b-122">Meerdere beleidsregels zorgen wel voor hogere administratiekosten, dus controleer altijd of u specifieke items werkelijk moet opnemen of uitsluiten.</span><span class="sxs-lookup"><span data-stu-id="3044b-122">However, multiple policies result in higher administrative overheads, so always confirm whether you really need inclusions and exclusions.</span></span> <span data-ttu-id="3044b-123">Onthoud dat er voor de standaardconfiguratie, die van toepassing is op de gehele locatie, geen limieten gelden en dat deze configuratie een betere oplossing kan zijn dan het maken en onderhouden van meerdere beleidsregels.</span><span class="sxs-lookup"><span data-stu-id="3044b-123">Remember that the default configuration that applies to the entire location doesn't have any limitations, and this configuration choice might be a better solution than creating and maintaining multiple policies.</span></span>

> [!TIP]
> <span data-ttu-id="3044b-124">Als u toch meerdere beleidsregels moet maken en onderhouden voor dit scenario, overweeg dan [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) te gebruiken voor efficiëntere configuratie.</span><span class="sxs-lookup"><span data-stu-id="3044b-124">If do you need to create and maintain multiple policies for this scenario, consider using [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) for more efficient configuration.</span></span>

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a><span data-ttu-id="3044b-125">Voorbeelden van het gebruik van meerdere beleidsregels om het overschrijden van limieten te voorkomen</span><span class="sxs-lookup"><span data-stu-id="3044b-125">Examples of using multiple policies to avoid exceeding maximum numbers</span></span>

<span data-ttu-id="3044b-126">De volgende voorbeelden bevatten oplossingen voor situaties waarin u niet alleen de locatie kunt opgeven voor het bewaarbeleid en rekening moet houden met het maximum voor het aantal vastgelegde items dat in de voorgaande sectie is besproken.</span><span class="sxs-lookup"><span data-stu-id="3044b-126">The following examples provide some design solutions for when you can't specify just the location for a retention policy, and must take into account the maximum number of items documented in the previous section.</span></span>

<span data-ttu-id="3044b-127">Voorbeeld met Exchange:</span><span class="sxs-lookup"><span data-stu-id="3044b-127">Exchange example:</span></span>

- <span data-ttu-id="3044b-128">**Scenario**: in een organisatie met ruim 40.000 gebruikerspostvakken worden de e-mailberichten van de meeste gebruikers 7 jaar behouden, maar van bepaalde gebruikers (425) binnen deze groep moeten de e-mailberichten slechts 5 jaar worden behouden.</span><span class="sxs-lookup"><span data-stu-id="3044b-128">**Requirement**: In an organization that has over 40,000 user mailboxes, most users must have their email retained for 7 years but a subset of identified users (425) must have their email retained for only 5 years.</span></span>

- <span data-ttu-id="3044b-129">**Oplossing**: maak een bewaarbeleid voor Exchange-e-mail met een retentieperiode van 7 jaar en sluit de geïdentificeerde gebruikers uit.</span><span class="sxs-lookup"><span data-stu-id="3044b-129">**Solution**: Create one retention policy for Exchange email with a retention period of 7 years and exclude the subset of users.</span></span> <span data-ttu-id="3044b-130">Maak vervolgens een bewaarbeleid voor Exchange-e-mail met een retentieperiode van 5 jaar waarin de geïdentificeerde gebruikers zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="3044b-130">Then create a second retention policy for Exchange email with a retention period of 5 years and include the subset of users.</span></span> 
    
    <span data-ttu-id="3044b-131">In beide gevallen ligt het aantal opgenomen en uitgesloten postvakken onder het maximale aantal postvakken voor een enkele beleidsregel en moeten de geïdentificeerde gebruikers expliciet worden uitgesloten van de eerste beleidsregel, omdat deze een [langere retentieperiode](retention.md#the-principles-of-retention-or-what-takes-precedence) heeft dan de tweede beleidsregel.</span><span class="sxs-lookup"><span data-stu-id="3044b-131">In both cases, the number included and excluded is below the maximum number of specified mailboxes for a single policy, and the subset of users must be explicitly excluded from the first policy because it has a [longer retention period](retention.md#the-principles-of-retention-or-what-takes-precedence) than the second policy.</span></span> <span data-ttu-id="3044b-132">Als de subset van gebruikers een langer bewaarbeleid vereist, hoeft u ze niet uit te sluiten van het eerste beleid.</span><span class="sxs-lookup"><span data-stu-id="3044b-132">If the subset of users required a longer retention policy, you wouldn't need to exclude them from the first policy.</span></span>
     
    <span data-ttu-id="3044b-133">Als er in de organisatie een nieuw personeelslid is, wordt het postvak van die persoon door deze oplossing automatisch opgenomen in het 7 jaar-beleid en zijn er geen gevolgen voor het maximale aantal ondersteunde items.</span><span class="sxs-lookup"><span data-stu-id="3044b-133">With this solution, if anybody new joins the organization, their mailbox is automatically included in the first policy for 7 years and there is no impact to the maximum numbers supported.</span></span> <span data-ttu-id="3044b-134">Als er echter nieuwe gebruikers zijn voor wie een retentieperiode van 5 jaar nodig is, neemt het aantal opgenomen en uitgesloten items toe richting de limiet van 1.000.</span><span class="sxs-lookup"><span data-stu-id="3044b-134">However, new users that require the 5-year retention period add to the include and exclude numbers, and this limit would be reached at 1,000.</span></span>

<span data-ttu-id="3044b-135">Voorbeeld met SharePoint:</span><span class="sxs-lookup"><span data-stu-id="3044b-135">SharePoint example:</span></span>

- <span data-ttu-id="3044b-136">**Scenario**: een organisatie heeft duizenden SharePoint-sites, maar voor slechts 2.000 sites is er een retentieperiode van 10 jaar nodig en voor 8.000 sites een retentieperiode van 4 jaar.</span><span class="sxs-lookup"><span data-stu-id="3044b-136">**Requirement**: An organization has several thousand SharePoint sites but only 2,000 sites require a retention period of 10 years, and 8,000 sites require a retention period of 4 years.</span></span>

- <span data-ttu-id="3044b-137">**Oplossing**: maak 20 bewaarbeleidsregels voor SharePoint met een retentieperiode van 10 jaar waarin 100 specifieke sites zijn opgenomen en 80 bewaarbeleidsregels voor SharePoint met een retentieperiode van 4 jaar waarin 100 specifieke sites zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="3044b-137">**Solution**: Create 20 retention policies for SharePoint with a retention period of 10 years that includes 100 specific sites, and create 80 retention policies for SharePoint with a retention period of 4 years that includes 100 specific sites.</span></span>
    
    <span data-ttu-id="3044b-138">Omdat u niet alle SharePoint-sites hoeft te behouden, maakt u bewaarbeleidsregels waarin specifieke sites zijn opgenomen.</span><span class="sxs-lookup"><span data-stu-id="3044b-138">Because you don't need to retain all SharePoint sites, you must create retention policies that specify the specific sites.</span></span> <span data-ttu-id="3044b-139">Omdat een bewaarbeleidsregel niet meer dan 100 specifieke sites ondersteunt, moet u meerdere beleidsregels maken voor beide retentieperiodes.</span><span class="sxs-lookup"><span data-stu-id="3044b-139">Because a retention policy doesn't support more than 100 specified sites, you must create multiple policies for the two retention periods.</span></span> <span data-ttu-id="3044b-140">Deze bewaarbeleidsregels hebben een maximaal aantal opgenomen sites, dus voor de volgende nieuwe site is er een nieuwe bewaarbeleidsregel nodig, ongeacht de retentieperiode.</span><span class="sxs-lookup"><span data-stu-id="3044b-140">These retention policies  have the maximum number of included sites, so the next new site that needs retaining would require a new retention policy, irrespective of the retention period.</span></span>