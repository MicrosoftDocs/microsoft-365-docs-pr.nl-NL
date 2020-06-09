---
title: Exchange-beheercentrum in standalone EOP
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
description: Meer informatie over de webmanagementinterface in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: 777597489e54c642220cb42f0c686b675101897f
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44616996"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="67f86-103">Exchange-beheercentrum in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="67f86-103">Exchange admin center in standalone EOP</span></span>

<span data-ttu-id="67f86-104">Het Exchange-beheercentrum (EAC) is een webgebaseerde beheerconsole voor standalone Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="67f86-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="67f86-105">Op zoek naar de Exchange Online-versie van dit onderwerp?</span><span class="sxs-lookup"><span data-stu-id="67f86-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="67f86-106">Zie [Exchange-beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="67f86-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="67f86-107">Open de EAC in EOP</span><span class="sxs-lookup"><span data-stu-id="67f86-107">Open the EAC in EOP</span></span>

<span data-ttu-id="67f86-108">Standalone EOP-klanten hebben toegang tot de EAC via de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="67f86-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="67f86-109">**Vanuit het Microsoft 365-beheercentrum**:</span><span class="sxs-lookup"><span data-stu-id="67f86-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="67f86-110">Ga naar <https://admin.microsoft.com> en klik op Alles **weergeven.**</span><span class="sxs-lookup"><span data-stu-id="67f86-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klik op Alles weergeven in het Microsoft 365-beheercentrum](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="67f86-112">Klik in de sectie **Beheercentra** die wordt weergegeven op **Alle beheercentra**.</span><span class="sxs-lookup"><span data-stu-id="67f86-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klik op Alle beheercentra in het Microsoft 365-beheercentrum](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="67f86-114">Klik op de pagina **Alle beheercentra** die wordt weergegeven op **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="67f86-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="67f86-115">Ga direct naar `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="67f86-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="67f86-116">Gemeenschappelijke gebruikersinterface-elementen in de EAC in EOP</span><span class="sxs-lookup"><span data-stu-id="67f86-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="67f86-117">In deze sectie worden de elementen van de gebruikersinterface beschreven die in de EAC worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="67f86-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-AdminCenter](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="67f86-119">Functievenster</span><span class="sxs-lookup"><span data-stu-id="67f86-119">Feature Pane</span></span>

<span data-ttu-id="67f86-120">Dit is het eerste navigatieniveau voor de meeste taken die u in de EAC uitvoert.</span><span class="sxs-lookup"><span data-stu-id="67f86-120">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="67f86-121">Het functievenster wordt georganiseerd op functiegebieden.</span><span class="sxs-lookup"><span data-stu-id="67f86-121">The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="67f86-122">**Geadresseerden**: hier ziet u groepen en externe contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="67f86-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="67f86-123">**Machtigingen**: hiermee beheert u beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="67f86-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="67f86-124">**Compliance Management**: Hier vindt u het rapport van de beheerdersrolgroep en het logboekrapport voor beheerderscontrole.</span><span class="sxs-lookup"><span data-stu-id="67f86-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="67f86-125">**Beveiliging:** hier u anti-malwarebeleid, het standaardverbindingsfilterbeleid en DKIM beheren.</span><span class="sxs-lookup"><span data-stu-id="67f86-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="67f86-126">U moet antimalwarebeleid en het standaardfilterbeleid voor verbinding beheren in het Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="67f86-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="67f86-127">Zie [Anti-malwarebeleid configureren in EOP](configure-anti-malware-policies.md) en [Verbindingsfiltering configureren in EOP](configure-the-connection-filter-policy.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="67f86-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="67f86-128">**E-mailstroom:** hiermee beheert u e-mailstroomregels (ook wel transportregels genoemd), geaccepteerde domeinen en connectoren, evenals waar u berichttracering uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="67f86-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="67f86-129">**Hybride:** Hier u de [wizard Hybride configuratie](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)uitvoeren en u de Exchange Online [PowerShell-module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)installeren.</span><span class="sxs-lookup"><span data-stu-id="67f86-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="67f86-130">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="67f86-130">Tabs</span></span>

<span data-ttu-id="67f86-131">De tabbladen zijn uw tweede niveau van navigatie.</span><span class="sxs-lookup"><span data-stu-id="67f86-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="67f86-132">Elk van de functiegebieden bevat verschillende tabbladen, die elk een functie vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="67f86-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="67f86-133">Werkbalk</span><span class="sxs-lookup"><span data-stu-id="67f86-133">Toolbar</span></span>

<span data-ttu-id="67f86-134">Wanneer u op de meeste tabbladen klikt, ziet u een werkbalk.</span><span class="sxs-lookup"><span data-stu-id="67f86-134">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="67f86-135">Op de werkbalk zijn pictogrammen die een specifieke actie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="67f86-135">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="67f86-136">In de volgende tabel worden de pictogrammen en hun acties beschreven.</span><span class="sxs-lookup"><span data-stu-id="67f86-136">The following table describes the icons and their actions.</span></span>

||||
|---|---|---|
|<span data-ttu-id="67f86-137">**Pictogram**</span><span class="sxs-lookup"><span data-stu-id="67f86-137">**Icon**</span></span>|<span data-ttu-id="67f86-138">**Naam**</span><span class="sxs-lookup"><span data-stu-id="67f86-138">**Name**</span></span>|<span data-ttu-id="67f86-139">**Actie**</span><span class="sxs-lookup"><span data-stu-id="67f86-139">**Action**</span></span>|
|![Pictogram toevoegen](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="67f86-141">Toevoegen, Nieuw</span><span class="sxs-lookup"><span data-stu-id="67f86-141">Add, New</span></span>|<span data-ttu-id="67f86-142">Gebruik dit pictogram om een nieuw object te maken.</span><span class="sxs-lookup"><span data-stu-id="67f86-142">Use this icon to create a new object.</span></span> <span data-ttu-id="67f86-143">Sommige van deze pictogrammen hebben een bijbehorende pijl-omlaag waarop u klikken om extra objecten weer te geven die u maken.</span><span class="sxs-lookup"><span data-stu-id="67f86-143">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Pictogram Bewerken](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="67f86-145">Bewerken</span><span class="sxs-lookup"><span data-stu-id="67f86-145">Edit</span></span>|<span data-ttu-id="67f86-146">Gebruik dit pictogram om een object te bewerken.</span><span class="sxs-lookup"><span data-stu-id="67f86-146">Use this icon to edit an object.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="67f86-148">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="67f86-148">Delete</span></span>|<span data-ttu-id="67f86-149">Gebruik dit pictogram om een object te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="67f86-149">Use this icon to delete an object.</span></span> <span data-ttu-id="67f86-150">Sommige verwijderpictogrammen hebben een pijl-omlaag waarop u klikken om extra opties weer te geven.</span><span class="sxs-lookup"><span data-stu-id="67f86-150">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|<span data-ttu-id="67f86-152">Zoek</span><span class="sxs-lookup"><span data-stu-id="67f86-152">Search</span></span>|<span data-ttu-id="67f86-153">Gebruik dit pictogram om een zoekvak te openen waarin u de zoekterm typen voor een object dat u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="67f86-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="67f86-155">Vernieuwen</span><span class="sxs-lookup"><span data-stu-id="67f86-155">Refresh</span></span>|<span data-ttu-id="67f86-156">Gebruik dit pictogram om de lijstweergave te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="67f86-156">Use this icon to refresh the list view.</span></span>|
|![Pictogram Meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="67f86-158">Meer opties</span><span class="sxs-lookup"><span data-stu-id="67f86-158">More options</span></span>|<span data-ttu-id="67f86-159">Gebruik dit pictogram om meer acties weer te geven die u uitvoeren voor de objecten van dat tabblad.</span><span class="sxs-lookup"><span data-stu-id="67f86-159">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="67f86-160">In ontvangers \*\* \> gebruikers\*\* die op dit pictogram klikken, ziet u bijvoorbeeld de optie om een **geavanceerd zoeken**uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="67f86-160">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Pictogram Pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram Pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="67f86-163">Pijl-omhoog en pijl-omlaag</span><span class="sxs-lookup"><span data-stu-id="67f86-163">Up arrow and down arrow</span></span>|<span data-ttu-id="67f86-164">Gebruik deze pictogrammen om de prioriteit van een object omhoog of omlaag te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="67f86-164">Use these icons to move an object's priority up or down.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="67f86-166">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="67f86-166">Remove</span></span>|<span data-ttu-id="67f86-167">Gebruik dit pictogram om objecten uit een lijst te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="67f86-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="67f86-168">Lijstweergave</span><span class="sxs-lookup"><span data-stu-id="67f86-168">List View</span></span>

<span data-ttu-id="67f86-169">Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave.</span><span class="sxs-lookup"><span data-stu-id="67f86-169">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="67f86-170">De zichtbare limiet met de EAC-lijstweergave is ongeveer 10.000 objecten.</span><span class="sxs-lookup"><span data-stu-id="67f86-170">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="67f86-171">Bovendien is paging opgenomen, zodat u pagina naar de resultaten.</span><span class="sxs-lookup"><span data-stu-id="67f86-171">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="67f86-172">Detailvenster</span><span class="sxs-lookup"><span data-stu-id="67f86-172">Details Pane</span></span>

<span data-ttu-id="67f86-173">Wanneer u een object selecteert in de lijstweergave, wordt informatie over dat object weergegeven in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="67f86-173">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="67f86-174">In sommige gevallen bevat het detailvenster beheertaken.</span><span class="sxs-lookup"><span data-stu-id="67f86-174">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="67f86-175">Me tegel en Help</span><span class="sxs-lookup"><span data-stu-id="67f86-175">Me tile and Help</span></span>

<span data-ttu-id="67f86-176">Met de tegel **Ik** u de EAC afmelden en u aanmelden als een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="67f86-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="67f86-177">In **Help**het ![ ](../../media/ITPro-EAC-HelpIcon.gif) vervolgkeuzemenu Help-pictogram help u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="67f86-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="67f86-178">**Help:** klik op ![ Help-pictogram ](../../media/ITPro-EAC-HelpIcon.gif) om de online help-inhoud te bekijken.</span><span class="sxs-lookup"><span data-stu-id="67f86-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="67f86-179">**Feedback**: Feedback geven.</span><span class="sxs-lookup"><span data-stu-id="67f86-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="67f86-180">**Community**: Plaats een vraag om antwoorden te vinden in de communityforums.</span><span class="sxs-lookup"><span data-stu-id="67f86-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="67f86-181">**Help-bel uitschakelen:** in de Help-bel wordt contextuele hulp weergegeven voor velden wanneer u een object maakt of bewerkt.</span><span class="sxs-lookup"><span data-stu-id="67f86-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="67f86-182">U de Help-bel uitschakelen of inschakelen als deze is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="67f86-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="67f86-183">**Command Logging weergeven**: er wordt een nieuw venster geopend met de gelijkwaardige PowerShell-opdrachten op basis van wat u hebt geconfigureerd in EAC.</span><span class="sxs-lookup"><span data-stu-id="67f86-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="67f86-184">Ondersteunde browsers</span><span class="sxs-lookup"><span data-stu-id="67f86-184">Supported Browsers</span></span>

<span data-ttu-id="67f86-185">Voor de beste ervaring met de EAC raden we u aan altijd de nieuwste browsers, Office-clients en -apps te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="67f86-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="67f86-186">We raden u ook aan software-updates te installeren wanneer deze beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="67f86-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="67f86-187">Zie [Systeemvereisten voor Office voor](https://products.office.com/office-system-requirements)meer informatie over de ondersteunde browsers en systeemvereisten voor de service.</span><span class="sxs-lookup"><span data-stu-id="67f86-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="67f86-188">Ondersteunde talen</span><span class="sxs-lookup"><span data-stu-id="67f86-188">Supported languages</span></span>

<span data-ttu-id="67f86-189">De volgende talen worden ondersteund en beschikbaar voor de EAC in standalone EOP.</span><span class="sxs-lookup"><span data-stu-id="67f86-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="67f86-190">Amharic</span><span class="sxs-lookup"><span data-stu-id="67f86-190">Amharic</span></span>

- <span data-ttu-id="67f86-191">Arabisch</span><span class="sxs-lookup"><span data-stu-id="67f86-191">Arabic</span></span>

- <span data-ttu-id="67f86-192">Baskisch (Baskisch)</span><span class="sxs-lookup"><span data-stu-id="67f86-192">Basque (Basque)</span></span>

- <span data-ttu-id="67f86-193">Bengaals (India)</span><span class="sxs-lookup"><span data-stu-id="67f86-193">Bengali (India)</span></span>

- <span data-ttu-id="67f86-194">Bulgarian</span><span class="sxs-lookup"><span data-stu-id="67f86-194">Bulgarian</span></span>

- <span data-ttu-id="67f86-195">Catalan</span><span class="sxs-lookup"><span data-stu-id="67f86-195">Catalan</span></span>

- <span data-ttu-id="67f86-196">Chinees (vereenvoudigd)</span><span class="sxs-lookup"><span data-stu-id="67f86-196">Chinese (Simplified)</span></span>

- <span data-ttu-id="67f86-197">Chinees (traditioneel)</span><span class="sxs-lookup"><span data-stu-id="67f86-197">Chinese (Traditional)</span></span>

- <span data-ttu-id="67f86-198">Croatian</span><span class="sxs-lookup"><span data-stu-id="67f86-198">Croatian</span></span>

- <span data-ttu-id="67f86-199">Czech</span><span class="sxs-lookup"><span data-stu-id="67f86-199">Czech</span></span>

- <span data-ttu-id="67f86-200">Danish</span><span class="sxs-lookup"><span data-stu-id="67f86-200">Danish</span></span>

- <span data-ttu-id="67f86-201">Dutch</span><span class="sxs-lookup"><span data-stu-id="67f86-201">Dutch</span></span>

- <span data-ttu-id="67f86-202">Dutch</span><span class="sxs-lookup"><span data-stu-id="67f86-202">Dutch</span></span>

- <span data-ttu-id="67f86-203">English</span><span class="sxs-lookup"><span data-stu-id="67f86-203">English</span></span>

- <span data-ttu-id="67f86-204">Estonian</span><span class="sxs-lookup"><span data-stu-id="67f86-204">Estonian</span></span>

- <span data-ttu-id="67f86-205">Filipijns (Filippijnen)</span><span class="sxs-lookup"><span data-stu-id="67f86-205">Filipino (Philippines)</span></span>

- <span data-ttu-id="67f86-206">Finnish</span><span class="sxs-lookup"><span data-stu-id="67f86-206">Finnish</span></span>

- <span data-ttu-id="67f86-207">French</span><span class="sxs-lookup"><span data-stu-id="67f86-207">French</span></span>

- <span data-ttu-id="67f86-208">Galician</span><span class="sxs-lookup"><span data-stu-id="67f86-208">Galician</span></span>

- <span data-ttu-id="67f86-209">German</span><span class="sxs-lookup"><span data-stu-id="67f86-209">German</span></span>

- <span data-ttu-id="67f86-210">Greek</span><span class="sxs-lookup"><span data-stu-id="67f86-210">Greek</span></span>

- <span data-ttu-id="67f86-211">Gujarati</span><span class="sxs-lookup"><span data-stu-id="67f86-211">Gujarati</span></span>

- <span data-ttu-id="67f86-212">Hebrew</span><span class="sxs-lookup"><span data-stu-id="67f86-212">Hebrew</span></span>

- <span data-ttu-id="67f86-213">Hindi</span><span class="sxs-lookup"><span data-stu-id="67f86-213">Hindi</span></span>

- <span data-ttu-id="67f86-214">Hungarian</span><span class="sxs-lookup"><span data-stu-id="67f86-214">Hungarian</span></span>

- <span data-ttu-id="67f86-215">IJslands</span><span class="sxs-lookup"><span data-stu-id="67f86-215">Icelandic</span></span>

- <span data-ttu-id="67f86-216">Indonesian</span><span class="sxs-lookup"><span data-stu-id="67f86-216">Indonesian</span></span>

- <span data-ttu-id="67f86-217">Italian</span><span class="sxs-lookup"><span data-stu-id="67f86-217">Italian</span></span>

- <span data-ttu-id="67f86-218">Japanese</span><span class="sxs-lookup"><span data-stu-id="67f86-218">Japanese</span></span>

- <span data-ttu-id="67f86-219">Kannada</span><span class="sxs-lookup"><span data-stu-id="67f86-219">Kannada</span></span>

- <span data-ttu-id="67f86-220">Kazakh</span><span class="sxs-lookup"><span data-stu-id="67f86-220">Kazakh</span></span>

- <span data-ttu-id="67f86-221">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="67f86-221">Kiswahili</span></span>

- <span data-ttu-id="67f86-222">Korean</span><span class="sxs-lookup"><span data-stu-id="67f86-222">Korean</span></span>

- <span data-ttu-id="67f86-223">Latvian</span><span class="sxs-lookup"><span data-stu-id="67f86-223">Latvian</span></span>

- <span data-ttu-id="67f86-224">Lithuanian</span><span class="sxs-lookup"><span data-stu-id="67f86-224">Lithuanian</span></span>

- <span data-ttu-id="67f86-225">Maleis (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="67f86-225">Malay (Brunei Darussalam)</span></span>

- <span data-ttu-id="67f86-226">Maleis (Maleisië)</span><span class="sxs-lookup"><span data-stu-id="67f86-226">Malay (Malaysia)</span></span>

- <span data-ttu-id="67f86-227">Malajalam</span><span class="sxs-lookup"><span data-stu-id="67f86-227">Malayalam</span></span>

- <span data-ttu-id="67f86-228">Marathi</span><span class="sxs-lookup"><span data-stu-id="67f86-228">Marathi</span></span>

- <span data-ttu-id="67f86-229">Noors (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="67f86-229">Norwegian (Bokmål)</span></span>

- <span data-ttu-id="67f86-230">Noors (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="67f86-230">Norwegian (Nynorsk)</span></span>

- <span data-ttu-id="67f86-231">Oriya</span><span class="sxs-lookup"><span data-stu-id="67f86-231">Oriya</span></span>

- <span data-ttu-id="67f86-232">Perzisch</span><span class="sxs-lookup"><span data-stu-id="67f86-232">Persian</span></span>

- <span data-ttu-id="67f86-233">Polish</span><span class="sxs-lookup"><span data-stu-id="67f86-233">Polish</span></span>

- <span data-ttu-id="67f86-234">Portugees (Brazilië)</span><span class="sxs-lookup"><span data-stu-id="67f86-234">Portuguese (Brazil)</span></span>

- <span data-ttu-id="67f86-235">Portugees (Portugal)</span><span class="sxs-lookup"><span data-stu-id="67f86-235">Portuguese (Portugal)</span></span>

- <span data-ttu-id="67f86-236">Romanian</span><span class="sxs-lookup"><span data-stu-id="67f86-236">Romanian</span></span>

- <span data-ttu-id="67f86-237">Russian</span><span class="sxs-lookup"><span data-stu-id="67f86-237">Russian</span></span>

- <span data-ttu-id="67f86-238">Servisch (Cyrillisch, Servië)</span><span class="sxs-lookup"><span data-stu-id="67f86-238">Serbian (Cyrillic, Serbia)</span></span>

- <span data-ttu-id="67f86-239">Servisch (Latijn)</span><span class="sxs-lookup"><span data-stu-id="67f86-239">Serbian (Latin)</span></span>

- <span data-ttu-id="67f86-240">Slovak</span><span class="sxs-lookup"><span data-stu-id="67f86-240">Slovak</span></span>

- <span data-ttu-id="67f86-241">Slovenian</span><span class="sxs-lookup"><span data-stu-id="67f86-241">Slovenian</span></span>

- <span data-ttu-id="67f86-242">Spanish</span><span class="sxs-lookup"><span data-stu-id="67f86-242">Spanish</span></span>

- <span data-ttu-id="67f86-243">Swedish</span><span class="sxs-lookup"><span data-stu-id="67f86-243">Swedish</span></span>

- <span data-ttu-id="67f86-244">Tamil</span><span class="sxs-lookup"><span data-stu-id="67f86-244">Tamil</span></span>

- <span data-ttu-id="67f86-245">Telugu</span><span class="sxs-lookup"><span data-stu-id="67f86-245">Telugu</span></span>

- <span data-ttu-id="67f86-246">Thai</span><span class="sxs-lookup"><span data-stu-id="67f86-246">Thai</span></span>

- <span data-ttu-id="67f86-247">Turkish</span><span class="sxs-lookup"><span data-stu-id="67f86-247">Turkish</span></span>

- <span data-ttu-id="67f86-248">Ukrainian</span><span class="sxs-lookup"><span data-stu-id="67f86-248">Ukrainian</span></span>

- <span data-ttu-id="67f86-249">Urdu</span><span class="sxs-lookup"><span data-stu-id="67f86-249">Urdu</span></span>

- <span data-ttu-id="67f86-250">Vietnamese</span><span class="sxs-lookup"><span data-stu-id="67f86-250">Vietnamese</span></span>

- <span data-ttu-id="67f86-251">Welsh</span><span class="sxs-lookup"><span data-stu-id="67f86-251">Welsh</span></span>
