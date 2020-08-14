---
title: Interacties tussen groepen Services
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: Interacties tussen groepen Services
ms.openlocfilehash: 9632debf1bc6fdd2fce061a4c535906410700175
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662587"
---
# <a name="groups-services-interactions"></a><span data-ttu-id="08a52-103">Interacties tussen groepen Services</span><span class="sxs-lookup"><span data-stu-id="08a52-103">Groups services interactions</span></span>

<span data-ttu-id="08a52-104">Microsoft 365 groepen biedt een gemeenschappelijke Fabric voor een aantal services en werkbelasting in het Microsoft 365-platform om een verbinding te kunnen voeren voor eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="08a52-104">Microsoft 365 Groups provides a common fabric for a number of services and workloads within the Microsoft 365 platform to deliver a connected experience for end-users.</span></span> <span data-ttu-id="08a52-105">In de kern is een Microsoft 365-groep beschikbaar voor de volgende bewerkingen:</span><span class="sxs-lookup"><span data-stu-id="08a52-105">At its core, a Microsoft 365 group exists to provide:</span></span>

- <span data-ttu-id="08a52-106">Een manier om het lidmaatschap (Azure AD) te beheren</span><span class="sxs-lookup"><span data-stu-id="08a52-106">A way to manage the membership (Azure AD)</span></span>
- <span data-ttu-id="08a52-107">Een plaats waar berichten en gesprekken plaatsvinden (Exchange-postvak, Microsoft teams, Yammer)</span><span class="sxs-lookup"><span data-stu-id="08a52-107">A place for messaging and conversations to take place (Exchange mailbox, Microsoft Teams, Yammer)</span></span>
- <span data-ttu-id="08a52-108">Een locatie voor het opslaan van bestanden (SharePoint)</span><span class="sxs-lookup"><span data-stu-id="08a52-108">A place for files to be stored (SharePoint)</span></span>
- <span data-ttu-id="08a52-109">Een agenda voor planning (Exchange)</span><span class="sxs-lookup"><span data-stu-id="08a52-109">A calendar for scheduling (Exchange)</span></span>
- <span data-ttu-id="08a52-110">Een notitieblok voor het vastleggen van notities (OneNote)</span><span class="sxs-lookup"><span data-stu-id="08a52-110">A notebook for capturing notes (OneNote)</span></span>

<span data-ttu-id="08a52-111">Wanneer u groepen maakt, worden er ook een aantal andere resources ingericht, maar deze zijn pas zichtbaar wanneer ze voor het eerst worden geopend voor de eerste keer van de service:</span><span class="sxs-lookup"><span data-stu-id="08a52-111">At the point of group creation, a number of other resources are also provisioned, however they are not visible until accessed for the first time from the service:</span></span>

- <span data-ttu-id="08a52-112">Een bord voor het beheren van groeps taken (planner)</span><span class="sxs-lookup"><span data-stu-id="08a52-112">A board for managing group tasks (Planner)</span></span>
- <span data-ttu-id="08a52-113">Een werkruimte voor rapportage (Power BI)</span><span class="sxs-lookup"><span data-stu-id="08a52-113">A workspace for reporting (Power BI)</span></span>
- <span data-ttu-id="08a52-114">Een gebied voor gedeelde Video's (Microsoft stream)</span><span class="sxs-lookup"><span data-stu-id="08a52-114">An area for shared videos (Microsoft Stream)</span></span>
- <span data-ttu-id="08a52-115">Een gebied voor gedeelde formulieren (formulieren)</span><span class="sxs-lookup"><span data-stu-id="08a52-115">An area for shared forms (Forms)</span></span>

<span data-ttu-id="08a52-116">In Microsoft 365 kunnen andere services communiceren met Microsoft 365-groepen om extra functies en mogelijkheden voor groepsleden te bieden.</span><span class="sxs-lookup"><span data-stu-id="08a52-116">Across Microsoft 365, other services are able to interact with Microsoft 365 groups to deliver additional functionality and capabilities to group members.</span></span>
<span data-ttu-id="08a52-117">Voorbeelden hiervan zijn:</span><span class="sxs-lookup"><span data-stu-id="08a52-117">Examples of this include:</span></span>

- <span data-ttu-id="08a52-118">Power-apps voor apps</span><span class="sxs-lookup"><span data-stu-id="08a52-118">Power Apps for apps</span></span>
- <span data-ttu-id="08a52-119">Automatisch aan de werkstroom voor werkstromen</span><span class="sxs-lookup"><span data-stu-id="08a52-119">Power Automate for workflows</span></span>
- <span data-ttu-id="08a52-120">Project op het web en routekaart voor het waterval van Project Management</span><span class="sxs-lookup"><span data-stu-id="08a52-120">Project on the web and Roadmap for waterfall-based project management</span></span>
- <span data-ttu-id="08a52-121">Teams voor kanaal gesprekken</span><span class="sxs-lookup"><span data-stu-id="08a52-121">Teams for channel-based conversations</span></span>
- <span data-ttu-id="08a52-122">Yammer voor community's van belang</span><span class="sxs-lookup"><span data-stu-id="08a52-122">Yammer for communities of interest</span></span>

## <a name="user-interactions-with-groups"></a><span data-ttu-id="08a52-123">Gebruikersinteracties met groepen</span><span class="sxs-lookup"><span data-stu-id="08a52-123">User interactions with groups</span></span>

<span data-ttu-id="08a52-124">Microsoft 365-groepen kunnen worden gemaakt en beheerd vanuit diverse interfaces, zowel beheerders als eindgebruikers.</span><span class="sxs-lookup"><span data-stu-id="08a52-124">Microsoft 365 Groups can be created and managed from a variety of interfaces, both by administrators and end-users.</span></span> 

### <a name="administrative-experiences"></a><span data-ttu-id="08a52-125">Beheer ervaring</span><span class="sxs-lookup"><span data-stu-id="08a52-125">Administrative experiences</span></span>

<span data-ttu-id="08a52-126">Beheerders kunnen Microsoft 365-groepen maken en beheren vanuit diverse beheer centra, opdrachtregel interfaces die ondersteuning bieden voor het uitvoeren van scripts en aangepaste apps die met de Graph-API werken.</span><span class="sxs-lookup"><span data-stu-id="08a52-126">Administrators can create and manage Microsoft 365 groups from several of the workload admin centers, command-line interfaces that support scripting, as well as custom-built apps interacting with the Graph API.</span></span> <span data-ttu-id="08a52-127">De enige uitzondering hierop is Yammer-groepen die moeten worden gemaakt binnen de Yammer-website.</span><span class="sxs-lookup"><span data-stu-id="08a52-127">The only exception to this is Yammer groups – which must be created from within the Yammer web interface.</span></span>

<span data-ttu-id="08a52-128">**Gerelateerde instellingen**</span><span class="sxs-lookup"><span data-stu-id="08a52-128">**Related settings**</span></span>

<span data-ttu-id="08a52-129">In de verschillende beheerinterfaces die de groepsinstellingen kunnen beheren, bestaan diverse overlappingen waarvan u op de hoogte moet zijn.</span><span class="sxs-lookup"><span data-stu-id="08a52-129">Across the various administrative interfaces that can manage group settings exists several overlaps which you should be aware of.</span></span>

<span data-ttu-id="08a52-130">**Microsoft 365-beheercentrum**</span><span class="sxs-lookup"><span data-stu-id="08a52-130">**Microsoft 365 admin center**</span></span>

<span data-ttu-id="08a52-131">In het Microsoft 365-Beheercentrum is gasttoegang voor groepen standaard ingeschakeld, en is de mogelijkheid om eigenaren toe te voegen om gasten toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="08a52-131">In the Microsoft 365 admin center, guest access to Groups is enabled by default, as is the ability to allow owners to add guests.</span></span> <span data-ttu-id="08a52-132">Er zijn geen besturingselementen voor organisatieniveau beschikbaar voor groepen uit dit Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="08a52-132">There are no further organization-level controls available for Groups from this admin center.</span></span>

<span data-ttu-id="08a52-133">**Azure AD-Beheercentrum**</span><span class="sxs-lookup"><span data-stu-id="08a52-133">**Azure AD admin center**</span></span>

<span data-ttu-id="08a52-134">Het Azure AD-Beheercentrum bevat besturingselementen om te bepalen of gebruikersgroepen kunnen maken of eigenaren kunnen toewijzen in azure-portals, evenals de beleidsinstellingen voor de vervaldatum en de naamgeving.</span><span class="sxs-lookup"><span data-stu-id="08a52-134">The Azure AD admin center offers controls around whether users can create Groups or assign owners in Azure portals, as well as expiration and naming policy settings.</span></span>

<span data-ttu-id="08a52-135">Het Beheercentrum biedt ook een aantal opties voor de uitnodigingen van een gast, die verder gaan dan het aantal van het Microsoft 365-Beheercentrum, bijvoorbeeld de mogelijkheid om te beperken of niet-eigenaren ook gasten kunnen uitnodigen</span><span class="sxs-lookup"><span data-stu-id="08a52-135">The admin center also provides a number of guest invitation control measures that go beyond that of the Microsoft 365 admin center, such as the ability to limit whether non-owners can also invite guests</span></span>

<span data-ttu-id="08a52-136">**SharePoint**</span><span class="sxs-lookup"><span data-stu-id="08a52-136">**SharePoint**</span></span>

<span data-ttu-id="08a52-137">SharePoint-sites worden gemaakt met de beveiligingsgroepen eigenaar, lid en bezoekers, en de eerste twee stemmen overeen met hun Microsoft 365-groep tegenhangers.</span><span class="sxs-lookup"><span data-stu-id="08a52-137">SharePoint sites are created with Owner, Member and Visitor security groups, with the first two matching up to their Microsoft 365 Group counterparts.</span></span> <span data-ttu-id="08a52-138">Hoewel lidmaatschap van SharePoint Online-sites meestal wordt beheerd door de bijbehorende Microsoft 365-groep, is het geen bidirectioneelere relatie.</span><span class="sxs-lookup"><span data-stu-id="08a52-138">While membership for SharePoint Online sites is generally managed by the associated Microsoft 365 Group, it is not a bidirectional relationship.</span></span> <span data-ttu-id="08a52-139">Wijzigingen aan het lidmaatschap van het Microsoft 365-groepsniveau worden weergegeven in SharePoint, maar als lidmaatschap in de SharePoint-groep is gewijzigd, wordt dit niet weergegeven in de groep Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08a52-139">Any changes to membership at the Microsoft 365 group level are reflected in SharePoint, however if membership is changed in the SharePoint group, this is not reflected in the Microsoft 365 group.</span></span>

### <a name="user-experiences"></a><span data-ttu-id="08a52-140">Gebruikerservaring</span><span class="sxs-lookup"><span data-stu-id="08a52-140">User experiences</span></span>

