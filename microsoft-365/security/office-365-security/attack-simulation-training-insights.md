---
title: Meer inzicht krijgen middels aanvalssimulatietraining
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe training voor aanvalssimulaties in de Microsoft 365 Defender-portal werknemers beïnvloedt en inzichten kunnen krijgen uit simulatie- en trainingsresultaten.
ms.technology: mdo
ms.openlocfilehash: e189864a42d025bb5ce720a6edb6c1c2c8c84623
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878374"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="97094-103">Meer inzicht krijgen middels aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="97094-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="97094-104">**Van toepassing op** [Microsoft Defender voor Office 365 abonnement 2](defender-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="97094-104">**Applies to** [Microsoft Defender for Office 365 plan 2](defender-for-office-365.md)</span></span>

<span data-ttu-id="97094-105">In de trainingstraining aanvalssimulatie biedt Microsoft u inzichten op basis van resultaten van simulaties en trainingen die werknemers hebben doormaakt.</span><span class="sxs-lookup"><span data-stu-id="97094-105">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="97094-106">Deze inzichten helpen u op de hoogte te blijven van de voortgang van de bedreigingsbereidheid van uw werknemers en u kunt ook de volgende stappen aanbevelen om uw werknemers en uw omgeving beter voor te bereiden op aanvallen.</span><span class="sxs-lookup"><span data-stu-id="97094-106">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

<span data-ttu-id="97094-107">We werken voortdurend aan het uitbreiden van de inzichten die voor u beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="97094-107">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="97094-108">Gedrag en aanbevolen acties zijn momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="97094-108">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="97094-109">Om te beginnen gaat u naar De training voor de [aanvalssimulatie in Microsoft 365 Defender-portal.](https://security.microsoft.com/attacksimulator?viewid=overview)</span><span class="sxs-lookup"><span data-stu-id="97094-109">To start, head over to [Attack simulation training in the Microsoft 365 Defender portal](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="97094-110">Effect op het gedrag van compromissen</span><span class="sxs-lookup"><span data-stu-id="97094-110">Behavior impact on compromise rate</span></span>

<span data-ttu-id="97094-111">Op het **tabblad Overzicht** van de trainingstraining aanvalssimulatie vindt u de invloed van het gedrag op de kaart **met compromispercentages.**</span><span class="sxs-lookup"><span data-stu-id="97094-111">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="97094-112">Op deze kaart ziet u hoe werknemers om zijngegaan met de simulaties die u hebt uitgevoerd, in tegenstelling tot het **voorspelde compromispercentage.**</span><span class="sxs-lookup"><span data-stu-id="97094-112">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="97094-113">U kunt deze inzichten gebruiken om de voortgang in de gereedheid van bedreigingen voor werknemers bij te houden door meerdere simulaties uit te werken tegen dezelfde groepen werknemers.</span><span class="sxs-lookup"><span data-stu-id="97094-113">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="97094-114">In de grafiek ziet u:</span><span class="sxs-lookup"><span data-stu-id="97094-114">In the graph you can see:</span></span>

- <span data-ttu-id="97094-115">**Voorspelde compromissnelheid** die de gemiddelde compromissnelheid weerspiegelt voor simulaties met hetzelfde type payload in andere Microsoft 365 tenants die gebruikmaken van attack-simulatietraining.</span><span class="sxs-lookup"><span data-stu-id="97094-115">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="97094-116">**Het werkelijke compromispercentage** weerspiegelt het percentage werknemers dat voor de simulatie is gevallen.</span><span class="sxs-lookup"><span data-stu-id="97094-116">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="97094-117">Daarnaast wordt het verschil weerspiegeld tussen het werkelijke aantal werknemers dat door de aanval is gecompromitteerd `<number> less susceptible to phishing` en het voorspelde compromispercentage.</span><span class="sxs-lookup"><span data-stu-id="97094-117">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="97094-118">Dit aantal werknemers wordt in de toekomst minder vaak door soortgelijke aanvallen gecompromitteerd, maar geeft aan hoe werknemers het over het algemeen hebben gedaan, in tegenstelling tot het `<percent%> better than predicted rate` voorspelde compromispercentage.</span><span class="sxs-lookup"><span data-stu-id="97094-118">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="97094-119">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="97094-119">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="97094-120">Als u een gedetailleerder rapport wilt bekijken, klikt u op Simulaties en **trainingsre doeltreffendheidsrapport weergeven.**</span><span class="sxs-lookup"><span data-stu-id="97094-120">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="97094-121">Dit rapport bevat dezelfde informatie met aanvullende context uit de simulatie zelf (bijvoorbeeld de simulatietechniek en het totale aantal beoogde gebruikers).</span><span class="sxs-lookup"><span data-stu-id="97094-121">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="97094-122">Aanbevolen acties</span><span class="sxs-lookup"><span data-stu-id="97094-122">Recommended actions</span></span>

<span data-ttu-id="97094-123">Op het [ **tabblad Simulaties** gaat](https://security.microsoft.com/attacksimulator?viewid=simulations)u met het selecteren van een simulatie naar de details van de simulatie, waar u de sectie **Aanbevolen acties** vindt.</span><span class="sxs-lookup"><span data-stu-id="97094-123">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="97094-124">In de sectie Aanbevolen acties worden aanbevelingen be details gegeven die beschikbaar zijn in [Microsoft Secure Score.](../defender/microsoft-secure-score.md)</span><span class="sxs-lookup"><span data-stu-id="97094-124">The recommended actions section details recommendations as available in [Microsoft Secure Score](../defender/microsoft-secure-score.md).</span></span> <span data-ttu-id="97094-125">Deze aanbevelingen zijn gebaseerd op de payload die in de simulatie wordt gebruikt en helpen u uw werknemers en uw omgeving te beschermen.</span><span class="sxs-lookup"><span data-stu-id="97094-125">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="97094-126">Als u op elke verbeteringsactie klikt, krijgt u de details.</span><span class="sxs-lookup"><span data-stu-id="97094-126">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="97094-127">![Sectie Aanbevelingsacties over training voor aanvalssimulatie](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="97094-127">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="97094-128">Gerelateerde koppelingen</span><span class="sxs-lookup"><span data-stu-id="97094-128">Related Links</span></span>

[<span data-ttu-id="97094-129">Aan de slag met aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="97094-129">Get started using Attack simulation training</span></span>](attack-simulation-training-get-started.md)

[<span data-ttu-id="97094-130">Een phishing-aanvalssimulatie maken</span><span class="sxs-lookup"><span data-stu-id="97094-130">Create a phishing attack simulation</span></span>](attack-simulation-training.md)

[<span data-ttu-id="97094-131">een payload maken voor het trainen van uw personen</span><span class="sxs-lookup"><span data-stu-id="97094-131">create a payload for training your people</span></span>](attack-simulation-training-payloads.md)
