---
title: Exchange-beheercentrum in Exchange Online Protection
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Het Exchange-beheercentrum (EAC) is de webgebaseerde beheerconsole voor Microsoft Exchange Online Protection (EOP).
ms.openlocfilehash: 3b5fb014e56a9928d58abffd5e4c96e1eef463ad
ms.sourcegitcommit: 9224a7a5886c0c5fa0bc12bd9f7234a0eba90023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42812426"
---
# <a name="exchange-admin-center-in-exchange-online-protection"></a><span data-ttu-id="e0472-103">Exchange-beheercentrum in Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0472-103">Exchange admin center in Exchange Online Protection</span></span>

<span data-ttu-id="e0472-104">Het Exchange-beheercentrum (EAC) is de webgebaseerde beheerconsole voor Microsoft Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="e0472-104">The Exchange admin center (EAC) is the web-based management console for Microsoft Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="e0472-105">Op zoek naar de Exchange Server-versie van dit onderwerp?</span><span class="sxs-lookup"><span data-stu-id="e0472-105">Looking for the Exchange Server version of this topic?</span></span> <span data-ttu-id="e0472-106">Zie [Exchange-beheercentrum in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="e0472-106">See [Exchange admin center in Exchange Server](https://docs.microsoft.com/exchange/architecture/client-access/exchange-admin-center).</span></span>

<span data-ttu-id="e0472-107">Op zoek naar de Exchange Online versie van dit onderwerp?</span><span class="sxs-lookup"><span data-stu-id="e0472-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="e0472-108">Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="e0472-108">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="accessing-the-eac"></a><span data-ttu-id="e0472-109">Toegang tot de EAC</span><span class="sxs-lookup"><span data-stu-id="e0472-109">Accessing the EAC</span></span>

<span data-ttu-id="e0472-110">In de meeste gevallen krijgen EOP-klanten toegang tot de EAC via het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="e0472-110">In most cases, EOP customers will access the EAC through the Microsoft 365 admin center.</span></span> <span data-ttu-id="e0472-111">U vindt een link naar EOP in het vervolgkeuzemenu in de tegel **Beheerder,** die naast de tegel **Ik** staat.</span><span class="sxs-lookup"><span data-stu-id="e0472-111">You can find a link to EOP in the drop-down menu in the **Admin** tile, which is next to the **Me** tile.</span></span> <span data-ttu-id="e0472-112">Klik op de tegel **Beheerder** en selecteer **Exchange Online Protection** in het vervolgkeuzemenu dat naar de EAC moet worden gebracht.</span><span class="sxs-lookup"><span data-stu-id="e0472-112">Click the **Admin** tile and select **Exchange Online Protection** from the drop-down menu to be taken to the EAC.</span></span>

<span data-ttu-id="e0472-113">U ook rechtstreeks via de volgende URL `https://admin.protection.outlook.com/ecp/<companydomain>`toegang krijgen tot de eac-aanmeldingspagina:.</span><span class="sxs-lookup"><span data-stu-id="e0472-113">You can also access the EAC sign in page directly via the following URL: `https://admin.protection.outlook.com/ecp/<companydomain>`.</span></span> <span data-ttu-id="e0472-114">Bijvoorbeeld `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`.</span><span class="sxs-lookup"><span data-stu-id="e0472-114">For example, `https://admin.protection.outlook.com/ecp/contoso.onmicrosoft.com`.</span></span> <span data-ttu-id="e0472-115">Na het opgeven van uw gebruikersreferenties wordt u rechtstreeks naar de EAC gebracht.</span><span class="sxs-lookup"><span data-stu-id="e0472-115">After specifying your user credentials you will be taken directly into the EAC.</span></span>

## <a name="common-user-interface-elements-in-the-eac"></a><span data-ttu-id="e0472-116">Veelvoorkomende gebruikersinterface-elementen in de EAC</span><span class="sxs-lookup"><span data-stu-id="e0472-116">Common user interface elements in the EAC</span></span>

<span data-ttu-id="e0472-117">In deze sectie worden de elementen van de gebruikersinterface beschreven die in de EAC worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="e0472-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-Beheercentrum](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="e0472-119">Functievenster</span><span class="sxs-lookup"><span data-stu-id="e0472-119">Feature Pane</span></span>

<span data-ttu-id="e0472-120">Dit is het eerste navigatieniveau voor de meeste taken die u in de EAC uitvoert.</span><span class="sxs-lookup"><span data-stu-id="e0472-120">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="e0472-121">Het functievenster is ingedeeld op functiegebieden.</span><span class="sxs-lookup"><span data-stu-id="e0472-121">The feature pane is organized by feature areas.</span></span>

1. <span data-ttu-id="e0472-122">**Geadresseerden:** hier ziet u interne gebruikers en externe contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="e0472-122">**Recipients**: This is where you'll view internal users and external contacts.</span></span>

2. <span data-ttu-id="e0472-123">**Machtigingen:** hier beheert u beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="e0472-123">**Permissions**: This where you'll manage administrator roles.</span></span>

3. <span data-ttu-id="e0472-124">**Compliance Management:** Hier vindt u controlelogboeken en rapporten, zoals het rapport van de groep beheerdersfuncties.</span><span class="sxs-lookup"><span data-stu-id="e0472-124">**Compliance Management**: This is where you'll find audit logs and reports, such as the administrator role group report.</span></span>

4. <span data-ttu-id="e0472-125">**Bescherming:** Hier beheert u anti-malware- en antispambescherming voor uw organisatie en beheert u berichten in quarantaine.</span><span class="sxs-lookup"><span data-stu-id="e0472-125">**Protection**: This is where you'll manage anti-malware and anti-spam protection for your organization, as well as manage messages in quarantine.</span></span>

5. <span data-ttu-id="e0472-126">**Mail Flow:** Hier beheert u regels, geaccepteerde domeinen en connectoren en waar u naartoe gaat om berichttracering uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e0472-126">**Mail Flow**: This is where you'll manage rules, accepted domains, and connectors, as well as where you'll go to perform message trace.</span></span>

### <a name="tabs"></a><span data-ttu-id="e0472-127">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="e0472-127">Tabs</span></span>

<span data-ttu-id="e0472-128">De tabbladen zijn uw tweede niveau van navigatie.</span><span class="sxs-lookup"><span data-stu-id="e0472-128">The tabs are your second level of navigation.</span></span> <span data-ttu-id="e0472-129">Elk van de functiegebieden bevat verschillende tabbladen, die elk een functie vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="e0472-129">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="e0472-130">Werkbalk</span><span class="sxs-lookup"><span data-stu-id="e0472-130">Toolbar</span></span>

<span data-ttu-id="e0472-131">Wanneer u op de meeste tabbladen klikt, ziet u een werkbalk.</span><span class="sxs-lookup"><span data-stu-id="e0472-131">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="e0472-132">De werkbalk heeft pictogrammen die een specifieke actie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e0472-132">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="e0472-133">In de volgende tabel worden de pictogrammen en hun acties beschreven.</span><span class="sxs-lookup"><span data-stu-id="e0472-133">The following table describes the icons and their actions.</span></span>

|<span data-ttu-id="e0472-134">**Pictogram**</span><span class="sxs-lookup"><span data-stu-id="e0472-134">**Icon**</span></span>|<span data-ttu-id="e0472-135">**Naam**</span><span class="sxs-lookup"><span data-stu-id="e0472-135">**Name**</span></span>|<span data-ttu-id="e0472-136">**Actie**</span><span class="sxs-lookup"><span data-stu-id="e0472-136">**Action**</span></span>|
|:-----|:-----|:-----|
|![Pictogram toevoegen](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="e0472-138">Toevoegen, Nieuw</span><span class="sxs-lookup"><span data-stu-id="e0472-138">Add, New</span></span>|<span data-ttu-id="e0472-139">Gebruik dit pictogram om een nieuw object te maken.</span><span class="sxs-lookup"><span data-stu-id="e0472-139">Use this icon to create a new object.</span></span> <span data-ttu-id="e0472-140">Sommige van deze pictogrammen hebben een bijbehorende pijl-omlaag waarop u klikken om extra objecten weer te geven die u maken.</span><span class="sxs-lookup"><span data-stu-id="e0472-140">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Pictogram Bewerken](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="e0472-142">Bewerken</span><span class="sxs-lookup"><span data-stu-id="e0472-142">Edit</span></span>|<span data-ttu-id="e0472-143">Gebruik dit pictogram om een object te bewerken.</span><span class="sxs-lookup"><span data-stu-id="e0472-143">Use this icon to edit an object.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="e0472-145">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="e0472-145">Delete</span></span>|<span data-ttu-id="e0472-146">Gebruik dit pictogram om een object te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e0472-146">Use this icon to delete an object.</span></span> <span data-ttu-id="e0472-147">Sommige verwijderpictogrammen hebben een pijl-omlaag waarop u klikken om extra opties weer te geven.</span><span class="sxs-lookup"><span data-stu-id="e0472-147">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|<span data-ttu-id="e0472-149">Zoek</span><span class="sxs-lookup"><span data-stu-id="e0472-149">Search</span></span>|<span data-ttu-id="e0472-150">Gebruik dit pictogram om een zoekvak te openen waarin u de zoekterm typen voor een object dat u wilt vinden.</span><span class="sxs-lookup"><span data-stu-id="e0472-150">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="e0472-152">Vernieuwen</span><span class="sxs-lookup"><span data-stu-id="e0472-152">Refresh</span></span>|<span data-ttu-id="e0472-153">Gebruik dit pictogram om de lijstweergave te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="e0472-153">Use this icon to refresh the list view.</span></span>|
|![Pictogram Meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="e0472-155">Meer opties</span><span class="sxs-lookup"><span data-stu-id="e0472-155">More options</span></span>|<span data-ttu-id="e0472-156">Gebruik dit pictogram om meer acties weer te geven die u voor de objecten van dat tabblad uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="e0472-156">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="e0472-157">In \*\* \> Ontvangers\*\* die bijvoorbeeld op dit pictogram klikken, wordt de optie weergegeven om een **geavanceerd zoeken**uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="e0472-157">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Pictogram Pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram Pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="e0472-160">Pijl-omhoog en pijl-omlaag</span><span class="sxs-lookup"><span data-stu-id="e0472-160">Up arrow and down arrow</span></span>|<span data-ttu-id="e0472-161">Gebruik deze pictogrammen om de prioriteit van een object omhoog of omlaag te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="e0472-161">Use these icons to move an object's priority up or down.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="e0472-163">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="e0472-163">Remove</span></span>|<span data-ttu-id="e0472-164">Gebruik dit pictogram om objecten uit een lijst te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="e0472-164">Use this icon to remove objects from a list.</span></span>|

### <a name="list-view"></a><span data-ttu-id="e0472-165">Lijstweergave</span><span class="sxs-lookup"><span data-stu-id="e0472-165">List View</span></span>

<span data-ttu-id="e0472-166">Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave.</span><span class="sxs-lookup"><span data-stu-id="e0472-166">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="e0472-167">De zichtbaarbare limiet met de EAC-lijstweergave is ongeveer 10.000 objecten.</span><span class="sxs-lookup"><span data-stu-id="e0472-167">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="e0472-168">Bovendien is paging opgenomen, zodat u pagina naar resultaten.</span><span class="sxs-lookup"><span data-stu-id="e0472-168">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="e0472-169">Details venster</span><span class="sxs-lookup"><span data-stu-id="e0472-169">Details Pane</span></span>

<span data-ttu-id="e0472-170">Wanneer u een object selecteert in de lijstweergave, wordt informatie over dat object weergegeven in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="e0472-170">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="e0472-171">In sommige gevallen bevat het detailvenster beheertaken.</span><span class="sxs-lookup"><span data-stu-id="e0472-171">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="e0472-172">Mijn tegel en Help</span><span class="sxs-lookup"><span data-stu-id="e0472-172">Me tile and Help</span></span>

<span data-ttu-id="e0472-173">Met de tegel **Ik** u de EAC afmelden en u als andere gebruiker aanmelden.</span><span class="sxs-lookup"><span data-stu-id="e0472-173">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="e0472-174">In het vervolgkeuzemenu Help-pictogram-pictogram **Help**![](../../media/ITPro-EAC-HelpIcon.gif) u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="e0472-174">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

1. <span data-ttu-id="e0472-175">**Help:** ![Klik](../../media/ITPro-EAC-HelpIcon.gif) op Help-pictogram om de online help-inhoud te bekijken.</span><span class="sxs-lookup"><span data-stu-id="e0472-175">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

2. <span data-ttu-id="e0472-176">**Help-bel uitschakelen:** in de Help-bel worden contextuele help voor velden weergegeven wanneer u een object maakt of bewerkt.</span><span class="sxs-lookup"><span data-stu-id="e0472-176">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="e0472-177">U de Help-bel uitschakelen of inschakelen als deze is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e0472-177">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

3. <span data-ttu-id="e0472-178">**Auteursrecht**: Klik op deze link om de copyright verklaring voor Exchange Online Protection te lezen.</span><span class="sxs-lookup"><span data-stu-id="e0472-178">**Copyright**: Click this link to read the copyright notice for Exchange Online Protection.</span></span>

4. <span data-ttu-id="e0472-179">**Privacy**: Klik hier om het privacybeleid voor Exchange Online Protection te lezen.</span><span class="sxs-lookup"><span data-stu-id="e0472-179">**Privacy**: Click to read the privacy policy for Exchange Online Protection.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="e0472-180">Ondersteunde browsers</span><span class="sxs-lookup"><span data-stu-id="e0472-180">Supported Browsers</span></span>

<span data-ttu-id="e0472-181">Voor de beste ervaring met de EAC raden we u aan altijd de nieuwste browsers, Office-clients en apps te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="e0472-181">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="e0472-182">We raden u ook aan software-updates te installeren wanneer deze beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="e0472-182">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="e0472-183">Zie [Systeemvereisten voor Office voor](https://products.office.com/office-system-requirements)meer informatie over de ondersteunde browsers en systeemvereisten voor de service.</span><span class="sxs-lookup"><span data-stu-id="e0472-183">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages-in-eop"></a><span data-ttu-id="e0472-184">Ondersteunde talen in EOP</span><span class="sxs-lookup"><span data-stu-id="e0472-184">Supported languages in EOP</span></span>

<span data-ttu-id="e0472-185">De volgende talen worden ondersteund en beschikbaar voor Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="e0472-185">The following languages are supported and available for Exchange Online Protection.</span></span>

- <span data-ttu-id="e0472-186">Amharic</span><span class="sxs-lookup"><span data-stu-id="e0472-186">Amharic</span></span>

- <span data-ttu-id="e0472-187">Arabisch</span><span class="sxs-lookup"><span data-stu-id="e0472-187">Arabic</span></span>

- <span data-ttu-id="e0472-188">Baskisch (Baskisch)</span><span class="sxs-lookup"><span data-stu-id="e0472-188">Basque (Basque)</span></span>

- <span data-ttu-id="e0472-189">Bengaals (India)</span><span class="sxs-lookup"><span data-stu-id="e0472-189">Bengali (India)</span></span>

- <span data-ttu-id="e0472-190">Bulgaars</span><span class="sxs-lookup"><span data-stu-id="e0472-190">Bulgarian</span></span>

- <span data-ttu-id="e0472-191">Catalaans</span><span class="sxs-lookup"><span data-stu-id="e0472-191">Catalan</span></span>

- <span data-ttu-id="e0472-192">Chinees (vereenvoudigd)</span><span class="sxs-lookup"><span data-stu-id="e0472-192">Chinese (Simplified)</span></span>

- <span data-ttu-id="e0472-193">Chinees (traditioneel)</span><span class="sxs-lookup"><span data-stu-id="e0472-193">Chinese (Traditional)</span></span>

- <span data-ttu-id="e0472-194">Kroatisch</span><span class="sxs-lookup"><span data-stu-id="e0472-194">Croatian</span></span>

- <span data-ttu-id="e0472-195">Tsjechisch</span><span class="sxs-lookup"><span data-stu-id="e0472-195">Czech</span></span>

- <span data-ttu-id="e0472-196">Deens</span><span class="sxs-lookup"><span data-stu-id="e0472-196">Danish</span></span>

- <span data-ttu-id="e0472-197">Nederlands</span><span class="sxs-lookup"><span data-stu-id="e0472-197">Dutch</span></span>

- <span data-ttu-id="e0472-198">Nederlands</span><span class="sxs-lookup"><span data-stu-id="e0472-198">Dutch</span></span>

- <span data-ttu-id="e0472-199">Engels</span><span class="sxs-lookup"><span data-stu-id="e0472-199">English</span></span>

- <span data-ttu-id="e0472-200">Estisch</span><span class="sxs-lookup"><span data-stu-id="e0472-200">Estonian</span></span>

- <span data-ttu-id="e0472-201">Filipijns (Filippijnen)</span><span class="sxs-lookup"><span data-stu-id="e0472-201">Filipino (Philippines)</span></span>

- <span data-ttu-id="e0472-202">Fins</span><span class="sxs-lookup"><span data-stu-id="e0472-202">Finnish</span></span>

- <span data-ttu-id="e0472-203">Frans</span><span class="sxs-lookup"><span data-stu-id="e0472-203">French</span></span>

- <span data-ttu-id="e0472-204">Galicisch</span><span class="sxs-lookup"><span data-stu-id="e0472-204">Galician</span></span>

- <span data-ttu-id="e0472-205">Duits</span><span class="sxs-lookup"><span data-stu-id="e0472-205">German</span></span>

- <span data-ttu-id="e0472-206">Grieks</span><span class="sxs-lookup"><span data-stu-id="e0472-206">Greek</span></span>

- <span data-ttu-id="e0472-207">Gujarati</span><span class="sxs-lookup"><span data-stu-id="e0472-207">Gujarati</span></span>

- <span data-ttu-id="e0472-208">Hebreeuws</span><span class="sxs-lookup"><span data-stu-id="e0472-208">Hebrew</span></span>

- <span data-ttu-id="e0472-209">Hindi</span><span class="sxs-lookup"><span data-stu-id="e0472-209">Hindi</span></span>

- <span data-ttu-id="e0472-210">Hongaars</span><span class="sxs-lookup"><span data-stu-id="e0472-210">Hungarian</span></span>

- <span data-ttu-id="e0472-211">IJslands</span><span class="sxs-lookup"><span data-stu-id="e0472-211">Icelandic</span></span>

- <span data-ttu-id="e0472-212">Indonesisch</span><span class="sxs-lookup"><span data-stu-id="e0472-212">Indonesian</span></span>

- <span data-ttu-id="e0472-213">Italiaans</span><span class="sxs-lookup"><span data-stu-id="e0472-213">Italian</span></span>

- <span data-ttu-id="e0472-214">Japans</span><span class="sxs-lookup"><span data-stu-id="e0472-214">Japanese</span></span>

- <span data-ttu-id="e0472-215">Kannada</span><span class="sxs-lookup"><span data-stu-id="e0472-215">Kannada</span></span>

- <span data-ttu-id="e0472-216">Kazachstaans</span><span class="sxs-lookup"><span data-stu-id="e0472-216">Kazakh</span></span>

- <span data-ttu-id="e0472-217">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="e0472-217">Kiswahili</span></span>

- <span data-ttu-id="e0472-218">Koreaans</span><span class="sxs-lookup"><span data-stu-id="e0472-218">Korean</span></span>

- <span data-ttu-id="e0472-219">Lets</span><span class="sxs-lookup"><span data-stu-id="e0472-219">Latvian</span></span>

- <span data-ttu-id="e0472-220">Litouws</span><span class="sxs-lookup"><span data-stu-id="e0472-220">Lithuanian</span></span>

- <span data-ttu-id="e0472-221">Maleis (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="e0472-221">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="e0472-222">Maleis (Maleisië)</span><span class="sxs-lookup"><span data-stu-id="e0472-222">Malay (Malaysia)</span></span>

- <span data-ttu-id="e0472-223">Malajalam</span><span class="sxs-lookup"><span data-stu-id="e0472-223">Malayalam</span></span>

- <span data-ttu-id="e0472-224">Marathi</span><span class="sxs-lookup"><span data-stu-id="e0472-224">Marathi</span></span>

- <span data-ttu-id="e0472-225">Noors (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="e0472-225">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="e0472-226">Noors (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="e0472-226">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="e0472-227">Oriya</span><span class="sxs-lookup"><span data-stu-id="e0472-227">Oriya</span></span>

- <span data-ttu-id="e0472-228">Perzisch</span><span class="sxs-lookup"><span data-stu-id="e0472-228">Persian</span></span>

- <span data-ttu-id="e0472-229">Pools</span><span class="sxs-lookup"><span data-stu-id="e0472-229">Polish</span></span>

- <span data-ttu-id="e0472-230">Portugees (Brazilië)</span><span class="sxs-lookup"><span data-stu-id="e0472-230">Portuguese (Brazil)</span></span>

- <span data-ttu-id="e0472-231">Portugees (Portugal)</span><span class="sxs-lookup"><span data-stu-id="e0472-231">Portuguese (Portugal)</span></span>

- <span data-ttu-id="e0472-232">Roemeens</span><span class="sxs-lookup"><span data-stu-id="e0472-232">Romanian</span></span>

- <span data-ttu-id="e0472-233">Russisch</span><span class="sxs-lookup"><span data-stu-id="e0472-233">Russian</span></span>

- <span data-ttu-id="e0472-234">Servisch (Cyrillisch, Servië)</span><span class="sxs-lookup"><span data-stu-id="e0472-234">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="e0472-235">Servisch (Latijn)</span><span class="sxs-lookup"><span data-stu-id="e0472-235">Serbian (Latin)</span></span>

- <span data-ttu-id="e0472-236">Slowaaks</span><span class="sxs-lookup"><span data-stu-id="e0472-236">Slovak</span></span>

- <span data-ttu-id="e0472-237">Sloveens</span><span class="sxs-lookup"><span data-stu-id="e0472-237">Slovenian</span></span>

- <span data-ttu-id="e0472-238">Spaans</span><span class="sxs-lookup"><span data-stu-id="e0472-238">Spanish</span></span>

- <span data-ttu-id="e0472-239">Zweeds</span><span class="sxs-lookup"><span data-stu-id="e0472-239">Swedish</span></span>

- <span data-ttu-id="e0472-240">Tamil</span><span class="sxs-lookup"><span data-stu-id="e0472-240">Tamil</span></span>

- <span data-ttu-id="e0472-241">Telugu</span><span class="sxs-lookup"><span data-stu-id="e0472-241">Telugu</span></span>

- <span data-ttu-id="e0472-242">Thais</span><span class="sxs-lookup"><span data-stu-id="e0472-242">Thai</span></span>

- <span data-ttu-id="e0472-243">Turks</span><span class="sxs-lookup"><span data-stu-id="e0472-243">Turkish</span></span>

- <span data-ttu-id="e0472-244">Oekraïens</span><span class="sxs-lookup"><span data-stu-id="e0472-244">Ukrainian</span></span>

- <span data-ttu-id="e0472-245">Urdu</span><span class="sxs-lookup"><span data-stu-id="e0472-245">Urdu</span></span>

- <span data-ttu-id="e0472-246">Vietnamees</span><span class="sxs-lookup"><span data-stu-id="e0472-246">Vietnamese</span></span>

- <span data-ttu-id="e0472-247">Welsh</span><span class="sxs-lookup"><span data-stu-id="e0472-247">Welsh</span></span>


