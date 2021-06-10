---
title: Niet-bewaardergegevensbronnen toevoegen aan een Advanced eDiscovery zaak
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
description: U kunt niet-bewaargegevensbronnen toevoegen aan een Advanced eDiscovery en de gegevensbron in de wacht zetten. Niet-bewaardergegevensbronnen worden opnieuw geïndexeerd, zodat inhoud die is gemarkeerd als gedeeltelijk geïndexeerd, opnieuw wordt verwerkt, zodat deze volledig en snel kan worden doorzocht.
ms.openlocfilehash: 467f0e1167bfebe21bd3f2bbd52acd81529b8685
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/31/2020
ms.locfileid: "52161647"
---
# <a name="add-non-custodial-data-sources-to-an-advanced-ediscovery-case"></a><span data-ttu-id="00537-104">Niet-bewaardergegevensbronnen toevoegen aan een Advanced eDiscovery zaak</span><span class="sxs-lookup"><span data-stu-id="00537-104">Add non-custodial data sources to an Advanced eDiscovery case</span></span>

<span data-ttu-id="00537-105">In Advanced eDiscovery gevallen voldoet het niet altijd aan uw behoeften om een Microsoft 365 gegevensbron te koppelen aan een bewaarder in de zaak.</span><span class="sxs-lookup"><span data-stu-id="00537-105">In Advanced eDiscovery cases, it doesn't always meet your needs to associate a Microsoft 365 data source with a custodian in the case.</span></span> <span data-ttu-id="00537-106">Maar mogelijk moet u die gegevens nog steeds koppelen aan een zaak, zodat u deze kunt doorzoeken, toevoegen aan een revisieset en deze kunt analyseren en controleren.</span><span class="sxs-lookup"><span data-stu-id="00537-106">But you may still need to associate that data with a case so that you can search it, add it to a review set, and analyze and review it.</span></span> <span data-ttu-id="00537-107">De functie in Advanced eDiscovery wordt  niet-bewaardergegevensbronnen genoemd en u kunt gegevens toevoegen aan een zaak zonder dat u deze aan een bewaarder moet koppelen.</span><span class="sxs-lookup"><span data-stu-id="00537-107">The feature in Advanced eDiscovery is called *non-custodial data sources* and lets you add data to a case without having to associate it to a custodian.</span></span> <span data-ttu-id="00537-108">De functie past ook dezelfde Advanced eDiscovery toe op niet-bewaardergegevens die beschikbaar zijn voor gegevens die zijn gekoppeld aan bewaarder.</span><span class="sxs-lookup"><span data-stu-id="00537-108">It also applies the same Advanced eDiscovery functionality to non-custodial data that's available for data associated with custodian.</span></span> <span data-ttu-id="00537-109">Twee van de handigste dingen die u kunt toepassen op niet-bewaardergegevens, is het in de wacht zetten en verwerken met [geavanceerde indexering.](indexing-custodian-data.md)</span><span class="sxs-lookup"><span data-stu-id="00537-109">Two of the most useful things that you can apply to non-custodial data is placing it on hold and processing it using [Advanced indexing](indexing-custodian-data.md).</span></span>

## <a name="add-a-non-custodial-data-source"></a><span data-ttu-id="00537-110">Een niet-bewaardergegevensbron toevoegen</span><span class="sxs-lookup"><span data-stu-id="00537-110">Add a non-custodial data source</span></span>

<span data-ttu-id="00537-111">Volg deze stappen om niet-bewaardergegevensbronnen toe te voegen en te beheren in een Advanced eDiscovery geval.</span><span class="sxs-lookup"><span data-stu-id="00537-111">Follow these steps to add and manage non-custodial data sources in an Advanced eDiscovery case.</span></span>

1. <span data-ttu-id="00537-112">Klik op **Advanced eDiscovery** startpagina op de zaak aan wie u de gegevens wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="00537-112">On the **Advanced eDiscovery** home page, click the case that you want to add the data to.</span></span>

2. <span data-ttu-id="00537-113">Klik op **het tabblad Gegevensbronnen** en klik vervolgens op **Gegevensbron toevoegen**  >  **Gegevenslocaties toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="00537-113">Click the **Data sources** tab and then click **Add data source** > **Add data locations**.</span></span>

