---
title: Inzicht in regels voor langzame e-mailstroom oplossen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze het inzicht in regels voor trage e-mailstroom oplossen in het beveiligings- & compliancecentrum gebruiken om inefficiënte of gebroken regels voor e-mailstroom (ook wel transportregels genoemd) in hun organisatie te identificeren en op te lossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 22ce3549077ad9b358165245159393d3e25e61c8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924104"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="512d6-103">Inzicht in regels voor trage e-mailstroom oplossen in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="512d6-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="512d6-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="512d6-104">**Applies to**</span></span>
- [<span data-ttu-id="512d6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="512d6-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="512d6-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="512d6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="512d6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="512d6-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="512d6-108">Inefficiënte regels voor e-mailstroom (ook wel transportregels genoemd) kunnen leiden tot vertragingen in de e-mailstroom voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="512d6-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="512d6-109">In dit inzicht worden regels voor e-mailstroomrapporten berapportage die van invloed zijn op de e-mailstroom van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="512d6-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="512d6-110">Voorbeelden van deze typen regels zijn:</span><span class="sxs-lookup"><span data-stu-id="512d6-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="512d6-111">Voorwaarden die gebruik maken **van Is lid van** voor grote groepen.</span><span class="sxs-lookup"><span data-stu-id="512d6-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="512d6-112">Voorwaarden die gebruikmaken van complexe regulier expressiepatroon (regex).</span><span class="sxs-lookup"><span data-stu-id="512d6-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="512d6-113">Voorwaarden voor het inchecken van bijlagen met inhoud.</span><span class="sxs-lookup"><span data-stu-id="512d6-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="512d6-114">Het **inzicht** in regels voor  trage e-mailstroom oplossen in het gebied Aanbevolen voor u van het e-mailstroomdashboard [in](mail-flow-insights-v2.md) het Compliancecentrum voor beveiliging [&](https://protection.office.com) meldt u wanneer het te lang duurt voordat een regel voor een e-mailstroom wordt voltooid.</span><span class="sxs-lookup"><span data-stu-id="512d6-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="512d6-115">Dit inzicht wordt alleen weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-mailluss hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="512d6-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="512d6-116">U kunt deze melding gebruiken om e-mailstroomregels te identificeren en aan te passen om vertragingen in de e-mailstroom te verminderen.</span><span class="sxs-lookup"><span data-stu-id="512d6-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Inzicht in regels voor trage e-mailstroom oplossen in het gebied Aanbevolen voor u van het e-mailstroomdashboard](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="512d6-118">Wanneer u op **Details weergeven** op de widget klikt, wordt er een flyout weergegeven met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="512d6-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="512d6-119">**Regel:** U kunt de muisaanwijzer boven de samenvatting houden om alle voorwaarden, uitzonderingen en acties van de regel weer te geven.</span><span class="sxs-lookup"><span data-stu-id="512d6-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="512d6-120">U kunt op de samenvatting klikken om de regel te bewerken in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="512d6-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="512d6-121">**Aantal geëvalueerde berichten:** U kunt op [](message-trace-scc.md) **Voorbeeldberichten** weergeven klikken om de resultaten van bericht trace te bekijken voor een voorbeeld van de berichten die door de regel zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="512d6-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="512d6-122">**Gemiddelde tijd besteed aan elk bericht**</span><span class="sxs-lookup"><span data-stu-id="512d6-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="512d6-123">**Mediaan tijd besteed aan een bericht:** de middelste waarde die de bovenste helft scheidt van de onderste helft van de tijdsgegevens.</span><span class="sxs-lookup"><span data-stu-id="512d6-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Details flyout that appears after clicking View details on the Fix slow mail flow rules insight](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="512d6-125">Zie Voorwaarden en uitzonderingen voor e-mailstroomregelen (predicaten) in Exchange Online voor meer informatie over voorwaarden en [uitzonderingen in regels voor e-mailstroom.](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="512d6-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="512d6-126">Zie ook</span><span class="sxs-lookup"><span data-stu-id="512d6-126">See also</span></span>

<span data-ttu-id="512d6-127">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="512d6-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>