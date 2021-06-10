---
title: Microsoft Defender voor eindpuntincidenten beheren
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
ms.openlocfilehash: c86b53abf54788740c8c78cb0ecf9251b10ea8f7
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842336"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a><span data-ttu-id="b027a-104">Microsoft Defender voor eindpuntincidenten beheren</span><span class="sxs-lookup"><span data-stu-id="b027a-104">Manage Microsoft Defender for Endpoint incidents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b027a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b027a-105">**Applies to:**</span></span>
- [<span data-ttu-id="b027a-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="b027a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b027a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b027a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b027a-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b027a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b027a-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b027a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b027a-110">Het beheren van incidenten is een belangrijk onderdeel van elke cyberbeveiligingsactie.</span><span class="sxs-lookup"><span data-stu-id="b027a-110">Managing incidents is an important part of every cybersecurity operation.</span></span> <span data-ttu-id="b027a-111">U kunt incidenten beheren door een incident te selecteren in **de** wachtrij Incidenten of in het **deelvenster Incidentenbeheer.**</span><span class="sxs-lookup"><span data-stu-id="b027a-111">You can manage incidents by selecting an incident from the **Incidents queue** or the **Incidents management pane**.</span></span> 


<span data-ttu-id="b027a-112">Als u een incident selecteert in **de wachtrij Incidenten,** wordt het **deelvenster Incidentbeheer** weergegeven, waar u de incidentpagina kunt openen voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b027a-112">Selecting an incident from the **Incidents queue** brings up the **Incident management pane** where you can open the incident page for details.</span></span>


![Afbeelding van het deelvenster Incidentenbeheer](images/atp-incidents-mgt-pane-updated.png)

<span data-ttu-id="b027a-114">U kunt incidenten aan uzelf toewijzen, de status en classificatie wijzigen, de naam ervan wijzigen of opmerkingen maken om de voortgang bij te houden.</span><span class="sxs-lookup"><span data-stu-id="b027a-114">You can assign incidents to yourself, change the status and classification, rename, or comment on them to keep track of their progress.</span></span>

> [!TIP]
> <span data-ttu-id="b027a-115">Voor meer zichtbaarheid in één oogopslag worden incidentnamen automatisch gegenereerd op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="b027a-115">For additional visibility at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span> <span data-ttu-id="b027a-116">Hierdoor kunt u snel inzicht krijgen in het bereik van het incident.</span><span class="sxs-lookup"><span data-stu-id="b027a-116">This allows you to quickly understand the scope of the incident.</span></span>
>
> <span data-ttu-id="b027a-117">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="b027a-117">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>
>
> <span data-ttu-id="b027a-118">Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, behouden hun namen.</span><span class="sxs-lookup"><span data-stu-id="b027a-118">Incidents that existed prior the rollout of automatic incident naming will retain their names.</span></span>
>


![Afbeelding van de pagina incidentdetails](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a><span data-ttu-id="b027a-120">Incidenten toewijzen</span><span class="sxs-lookup"><span data-stu-id="b027a-120">Assign incidents</span></span>
<span data-ttu-id="b027a-121">Als er nog geen incident is toegewezen, kunt u Toewijzen aan **mij** selecteren om het incident aan uzelf toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="b027a-121">If an incident has not been assigned yet, you can select **Assign to me** to assign the incident to yourself.</span></span> <span data-ttu-id="b027a-122">Als u dit doet, wordt ervan uit gegaan dat u niet alleen eigenaar bent van het incident, maar ook van alle waarschuwingen die aan het incident zijn gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="b027a-122">Doing so assumes ownership of not just the incident, but also all the alerts associated with it.</span></span>

## <a name="set-status-and-classification"></a><span data-ttu-id="b027a-123">Status en classificatie instellen</span><span class="sxs-lookup"><span data-stu-id="b027a-123">Set status and classification</span></span>
### <a name="incident-status"></a><span data-ttu-id="b027a-124">Incidentstatus</span><span class="sxs-lookup"><span data-stu-id="b027a-124">Incident status</span></span>
<span data-ttu-id="b027a-125">U kunt incidenten categoriseren (als **Actief** of **Opgelost)** door hun status te wijzigen naarmate het onderzoek vordert.</span><span class="sxs-lookup"><span data-stu-id="b027a-125">You can categorize incidents (as **Active**, or **Resolved**) by changing their status as your investigation progresses.</span></span> <span data-ttu-id="b027a-126">Op deze manier kunt u organiseren en beheren hoe uw team kan reageren op incidenten.</span><span class="sxs-lookup"><span data-stu-id="b027a-126">This helps you organize and manage how your team can respond to incidents.</span></span>

<span data-ttu-id="b027a-127">Uw soc-analist kan bijvoorbeeld de urgente **Actieve** incidenten van vandaag bekijken en besluiten deze aan zichzelf toe te wijzen voor onderzoek.</span><span class="sxs-lookup"><span data-stu-id="b027a-127">For example, your SoC analyst can review the urgent **Active** incidents for the day, and decide to assign them to himself for investigation.</span></span>

<span data-ttu-id="b027a-128">Uw soc-analist kan het incident ook instellen als **Opgelost** als het incident is opgelost.</span><span class="sxs-lookup"><span data-stu-id="b027a-128">Alternatively, your SoC analyst might set the incident as **Resolved** if the incident has been remediated.</span></span> 

### <a name="classification"></a><span data-ttu-id="b027a-129">Classificatie</span><span class="sxs-lookup"><span data-stu-id="b027a-129">Classification</span></span>
<span data-ttu-id="b027a-130">U kunt ervoor kiezen geen classificatie in te stellen of te bepalen of een incident waar of onwaar is.</span><span class="sxs-lookup"><span data-stu-id="b027a-130">You can choose not to set a classification, or decide to specify whether an incident is true or false.</span></span> <span data-ttu-id="b027a-131">Als u dit doet, kan het team patronen zien en er van leren.</span><span class="sxs-lookup"><span data-stu-id="b027a-131">Doing so helps the team see patterns and learn from them.</span></span>

### <a name="add-comments"></a><span data-ttu-id="b027a-132">Opmerkingen toevoegen</span><span class="sxs-lookup"><span data-stu-id="b027a-132">Add comments</span></span>
<span data-ttu-id="b027a-133">U kunt opmerkingen toevoegen en historische gebeurtenissen over een incident bekijken om eerdere wijzigingen in het incident weer te geven.</span><span class="sxs-lookup"><span data-stu-id="b027a-133">You can add comments and view historical events about an incident to see previous changes made to it.</span></span>

<span data-ttu-id="b027a-134">Wanneer een wijziging of opmerking wordt aangebracht in een waarschuwing, wordt deze opgenomen in de sectie Opmerkingen en geschiedenis.</span><span class="sxs-lookup"><span data-stu-id="b027a-134">Whenever a change or comment is made to an alert, it is recorded in the Comments and history section.</span></span>

<span data-ttu-id="b027a-135">Toegevoegde opmerkingen worden direct weergegeven in het deelvenster.</span><span class="sxs-lookup"><span data-stu-id="b027a-135">Added comments instantly appear on the pane.</span></span>



## <a name="related-topics"></a><span data-ttu-id="b027a-136">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b027a-136">Related topics</span></span>
- [<span data-ttu-id="b027a-137">Incidentenwachtrij</span><span class="sxs-lookup"><span data-stu-id="b027a-137">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="b027a-138">De incidentenwachtrij weergeven en organiseren</span><span class="sxs-lookup"><span data-stu-id="b027a-138">View and organize the Incidents queue</span></span>](view-incidents-queue.md)
- [<span data-ttu-id="b027a-139">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="b027a-139">Investigate incidents</span></span>](investigate-incidents.md)
