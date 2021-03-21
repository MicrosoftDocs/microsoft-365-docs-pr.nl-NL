---
title: Inzicht in automatisch doorgestuurde berichten
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Beheerders kunnen meer informatie krijgen over het rapport Automatisch doorgestuurde berichten in het e-mailstroomdashboard in het beveiligings- & Compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 75cf060d9a597bb991fc8af2c4c70f9ecc592ad7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929358"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="b2cc7-103">Inzicht in automatisch doorgestuurde berichten in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="b2cc7-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b2cc7-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-104">**Applies to**</span></span>
- [<span data-ttu-id="b2cc7-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="b2cc7-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="b2cc7-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="b2cc7-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="b2cc7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b2cc7-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="b2cc7-108">Het **inzicht in** automatisch doorgestuurde berichten in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het [Beveiligings- & Compliancecentrum](https://protection.office.com) bevat informatie over berichten die automatisch vanuit uw organisatie worden doorgestuurd naar geadresseerden in externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="b2cc7-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget Automatisch doorgestuurde berichten in het beveiligings- & compliancecentrum](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="b2cc7-110">Details van automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="b2cc7-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="b2cc7-111">Wanneer u op het aantal berichten in de widget klikt, wordt er een flyoutvenster weergegeven met meer informatie over de automatisch doorgestuurde berichten:</span><span class="sxs-lookup"><span data-stu-id="b2cc7-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="b2cc7-112">**Automatisch doorgestuurde berichten doorsturen:**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="b2cc7-113">**Op e-mailstroomregels**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="b2cc7-114">**Op Regels voor Postvak IN**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="b2cc7-115">**Doorsturen via SMTP:** Deze methode geeft automatisch doorsturen aan dat beheerders kunnen configureren in een postvak, zoals beschreven in E-mail doorsturen configureren [voor een postvak.](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="b2cc7-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="b2cc7-116">Een koppeling naar het [rapport Doorsturen](view-mail-flow-reports.md#forwarding-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b2cc7-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="b2cc7-117">**Automatisch doorgestuurde berichten door domeinen en gebruikers:**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="b2cc7-118">**Top 5 domeinen die zijn doorgestuurd naar**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="b2cc7-119">**Nieuwe domeinen (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="b2cc7-120">**Top 5 doorsturende gebruikers**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="b2cc7-121">**Nieuwe gebruikers (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="b2cc7-121">**New users (last week)**</span></span>
  - <span data-ttu-id="b2cc7-122">Een koppeling naar het [rapport Wijzigingen doorsturen](mfi-new-users-forwarding-email.md#forwarding-modifications-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b2cc7-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Details flyout for the Auto-forwarded messages report in the Security & Compliance Center](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="b2cc7-124">Inzichten</span><span class="sxs-lookup"><span data-stu-id="b2cc7-124">Insights</span></span>

<span data-ttu-id="b2cc7-125">Er worden twee inzichten gegenereerd op basis van de rapportgegevens:</span><span class="sxs-lookup"><span data-stu-id="b2cc7-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="b2cc7-126">Nieuwe gebruikers die e-mail doorsturen</span><span class="sxs-lookup"><span data-stu-id="b2cc7-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="b2cc7-127">Nieuwe domeinen die e-mail worden doorgestuurd</span><span class="sxs-lookup"><span data-stu-id="b2cc7-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="b2cc7-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="b2cc7-128">See also</span></span>

<span data-ttu-id="b2cc7-129">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="b2cc7-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>