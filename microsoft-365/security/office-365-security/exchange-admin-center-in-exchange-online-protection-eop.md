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
description: Meer informatie over de web management interface in standalone Exchange Online Protection (EOP).
ms.openlocfilehash: 732991befa9084b62c152295d10a2bbf94bc36ec
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202949"
---
# <a name="exchange-admin-center-in-standalone-eop"></a><span data-ttu-id="63a33-103">Exchange-beheercentrum in standalone EOP</span><span class="sxs-lookup"><span data-stu-id="63a33-103">Exchange admin center in standalone EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="63a33-104">Het Exchange-Beheercentrum is een webgebaseerd beheerconsole voor standalone Exchange Online Protection (EOP).</span><span class="sxs-lookup"><span data-stu-id="63a33-104">The Exchange admin center (EAC) is a web-based management console for standalone Exchange Online Protection (EOP).</span></span>

<span data-ttu-id="63a33-105">Zoekt u de Exchange Online-versie van dit onderwerp?</span><span class="sxs-lookup"><span data-stu-id="63a33-105">Looking for the Exchange Online version of this topic?</span></span> <span data-ttu-id="63a33-106">Zie [Exchange-Beheercentrum in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="63a33-106">See [Exchange admin center in Exchange Online](https://docs.microsoft.com/exchange/exchange-admin-center).</span></span>

## <a name="open-the-eac-in-eop"></a><span data-ttu-id="63a33-107">Het Exchange-Beheercentrum openen in EOP</span><span class="sxs-lookup"><span data-stu-id="63a33-107">Open the EAC in EOP</span></span>

<span data-ttu-id="63a33-108">Zelfstandige EOP-klanten hebben toegang tot het SBV-programma met behulp van de volgende methoden:</span><span class="sxs-lookup"><span data-stu-id="63a33-108">Standalone EOP customers can access the EAC by using the following methods:</span></span>

- <span data-ttu-id="63a33-109">**Vanuit het Microsoft 365-Beheercentrum**:</span><span class="sxs-lookup"><span data-stu-id="63a33-109">**From the Microsoft 365 admin center**:</span></span>

  1. <span data-ttu-id="63a33-110">Ga naar <https://admin.microsoft.com> en klik op **AllesWeergeven**.</span><span class="sxs-lookup"><span data-stu-id="63a33-110">Go to <https://admin.microsoft.com> and click **Show all**.</span></span>

     ![Klik op AllesWeergeven in het Microsoft 365-Beheercentrum](../../media/m365-center-show-all.png)

  2. <span data-ttu-id="63a33-112">Klik in de sectie **beheer centra** die wordt weergegeven op **alle beheer centra**.</span><span class="sxs-lookup"><span data-stu-id="63a33-112">In the **Admin centers** section that appears, click **All admin centers**.</span></span>

     ![Klik op alle beheer centra in het Microsoft 365-Beheercentrum.](../../media/m365-center-select-all-admin-centers.png)

  3. <span data-ttu-id="63a33-114">Op de pagina **all admin Centers** die worden weergegeven, klikt u op **Exchange Online Protection**.</span><span class="sxs-lookup"><span data-stu-id="63a33-114">On the **All admin centers** page that appears, click **Exchange Online Protection**.</span></span>

- <span data-ttu-id="63a33-115">Ga rechtstreeks naar `https://admin.protection.outlook.com/ecp/` .</span><span class="sxs-lookup"><span data-stu-id="63a33-115">Go directly to `https://admin.protection.outlook.com/ecp/`.</span></span>

## <a name="common-user-interface-elements-in-the-eac-in-eop"></a><span data-ttu-id="63a33-116">Veelvoorkomende elementen van de gebruikersinterface in het Exchange-Beheercentrum in EOP</span><span class="sxs-lookup"><span data-stu-id="63a33-116">Common user interface elements in the EAC in EOP</span></span>

<span data-ttu-id="63a33-117">In deze sectie worden de onderdelen van de gebruikersinterface beschreven die zijn gevonden in het Exchange-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="63a33-117">This section describes the user interface elements that are found in the EAC.</span></span>

![EOP-Te102827792beheercentrum](../../media/EOP-AdminCenter.png)

### <a name="feature-pane"></a><span data-ttu-id="63a33-119">Deelvenster functie</span><span class="sxs-lookup"><span data-stu-id="63a33-119">Feature Pane</span></span>

<span data-ttu-id="63a33-120">Dit is het eerste niveau van navigatie voor de meeste taken die u in het Exchange-Beheercentrum uitvoert.</span><span class="sxs-lookup"><span data-stu-id="63a33-120">This is the first level of navigation for most of the tasks you'll perform in the EAC.</span></span> <span data-ttu-id="63a33-121">Het deelvenster functie is ingedeeld op functiegebieden.</span><span class="sxs-lookup"><span data-stu-id="63a33-121">The feature pane is organized by feature areas.</span></span>

- <span data-ttu-id="63a33-122">**Geadresseerden**: in dit voorbeeld ziet u groepen en externe contactpersonen.</span><span class="sxs-lookup"><span data-stu-id="63a33-122">**Recipients**: This is where you'll view groups and external contacts.</span></span>

- <span data-ttu-id="63a33-123">**Machtigingen**: Hiermee beheert u beheerdersrollen.</span><span class="sxs-lookup"><span data-stu-id="63a33-123">**Permissions**: This where you'll manage admin roles.</span></span>

- <span data-ttu-id="63a33-124">**Nalevings beheer**: Hier vindt u het rapport met rollen van beheerders en het controleverslag van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="63a33-124">**Compliance Management**: This is where you'll find the administrator role group report and the admin audit log report.</span></span>

- <span data-ttu-id="63a33-125">**Beveiliging**: hier kunt u beleidsregels voor anti malware, het standaardbeleid voor verbindings filters en dkim.</span><span class="sxs-lookup"><span data-stu-id="63a33-125">**Protection**: This is where you can manage anti-malware policies, the default connection filter policy, and DKIM.</span></span>

  > [!NOTE]
  > <span data-ttu-id="63a33-126">U dient beleidsregels voor anti-malware en het standaardbeleid voor verbindings filters te beheren in het compliance-& Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="63a33-126">You should manage anti-malware policies and the default connection filter policy in the Security & Compliance Center.</span></span> <span data-ttu-id="63a33-127">Zie voor meer informatie [anti-malwarebeleid in EOP configureren](configure-anti-malware-policies.md) en het [filteren van verbindingen in EOP configureren](configure-the-connection-filter-policy.md).</span><span class="sxs-lookup"><span data-stu-id="63a33-127">For more information, see [Configure anti-malware policies in EOP](configure-anti-malware-policies.md) and [Configure connection filtering in EOP](configure-the-connection-filter-policy.md).</span></span>

- <span data-ttu-id="63a33-128">**E-mail stroom**: dit is waar u de e-mail stroom regels (ook wel de zogenaamde transportregels genoemd), geaccepteerde domeinen en connectors beheert, en waar u de bericht tracering kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="63a33-128">**Mail Flow**: This is where you'll manage mail flow rules (also known as transport rules), accepted domains, and connectors, as well as where you can go to run message trace.</span></span>

- <span data-ttu-id="63a33-129">**Hybride**: dit is de plek waar u de [wizard hybride configuratie](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard)kunt uitvoeren en waar u de [PowerShell-module van Exchange Online](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell)kunt installeren.</span><span class="sxs-lookup"><span data-stu-id="63a33-129">**Hybrid**: This is where you can run the [Hybrid Configuration Wizard](https://docs.microsoft.com/Exchange/hybrid-configuration-wizard), and where you can install the [Exchange Online PowerShell module](https://docs.microsoft.com/powershell/exchange/mfa-connect-to-exchange-online-powershell).</span></span>

### <a name="tabs"></a><span data-ttu-id="63a33-130">Tabvolgorde</span><span class="sxs-lookup"><span data-stu-id="63a33-130">Tabs</span></span>

<span data-ttu-id="63a33-131">De tabbladen vormen een tweede navigatieniveau.</span><span class="sxs-lookup"><span data-stu-id="63a33-131">The tabs are your second level of navigation.</span></span> <span data-ttu-id="63a33-132">Elk functiegebied bevat diverse tabbladen, elk met een functie.</span><span class="sxs-lookup"><span data-stu-id="63a33-132">Each of the feature areas contains various tabs, each representing a feature.</span></span>

### <a name="toolbar"></a><span data-ttu-id="63a33-133">Werkbalk</span><span class="sxs-lookup"><span data-stu-id="63a33-133">Toolbar</span></span>

<span data-ttu-id="63a33-134">Wanneer u op de meeste tabbladen klikt, wordt een werkbalk weergegeven.</span><span class="sxs-lookup"><span data-stu-id="63a33-134">When you click most tabs, you'll see a toolbar.</span></span> <span data-ttu-id="63a33-135">De werkbalk bevat pictogrammen die een specifieke actie uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="63a33-135">The toolbar has icons that perform a specific action.</span></span> <span data-ttu-id="63a33-136">In de volgende tabel worden de pictogrammen en de bijbehorende acties beschreven.</span><span class="sxs-lookup"><span data-stu-id="63a33-136">The following table describes the icons and their actions.</span></span>

****

|<span data-ttu-id="63a33-137">Pictogram</span><span class="sxs-lookup"><span data-stu-id="63a33-137">Icon</span></span>|<span data-ttu-id="63a33-138">Naam</span><span class="sxs-lookup"><span data-stu-id="63a33-138">Name</span></span>|<span data-ttu-id="63a33-139">Actierij</span><span class="sxs-lookup"><span data-stu-id="63a33-139">Action</span></span>|
|---|---|---|
|![Pictogram toevoegen](../../media/ITPro-EAC-AddIcon.gif)|<span data-ttu-id="63a33-141">Toevoegen, nieuw</span><span class="sxs-lookup"><span data-stu-id="63a33-141">Add, New</span></span>|<span data-ttu-id="63a33-142">Gebruik dit pictogram om een nieuw object te maken.</span><span class="sxs-lookup"><span data-stu-id="63a33-142">Use this icon to create a new object.</span></span> <span data-ttu-id="63a33-143">Sommige van deze pictogrammen bevatten een pijl-omlaag waarop u kunt klikken om extra objecten weer te geven die u kunt maken.</span><span class="sxs-lookup"><span data-stu-id="63a33-143">Some of these icons have an associated down arrow you can click to show additional objects you can create.</span></span>|
|![Pictogram bewerken](../../media/ITPro-EAC-EditIcon.gif)|<span data-ttu-id="63a33-145">Bewerken</span><span class="sxs-lookup"><span data-stu-id="63a33-145">Edit</span></span>|<span data-ttu-id="63a33-146">Gebruik dit pictogram als u een object wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="63a33-146">Use this icon to edit an object.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-DeleteIcon.gif)|<span data-ttu-id="63a33-148">Wissen</span><span class="sxs-lookup"><span data-stu-id="63a33-148">Delete</span></span>|<span data-ttu-id="63a33-149">Gebruik dit pictogram om een object te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="63a33-149">Use this icon to delete an object.</span></span> <span data-ttu-id="63a33-150">Sommige delete-pictogrammen bevatten een pijl-omlaag waarop u kunt klikken om extra opties weer te geven.</span><span class="sxs-lookup"><span data-stu-id="63a33-150">Some delete icons have a down arrow you can click to show additional options.</span></span>|
|![Pictogram Zoeken](../../media/ITPro-EAC-.gif)|<span data-ttu-id="63a33-152">Vinden</span><span class="sxs-lookup"><span data-stu-id="63a33-152">Search</span></span>|<span data-ttu-id="63a33-153">Gebruik dit pictogram om een zoekvak te openen waarin u de zoekterm kunt typen voor een object dat u wilt zoeken.</span><span class="sxs-lookup"><span data-stu-id="63a33-153">Use this icon to open a search box in which you can type the search phrase for an object you want to find.</span></span>|
|![Pictogram Vernieuwen](../../media/ITPro-EAC-RefreshIcon.gif)|<span data-ttu-id="63a33-155">Vernieuwen</span><span class="sxs-lookup"><span data-stu-id="63a33-155">Refresh</span></span>|<span data-ttu-id="63a33-156">Gebruik dit pictogram om de lijstweergave te vernieuwen.</span><span class="sxs-lookup"><span data-stu-id="63a33-156">Use this icon to refresh the list view.</span></span>|
|![Pictogram meer opties](../../media/ITPro-EAC-MoreOptionsIcon.gif)|<span data-ttu-id="63a33-158">Meer opties</span><span class="sxs-lookup"><span data-stu-id="63a33-158">More options</span></span>|<span data-ttu-id="63a33-159">Gebruik dit pictogram om meer acties weer te geven die u voor dit tabblad objecten kunt uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="63a33-159">Use this icon to view more actions you can perform for that tab's objects.</span></span> <span data-ttu-id="63a33-160">Bij \*\* \> gebruikers\*\* die op dit pictogram klikken, ziet u bijvoorbeeld de optie voor het uitvoeren van een **Geavanceerd zoeken**.</span><span class="sxs-lookup"><span data-stu-id="63a33-160">For example, in **Recipients \> Users** clicking this icon shows the option to perform an **Advanced Search**.</span></span>|
|![Pictogram pijl-omhoog](../../media/ITPro-EAC-UpArrowIcon.gif)![Pictogram pijl-omlaag](../../media/ITPro-EAC-DownArrowIcon.gif)|<span data-ttu-id="63a33-163">Pijl-omhoog en pijl-omlaag</span><span class="sxs-lookup"><span data-stu-id="63a33-163">Up arrow and down arrow</span></span>|<span data-ttu-id="63a33-164">Gebruik deze pictogrammen als u de prioriteit van een object omhoog of omlaag wilt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="63a33-164">Use these icons to move an object's priority up or down.</span></span>|
|![Pictogram Verwijderen](../../media/ITPro-EAC-RemoveIcon.gif)|<span data-ttu-id="63a33-166">Schakel</span><span class="sxs-lookup"><span data-stu-id="63a33-166">Remove</span></span>|<span data-ttu-id="63a33-167">Gebruik dit pictogram om objecten uit een lijst te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="63a33-167">Use this icon to remove objects from a list.</span></span>|
|

### <a name="list-view"></a><span data-ttu-id="63a33-168">Lijstweergave</span><span class="sxs-lookup"><span data-stu-id="63a33-168">List View</span></span>

<span data-ttu-id="63a33-169">Wanneer u een tabblad selecteert, ziet u in de meeste gevallen een lijstweergave.</span><span class="sxs-lookup"><span data-stu-id="63a33-169">When you select a tab, in most cases you'll see a list view.</span></span> <span data-ttu-id="63a33-170">De zichtbare limiet met de lijstweergave van het SBV is ongeveer 10.000 objecten.</span><span class="sxs-lookup"><span data-stu-id="63a33-170">The viewable limit with the EAC list view is approximately 10,000 objects.</span></span> <span data-ttu-id="63a33-171">Daarnaast is paginering ook opgenomen, zodat u de resultaten van de pagina kunt laten opvallen.</span><span class="sxs-lookup"><span data-stu-id="63a33-171">In addition, paging is included so that you can page to results.</span></span>

### <a name="details-pane"></a><span data-ttu-id="63a33-172">Deelvenster Details</span><span class="sxs-lookup"><span data-stu-id="63a33-172">Details Pane</span></span>

<span data-ttu-id="63a33-173">Wanneer u in de lijstweergave een object selecteert, wordt informatie over dat object weergegeven in het detailvenster.</span><span class="sxs-lookup"><span data-stu-id="63a33-173">When you select an object from the list view, information about that object is displayed in the details pane.</span></span> <span data-ttu-id="63a33-174">In sommige gevallen bevat het detailvenster beheertaken.</span><span class="sxs-lookup"><span data-stu-id="63a33-174">In some cases the details pane includes management tasks.</span></span>

### <a name="me-tile-and-help"></a><span data-ttu-id="63a33-175">Ik-tegel en Help</span><span class="sxs-lookup"><span data-stu-id="63a33-175">Me tile and Help</span></span>

<span data-ttu-id="63a33-176">Met de tegel **Ik** kunt u zich afmelden bij het SBV-bericht en u aanmelden als een andere gebruiker.</span><span class="sxs-lookup"><span data-stu-id="63a33-176">The **Me** tile allows you to sign out the EAC and sign in as a different user.</span></span> <span data-ttu-id="63a33-177">In het **Help** ![ ](../../media/ITPro-EAC-HelpIcon.gif) vervolgkeuzemenu Help-Help-pictogram kunt u de volgende acties uitvoeren:</span><span class="sxs-lookup"><span data-stu-id="63a33-177">From the **Help**![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) drop-down menu, you can perform the following actions:</span></span>

- <span data-ttu-id="63a33-178">**Help**: Klik op ![ Help-pictogram ](../../media/ITPro-EAC-HelpIcon.gif) om de inhoud van de online-Help weer te geven.</span><span class="sxs-lookup"><span data-stu-id="63a33-178">**Help**: Click ![Help Icon](../../media/ITPro-EAC-HelpIcon.gif) to view the online help content.</span></span>

- <span data-ttu-id="63a33-179">**Feedback**: Geef feedback.</span><span class="sxs-lookup"><span data-stu-id="63a33-179">**Feedback**: Leave feedback.</span></span>

- <span data-ttu-id="63a33-180">**Community**: Stel een vraag voor het zoeken van antwoorden op de forums van de community.</span><span class="sxs-lookup"><span data-stu-id="63a33-180">**Community**: Post a question for find answers in the community forums.</span></span>

- <span data-ttu-id="63a33-181">**Help bellen uitschakelen**: de Help-Bel wordt contextuele Help voor velden weergegeven wanneer u een object maakt of bewerkt.</span><span class="sxs-lookup"><span data-stu-id="63a33-181">**Disable Help bubble**: The Help bubble displays contextual help for fields when you create or edit an object.</span></span> <span data-ttu-id="63a33-182">U kunt de Help bellen uitschakelen of inschakelen als deze functie is uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="63a33-182">You can turn off the Help bubble or turn it on if it has been disabled.</span></span>

- <span data-ttu-id="63a33-183">**Logboekregistratie weergeven**: er wordt een nieuw venster geopend waarin de overeenkomstige PowerShell-opdrachten worden weergegeven op basis van wat u hebt geconfigureerd in het SBV</span><span class="sxs-lookup"><span data-stu-id="63a33-183">**Show Command Logging**: A new window opens that shows the equivalent PowerShell commands based on what you configured in EAC.</span></span>

## <a name="supported-browsers"></a><span data-ttu-id="63a33-184">Ondersteunde browsers</span><span class="sxs-lookup"><span data-stu-id="63a33-184">Supported Browsers</span></span>

<span data-ttu-id="63a33-185">Voor de beste ervaring met het beheer van het beheer wordt u aangeraden altijd de meest recente browsers, Office-clients en apps te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="63a33-185">For the best experience using the EAC, we recommend that you always use the latest browsers, Office clients, and apps.</span></span> <span data-ttu-id="63a33-186">We raden u ook aan software-updates te installeren wanneer deze beschikbaar komen.</span><span class="sxs-lookup"><span data-stu-id="63a33-186">We also recommend that you install software updates when they become available.</span></span> <span data-ttu-id="63a33-187">Zie [systeemvereisten voor Office](https://products.office.com/office-system-requirements)voor meer informatie over de ondersteunde browsers en systeemvereisten voor de service.</span><span class="sxs-lookup"><span data-stu-id="63a33-187">For more information about the supported browsers and system requirements for the service, see [System requirements for Office](https://products.office.com/office-system-requirements).</span></span>

## <a name="supported-languages"></a><span data-ttu-id="63a33-188">Ondersteunde talen</span><span class="sxs-lookup"><span data-stu-id="63a33-188">Supported languages</span></span>

<span data-ttu-id="63a33-189">De volgende talen worden ondersteund en zijn beschikbaar voor de EOP in standalone.</span><span class="sxs-lookup"><span data-stu-id="63a33-189">The following languages are supported and available for the EAC in standalone EOP.</span></span>

- <span data-ttu-id="63a33-190">Amhaars</span><span class="sxs-lookup"><span data-stu-id="63a33-190">Amharic</span></span>
- <span data-ttu-id="63a33-191">Arabisch</span><span class="sxs-lookup"><span data-stu-id="63a33-191">Arabic</span></span>
- <span data-ttu-id="63a33-192">Baskisch (Baskisch)</span><span class="sxs-lookup"><span data-stu-id="63a33-192">Basque (Basque)</span></span>
- <span data-ttu-id="63a33-193">Bengalees (India)</span><span class="sxs-lookup"><span data-stu-id="63a33-193">Bengali (India)</span></span>
- <span data-ttu-id="63a33-194">Bulgarian</span><span class="sxs-lookup"><span data-stu-id="63a33-194">Bulgarian</span></span>
- <span data-ttu-id="63a33-195">Catalan</span><span class="sxs-lookup"><span data-stu-id="63a33-195">Catalan</span></span>
- <span data-ttu-id="63a33-196">Chinees (vereenvoudigd)</span><span class="sxs-lookup"><span data-stu-id="63a33-196">Chinese (Simplified)</span></span>
- <span data-ttu-id="63a33-197">Chinees (traditioneel)</span><span class="sxs-lookup"><span data-stu-id="63a33-197">Chinese (Traditional)</span></span>
- <span data-ttu-id="63a33-198">Croatian</span><span class="sxs-lookup"><span data-stu-id="63a33-198">Croatian</span></span>
- <span data-ttu-id="63a33-199">Czech</span><span class="sxs-lookup"><span data-stu-id="63a33-199">Czech</span></span>
- <span data-ttu-id="63a33-200">Danish</span><span class="sxs-lookup"><span data-stu-id="63a33-200">Danish</span></span>
- <span data-ttu-id="63a33-201">Dutch</span><span class="sxs-lookup"><span data-stu-id="63a33-201">Dutch</span></span>
- <span data-ttu-id="63a33-202">English</span><span class="sxs-lookup"><span data-stu-id="63a33-202">English</span></span>
- <span data-ttu-id="63a33-203">Estonian</span><span class="sxs-lookup"><span data-stu-id="63a33-203">Estonian</span></span>
- <span data-ttu-id="63a33-204">Filipijns (Filipijnen)</span><span class="sxs-lookup"><span data-stu-id="63a33-204">Filipino (Philippines)</span></span>
- <span data-ttu-id="63a33-205">Finnish</span><span class="sxs-lookup"><span data-stu-id="63a33-205">Finnish</span></span>
- <span data-ttu-id="63a33-206">French</span><span class="sxs-lookup"><span data-stu-id="63a33-206">French</span></span>
- <span data-ttu-id="63a33-207">Galician</span><span class="sxs-lookup"><span data-stu-id="63a33-207">Galician</span></span>
- <span data-ttu-id="63a33-208">German</span><span class="sxs-lookup"><span data-stu-id="63a33-208">German</span></span>
- <span data-ttu-id="63a33-209">Greek</span><span class="sxs-lookup"><span data-stu-id="63a33-209">Greek</span></span>
- <span data-ttu-id="63a33-210">Gujarati</span><span class="sxs-lookup"><span data-stu-id="63a33-210">Gujarati</span></span>
- <span data-ttu-id="63a33-211">Hebrew</span><span class="sxs-lookup"><span data-stu-id="63a33-211">Hebrew</span></span>
- <span data-ttu-id="63a33-212">Hindi</span><span class="sxs-lookup"><span data-stu-id="63a33-212">Hindi</span></span>
- <span data-ttu-id="63a33-213">Hungarian</span><span class="sxs-lookup"><span data-stu-id="63a33-213">Hungarian</span></span>
- <span data-ttu-id="63a33-214">IJslands</span><span class="sxs-lookup"><span data-stu-id="63a33-214">Icelandic</span></span>
- <span data-ttu-id="63a33-215">Indonesian</span><span class="sxs-lookup"><span data-stu-id="63a33-215">Indonesian</span></span>
- <span data-ttu-id="63a33-216">Italian</span><span class="sxs-lookup"><span data-stu-id="63a33-216">Italian</span></span>
- <span data-ttu-id="63a33-217">Japanese</span><span class="sxs-lookup"><span data-stu-id="63a33-217">Japanese</span></span>
- <span data-ttu-id="63a33-218">Kannada</span><span class="sxs-lookup"><span data-stu-id="63a33-218">Kannada</span></span>
- <span data-ttu-id="63a33-219">Kazakh</span><span class="sxs-lookup"><span data-stu-id="63a33-219">Kazakh</span></span>
- <span data-ttu-id="63a33-220">Swahili</span><span class="sxs-lookup"><span data-stu-id="63a33-220">Kiswahili</span></span>
- <span data-ttu-id="63a33-221">Korean</span><span class="sxs-lookup"><span data-stu-id="63a33-221">Korean</span></span>
- <span data-ttu-id="63a33-222">Latvian</span><span class="sxs-lookup"><span data-stu-id="63a33-222">Latvian</span></span>
- <span data-ttu-id="63a33-223">Lithuanian</span><span class="sxs-lookup"><span data-stu-id="63a33-223">Lithuanian</span></span>
- <span data-ttu-id="63a33-224">Maleis (Brunei Darussalam)</span><span class="sxs-lookup"><span data-stu-id="63a33-224">Malay (Brunei Darussalam)</span></span>
- <span data-ttu-id="63a33-225">Maleis (Maleisië)</span><span class="sxs-lookup"><span data-stu-id="63a33-225">Malay (Malaysia)</span></span>
- <span data-ttu-id="63a33-226">Malajalam</span><span class="sxs-lookup"><span data-stu-id="63a33-226">Malayalam</span></span>
- <span data-ttu-id="63a33-227">Marathi</span><span class="sxs-lookup"><span data-stu-id="63a33-227">Marathi</span></span>
- <span data-ttu-id="63a33-228">Noors (Bokmål)</span><span class="sxs-lookup"><span data-stu-id="63a33-228">Norwegian (Bokmål)</span></span>
- <span data-ttu-id="63a33-229">Noors (Nynorsk)</span><span class="sxs-lookup"><span data-stu-id="63a33-229">Norwegian (Nynorsk)</span></span>
- <span data-ttu-id="63a33-230">Oriya</span><span class="sxs-lookup"><span data-stu-id="63a33-230">Oriya</span></span>
- <span data-ttu-id="63a33-231">Perzisch</span><span class="sxs-lookup"><span data-stu-id="63a33-231">Persian</span></span>
- <span data-ttu-id="63a33-232">Polish</span><span class="sxs-lookup"><span data-stu-id="63a33-232">Polish</span></span>
- <span data-ttu-id="63a33-233">Portugees (Brazilië)</span><span class="sxs-lookup"><span data-stu-id="63a33-233">Portuguese (Brazil)</span></span>
- <span data-ttu-id="63a33-234">Portugees (Portugal)</span><span class="sxs-lookup"><span data-stu-id="63a33-234">Portuguese (Portugal)</span></span>
- <span data-ttu-id="63a33-235">Romanian</span><span class="sxs-lookup"><span data-stu-id="63a33-235">Romanian</span></span>
- <span data-ttu-id="63a33-236">Russian</span><span class="sxs-lookup"><span data-stu-id="63a33-236">Russian</span></span>
- <span data-ttu-id="63a33-237">Servisch (Cyrillisch, Servië)</span><span class="sxs-lookup"><span data-stu-id="63a33-237">Serbian (Cyrillic, Serbia)</span></span>
- <span data-ttu-id="63a33-238">Servisch (Latijns)</span><span class="sxs-lookup"><span data-stu-id="63a33-238">Serbian (Latin)</span></span>
- <span data-ttu-id="63a33-239">Slovak</span><span class="sxs-lookup"><span data-stu-id="63a33-239">Slovak</span></span>
- <span data-ttu-id="63a33-240">Slovenian</span><span class="sxs-lookup"><span data-stu-id="63a33-240">Slovenian</span></span>
- <span data-ttu-id="63a33-241">Spanish</span><span class="sxs-lookup"><span data-stu-id="63a33-241">Spanish</span></span>
- <span data-ttu-id="63a33-242">Swedish</span><span class="sxs-lookup"><span data-stu-id="63a33-242">Swedish</span></span>
- <span data-ttu-id="63a33-243">Tamil</span><span class="sxs-lookup"><span data-stu-id="63a33-243">Tamil</span></span>
- <span data-ttu-id="63a33-244">Telugu</span><span class="sxs-lookup"><span data-stu-id="63a33-244">Telugu</span></span>
- <span data-ttu-id="63a33-245">Thai</span><span class="sxs-lookup"><span data-stu-id="63a33-245">Thai</span></span>
- <span data-ttu-id="63a33-246">Turkish</span><span class="sxs-lookup"><span data-stu-id="63a33-246">Turkish</span></span>
- <span data-ttu-id="63a33-247">Ukrainian</span><span class="sxs-lookup"><span data-stu-id="63a33-247">Ukrainian</span></span>
- <span data-ttu-id="63a33-248">Urdu</span><span class="sxs-lookup"><span data-stu-id="63a33-248">Urdu</span></span>
- <span data-ttu-id="63a33-249">Vietnamese</span><span class="sxs-lookup"><span data-stu-id="63a33-249">Vietnamese</span></span>
- <span data-ttu-id="63a33-250">Welsh</span><span class="sxs-lookup"><span data-stu-id="63a33-250">Welsh</span></span>
