---
title: Gedeelde query's gebruiken in geavanceerde zoekopdrachten
description: Begin onmiddellijk met het zoeken naar bedreigingen met vooraf gedefinieerde en gedeelde query's. Deel uw query's met het publiek of met uw organisatie.
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, github repo, my queries, shared queries
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9788594eaab29aba54c634e79c7aa00d6148aacd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059977"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="55fd3-105">Gedeelde query's gebruiken in geavanceerde zoekopdrachten</span><span class="sxs-lookup"><span data-stu-id="55fd3-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55fd3-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="55fd3-106">**Applies to:**</span></span>
- [<span data-ttu-id="55fd3-107">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="55fd3-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

><span data-ttu-id="55fd3-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="55fd3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="55fd3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="55fd3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhunting-abovefoldlink)

<span data-ttu-id="55fd3-110">[Geavanceerde](advanced-hunting-overview.md) zoekquery's kunnen worden gedeeld tussen gebruikers in dezelfde organisatie.</span><span class="sxs-lookup"><span data-stu-id="55fd3-110">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="55fd3-111">U kunt ook query's vinden die openbaar zijn gedeeld op GitHub.</span><span class="sxs-lookup"><span data-stu-id="55fd3-111">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="55fd3-112">Met deze query's kunt u snel specifieke scenario's voor het zoeken naar bedreigingen uitvoeren zonder dat u zelf query's moet schrijven.</span><span class="sxs-lookup"><span data-stu-id="55fd3-112">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Afbeelding van gedeelde query's](images/atp-advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="55fd3-114">Een query opslaan, wijzigen en delen</span><span class="sxs-lookup"><span data-stu-id="55fd3-114">Save, modify, and share a query</span></span>
<span data-ttu-id="55fd3-115">U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="55fd3-115">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span>

1. <span data-ttu-id="55fd3-116">Typ een nieuwe query of laad een bestaande query onder **Gedeelde query's** of **Mijn query's.**</span><span class="sxs-lookup"><span data-stu-id="55fd3-116">Type a new query or load an existing one from under **Shared queries** or **My queries**.</span></span>

2. <span data-ttu-id="55fd3-117">Selecteer **Opslaan** of **Opslaan als** in de opties voor opslaan.</span><span class="sxs-lookup"><span data-stu-id="55fd3-117">Select **Save** or **Save as** from the save options.</span></span> <span data-ttu-id="55fd3-118">Als u wilt voorkomen dat u een bestaande query overschrijft, kiest **u Opslaan als**.</span><span class="sxs-lookup"><span data-stu-id="55fd3-118">To avoid overwriting an existing query, choose **Save as**.</span></span>

3. <span data-ttu-id="55fd3-119">Voer een naam in voor de query.</span><span class="sxs-lookup"><span data-stu-id="55fd3-119">Enter a name for the query.</span></span>

   ![Afbeelding van het opslaan van een query](images/advanced-hunting-save-query.png)

4. <span data-ttu-id="55fd3-121">Selecteer de map waarin u de query wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="55fd3-121">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="55fd3-122">**Gedeelde query's:** gedeeld met alle gebruikers in uw organisatie</span><span class="sxs-lookup"><span data-stu-id="55fd3-122">**Shared queries** — shared to all users in your organization</span></span>
    - <span data-ttu-id="55fd3-123">**Mijn query's,** die alleen voor u toegankelijk zijn</span><span class="sxs-lookup"><span data-stu-id="55fd3-123">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="55fd3-124">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="55fd3-124">Select **Save**.</span></span>

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="55fd3-125">Een query verwijderen of de naam wijzigen</span><span class="sxs-lookup"><span data-stu-id="55fd3-125">Delete or rename a query</span></span>
1. <span data-ttu-id="55fd3-126">Klik met de rechtermuisknop op een query die u wilt wijzigen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="55fd3-126">Right-click on a query you want to rename or delete.</span></span>

    ![Afbeelding van de verwijderquery](images/atp_advanced_hunting_delete_rename.png)

2. <span data-ttu-id="55fd3-128">Selecteer **Verwijderen** en bevestig verwijdering.</span><span class="sxs-lookup"><span data-stu-id="55fd3-128">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="55fd3-129">Of selecteer **Naam wijzigen** en geef een nieuwe naam op voor de query.</span><span class="sxs-lookup"><span data-stu-id="55fd3-129">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="55fd3-130">Een directe koppeling naar een query maken</span><span class="sxs-lookup"><span data-stu-id="55fd3-130">Create a direct link to a query</span></span>
<span data-ttu-id="55fd3-131">Als u een koppeling wilt genereren die uw query rechtstreeks opent in de geavanceerde queryeditor, rondt u de query af en selecteert u **Koppeling delen.**</span><span class="sxs-lookup"><span data-stu-id="55fd3-131">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="55fd3-132">Access-query's in de GitHub-opslagplaats</span><span class="sxs-lookup"><span data-stu-id="55fd3-132">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="55fd3-133">Microsoft-beveiligingsonderzoekers delen regelmatig geavanceerde zoekquery's in een aangewezen [openbare opslagplaats op GitHub.](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries)</span><span class="sxs-lookup"><span data-stu-id="55fd3-133">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://github.com/Microsoft/WindowsDefenderATP-Hunting-Queries).</span></span> <span data-ttu-id="55fd3-134">Deze opslagplaats staat open voor bijdragen.</span><span class="sxs-lookup"><span data-stu-id="55fd3-134">This repository is open to contributions.</span></span> <span data-ttu-id="55fd3-135">Als u wilt bijdragen, [kunt u gratis deelnemen aan GitHub.](https://github.com/)</span><span class="sxs-lookup"><span data-stu-id="55fd3-135">To contribute, [join GitHub for free](https://github.com/).</span></span> 

>[!TIP]
><span data-ttu-id="55fd3-136">Beveiligingsonderzoekers van Microsoft bieden ook geavanceerde zoekquery's die u kunt gebruiken om activiteiten en indicatoren te vinden die zijn gekoppeld aan nieuwe bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="55fd3-136">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="55fd3-137">Deze query's worden geleverd als onderdeel van de [bedreigingsanalyserapporten](threat-analytics.md) in het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="55fd3-137">These queries are provided as part of the [threat analytics](threat-analytics.md) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="55fd3-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="55fd3-138">Related topics</span></span>
- [<span data-ttu-id="55fd3-139">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="55fd3-139">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="55fd3-140">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="55fd3-140">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="55fd3-141">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="55fd3-141">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="55fd3-142">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="55fd3-142">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="55fd3-143">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="55fd3-143">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="55fd3-144">Overzicht van aangepaste detectie</span><span class="sxs-lookup"><span data-stu-id="55fd3-144">Custom detections overview</span></span>](overview-custom-detections.md)
