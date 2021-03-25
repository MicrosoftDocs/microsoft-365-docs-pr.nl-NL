---
title: Microsoft Defender ATP Flow-connector
ms.reviewer: ''
description: Gebruik Microsoft Defender ATP Flow-connector om de beveiliging te automatiseren en een stroom te maken die wordt geactiveerd wanneer er een nieuwe waarschuwing op uw tenant wordt geplaatst.
keywords: flow, ondersteunde api's, api, Microsoft flow, query, automatisering
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6fd210ddfb8e3ab6e4f1f4ffc0635c8b813e3a07
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163385"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a><span data-ttu-id="1601d-104">Microsoft Power Automate (voorheen Microsoft Flow) en Azure-functies</span><span class="sxs-lookup"><span data-stu-id="1601d-104">Microsoft Power Automate (formerly Microsoft Flow), and Azure Functions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1601d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="1601d-105">**Applies to:**</span></span>
- [<span data-ttu-id="1601d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="1601d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1601d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1601d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


- <span data-ttu-id="1601d-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="1601d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="1601d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="1601d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="1601d-110">Het automatiseren van beveiligingsprocedures is een standaardvereiste voor elk modern Beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="1601d-110">Automating security procedures is a standard requirement for every modern Security Operations Center.</span></span> <span data-ttu-id="1601d-111">Het ontbreken van professionele cyberverdedigers dwingt SOC om op de meest efficiënte manier te werken en automatisering is een must.</span><span class="sxs-lookup"><span data-stu-id="1601d-111">The lack of professional cyber defenders forces SOC to work in the most efficient way and automation is a must.</span></span> <span data-ttu-id="1601d-112">Microsoft Power Automate ondersteunt verschillende connectors die daar precies voor zijn gemaakt.</span><span class="sxs-lookup"><span data-stu-id="1601d-112">Microsoft Power Automate supports different connectors that were built exactly for that.</span></span> <span data-ttu-id="1601d-113">U kunt binnen enkele minuten een end-to-end procedureautomatisering maken.</span><span class="sxs-lookup"><span data-stu-id="1601d-113">You can build an end-to-end procedure automation within a few minutes.</span></span>

<span data-ttu-id="1601d-114">Microsoft Defender API heeft een officiële Stroomconnector met veel mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="1601d-114">Microsoft Defender API has an official Flow Connector with many capabilities.</span></span>

![Afbeelding van referenties bewerken1](images/api-flow-0.png)

> [!NOTE]
> <span data-ttu-id="1601d-116">Zie Licenties voor [premium-connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors)voor meer informatie over licentievoorwaarden voor premium connectors.</span><span class="sxs-lookup"><span data-stu-id="1601d-116">For more details about premium connectors licensing prerequisites, see [Licensing for premium connectors](https://docs.microsoft.com/power-automate/triggers-introduction#licensing-for-premium-connectors).</span></span>


## <a name="usage-example"></a><span data-ttu-id="1601d-117">Gebruiksvoorbeeld</span><span class="sxs-lookup"><span data-stu-id="1601d-117">Usage example</span></span>

<span data-ttu-id="1601d-118">In het volgende voorbeeld wordt gedemonstreerd hoe u een stroom maakt die wordt geactiveerd op elk moment dat er een nieuwe waarschuwing op uw tenant plaatsvindt.</span><span class="sxs-lookup"><span data-stu-id="1601d-118">The following example demonstrates how to create a Flow that is triggered any time a new Alert occurs on your tenant.</span></span>

1. <span data-ttu-id="1601d-119">Meld u aan [bij Microsoft Power Automate.](https://flow.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1601d-119">Log in to [Microsoft Power Automate](https://flow.microsoft.com).</span></span>

2. <span data-ttu-id="1601d-120">Ga naar **Mijn stromen**  >  **Nieuw**  >  **geautomatiseerd-van leeg**.</span><span class="sxs-lookup"><span data-stu-id="1601d-120">Go to **My flows** > **New** > **Automated-from blank**.</span></span>

    ![Afbeelding van referenties bewerken2](images/api-flow-1.png)

3. <span data-ttu-id="1601d-122">Kies een naam voor uw stroom, zoek naar 'Microsoft Defender ATP Triggers' als trigger en selecteer vervolgens de nieuwe trigger Waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="1601d-122">Choose a name for your Flow, search for "Microsoft Defender ATP Triggers" as the trigger, and then select the new Alerts trigger.</span></span>

    ![Afbeelding van referenties bewerken3](images/api-flow-2.png)

<span data-ttu-id="1601d-124">Nu hebt u een stroom die wordt geactiveerd telkens wanneer er een nieuwe waarschuwing wordt gegeven.</span><span class="sxs-lookup"><span data-stu-id="1601d-124">Now you have a Flow that is triggered every time a new Alert occurs.</span></span>

![Afbeelding van referenties bewerken4](images/api-flow-3.png)

<span data-ttu-id="1601d-126">Het enige wat u nu hoeft te doen, is uw volgende stappen kiezen.</span><span class="sxs-lookup"><span data-stu-id="1601d-126">All you need to do now is choose your next steps.</span></span>
<span data-ttu-id="1601d-127">U kunt het apparaat bijvoorbeeld isoleren als de ernst van de waarschuwing hoog is en er een e-mailbericht over verzenden.</span><span class="sxs-lookup"><span data-stu-id="1601d-127">For example, you can isolate the device if the Severity of the Alert is High and send an email about it.</span></span>
<span data-ttu-id="1601d-128">De waarschuwingstrigger bevat alleen de waarschuwings-id en de machine-id.</span><span class="sxs-lookup"><span data-stu-id="1601d-128">The Alert trigger provides only the Alert ID and the Machine ID.</span></span> <span data-ttu-id="1601d-129">U kunt de verbindingslijn gebruiken om deze entiteiten uit te vouwen.</span><span class="sxs-lookup"><span data-stu-id="1601d-129">You can use the connector to expand these entities.</span></span>

### <a name="get-the-alert-entity-using-the-connector"></a><span data-ttu-id="1601d-130">De entiteit Waarschuwing ontvangen met behulp van de verbindingslijn</span><span class="sxs-lookup"><span data-stu-id="1601d-130">Get the Alert entity using the connector</span></span>

1. <span data-ttu-id="1601d-131">Kies **Microsoft Defender ATP** voor de nieuwe stap.</span><span class="sxs-lookup"><span data-stu-id="1601d-131">Choose **Microsoft Defender ATP** for the new step.</span></span>

2. <span data-ttu-id="1601d-132">Kies **Waarschuwingen - Eén waarschuwings-API ontvangen.**</span><span class="sxs-lookup"><span data-stu-id="1601d-132">Choose **Alerts - Get single alert API**.</span></span>

3. <span data-ttu-id="1601d-133">Stel de **waarschuwings-id** van de laatste stap in als **Invoer.**</span><span class="sxs-lookup"><span data-stu-id="1601d-133">Set the **Alert ID** from the last step as **Input**.</span></span>

    ![Afbeelding van referenties bewerken5](images/api-flow-4.png)

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a><span data-ttu-id="1601d-135">Het apparaat isoleren als de ernst van de waarschuwing hoog is</span><span class="sxs-lookup"><span data-stu-id="1601d-135">Isolate the device if the Alert's severity is High</span></span>

1. <span data-ttu-id="1601d-136">Voorwaarde **toevoegen** als een nieuwe stap.</span><span class="sxs-lookup"><span data-stu-id="1601d-136">Add **Condition** as a new step.</span></span>

2. <span data-ttu-id="1601d-137">Controleer of de ernst van de waarschuwing **gelijk is aan** Hoog.</span><span class="sxs-lookup"><span data-stu-id="1601d-137">Check if the Alert severity **is equal to** High.</span></span>

   <span data-ttu-id="1601d-138">Zo ja, voeg dan de **MICROSOFT Defender ATP - Machineactie isoleren** toe met de machine-id en een opmerking.</span><span class="sxs-lookup"><span data-stu-id="1601d-138">If yes, add the **Microsoft Defender ATP - Isolate machine** action with the Machine ID and a comment.</span></span>

    ![Afbeelding van referenties bewerken6](images/api-flow-5.png)

3. <span data-ttu-id="1601d-140">Voeg een nieuwe stap toe voor het e-mailen over de waarschuwing en de isolatie.</span><span class="sxs-lookup"><span data-stu-id="1601d-140">Add a new step for emailing about the Alert and the Isolation.</span></span> <span data-ttu-id="1601d-141">Er zijn meerdere e-mailconnectoren die heel eenvoudig te gebruiken zijn, zoals Outlook of Gmail.</span><span class="sxs-lookup"><span data-stu-id="1601d-141">There are multiple email connectors that are very easy to use, such as Outlook or Gmail.</span></span>

4. <span data-ttu-id="1601d-142">Sla uw stroom op.</span><span class="sxs-lookup"><span data-stu-id="1601d-142">Save your flow.</span></span>

<span data-ttu-id="1601d-143">U kunt ook een geplande stroom **maken** met geavanceerde query's en nog veel meer.</span><span class="sxs-lookup"><span data-stu-id="1601d-143">You can also create a **scheduled** flow that runs Advanced Hunting queries and much more!</span></span>

## <a name="related-topic"></a><span data-ttu-id="1601d-144">Gerelateerd onderwerp</span><span class="sxs-lookup"><span data-stu-id="1601d-144">Related topic</span></span>
- [<span data-ttu-id="1601d-145">Microsoft Defender voor eindpunt-API's</span><span class="sxs-lookup"><span data-stu-id="1601d-145">Microsoft Defender for Endpoint APIs</span></span>](apis-intro.md)
