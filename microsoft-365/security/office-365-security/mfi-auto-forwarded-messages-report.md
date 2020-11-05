---
title: Inzicht in automatisch doorgestuurde berichten
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: b5543faa-44fa-44c5-8180-fb835e7e452d
description: Beheerders kunnen informatie vinden over het rapport met automatisch doorgestuurde berichten in het dashboard voor de e-mail stroom van het beveiligings & nalevings centrum.
ms.openlocfilehash: 28cb593d56d0b0054c8c8cbe4596d4f7df6442ab
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920594"
---
# <a name="auto-forwarded-messages-insight-in-the-security--compliance-center"></a><span data-ttu-id="82b2d-103">Berichten met automatisch doorgestuurde inzichten in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="82b2d-103">Auto-forwarded messages insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="82b2d-104">Met de **automatisch doorgestuurde berichten** in het [Dashboard voor e-mail stromen](mail-flow-insights-v2.md) in de [beveiligings & nalevings centrum](https://protection.office.com) wordt informatie weergegeven over berichten die automatisch van uw organisatie worden doorgestuurd naar geadresseerden in externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="82b2d-104">The **Auto-forwarded messages** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) displays information about messages that are automatically forwarded from your organization to recipients in external domains.</span></span>

![Widget berichten automatisch doorsturen in het Beveiligingscentrum beveiligings &](../../media/mfi-auto-forwarded-messages.png)

## <a name="auto-forwarded-messages-details"></a><span data-ttu-id="82b2d-106">Details van automatisch doorgestuurde berichten</span><span class="sxs-lookup"><span data-stu-id="82b2d-106">Auto-forwarded messages details</span></span>

<span data-ttu-id="82b2d-107">Wanneer u op het aantal berichten in het object klikt, wordt er een flyout weergegeven met meer informatie over de automatisch doorgestuurde berichten:</span><span class="sxs-lookup"><span data-stu-id="82b2d-107">When you click the number of messages in the widget, a flyout pane appears that shows more information about the auto-forwarded messages:</span></span>

- <span data-ttu-id="82b2d-108">**Berichten automatisch doorsturen met behulp van doorstuur methoden** :</span><span class="sxs-lookup"><span data-stu-id="82b2d-108">**Auto-forwarded messages by forwarding methods** :</span></span>

  - <span data-ttu-id="82b2d-109">**Door een e-mail stroom regel**</span><span class="sxs-lookup"><span data-stu-id="82b2d-109">**By mail flow rules**</span></span>
  - <span data-ttu-id="82b2d-110">**Door regels voor Postvak in**</span><span class="sxs-lookup"><span data-stu-id="82b2d-110">**By Inbox rules**</span></span>
  - <span data-ttu-id="82b2d-111">**Door het doorsturen van SMTP: met** deze methode wordt automatisch doorsturen aangegeven die beheerders kunnen configureren in een postvak, zoals beschreven in het [doorsturen van e-mail voor een postvak configureren](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span><span class="sxs-lookup"><span data-stu-id="82b2d-111">**By SMTP forwarding** : This method indicates automatic forwarding that admins can configure on a mailbox as described in [Configure email forwarding for a mailbox](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding).</span></span>
  - <span data-ttu-id="82b2d-112">Een koppeling naar het [doorstuur rapport](view-mail-flow-reports.md#forwarding-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="82b2d-112">A link to the [Forwarding report](view-mail-flow-reports.md#forwarding-report) for more details.</span></span>

- <span data-ttu-id="82b2d-113">**Berichten automatisch doorsturen en door domeinen en gebruikers** :</span><span class="sxs-lookup"><span data-stu-id="82b2d-113">**Auto-forwarded messages by domains and users** :</span></span>

  - <span data-ttu-id="82b2d-114">**Vijf belangrijkste domeinen doorgestuurd naar**</span><span class="sxs-lookup"><span data-stu-id="82b2d-114">**Top 5 domains forwarded to**</span></span>
  - <span data-ttu-id="82b2d-115">**Nieuwe domeinen (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="82b2d-115">**New domains (last week)**</span></span>
  - <span data-ttu-id="82b2d-116">**Belangrijkste 5 doorstuur gebruikers**</span><span class="sxs-lookup"><span data-stu-id="82b2d-116">**Top 5 forwarding users**</span></span>
  - <span data-ttu-id="82b2d-117">**Nieuwe gebruikers (vorige week)**</span><span class="sxs-lookup"><span data-stu-id="82b2d-117">**New users (last week)**</span></span>
  - <span data-ttu-id="82b2d-118">Een koppeling naar de [lijst met wijzigingen doorsturen](mfi-new-users-forwarding-email.md#forwarding-modifications-report) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="82b2d-118">A link to the [Forwarding modifications report](mfi-new-users-forwarding-email.md#forwarding-modifications-report) for more details.</span></span>

![Flyout Details van het rapport met automatisch doorgestuurde berichten in het Beveiligingscentrum beveiligings &](../../media/mfi-auto-forwarded-messages-details.png)

## <a name="insights"></a><span data-ttu-id="82b2d-120">Inzichten</span><span class="sxs-lookup"><span data-stu-id="82b2d-120">Insights</span></span>

<span data-ttu-id="82b2d-121">Er worden twee inzichten gegenereerd op basis van de rapportgegevens:</span><span class="sxs-lookup"><span data-stu-id="82b2d-121">Two insights are generated based on the report data:</span></span>

- [<span data-ttu-id="82b2d-122">Nieuwe gebruikers die e-mail doorsturen</span><span class="sxs-lookup"><span data-stu-id="82b2d-122">New users forwarding email</span></span>](mfi-new-users-forwarding-email.md)
- [<span data-ttu-id="82b2d-123">Nieuwe domeinen die e-mail worden doorgestuurd</span><span class="sxs-lookup"><span data-stu-id="82b2d-123">New domains being forwarded email</span></span>](mfi-new-domains-being-forwarded-email.md)

## <a name="see-also"></a><span data-ttu-id="82b2d-124">Zie ook</span><span class="sxs-lookup"><span data-stu-id="82b2d-124">See also</span></span>

<span data-ttu-id="82b2d-125">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="82b2d-125">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
