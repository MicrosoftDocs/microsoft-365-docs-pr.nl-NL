---
title: De incidentenwachtrij weergeven en organiseren
ms.reviewer: ''
description: Bekijk de lijst met incidenten en leer hoe u filters kunt toepassen om de lijst te beperken en een meer gerichte weergave te krijgen.
keywords: weergeven, organiseren, incidenten, aggregatie, onderzoeken, wachtrij, ttp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 56fd5aa10cf30e7bdcad213a68430b460e65647c
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844212"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-incidents-queue"></a><span data-ttu-id="1675c-104">De wachtrij Microsoft Defender voor eindpuntincidenten weergeven en organiseren</span><span class="sxs-lookup"><span data-stu-id="1675c-104">View and organize the Microsoft Defender for Endpoint Incidents queue</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1675c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1675c-105">**Applies to:**</span></span>
- [<span data-ttu-id="1675c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="1675c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="1675c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1675c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="1675c-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1675c-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1675c-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1675c-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="1675c-110">De **wachtrij Incidenten** toont een verzameling incidenten die zijn gemarkeerd vanaf apparaten in uw netwerk.</span><span class="sxs-lookup"><span data-stu-id="1675c-110">The **Incidents queue** shows a collection of incidents that were flagged from devices in your network.</span></span> <span data-ttu-id="1675c-111">Het helpt u incidenten te sorteren om prioriteit te geven en een weloverwogen antwoordbesluit voor cyberbeveiliging te maken.</span><span class="sxs-lookup"><span data-stu-id="1675c-111">It helps you sort through incidents to prioritize and create an informed cybersecurity response decision.</span></span>

<span data-ttu-id="1675c-112">Standaard worden in de wachtrij incidenten weergegeven die de afgelopen 30 dagen zijn gezien, waarbij het meest recente incident boven aan de lijst wordt weergegeven, zodat u de meest recente incidenten als eerste kunt zien.</span><span class="sxs-lookup"><span data-stu-id="1675c-112">By default, the queue displays incidents seen in the last 30 days, with the most recent incident showing at the top of the list, helping you see the most recent incidents first.</span></span>

<span data-ttu-id="1675c-113">Er zijn verschillende opties waar u uit kunt kiezen om de wachtrijweergave Incidenten aan te passen.</span><span class="sxs-lookup"><span data-stu-id="1675c-113">There are several options you can choose from to customize the Incidents queue view.</span></span> 

<span data-ttu-id="1675c-114">Op de bovenste navigatie kunt u:</span><span class="sxs-lookup"><span data-stu-id="1675c-114">On the top navigation you can:</span></span>
- <span data-ttu-id="1675c-115">Kolommen aanpassen om kolommen toe te voegen of te verwijderen</span><span class="sxs-lookup"><span data-stu-id="1675c-115">Customize columns to add or remove columns</span></span> 
- <span data-ttu-id="1675c-116">Het aantal items wijzigen dat per pagina moet worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="1675c-116">Modify the number of items to view per page</span></span>
- <span data-ttu-id="1675c-117">De items selecteren die per pagina moeten worden weergegeven</span><span class="sxs-lookup"><span data-stu-id="1675c-117">Select the items to show per page</span></span>
- <span data-ttu-id="1675c-118">Batch-select the incidents to assign</span><span class="sxs-lookup"><span data-stu-id="1675c-118">Batch-select the incidents to assign</span></span> 
- <span data-ttu-id="1675c-119">Navigeren tussen pagina's</span><span class="sxs-lookup"><span data-stu-id="1675c-119">Navigate between pages</span></span>
- <span data-ttu-id="1675c-120">Filters toepassen</span><span class="sxs-lookup"><span data-stu-id="1675c-120">Apply filters</span></span>

![Afbeelding van incidentenwachtrij](images/atp-incident-queue.png)

## <a name="sort-and-filter-the-incidents-queue"></a><span data-ttu-id="1675c-122">De wachtrij voor incidenten sorteren en filteren</span><span class="sxs-lookup"><span data-stu-id="1675c-122">Sort and filter the incidents queue</span></span>
<span data-ttu-id="1675c-123">U kunt de volgende filters toepassen om de lijst met incidenten te beperken en een meer gerichte weergave te krijgen.</span><span class="sxs-lookup"><span data-stu-id="1675c-123">You can apply the following filters to limit the list of incidents and get a more focused view.</span></span>

### <a name="severity"></a><span data-ttu-id="1675c-124">Ernst</span><span class="sxs-lookup"><span data-stu-id="1675c-124">Severity</span></span>

<span data-ttu-id="1675c-125">Ernst van incident</span><span class="sxs-lookup"><span data-stu-id="1675c-125">Incident severity</span></span> | <span data-ttu-id="1675c-126">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="1675c-126">Description</span></span>
:---|:---
<span data-ttu-id="1675c-127">Hoog</span><span class="sxs-lookup"><span data-stu-id="1675c-127">High</span></span> </br><span data-ttu-id="1675c-128">(Rood)</span><span class="sxs-lookup"><span data-stu-id="1675c-128">(Red)</span></span> | <span data-ttu-id="1675c-129">Bedreigingen die vaak worden gekoppeld aan geavanceerde permanente bedreigingen (APT).</span><span class="sxs-lookup"><span data-stu-id="1675c-129">Threats often associated with advanced persistent threats (APT).</span></span> <span data-ttu-id="1675c-130">Deze incidenten geven een hoog risico aan vanwege de ernst van de schade die ze kunnen toebrengen aan apparaten.</span><span class="sxs-lookup"><span data-stu-id="1675c-130">These incidents indicate a high risk due to the severity of damage they can inflict on devices.</span></span>
<span data-ttu-id="1675c-131">Gemiddeld</span><span class="sxs-lookup"><span data-stu-id="1675c-131">Medium</span></span> </br><span data-ttu-id="1675c-132">(Oranje)</span><span class="sxs-lookup"><span data-stu-id="1675c-132">(Orange)</span></span> | <span data-ttu-id="1675c-133">Bedreigingen die zelden worden waargenomen in de organisatie, zoals afwijkende registerwijziging, uitvoering van verdachte bestanden en waargenomen gedrag dat typisch is voor aanvalsfasen.</span><span class="sxs-lookup"><span data-stu-id="1675c-133">Threats rarely observed in the organization, such as anomalous registry change, execution of suspicious files, and observed behaviors typical of attack stages.</span></span>
<span data-ttu-id="1675c-134">Laag</span><span class="sxs-lookup"><span data-stu-id="1675c-134">Low</span></span> </br><span data-ttu-id="1675c-135">(Geel)</span><span class="sxs-lookup"><span data-stu-id="1675c-135">(Yellow)</span></span> | <span data-ttu-id="1675c-136">Bedreigingen die zijn gekoppeld aan voorkomende malware en hackprogramma's die niet noodzakelijkerwijs een geavanceerde bedreiging aangeven die is gericht op de organisatie.</span><span class="sxs-lookup"><span data-stu-id="1675c-136">Threats associated with prevalent malware and hack-tools that do not necessarily indicate an advanced threat targeting the organization.</span></span>
<span data-ttu-id="1675c-137">Informatief</span><span class="sxs-lookup"><span data-stu-id="1675c-137">Informational</span></span> </br><span data-ttu-id="1675c-138">(Grijs)</span><span class="sxs-lookup"><span data-stu-id="1675c-138">(Grey)</span></span> | <span data-ttu-id="1675c-139">Informatie-incidenten worden mogelijk niet beschouwd als schadelijk voor het netwerk, maar kunnen wel goed zijn om bij te houden.</span><span class="sxs-lookup"><span data-stu-id="1675c-139">Informational incidents might not be considered harmful to the network but might be good to keep track of.</span></span>

## <a name="assigned-to"></a><span data-ttu-id="1675c-140">Toegewezen aan</span><span class="sxs-lookup"><span data-stu-id="1675c-140">Assigned to</span></span>
<span data-ttu-id="1675c-141">U kunt ervoor kiezen om de lijst te filteren door toegewezen aan iedereen of degenen te selecteren die aan u zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="1675c-141">You can choose to filter the list by selecting assigned to anyone or ones that are assigned to you.</span></span>

### <a name="category"></a><span data-ttu-id="1675c-142">Categorie</span><span class="sxs-lookup"><span data-stu-id="1675c-142">Category</span></span>
<span data-ttu-id="1675c-143">Incidenten worden gecategoriseerd op basis van de beschrijving van het stadium waarin de cyberbeveiligingsketen zich in de keten voor cyberbeveiligingsbeveiliging beveiligt.</span><span class="sxs-lookup"><span data-stu-id="1675c-143">Incidents are categorized based on the description of the stage by which the cybersecurity kill chain is in.</span></span> <span data-ttu-id="1675c-144">Deze weergave helpt de bedreigingsanalist om prioriteit, urgentie en bijbehorende antwoordstrategie te bepalen die moet worden geïmplementeerd op basis van context.</span><span class="sxs-lookup"><span data-stu-id="1675c-144">This view helps the threat analyst to determine priority, urgency, and corresponding response strategy to deploy based on context.</span></span>

### <a name="status"></a><span data-ttu-id="1675c-145">Status</span><span class="sxs-lookup"><span data-stu-id="1675c-145">Status</span></span>
<span data-ttu-id="1675c-146">U kunt ervoor kiezen om de lijst met weergegeven incidenten te beperken op basis van hun status om te zien welke actief of opgelost zijn.</span><span class="sxs-lookup"><span data-stu-id="1675c-146">You can choose to limit the list of incidents shown based on their status to see which ones are active or resolved.</span></span>

### <a name="data-sensitivity"></a><span data-ttu-id="1675c-147">Gegevensgevoeligheid</span><span class="sxs-lookup"><span data-stu-id="1675c-147">Data sensitivity</span></span>
<span data-ttu-id="1675c-148">Gebruik dit filter om incidenten weer te geven die gevoeligheidslabels bevatten.</span><span class="sxs-lookup"><span data-stu-id="1675c-148">Use this filter to show incidents that contain sensitivity labels.</span></span>

## <a name="incident-naming"></a><span data-ttu-id="1675c-149">Naamgeving voor incidenten</span><span class="sxs-lookup"><span data-stu-id="1675c-149">Incident naming</span></span>

<span data-ttu-id="1675c-150">Als u het bereik van het incident in één oogopslag wilt begrijpen, worden incidentnamen automatisch gegenereerd op basis van waarschuwingskenmerken, zoals het aantal getroffen eindpunten, beïnvloede gebruikers, detectiebronnen of categorieën.</span><span class="sxs-lookup"><span data-stu-id="1675c-150">To understand the incident's scope at a glance, incident names are automatically generated based on alert attributes such as the number of endpoints affected, users affected, detection sources or categories.</span></span>

<span data-ttu-id="1675c-151">Bijvoorbeeld: *incident met meerdere fases op meerdere eindpunten die door meerdere bronnen zijn gerapporteerd.*</span><span class="sxs-lookup"><span data-stu-id="1675c-151">For example: *Multi-stage incident on multiple endpoints reported by multiple sources.*</span></span>

> [!NOTE]
> <span data-ttu-id="1675c-152">Incidenten die vóór de implementatie van automatische naamgeving voor incidenten hebben bestaan, behouden hun naam.</span><span class="sxs-lookup"><span data-stu-id="1675c-152">Incidents that existed prior the rollout of automatic incident naming will retain their name.</span></span>


## <a name="see-also"></a><span data-ttu-id="1675c-153">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1675c-153">See also</span></span>
- [<span data-ttu-id="1675c-154">Incidentenwachtrij</span><span class="sxs-lookup"><span data-stu-id="1675c-154">Incidents queue</span></span>](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [<span data-ttu-id="1675c-155">Incidenten beheren</span><span class="sxs-lookup"><span data-stu-id="1675c-155">Manage incidents</span></span>](manage-incidents.md)
- [<span data-ttu-id="1675c-156">Incidenten onderzoeken</span><span class="sxs-lookup"><span data-stu-id="1675c-156">Investigate incidents</span></span>](investigate-incidents.md)

