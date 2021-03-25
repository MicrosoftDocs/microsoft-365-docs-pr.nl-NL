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
description: Beheerders kunnen leren hoe ze het inzicht in mogelijke e-maillus oplossen in het e-mailstroomdashboard in het Beveiligings- & Compliancecentrum kunnen gebruiken om e-mailluss in hun organisatie te identificeren en op te lossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bb08eb2f9a5ea0eb72433f92b6d28175edc75b8
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204559"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="3aa5d-103">Mogelijk inzicht in e-maillus oplossen in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="3aa5d-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3aa5d-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="3aa5d-104">**Applies to**</span></span>
- [<span data-ttu-id="3aa5d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3aa5d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="3aa5d-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="3aa5d-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="3aa5d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3aa5d-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="3aa5d-108">E-mailluss zijn slecht omdat:</span><span class="sxs-lookup"><span data-stu-id="3aa5d-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="3aa5d-109">Ze verspillen systeembronnen.</span><span class="sxs-lookup"><span data-stu-id="3aa5d-109">They waste system resources.</span></span>
- <span data-ttu-id="3aa5d-110">Ze gebruiken het e-mailvolumequotum van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3aa5d-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="3aa5d-111">Ze verzenden verwarrende rapporten over niet-bezorging (ook wel NR's of niet-bezorgde berichten genoemd) naar de oorspronkelijke afzenders van het bericht.</span><span class="sxs-lookup"><span data-stu-id="3aa5d-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="3aa5d-112">Het inzicht in mogelijke  **e-maillus** oplossen in het gebied Aanbevolen voor u van het e-mailstroomdashboard in het [beveiligings- & compliancecentrum](https://protection.office.com) meldt u wanneer er een e-maillus wordt gedetecteerd in uw organisatie. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="3aa5d-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="3aa5d-113">Dit inzicht wordt alleen weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-mailluss hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="3aa5d-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Inzicht in regels voor trage e-mailstroom oplossen in het gebied Aanbevolen voor u van het e-mailstroomdashboard](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="3aa5d-115">Wanneer u op **Details weergeven** op de widget klikt, wordt er een flyout weergegeven met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="3aa5d-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="3aa5d-116">**Domein**</span><span class="sxs-lookup"><span data-stu-id="3aa5d-116">**Domain**</span></span>
- <span data-ttu-id="3aa5d-117">**Aantal berichten:** U kunt op [](message-trace-scc.md) **Voorbeeldberichten weergeven** klikken om de resultaten van bericht trace te bekijken voor een voorbeeld van de berichten die door de lus zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="3aa5d-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="3aa5d-118">**Domeintype**" Bijvoorbeeld Gezaghebbend of Niet-gezaghebbend.</span><span class="sxs-lookup"><span data-stu-id="3aa5d-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="3aa5d-119">**MX-record:** De host **(Mail server)** en **Prioriteitswaarden** van de MX-record voor het domein.</span><span class="sxs-lookup"><span data-stu-id="3aa5d-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="3aa5d-120">**Reden voor lus** **en Oplossing:** We identificeren de meest voorkomende scenario's voor e-maillus en bieden aanbevolen acties om de lus op te lossen.</span><span class="sxs-lookup"><span data-stu-id="3aa5d-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Details flyout that appears after clicking View details on the Fix possible mail loop insight](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="3aa5d-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3aa5d-122">See also</span></span>

<span data-ttu-id="3aa5d-123">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="3aa5d-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
