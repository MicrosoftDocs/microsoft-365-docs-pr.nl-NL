---
title: Inzicht in mogelijke e-maillus oplossen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp & van het hulpprogramma voor het oplossen van e-mail lussen in hun organisatie e-mail lussen kunt identificeren en oplossen.
ms.openlocfilehash: 162752ce6981e27d6ae2923aeb0fc33aec42bb0f
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826951"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="4b9e3-103">Mogelijke oplossing voor e-mail lussen in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="4b9e3-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

<span data-ttu-id="4b9e3-104">Een lus voor e-mailberichten is slecht omdat dit de systeembronnen verspilt, het volume quotum van uw organisatie gebruikt en geen rapporten van niet-uitgevoerde bezorging (ook wel Ndr's genoemd) aan de oorspronkelijke afzenders stuurt.</span><span class="sxs-lookup"><span data-stu-id="4b9e3-104">A mail loop is bad because it wastes system resources, consumes your organization's mail volume quota, and sends confusing non-delivery reports (also known as NDRs or bounce messages) to the original senders.</span></span>

<span data-ttu-id="4b9e3-105">In het gedeelte **voor** het aanvullen van e-mail van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de & beveiligings **Update** wordt u gewaarschuwd wanneer een e-mail in uw organisatie wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="4b9e3-105">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center notifies you when a mail loop is detected in your organization.</span></span> <span data-ttu-id="4b9e3-106">Dit inzicht wordt alleen weergegeven nadat de voorwaarde is vastgesteld (als u geen e-mail lussen hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="4b9e3-106">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Meer inzicht in langzame e-mail stroom regels op het gebied aanbevolen voor u in het dashboard voor e-mail stroom](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="4b9e3-108">Wanneer u op Details van het object **weergeven** klikt, verschijnt er een flyout met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="4b9e3-108">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="4b9e3-109">**Domein**</span><span class="sxs-lookup"><span data-stu-id="4b9e3-109">**Domain**</span></span>
- <span data-ttu-id="4b9e3-110">**Aantal berichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de berichten die door de lus werden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="4b9e3-110">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="4b9e3-111">**Domeintype**, bijvoorbeeld bindend of niet-bindend.</span><span class="sxs-lookup"><span data-stu-id="4b9e3-111">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="4b9e3-112">**MX-record**: de host (**e-mail server**) en de **prioriteits** waarden van de MX-record voor het domein.</span><span class="sxs-lookup"><span data-stu-id="4b9e3-112">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="4b9e3-113">**Reden voor herhaling** en **oplossing**: we proberen de meest voorkomende scenario's voor e-mail lussen te identificeren en de aanbevolen acties te geven (indien beschikbaar) om de lus te verhelpen.</span><span class="sxs-lookup"><span data-stu-id="4b9e3-113">**Loop reason** and **How to fix**: We'll try to identify the most common mail loop scenarios and provide the recommended actions (if available) to fix the loop.</span></span>

![Voorbeeld van een flyout dat wordt weergegeven nadat u op Details weergeven hebt geklikt in de mogelijke oplossing voor e-mail](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="related-topics"></a><span data-ttu-id="4b9e3-115">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="4b9e3-115">Related topics</span></span>

<span data-ttu-id="4b9e3-116">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="4b9e3-116">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