3. <span data-ttu-id="00537-114">Kies op **de flyoutpagina Nieuwe niet-bewaargegevenslocaties** de gegevensbronnen die u aan de zaak wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="00537-114">On the **New non-custodial data locations** flyout page, choose the data sources that you want to add to the case.</span></span> <span data-ttu-id="00537-115">U kunt meerdere postvakken en sites toevoegen door de secties SharePoint **of** **Exchange** uit te breiden en vervolgens op Bewerken **te klikken.**</span><span class="sxs-lookup"><span data-stu-id="00537-115">You can add multiple mailboxes and sites by expanding the **SharePoint** or **Exchange** sections and then clicking **Edit**.</span></span>

   ![Voeg SharePoint sites en postvakken Exchange als niet-bewaarder gegevensbronnen toe](../media/NonCustodialDataSources1.png)

   - <span data-ttu-id="00537-117">**SharePoint** - Klik op **Bewerken om** sites toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="00537-117">**SharePoint** - Click **Edit** to add sites.</span></span> <span data-ttu-id="00537-118">Selecteer een site in de lijst of u kunt zoeken naar een site door de URL van de site in de zoekbalk te typen.</span><span class="sxs-lookup"><span data-stu-id="00537-118">Select a site in the list or you can search for a site by typing the URL of the site in the search bar.</span></span> <span data-ttu-id="00537-119">Selecteer de sites die u wilt toevoegen als niet-bewaarder-gegevensbronnen en klik op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="00537-119">Select the sites that you want to add as non-custodian data sources and click **Add**.</span></span>

   - <span data-ttu-id="00537-120">**Exchange-** Klik op **Bewerken om** postvakken toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="00537-120">**Exchange** - Click **Edit** to add mailboxes.</span></span> <span data-ttu-id="00537-121">Typ een naam of alias (minimaal drie tekens) in het zoekvak voor postvakken of distributiegroepen.</span><span class="sxs-lookup"><span data-stu-id="00537-121">Type a name or alias (a minimum of three characters) in the search box for mailboxes or distribution groups.</span></span> <span data-ttu-id="00537-122">Selecteer de postvakken die u wilt toevoegen als niet-bewaardergegevensbronnen en klik op **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="00537-122">Select the mailboxes that you want to add as non-custodian data sources and click **Add**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="00537-123">U kunt de **secties SharePoint** en **Exchange** gebruiken om sites en postvakken toe te voegen die zijn gekoppeld aan een team of Yammer groep als niet-bewaardergegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="00537-123">You can use the **SharePoint** and **Exchange** sections to add sites and mailboxes associated with a Team or Yammer group as non-custodial data sources.</span></span> <span data-ttu-id="00537-124">U moet afzonderlijk het postvak en de site toevoegen die zijn gekoppeld aan een team of Yammer groep.</span><span class="sxs-lookup"><span data-stu-id="00537-124">You have to separately add the mailbox and site associated with a Team or Yammer group.</span></span>

4. <span data-ttu-id="00537-125">Nadat u niet-bewaardergegevensbronnen hebt toegevoegd, kunt u deze locaties al dan niet in de wacht zetten.</span><span class="sxs-lookup"><span data-stu-id="00537-125">After you add non-custodial data sources, you have the option to place those locations on hold or not.</span></span> <span data-ttu-id="00537-126">Schakel het selectievakje **In-** of uitschakelen naast de gegevensbron in of uit om het in de wacht te zetten.</span><span class="sxs-lookup"><span data-stu-id="00537-126">Select or unselect the **Hold** checkbox next to the data source to place it on hold.</span></span>

5. <span data-ttu-id="00537-127">Klik **onder** aan de flyout pagina **Nieuwe niet-bewaargegevenslocaties** op Toevoegen om de gegevensbronnen aan de zaak toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="00537-127">Click **Add** at the bottom of the **New non-custodial data locations** flyout page to add the data sources to the case.</span></span>

   <span data-ttu-id="00537-128">Elke niet-bewaardergegevensbron die u hebt toegevoegd, wordt weergegeven op de **pagina Gegevensbronnen.**</span><span class="sxs-lookup"><span data-stu-id="00537-128">Each non-custodial data source that you added is listed on the **Data sources** page.</span></span> <span data-ttu-id="00537-129">Niet-bewaardergegevensbronnen worden geïdentificeerd door **de** gegevenslocatiewaarde in de kolom **Brontype.**</span><span class="sxs-lookup"><span data-stu-id="00537-129">Non-custodial data sources are identified by the **Data location** value in the **Source type** column.</span></span>

   ![Niet-bewaardergegevensbronnen op het tabblad Gegevensbronnen](../media/NonCustodialDataSources2.png)

