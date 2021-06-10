---
title: Gedeelde query's gebruiken in Microsoft 365 defender advanced hunting
description: Begin onmiddellijk met het zoeken naar bedreigingen met vooraf gedefinieerde en gedeelde query's. Deel uw query's met het publiek of met uw organisatie.
keywords: advanced hunting, threat hunting, cyber threat hunting, Microsoft 365 Defender, microsoft 365, m365, search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
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
ms.openlocfilehash: 83c78f9df5560c75e40a171d770e994b86049204
ms.sourcegitcommit: 7cc2be0244fcc30049351e35c25369cacaaf4ca9
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2021
ms.locfileid: "51952582"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="15955-105">Gedeelde query's gebruiken in geavanceerde zoekopdrachten</span><span class="sxs-lookup"><span data-stu-id="15955-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="15955-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="15955-106">**Applies to:**</span></span>
- <span data-ttu-id="15955-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="15955-107">Microsoft 365 Defender</span></span>
- <span data-ttu-id="15955-108">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="15955-108">Microsoft Defender for Endpoint</span></span>



<span data-ttu-id="15955-109">[Geavanceerde](advanced-hunting-overview.md) zoekquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie.</span><span class="sxs-lookup"><span data-stu-id="15955-109">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="15955-110">U kunt ook query's vinden die openbaar zijn gedeeld op GitHub.</span><span class="sxs-lookup"><span data-stu-id="15955-110">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="15955-111">Met deze query's kunt u snel specifieke scenario's voor het zoeken naar bedreigingen uitvoeren zonder dat u zelf query's moet schrijven.</span><span class="sxs-lookup"><span data-stu-id="15955-111">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="15955-113">Een query opslaan, wijzigen en delen</span><span class="sxs-lookup"><span data-stu-id="15955-113">Save, modify, and share a query</span></span>
<span data-ttu-id="15955-114">U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="15955-114">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="15955-115">Een query maken of wijzigen.</span><span class="sxs-lookup"><span data-stu-id="15955-115">Create or modify a query.</span></span> 

2. <span data-ttu-id="15955-116">Klik op **de vervolgkeuzeknop** Query opslaan en selecteer **Opslaan als**.</span><span class="sxs-lookup"><span data-stu-id="15955-116">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="15955-117">Voer een naam in voor de query.</span><span class="sxs-lookup"><span data-stu-id="15955-117">Enter a name for the query.</span></span> 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="15955-119">Selecteer de map waarin u de query wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="15955-119">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="15955-120">**Gedeelde query's:** gedeeld met alle gebruikers van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="15955-120">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="15955-121">**Mijn query's,** die alleen voor u toegankelijk zijn</span><span class="sxs-lookup"><span data-stu-id="15955-121">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="15955-122">Klik op **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="15955-122">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="15955-123">Een query verwijderen of de naam wijzigen</span><span class="sxs-lookup"><span data-stu-id="15955-123">Delete or rename a query</span></span>
1. <span data-ttu-id="15955-124">Klik met de rechtermuisknop op een query die u wilt wijzigen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="15955-124">Right-click on a query you want to rename or delete.</span></span>

    ![Afbeelding van de verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="15955-126">Selecteer **Verwijderen** en bevestig verwijdering.</span><span class="sxs-lookup"><span data-stu-id="15955-126">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="15955-127">Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.</span><span class="sxs-lookup"><span data-stu-id="15955-127">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="15955-128">Een directe koppeling naar een query maken</span><span class="sxs-lookup"><span data-stu-id="15955-128">Create a direct link to a query</span></span>
<span data-ttu-id="15955-129">Als u een koppeling wilt genereren die uw query rechtstreeks opent in de geavanceerde queryeditor, rondt u de query af en selecteert u **Koppeling delen.**</span><span class="sxs-lookup"><span data-stu-id="15955-129">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="15955-130">Access-query's in de GitHub archief</span><span class="sxs-lookup"><span data-stu-id="15955-130">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="15955-131">Microsoft-beveiligingsonderzoekers delen regelmatig geavanceerde zoekquery's in een aangewezen [openbare opslagplaats op GitHub.](https://aka.ms/hunting-queries)</span><span class="sxs-lookup"><span data-stu-id="15955-131">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="15955-132">Deze opslagplaats staat open voor bijdragen.</span><span class="sxs-lookup"><span data-stu-id="15955-132">This repository is open to contributions.</span></span> <span data-ttu-id="15955-133">Als u wilt bijdragen, [kunt GitHub gratis deelnemen.](https://github.com/)</span><span class="sxs-lookup"><span data-stu-id="15955-133">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="15955-134">Beveiligingsonderzoekers van Microsoft bieden ook geavanceerde zoekquery's die u kunt gebruiken om activiteiten en indicatoren te vinden die zijn gekoppeld aan nieuwe bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="15955-134">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="15955-135">Deze query's worden geleverd als onderdeel van de [bedreigingsanalyserapporten](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) in Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="15955-135">These queries are provided as part of the [threat analytics](/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

>[!NOTE]
><span data-ttu-id="15955-136">Sommige tabellen in dit artikel zijn mogelijk niet beschikbaar in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="15955-136">Some tables in this article might not be available in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="15955-137">[Schakel de Microsoft 365 Defender in om](m365d-enable.md) te zoeken naar bedreigingen met behulp van meer gegevensbronnen.</span><span class="sxs-lookup"><span data-stu-id="15955-137">[Turn on Microsoft 365 Defender](m365d-enable.md) to hunt for threats using more data sources.</span></span> <span data-ttu-id="15955-138">U kunt uw geavanceerde zoekwerkstromen verplaatsen van Microsoft Defender voor Eindpunt naar Microsoft 365 Defender door de stappen in Geavanceerde zoekquery's migreren uit [Microsoft Defender voor Eindpunt te volgen.](advanced-hunting-migrate-from-mde.md)</span><span class="sxs-lookup"><span data-stu-id="15955-138">You can move your advanced hunting workflows from Microsoft Defender for Endpoint to Microsoft 365 Defender by following the steps in [Migrate advanced hunting queries from Microsoft Defender for Endpoint](advanced-hunting-migrate-from-mde.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="15955-139">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="15955-139">Related topics</span></span>
- [<span data-ttu-id="15955-140">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="15955-140">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="15955-141">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="15955-141">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="15955-142">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="15955-142">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="15955-143">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="15955-143">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="15955-144">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="15955-144">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="15955-145">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="15955-145">Apply query best practices</span></span>](advanced-hunting-best-practices.md)