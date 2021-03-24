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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 97921f0e-832f-40c7-b56d-414faede5191
ms.collection:
- M365-security-compliance
description: Meer informatie over de webbeheerinterface in zelfstandige Exchange Online Protection (EOP).
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ab834d14673370a39e148aefa568591ff4c50b8f
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060341"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="0b7c8-103">Exchange-beheercentrum in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="0b7c8-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0b7c8-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="0b7c8-104">**Applies to**</span></span>
-  [<span data-ttu-id="0b7c8-105">Zelfstandige Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0b7c8-105">Exchange Online Protection standalone</span></span>](exchange-online-protection-overview.md)

<span data-ttu-id="0b7c8-106">Het Exchange-beheercentrum (EAC) is een webbeheerconsole voor zelfstandige Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="0b7c8-106">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="0b7c8-107">Zoekt u de Exchange Online-versie van dit onderwerp?</span><span class="sxs-lookup"><span data-stu-id="0b7c8-107">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="0b7c8-108">Zie [Exchange-beheercentrum in Exchange Online.](/exchange/exchange-admin-center)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-108">See [Exchange admin center in Exchange Online](/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="0b7c8-109">Het EAC openen in EOP</span><span class="sxs-lookup"><span data-stu-id="0b7c8-109">Open the EAC in EOP</span></span>

<span data-ttu-id="0b7c8-110">Zelfstandige EOP-klanten hebben toegang tot het EAC op basis van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="0b7c8-110">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="0b7c8-111">**Vanuit het Microsoft 365-beheercentrum:**</span><span class="sxs-lookup"><span data-stu-id="0b7c8-111">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="0b7c8-112">Ga naar <https://admin.microsoft.com> en klik op Alles **tonen.**</span><span class="sxs-lookup"><span data-stu-id="0b7c8-112">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klik op Alles tonen in het Microsoft 365-beheercentrum](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="0b7c8-114">Klik in **de sectie Beheercentra** die wordt weergegeven op **Alle beheercentra.**</span><span class="sxs-lookup"><span data-stu-id="0b7c8-114">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klik op Alle beheercentra in het Microsoft 365-beheercentrum](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="0b7c8-116">Klik op **de pagina Alle beheercentra** die wordt weergegeven op **Exchange Online Protection.**</span><span class="sxs-lookup"><span data-stu-id="0b7c8-116">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="0b7c8-117">Ga rechtstreeks naar `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="0b7c8-117">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="0b7c8-118">Algemene elementen van de gebruikersinterface in het EAC in EOP</span><span class="sxs-lookup"><span data-stu-id="0b7c8-118">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="0b7c8-119">In deze sectie worden de elementen van de gebruikersinterface beschreven die in het EAC worden gevonden.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-119">This section describes the user interface elements that are found in the EAC.</span></span>

![Het Exchange-beheercentrum in Exchange Online Protection](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="0b7c8-121">Functiedeelvenster</span><span class="sxs-lookup"><span data-stu-id="0b7c8-121">Feature Pane</span></span>

<span data-ttu-id="0b7c8-122">Dit is het eerste navigatieniveau voor de meeste taken die u in het EAC uitvoert.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-122">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="0b7c8-123">Het functievenster is ingedeeld op functiegebieden.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-123">The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="0b7c8-124">**Geadresseerden:** hier worden groepen en externe contactpersonen bekeken.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-124">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="0b7c8-125">**Machtigingen:** dit is de plek waar u beheerdersrollen beheert.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-125">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="0b7c8-126">**Compliancebeheer:** hier vindt u het rapport van de beheerdersrolgroep en het auditlogboekrapport van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-126">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="0b7c8-127">**Beveiliging:** hier kunt u anti-malwarebeleid, het standaardbeleid voor verbindingsfilters en DKIM beheren.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-127">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="0b7c8-128">U moet anti-malwarebeleid en het standaardbeleid voor verbindingsfilters beheren in & compliancecentrum.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-128">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="0b7c8-129">Zie [Anti-malwarebeleid](configure-anti-malware-policies.md) configureren in EOP en [Verbindingsfilters configureren in EOP](configure-the-connection-filter-policy.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-129">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="0b7c8-130">**E-mailstroom:** hier beheert u regels voor de e-mailstroom (ook wel transportregels genoemd), geaccepteerde domeinen en verbindingslijnen, en kunt u berichten traceren.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-130">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="0b7c8-131">**Hybride:** Hier kunt u de wizard Hybride configuratie uitvoeren [en](/Exchange/hybrid-configuration-wizard)de Exchange [Online PowerShell-module installeren.](/powershell/exchange/mfa-connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-131">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="0b7c8-132">Tabbladen</span><span class="sxs-lookup"><span data-stu-id="0b7c8-132">Tabs</span></span>

<span data-ttu-id="0b7c8-133">De tabbladen zijn uw tweede navigatieniveau.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-133">The tabs are your second level of navigation.</span></span> <span data-ttu-id="0b7c8-134">Elk van de functiegebieden bevat verschillende tabbladen, die elk een functie vertegenwoordigen.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-134">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="0b7c8-135">Werkbalk</span><span class="sxs-lookup"><span data-stu-id="0b7c8-135">Toolbar</span></span>

<span data-ttu-id="0b7c8-136">Wanneer u op de meeste tabbladen klikt, ziet u een werkbalk.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-136">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="0b7c8-137">De werkbalk heeft pictogrammen die een specifieke actie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-137">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="0b7c8-138">In de volgende tabel worden de pictogrammen en hun acties beschreven.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-138">The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="0b7c8-139">Pictogram</span><span class="sxs-lookup"><span data-stu-id="0b7c8-139">Icon</span></span>|<span data-ttu-id="0b7c8-140">Naam</span><span class="sxs-lookup"><span data-stu-id="0b7c8-140">Name</span></span>|<span data-ttu-id="0b7c8-141">Actie</span><span class="sxs-lookup"><span data-stu-id="0b7c8-141">Action</span></span>|
|---|---|---|
|![Pictogram Toevoegen](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="0b7c8-143">Toevoegen, Nieuw</span><span class="sxs-lookup"><span data-stu-id="0b7c8-143">Add, New</span></span>|<span data-ttu-id="0b7c8-144">Gebruik dit pictogram om een nieuw object te maken.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-144">Use this icon to create a new object.</span></span> <span data-ttu-id="0b7c8-145">Sommige van deze pictogrammen hebben een bijbehorende pijl-omlaag waar u op kunt klikken om extra objecten weer te geven die u kunt maken.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-145">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Pictogram Bewerken](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="0b7c8-147">Bewerken</span><span class="sxs-lookup"><span data-stu-id="0b7c8-147">Edit</span></span>|<span data-ttu-id="0b7c8-148">Gebruik dit pictogram om een object te bewerken.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-148">Use this icon to edit an object.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="0b7c8-150">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="0b7c8-150">Delete</span></span>|<span data-ttu-id="0b7c8-151">Gebruik dit pictogram om een object te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-151">Use this icon to delete an object.</span></span> <span data-ttu-id="0b7c8-152">Sommige verwijderpictogrammen hebben een pijl-omlaag waar u op kunt klikken om extra opties weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-152">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|<span data-ttu-id="0b7c8-154">Zoeken</span><span class="sxs-lookup"><span data-stu-id="0b7c8-154">Search</span></span>|<span data-ttu-id="0b7c8-155">Gebruik dit pictogram om een zoekvak te openen waarin u de zoekzin kunt typen voor een object dat u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-155">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="0b7c8-157">Vernieuwen</span><span class="sxs-lookup"><span data-stu-id="0b7c8-157">Refresh</span></span>|<span data-ttu-id="0b7c8-158">Gebruik dit pictogram om de lijstweergave te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-158">Use this icon to refresh the list view.</span></span>|
|![Pictogram Meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="0b7c8-160">Meer opties</span><span class="sxs-lookup"><span data-stu-id="0b7c8-160">More options</span></span>|<span data-ttu-id="0b7c8-161">Gebruik dit pictogram om meer acties weer te geven die u kunt uitvoeren voor de objecten van dat tabblad.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-161">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="0b7c8-162">In Geadresseerden **worden bijvoorbeeld gebruikers weergegeven \> die** op dit pictogram klikken, de optie om een geavanceerd zoeken **uit te voeren.**</span><span class="sxs-lookup"><span data-stu-id="0b7c8-162">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Pictogram Pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram Pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="0b7c8-165">Pijl-omhoog en pijl-omlaag</span><span class="sxs-lookup"><span data-stu-id="0b7c8-165">Up arrow and down arrow</span></span>|<span data-ttu-id="0b7c8-166">Gebruik deze pictogrammen om de prioriteit van een object omhoog of omlaag te verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-166">Use these icons to move an object's priority up or down.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="0b7c8-168">Verwijderen</span><span class="sxs-lookup"><span data-stu-id="0b7c8-168">Remove</span></span>|<span data-ttu-id="0b7c8-169">Gebruik dit pictogram om objecten uit een lijst te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-169">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="0b7c8-170">Lijstweergave</span><span class="sxs-lookup"><span data-stu-id="0b7c8-170">List View</span></span>

<span data-ttu-id="0b7c8-171">Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-171">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="0b7c8-172">De weergavelimiet met de EAC-lijstweergave is ongeveer 10.000 objecten.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-172">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="0b7c8-173">Daarnaast is paging opgenomen, zodat u naar resultaten kunt pagina's.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-173">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="0b7c8-174">Detailvenster</span><span class="sxs-lookup"><span data-stu-id="0b7c8-174">Details Pane</span></span>

<span data-ttu-id="0b7c8-175">Wanneer u een object selecteert in de lijstweergave, wordt informatie over dat object weergegeven in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-175">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="0b7c8-176">In sommige gevallen bevat het detailvenster beheertaken.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-176">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="0b7c8-177">Mij-tegel en Help</span><span class="sxs-lookup"><span data-stu-id="0b7c8-177">Me tile and Help</span></span>

<span data-ttu-id="0b7c8-178">Met **de tegel** Ik kunt u het EAC afmelden en u aanmelden als een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-178">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="0b7c8-179">In de **vervolgkeuzelijst** ![ ](../../media/ITPro-EAC-HelpIcon.gif) Help-pictogram help kunt u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="0b7c8-179">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can do the following actions:</span></span>

- <span data-ttu-id="0b7c8-180">**Help:** Klik op ![ ](../../media/ITPro-EAC-HelpIcon.gif) Help-pictogram om de online Help-inhoud weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-180">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>
- <span data-ttu-id="0b7c8-181">**Feedback:** Feedback geven.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-181">**Feedback**: Leave feedback.</span></span>
- <span data-ttu-id="0b7c8-182">**Community:** Plaats een vraag voor het vinden van antwoorden in de communityforums.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-182">**Community**: Post a question for find answers in the community forums.</span></span>
- <span data-ttu-id="0b7c8-183">**Help-bellen uitschakelen:** in de Help-bel worden contextuele help-informatie weergegeven voor velden wanneer u een object maakt of bewerkt.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-183">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="0b7c8-184">U kunt de Help-bel uitschakelen of in- of uitschakelen als deze is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-184">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>
- <span data-ttu-id="0b7c8-185">**Opdrachtregistratie weergeven:** er wordt een nieuw venster geopend waarin de equivalente PowerShell-opdrachten worden weergegeven op basis van wat u hebt geconfigureerd in EAC.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-185">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="0b7c8-186">Ondersteunde browsers</span><span class="sxs-lookup"><span data-stu-id="0b7c8-186">Supported Browsers</span></span>

<span data-ttu-id="0b7c8-187">Voor de beste ervaring met het EAC raden we u aan altijd de nieuwste browsers, Office-clients en apps te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-187">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="0b7c8-188">We raden u ook aan software-updates te installeren wanneer deze beschikbaar komen.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-188">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="0b7c8-189">Zie Systeemvereisten voor Office voor meer informatie over de ondersteunde browsers en systeemvereisten [voor de service.](https://products.office.com/office-system-requirements)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-189">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="0b7c8-190">Ondersteunde talen</span><span class="sxs-lookup"><span data-stu-id="0b7c8-190">Supported languages</span></span>

<span data-ttu-id="0b7c8-191">De volgende talen worden ondersteund en beschikbaar voor het EAC in zelfstandige EOP.</span><span class="sxs-lookup"><span data-stu-id="0b7c8-191">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="0b7c8-192">Amharic</span><span class="sxs-lookup"><span data-stu-id="0b7c8-192">Amharic</span></span>
- <span data-ttu-id="0b7c8-193">Arabisch</span><span class="sxs-lookup"><span data-stu-id="0b7c8-193">Arabic</span></span>
- <span data-ttu-id="0b7c8-194">Baskisch (Baskisch)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-194">Basque (Basque)</span></span>
- <span data-ttu-id="0b7c8-195">Bengali (India)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-195">Bengali (India)</span></span>
- <span data-ttu-id="0b7c8-196">Bulgarian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-196">Bulgarian</span></span>
- <span data-ttu-id="0b7c8-197">Catalan</span><span class="sxs-lookup"><span data-stu-id="0b7c8-197">Catalan</span></span>
- <span data-ttu-id="0b7c8-198">Chinees (vereenvoudigd)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-198">Chinese (Simplified)</span></span>
- <span data-ttu-id="0b7c8-199">Chinees (traditioneel)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-199">Chinese (Traditional)</span></span>
- <span data-ttu-id="0b7c8-200">Croatian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-200">Croatian</span></span>
- <span data-ttu-id="0b7c8-201">Czech</span><span class="sxs-lookup"><span data-stu-id="0b7c8-201">Czech</span></span>
- <span data-ttu-id="0b7c8-202">Danish</span><span class="sxs-lookup"><span data-stu-id="0b7c8-202">Danish</span></span>
- <span data-ttu-id="0b7c8-203">Dutch</span><span class="sxs-lookup"><span data-stu-id="0b7c8-203">Dutch</span></span>
- <span data-ttu-id="0b7c8-204">Engels</span><span class="sxs-lookup"><span data-stu-id="0b7c8-204">English</span></span>
- <span data-ttu-id="0b7c8-205">Estonian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-205">Estonian</span></span>
- <span data-ttu-id="0b7c8-206">Filipijns (Filipijnen)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-206">Filipino (Philippines)</span></span>
- <span data-ttu-id="0b7c8-207">Finnish</span><span class="sxs-lookup"><span data-stu-id="0b7c8-207">Finnish</span></span>
- <span data-ttu-id="0b7c8-208">French</span><span class="sxs-lookup"><span data-stu-id="0b7c8-208">French</span></span>
- <span data-ttu-id="0b7c8-209">Galician</span><span class="sxs-lookup"><span data-stu-id="0b7c8-209">Galician</span></span>
- <span data-ttu-id="0b7c8-210">German</span><span class="sxs-lookup"><span data-stu-id="0b7c8-210">German</span></span>
- <span data-ttu-id="0b7c8-211">Greek</span><span class="sxs-lookup"><span data-stu-id="0b7c8-211">Greek</span></span>
- <span data-ttu-id="0b7c8-212">Gujarati</span><span class="sxs-lookup"><span data-stu-id="0b7c8-212">Gujarati</span></span>
- <span data-ttu-id="0b7c8-213">Hebrew</span><span class="sxs-lookup"><span data-stu-id="0b7c8-213">Hebrew</span></span>
- <span data-ttu-id="0b7c8-214">Hindi</span><span class="sxs-lookup"><span data-stu-id="0b7c8-214">Hindi</span></span>
- <span data-ttu-id="0b7c8-215">Hungarian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-215">Hungarian</span></span>
- <span data-ttu-id="0b7c8-216">IJslands</span><span class="sxs-lookup"><span data-stu-id="0b7c8-216">Icelandic</span></span>
- <span data-ttu-id="0b7c8-217">Indonesian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-217">Indonesian</span></span>
- <span data-ttu-id="0b7c8-218">Italian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-218">Italian</span></span>
- <span data-ttu-id="0b7c8-219">Japanese</span><span class="sxs-lookup"><span data-stu-id="0b7c8-219">Japanese</span></span>
- <span data-ttu-id="0b7c8-220">Kannada</span><span class="sxs-lookup"><span data-stu-id="0b7c8-220">Kannada</span></span>
- <span data-ttu-id="0b7c8-221">Kazakh</span><span class="sxs-lookup"><span data-stu-id="0b7c8-221">Kazakh</span></span>
- <span data-ttu-id="0b7c8-222">Kiswahili</span><span class="sxs-lookup"><span data-stu-id="0b7c8-222">Kiswahili</span></span>
- <span data-ttu-id="0b7c8-223">Korean</span><span class="sxs-lookup"><span data-stu-id="0b7c8-223">Korean</span></span>
- <span data-ttu-id="0b7c8-224">Latvian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-224">Latvian</span></span>
- <span data-ttu-id="0b7c8-225">Lithuanian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-225">Lithuanian</span></span>
- <span data-ttu-id="0b7c8-226">Maleis (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-226">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="0b7c8-227">Maleis (Maleisië)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-227">Malay (Malaysia)</span></span>
- <span data-ttu-id="0b7c8-228">Malajalam</span><span class="sxs-lookup"><span data-stu-id="0b7c8-228">Malayalam</span></span>
- <span data-ttu-id="0b7c8-229">Marathi</span><span class="sxs-lookup"><span data-stu-id="0b7c8-229">Marathi</span></span>
- <span data-ttu-id="0b7c8-230">Noors (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-230">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="0b7c8-231">Noors (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-231">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="0b7c8-232">Oriya</span><span class="sxs-lookup"><span data-stu-id="0b7c8-232">Oriya</span></span>
- <span data-ttu-id="0b7c8-233">Perzisch</span><span class="sxs-lookup"><span data-stu-id="0b7c8-233">Persian</span></span>
- <span data-ttu-id="0b7c8-234">Polish</span><span class="sxs-lookup"><span data-stu-id="0b7c8-234">Polish</span></span>
- <span data-ttu-id="0b7c8-235">Portugees (Brazilië)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-235">Portuguese (Brazil)</span></span>
- <span data-ttu-id="0b7c8-236">Portugees (Portugal)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-236">Portuguese (Portugal)</span></span>
- <span data-ttu-id="0b7c8-237">Romanian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-237">Romanian</span></span>
- <span data-ttu-id="0b7c8-238">Russian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-238">Russian</span></span>
- <span data-ttu-id="0b7c8-239">Servisch (Cyrillisch, Servië)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-239">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="0b7c8-240">Servisch (Latijns)</span><span class="sxs-lookup"><span data-stu-id="0b7c8-240">Serbian (Latin)</span></span>
- <span data-ttu-id="0b7c8-241">Slovak</span><span class="sxs-lookup"><span data-stu-id="0b7c8-241">Slovak</span></span>
- <span data-ttu-id="0b7c8-242">Slovenian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-242">Slovenian</span></span>
- <span data-ttu-id="0b7c8-243">Spanish</span><span class="sxs-lookup"><span data-stu-id="0b7c8-243">Spanish</span></span>
- <span data-ttu-id="0b7c8-244">Swedish</span><span class="sxs-lookup"><span data-stu-id="0b7c8-244">Swedish</span></span>
- <span data-ttu-id="0b7c8-245">Tamil</span><span class="sxs-lookup"><span data-stu-id="0b7c8-245">Tamil</span></span>
- <span data-ttu-id="0b7c8-246">Telugu</span><span class="sxs-lookup"><span data-stu-id="0b7c8-246">Telugu</span></span>
- <span data-ttu-id="0b7c8-247">Thai</span><span class="sxs-lookup"><span data-stu-id="0b7c8-247">Thai</span></span>
- <span data-ttu-id="0b7c8-248">Turkish</span><span class="sxs-lookup"><span data-stu-id="0b7c8-248">Turkish</span></span>
- <span data-ttu-id="0b7c8-249">Ukrainian</span><span class="sxs-lookup"><span data-stu-id="0b7c8-249">Ukrainian</span></span>
- <span data-ttu-id="0b7c8-250">Urdu</span><span class="sxs-lookup"><span data-stu-id="0b7c8-250">Urdu</span></span>
- <span data-ttu-id="0b7c8-251">Vietnamese</span><span class="sxs-lookup"><span data-stu-id="0b7c8-251">Vietnamese</span></span>
- <span data-ttu-id="0b7c8-252">Welsh</span><span class="sxs-lookup"><span data-stu-id="0b7c8-252">Welsh</span></span>