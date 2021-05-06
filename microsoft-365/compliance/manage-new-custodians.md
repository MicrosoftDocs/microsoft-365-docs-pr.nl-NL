---
title: Beheerders beheren in een Advanced eDiscovery zaak
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Meer informatie over het weergeven, bewerken en bulksgewijs bewerken van de lijst met bewaarders in een Advanced eDiscovery geval.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a1e9e9d481073c8bb2827d5d65537dbf2b63ef1f
ms.sourcegitcommit: 555b200b618085706dabf8648d27fb6d6427cfce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/30/2020
ms.locfileid: "52161644"
---
# <a name="manage-custodians-in-an-advanced-ediscovery-case"></a><span data-ttu-id="15d5d-103">Beheerders beheren in een Advanced eDiscovery zaak</span><span class="sxs-lookup"><span data-stu-id="15d5d-103">Manage custodians in an Advanced eDiscovery case</span></span>

<span data-ttu-id="15d5d-104">De pagina Bewaarders op het **tabblad Bronnen** in Advanced eDiscovery zaak bevat een lijst met alle bewaarders die aan de zaak zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-104">The Custodians page on the **Sources** tab in an Advanced eDiscovery case contains a list of all custodians that have been added to the case.</span></span> <span data-ttu-id="15d5d-105">Nadat u bewaarders aan een zaak hebt toevoegen, worden gegevens over elke bewaarder automatisch verzameld uit Azure Active Directory en kunnen ze worden bekeken in Advanced eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="15d5d-105">After you add custodians to a case, details about each custodian are automatically collected from Azure Active Directory and are viewable in Advanced eDiscovery.</span></span>

![Beheerders beheren](../media/CustodianDetails.PNG)

## <a name="view-custodian-details"></a><span data-ttu-id="15d5d-107">Bewaardetails weergeven</span><span class="sxs-lookup"><span data-stu-id="15d5d-107">View custodian details</span></span>

<span data-ttu-id="15d5d-108">Als u de details van een voogd wilt bekijken, klikt u op de bewaarder in de lijst op **het tabblad Bewaarders.** Er wordt een flyoutpagina weergegeven met de volgende informatie over de bewaarder:</span><span class="sxs-lookup"><span data-stu-id="15d5d-108">To view the details about a custodian, click the custodian from the list on the **Custodians** tab. A flyout page is displayed and contains the following information about the custodian:</span></span>

- <span data-ttu-id="15d5d-109">Contactgegevens</span><span class="sxs-lookup"><span data-stu-id="15d5d-109">Contact information</span></span>

  - <span data-ttu-id="15d5d-110">**Weergavenaam:** de naam die wordt weergegeven in het adresboek voor de bewaarder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-110">**Display Name** - The name displayed in the address book for the custodian.</span></span> <span data-ttu-id="15d5d-111">Dit is meestal de combinatie van de voornaam, het middelste begin en de achternaam van de bewaarder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-111">This is usually the combination of the custodian's first name, middle initial, and last name.</span></span>
  
   - <span data-ttu-id="15d5d-112">**Mail/SMTP:** het primaire SMTP-adres voor de beheerder, bijvoorbeeld brianj@contoso.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="15d5d-112">**Mail/SMTP** - The primary SMTP address for the custodian, for example, brianj@contoso.onmicrosoft.com.</span></span> <span data-ttu-id="15d5d-113">De naam van de hoofdgebruiker (UPN) van de bewaarder wordt ook vermeld.</span><span class="sxs-lookup"><span data-stu-id="15d5d-113">The custodian's user principal name (UPN) is also listed.</span></span>

  - <span data-ttu-id="15d5d-114">**Titel** - De functie van de bewaarder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-114">**Title** - The custodian's job title.</span></span>

  - <span data-ttu-id="15d5d-115">**Afdeling** - De naam van de afdeling waarin de voogd werkt.</span><span class="sxs-lookup"><span data-stu-id="15d5d-115">**Department** - The name for the department in which the custodian works.</span></span>

  - <span data-ttu-id="15d5d-116">**Manager** - De beheerder van de voogd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-116">**Manager** - The custodian's manager.</span></span> <span data-ttu-id="15d5d-117">De aangewezen manager ontvangt elke escalatiecommunicatie voor deze beheerder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-117">The designated manager will receive any escalation communications for this custodian.</span></span>
  
