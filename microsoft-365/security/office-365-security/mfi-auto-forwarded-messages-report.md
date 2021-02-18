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
description: Beheerders vinden meer informatie over het rapport met automatisch doorgestuurde berichten in het dashboard voor de e-mailstroom in het & compliancecentrum.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8f5e7088a88307576a054a1f6833101789d68d01
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290631"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="c2cb3-103">Inzichten in automatisch doorgestuurde berichten in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="c2cb3-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c2cb3-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-104">**Applies to**</span></span>
- [<span data-ttu-id="c2cb3-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c2cb3-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c2cb3-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c2cb3-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c2cb3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c2cb3-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c2cb3-108">Het inzicht in automatisch doorgestuurde berichten in het [dashboard E-mailstroom](mail-flow-insights-v2.md) in het [beveiligings- & Compliancecentrum](https://protection.office.com) geeft informatie weer over berichten die automatisch vanuit uw organisatie worden doorgestuurd naar geadresseerden in externe domeinen. </span><span class="sxs-lookup"><span data-stu-id="c2cb3-108">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget voor automatisch doorgestuurde berichten in het & compliancecentrum](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="c2cb3-110">Details van automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="c2cb3-110">Auto-forwarded messages details</span></span>

<span data-ttu-id="c2cb3-111">Wanneer u op het aantal berichten in de widget klikt, wordt een flyoutvenster weergegeven met meer informatie over de automatisch doorgestuurde berichten:</span><span class="sxs-lookup"><span data-stu-id="c2cb3-111">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="c2cb3-112">**Automatisch doorgestuurde berichten met methoden voor doorsturen:**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-112">**Auto-forwarded messages by forwarding methods**:</span></span>

  - <span data-ttu-id="c2cb3-113">**Regels voor de e-mailstroom**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-113">**By mail flow rules**</span></span>
  - <span data-ttu-id="c2cb3-114">**Op regels voor Postvak IN**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-114">**By Inbox rules**</span></span>
  - <span data-ttu-id="c2cb3-115">**Doorsturen via SMTP:** met deze methode wordt automatisch doorsturen aangegeven die beheerders voor een postvak kunnen configureren, zoals is beschreven in Doorsturen van e-mail configureren [voor een postvak.](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)</span><span class="sxs-lookup"><span data-stu-id="c2cb3-115">**By SMTP forwarding**: This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="c2cb3-116">Een koppeling naar het [doorsturende rapport](view-mail-flow-reports.md#forwarding-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c2cb3-116">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="c2cb3-117">**Automatisch doorgestuurde berichten van domeinen en gebruikers:**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-117">**Auto-forwarded messages by domains and users**:</span></span>

  - <span data-ttu-id="c2cb3-118">**De vijf belangrijkste domeinen die zijn doorgestuurd naar**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-118">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="c2cb3-119">**Nieuwe domeinen (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-119">**New domains (last week)**</span></span>
  - <span data-ttu-id="c2cb3-120">**De vijf belangrijkste doorsturende gebruikers**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-120">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="c2cb3-121">**Nieuwe gebruikers (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="c2cb3-121">**New users (last week)**</span></span>
  - <span data-ttu-id="c2cb3-122">Een koppeling naar het [rapport met doorgestuurde wijzigingen](mfi-new-users-forwarding-email.md#forwarding-modifications-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c2cb3-122">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Flyout Details voor het rapport Automatisch doorgestuurde berichten in het beveiligings- & compliancecentrum](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="c2cb3-124">Inzichten</span><span class="sxs-lookup"><span data-stu-id="c2cb3-124">Insights</span></span>

<span data-ttu-id="c2cb3-125">Er worden twee inzichten gegenereerd op basis van de rapportgegevens:</span><span class="sxs-lookup"><span data-stu-id="c2cb3-125">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="c2cb3-126">Nieuwe gebruikers die e-mail doorsturen</span><span class="sxs-lookup"><span data-stu-id="c2cb3-126">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="c2cb3-127">Nieuwe domeinen die e-mail worden doorgestuurd</span><span class="sxs-lookup"><span data-stu-id="c2cb3-127">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="c2cb3-128">Zie ook</span><span class="sxs-lookup"><span data-stu-id="c2cb3-128">See also</span></span>

<span data-ttu-id="c2cb3-129">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c2cb3-129">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
