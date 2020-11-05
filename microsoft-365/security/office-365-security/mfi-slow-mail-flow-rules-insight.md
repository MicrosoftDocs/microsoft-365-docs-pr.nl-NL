---
title: Inzicht in regels voor langzame e-mailstroom oplossen
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 37125cdb-715d-42d0-b669-1a8efa140813
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u het probleem kunt verhelpen met behulp van het artikel over het oplossen van problemen in de beveiliging & nalevings centrum voor het identificeren en oplossen van onjuiste of verbroken e-mail stroom regels (ook wel een transportregel genoemd) in hun organisatie.
ms.openlocfilehash: f51c5a577fc6d9c52e35a5217cae4ae94c546c9d
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920546"
---
# <a name="fix-slow-mail-flow-rules-insight-in-the-security--compliance-center"></a><span data-ttu-id="f9884-103">Inzicht in langzame e-mail stroom regels in het nalevings centrum voor beveiliging &</span><span class="sxs-lookup"><span data-stu-id="f9884-103">Fix slow mail flow rules insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f9884-104">In de efficiëntie regels voor de e-mail stroom (ook wel transport-regels genoemd) kan de e-mail stroom vertragingen voor uw organisatie veroorzaken.</span><span class="sxs-lookup"><span data-stu-id="f9884-104">Inefficient mail flow rules (also known as transport rules) can lead to mail flow delays for your organization.</span></span> <span data-ttu-id="f9884-105">Dit inzicht geeft een overzicht van e-mail stroom regels met gevolgen voor de e-mail stroom van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="f9884-105">This insight reports mail flow rules that have an impact on your organization's mail flow.</span></span> <span data-ttu-id="f9884-106">Voorbeelden van dit soort regels zijn:</span><span class="sxs-lookup"><span data-stu-id="f9884-106">Examples of these types of rules include:</span></span>

- <span data-ttu-id="f9884-107">Voorwaarden die **deel uitmaakt van** grote groepen.</span><span class="sxs-lookup"><span data-stu-id="f9884-107">Conditions that use **Is member of** for large groups.</span></span>
- <span data-ttu-id="f9884-108">Voorwaarden die gebruikmaken van complexe reguliere expressies (regex)-patroon.</span><span class="sxs-lookup"><span data-stu-id="f9884-108">Conditions that use complex regular expression (regex) pattern matching.</span></span>
- <span data-ttu-id="f9884-109">Voorwaarden voor het gebruik van inhouds controle in bijlagen.</span><span class="sxs-lookup"><span data-stu-id="f9884-109">Conditions that use content checking in attachments.</span></span>

<span data-ttu-id="f9884-110">Met het beleid voor **trage e-mail stroom** kunt u het aanbevolen gebied van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in het [Beveiligingscentrum](https://protection.office.com) **voor** e-mail stroom op de beveiliging &</span><span class="sxs-lookup"><span data-stu-id="f9884-110">The **Fix slow mail flow rules** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail flow rule is taking too long to complete.</span></span>

<span data-ttu-id="f9884-111">Dit inzicht wordt alleen weergegeven nadat de voorwaarde is vastgesteld (als u geen e-mail lussen hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="f9884-111">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

<span data-ttu-id="f9884-112">U kunt deze melding gebruiken om de regels voor de e-mail stroom te identificeren en te perfectioneren, zodat de vertragingen van e-mailberichten kunnen worden beperkt.</span><span class="sxs-lookup"><span data-stu-id="f9884-112">You can use this notification to help you to identify and fine-tune mail flow rules to help reduce mail flow delays.</span></span>

![Meer inzicht in langzame e-mail stroom regels op het gebied aanbevolen voor u in het dashboard voor e-mail stroom](../../media/mfi-fix-slow-mail-flow-rules.png)

<span data-ttu-id="f9884-114">Wanneer u op Details van het object **weergeven** klikt, verschijnt er een flyout met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="f9884-114">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="f9884-115">**Regel** : u kunt de muisaanwijzer op het overzicht plaatsen om alle voorwaarden, uitzonderingen en acties van de regel te zien.</span><span class="sxs-lookup"><span data-stu-id="f9884-115">**Rule** : You can hover over the summary to see all of the conditions, exceptions, and actions of the rule.</span></span> <span data-ttu-id="f9884-116">U kunt op het overzicht klikken om de regel in het Exchange-Beheercentrum (SBV) te bewerken.</span><span class="sxs-lookup"><span data-stu-id="f9884-116">You can click on the summary to edit the rule in the Exchange admin center (EAC).</span></span>
- <span data-ttu-id="f9884-117">**Aantal geëvalueerde berichten** : u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de berichten die door de regel werden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="f9884-117">**Number of messages evaluated** : You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the rule.</span></span>
- <span data-ttu-id="f9884-118">**Gemiddelde tijd die is besteed aan elk bericht**</span><span class="sxs-lookup"><span data-stu-id="f9884-118">**Average time spent on each message**</span></span>
- <span data-ttu-id="f9884-119">**Mediaan tijd besteed aan een bericht** : de middelste waarde die de bovenste helft van de onderste helft van de gegevens scheidt.</span><span class="sxs-lookup"><span data-stu-id="f9884-119">**Median time spent on a message** : The middle value that separates the upper half from the lower half of time data.</span></span>

![Voorbeeld van een flyout dat wordt weergegeven nadat u op Details weergeven hebt geklikt in de regel langzame e-mail stroom](../../media/mfi-fix-slow-mail-flow-rules-details.png)

<span data-ttu-id="f9884-121">Zie voor meer informatie over voorwaarden en uitzonderingen in de e-mail stroom regels de [voorwaarden voor de e-mail stroom regels en uitzonderingen (predikaten) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span><span class="sxs-lookup"><span data-stu-id="f9884-121">For more information about conditions and exceptions in mail flow rules, see [Mail flow rule conditions and exceptions (predicates) in Exchange Online](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions).</span></span>

## <a name="see-also"></a><span data-ttu-id="f9884-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="f9884-122">See also</span></span>

<span data-ttu-id="f9884-123">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="f9884-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