- <span data-ttu-id="15d5d-118">Locatiegegevens</span><span class="sxs-lookup"><span data-stu-id="15d5d-118">Location information</span></span>

  - <span data-ttu-id="15d5d-119">**Plaats** : de plaats waar de bewaarder zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="15d5d-119">**City** - The city in which the custodian is located.</span></span>

  - <span data-ttu-id="15d5d-120">**Staat** - De staat of provincie in het adres van de bewaarder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-120">**State** - The state or province in the custodian's address.</span></span>

  - <span data-ttu-id="15d5d-121">**Land/regio** : het land/de regio waar de bewaarder zich bevindt.</span><span class="sxs-lookup"><span data-stu-id="15d5d-121">**Country/Region** - The country/region where the custodian is located.</span></span>

  - <span data-ttu-id="15d5d-122">**Office** - De kantoorlocatie in de bedrijfsruimte van de beheerder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-122">**Office** - The office location in the custodian's place of business.</span></span>

- <span data-ttu-id="15d5d-123">Case-informatie</span><span class="sxs-lookup"><span data-stu-id="15d5d-123">Case information</span></span>

  - <span data-ttu-id="15d5d-124">**Status van wacht** houden: geeft aan of de bewaarder in de wacht is geplaatst.</span><span class="sxs-lookup"><span data-stu-id="15d5d-124">**Hold status** - Indicates if the custodian has been placed on hold.</span></span> 

  - <span data-ttu-id="15d5d-125">**Communicatiestatus:** geeft aan of de bewaarder een bewaartermijn heeft gekregen.</span><span class="sxs-lookup"><span data-stu-id="15d5d-125">**Communication status**: Indicates if the custodian has been issued a hold notice.</span></span> <span data-ttu-id="15d5d-126">Als de bewaarder een kennisgeving heeft afgegeven, wordt deze waarde van deze eigenschap **gepubliceerd.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-126">If the custodian has been issued a notice, this value of this property is **Published**.</span></span> <span data-ttu-id="15d5d-127">Als de bewaarder geen kennisgeving heeft gekregen, is de status **Niet-gepubliceerd.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-127">If the custodian has not been issued a notice, the status is **Un-published**.</span></span> 

  - <span data-ttu-id="15d5d-128">**Status** : de status van de bewaarder in de zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-128">**Status** - The status of the custodian within the case.</span></span> <span data-ttu-id="15d5d-129">Een status van **Actief** geeft aan dat de bewaarder deel uitmaakt van de zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-129">A status of **Active** indicates that the custodian is part of the case.</span></span> <span data-ttu-id="15d5d-130">Als een voogd uit een zaak wordt vrijgegeven, wordt de status gewijzigd in **Uitgebracht.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-130">If a custodian is released from a case, the status is changed to **Released**.</span></span> 

- <span data-ttu-id="15d5d-131">Gegevensbronnen en indexeringsgegevens</span><span class="sxs-lookup"><span data-stu-id="15d5d-131">Data sources and indexing information</span></span>

    - <span data-ttu-id="15d5d-132">**Gegevensbronnen:** toont het aantal en het type gegevensbronnen (postvakken, sites en Teams) dat is gekoppeld aan de bewaarder en die deel uitmaken van de zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-132">**Data sources** - Shows the count and type of data sources (mailboxes, sites, and Teams) that are associated with the custodian and are part of the case.</span></span>

    - <span data-ttu-id="15d5d-133">**Bijgewerkte tijd indexeren:** geeft de tijd en datum aan waarop de geavanceerde indexeringsbaan voor het laatst is geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-133">**Index updated time** - Indicates the time and date for when the advanced indexing job was last triggered.</span></span> <span data-ttu-id="15d5d-134">Deze eigenschap geeft ook aan wanneer het geavanceerde indexeringsproces momenteel wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-134">This property will also indicate when the advanced indexing process is currently in progress.</span></span>


