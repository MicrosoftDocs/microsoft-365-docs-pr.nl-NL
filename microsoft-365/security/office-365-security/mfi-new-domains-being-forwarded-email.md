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
description: Beheerders kunnen leren hoe ze het inzicht van de nieuwe domeinen die per e-mail worden doorgestuurd, kunnen gebruiken in het e-mailstroomdashboard in het beveiligings- & compliancecentrum om te onderzoeken wanneer hun gebruikers berichten doorsturen naar externe domeinen die nog nooit zijn doorgestuurd naar.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1310350bd4ff6b43d321f5888c9436ac71debb82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929346"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="c75a5-103">Nieuwe domeinen die inzicht krijgen in e-mail doorgestuurd in het Beveiligings- & Compliance center</span><span class="sxs-lookup"><span data-stu-id="c75a5-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="c75a5-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c75a5-104">**Applies to**</span></span>
- [<span data-ttu-id="c75a5-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="c75a5-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="c75a5-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c75a5-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="c75a5-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c75a5-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="c75a5-108">Er zijn geldige zakelijke redenen om e-mailberichten door te sturen naar externe geadresseerden in specifieke domeinen.</span><span class="sxs-lookup"><span data-stu-id="c75a5-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="c75a5-109">Het is echter verdacht wanneer gebruikers in uw organisatie plotseling berichten doorsturen naar een domein waar niemand in uw organisatie ooit berichten heeft doorgestuurd naar (een nieuw domein).</span><span class="sxs-lookup"><span data-stu-id="c75a5-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="c75a5-110">Deze voorwaarde kan aangeven dat de gebruikersaccounts zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="c75a5-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="c75a5-111">Zie Reageren op een gekromd [e-mailaccount](responding-to-a-compromised-email-account.md)als u vermoedt dat de accounts zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="c75a5-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="c75a5-112">De **nieuwe domeinen die e-mailinzicht** worden doorgestuurd in het beveiligings- & [compliancecentrum,](https://protection.office.com) worden u op de hoogte gehouden wanneer gebruikers in uw organisatie berichten doorsturen naar nieuwe domeinen.</span><span class="sxs-lookup"><span data-stu-id="c75a5-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="c75a5-113">Dit inzicht wordt alleen weergegeven wanneer het probleem wordt gedetecteerd en wordt weergegeven op de pagina [Rapport](view-mail-flow-reports.md#forwarding-report) doorsturen.</span><span class="sxs-lookup"><span data-stu-id="c75a5-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="c75a5-115">Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer informatie over de doorgestuurde berichten kunt vinden, waaronder een koppeling naar [het rapport Doorsturen.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="c75a5-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Details flyout that appears after clicking on the New domains being forwarded email insight (Details flyout that appears after clicking on the New domains being forwarded email insight](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="c75a5-117">U kunt ook naar deze detailspagina gaan wanneer u het inzicht selecteert nadat u op Alles weergeven hebt geklikt **in** het gebied Top **insights & aanbevelingen** op ( \> **Rapportendashboard** of <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="c75a5-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="c75a5-118">Als u wilt voorkomen dat berichten automatisch worden doorgestuurd naar externe domeinen, configureert u een extern domein voor sommige of alle externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="c75a5-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="c75a5-119">Zie Externe domeinen beheren in Exchange Online voor [meer informatie.](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="c75a5-119">For more information, see [Manage remote domains in Exchange Online](/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c75a5-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c75a5-120">Related topics</span></span>

<span data-ttu-id="c75a5-121">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="c75a5-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>