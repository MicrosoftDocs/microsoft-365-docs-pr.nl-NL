---
title: Microsoft Defender ATP-incidenten beheren
description: Beheer incidenten door deze toe te wijzen, de status ervan bij te werken of de classificatie in te stellen.
keywords: incidenten, beheren, toewijzen, status, classificatie, true alert, false alert
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b8b5e806d09f08a12c090a1055f2c165f25b7ea1
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185806"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="ad6ae-104">Microsoft Defender voor eindpuntincidenten beheren</span><span class="sxs-lookup"><span data-stu-id="ad6ae-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="ad6ae-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="ad6ae-105">**Applies to:**</span></span>
- [<span data-ttu-id="ad6ae-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="ad6ae-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ad6ae-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ad6ae-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ad6ae-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="ad6ae-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ad6ae-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="ad6ae-110">Het beheren van incidenten is een belangrijk onderdeel van elke cyberbeveiligingsactie.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="ad6ae-111">U kunt incidenten beheren door een incident te selecteren in **de** wachtrij Incidenten of in het **deelvenster Incidentenbeheer.**</span><span class="sxs-lookup"><span data-stu-id="ad6ae-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="ad6ae-112">Als u een incident selecteert in **de wachtrij Incidenten,** wordt het **deelvenster Incidentbeheer** weergegeven, waar u de incidentpagina kunt openen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Afbeelding van het deelvenster Incidentenbeheer](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="ad6ae-114">U kunt incidenten aan uzelf toewijzen, de status en classificatie wijzigen, de naam ervan wijzigen of opmerkingen maken om de voortgang bij te houden.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="ad6ae-115">Voor meer zichtbaarheid in één oogopslag worden incidentnamen automatisch gegenereerd op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="ad6ae-116">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="ad6ae-117">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="ad6ae-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="ad6ae-118">Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, behouden hun namen.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Afbeelding van de pagina incidentdetails](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="ad6ae-120">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="ad6ae-120">Assign incidents</span></span>
<span data-ttu-id="ad6ae-121">Als er nog geen incident is toegewezen, kunt u Toewijzen aan **mij** selecteren om het incident aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="ad6ae-122">Als u dit doet, wordt ervan uit gegaan dat u niet alleen eigenaar bent van het incident, maar ook van alle waarschuwingen die aan het incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="ad6ae-123">Status en classificatie instellen</span><span class="sxs-lookup"><span data-stu-id="ad6ae-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="ad6ae-124">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="ad6ae-124">Incident status</span></span>
<span data-ttu-id="ad6ae-125">U kunt incidenten categoriseren (als **Actief** of **Opgelost)** door hun status te wijzigen naarmate het onderzoek vordert.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="ad6ae-126">Op deze manier kunt u organiseren en beheren hoe uw team kan reageren op incidenten.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="ad6ae-127">Uw soc-analist kan bijvoorbeeld de urgente **Actieve** incidenten van vandaag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="ad6ae-128">Uw soc-analist kan het incident ook instellen als **Opgelost** als het incident is opgelost.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="ad6ae-129">Classificatie</span><span class="sxs-lookup"><span data-stu-id="ad6ae-129">Classification</span></span>
<span data-ttu-id="ad6ae-130">U kunt ervoor kiezen geen classificatie in te stellen of te bepalen of een incident waar of onwaar is.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="ad6ae-131">Als u dit doet, kan het team patronen zien en er van leren.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="ad6ae-132">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="ad6ae-132">Add comments</span></span>
<span data-ttu-id="ad6ae-133">U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen in het incident weer te geven.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="ad6ae-134">Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="ad6ae-135">Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="ad6ae-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="ad6ae-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="ad6ae-136">Related topics</span></span>
- [<span data-ttu-id="ad6ae-137">Wachtrij incidenten</span><span class="sxs-lookup"><span data-stu-id="ad6ae-137">Incidents queue</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="ad6ae-138">De wachtrij Incidenten weergeven en ordenen</span><span class="sxs-lookup"><span data-stu-id="ad6ae-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="ad6ae-139">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="ad6ae-139">Investigate incidents</span></span>](investigate-incidents.md)
