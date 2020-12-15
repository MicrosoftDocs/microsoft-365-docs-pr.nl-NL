---
title: Meer inzicht krijgen middels aanvalssimulatietraining
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Beheerders kunnen zien hoe aanvals training in het Microsoft 365-Beveiligingscentrum van invloed is op werknemers en inzicht krijgen in de resultaten van simulatie en training.
ms.openlocfilehash: 6fc109469f8a9a3cf6aa87e9b8f9e3a024fed6e3
ms.sourcegitcommit: 1a9f0f878c045e1ddd59088ca2a94397605a242a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/14/2020
ms.locfileid: "49667593"
---
# <a name="gain-insights-through-attack-simulation-training"></a><span data-ttu-id="5309e-103">Meer inzicht krijgen middels aanvalssimulatietraining</span><span class="sxs-lookup"><span data-stu-id="5309e-103">Gain insights through Attack simulation training</span></span>

<span data-ttu-id="5309e-104">In simulatie training voor een aanval biedt Microsoft u inzichten op basis van de resultaten van simulaties en opleidingen waarvan de werknemers zijn gekomen.</span><span class="sxs-lookup"><span data-stu-id="5309e-104">Within Attack simulation training, Microsoft provides you with insights based on outcomes of simulations and trainings that employees went through.</span></span> <span data-ttu-id="5309e-105">Met deze inzichten wordt u op de hoogte gehouden van de voortgang van uw werknemers, en adviseert u de volgende stappen om uw werknemers en uw omgeving beter voor te bereiden op aanvallen.</span><span class="sxs-lookup"><span data-stu-id="5309e-105">These insights will help keep you informed on the threat readiness progress of your employees, as well as recommend next steps to better prepare your employees and your environment for attacks.</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="5309e-106">We werken voortdurend aan de uitbreiding van de inzichten die voor u beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="5309e-106">We are continuously working on expanding the insights that are available to you.</span></span> <span data-ttu-id="5309e-107">De werking van gedrag en aanbevolen acties zijn momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="5309e-107">Behavior impact and recommended actions are currently available.</span></span> <span data-ttu-id="5309e-108">Als u wilt beginnen, gaat u naar [training voor simulatie van aanval in het Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/attacksimulator?viewid=overview).</span><span class="sxs-lookup"><span data-stu-id="5309e-108">To start, head over to [Attack simulation training in the Microsoft 365 security center](https://security.microsoft.com/attacksimulator?viewid=overview).</span></span>

## <a name="behavior-impact-on-compromise-rate"></a><span data-ttu-id="5309e-109">Werking van invloed op compromissen</span><span class="sxs-lookup"><span data-stu-id="5309e-109">Behavior impact on compromise rate</span></span>

<span data-ttu-id="5309e-110">Op het tabblad **overzicht** van simulatie van aanval aanval ziet u de **gevolgen voor compromissen voor de beoordeling van de compromissen** .</span><span class="sxs-lookup"><span data-stu-id="5309e-110">On the **Overview** tab of Attack simulation training, you'll find the **behavior impact on compromise rate** card.</span></span> <span data-ttu-id="5309e-111">Op deze kaart ziet u hoe werknemers omgaan met de simulaties die u hebt gemaakt, contrast voor de **voorspelde compromis graad**.</span><span class="sxs-lookup"><span data-stu-id="5309e-111">This card shows how employees dealt with the simulations you ran in contrast to the **predicted compromise rate**.</span></span> <span data-ttu-id="5309e-112">U kunt deze inzichten gebruiken om de voortgang van de werknemers gereed te houden door meerdere simulaties uit te voeren voor dezelfde groepen werknemers.</span><span class="sxs-lookup"><span data-stu-id="5309e-112">You can use these insights to track progress in employees threat readiness by running multiple simulations against the same groups of employees.</span></span>

<span data-ttu-id="5309e-113">In de grafiek ziet u:</span><span class="sxs-lookup"><span data-stu-id="5309e-113">In the graph you can see:</span></span>

- <span data-ttu-id="5309e-114">**Voorspelbare compromis graad** waarbij de gemiddelde compromis graad voor simulaties wordt gebruikt met hetzelfde type nettolading in andere microsoft 365-tenants die gebruikmaken van simulatie training.</span><span class="sxs-lookup"><span data-stu-id="5309e-114">**Predicted compromise rate** which reflects the average compromise rate for simulations using the same type of payload across other Microsoft 365 tenants that use Attack simulation training.</span></span>
- <span data-ttu-id="5309e-115">De **effectieve baudrate** weerspiegelt het percentage van de werknemers dat is gezakt voor de simulatie.</span><span class="sxs-lookup"><span data-stu-id="5309e-115">**Actual compromise rate** reflects the percentage of employees that fell for the simulation.</span></span>

<span data-ttu-id="5309e-116">Daarnaast `<number> less susceptible to phishing` weerspiegelt het verschil tussen het werkelijke aantal werknemers dat is aangetast door de aanval en de voorspelde compromissen.</span><span class="sxs-lookup"><span data-stu-id="5309e-116">Additionally, `<number> less susceptible to phishing` reflects the difference between actual number of employees compromised by the attack and the predicted compromise rate.</span></span> <span data-ttu-id="5309e-117">Dit aantal werknemers is minder waarschijnlijk met soortgelijke aanvallen in de toekomst, terwijl ook `<percent%> better than predicted rate` wordt aangegeven hoe werknemers in het geheel hebben gereageerd op het voor spelde compromis.</span><span class="sxs-lookup"><span data-stu-id="5309e-117">This number of employees is less likely to be compromised by similar attacks in the future, while `<percent%> better than predicted rate` indicates how employees did overall in contrast with the predicted compromise rate.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5309e-118">![Kaart voor gedrag van gedrag bij simulatie van aanvals overzicht](../../media/attack-sim-preview-behavior-impact-card.png)</span><span class="sxs-lookup"><span data-stu-id="5309e-118">![Behavior impact card on Attack simulation training overview](../../media/attack-sim-preview-behavior-impact-card.png)</span></span>

<span data-ttu-id="5309e-119">Als u een gedetailleerdere rapporten wilt weergeven, klikt u op **simulaties weergeven en rapport over trainings effectiviteit**.</span><span class="sxs-lookup"><span data-stu-id="5309e-119">To see a more detailed report, click **View simulations and training efficacy report**.</span></span> <span data-ttu-id="5309e-120">Dit rapport bevat dezelfde informatie met aanvullende context uit de simulatie zelf (bijvoorbeeld simulatie techniek en totaal aantal gebruikers die zijn gericht).</span><span class="sxs-lookup"><span data-stu-id="5309e-120">This report provides the same information with additional context from the simulation itself (for example, simulation technique and total users targeted).</span></span>

## <a name="recommended-actions"></a><span data-ttu-id="5309e-121">Aanbevolen acties</span><span class="sxs-lookup"><span data-stu-id="5309e-121">Recommended actions</span></span>

<span data-ttu-id="5309e-122">Wanneer u op het [tabblad **simulaties**](https://security.microsoft.com/attacksimulator?viewid=simulations)een simulatie selecteert, krijgt u de gewenste details van de simulatie, waar u de sectie **aanbevolen acties** vindt.</span><span class="sxs-lookup"><span data-stu-id="5309e-122">On the [**Simulations** tab](https://security.microsoft.com/attacksimulator?viewid=simulations), selecting a simulation will take you to the simulation details, where you'll find the **Recommended actions** section.</span></span>

<span data-ttu-id="5309e-123">De sectie aanbevolen acties bevat een beschrijving van de aanbevelingen die beschikbaar zijn in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span><span class="sxs-lookup"><span data-stu-id="5309e-123">The recommended actions section details recommendations as available in [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span> <span data-ttu-id="5309e-124">Deze aanbevelingen zijn gebaseerd op de nettolading die wordt gebruikt in de simulatie en helpt u bij het beschermen van uw werknemers en uw omgeving.</span><span class="sxs-lookup"><span data-stu-id="5309e-124">These recommendations are based on the payload used in the simulation, and will help you protect your employees and your environment.</span></span> <span data-ttu-id="5309e-125">Door te klikken op elke actie bij verbetering gaat u naar de details.</span><span class="sxs-lookup"><span data-stu-id="5309e-125">Clicking on each improvement action will take you to its details.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="5309e-126">![Sectie aanbevelings acties voor simulatie van aanval](../../media/attack-sim-preview-recommended-actions.png)</span><span class="sxs-lookup"><span data-stu-id="5309e-126">![Recommendation actions section on Attack simulation training](../../media/attack-sim-preview-recommended-actions.png)</span></span>

## <a name="related-links"></a><span data-ttu-id="5309e-127">Verwante koppelingen</span><span class="sxs-lookup"><span data-stu-id="5309e-127">Related Links</span></span>

<span data-ttu-id="5309e-128">**Aanvals Simulator** [Maak een simulatie aanval](attack-simulation-training.md) en [Maak een nettolading voor de opleiding van uw personen](attack-simulation-training-payloads.md)</span><span class="sxs-lookup"><span data-stu-id="5309e-128">**Attack Simulator** [Create a phishing attack simulation](attack-simulation-training.md) and [create a payload for training your people](attack-simulation-training-payloads.md)</span></span>
