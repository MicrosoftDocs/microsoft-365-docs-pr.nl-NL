---
title: Gedeelde query's gebruiken in Microsoft Threat Protection Advanced jacht
description: Start de bedreigings jacht direct met vooraf gedefinieerde en gedeelde query's. Uw query's delen met het publiek of uw organisatie.
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, telemetrie, aangepaste detectie, schema, kusto, github repo, mijn query's, gedeelde query's
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 7cdb15be274c89bd92995b9e947489c62521c6bb
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48429681"
---
# <a name="use-shared-queries-in-advanced-hunting"></a><span data-ttu-id="f9e91-105">Gedeelde query's gebruiken in geavanceerde jacht</span><span class="sxs-lookup"><span data-stu-id="f9e91-105">Use shared queries in advanced hunting</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f9e91-106">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f9e91-106">**Applies to:**</span></span>
- <span data-ttu-id="f9e91-107">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f9e91-107">Microsoft Threat Protection</span></span>



<span data-ttu-id="f9e91-108">U kunt [Geavanceerde](advanced-hunting-overview.md) zoekopdrachten delen tussen gebruikers in dezelfde organisatie.</span><span class="sxs-lookup"><span data-stu-id="f9e91-108">[Advanced hunting](advanced-hunting-overview.md) queries can be shared among users in the same organization.</span></span> <span data-ttu-id="f9e91-109">U kunt ook zoeken naar query's die openbaar zijn gemaakt op GitHub.</span><span class="sxs-lookup"><span data-stu-id="f9e91-109">You can also find queries shared publicly on GitHub.</span></span> <span data-ttu-id="f9e91-110">Met deze query's kunt u snel specifieke scenario's van de Threat-jacht maken zonder dat u query's helemaal hoeft te schrijven.</span><span class="sxs-lookup"><span data-stu-id="f9e91-110">These queries let you quickly pursue specific threat hunting scenarios without having to write queries from scratch.</span></span>

