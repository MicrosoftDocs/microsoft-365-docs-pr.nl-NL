---
title: Belangrijkste e-mail stroom status van e-mail stroom in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u met behulp van de belangrijkste status van de e-mail stroom van het e-mailsysteem in het Beveiligingscentrum van het & Beveiligingscentrum van uw MX-records problemen met de e-mail stroom kunt oplossen.
ms.openlocfilehash: 0d750ab4dbe5875796118086fae1d9119dc486f0
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920582"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="efa67-103">Belangrijkste status inzicht in de e-mail stroom van het domein in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="efa67-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="efa67-104">Met de **belangrijkste status van de e-mail stroom** van het domein in het nalevings [Dashboard](mail-flow-insights-v2.md) van de [beveiligings &](https://protection.office.com) hebt u de huidige status van de e-mail stroom voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="efa67-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="efa67-105">Dit inzicht helpt bij het identificeren en oplossen van domeinen met een *_e-mail stroom_* _ problemen.</span><span class="sxs-lookup"><span data-stu-id="efa67-105">This insight helps you identify and troubleshoot domains that are experiencing \* *_mail flow_* _ issues.</span></span> <span data-ttu-id="efa67-106">Het domein kan bijvoorbeeld geen externe e-mail ontvangen omdat het domein is verlopen of het domein een onjuiste MX-record heeft.</span><span class="sxs-lookup"><span data-stu-id="efa67-106">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![De widget hoofddomein stroom status in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="efa67-108">Wanneer u klikt op _ *weergave Details* \* in de widget, verschijnt er een flyout met een **domein status** waarin meer Details voor de status van elk domein worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="efa67-108">When you click _ *View details* \* in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="efa67-109">**Domein**</span><span class="sxs-lookup"><span data-stu-id="efa67-109">**Domain**</span></span>
- <span data-ttu-id="efa67-110">**Vorige MX-record**</span><span class="sxs-lookup"><span data-stu-id="efa67-110">**Previous MX record**</span></span>
- <span data-ttu-id="efa67-111">**Huidige MX-record**</span><span class="sxs-lookup"><span data-stu-id="efa67-111">**Current MX record**</span></span>
- <span data-ttu-id="efa67-112">**Status van ontvangen e-mail**</span><span class="sxs-lookup"><span data-stu-id="efa67-112">**Email receiving status**</span></span>
- <span data-ttu-id="efa67-113">**Domein status** : een groen vinkje geeft de huidige MX-record aan (op het moment dat u hebt geklikt op de widget) komt overeen met de waarde die we hebben voor de record en het domein heeft een e-mail ontvangen in de afgelopen twee uur.</span><span class="sxs-lookup"><span data-stu-id="efa67-113">**Domain status** : A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="efa67-114">Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein geen e-mailbericht heeft ontvangen in de afgelopen 6 uur.</span><span class="sxs-lookup"><span data-stu-id="efa67-114">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="efa67-115">Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="efa67-115">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="efa67-116">Neem contact op met uw domeinregistratieservice of DNS-hostingservice om te zien of het domein is verlopen, of dat de MX-record van het domein onjuist is.</span><span class="sxs-lookup"><span data-stu-id="efa67-116">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="efa67-117">U kunt klikken op **meer weergeven** om dezelfde gegevens te bekijken voor meer domeinen.</span><span class="sxs-lookup"><span data-stu-id="efa67-117">You can click **View more** to see the same information for more domains.</span></span>

![Flyout Details in de e-mail stroom status van het belangrijkste domein](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="efa67-119">Zie ook</span><span class="sxs-lookup"><span data-stu-id="efa67-119">See also</span></span>

<span data-ttu-id="efa67-120">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="efa67-120">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
