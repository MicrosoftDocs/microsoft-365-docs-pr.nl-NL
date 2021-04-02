---
title: Gedeelde query's gebruiken in geavanceerde microsoft 365 Defender-zoekopdrachten
description: Begin onmiddellijk met het zoeken naar bedreigingen met vooraf gedefinieerde en gedeelde query's. Deel uw query's met het publiek of met uw organisatie.
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: fbc5b4c53487bceab5786a7ce75a56741a3c9cb2
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499720"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="d9c18-105">Gedeelde query's gebruiken in geavanceerde zoekopdrachten</span><span class="sxs-lookup"><span data-stu-id="d9c18-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d9c18-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d9c18-106">**Applies to:**</span></span>
- <span data-ttu-id="d9c18-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d9c18-107">Microsoft 365 Defender</span></span>



<span data-ttu-id="d9c18-108">[Geavanceerde](advanced-hunting-overview.md) zoekquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie.</span><span class="sxs-lookup"><span data-stu-id="d9c18-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="d9c18-109">U kunt ook query's vinden die openbaar zijn gedeeld op GitHub.</span><span class="sxs-lookup"><span data-stu-id="d9c18-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="d9c18-110">Met deze query's kunt u snel specifieke scenario's voor het zoeken naar bedreigingen uitvoeren zonder dat u zelf query's moet schrijven.</span><span class="sxs-lookup"><span data-stu-id="d9c18-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="d9c18-112">Een query opslaan, wijzigen en delen</span><span class="sxs-lookup"><span data-stu-id="d9c18-112">Save, modify, and share a query</span></span>
<span data-ttu-id="d9c18-113">U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d9c18-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="d9c18-114">Een query maken of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="d9c18-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="d9c18-115">Klik op **de vervolgkeuzeknop** Query opslaan en selecteer **Opslaan als**.</span><span class="sxs-lookup"><span data-stu-id="d9c18-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="d9c18-116">Voer een naam in voor de query.</span><span class="sxs-lookup"><span data-stu-id="d9c18-116">Enter a name for the query.</span></span> 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="d9c18-118">Selecteer de map waarin u de query wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="d9c18-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="d9c18-119">**Gedeelde query's:** gedeeld met alle gebruikers van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="d9c18-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="d9c18-120">**Mijn query's,** die alleen voor u toegankelijk zijn</span><span class="sxs-lookup"><span data-stu-id="d9c18-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="d9c18-121">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="d9c18-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="d9c18-122">Een query verwijderen of de naam wijzigen</span><span class="sxs-lookup"><span data-stu-id="d9c18-122">Delete or rename a query</span></span>
1. <span data-ttu-id="d9c18-123">Klik met de rechtermuisknop op een query die u wilt wijzigen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d9c18-123">Right-click on a query you want to rename or delete.</span></span>

    ![Afbeelding van de verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="d9c18-125">Selecteer **Verwijderen** en bevestig verwijdering.</span><span class="sxs-lookup"><span data-stu-id="d9c18-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="d9c18-126">Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.</span><span class="sxs-lookup"><span data-stu-id="d9c18-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="d9c18-127">Een directe koppeling naar een query maken</span><span class="sxs-lookup"><span data-stu-id="d9c18-127">Create a direct link to a query</span></span>
<span data-ttu-id="d9c18-128">Als u een koppeling wilt genereren die uw query rechtstreeks opent in de geavanceerde queryeditor, rondt u de query af en selecteert u **Koppeling delen.**</span><span class="sxs-lookup"><span data-stu-id="d9c18-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="d9c18-129">Access-query's in de GitHub-opslagplaats</span><span class="sxs-lookup"><span data-stu-id="d9c18-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="d9c18-130">Microsoft-beveiligingsonderzoekers delen regelmatig geavanceerde zoekquery's in een aangewezen [openbare opslagplaats op GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="d9c18-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="d9c18-131">Deze opslagplaats staat open voor bijdragen.</span><span class="sxs-lookup"><span data-stu-id="d9c18-131">This repository is open to contributions.</span></span> <span data-ttu-id="d9c18-132">Als u wilt bijdragen, [kunt u gratis deelnemen aan GitHub.](https://github.com/)</span><span class="sxs-lookup"><span data-stu-id="d9c18-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="d9c18-133">Beveiligingsonderzoekers van Microsoft bieden ook geavanceerde zoekquery's die u kunt gebruiken om activiteiten en indicatoren te vinden die zijn gekoppeld aan nieuwe bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="d9c18-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="d9c18-134">Deze query's worden geleverd als onderdeel van de [bedreigingsanalyserapporten](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="d9c18-134">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9c18-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d9c18-135">Related topics</span></span>
- [<span data-ttu-id="d9c18-136">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="d9c18-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d9c18-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="d9c18-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d9c18-138">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="d9c18-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="d9c18-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="d9c18-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d9c18-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="d9c18-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d9c18-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="d9c18-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)