![Afbeelding van gedeelde query's](../../media/advanced-hunting-shared-queries.png)

## <a name="save-modify-and-share-a-query"></a><span data-ttu-id="f9e91-112">Een query opslaan, wijzigen en delen</span><span class="sxs-lookup"><span data-stu-id="f9e91-112">Save, modify, and share a query</span></span>
<span data-ttu-id="f9e91-113">U kunt een nieuwe of bestaande query opslaan, zodat deze alleen toegankelijk is voor u of wordt gedeeld met andere gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f9e91-113">You can save a new or existing query so that it is only accessible to you or shared with other users in your organization.</span></span> 

1. <span data-ttu-id="f9e91-114">Maak of wijzig een query.</span><span class="sxs-lookup"><span data-stu-id="f9e91-114">Create or modify a query.</span></span> 

2. <span data-ttu-id="f9e91-115">Klik op de vervolgkeuzeknop **query opslaan** en selecteer **Opslaan als**.</span><span class="sxs-lookup"><span data-stu-id="f9e91-115">Click the **Save query** drop-down button and select **Save as**.</span></span>
    
3. <span data-ttu-id="f9e91-116">Voer een naam in voor de query.</span><span class="sxs-lookup"><span data-stu-id="f9e91-116">Enter a name for the query.</span></span> 

   ![Afbeelding van het opslaan van een query](../../media/advanced-hunting-save-query.png)

4. <span data-ttu-id="f9e91-118">Selecteer de map waarin u de query wilt opslaan.</span><span class="sxs-lookup"><span data-stu-id="f9e91-118">Select the folder where you'd like to save the query.</span></span>
    - <span data-ttu-id="f9e91-119">**Gedeelde query's** , gedeeld met alle gebruikers van uw organisatie</span><span class="sxs-lookup"><span data-stu-id="f9e91-119">**Shared queries** — shared to all users your organization</span></span>
    - <span data-ttu-id="f9e91-120">**Mijn query's** : alleen toegankelijk voor u</span><span class="sxs-lookup"><span data-stu-id="f9e91-120">**My queries** — accessible only to you</span></span>
    
5. <span data-ttu-id="f9e91-121">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="f9e91-121">Select **Save**.</span></span> 

## <a name="delete-or-rename-a-query"></a><span data-ttu-id="f9e91-122">Een query verwijderen of de naam ervan wijzigen</span><span class="sxs-lookup"><span data-stu-id="f9e91-122">Delete or rename a query</span></span>
1. <span data-ttu-id="f9e91-123">Klik met de rechtermuisknop op de query waarvan u de naam wilt wijzigen of die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="f9e91-123">Right-click on a query you want to rename or delete.</span></span>

    ![Afbeelding van verwijderquery](../../media/advanced_hunting_delete_rename.png)

2. <span data-ttu-id="f9e91-125">Selecteer **verwijderen** en bevestig de verwijdering.</span><span class="sxs-lookup"><span data-stu-id="f9e91-125">Select **Delete** and confirm deletion.</span></span> <span data-ttu-id="f9e91-126">Of selecteer **naam wijzigen** en geef een nieuwe naam voor de query op.</span><span class="sxs-lookup"><span data-stu-id="f9e91-126">Or select **Rename** and provide a new name for the query.</span></span>

## <a name="create-a-direct-link-to-a-query"></a><span data-ttu-id="f9e91-127">Een directe koppeling maken naar een query</span><span class="sxs-lookup"><span data-stu-id="f9e91-127">Create a direct link to a query</span></span>
<span data-ttu-id="f9e91-128">Als u een koppeling wilt maken waarmee de query rechtstreeks wordt geopend in de geavanceerde jacht query editor, maakt u de query af en selecteert u **koppeling delen**.</span><span class="sxs-lookup"><span data-stu-id="f9e91-128">To generate a link that opens your query directly in the advanced hunting query editor, finalize your query and select **Share link**.</span></span>

## <a name="access-queries-in-the-github-repository"></a><span data-ttu-id="f9e91-129">Access-query's in de GitHub-bibliotheek</span><span class="sxs-lookup"><span data-stu-id="f9e91-129">Access queries in the GitHub repository</span></span>  
<span data-ttu-id="f9e91-130">Microsoft-beveiligingsonderzoekers delen regelmatig geavanceerde jacht-query's in een [aangewezen openbare opslagplaats op github](https://aka.ms/hunting-queries).</span><span class="sxs-lookup"><span data-stu-id="f9e91-130">Microsoft security researchers regularly share advanced hunting queries in a [designated public repository on GitHub](https://aka.ms/hunting-queries).</span></span> <span data-ttu-id="f9e91-131">Deze bibliotheek is geopend met bijdragen.</span><span class="sxs-lookup"><span data-stu-id="f9e91-131">This repository is open to contributions.</span></span> <span data-ttu-id="f9e91-132">Als u een bijdrage wilt leveren, kunt u [gratis deelnemen aan github](https://github.com/).</span><span class="sxs-lookup"><span data-stu-id="f9e91-132">To contribute, [join GitHub for free](https://github.com/).</span></span>

>[!tip]
><span data-ttu-id="f9e91-133">Microsoft-beveiligingsonderzoekers leveren ook geavanceerde jacht-query's die u kunt gebruiken om te zoeken naar activiteiten en indicatoren die zijn gekoppeld aan de opkomende bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="f9e91-133">Microsoft security researchers also provide advanced hunting queries that you can use to locate activities and indicators associated with emerging threats.</span></span> <span data-ttu-id="f9e91-134">Deze query's worden opgenomen als onderdeel van de [Threat Analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) -rapporten in het Microsoft Defender-Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="f9e91-134">These queries are provided as part of the [threat analytics](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) reports in Microsoft Defender Security Center.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f9e91-135">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f9e91-135">Related topics</span></span>
- [<span data-ttu-id="f9e91-136">Overzicht van geavanceerd opsporen</span><span class="sxs-lookup"><span data-stu-id="f9e91-136">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f9e91-137">De querytaal leren</span><span class="sxs-lookup"><span data-stu-id="f9e91-137">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f9e91-138">Werken met queryresultaten</span><span class="sxs-lookup"><span data-stu-id="f9e91-138">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="f9e91-139">Opsporen op apparaten en in e-mailberichten, apps en identiteiten</span><span class="sxs-lookup"><span data-stu-id="f9e91-139">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f9e91-140">Meer informatie over het schema</span><span class="sxs-lookup"><span data-stu-id="f9e91-140">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f9e91-141">Aanbevolen procedures voor query's toepassen</span><span class="sxs-lookup"><span data-stu-id="f9e91-141">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