## <a name="edit-a-custodian"></a><span data-ttu-id="15d5d-135">Een voogd bewerken</span><span class="sxs-lookup"><span data-stu-id="15d5d-135">Edit a custodian</span></span>

<span data-ttu-id="15d5d-136">Naarmate uw zaak vordert, kunt u ontdekken dat er mogelijk aanvullende gegevensbronnen zijn die relevant zijn voor een specifieke bewaarder & uw zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-136">As your case progresses, you may discover that there may be additional data sources relevant to a specific custodian & your case.</span></span> <span data-ttu-id="15d5d-137">In andere scenario's wilt u mogelijk bepaalde gegevensbronnen verwijderen die zijn beoordeeld en als niet relevant worden beschouwd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-137">In other scenarios, you may want to remove certain data sources that have been reviewed and deemed as not relevant.</span></span>

<span data-ttu-id="15d5d-138">De gegevensbronnen bijwerken die zijn gekoppeld aan een bewaarder:</span><span class="sxs-lookup"><span data-stu-id="15d5d-138">To update the data sources that are associated with a custodian:</span></span>

1. <span data-ttu-id="15d5d-139">Ga naar **eDiscovery > Advanced eDiscovery** en open de zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-139">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>
  
2. <span data-ttu-id="15d5d-140">Klik op **het tabblad** Bronnen.</span><span class="sxs-lookup"><span data-stu-id="15d5d-140">Click the **Sources** tab.</span></span>
  
3. <span data-ttu-id="15d5d-141">Selecteer op **de pagina Bewaarders** een bewaarder in de lijst en klik **op Bewerken** op de flyoutpagina.</span><span class="sxs-lookup"><span data-stu-id="15d5d-141">On the **Custodians** page, select a custodian from the list and click **Edit** on the flyout page.</span></span>

    ![Gegevensbronnen bewerken](../media/EditCustodianDataSource.PNG)
  
4. <span data-ttu-id="15d5d-143">Klik **op het tabblad Gegevensbronnen** kiezen om de instellingen voor het postvak en Exchange OneDrive van de beheerder te wijzigen en klik op **Gegevensbronnen kiezen.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-143">Click **Choose data sources** tab to change the settings for the custodian's Exchange mailbox and OneDrive account, click **Choose data sources**.</span></span>
  
5. <span data-ttu-id="15d5d-144">Klik op het tabblad Extra **gegevensbronnen** selecteren om postvakken Teams, SharePoint of Exchange aan de bewaarder toe te voegen of te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="15d5d-144">Click the **Select additional data sources** tab to add or remove Teams, SharePoint, or Exchange mailboxes associated with the custodian.</span></span> 

    <span data-ttu-id="15d5d-145">Zie Beheerders toevoegen aan een zaak voor meer informatie over gegevensbronnen die zijn gekoppeld aan [een](add-custodians-to-case.md)voogd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-145">For more information about data sources associated with a custodian, see [Add custodians to a case](add-custodians-to-case.md).</span></span> 
  
6. <span data-ttu-id="15d5d-146">Klik **op Bewaar bewaarplaats plaatsen om** de bewaarplaats voor de bewaarder in of uit te schakelen.</span><span class="sxs-lookup"><span data-stu-id="15d5d-146">Click **Place custodial holds** to enable or disable the hold for the custodian.</span></span>

## <a name="re-index-custodian-data"></a><span data-ttu-id="15d5d-147">Bewaargegevens opnieuw indexeren</span><span class="sxs-lookup"><span data-stu-id="15d5d-147">Re-index custodian data</span></span>