<span data-ttu-id="00537-131">Nadat u niet-bewaardergegevensbronnen aan de zaak hebt toevoegen, wordt een taak met de  naam Niet-bewaardergegevens opnieuw *indexeren* gemaakt en weergegeven op het tabblad Taken van de zaak.</span><span class="sxs-lookup"><span data-stu-id="00537-131">After you add non-custodial data sources to the case, a job named *Reindexing non-custodial data* is created and displayed on the **Jobs** tab of the case.</span></span> <span data-ttu-id="00537-132">Nadat de taak is gemaakt, wordt het proces voor geavanceerde indexering gestart en worden de gegevensbronnen opnieuw geïndexeerd.</span><span class="sxs-lookup"><span data-stu-id="00537-132">After the job is created, the Advanced indexing process in initiated and the data sources are reindexed.</span></span>

## <a name="manage-the-hold-for-non-custodial-data-sources"></a><span data-ttu-id="00537-133">De bewaarneming voor niet-bewaardergegevensbronnen beheren</span><span class="sxs-lookup"><span data-stu-id="00537-133">Manage the hold for non-custodial data sources</span></span>

<span data-ttu-id="00537-134">Nadat u een niet-bewaardergegevensbron in de wacht hebt gezet, wordt automatisch een bewaarbeleid gemaakt dat de niet-bewaardergegevensbronnen voor de zaak bevat.</span><span class="sxs-lookup"><span data-stu-id="00537-134">After you place a hold on a non-custodial data source, a hold policy that contains the non-custodial data sources for the case is automatically created.</span></span> <span data-ttu-id="00537-135">Wanneer u andere niet-bewaargegevensbronnen in de wacht zet, worden deze toegevoegd aan dit bewaarbeleid.</span><span class="sxs-lookup"><span data-stu-id="00537-135">When you place other non-custodial data sources on hold, they are added to this hold policy.</span></span>

1. <span data-ttu-id="00537-136">Open de Advanced eDiscovery en selecteer het **tabblad** Wacht houden.</span><span class="sxs-lookup"><span data-stu-id="00537-136">Open the Advanced eDiscovery case and select the **Hold** tab.</span></span>

2. <span data-ttu-id="00537-137">Klik **op NCDSHold- \<GUID\>**, waarbij de GUID-waarde uniek is voor de zaak.</span><span class="sxs-lookup"><span data-stu-id="00537-137">Click **NCDSHold-\<GUID\>**, where the GUID value is unique to the case.</span></span>

   <span data-ttu-id="00537-138">Op de flyoutpagina worden informatie en statistieken weergegeven over de niet-bewaardergegevensbronnen die in de wacht staan.</span><span class="sxs-lookup"><span data-stu-id="00537-138">The flyout page display information and statistics about the non-custodial data sources on hold.</span></span>

   ![Op de flyoutpagina voor gegevensbronnen die niet worden bewaard, worden statistieken weergegeven](../media/NonCustodialDataSourcesHoldFlyout.png)

3. <span data-ttu-id="00537-140">Klik **op Wacht houden bewerken** om de niet-bewaardergegevensbronnen weer te geven die in de wacht zijn geplaatst en de volgende beheertaken uit te voeren:</span><span class="sxs-lookup"><span data-stu-id="00537-140">Click **Edit hold** to view the non-custodial data sources placed on hold and perform the following management tasks:</span></span>

   - <span data-ttu-id="00537-141">Op de **pagina** Locaties kunt u een niet-bewarende gegevensbron vrijgeven door deze uit de wacht te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="00537-141">On the **Locations** page, you can release a non-custodial data source by removing it from the hold.</span></span> <span data-ttu-id="00537-142">Als u een gegevensbron los laat, wordt de niet-bewaardergegevensbron niet uit de zaak verwijderd.</span><span class="sxs-lookup"><span data-stu-id="00537-142">Releasing a data source doesn't remove the non-custodial data source from the case.</span></span> <span data-ttu-id="00537-143">Hiermee wordt alleen de wacht die in de gegevensbron is geplaatst, verwijderd.</span><span class="sxs-lookup"><span data-stu-id="00537-143">It only removes the hold that was placed on the data source.</span></span>

   - <span data-ttu-id="00537-144">Op de **pagina Query** kunt u de bewaarfunctie bewerken om een op query gebaseerde bewaarfunctie te maken die wordt toegepast op alle tha niet-bewaardergegevensbronnen in de zaak.</span><span class="sxs-lookup"><span data-stu-id="00537-144">On the **Query** page, you can edit the hold to create a query-based hold that is applied to all tha non-custodial data sources in the case.</span></span>
