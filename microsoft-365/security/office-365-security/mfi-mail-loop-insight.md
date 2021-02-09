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
description: Beheerders kunnen in het dashboard E-mailstroom in het beveiligings- & Compliancecentrum leren hoe ze het inzicht in mogelijke e-mailluss in het dashboard E-maillus herstellen kunnen gebruiken om e-maillussen in hun organisatie te identificeren en te herstellen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3c9607f053fb5011b8c8af3c8bb2073a9d022909
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150229"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="3fc29-103">Inzicht in mogelijke e-maillus herstellen in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="3fc29-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="3fc29-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="3fc29-104">**Applies to**</span></span>
- [<span data-ttu-id="3fc29-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="3fc29-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="3fc29-106">Microsoft Defender voor Office 365-abonnement 1 en abonnement 2</span><span class="sxs-lookup"><span data-stu-id="3fc29-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="3fc29-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3fc29-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="3fc29-108">E-maillussen zijn slecht omdat:</span><span class="sxs-lookup"><span data-stu-id="3fc29-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="3fc29-109">Ze verspillen systeembronnen.</span><span class="sxs-lookup"><span data-stu-id="3fc29-109">They waste system resources.</span></span>
- <span data-ttu-id="3fc29-110">Ze verbruiken het volumequotum voor e-mail van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3fc29-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="3fc29-111">Ze verzenden verwarrende rapporten over niet-bezorging (ook wel NR's of niet-bezorgdberichten genoemd) naar de oorspronkelijke afzenders van het bericht.</span><span class="sxs-lookup"><span data-stu-id="3fc29-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="3fc29-112">Het inzicht in mogelijke  **e-mailluss** in het gebied Aanbevolen voor u in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & Compliancecentrum](https://protection.office.com) wordt u op de hoogte stellen wanneer een e-maillus wordt gedetecteerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3fc29-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="3fc29-113">Dit inzicht wordt pas weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-maillussen hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="3fc29-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Inzicht in regels voor trage e-mailstroom oplossen in het gebied Aanbevolen voor u in het dashboard E-mailstroom](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="3fc29-115">Wanneer u op **Details weergeven** in de widget klikt, verschijnt er een flyout met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="3fc29-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="3fc29-116">**Domein**</span><span class="sxs-lookup"><span data-stu-id="3fc29-116">**Domain**</span></span>
- <span data-ttu-id="3fc29-117">**Aantal berichten:** u kunt op [](message-trace-scc.md) **Voorbeeldberichten** weergeven klikken om de resultaten van bericht traceren te bekijken voor een voorbeeld van de berichten die door de lus zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="3fc29-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="3fc29-118">**Domeintype"** Bijvoorbeeld Gezaghebbend of Niet-gezaghebbend.</span><span class="sxs-lookup"><span data-stu-id="3fc29-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="3fc29-119">**MX-record:** De host **(Mail Server)** en **prioriteitswaarden** van de MX-record voor het domein.</span><span class="sxs-lookup"><span data-stu-id="3fc29-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="3fc29-120">**Loop reason** and **How to fix:** We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span><span class="sxs-lookup"><span data-stu-id="3fc29-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Flyout details die wordt weergegeven nadat u op Details weergeven hebt geklikt op het inzicht in Mogelijke e-maillus herstellen](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="3fc29-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="3fc29-122">See also</span></span>

<span data-ttu-id="3fc29-123">Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="3fc29-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