<span data-ttu-id="15d5d-148">In de meeste eDiscovery-werkstromen voor juridische onderzoeken wordt een subset van de gegevens van een bewaarder doorzocht nadat de bewaarder is toegevoegd aan een juridische zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-148">In most eDiscovery workflows for legal investigations, a subset of a custodian's data is searched after the custodian is added to a legal case.</span></span> <span data-ttu-id="15d5d-149">Vanwege zeer grote bestandsgrootten of mogelijke gegevensbeschaving, kunnen sommige items in de gegevensbronnen die zijn gekoppeld aan een bewaarder gedeeltelijk worden geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-149">Because of very large file sizes or possible data corruption, some items in the data sources associated with a custodian may be partially indexed.</span></span> <span data-ttu-id="15d5d-150">Met de [geavanceerde indexeringsfunctie](indexing-custodian-data.md) in de Advanced eDiscovery kunnen de meeste gedeeltelijk geïndexeerde items automatisch worden gesaneerd door deze items op aanvraag opnieuw te indexeren.</span><span class="sxs-lookup"><span data-stu-id="15d5d-150">Using the [advanced indexing](indexing-custodian-data.md) capability in the Advanced eDiscovery, most partially indexed items can be automatically remediated by re-indexing these items on demand.</span></span>

<span data-ttu-id="15d5d-151">Wanneer een bewaarder aan een zaak wordt toegevoegd, worden de gegevens in de gegevensbronnen die aan de bewaarder zijn gekoppeld, automatisch opnieuw geïndexeerd (door het geavanceerde indexeringsproces).</span><span class="sxs-lookup"><span data-stu-id="15d5d-151">When a custodian is added to a case, the data located in the data sources associated with the custodian is automatically re-indexed (by the advanced indexing process).</span></span> <span data-ttu-id="15d5d-152">Dit betekent dat u de gegevens op hun plaats kunt laten in plaats van de gegevens te moeten downloaden en herstellen en vervolgens offline kunt doorzoeken).</span><span class="sxs-lookup"><span data-stu-id="15d5d-152">This means you can leave the data in-place instead of having to download and remediate it and then search it offline).</span></span> <span data-ttu-id="15d5d-153">Tijdens de levenscyclus van een juridische zaak kunnen nieuwe gegevensbronnen echter worden gekoppeld aan een bewaarder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-153">However, during the lifecycle of a legal case new data sources might be associated with a custodian.</span></span> <span data-ttu-id="15d5d-154">In dit geval kunt u de gegevens van de bewaarder opnieuw indexeren door het geavanceerde indexeringsproces opnieuw uit te werken om gedeeltelijk geïndexeerde items te corrigeren en de index voor de gegevens van de bewaarder bij te werken.</span><span class="sxs-lookup"><span data-stu-id="15d5d-154">In this case, you can re-index the custodian's data by re-running the advanced indexing process to remediate any partially indexed items and update the index for the custodian's data.</span></span>

<span data-ttu-id="15d5d-155">Als u het proces voor het opnieuw indexeren wilt activeren om gedeeltelijk geïndexeerde items aan te pakken:</span><span class="sxs-lookup"><span data-stu-id="15d5d-155">To trigger the re-indexing process to address partially indexed items:</span></span>

1. <span data-ttu-id="15d5d-156">Ga naar **eDiscovery > Advanced eDiscovery** en open de zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-156">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="15d5d-157">Klik op **het tabblad** Bronnen.</span><span class="sxs-lookup"><span data-stu-id="15d5d-157">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="15d5d-158">Selecteer op **de pagina Bewaarders** een bewaarder waarvan de gegevens opnieuw moeten worden geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-158">On the **Custodians** page, select a custodian whose data must be reindexed.</span></span>

4. <span data-ttu-id="15d5d-159">Klik op de flyoutpagina op **Index bijwerken.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-159">On the flyout page, click **Update index**.</span></span>

   <span data-ttu-id="15d5d-160">Er wordt een dialoogvenster weergegeven waarin wordt gezegd dat de indexbaan is gemaakt.</span><span class="sxs-lookup"><span data-stu-id="15d5d-160">A dialog is displayed saying the index job has been created.</span></span>

