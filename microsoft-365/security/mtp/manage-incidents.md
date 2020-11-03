---
title: Incidenten beheren in Microsoft 365 Defender
description: Meer informatie over het toewijzen en bijwerken van de status.
keywords: incident, incidenten, waarschuwingen, gerelateerde waarschuwingen, toewijzen, bijwerken, status, beheren, classificatie, Microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 29f55d99dd3acd26ae305c03b533e2ca9bb61f2a
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846650"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a><span data-ttu-id="d925b-104">Incidenten beheren in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d925b-104">Manage incidents in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d925b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d925b-105">**Applies to:**</span></span>
- <span data-ttu-id="d925b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d925b-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="d925b-107">Het beheren van incidenten is een belangrijke oplossing voor de bedreigingen.</span><span class="sxs-lookup"><span data-stu-id="d925b-107">Managing incidents is critical in ensuring that threats are contained and addressed.</span></span> <span data-ttu-id="d925b-108">U kunt in Microsoft 365 Defender toegang krijgen tot het beheer van incidenten op apparaten, gebruikers en postvakken.</span><span class="sxs-lookup"><span data-stu-id="d925b-108">In Microsoft 365 Defender, you have access to managing incidents on devices, users, and mailboxes.</span></span> 


<span data-ttu-id="d925b-109">U kunt incidenten beheren door een incident te selecteren in de **wachtrij met incidenten**.</span><span class="sxs-lookup"><span data-stu-id="d925b-109">You can manage incidents by selecting an incident from the **Incidents queue**.</span></span> 

<span data-ttu-id="d925b-110">U kunt de naam van een incident bewerken, dit oplossen en de classificatie en bepaling ervan instellen.</span><span class="sxs-lookup"><span data-stu-id="d925b-110">You can edit the name of an incident, resolve it, set its classification and determination.</span></span> <span data-ttu-id="d925b-111">U kunt het incident ook aan uzelf toewijzen, tags en opmerkingen toevoegen aan uw incident.</span><span class="sxs-lookup"><span data-stu-id="d925b-111">You can also assign the incident to yourself, add incident tags and comments.</span></span>

<span data-ttu-id="d925b-112">Wanneer u een bericht ontvangt waarbij u wordt onderzocht, kunt u ook op het tabblad waarschuwingen het volgende doen: een groter of kleiner incident maken dat alle relevante waarschuwingen omvat.</span><span class="sxs-lookup"><span data-stu-id="d925b-112">In cases where while investigating you would like to move alerts from one incident to another you can also do so from the Alerts tab, thus creating a larger or smaller incident that include all relevant alerts.</span></span>

## <a name="edit-incident-name"></a><span data-ttu-id="d925b-113">Naam van incident bewerken</span><span class="sxs-lookup"><span data-stu-id="d925b-113">Edit incident name</span></span>
<span data-ttu-id="d925b-114">Voor incidenten worden automatisch een naam toegewezen op basis van waarschuwings kenmerken, zoals het aantal beïnvloede eindpunten, gebruikers die worden getroffen, de detectie bronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="d925b-114">Incidents are automatically assigned a name based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="d925b-115">Zo kunt u snel inzicht krijgen in de reikwijdte van het incident.</span><span class="sxs-lookup"><span data-stu-id="d925b-115">This allows you to quickly understand the scope of the incident.</span></span>

<span data-ttu-id="d925b-116">Voorbeeld: een *incident van meerdere stappen op meerdere eindpunten, gerapporteerd door meerdere bronnen.*</span><span class="sxs-lookup"><span data-stu-id="d925b-116">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

<span data-ttu-id="d925b-117">U kunt de naam van het incident wijzigen, zodat dit beter wordt uitgelijnd met de naamgevingsconventie van uw voorkeur.</span><span class="sxs-lookup"><span data-stu-id="d925b-117">You can modify the incident name to better align with your preferred naming convention.</span></span>

> [!NOTE]
> <span data-ttu-id="d925b-118">Voor incidenten die bestonden na de implementatie van de functie voor het automatisch gebruiken van de naam van een incident, behoudt hun naam.</span><span class="sxs-lookup"><span data-stu-id="d925b-118">Incidents that existed prior the rollout of the automatic incident naming feature will retain their name.</span></span>