<span data-ttu-id="08a52-141">Eindgebruikers kunnen groepen maken op basis van diverse services binnen Microsoft 365 en in anderen die ze alleen met een groep kunnen delen.</span><span class="sxs-lookup"><span data-stu-id="08a52-141">End users can create groups from several of the services within Microsoft 365, and in others they can only share with a group.</span></span>

<span data-ttu-id="08a52-142">Met de volgende services kan het maken van groepen door eindgebruikers:</span><span class="sxs-lookup"><span data-stu-id="08a52-142">The following services allow creation of groups by end users:</span></span>
                         
<span data-ttu-id="08a52-143">Outlook planner project voor de webshare Point stream Microsoft teams Yammer</span><span class="sxs-lookup"><span data-stu-id="08a52-143">Outlook Planner Project for the web SharePoint  Stream  Microsoft Teams Yammer</span></span>

<span data-ttu-id="08a52-144">**Beperking van het maken van groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-144">**Restriction of group creation**</span></span>

<span data-ttu-id="08a52-145">Een veelgebruikte aanpak voor het beheren van sprawl van teams is beperkt welke gebruikers ze kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-145">A common approach to control sprawl of teams is to limit which users can create them.</span></span> <span data-ttu-id="08a52-146">Dit kan alleen worden gedaan door het maken van groepen te beperken.</span><span class="sxs-lookup"><span data-stu-id="08a52-146">This can only be done by limiting the creation of groups.</span></span> <span data-ttu-id="08a52-147">Dit heeft gevolgen voor de mogelijkheid om groepen te maken van andere services, indien dit voor eindgebruikers mogelijk noodzakelijk is.</span><span class="sxs-lookup"><span data-stu-id="08a52-147">Doing this impacts the ability to create groups from other services where that may be necessary for end-user.</span></span> <span data-ttu-id="08a52-148">Microsoft 365-groepen biedt geen ondersteuning voor de mogelijkheid om het maken van groepen van bepaalde apps of services te beperken, terwijl u de groepen van derden toestaat.</span><span class="sxs-lookup"><span data-stu-id="08a52-148">Microsoft 365 Groups does not support the ability to restrict the creation of groups from some apps or services while allowing it from others.</span></span>

<span data-ttu-id="08a52-149">De ervaring voor het maken van groepen is afhankelijk van apps en services:</span><span class="sxs-lookup"><span data-stu-id="08a52-149">The experience of group creation restriction varies between apps and services:</span></span>


|<span data-ttu-id="08a52-150">App of service</span><span class="sxs-lookup"><span data-stu-id="08a52-150">App or service</span></span>|<span data-ttu-id="08a52-151">Optreedt</span><span class="sxs-lookup"><span data-stu-id="08a52-151">Experience</span></span>|
|:-------------|:---------|
|<span data-ttu-id="08a52-152">Outlook</span><span class="sxs-lookup"><span data-stu-id="08a52-152">Outlook</span></span>|<span data-ttu-id="08a52-153">De optie **nieuwe groep** wordt verwijderd uit het menu Nieuw op de pagina personen</span><span class="sxs-lookup"><span data-stu-id="08a52-153">**New group** option is removed from New menu in people page</span></span>|
|<span data-ttu-id="08a52-154">Planner</span><span class="sxs-lookup"><span data-stu-id="08a52-154">Planner</span></span>|<span data-ttu-id="08a52-155">**Nieuw plan** geeft aan dat het maken van groepen is uitgeschakeld en dat u aanbiedingen wilt toevoegen aan een bestaande groep</span><span class="sxs-lookup"><span data-stu-id="08a52-155">**New plan** explains that group creation has been turned off and offers to add the plan to an existing group</span></span>|
|<span data-ttu-id="08a52-156">Project voor het web en routekaart</span><span class="sxs-lookup"><span data-stu-id="08a52-156">Project for the web and Roadmap</span></span>|<span data-ttu-id="08a52-157">Menu **groep maken** geeft uitleg dat het maken van groepen is beperkt en dat een bestaande groep wordt voorgesteld.</span><span class="sxs-lookup"><span data-stu-id="08a52-157">**Create group** menu explains that group creation is restricted and suggests using an existing group.</span></span>|
|<span data-ttu-id="08a52-158">SharePoint</span><span class="sxs-lookup"><span data-stu-id="08a52-158">SharePoint</span></span>|<span data-ttu-id="08a52-159">U kunt nog steeds een team site maken die niet is gekoppeld aan een groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-159">Still able to create a team site that is not connected to a group.</span></span>|
|<span data-ttu-id="08a52-160">Stream</span><span class="sxs-lookup"><span data-stu-id="08a52-160">Stream</span></span>|<span data-ttu-id="08a52-161">De optie **groep** wordt niet weergegeven in het **menu maken**.</span><span class="sxs-lookup"><span data-stu-id="08a52-161">**Group** option does not appear under the **Create menu**.</span></span>|
|<span data-ttu-id="08a52-162">Teams</span><span class="sxs-lookup"><span data-stu-id="08a52-162">Teams</span></span>|<span data-ttu-id="08a52-163">Gebruiker kan geen team maken met een nieuwe groep, maar u kunt nog wel een team maken dat gebruikmaakt van een bestaande groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-163">User cannot create a team with a new group but can still create a team that utilizes an existing group.</span></span><br><br><span data-ttu-id="08a52-164">U **maakt een team** knop door **team maken van een groep**te vervangen.</span><span class="sxs-lookup"><span data-stu-id="08a52-164">**Create a team** button is replaced with **Create team from a group**.</span></span>|
|<span data-ttu-id="08a52-165">Yammer</span><span class="sxs-lookup"><span data-stu-id="08a52-165">Yammer</span></span>|<span data-ttu-id="08a52-166">**De optie een groep maken** wordt verwijderd uit hoofdgroepen/community's-navigatie.</span><span class="sxs-lookup"><span data-stu-id="08a52-166">**Create a group** option is removed from main Groups/Communities navigation.</span></span>|

## <a name="services-interactions-with-groups"></a><span data-ttu-id="08a52-167">Service interacties met groepen</span><span class="sxs-lookup"><span data-stu-id="08a52-167">Services interactions with groups</span></span>

<span data-ttu-id="08a52-168">Zie de groepen in Microsoft 365-poster voor informatie over de verschillende soorten groepen, hoe deze worden gemaakt en beheerd en wat de aanbevelingen zijn.</span><span class="sxs-lookup"><span data-stu-id="08a52-168">See the Groups in Microsoft 365 poster for information about different types of groups, how these are created and managed, and a few governance recommendations.</span></span>

