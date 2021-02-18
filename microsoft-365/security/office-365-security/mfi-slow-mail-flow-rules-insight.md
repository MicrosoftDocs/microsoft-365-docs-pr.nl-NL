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
description: Beheerders kunnen in het beveiligings- &-compliancecentrum weten hoe ze niet-efficiënt of niet-efficiënt werkende regels voor de e-mailstroom (ook wel transportregels genoemd) in hun organisatie kunnen vaststellen en oplossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a50fa0d36cb025f5d0627a2212254b9d08dc5d9c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290691"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="98603-103">Inzicht in regels voor trage e-mailstroom oplossen in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="98603-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="98603-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="98603-104">**Applies to**</span></span>
- [<span data-ttu-id="98603-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="98603-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="98603-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="98603-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="98603-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="98603-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="98603-108">Niet-efficiënt e-mailstroomregels (ook wel transportregels genoemd) kunnen leiden tot vertragingen in de e-mailstroom voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="98603-108">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="98603-109">Dit inzicht rapporteert regels voor de e-mailstroom die van invloed zijn op de e-mailstroom van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="98603-109">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="98603-110">Voorbeelden van deze soorten regels zijn:</span><span class="sxs-lookup"><span data-stu-id="98603-110">Examples of these types of rules include:</span></span>

- <span data-ttu-id="98603-111">Voorwaarden die gebruikmaken **van Is lid van** grote groepen.</span><span class="sxs-lookup"><span data-stu-id="98603-111">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="98603-112">Voorwaarden die gebruikmaken van complexe reguliere expressies (regex)-patroonmatching.</span><span class="sxs-lookup"><span data-stu-id="98603-112">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="98603-113">Voorwaarden die gebruikmaken van het controleren van inhoud in bijlagen.</span><span class="sxs-lookup"><span data-stu-id="98603-113">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="98603-114">Informatie over regels voor trage  **e-mailstroom** oplossen in het gebied Aanbevolen voor u in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & Compliancecentrum](https://protection.office.com) laat u weten wanneer het te lang duurt voordat een e-mailstroomregel is voltooid.</span><span class="sxs-lookup"><span data-stu-id="98603-114">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="98603-115">Dit inzicht wordt pas weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-maillussen hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="98603-115">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="98603-116">U kunt deze melding gebruiken om regels voor de e-mailstroom te identificeren en aan te passen om de vertraging van de e-mailstroom te beperken.</span><span class="sxs-lookup"><span data-stu-id="98603-116">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Inzicht in regels voor langzame e-mailstroom oplossen in het gebied Aanbevolen voor u in het dashboard E-mailstroom](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="98603-118">Wanneer u op **Details weergeven** in de widget klikt, verschijnt er een flyout met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="98603-118">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="98603-119">**Regel:** u kunt de muisaanwijzer op het overzicht houden om alle voorwaarden, uitzonderingen en acties van de regel te bekijken.</span><span class="sxs-lookup"><span data-stu-id="98603-119">**Rule**: You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="98603-120">U kunt op de samenvatting klikken om de regel te bewerken in het Exchange-beheercentrum (EAC).</span><span class="sxs-lookup"><span data-stu-id="98603-120">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="98603-121">**Aantal geëvalueerde** berichten:  U kunt op [](message-trace-scc.md) Voorbeeldberichten weergeven klikken om de resultaten van bericht traceren te bekijken voor een voorbeeld van de berichten die door de regel zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="98603-121">**Number of messages evaluated**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="98603-122">**Gemiddelde tijd besteed aan elk bericht**</span><span class="sxs-lookup"><span data-stu-id="98603-122">**Average time spent on each message**</span></span>
- <span data-ttu-id="98603-123">**Mediaantijd besteed aan een bericht:** de middelste waarde die de bovenste helft scheidt van de onderste helft van de tijdgegevens.</span><span class="sxs-lookup"><span data-stu-id="98603-123">**Median time spent on a message**: The middle value that separates the upper half from the lower half of time data.</span></span>

![Flyout details die wordt weergegeven nadat u op Details weergeven hebt geklikt op het inzicht in regels voor vertraagde e-mailstroom herstellen](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="98603-125">Zie voorwaarden en uitzonderingen voor e-mailstroomregels en uitzonderingen (predicaten) in Exchange Online voor meer informatie over voorwaarden en [uitzonderingen in regels voor de e-mailstroom.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)</span><span class="sxs-lookup"><span data-stu-id="98603-125">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="98603-126">Zie ook</span><span class="sxs-lookup"><span data-stu-id="98603-126">See also</span></span>

<span data-ttu-id="98603-127">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="98603-127">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