<span data-ttu-id="15d5d-161">Het opnieuw indexeren van bewaargegevens is een langlopende procedure. de bijbehorende taak die is gemaakt, heet Gegevens van beheerders opnieuw **indexeren.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-161">Re-indexing custodian data is a long-running process; the corresponding job that's created is named **Re-indexing custodian data**.</span></span> <span data-ttu-id="15d5d-162">U kunt de voortgang bijhouden op **het** tabblad Taken of op het tabblad **Bewaarders** door de status in de kolom **Indexeringsstatus te** controleren.</span><span class="sxs-lookup"><span data-stu-id="15d5d-162">You can track the progress on the **Jobs** tab or on the **Custodians** tab by monitoring the status in the **Indexing job status** column.</span></span>

<span data-ttu-id="15d5d-163">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="15d5d-163">For more information, see:</span></span>

- [<span data-ttu-id="15d5d-164">Werken met verwerkingsfouten</span><span class="sxs-lookup"><span data-stu-id="15d5d-164">Work with processing errors</span></span>](processing-data-for-case.md)

- [<span data-ttu-id="15d5d-165">Taken beheren</span><span class="sxs-lookup"><span data-stu-id="15d5d-165">Manage jobs</span></span>](managing-jobs-ediscovery20.md)

## <a name="release-a-custodian-from-a-case"></a><span data-ttu-id="15d5d-166">Een bewaarder vrij laten van een zaak</span><span class="sxs-lookup"><span data-stu-id="15d5d-166">Release a custodian from a case</span></span>

<span data-ttu-id="15d5d-167">Een bewaarder wordt uitgebracht in situaties waarin een zaak is gesloten, de bewaarder niet langer verplicht is inhoud voor een zaak te bewaren of wanneer de bewaarder niet langer relevant wordt geacht voor de zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-167">A custodian is released in situations where a case is closed, the custodian is no longer under obligation to preserve content for a case, or when the custodian is deemed to no longer be relevant to the case.</span></span> 

<span data-ttu-id="15d5d-168">Als u een bewaarder vrij laat nadat een bewaartermijn is gepubliceerd, wordt een releasebericht verzonden naar de bewaarder.</span><span class="sxs-lookup"><span data-stu-id="15d5d-168">If you release a custodian after a hold notice was published, a release notice will be sent to the custodian.</span></span> <span data-ttu-id="15d5d-169">Bovendien worden alle bewaarnemingen die zijn geplaatst op gegevensbronnen die aan de bewaarder zijn gekoppeld, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-169">Additionally, any holds placed on data sources that were associated with the custodian are removed.</span></span> <span data-ttu-id="15d5d-170">Als de bewaarder is geplaatst in een stilte- of bewaartermijn, waarbij geen meldingen over wettelijke bewaartermijnen zijn afgegeven, wordt er geen releasemelding verzonden, maar worden alle bewaarnemingen die zijn geplaatst op gegevensbronnen die aan die bewaarder zijn gekoppeld, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="15d5d-170">If the custodian was placed on a *silent hold*, where they weren't issued any legal hold notifications, a release notice will not be sent but any holds placed on data sources that were associated with that custodian are removed.</span></span>

<span data-ttu-id="15d5d-171">Een bewaarder vrij laten:</span><span class="sxs-lookup"><span data-stu-id="15d5d-171">To release a custodian:</span></span> 

1. <span data-ttu-id="15d5d-172">Ga naar **eDiscovery > Advanced eDiscovery** en open de zaak.</span><span class="sxs-lookup"><span data-stu-id="15d5d-172">Go to  **eDiscovery > Advanced eDiscovery** and open the case.</span></span>

