---
title: Gedeelde query's gebruiken in geavanceerde jacht op Microsoft Threat Protection
description: Start onmiddellijk dreigingsjacht met vooraf gedefinieerde en gedeelde query's. Deel uw vragen met het publiek of uw organisatie.
keywords: geavanceerde jacht, dreigingjacht, cyberdreigingsjacht, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetrie, aangepaste detecties, schema, kusto, github repo, mijn zoekopdrachten, gedeelde query's
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 7ff46226e2535ed9826a61afa857e38b03c06ce1
ms.sourcegitcommit: 74bf600424d0cb7b9d16b4f391aeda7875058be1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42807337"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="cf214-105">Gedeelde query's gebruiken in geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="cf214-105">Use shared queries in advanced hunting</span></span>

<span data-ttu-id="cf214-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="cf214-106">**Applies to:**</span></span>
- <span data-ttu-id="cf214-107">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="cf214-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="cf214-108">[Geavanceerde](advanced-hunting-overview.md) jachtquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie.</span><span class="sxs-lookup"><span data-stu-id="cf214-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="cf214-109">U ook query's vinden die openbaar worden gedeeld op GitHub.</span><span class="sxs-lookup"><span data-stu-id="cf214-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="cf214-110">Met deze query's u snel specifieke scenario's voor bedreigingsjacht nastreven zonder dat u query's vanaf nul hoeft te schrijven.</span><span class="sxs-lookup"><span data-stu-id="cf214-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="cf214-112">Een query opslaan, wijzigen en delen</span><span class="sxs-lookup"><span data-stu-id="cf214-112">Save, modify, and share a query</span></span>
<span data-ttu-id="cf214-113">U een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk voor u is of wordt gedeeld met andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="cf214-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="cf214-114">Een query maken of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="cf214-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="cf214-115">Klik **op** de vervolgkeuzelijst Query opslaan en selecteer **Opslaan als**.</span><span class="sxs-lookup"><span data-stu-id="cf214-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="cf214-116">Voer een naam in voor de query.</span><span class="sxs-lookup"><span data-stu-id="cf214-116">Enter a name for the query.</span></span> 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="cf214-118">Selecteer de map waar u de query wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="cf214-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="cf214-119">**Gedeelde query's** — gedeeld met alle gebruikers van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="cf214-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="cf214-120">**Mijn vragen** — alleen voor u toegankelijk</span><span class="sxs-lookup"><span data-stu-id="cf214-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="cf214-121">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="cf214-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="cf214-122">Een query verwijderen of de naam wijzigen</span><span class="sxs-lookup"><span data-stu-id="cf214-122">Delete or rename a query</span></span>
1. <span data-ttu-id="cf214-123">Klik met de rechtermuisknop op een query die u wilt hernoemen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="cf214-123">Right-click on a query you want to rename or delete.</span></span>

    ![Afbeelding van verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="cf214-125">Selecteer **Verwijderen** en verwijdering bevestigen.</span><span class="sxs-lookup"><span data-stu-id="cf214-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="cf214-126">Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.</span><span class="sxs-lookup"><span data-stu-id="cf214-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="cf214-127">Toegang tot query's in de GitHub-repository</span><span class="sxs-lookup"><span data-stu-id="cf214-127">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="cf214-128">Microsoft security onderzoekers delen regelmatig geavanceerde jacht query's in een [aangewezen openbare repository op GitHub](https://github.com/microsoft/MTP-AHQ).</span><span class="sxs-lookup"><span data-stu-id="cf214-128">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/microsoft/MTP-AHQ).</span></span> <span data-ttu-id="cf214-129">Deze repository staat open voor bijdragen.</span><span class="sxs-lookup"><span data-stu-id="cf214-129">This repository is open to contributions.</span></span> <span data-ttu-id="cf214-130">Om bij te dragen, [word je gratis lid van GitHub.](https://github.com/)</span><span class="sxs-lookup"><span data-stu-id="cf214-130">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="cf214-131">Microsoft security onderzoekers bieden ook geavanceerde jacht query's die u gebruiken om activiteiten en indicatoren in verband met opkomende bedreigingen te lokaliseren.</span><span class="sxs-lookup"><span data-stu-id="cf214-131">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="cf214-132">Deze query's worden geleverd als onderdeel van de [rapporten over bedreigingsanalyse](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) in Microsoft Defender Security Center.</span><span class="sxs-lookup"><span data-stu-id="cf214-132">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="cf214-133">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="cf214-133">Related topics</span></span>
- [<span data-ttu-id="cf214-134">Proactief op zoek naar bedreigingen</span><span class="sxs-lookup"><span data-stu-id="cf214-134">Proactively hunt for threats</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cf214-135">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="cf214-135">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cf214-136">Zoek naar bedreigingen op verschillende apparaten en e-mails</span><span class="sxs-lookup"><span data-stu-id="cf214-136">Hunt for threats across devices and emails</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="cf214-137">Het schema begrijpen</span><span class="sxs-lookup"><span data-stu-id="cf214-137">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cf214-138">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="cf214-138">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
