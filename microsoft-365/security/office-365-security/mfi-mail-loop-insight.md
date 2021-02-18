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
ms.openlocfilehash: 7fde0041dfb9901cb0a327eafec78d98a40b4cb9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290559"
---
# <a name="fix-possible-mail-loop-insight-in-the-security--compliance-center"></a><span data-ttu-id="0b785-103">Inzicht in mogelijke e-maillus herstellen in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="0b785-103">Fix possible mail loop insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0b785-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="0b785-104">**Applies to**</span></span>
- [<span data-ttu-id="0b785-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0b785-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0b785-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="0b785-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0b785-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b785-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="0b785-108">E-maillussen zijn slecht omdat:</span><span class="sxs-lookup"><span data-stu-id="0b785-108">Mail loops are bad because:</span></span>

- <span data-ttu-id="0b785-109">Ze verspillen systeembronnen.</span><span class="sxs-lookup"><span data-stu-id="0b785-109">They waste system resources.</span></span>
- <span data-ttu-id="0b785-110">Ze verbruiken het volumequotum voor e-mail van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0b785-110">They consume your organization's mail volume quota.</span></span>
- <span data-ttu-id="0b785-111">Ze verzenden verwarrende rapporten over niet-bezorging (ook wel NDR's of niet-bezorgdberichten genoemd) naar de oorspronkelijke afzenders van het bericht.</span><span class="sxs-lookup"><span data-stu-id="0b785-111">They send confusing non-delivery reports (also known as NDRs or bounce messages) to the original message senders.</span></span>

<span data-ttu-id="0b785-112">Het inzicht in mogelijke  **e-mailluss** in het gebied Aanbevolen voor u in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [beveiligings- & Compliancecentrum](https://protection.office.com) wordt u op de hoogte stellen wanneer een e-maillus wordt gedetecteerd in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0b785-112">The **Fix possible mail loop** insight in the **Recommended for you** area of the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) notifies you when a mail loop is detected in your organization.</span></span>

<span data-ttu-id="0b785-113">Dit inzicht wordt pas weergegeven nadat de voorwaarde is gedetecteerd (als u geen e-maillussen hebt, ziet u het inzicht niet).</span><span class="sxs-lookup"><span data-stu-id="0b785-113">This insight appears only after the condition is detected (if you don't have any mail loops, you won't see the insight).</span></span>

![Inzicht in regels voor trage e-mailstroom oplossen in het gebied Aanbevolen voor u in het dashboard E-mailstroom](../../media/mfi-fix-possible-mail-loop.png)

<span data-ttu-id="0b785-115">Wanneer u op **Details weergeven** in de widget klikt, verschijnt er een flyout met meer informatie:</span><span class="sxs-lookup"><span data-stu-id="0b785-115">When you click **View details** on the widget, a flyout appears with more information:</span></span>

- <span data-ttu-id="0b785-116">**Domein**</span><span class="sxs-lookup"><span data-stu-id="0b785-116">**Domain**</span></span>
- <span data-ttu-id="0b785-117">**Aantal berichten:** u kunt op [](message-trace-scc.md) **Voorbeeldberichten** weergeven klikken om de resultaten van bericht traceren te bekijken voor een voorbeeld van de berichten die door de lus zijn beïnvloed.</span><span class="sxs-lookup"><span data-stu-id="0b785-117">**Number of messages**: You can click **View sample messages** to see the [message trace](message-trace-scc.md) results for a sample of the messages that were affected by the loop.</span></span>
- <span data-ttu-id="0b785-118">**Domeintype"** Bijvoorbeeld Gezaghebbend of Niet-gezaghebbend.</span><span class="sxs-lookup"><span data-stu-id="0b785-118">**Domain type**" For example, Authoritative or Non-authoritative.</span></span>
- <span data-ttu-id="0b785-119">**MX-record:** De host **(Mail Server)** en **prioriteitswaarden** van de MX-record voor het domein.</span><span class="sxs-lookup"><span data-stu-id="0b785-119">**MX record**: The host (**Mail server**) and **Priority** values of the MX record for the domain.</span></span>
- <span data-ttu-id="0b785-120">**Loop reason** and **How to fix:** We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span><span class="sxs-lookup"><span data-stu-id="0b785-120">**Loop reason** and **How to fix**: We'll identify the most common mail loop scenarios and provide recommended actions to fix the loop.</span></span>

![Flyout details die wordt weergegeven nadat u op Details weergeven hebt geklikt op het inzicht in Mogelijke e-maillus herstellen](../../media/mfi-fix-possible-mail-loop-details.png)

## <a name="see-also"></a><span data-ttu-id="0b785-122">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0b785-122">See also</span></span>

<span data-ttu-id="0b785-123">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="0b785-123">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
