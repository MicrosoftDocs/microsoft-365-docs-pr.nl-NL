---
title: Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
description: Beheerders kunnen inzicht krijgen in de manier waarop u via de nieuwe domeinen e-mail informatie in het compliance-Dash & Board kunt gebruiken om te onderzoeken wanneer hun gebruikers berichten doorsturen naar externe domeinen waarnaar nooit is doorgestuurd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb44f5d577d18fc38333cca5e8d2d862f288a2e0
ms.sourcegitcommit: 537e513a4a232a01e44ecbc76d86a8bcaf142482
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/27/2021
ms.locfileid: "50029856"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="31f34-103">Nieuwe domeinen worden doorgestuurd via e-mail inzicht in de beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="31f34-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="31f34-104">Er zijn geldige zakelijke redenen voor het doorsturen van e-mailberichten naar externe geadresseerden in bepaalde domeinen.</span><span class="sxs-lookup"><span data-stu-id="31f34-104">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="31f34-105">Het is echter ook verdacht Wanneer gebruikers in uw organisatie zich op een plotselinge plaats van berichten naar een domein kunnen doorsturen, ongeacht waar niemand in uw organisatie ooit berichten heeft doorgestuurd naar (een nieuw domein).</span><span class="sxs-lookup"><span data-stu-id="31f34-105">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="31f34-106">Dit kan betekenen dat de gebruikersaccounts zijn aangetast.</span><span class="sxs-lookup"><span data-stu-id="31f34-106">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="31f34-107">Als u vermoedt dat de accounts zijn aangetast, raadpleegt u [reageren op een gemanipuleerd e-mailaccount](responding-to-a-compromised-email-account.md).</span><span class="sxs-lookup"><span data-stu-id="31f34-107">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="31f34-108">De **nieuwe domeinen waarnaar e-mail inzicht wordt doorgestuurd** in de [beveiliging & nalevings centrum](https://protection.office.com) u ontvangt een melding wanneer gebruikers in uw organisatie berichten doorsturen naar nieuwe domeinen.</span><span class="sxs-lookup"><span data-stu-id="31f34-108">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="31f34-109">Dit inzicht wordt alleen weergegeven als het probleem zich voordoet, en wordt weergegeven op de pagina voor het [doorsturen van rapporten](view-mail-flow-reports.md#forwarding-report) .</span><span class="sxs-lookup"><span data-stu-id="31f34-109">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="31f34-111">Wanneer u op de widget klikt, verschijnt er een flyout waar u meer informatie kunt vinden over de doorgestuurde berichten, waaronder een koppeling terug naar het [doorstuur rapport](view-mail-flow-reports.md#forwarding-report).</span><span class="sxs-lookup"><span data-stu-id="31f34-111">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Info-menu dat wordt weergegeven nadat u op de nieuwe domeinen wordt doorgestuurd](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="31f34-113">U kunt deze detailpagina ook raadplegen wanneer u het inzicht selecteert nadat u op **AllesWeergeven** hebt geklikt in het gebied **belangrijkste inzichten &** gebied voor aanbevelingen ( \> **Dashboard** rapporten of <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="31f34-113">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="31f34-114">Configureer een extern domein voor sommige of alle externe domeinen om te voorkomen dat u automatische doorstuur berichten doorschakelt naar externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="31f34-114">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="31f34-115">Zie [externe domeinen beheren in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="31f34-115">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="31f34-116">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="31f34-116">Related topics</span></span>

<span data-ttu-id="31f34-117">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="31f34-117">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
