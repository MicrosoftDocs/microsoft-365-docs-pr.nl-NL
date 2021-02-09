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
description: Beheerders kunnen in het dashboard E-mailstroom in het beveiligings- &-compliancecentrum informatie vinden over het gebruik van de nieuwe domeinen die e-mailinzichten worden doorgestuurd om te onderzoeken wanneer gebruikers berichten doorsturen naar externe domeinen die nooit zijn doorgestuurd.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a4429f1657861091082fdfaedb52c85cec3a0cc1
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150597"
---
# <a name="new-domains-being-forwarded-email-insight-in-the-security--compliance-center"></a><span data-ttu-id="756a6-103">Nieuwe domeinen die e-mailinzichten worden doorgestuurd in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="756a6-103">New domains being forwarded email insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="756a6-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="756a6-104">**Applies to**</span></span>
- [<span data-ttu-id="756a6-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="756a6-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="756a6-106">Microsoft Defender voor Office 365-abonnement 1 en abonnement 2</span><span class="sxs-lookup"><span data-stu-id="756a6-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="756a6-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="756a6-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="756a6-108">Er zijn geldige zakelijke redenen om e-mailberichten door te sturen naar externe geadresseerden in bepaalde domeinen.</span><span class="sxs-lookup"><span data-stu-id="756a6-108">There are valid business reasons to forward email messages to external recipients in specific domains.</span></span> <span data-ttu-id="756a6-109">Het is echter verdacht als gebruikers in uw organisatie plotseling beginnen met het doorsturen van berichten naar een domein waar niemand in uw organisatie ooit berichten naar heeft doorgestuurd (een nieuw domein).</span><span class="sxs-lookup"><span data-stu-id="756a6-109">However, it's suspicious when users in your organization suddenly start forwarding messages to a domain where no one in your organization has ever forwarded messages to (a new domain).</span></span>

<span data-ttu-id="756a6-110">Deze voorwaarde kan aangeven dat de gebruikersaccounts zijn gehackt.</span><span class="sxs-lookup"><span data-stu-id="756a6-110">This condition might indicate that the user accounts are compromised.</span></span> <span data-ttu-id="756a6-111">Als u vermoedt dat de accounts zijn gehackt, bekijkt u Hoe u [reageert op een gekromd e-mailaccount.](responding-to-a-compromised-email-account.md)</span><span class="sxs-lookup"><span data-stu-id="756a6-111">If you suspect the accounts have been compromised, see [Responding to a compromised email account](responding-to-a-compromised-email-account.md).</span></span>

<span data-ttu-id="756a6-112">De **nieuwe domeinen die e-mailinzichten** worden doorgestuurd in het [beveiligings- & compliancecentrum](https://protection.office.com) melden u wanneer gebruikers in uw organisatie berichten naar nieuwe domeinen doorsturen.</span><span class="sxs-lookup"><span data-stu-id="756a6-112">The **New domains being forwarded email** insight in the [Security & Compliance Center](https://protection.office.com) notifies you when users in your organization are forwarding messages to new domains.</span></span>

<span data-ttu-id="756a6-113">Dit inzicht wordt alleen weergegeven wanneer het probleem is gedetecteerd en wordt weergegeven op de [pagina Doorsturen-rapport.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="756a6-113">This insight appears only when the issue is detected, and it appears on the [Forwarding report](view-mail-flow-reports.md#forwarding-report) page.</span></span>

![Inzicht in nieuwe domeinen waarnaar e-mails worden doorgestuurd](../../media/mfi-new-domains-being-forwarded.png)

<span data-ttu-id="756a6-115">Wanneer u op de widget klikt, wordt er een flyout weergegeven waar u meer informatie over de doorgestuurde berichten kunt vinden, inclusief een koppeling naar het [rapport Doorsturen.](view-mail-flow-reports.md#forwarding-report)</span><span class="sxs-lookup"><span data-stu-id="756a6-115">When you click on the widget, a flyout appears where you can find more details about the forwarded messages, including a link back to the [Forwarding report](view-mail-flow-reports.md#forwarding-report).</span></span>

![Flyout details die wordt weergegeven nadat u op de nieuwe domeinen hebt geklikt die e-mailinzicht worden doorgestuurd](../../media/mfi-new-domains-being-forwarded-details.png)

<span data-ttu-id="756a6-117">U komt ook op deze detailpagina wanneer u het inzicht selecteert nadat u op Alles weergeven **hebt** geklikt in het gebied topinzichten **&** gebied met aanbevelingen op (**Dashboard** Rapporten of \>  <https://protection.office.com/insightdashboard> ).</span><span class="sxs-lookup"><span data-stu-id="756a6-117">You can also get to this details page when you select the insight after you click **View all** in the **Top insights & recommendations** area on (**Reports** \> **Dashboard** or <https://protection.office.com/insightdashboard>).</span></span>

<span data-ttu-id="756a6-118">Als u wilt voorkomen dat berichten automatisch worden doorgestuurd naar externe domeinen, configureert u een extern domein voor bepaalde of alle externe domeinen.</span><span class="sxs-lookup"><span data-stu-id="756a6-118">To prevent automatic message forwarding to external domains, configure a remote domain for some or all external domains.</span></span> <span data-ttu-id="756a6-119">Zie Externe domeinen beheren [in Exchange Online voor meer informatie.](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)</span><span class="sxs-lookup"><span data-stu-id="756a6-119">For more information, see [Manage remote domains in Exchange Online](https://docs.microsoft.com/Exchange/mail-flow-best-practices/remote-domains/manage-remote-domains).</span></span>

## <a name="related-topics"></a><span data-ttu-id="756a6-120">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="756a6-120">Related topics</span></span>

<span data-ttu-id="756a6-121">Voor informatie over andere inzichten in het dashboard voor de e-mailstroom, bekijkt u inzichten in de e-mailstroom in het & [compliancecentrum.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="756a6-121">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