<span data-ttu-id="08a52-169">[![Miniatuurafbeelding van de infographic voor groepen](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span><span class="sxs-lookup"><span data-stu-id="08a52-169">[![Thumb image for groups infographic](../downloads/msft-m365-groups-architecture-thumb.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf)</span></span>

<span data-ttu-id="08a52-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span><span class="sxs-lookup"><span data-stu-id="08a52-170">[PDF](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/downloads/msft-m365-groups.pdf) \| [Visio](https://github.com/MicrosoftDocs/OfficeDocs-Enterprise/raw/live/Enterprise/downloads/msft-m365-groups.vsdx)</span></span>

<span data-ttu-id="08a52-171">De volgende tabel bevat een overzicht van Microsoft 365 groepen interacties met verschillende services:</span><span class="sxs-lookup"><span data-stu-id="08a52-171">The following table provides an overview of Microsoft 365 Groups interactions with various services:</span></span>

|<span data-ttu-id="08a52-172">Product</span><span class="sxs-lookup"><span data-stu-id="08a52-172">Product</span></span>|<span data-ttu-id="08a52-173">Functies</span><span class="sxs-lookup"><span data-stu-id="08a52-173">Features</span></span>|<span data-ttu-id="08a52-174">Gaat de service</span><span class="sxs-lookup"><span data-stu-id="08a52-174">Does the service</span></span><br><span data-ttu-id="08a52-175">bestaan zonder een groep?</span><span class="sxs-lookup"><span data-stu-id="08a52-175">exist without a group?</span></span>|<span data-ttu-id="08a52-176">Kan de service</span><span class="sxs-lookup"><span data-stu-id="08a52-176">Can the service</span></span><br><span data-ttu-id="08a52-177">een groep maken?</span><span class="sxs-lookup"><span data-stu-id="08a52-177">create a group?</span></span>|<span data-ttu-id="08a52-178">Verwijdert de</span><span class="sxs-lookup"><span data-stu-id="08a52-178">Does deleting the</span></span><br><span data-ttu-id="08a52-179">exemplaar verwijderen van de groep?</span><span class="sxs-lookup"><span data-stu-id="08a52-179">instance delete the group?</span></span>|
|:---|:---|:---|:---|:---|
|<span data-ttu-id="08a52-180">Azure AD</span><span class="sxs-lookup"><span data-stu-id="08a52-180">Azure AD</span></span>|<span data-ttu-id="08a52-181">Lidmaatschap, besturingselementen voor groepen, gasten</span><span class="sxs-lookup"><span data-stu-id="08a52-181">Membership, Group controls, Guests</span></span>|<span data-ttu-id="08a52-182">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-182">Yes</span></span>|<span data-ttu-id="08a52-183">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-183">Yes</span></span>|<span data-ttu-id="08a52-184">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-184">Yes</span></span>|
|<span data-ttu-id="08a52-185">Exchange</span><span class="sxs-lookup"><span data-stu-id="08a52-185">Exchange</span></span>|<span data-ttu-id="08a52-186">Agenda, Postvak</span><span class="sxs-lookup"><span data-stu-id="08a52-186">Calendar, mailbox</span></span>|<span data-ttu-id="08a52-187">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-187">Yes</span></span>|<span data-ttu-id="08a52-188">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-188">Yes</span></span>|<span data-ttu-id="08a52-189">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-189">Yes</span></span>|
|<span data-ttu-id="08a52-190">Vormen</span><span class="sxs-lookup"><span data-stu-id="08a52-190">Forms</span></span>|<span data-ttu-id="08a52-191">Trans</span><span class="sxs-lookup"><span data-stu-id="08a52-191">Form</span></span>|<span data-ttu-id="08a52-192">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-192">Yes</span></span>|<span data-ttu-id="08a52-193">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-193">No</span></span>|<span data-ttu-id="08a52-194">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-194">No</span></span>|
|<span data-ttu-id="08a52-195">OneNote</span><span class="sxs-lookup"><span data-stu-id="08a52-195">OneNote</span></span>|<span data-ttu-id="08a52-196">Terechtkom</span><span class="sxs-lookup"><span data-stu-id="08a52-196">Notebook</span></span>|<span data-ttu-id="08a52-197">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-197">Yes</span></span>|<span data-ttu-id="08a52-198">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-198">No</span></span>|<span data-ttu-id="08a52-199">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-199">No</span></span>|
|<span data-ttu-id="08a52-200">Planner</span><span class="sxs-lookup"><span data-stu-id="08a52-200">Planner</span></span>|<span data-ttu-id="08a52-201">Takenbord</span><span class="sxs-lookup"><span data-stu-id="08a52-201">Task board</span></span>|<span data-ttu-id="08a52-202">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-202">No</span></span>|<span data-ttu-id="08a52-203">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-203">Yes</span></span>|<span data-ttu-id="08a52-204">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-204">Yes</span></span>|
|<span data-ttu-id="08a52-205">Power apps-app</span><span class="sxs-lookup"><span data-stu-id="08a52-205">Power Apps app</span></span>|<span data-ttu-id="08a52-206">App</span><span class="sxs-lookup"><span data-stu-id="08a52-206">App</span></span>|<span data-ttu-id="08a52-207">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-207">Yes</span></span>|<span data-ttu-id="08a52-208">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-208">No</span></span>|<span data-ttu-id="08a52-209">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-209">No</span></span>|
|<span data-ttu-id="08a52-210">Automatisch aan de macht</span><span class="sxs-lookup"><span data-stu-id="08a52-210">Power Automate</span></span>|<span data-ttu-id="08a52-211">Workflowregels</span><span class="sxs-lookup"><span data-stu-id="08a52-211">Workflow</span></span>|<span data-ttu-id="08a52-212">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-212">Yes</span></span>|<span data-ttu-id="08a52-213">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-213">No</span></span>|<span data-ttu-id="08a52-214">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-214">No</span></span>|
|<span data-ttu-id="08a52-215">Power BI (klassiek)</span><span class="sxs-lookup"><span data-stu-id="08a52-215">Power BI (classic)</span></span>|<span data-ttu-id="08a52-216">Vinden</span><span class="sxs-lookup"><span data-stu-id="08a52-216">Workspace</span></span>|<span data-ttu-id="08a52-217">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-217">No</span></span>|<span data-ttu-id="08a52-218">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-218">Yes</span></span>|<span data-ttu-id="08a52-219">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-219">Yes</span></span>|
|<span data-ttu-id="08a52-220">Power BI (nieuw)</span><span class="sxs-lookup"><span data-stu-id="08a52-220">Power BI (new)</span></span>|<span data-ttu-id="08a52-221">Vinden</span><span class="sxs-lookup"><span data-stu-id="08a52-221">Workspace</span></span>|<span data-ttu-id="08a52-222">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-222">Yes</span></span>|<span data-ttu-id="08a52-223">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-223">No</span></span>|<span data-ttu-id="08a52-224">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-224">Yes</span></span>|
|<span data-ttu-id="08a52-225">Project voor het web</span><span class="sxs-lookup"><span data-stu-id="08a52-225">Project for the web</span></span>|<span data-ttu-id="08a52-226">Project plan</span><span class="sxs-lookup"><span data-stu-id="08a52-226">Project plan</span></span>|<span data-ttu-id="08a52-227">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-227">Yes</span></span>|<span data-ttu-id="08a52-228">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-228">Yes</span></span>|<span data-ttu-id="08a52-229">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-229">No</span></span>|
|<span data-ttu-id="08a52-230">Routekaart</span><span class="sxs-lookup"><span data-stu-id="08a52-230">Roadmap</span></span>|<span data-ttu-id="08a52-231">Routekaart</span><span class="sxs-lookup"><span data-stu-id="08a52-231">Roadmap</span></span>|<span data-ttu-id="08a52-232">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-232">Yes</span></span>|<span data-ttu-id="08a52-233">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-233">Yes</span></span>|<span data-ttu-id="08a52-234">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-234">No</span></span>|
|<span data-ttu-id="08a52-235">SharePoint</span><span class="sxs-lookup"><span data-stu-id="08a52-235">SharePoint</span></span>|<span data-ttu-id="08a52-236">Site</span><span class="sxs-lookup"><span data-stu-id="08a52-236">Site</span></span>|<span data-ttu-id="08a52-237">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-237">Yes</span></span>|<span data-ttu-id="08a52-238">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-238">Yes</span></span>|<span data-ttu-id="08a52-239">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-239">Yes</span></span>|
|<span data-ttu-id="08a52-240">Stream</span><span class="sxs-lookup"><span data-stu-id="08a52-240">Stream</span></span>|<span data-ttu-id="08a52-241">Kanaal, video</span><span class="sxs-lookup"><span data-stu-id="08a52-241">Channel, video</span></span>|<span data-ttu-id="08a52-242">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-242">Yes</span></span>|<span data-ttu-id="08a52-243">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-243">Yes</span></span>|<span data-ttu-id="08a52-244">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-244">Yes</span></span>|
|<span data-ttu-id="08a52-245">Teams</span><span class="sxs-lookup"><span data-stu-id="08a52-245">Teams</span></span>|<span data-ttu-id="08a52-246">Ondersteuning</span><span class="sxs-lookup"><span data-stu-id="08a52-246">Team</span></span>|<span data-ttu-id="08a52-247">Nee</span><span class="sxs-lookup"><span data-stu-id="08a52-247">No</span></span>|<span data-ttu-id="08a52-248">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-248">Yes</span></span>|<span data-ttu-id="08a52-249">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-249">Yes</span></span>|
|<span data-ttu-id="08a52-250">Yammer</span><span class="sxs-lookup"><span data-stu-id="08a52-250">Yammer</span></span>|<span data-ttu-id="08a52-251">Groep</span><span class="sxs-lookup"><span data-stu-id="08a52-251">Group</span></span>|<span data-ttu-id="08a52-252">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-252">Yes</span></span>|<span data-ttu-id="08a52-253">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-253">Yes</span></span>|<span data-ttu-id="08a52-254">Ja</span><span class="sxs-lookup"><span data-stu-id="08a52-254">Yes</span></span>|

<span data-ttu-id="08a52-255">Hoewel de bovenstaande tabel een algemeen overzicht biedt van groeps interacties met Microsoft 365-Services, zijn er een aantal nuances en intricacies die u moet begrijpen.</span><span class="sxs-lookup"><span data-stu-id="08a52-255">While the table above provides a high-level overview of group interactions with Microsoft 365 services, there are a number of nuances and intricacies that you should understand.</span></span> <span data-ttu-id="08a52-256">In de volgende secties vindt u meer gedetailleerde informatie over de specifieke werkbelastingen en hun interacties met groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-256">The following sections take a more in-depth look at the specific workloads and their interactions with groups.</span></span>

## <a name="azure-ad"></a><span data-ttu-id="08a52-257">Azure AD</span><span class="sxs-lookup"><span data-stu-id="08a52-257">Azure AD</span></span>

<span data-ttu-id="08a52-258">Azure AD biedt de onderliggende functies voor Identiteitsbeheer in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08a52-258">Azure AD provides the underlying identity management capabilities across Microsoft 365.</span></span>

<span data-ttu-id="08a52-259">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-259">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-260">Groepslidmaatschap</span><span class="sxs-lookup"><span data-stu-id="08a52-260">Group membership</span></span>
- <span data-ttu-id="08a52-261">Naam beleid</span><span class="sxs-lookup"><span data-stu-id="08a52-261">Naming policy</span></span>
- <span data-ttu-id="08a52-262">Verloopbeleid</span><span class="sxs-lookup"><span data-stu-id="08a52-262">Expiration policy</span></span>
- <span data-ttu-id="08a52-263">Gast</span><span class="sxs-lookup"><span data-stu-id="08a52-263">Guests</span></span>
- <span data-ttu-id="08a52-264">Beperking van het maken van groepen</span><span class="sxs-lookup"><span data-stu-id="08a52-264">Restriction of Group creation</span></span>

<span data-ttu-id="08a52-265">**Kan Azure AD een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-265">**Can Azure AD create a Group?**</span></span>

<span data-ttu-id="08a52-266">Ja, Microsoft 365-groepen kunnen worden gemaakt op basis van Azure AD via de webportal van beheer, via PowerShell of graph API.</span><span class="sxs-lookup"><span data-stu-id="08a52-266">Yes, Microsoft 365 Groups can be created from Azure AD either through the administration web portal, through PowerShell, or Graph API.</span></span>

<span data-ttu-id="08a52-267">**Bestaat Azure AD zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-267">**Does Azure AD exist without a group?**</span></span>

<span data-ttu-id="08a52-268">Ja, Azure AD voert een geweldig aantal services uit die geen relatie hebben met Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-268">Yes, Azure AD performs a great number of services that have no relation to Microsoft 365 Groups.</span></span> <span data-ttu-id="08a52-269">Elke groep Microsoft 365 wordt weergegeven als een object in azure AD.</span><span class="sxs-lookup"><span data-stu-id="08a52-269">Each Microsoft 365 group is represented as an object in Azure AD.</span></span>

<span data-ttu-id="08a52-270">**Kunnen er meerdere exemplaren van Azure AD per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-270">**Can there be multiple instances of Azure AD per Group?**</span></span>

<span data-ttu-id="08a52-271">Nee, er is maar één exemplaar van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="08a52-271">No, there is only one instance of Azure AD.</span></span>

<span data-ttu-id="08a52-272">**Kan Azure AD worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-272">**Can Azure AD be associated with multiple Groups?**</span></span>

<span data-ttu-id="08a52-273">Ja, omdat Azure AD het onderliggende platform is dat de service voor groeps lidmaatschap biedt.</span><span class="sxs-lookup"><span data-stu-id="08a52-273">Yes, because Azure AD is the underlying platform that provides the group membership service.</span></span>

<span data-ttu-id="08a52-274">**Kan de koppeling van Azure AD met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-274">**Can Azure AD’s association with a group change?**</span></span>

<span data-ttu-id="08a52-275">Nee, Azure AD is het onderliggende platform waar groepen bestaan.</span><span class="sxs-lookup"><span data-stu-id="08a52-275">No, Azure AD is the underlying platform where groups exist.</span></span>

<span data-ttu-id="08a52-276">**Verwijdert het exemplaar van de groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-276">**Does deleting the instance delete the Group?**</span></span>

<span data-ttu-id="08a52-277">Als u de groep in azure AD verwijdert, worden de bijbehorende services en inhoud van de groep verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-277">Deleting the group in Azure AD will delete relevant group-associated services and content.</span></span>

## <a name="teams"></a><span data-ttu-id="08a52-278">Teams</span><span class="sxs-lookup"><span data-stu-id="08a52-278">Teams</span></span>

<span data-ttu-id="08a52-279">Teams is een werkruimte met chat centrum voor een betere samenwerking door een enkelvoudige interface te bieden voor de interactie met diverse Microsoft-services en services van derden.</span><span class="sxs-lookup"><span data-stu-id="08a52-279">Teams is a chat-centered workspace aimed at enhancing collaboration by providing a singular interface to interact with a variety of Microsoft and third-party services.</span></span>

<span data-ttu-id="08a52-280">Wanneer een team wordt gemaakt, worden standaard de e-mail en de agenda die zijn gekoppeld aan de Microsoft 365-groep, verborgen in de algemene adreslijst in Exchange, en in Outlook.</span><span class="sxs-lookup"><span data-stu-id="08a52-280">By default, when a team is created, the mailbox and calendar associated with the Microsoft 365 group are hidden from both the Global Address List in Exchange, as well as Outlook.</span></span> <span data-ttu-id="08a52-281">Dit kan handmatig worden overschreven door een beheerder als de gebruiker Outlook en teams wil gebruiken in dezelfde Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-281">This can be manually overridden by an administrator if the user would like to use both Outlook and Teams on the same Microsoft 365 Group.</span></span>

<span data-ttu-id="08a52-282">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-282">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-283">Communicatie</span><span class="sxs-lookup"><span data-stu-id="08a52-283">Conversations</span></span>
- <span data-ttu-id="08a52-284">& tabbladen kanalen</span><span class="sxs-lookup"><span data-stu-id="08a52-284">Channels & tabs</span></span>
- <span data-ttu-id="08a52-285">Rekken</span><span class="sxs-lookup"><span data-stu-id="08a52-285">Meetings</span></span>

<span data-ttu-id="08a52-286">**Kunnen teams een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-286">**Can Teams create a group?**</span></span>

<span data-ttu-id="08a52-287">Ja, als u een nieuw team wilt maken, maakt u een nieuwe groep Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08a52-287">Yes, creating a new team will create a new Microsoft 365 group.</span></span> <span data-ttu-id="08a52-288">U kunt ook een team maken voor een bestaande groep die momenteel geen abonnement heeft.</span><span class="sxs-lookup"><span data-stu-id="08a52-288">It is also possible to create a team for an existing group that does not currently have one.</span></span>

<span data-ttu-id="08a52-289">**Bestaan teams zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-289">**Do teams exist without a group?**</span></span>

<span data-ttu-id="08a52-290">Nee, het is niet mogelijk dat een team bestaat zonder een groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-290">No, it is not possible for a team to exist without a Group.</span></span>

<span data-ttu-id="08a52-291">**Kunnen er meerdere teams per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-291">**Can there be multiple teams per group?**</span></span>

<span data-ttu-id="08a52-292">Nee, de relatie tussen een team en een groep is 1:1.</span><span class="sxs-lookup"><span data-stu-id="08a52-292">No, the relationship between a team and a group is 1:1.</span></span>

<span data-ttu-id="08a52-293">**Kan een team worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-293">**Can a team be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-294">Nee, het team zelf kan maar aan één groep worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-294">No, the team itself can only be associated with a single group.</span></span>

<span data-ttu-id="08a52-295">**Kan de koppeling van een team met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-295">**Can a team’s association with a group change?**</span></span>

<span data-ttu-id="08a52-296">Nee, het team kan maar ooit worden gekoppeld aan de groep waaraan het oorspronkelijk is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-296">No, the team can only ever be associated with the group to which it was originally associated.</span></span>

<span data-ttu-id="08a52-297">**Verwijdert het team de groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-297">**Does deleting the team delete the group?**</span></span>

<span data-ttu-id="08a52-298">Ja, als u het team verwijdert in Microsoft teams, wordt de groep, de gekoppelde services en de inhoud verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-298">Yes, deleting the team in Microsoft Teams will delete the group, group-associated services, and content.</span></span>

## <a name="exchange"></a><span data-ttu-id="08a52-299">Exchange</span><span class="sxs-lookup"><span data-stu-id="08a52-299">Exchange</span></span>

<span data-ttu-id="08a52-300">Exchange Online levert functies voor berichten, agenda's, contactpersonen en bijbehorende functionaliteit.</span><span class="sxs-lookup"><span data-stu-id="08a52-300">Exchange Online provides messaging, calendar, contact, and associated functionality.</span></span> <span data-ttu-id="08a52-301">In de context van een groep is slechts één resource gekoppeld, in plaats van een volledig service-exemplaar.</span><span class="sxs-lookup"><span data-stu-id="08a52-301">In the context of a Group, only a single resource is associated – as opposed to an entire service instance.</span></span>

<span data-ttu-id="08a52-302">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-302">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-303">Postvak en agenda</span><span class="sxs-lookup"><span data-stu-id="08a52-303">Mailbox and calendar</span></span>
- <span data-ttu-id="08a52-304">Mogelijkheid om alle groepsleden te e-mailen</span><span class="sxs-lookup"><span data-stu-id="08a52-304">Ability to email all Group members</span></span>
- <span data-ttu-id="08a52-305">Opslag van teams-kanaal gesprekken voor eDiscovery-doeleinden, planner-opmerkingen</span><span class="sxs-lookup"><span data-stu-id="08a52-305">Storage of Teams channel conversations for eDiscovery purposes, Planner comments</span></span>

<span data-ttu-id="08a52-306">**Kan Exchange een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-306">**Can Exchange create a group?**</span></span>

<span data-ttu-id="08a52-307">Ja, u kunt een groep maken vanuit het Exchange Online-Beheercentrum en vanuit Outlook.</span><span class="sxs-lookup"><span data-stu-id="08a52-307">Yes, it is possible to create a group from the Exchange Online admin center, as well as from Outlook.</span></span> <span data-ttu-id="08a52-308">U kunt distributielijsten van Exchange ook converteren naar Microsoft 365 groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-308">You can also convert Exchange distribution lists to Microsoft 365 groups.</span></span>

<span data-ttu-id="08a52-309">**Maakt Exchange geen groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-309">**Does Exchange exist without a Group?**</span></span>

<span data-ttu-id="08a52-310">Ja, Exchange Online biedt een aantal services, inclusief gedeelde postvakken en agenda's, zonder groeps koppeling.</span><span class="sxs-lookup"><span data-stu-id="08a52-310">Yes, Exchange Online provides a number of services, including shared mailboxes and calendars, without any group association.</span></span>

<span data-ttu-id="08a52-311">**Kunnen er meerdere exemplaren van Exchange-postvakken of-agenda's per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-311">**Can there be multiple instances of Exchange mailboxes or calendars per group?**</span></span>

<span data-ttu-id="08a52-312">Nee, er kunnen maar één postvak van Exchange Online zijn en agenda voor een groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-312">No, there can only be a single Exchange Online mailbox and calendar for a group.</span></span>

<span data-ttu-id="08a52-313">**Kunnen Exchange-postvakken en-agenda's worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-313">**Can Exchange mailboxes and calendars be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-314">Nee, het postvak en de agenda hebben een 1:1-relatie met de groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-314">No, the mailbox and calendar have a 1:1 relationship with the group.</span></span> <span data-ttu-id="08a52-315">Het is mogelijk dat u het postvak met andere gebruikers of groepen deelt, maar dit is niet van invloed op een vorm van Service Association.</span><span class="sxs-lookup"><span data-stu-id="08a52-315">It is possible to share the mailbox with other users or groups, however this does not establish any form of service association.</span></span>

<span data-ttu-id="08a52-316">**Kunnen de koppeling van het Exchange-postvak of de agenda van een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-316">**Can the Exchange mailbox or calendar’s association with a group change?**</span></span>

<span data-ttu-id="08a52-317">Nee, het postvak en de agenda kunnen niet worden gewijzigd in een andere groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-317">No, the mailbox and calendar   cannot be changed to a different group.</span></span> <span data-ttu-id="08a52-318">U kunt echter de inhoud van het ene Postvak verplaatsen naar het andere in Outlook of met behulp van een programma van derden.</span><span class="sxs-lookup"><span data-stu-id="08a52-318">However, the content can be moved from one mailbox to another within Outlook or by using a third-party tool.</span></span>

<span data-ttu-id="08a52-319">**Verwijdert het postvak van de groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-319">**Does deleting the mailbox delete the group?**</span></span>

<span data-ttu-id="08a52-320">Ja, als u het postvak in Exchange verwijdert, wordt de groep verwijderd en worden ook services en inhoud die aan de groep zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-320">Yes, deleting the mailbox in Exchange will delete the group as well as group-associated services and content.</span></span>

## <a name="forms"></a><span data-ttu-id="08a52-321">Vormen</span><span class="sxs-lookup"><span data-stu-id="08a52-321">Forms</span></span>

<span data-ttu-id="08a52-322">Forms biedt enquêtes en toetsen voor het web.</span><span class="sxs-lookup"><span data-stu-id="08a52-322">Forms provides web-based surveys and quizzes.</span></span>

<span data-ttu-id="08a52-323">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-323">**Key features provided to groups**</span></span>

- <span data-ttu-id="08a52-324">Eigendom van formulieren</span><span class="sxs-lookup"><span data-stu-id="08a52-324">Ownership of forms</span></span>

<span data-ttu-id="08a52-325">**Kan formulieren groepen maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-325">**Can Forms create a group?**</span></span>

<span data-ttu-id="08a52-326">Nee, formulieren kunnen geen groep maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-326">No, Forms cannot create a group.</span></span>

<span data-ttu-id="08a52-327">**Bestaan er formulieren zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-327">**Do forms exist without a group?**</span></span>

<span data-ttu-id="08a52-328">Ja, enquêtes en toetsen kunnen rechtstreeks worden gemaakt in het account van een eindgebruiker.</span><span class="sxs-lookup"><span data-stu-id="08a52-328">Yes, surveys and quizzes can be created directly in an end-user’s account.</span></span>

<span data-ttu-id="08a52-329">**Kunnen er meerdere formulieren per groep worden?**</span><span class="sxs-lookup"><span data-stu-id="08a52-329">**Can there be multiple forms per group?**</span></span>

<span data-ttu-id="08a52-330">Ja, er kunnen meerdere formulieren zijn die aan een groep zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-330">Yes, there can be multiple forms associated with a group.</span></span>

<span data-ttu-id="08a52-331">**Kunnen formulieren aan meerdere groepen worden gekoppeld?**</span><span class="sxs-lookup"><span data-stu-id="08a52-331">**Can forms be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-332">Nee, een formulier kan slechts aan één groep worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-332">No, a form can only be associated with a single group.</span></span>

<span data-ttu-id="08a52-333">**Kan de koppeling van een formulier met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-333">**Can a form’s association with a group change?**</span></span>

<span data-ttu-id="08a52-334">Nee, nadat een formulier is gekoppeld aan een groep (rechtstreeks binnen of eigenaar van een persoon die is overgebracht van een individu), kan het formulier niet worden verplaatst naar een andere groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-334">No, once a form is associated with a group (either created directly within, or ownership transferred from an individual) it cannot be moved to another group.</span></span>

<span data-ttu-id="08a52-335">**Verwijdert het formulier de groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-335">**Does deleting the form delete the group?**</span></span>

<span data-ttu-id="08a52-336">Nee, het is niet mogelijk om een groep uit de formulier interface te verwijderen, maar alleen afzonderlijke formulieren.</span><span class="sxs-lookup"><span data-stu-id="08a52-336">No, it is not possible to delete a group from the Forms interface, only individual forms.</span></span>

## <a name="onenote"></a><span data-ttu-id="08a52-337">OneNote</span><span class="sxs-lookup"><span data-stu-id="08a52-337">OneNote</span></span>

<span data-ttu-id="08a52-338">OneNote is een toepassing voor digitale notitieblokken.</span><span class="sxs-lookup"><span data-stu-id="08a52-338">OneNote is a digital notebook application.</span></span> <span data-ttu-id="08a52-339">Het OneNote-notitieblok dat is gemaakt met een groep, is een bestand in de bijbehorende SharePoint-site, in plaats van een service met een groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-339">The OneNote notebook created with a group is a file in the associated SharePoint site rather than a group-connected service.</span></span>

<span data-ttu-id="08a52-340">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-340">**Key features provided to groups**</span></span>

- <span data-ttu-id="08a52-341">Gedeeld notitieblok (opgeslagen in de door de groep gekoppelde SharePoint-bibliotheek)</span><span class="sxs-lookup"><span data-stu-id="08a52-341">Shared notebook (stored in the Group-associated SharePoint library)</span></span>

<span data-ttu-id="08a52-342">**Kan OneNote een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-342">**Can OneNote create a group?**</span></span>

<span data-ttu-id="08a52-343">Nee, u kunt geen groep maken met de OneNote-toepassing.</span><span class="sxs-lookup"><span data-stu-id="08a52-343">No, the OneNote application cannot create a group.</span></span>

<span data-ttu-id="08a52-344">**Bestaan er OneNote-notitieblokken zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-344">**Do OneNote notebooks exist without a group?**</span></span>

<span data-ttu-id="08a52-345">Ja, notitieblokken kunnen rechtstreeks worden gemaakt in OneDrive of op andere gedeelde locaties.</span><span class="sxs-lookup"><span data-stu-id="08a52-345">Yes, notebooks can be created directly in OneDrive or in other shared locations.</span></span>

<span data-ttu-id="08a52-346">**Kunnen er meerdere OneNote-notitieblokken per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-346">**Can there be multiple OneNote notebooks per group?**</span></span>

<span data-ttu-id="08a52-347">Ja, er is standaard een notitieblok gemaakt en anderen kunnen toevoegen, maar een koppeling naar OneNote uit met de groep gekoppelde services wordt altijd naar het standaardnotitieblok verzonden.</span><span class="sxs-lookup"><span data-stu-id="08a52-347">Yes, a notebook is created by default and others can be added, however any link to OneNote from group-associated services will always go to the default notebook.</span></span>

<span data-ttu-id="08a52-348">**Kan een OneNote-notitieblok worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-348">**Can a OneNote notebook be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-349">Nee, het notitieblok wordt opgeslagen in de door de groep gekoppelde SharePoint-site bibliotheek en gekoppeld aan diverse interfaces.</span><span class="sxs-lookup"><span data-stu-id="08a52-349">No, the notebook is stored in the group-associated SharePoint site library and linked from various interfaces.</span></span> <span data-ttu-id="08a52-350">Dit kan wel op dezelfde manier worden gedeeld met andere groepen, op dezelfde manier als met personen.</span><span class="sxs-lookup"><span data-stu-id="08a52-350">It can however be shared with other Groups in the same way it can be shared with individuals.</span></span>

<span data-ttu-id="08a52-351">**Kan de koppeling van het notitieblok met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-351">**Can the notebook’s association with a group change?**</span></span>

<span data-ttu-id="08a52-352">Nee, het notitieblok zelf is gekoppeld aan de groep en kan rechtstreeks worden geopend vanuit andere services die met een groep verbonden zijn, maar de inhoud kan worden verplaatst van het ene notitieblok naar het andere binnen de OneNote-toepassing.</span><span class="sxs-lookup"><span data-stu-id="08a52-352">No, the notebook itself is associated with the group and can be directly accessed from other group-connected services, however the content can be moved from one notebook to another within the OneNote application.</span></span>

<span data-ttu-id="08a52-353">**Verwijdert de groep als u het notitieblok verwijdert.**</span><span class="sxs-lookup"><span data-stu-id="08a52-353">**Does deleting the notebook delete the group?**</span></span>

<span data-ttu-id="08a52-354">Nee, maar als het OneNote-notitieblok wordt verwijderd, zijn er mogelijk verbroken koppelingen in enkele van de door de groep gekoppelde services.</span><span class="sxs-lookup"><span data-stu-id="08a52-354">No, however if the OneNote notebook is deleted there may be broken links in some of the group-associated services.</span></span>

## <a name="planner"></a><span data-ttu-id="08a52-355">Planner</span><span class="sxs-lookup"><span data-stu-id="08a52-355">Planner</span></span>

<span data-ttu-id="08a52-356">Planner is een lichtgewicht service voor groepsbeheer.</span><span class="sxs-lookup"><span data-stu-id="08a52-356">Planner is a lightweight  group task management service.</span></span>

<span data-ttu-id="08a52-357">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-357">**Key features provided to groups**</span></span>

- <span data-ttu-id="08a52-358">Bord voor het beheren van groeps taken</span><span class="sxs-lookup"><span data-stu-id="08a52-358">Board for managing group tasks</span></span>

<span data-ttu-id="08a52-359">**Kan planner een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-359">**Can Planner create a group?**</span></span>

<span data-ttu-id="08a52-360">Ja, het maken van een plan maakt een nieuwe groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-360">Yes, creation of a plan will create a new group.</span></span>

<span data-ttu-id="08a52-361">**Bestaat er een planner-bord zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-361">**Does a Planner board exist without a group?**</span></span>

<span data-ttu-id="08a52-362">Nee, een plan moet zijn gekoppeld aan een groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-362">No, a plan must be associated with a group.</span></span>

<span data-ttu-id="08a52-363">**Kunnen er meerdere abonnementen per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-363">**Can there be multiple plans per group?**</span></span>

<span data-ttu-id="08a52-364">Ja, er kunnen meerdere abonnementen per groep zijn.</span><span class="sxs-lookup"><span data-stu-id="08a52-364">Yes, there can be multiple plans per group.</span></span>

<span data-ttu-id="08a52-365">**Kan een plan worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-365">**Can a plan be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-366">Nee, op basis van het groepslidmaatschap moet het groepslidmaatschap de toegang bepalen.</span><span class="sxs-lookup"><span data-stu-id="08a52-366">No, a plan relies solely on the group membership to determine access.</span></span>

<span data-ttu-id="08a52-367">**Kan de koppeling van een plan met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-367">**Can a plan’s association with a group change?**</span></span>

<span data-ttu-id="08a52-368">Nee, als u een plan kopieert, wordt een nieuwe groep gemaakt.</span><span class="sxs-lookup"><span data-stu-id="08a52-368">No, however copying a plan creates a new group.</span></span>

> [!NOTE]
> <span data-ttu-id="08a52-369">Een groep die door een andere toepassing is gemaakt, wordt niet automatisch weergegeven in planner voor een gebruiker.</span><span class="sxs-lookup"><span data-stu-id="08a52-369">A Group created by any other application will not show up in Planner automatically for a user.</span></span> <span data-ttu-id="08a52-370">Om het bord in eerste instantie te openen, moeten ze dit openen vanuit een andere op de groep gebaseerde interface, zoals Outlook.</span><span class="sxs-lookup"><span data-stu-id="08a52-370">To access the board initially they will need to open it from another Group-based interface such as Outlook.</span></span>

<span data-ttu-id="08a52-371">**Wordt de groep verwijderd wanneer u het abonnement verwijdert?**</span><span class="sxs-lookup"><span data-stu-id="08a52-371">**Does deleting the plan delete the group?**</span></span>

<span data-ttu-id="08a52-372">Ja, als u een plan verwijdert, worden de services en inhoud van de groep en groep verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-372">Yes, deleting the plan will delete the group and group-associated services and content.</span></span>

## <a name="power-apps"></a><span data-ttu-id="08a52-373">Power-apps</span><span class="sxs-lookup"><span data-stu-id="08a52-373">Power Apps</span></span>

<span data-ttu-id="08a52-374">Power-apps bieden een canvas voor het ontwikkelen van apps zonder code.</span><span class="sxs-lookup"><span data-stu-id="08a52-374">Power Apps provides a canvas for app development without code.</span></span>

<span data-ttu-id="08a52-375">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-375">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-376">Apps kunnen worden gedeeld met een groep die moet worden uitgevoerd en gewijzigd</span><span class="sxs-lookup"><span data-stu-id="08a52-376">Apps can be shared with a group to be run and modified</span></span>

<span data-ttu-id="08a52-377">**Kunnen Power-apps groepen maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-377">**Can Power Apps create a group?**</span></span>

<span data-ttu-id="08a52-378">Nee, Power-apps kunnen geen Microsoft 365-groep maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-378">No, Power Apps cannot create a Microsoft 365 group.</span></span>

<span data-ttu-id="08a52-379">**Bestaan er Power-apps zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-379">**Do Power Apps exist without a group?**</span></span>

<span data-ttu-id="08a52-380">Ja, apps kunnen worden gemaakt binnen Power-apps en opgeslagen in het account Creators totdat ze worden gedeeld of gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="08a52-380">Yes, apps can be created within Power Apps and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="08a52-381">**Kunnen er meerdere apps per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-381">**Can there be multiple apps per group?**</span></span>

<span data-ttu-id="08a52-382">Ja, er kunnen meerdere apps met een groep worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-382">Yes, there can be multiple apps shared with a group.</span></span>

<span data-ttu-id="08a52-383">**Kunnen apps worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-383">**Can apps be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-384">Ja, een app kan worden gedeeld met meerdere groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-384">Yes, an app can be shared with multiple groups.</span></span>

<span data-ttu-id="08a52-385">**Kan de koppeling van een app met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-385">**Can an app’s association with a group change?**</span></span>

<span data-ttu-id="08a52-386">Ja, aangezien de koppeling tussen Power-apps en een Microsoft 365-groep alleen delen is, is de app nog steeds bij de maker.</span><span class="sxs-lookup"><span data-stu-id="08a52-386">Yes, as the association between Power Apps and a Microsoft 365 group is sharing only – the app still resides with the creator.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08a52-387">[Voor groepen moet beveiliging zijn ingeschakeld voordat apps kunnen worden gedeeld](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span><span class="sxs-lookup"><span data-stu-id="08a52-387">[Groups must be security enabled before apps can be shared with them](https://docs.microsoft.com/powerapps/maker/canvas-apps/share-app#share-an-app-with-office-365-groups).</span></span>

<span data-ttu-id="08a52-388">**Verwijdert de app in de groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-388">**Does deleting the app delete the group?**</span></span>

<span data-ttu-id="08a52-389">Nee, de apps zijn niet verbonden met de groep die u met hen deelt.</span><span class="sxs-lookup"><span data-stu-id="08a52-389">No, the apps are not connected to the group other than being shared with them.</span></span>

## <a name="power-automate"></a><span data-ttu-id="08a52-390">Automatisch aan de macht</span><span class="sxs-lookup"><span data-stu-id="08a52-390">Power Automate</span></span>

<span data-ttu-id="08a52-391">Automatisch automatiseren (voorheen bekend als Microsoft flow) levert werkstromen en automatiserings Services.</span><span class="sxs-lookup"><span data-stu-id="08a52-391">Power Automate (formerly known as Microsoft Flow) provides workflows and automation services.</span></span>

<span data-ttu-id="08a52-392">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-392">**Key features provided to groups**</span></span>

- <span data-ttu-id="08a52-393">U kunt werkstromen delen met een groep om deze uit te voeren en te wijzigen.</span><span class="sxs-lookup"><span data-stu-id="08a52-393">Workflows can be shared with a group to be run and modified.</span></span>

<span data-ttu-id="08a52-394">**Kan de groep een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-394">**Can Power Automate create a group?**</span></span>

<span data-ttu-id="08a52-395">Nee, automatisch automatiseren kan geen Microsoft 365-groep maken in de context van het bestand dat is gekoppeld aan een groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-395">No, Power Automate cannot create a Microsoft 365 group in the context of being associated with one.</span></span>

<span data-ttu-id="08a52-396">Het is ook mogelijk om een stroom te creëren waarmee verschillende bewerkingen worden uitgevoerd, zoals het maken van een Azure AD-beveiligingsgroep of het bijwerken van lidmaatschap van een groep van Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="08a52-396">It is possible however to create a flow that performs various operations such as creating an Azure AD security group or updating membership of a Microsoft 365 group.</span></span>

<span data-ttu-id="08a52-397">**Bestaan er stromen zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-397">**Do flows exist without a group?**</span></span>

<span data-ttu-id="08a52-398">Ja, stromen kunnen worden gemaakt binnen het automatiseren van de toepassing en bevinden zich in het account Creators totdat ze worden gedeeld of gepubliceerd.</span><span class="sxs-lookup"><span data-stu-id="08a52-398">Yes, flows can be created within Power Automate and reside within the creators account until shared or published.</span></span>

<span data-ttu-id="08a52-399">**Kunnen er meerdere stromen per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-399">**Can there be multiple flows per group?**</span></span>

<span data-ttu-id="08a52-400">Ja, er kunnen meerdere stromen met een groep worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-400">Yes, there can be multiple flows shared with a group.</span></span>

<span data-ttu-id="08a52-401">**Kan een stroom worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-401">**Can a flow be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-402">Ja, een stroom kan worden gedeeld met meerdere groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-402">Yes, a flow can be shared with multiple groups.</span></span>

<span data-ttu-id="08a52-403">**Kan een stroom koppeling met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-403">**Can a flow’s association with a group change?**</span></span>

<span data-ttu-id="08a52-404">Ja, aangezien de koppeling tussen het automatiseren van de werkstroom en een Microsoft 365-groep alleen delen is, is de stroom nog niet inbegrepen bij de auteur.</span><span class="sxs-lookup"><span data-stu-id="08a52-404">Yes, as the association between Power Automate and a Microsoft 365 group is sharing only – the flow still resides with the creator.</span></span>

<span data-ttu-id="08a52-405">**Verwijdert de groep verwijderen als u een stroom verwijdert.**</span><span class="sxs-lookup"><span data-stu-id="08a52-405">**Does deleting a flow delete the group?**</span></span>

<span data-ttu-id="08a52-406">Nee, zoals Power-apps, zijn de stromen niet verbonden met de groep die u met hen deelt.</span><span class="sxs-lookup"><span data-stu-id="08a52-406">No, like Power Apps, the flows are not connected to the group other than being shared with them.</span></span>

## <a name="power-bi-classic"></a><span data-ttu-id="08a52-407">Power BI (klassiek)</span><span class="sxs-lookup"><span data-stu-id="08a52-407">Power BI (classic)</span></span>

<span data-ttu-id="08a52-408">Power BI biedt interactieve dashboards en rapporten van gegevensgestuurde gegevens.</span><span class="sxs-lookup"><span data-stu-id="08a52-408">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="08a52-409">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-409">**Key features provided to groups**</span></span>

- <span data-ttu-id="08a52-410">Gegevensrapportage</span><span class="sxs-lookup"><span data-stu-id="08a52-410">Data reporting</span></span>

<span data-ttu-id="08a52-411">**Kan Power BI een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-411">**Can Power BI create a group?**</span></span>

<span data-ttu-id="08a52-412">Ja, als u een klassieke werkruimte maakt, wordt een Microsoft 365-groep gemaakt.</span><span class="sxs-lookup"><span data-stu-id="08a52-412">Yes, creating a classic workspace will create a Microsoft 365 group.</span></span>

<span data-ttu-id="08a52-413">**Bestaat er een klassieke werkruimte van Power BI zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-413">**Does a Power BI classic workspace exist without a group?**</span></span>

<span data-ttu-id="08a52-414">Nee, [in Power bi een klassieke werkruimte moet zijn gekoppeld aan een groep](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span><span class="sxs-lookup"><span data-stu-id="08a52-414">No, [a classic workspace in Power BI must be associated with a group](https://docs.microsoft.com/power-bi/collaborate-share/service-collaborate-power-bi-workspace).</span></span>

<span data-ttu-id="08a52-415">**Kunnen er meerdere Power BI-werkruimten per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-415">**Can there be multiple Power BI workspaces per group?**</span></span>

<span data-ttu-id="08a52-416">Nee, de relatie tussen een klassieke werkruimte en een groep is 1:1.</span><span class="sxs-lookup"><span data-stu-id="08a52-416">No, the relationship between a classic workspace and a group is 1:1.</span></span>

<span data-ttu-id="08a52-417">**Kan een werkruimte aan meerdere groepen worden gekoppeld?**</span><span class="sxs-lookup"><span data-stu-id="08a52-417">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-418">Technisch Nee, terwijl de klassieke werkruimte met de groep wordt gemaakt, kan de inhoud buiten de groep worden gedeeld met gebruikers en beveiligingsgroepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-418">Technically no, while the classic workspace is created with the group, the content can be shared outside of the Group with users and security groups.</span></span>

<span data-ttu-id="08a52-419">**Kan de koppeling van de werkruimte met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-419">**Can the workspace's association with a group change?**</span></span>

<span data-ttu-id="08a52-420">Nee, de klassieke werkruimte zelf is niet gekoppeld aan de groep, maar de inhoud kan worden verplaatst van de ene naar de andere werkruimte in de Power BI-interface of door de inhoud lokaal te exporteren.</span><span class="sxs-lookup"><span data-stu-id="08a52-420">No, the classic workspace itself is associated with the Group, however the content can be moved from one workspace to another within the Power BI interface or by exporting contents locally.</span></span>

<span data-ttu-id="08a52-421">**Verwijdert de groep uit de werkruimte?**</span><span class="sxs-lookup"><span data-stu-id="08a52-421">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="08a52-422">Ja, als u de werkruimte in Power BI verwijdert, wordt de groep en de gekoppelde services en inhoud verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-422">Yes, deleting the workspace in Power BI will delete group and  group-associated services and content.</span></span>

## <a name="power-bi-new"></a><span data-ttu-id="08a52-423">Power BI (nieuw)</span><span class="sxs-lookup"><span data-stu-id="08a52-423">Power BI (new)</span></span>

<span data-ttu-id="08a52-424">Power BI biedt interactieve dashboards en rapporten van gegevensgestuurde gegevens.</span><span class="sxs-lookup"><span data-stu-id="08a52-424">Power BI provides interactive data-driven dashboards and reports.</span></span>

<span data-ttu-id="08a52-425">Tijdens het maken van een nieuwe werkruimte in Power BI is geen Microsoft 365-groep gemaakt, wat betekent dat een groep op andere manieren een nieuwe (niet Classic) werkruimte in Power BI maakt.</span><span class="sxs-lookup"><span data-stu-id="08a52-425">While creating a new workspace in Power BI does not create a Microsoft 365 Group, creating a group by any other means creates a  new (not classic) workspace in Power BI.</span></span>

<span data-ttu-id="08a52-426">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-426">**Key features provided to groups**</span></span>

- <span data-ttu-id="08a52-427">Gegevensrapportage</span><span class="sxs-lookup"><span data-stu-id="08a52-427">Data reporting</span></span>

<span data-ttu-id="08a52-428">**Kan Power BI een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-428">**Can Power BI create a group?**</span></span>

<span data-ttu-id="08a52-429">Nee, het is niet mogelijk om een Microsoft 365-groep te maken op basis van de nieuwe Power BI-interface.</span><span class="sxs-lookup"><span data-stu-id="08a52-429">No, it is not possible to create a Microsoft 365 group from the new Power BI interface.</span></span>

<span data-ttu-id="08a52-430">**Bestaat de nieuwe Power BI-werkruimte zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-430">**Does the new Power BI workspace exist without a group?**</span></span>

<span data-ttu-id="08a52-431">Ja, het is mogelijk dat u rapporten en werkruimten die zijn gemaakt in Power BI, hebt gemaakt die niet zijn gekoppeld aan Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-431">Yes, it is possible to have reports and workspaces created in Power BI that are not associated with Microsoft 365 groups.</span></span>

<span data-ttu-id="08a52-432">**Kunnen er meerdere werkruimten per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-432">**Can there be multiple workspaces per group?**</span></span>

<span data-ttu-id="08a52-433">Ja, u [kunt meerdere werkruimten die zijn gemaakt met Power bi, delen met een enkele groep](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span><span class="sxs-lookup"><span data-stu-id="08a52-433">Yes, [multiple workspaces created by Power BI can be shared with a single group](https://docs.microsoft.com/power-bi/collaborate-share/service-create-the-new-workspaces#give-access-to-your-workspace).</span></span>

<span data-ttu-id="08a52-434">**Kan een werkruimte aan meerdere groepen worden gekoppeld?**</span><span class="sxs-lookup"><span data-stu-id="08a52-434">**Can a workspace be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-435">Nee, een werkruimte die u hebt gemaakt met Power BI, kan slechts aan één groep worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-435">No, a workspace created by Power BI can only be associated with a single group.</span></span>

<span data-ttu-id="08a52-436">**Kan de koppeling van een werkruimte met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-436">**Can a workspace's association with a group change?**</span></span>

<span data-ttu-id="08a52-437">Ja en Nee.</span><span class="sxs-lookup"><span data-stu-id="08a52-437">Yes and no.</span></span> <span data-ttu-id="08a52-438">Een werkruimte die u hebt gemaakt met Power BI, kan slechts aan één groep tegelijk worden gekoppeld, maar de koppeling kan op elk moment worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="08a52-438">A workspace created by Power BI can only be associated with a single group at a time but can change the association at any time.</span></span> <span data-ttu-id="08a52-439">Een werkruimte die is gemaakt in Power BI door een groep, wordt permanent aan die groep gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-439">A workspace created in Power BI by a group is permanently associated to that group.</span></span>

<span data-ttu-id="08a52-440">**Verwijdert de groep uit de werkruimte?**</span><span class="sxs-lookup"><span data-stu-id="08a52-440">**Does deleting the workspace delete the group?**</span></span>

<span data-ttu-id="08a52-441">Ja, als u de werkruimte in Power BI verwijdert, worden de services en inhoud die aan de groep zijn gekoppeld, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-441">Yes, deleting the workspace in Power BI will delete the group and group-associated services and content.</span></span>

## <a name="project-for-the-web"></a><span data-ttu-id="08a52-442">Project voor het web</span><span class="sxs-lookup"><span data-stu-id="08a52-442">Project for the web</span></span>

<span data-ttu-id="08a52-443">Project voor het web biedt de mogelijkheid om project plannen, Gantt-diagrammen en routekaarten te maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-443">Project for the web offers the ability to create project plans, Gantt charts, and roadmaps.</span></span>
<span data-ttu-id="08a52-444">Belangrijkste functies van groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-444">Key features provided to groups.</span></span>

- <span data-ttu-id="08a52-445">Project plannen</span><span class="sxs-lookup"><span data-stu-id="08a52-445">Project plans</span></span>

<span data-ttu-id="08a52-446">**Kan project een groep maken voor het web?**</span><span class="sxs-lookup"><span data-stu-id="08a52-446">**Can Project for the web create a group?**</span></span>

<span data-ttu-id="08a52-447">Ja, het is mogelijk om rechtstreeks vanuit project voor het web een nieuwe Microsoft 365-groep te maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-447">Yes, it is possible to create a new Microsoft 365 group directly from Project for the web.</span></span>

<span data-ttu-id="08a52-448">**Bestaan er projecten zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-448">**Do projects exist without a group?**</span></span>

<span data-ttu-id="08a52-449">Ja, projecten kunnen bestaan zonder dat ze zijn gekoppeld aan een Microsoft 365-groep, maar de toewijzing van taken vereist groeps koppeling.</span><span class="sxs-lookup"><span data-stu-id="08a52-449">Yes, projects can exist without being associated with a Microsoft 365 group, however assignment of tasks requires group association.</span></span>

<span data-ttu-id="08a52-450">**Kunnen er meerdere projecten per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-450">**Can there be multiple projects per group?**</span></span>

<span data-ttu-id="08a52-451">Ja, het is mogelijk om meerdere projecten in één groep te verbinden.</span><span class="sxs-lookup"><span data-stu-id="08a52-451">Yes, it is possible to connect multiple projects in a single group.</span></span>

<span data-ttu-id="08a52-452">**Kan project worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-452">**Can project be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-453">Nee, een project kan slechts aan één groep worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-453">No, a project can only be associated with a single group.</span></span>

<span data-ttu-id="08a52-454">**Kan de koppeling van een project met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-454">**Can a project’s association with a group change?**</span></span>

<span data-ttu-id="08a52-455">Nee, als de koppeling met een groep is gemaakt, kan deze niet worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="08a52-455">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="08a52-456">**Verwijdert het project de groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-456">**Does deleting the project delete the group?**</span></span>

<span data-ttu-id="08a52-457">Nee, als u het project verwijdert in project voor het web, wordt de groep niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-457">No, deleting the project in Project for the web will not delete the group.</span></span>

## <a name="roadmap"></a><span data-ttu-id="08a52-458">Routekaart</span><span class="sxs-lookup"><span data-stu-id="08a52-458">Roadmap</span></span>

<span data-ttu-id="08a52-459">Routekaart biedt de mogelijkheid project plannen te maken met project voor Internet en project online.</span><span class="sxs-lookup"><span data-stu-id="08a52-459">Roadmap provides the ability to create project roadmaps with Project for the web and Project Online.</span></span>

<span data-ttu-id="08a52-460">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-460">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-461">Project plannen</span><span class="sxs-lookup"><span data-stu-id="08a52-461">Project roadmaps</span></span>

<span data-ttu-id="08a52-462">**Kan een routekaart een groep maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-462">**Can Roadmap create a group?**</span></span>

<span data-ttu-id="08a52-463">Ja, het is mogelijk om rechtstreeks vanuit een routekaart een nieuwe Microsoft 365-groep te maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-463">Yes, it is possible to create a new Microsoft 365 group directly from roadmap.</span></span>

<span data-ttu-id="08a52-464">**Bestaat zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-464">**Does Roadmap exist without a group?**</span></span>

<span data-ttu-id="08a52-465">Ja, route plannen kunnen bestaan zonder dat ze zijn gekoppeld aan een groep van Microsoft 365, maar het delen van de routekaart vereist groeps koppeling.</span><span class="sxs-lookup"><span data-stu-id="08a52-465">Yes, roadmaps can exist without being associated with a Microsoft 365 group, however sharing the roadmap requires group association.</span></span>

<span data-ttu-id="08a52-466">**Kunnen er meerdere route plannen per groep zijn?**</span><span class="sxs-lookup"><span data-stu-id="08a52-466">**Can there be multiple roadmaps per group?**</span></span>

<span data-ttu-id="08a52-467">Ja, het is mogelijk om meerdere route plannen te verbinden met een enkele groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-467">Yes, it is possible to connect multiple roadmaps to a single group.</span></span>

<span data-ttu-id="08a52-468">**Kan een routekaart worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-468">**Can a roadmap be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-469">Nee, een routekaart kan maar aan één groep worden gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-469">No, a roadmap can only be associated with a single group.</span></span>

<span data-ttu-id="08a52-470">**Kan ik de koppeling van een routekaart met een groep wijzigen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-470">**Can a roadmap's association with a group change?**</span></span>

<span data-ttu-id="08a52-471">Nee, als de koppeling met een groep is gemaakt, kan deze niet worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="08a52-471">No, once the association with a group is established, it cannot change.</span></span>

<span data-ttu-id="08a52-472">**Verwijdert de groep als u het wegwijzer verwijdert.**</span><span class="sxs-lookup"><span data-stu-id="08a52-472">**Does deleting the roadmap delete the group?**</span></span>

<span data-ttu-id="08a52-473">Nee, als u het routekaart verwijdert, wordt de groep niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-473">No, deleting the roadmap will not delete the group.</span></span>

## <a name="sharepoint"></a><span data-ttu-id="08a52-474">SharePoint</span><span class="sxs-lookup"><span data-stu-id="08a52-474">SharePoint</span></span>

<span data-ttu-id="08a52-475">SharePoint is een systeem voor inhoudsbeheer op basis van andere zaken, opslagservices voor een aantal Microsoft 365-Services.</span><span class="sxs-lookup"><span data-stu-id="08a52-475">SharePoint is a web-based content management platform that provides among other things, storage services for a number of Microsoft 365 services.</span></span>

<span data-ttu-id="08a52-476">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-476">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-477">Document bibliotheek</span><span class="sxs-lookup"><span data-stu-id="08a52-477">Document library</span></span>
- <span data-ttu-id="08a52-478">Bibliotheek voor het opslaan van OneNote-notitieblokken</span><span class="sxs-lookup"><span data-stu-id="08a52-478">Library for storage of OneNote notebook</span></span>
- <span data-ttu-id="08a52-479">Opslag van teams-wiki-bestanden</span><span class="sxs-lookup"><span data-stu-id="08a52-479">Storage of Teams wiki files</span></span>

<span data-ttu-id="08a52-480">**Kan een groep worden gemaakt in SharePoint?**</span><span class="sxs-lookup"><span data-stu-id="08a52-480">**Can SharePoint create a group?**</span></span>

<span data-ttu-id="08a52-481">Ja, als u een team site maakt in SharePoint, wordt standaard een Microsoft 365-groep gemaakt.</span><span class="sxs-lookup"><span data-stu-id="08a52-481">Yes, creating a team site in SharePoint will create a Microsoft 365 group by default.</span></span> <span data-ttu-id="08a52-482">Het is ook mogelijk om een groep te maken en desgewenst een team voor een bestaande site te maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-482">It is also possible to create a group and, optionally, a team for an existing site.</span></span>

<span data-ttu-id="08a52-483">**Bestaan er SharePoint-sites zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-483">**Do SharePoint sites exist without a group?**</span></span>

<span data-ttu-id="08a52-484">Ja, SharePoint biedt een aantal niet-door de groep gekoppelde services en sites zoals communicatie-en hub-sites.</span><span class="sxs-lookup"><span data-stu-id="08a52-484">Yes, SharePoint offers a number of non-group-associated services and sites such as communication and hub sites.</span></span> 

<span data-ttu-id="08a52-485">**Kunnen er meerdere sites per groep worden?**</span><span class="sxs-lookup"><span data-stu-id="08a52-485">**Can there be multiple sites per group?**</span></span>

<span data-ttu-id="08a52-486">Nee, u kunt maar één site per groep hebben.</span><span class="sxs-lookup"><span data-stu-id="08a52-486">No, there can only be a single site per group.</span></span> <span data-ttu-id="08a52-487">Persoonlijke kanalen in teams gebruiken andere sites die niet zijn verbonden met de groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-487">Private channels in Teams use additional sites that are not connected to the group.</span></span>

<span data-ttu-id="08a52-488">**Kunnen sites aan meerdere groepen worden gekoppeld?**</span><span class="sxs-lookup"><span data-stu-id="08a52-488">**Can sites be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-489">Technisch Nee, maar wanneer een site met een groep wordt gemaakt, kan de inhoud met andere groepen worden gedeeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-489">Technically no, but while a site is created with a group, the content can be shared with other groups.</span></span>

<span data-ttu-id="08a52-490">**Kan de koppeling van een site met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-490">**Can a site’s association with a group change?**</span></span>

<span data-ttu-id="08a52-491">Nee, de site zelf is niet gekoppeld aan de groep, maar de inhoud kan worden verplaatst van de ene site naar de andere in de SharePoint-interface, door inhoud lokaal te exporteren of door middel van een programma van derden.</span><span class="sxs-lookup"><span data-stu-id="08a52-491">No, the site itself is associated with the group, however the content can be moved from one site to another within the SharePoint interface, by exporting content locally, or by using a third-party tool.</span></span>

<span data-ttu-id="08a52-492">**Verwijdert de groep uit de site?**</span><span class="sxs-lookup"><span data-stu-id="08a52-492">**Does deleting the site delete the group?**</span></span>

<span data-ttu-id="08a52-493">Ja, als u de site in SharePoint verwijdert, worden de services en de gekoppelde services en de bijbehorende groepen verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-493">Yes, deleting the site in SharePoint will delete group and group-associated services and content.</span></span>

## <a name="stream"></a><span data-ttu-id="08a52-494">Stream</span><span class="sxs-lookup"><span data-stu-id="08a52-494">Stream</span></span>

<span data-ttu-id="08a52-495">Microsoft stream is een video-hosting en deel platform.</span><span class="sxs-lookup"><span data-stu-id="08a52-495">Microsoft Stream is a video hosting and sharing platform.</span></span>

<span data-ttu-id="08a52-496">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-496">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-497">Video-opslag</span><span class="sxs-lookup"><span data-stu-id="08a52-497">Video storage</span></span>
- <span data-ttu-id="08a52-498">Opname van teams-vergadering</span><span class="sxs-lookup"><span data-stu-id="08a52-498">Teams meeting recording</span></span>
- <span data-ttu-id="08a52-499">Video kanalen</span><span class="sxs-lookup"><span data-stu-id="08a52-499">Video channels</span></span>

<span data-ttu-id="08a52-500">**Kan stream maken van een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-500">**Can Stream create a group?**</span></span>

<span data-ttu-id="08a52-501">Ja, het is mogelijk om rechtstreeks vanuit de stroom een nieuwe Microsoft 365-groep te maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-501">Yes, it is possible to create a new Microsoft 365 group directly from Stream.</span></span>

<span data-ttu-id="08a52-502">**Bestaat de stream zonder een groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-502">**Does Stream exist without a group?**</span></span>

<span data-ttu-id="08a52-503">Ja, videokanalen en Video's kunnen bestaan in stream zonder dat ze aan een groep zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-503">Yes, video channels and videos can exist in Stream without being associated with a group.</span></span>

<span data-ttu-id="08a52-504">**Kunnen er meerdere Video's en kanalen per groep worden toegevoegd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-504">**Can there be multiple videos and channels per Group?**</span></span>

<span data-ttu-id="08a52-505">Ja, er kunnen meerdere Video's en kanalen in elke groep worden toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="08a52-505">Yes, there can be multiple videos and channels in each group.</span></span>

<span data-ttu-id="08a52-506">**Kan een video of kanaal worden gekoppeld aan meerdere groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-506">**Can a video or channel be associated with multiple groups?**</span></span>

<span data-ttu-id="08a52-507">Ja, terwijl een video of kanaal wordt gemaakt met een groep, kunt u het bestanddelen met andere groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-507">Yes, while a video or channel is created with a group, it can be shared with other groups.</span></span>

<span data-ttu-id="08a52-508">**Kan de koppeling met een groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-508">**Can its association with a Group change?**</span></span>

<span data-ttu-id="08a52-509">Ja en Nee; Video's in de stroom zijn eigendom van de oorspronkelijke Uploader of vergaderings recorder, en kunnen dus aan een willekeurige groep worden gekoppeld, maar u kunt alleen videokanalen koppelen aan de groep waarin ze oorspronkelijk zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="08a52-509">Yes and no; videos in Stream are owned by the original uploader or meeting recorder and so can be associated with any group, however video channels can only be associated with the group they were originally created in.</span></span>

<span data-ttu-id="08a52-510">**Verwijdert de groep als u Video's of kanalen verwijdert?**</span><span class="sxs-lookup"><span data-stu-id="08a52-510">**Does deleting videos or channels delete the group?**</span></span>

<span data-ttu-id="08a52-511">Nee, Video's of kanalen verwijderen niet de groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-511">No, deleting videos or channels doesn’t delete the group.</span></span> <span data-ttu-id="08a52-512">Als u echter de groep zelf verwijdert, worden de services en inhoud van de groep verwijderd, met uitzondering van de feitelijke Video's.</span><span class="sxs-lookup"><span data-stu-id="08a52-512">However, deleting the group itself in Stream will delete group-associated services and content, except for the actual videos.</span></span>

## <a name="yammer"></a><span data-ttu-id="08a52-513">Yammer</span><span class="sxs-lookup"><span data-stu-id="08a52-513">Yammer</span></span>

<span data-ttu-id="08a52-514">Yammer is een sociaal platform dat is ontworpen voor de bevordering van de betrokkenheid van community's binnen en tussen organisaties.</span><span class="sxs-lookup"><span data-stu-id="08a52-514">Yammer is an enterprise social platform designed to foster community engagement within and between organizations.</span></span>

<span data-ttu-id="08a52-515">Door een community te maken (voorheen bekend als ' groep ') in Yammer wordt een postvak gemaakt, maar dit wordt niet in de huidige weergave gebruikt.</span><span class="sxs-lookup"><span data-stu-id="08a52-515">Creating a community (formerly known as “group”) in Yammer creates a mailbox, but at present this is not used.</span></span>

<span data-ttu-id="08a52-516">Een Microsoft 365-groep die is gekoppeld aan Yammer, kan niet worden gebruikt met een team in Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="08a52-516">A Microsoft 365 group that is associated with Yammer cannot be used with a team in Microsoft Teams.</span></span>

<span data-ttu-id="08a52-517">**Belangrijkste functies die beschikbaar zijn voor groepen**</span><span class="sxs-lookup"><span data-stu-id="08a52-517">**Key features provided to Groups**</span></span>

- <span data-ttu-id="08a52-518">Gespreks gebied</span><span class="sxs-lookup"><span data-stu-id="08a52-518">Conversation area</span></span>

<span data-ttu-id="08a52-519">**Kan Yammer een groep Microsoft 365 maken?**</span><span class="sxs-lookup"><span data-stu-id="08a52-519">**Can Yammer create a Microsoft 365 group?**</span></span>

<span data-ttu-id="08a52-520">Ja, als u een nieuwe groep maakt in Yammer, maakt u een nieuwe groep Microsoft 365, als de platforms verbonden zijn en de gebruiker de mogelijkheid heeft om een groep te maken.</span><span class="sxs-lookup"><span data-stu-id="08a52-520">Yes, creating a new group in Yammer will create a new Microsoft 365 group, if the platforms are connected and the user has the ability to create a group.</span></span>

<span data-ttu-id="08a52-521">Een Yammer-groep met gekoppelde Microsoft 365-groep kan niet worden gemaakt in een andere interface of service dan Yammer zelf.</span><span class="sxs-lookup"><span data-stu-id="08a52-521">A Yammer group with associated Microsoft 365 group cannot be created in any interface or service other than Yammer itself.</span></span>

<span data-ttu-id="08a52-522">**Bestaat er een Yammer-groep zonder een Microsoft 365-groep?**</span><span class="sxs-lookup"><span data-stu-id="08a52-522">**Does a Yammer group exist without a Microsoft 365 group?**</span></span>

<span data-ttu-id="08a52-523">Ja, het is mogelijk om een Yammer-groep te maken zonder een Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-523">Yes, it is possible to create a Yammer group without a Microsoft 365 group.</span></span>

<span data-ttu-id="08a52-524">Als het Yammer-platform niet is verbonden met Microsoft 365-groepen of gebruikers geen toegang hebben tot de groep Microsoft 365, worden Yammer-groepen gemaakt zonder een Microsoft 365-groeps koppeling.</span><span class="sxs-lookup"><span data-stu-id="08a52-524">If the Yammer platform is not connected to Microsoft 365 groups, or users do not have the ability to create a Microsoft 365 group, Yammer groups are created without a Microsoft 365 group association.</span></span>

<span data-ttu-id="08a52-525">**Kunnen er meerdere Yammer-groepen per Microsoft 365-groep worden?**</span><span class="sxs-lookup"><span data-stu-id="08a52-525">**Can there be multiple Yammer groups per Microsoft 365 group?**</span></span>

<span data-ttu-id="08a52-526">Nee, de relatie tussen een Yammer-groep en een Microsoft 365-groep is 1:1.</span><span class="sxs-lookup"><span data-stu-id="08a52-526">No, the relationship between a Yammer group and a Microsoft 365 group is 1:1.</span></span>

<span data-ttu-id="08a52-527">**Kan een Yammer-groep worden gekoppeld aan meerdere Microsoft 365-groepen?**</span><span class="sxs-lookup"><span data-stu-id="08a52-527">**Can a Yammer group be associated with multiple Microsoft 365 groups?**</span></span>

<span data-ttu-id="08a52-528">Nee, de Yammer-groep kan alleen worden gekoppeld aan één Microsoft 365-groep.</span><span class="sxs-lookup"><span data-stu-id="08a52-528">No, the Yammer group can only be associated with a single Microsoft 365 group.</span></span> <span data-ttu-id="08a52-529">Het is mogelijk dat berichten worden gedeeld met of verplaatst naar andere Yammer-groepen.</span><span class="sxs-lookup"><span data-stu-id="08a52-529">It is possible for posts to be shared with or moved to other Yammer groups.</span></span>

<span data-ttu-id="08a52-530">**Kan de koppeling van een Yammer-groep met een Microsoft 365-groep worden gewijzigd?**</span><span class="sxs-lookup"><span data-stu-id="08a52-530">**Can a Yammer group’s association with a Microsoft 365 group change?**</span></span>

<span data-ttu-id="08a52-531">Nee, de Yammer-groep kan maar ooit worden gekoppeld aan de Microsoft 365-groep waaraan deze oorspronkelijk is gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="08a52-531">No, the Yammer group can only ever be associated with the Microsoft 365 group to which it was originally associated.</span></span>

<span data-ttu-id="08a52-532">**Verwijdert de Yammer-groep de groep Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="08a52-532">**Does deleting the Yammer group delete the Microsoft 365 group?**</span></span>

<span data-ttu-id="08a52-533">Ja, als u de groep in Yammer verwijdert, worden verwante Microsoft-groepen en door groepen gekoppelde services en inhoud verwijderd.</span><span class="sxs-lookup"><span data-stu-id="08a52-533">Yes, deleting the group in Yammer will delete related Microsoft group and group-associated services and content.</span></span>

