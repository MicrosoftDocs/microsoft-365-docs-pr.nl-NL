---
title: Inzicht in automatisch doorgestuurde berichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Beheerders kunnen informatie vinden over het rapport met automatisch doorgestuurde berichten in het dashboard voor de e-mail stroom van het beveiligings & nalevings centrum.
ms.openlocfilehash: d4b772e6392e0af22e6bed475970f637ed03dcb1
ms.sourcegitcommit: 1522a6471e0c5254a6d0f592e1f4dfacd1dd473a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/24/2020
ms.locfileid: "48245945"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="33b44-103">Berichten met automatisch doorgestuurde inzichten in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="33b44-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="33b44-104">Met de **automatisch doorgestuurde berichten** in het [Dashboard voor e-mail stromen](mail-flow-insights-v2.md) in de [beveiligings & nalevings centrum](https://protection.office.com) wordt informatie weergegeven over berichten die automatisch van uw organisatie worden doorgestuurd naar geadresseerden in externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="33b44-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget berichten automatisch doorsturen in het Beveiligingscentrum beveiligings &](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="33b44-106">Details van automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="33b44-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="33b44-107">Wanneer u op het aantal berichten in het object klikt, wordt er een flyout weergegeven met meer informatie over de automatisch doorgestuurde berichten:</span><span class="sxs-lookup"><span data-stu-id="33b44-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="33b44-108">**Berichten automatisch doorsturen met behulp van doorstuur methoden**:</span><span class="sxs-lookup"><span data-stu-id="33b44-108">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="33b44-109">**Door een e-mail stroom regel**</span><span class="sxs-lookup"><span data-stu-id="33b44-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="33b44-110">**Door regels voor Postvak in**</span><span class="sxs-lookup"><span data-stu-id="33b44-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="33b44-111">**Door het doorsturen van SMTP**: dit is automatisch doorsturen die beheerders kunnen configureren in een postvak zoals beschreven in het [doorsturen van e-mail voor een postvak configureren](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="33b44-111">**By SMTP forwarding**: This is automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="33b44-112">Een koppeling naar het [doorstuur rapport](view-mail-flow-reports.md#forwarding-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="33b44-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="33b44-113">**Berichten automatisch doorsturen en door domeinen en gebruikers**:</span><span class="sxs-lookup"><span data-stu-id="33b44-113">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="33b44-114">**Vijf belangrijkste domeinen doorgestuurd naar**</span><span class="sxs-lookup"><span data-stu-id="33b44-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="33b44-115">**Nieuwe domeinen (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="33b44-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="33b44-116">**Belangrijkste 5 doorstuur gebruikers**</span><span class="sxs-lookup"><span data-stu-id="33b44-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="33b44-117">**Nieuwe gebruikers (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="33b44-117">**New users (last week)**</span></span>
  - <span data-ttu-id="33b44-118">Een koppeling naar de [lijst met wijzigingen doorsturen](mfi-new-users-forwarding-email.md#forwarding-modifications-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="33b44-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Flyout Details van het rapport met automatisch doorgestuurde berichten in het Beveiligingscentrum beveiligings &](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="33b44-120">Inzichten</span><span class="sxs-lookup"><span data-stu-id="33b44-120">Insights</span></span>

<span data-ttu-id="33b44-121">Er worden twee inzichten gegenereerd op basis van de rapportgegevens:</span><span class="sxs-lookup"><span data-stu-id="33b44-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="33b44-122">Nieuwe gebruikers die e-mail doorsturen</span><span class="sxs-lookup"><span data-stu-id="33b44-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="33b44-123">Nieuwe domeinen die e-mail worden doorgestuurd</span><span class="sxs-lookup"><span data-stu-id="33b44-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="33b44-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="33b44-124">See also</span></span>

<span data-ttu-id="33b44-125">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="33b44-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