2. <span data-ttu-id="15d5d-173">Klik op **het tabblad** Bronnen.</span><span class="sxs-lookup"><span data-stu-id="15d5d-173">Click the **Sources** tab.</span></span>

3. <span data-ttu-id="15d5d-174">Selecteer op **de pagina Bewaarders** de bewaarder die uit de zaak wordt vrijgegeven.</span><span class="sxs-lookup"><span data-stu-id="15d5d-174">On the **Custodians** page, and then select the custodian who is being released from the case.</span></span>

4. <span data-ttu-id="15d5d-175">Klik op de flyoutpagina op **Release bewaarder.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-175">On the flyout page, click **Release custodian**.</span></span>

   <span data-ttu-id="15d5d-176">Er wordt een waarschuwingspagina weergegeven waarin wordt uitgelegd dat als een bewaarplaats wordt geplaatst op een gegevensbron die aan de bewaarder is gekoppeld, de bewaarplaats wordt verwijderd en dat alle andere bewaarplaats die is gekoppeld aan een ander Advanced eDiscovery-geval, nog steeds van toepassing is.</span><span class="sxs-lookup"><span data-stu-id="15d5d-176">A warning page is displayed explaining that if a hold is placed on a data source associated with the custodian, the hold will be removed, and that any other hold associated with a different Advanced eDiscovery case will still apply.</span></span> <span data-ttu-id="15d5d-177">Dit geldt ook voor andere typen bewarings- en bewaarfuncties (zoals een Microsoft 365 bewaarbeleid).</span><span class="sxs-lookup"><span data-stu-id="15d5d-177">That includes other types of preservation and retention features (such as a Microsoft 365 retention policy).</span></span>

5. <span data-ttu-id="15d5d-178">Klik **op Ja** om te bevestigen dat u de bewaarder wilt vrij laten.</span><span class="sxs-lookup"><span data-stu-id="15d5d-178">Click **Yes** to confirm that you want to release the custodian.</span></span> 

    <span data-ttu-id="15d5d-179">De status voor deze gebruiker op het tabblad **Bewaarders** is ingesteld op **Uitgebracht** en de **status Wacht** op de flyout-pagina wordt gewijzigd in **Onwaar.**</span><span class="sxs-lookup"><span data-stu-id="15d5d-179">The status for this user on the **Custodians** tab is set to **Released** and the **Hold status** on the flyout page is changed to **False**.</span></span> 

> [!NOTE]
> <span data-ttu-id="15d5d-180">Een bewaarder kan tegelijk betrokken zijn bij verschillende rechtszaken.</span><span class="sxs-lookup"><span data-stu-id="15d5d-180">A custodian might be simultaneously involved in several legal cases.</span></span> <span data-ttu-id="15d5d-181">Wanneer een voogd uit een zaak wordt vrijgegeven, worden de bewaar- en meldingen voor andere zaken niet beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="15d5d-181">When a custodian is released from a case, the holds and notifications across other matters won't be impacted.</span></span>

## <a name="bulk-edit-custodians"></a><span data-ttu-id="15d5d-182">Beheerders bulksgewijs bewerken</span><span class="sxs-lookup"><span data-stu-id="15d5d-182">Bulk-edit custodians</span></span>

<span data-ttu-id="15d5d-183">U kunt de bulkeditor gebruiken om meerdere bewaarders tegelijk te bewerken.</span><span class="sxs-lookup"><span data-stu-id="15d5d-183">You can use the bulk editor to edit multiple custodians as the same time.</span></span> <span data-ttu-id="15d5d-184">Hiervoor selecteert u twee of meer bewaarders op het tabblad **Bewaarders** om de bulkeditor weer te geven en klikt u vervolgens op een van de taken.</span><span class="sxs-lookup"><span data-stu-id="15d5d-184">To do this, just select two or more custodians on the **Custodians** tab to display the bulk editor and then click one of tasks.</span></span>

![Flyout-pagina om instellingen van meerdere beheerders te bewerken](../media/AeDBulkEditCustodians.png)
