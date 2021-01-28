---
title: Inzicht in mogelijke e-maillus oplossen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: cb801985-3c89-4979-9c18-17829a4cb563
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp & van het hulpprogramma voor het oplossen van e-mail lussen in hun organisatie e-mail lussen kunt identificeren en oplossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f08c27c761cdfe4acbbd8cf80e8ab6da8012b55f
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029892"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="7ba96-103">Mogelijke oplossing voor e-mail lussen in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="7ba96-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="7ba96-104">E-mail lussen zijn ongeldig omdat:</span><span class="sxs-lookup"><span data-stu-id="7ba96-104">Mail loops are bad because:</span></span>

- <span data-ttu-id="7ba96-105">Ze verspillen systeembronnen.</span><span class="sxs-lookup"><span data-stu-id="7ba96-105">They waste system resources.</span></span>
- <span data-ttu-id="7ba96-106">De persoon die het e-mail volume quotum van uw organisatie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7ba96-106">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="7ba96-107">Ze verzenden ongeniet-bezorgingsrapporten (ook wel Ndr's genoemd of berichten die berichten versturen) naar de oorspronkelijke afzenders van het bericht.</span><span class="sxs-lookup"><span data-stu-id="7ba96-107">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="7ba96-108">In het gedeelte **voor** het aanvullen van e-mail van het [Dashboard voor e-mail stroom](mail-flow-insights-v2.md) in de [& beveiligings](https://protection.office.com) **Update** wordt u gewaarschuwd wanneer een e-mail in uw organisatie wordt gedetecteerd.</span><span class="sxs-lookup"><span data-stu-id="7ba96-108">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="7ba96-109">Dit inzicht wordt alleen weergegeven nadat de voorwaarde is vastgesteld (als u geen e-mail lussen hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="7ba96-109">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Meer inzicht in langzame e-mail stroom regels op het gebied aanbevolen voor u in het dashboard voor e-mail stroom](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="7ba96-111">Wanneer u op Details van het object **weergeven** klikt, verschijnt er een flyout met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="7ba96-111">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="7ba96-112">**Domein**</span><span class="sxs-lookup"><span data-stu-id="7ba96-112">**Domain**</span></span>
- <span data-ttu-id="7ba96-113">**Aantal berichten**: u kunt op **voorbeeldberichten weergeven** klikken om de resultaten van de [bericht tracering](message-trace-scc.md) te zien voor een voorbeeld van de berichten die door de lus werden beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="7ba96-113">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="7ba96-114">**Domeintype**, bijvoorbeeld bindend of niet-bindend.</span><span class="sxs-lookup"><span data-stu-id="7ba96-114">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="7ba96-115">**MX-record**: de host (**e-mail server**) en de **prioriteits** waarden van de MX-record voor het domein.</span><span class="sxs-lookup"><span data-stu-id="7ba96-115">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="7ba96-116">**Reden voor herhaling** en **oplossing**: de meest voorkomende scenario's voor mail lussen worden aangeduid met de meest voorkomende scenario's voor e-mail lussen en bieden aanbevolen acties om de lus op te lossen.</span><span class="sxs-lookup"><span data-stu-id="7ba96-116">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Voorbeeld van een flyout dat wordt weergegeven nadat u op Details weergeven hebt geklikt in de mogelijke oplossing voor e-mail](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="7ba96-118">Zie ook</span><span class="sxs-lookup"><span data-stu-id="7ba96-118">See also</span></span>

<span data-ttu-id="7ba96-119">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="7ba96-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
