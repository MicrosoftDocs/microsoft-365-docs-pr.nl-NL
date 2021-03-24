---
title: Inzicht in de status van de hoogste domeinstroomstroom in het e-mailstroomdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe ze het inzicht in de status van de hoogste domeinstroomstroom kunnen gebruiken in het e-mailstroomdashboard in het Beveiligings- & Compliancecentrum om problemen met de e-mailstroom met betrekking tot hun MX-records op te lossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 850e72fa0ad7a3f41450a1d0a2c02dd3df4a0cb5
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057898"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="94779-103">Inzicht in de status van de hoogste domeinstroomstroom in het beveiligings- & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="94779-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="94779-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="94779-104">**Applies to**</span></span>
- [<span data-ttu-id="94779-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="94779-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="94779-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="94779-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="94779-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94779-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="94779-108">Het **inzicht in de status** van de hoogste domeinstroomstroom in het [e-mailstroomdashboard](mail-flow-insights-v2.md) in het Beveiligings- & [Compliancecentrum](https://protection.office.com) geeft u de huidige status van de e-mailstroom voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="94779-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="94779-109">Met dit inzicht kunt u domeinen identificeren en oplossen die te maken hebben ***met e-mailstroomproblemen.***</span><span class="sxs-lookup"><span data-stu-id="94779-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="94779-110">Het domein kan bijvoorbeeld geen externe e-mail ontvangen omdat het domein is verlopen of omdat het domein een onjuiste MX-record heeft.</span><span class="sxs-lookup"><span data-stu-id="94779-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![De bovenste widget met domeinstroomstatus in het e-mailstroomdashboard in het beveiligings- & Compliancecentrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="94779-112">Wanneer u op **Details weergeven** in de widget klikt, wordt er een fly-out voor **domeinstatus** weergegeven waarin meer details worden weergegeven voor de status van elk domein:</span><span class="sxs-lookup"><span data-stu-id="94779-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="94779-113">**Domein**</span><span class="sxs-lookup"><span data-stu-id="94779-113">**Domain**</span></span>
- <span data-ttu-id="94779-114">**Vorige MX-record**</span><span class="sxs-lookup"><span data-stu-id="94779-114">**Previous MX record**</span></span>
- <span data-ttu-id="94779-115">**Huidige MX-record**</span><span class="sxs-lookup"><span data-stu-id="94779-115">**Current MX record**</span></span>
- <span data-ttu-id="94779-116">**Status voor het ontvangen van e-mail**</span><span class="sxs-lookup"><span data-stu-id="94779-116">**Email receiving status**</span></span>
- <span data-ttu-id="94779-117">**Domeinstatus:** een groen vinkje geeft aan dat de huidige MX-record (op het moment dat u op de widget hebt geklikt) overeenkomt met de waarde die we hebben op de record en dat het domein de afgelopen twee uur e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="94779-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="94779-118">Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="94779-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="94779-119">Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="94779-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="94779-120">Neem contact op met uw domeinregistrar of DNS-hostingservice om te zien of het domein is verlopen of dat de MX-record van het domein onjuist is.</span><span class="sxs-lookup"><span data-stu-id="94779-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="94779-121">U kunt op **Meer weergeven** klikken om dezelfde informatie weer te geven voor meer domeinen.</span><span class="sxs-lookup"><span data-stu-id="94779-121">You can click **View more** to see the same information for more domains.</span></span>

![Details flyout in the Top domain mail flow status insight](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="94779-123">Zie ook</span><span class="sxs-lookup"><span data-stu-id="94779-123">See also</span></span>

<span data-ttu-id="94779-124">Zie E-mailstroominzichten in het Beveiligings- & compliancecentrum voor meer informatie over andere inzichten [in het e-mailstroomdashboard.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="94779-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