## <a name="assign-incidents"></a><span data-ttu-id="d925b-119">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="d925b-119">Assign incidents</span></span>
<span data-ttu-id="d925b-120">Als er nog geen incident is toegewezen, kunt u **toewijzen aan mij** selecteren om het incident aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="d925b-120">If an incident has not yet been assigned, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="d925b-121">Dat betekent dat het eigendom van niet alleen het incident is, maar ook alle bijbehorende meldingen.</span><span class="sxs-lookup"><span data-stu-id="d925b-121">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="d925b-122">Status en classificatie instellen</span><span class="sxs-lookup"><span data-stu-id="d925b-122">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="d925b-123">Status van incident</span><span class="sxs-lookup"><span data-stu-id="d925b-123">Incident status</span></span>
<span data-ttu-id="d925b-124">U kunt incidenten (als **actief** of **opgelost** ) categoriseren door hun status te wijzigen tijdens het onderzoek.</span><span class="sxs-lookup"><span data-stu-id="d925b-124">You can categorize incidents (as **Active** , or **Resolved** ) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="d925b-125">Dit helpt u bij het organiseren en beheren van hoe uw team op incidenten kan reageren.</span><span class="sxs-lookup"><span data-stu-id="d925b-125">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="d925b-126">Uw SOC-analist kan bijvoorbeeld de dringende **actieve** incidenten voor de dag nakijken en besluiten ze aan zichzelf toe te wijzen voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="d925b-126">For example, your SOC analyst can review the urgent **Active** incidents for the day, and decide to assign them to herself for investigation.</span></span>

<span data-ttu-id="d925b-127">U kunt ook uw SOC-analist de schade aanwijzen als **opgelost** als het incident is verholpen.</span><span class="sxs-lookup"><span data-stu-id="d925b-127">Alternatively, your SOC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> <span data-ttu-id="d925b-128">Als u een incident verhelpt, worden alle waarschuwingen die deel uitmaken van het incident automatisch gesloten en nog steeds geopend.</span><span class="sxs-lookup"><span data-stu-id="d925b-128">Resolving an incident will automatically close all alerts that are part of the incident and still open.</span></span> 

### <a name="classification-and-determination"></a><span data-ttu-id="d925b-129">Classificatie en bepaling</span><span class="sxs-lookup"><span data-stu-id="d925b-129">Classification and determination</span></span>
<span data-ttu-id="d925b-130">U kunt ervoor kiezen om een classificatie niet in te stellen, of u kunt opgeven of een incident waar of onwaar is.</span><span class="sxs-lookup"><span data-stu-id="d925b-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="d925b-131">Dit helpt het team patronen te zien en ze te leren kennen.</span><span class="sxs-lookup"><span data-stu-id="d925b-131">Doing so helps the team see patterns and learn from them.</span></span> 

## <a name="add-comments"></a><span data-ttu-id="d925b-132">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="d925b-132">Add comments</span></span>
<span data-ttu-id="d925b-133">U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident weergeven om de eerdere wijzigingen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d925b-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="d925b-134">Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie opmerkingen en geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="d925b-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="d925b-135">Het toevoegen van opmerkingen wordt direct weergegeven in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="d925b-135">Added comments instantly appear on the pane.</span></span>

## <a name="add-incident-tags"></a><span data-ttu-id="d925b-136">Incident Tags toevoegen</span><span class="sxs-lookup"><span data-stu-id="d925b-136">Add incident tags</span></span>
<span data-ttu-id="d925b-137">U kunt aangepaste tags aan een incident toevoegen, bijvoorbeeld om een groep incidenten met een gemeenschappelijke kenmerken te markeren.</span><span class="sxs-lookup"><span data-stu-id="d925b-137">You can add custom tags to an incident, for example to flag a group of incidents with a common characteristics.</span></span> <span data-ttu-id="d925b-138">U kunt de wachtrij voor aanvragen later filteren op alle incidenten met een specifiek label.</span><span class="sxs-lookup"><span data-stu-id="d925b-138">You can later filter the incidents queue for all incidents that contain a specific tag.</span></span>
