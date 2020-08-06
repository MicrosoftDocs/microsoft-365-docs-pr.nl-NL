---
title: Belangrijkste e-mail stroom status van e-mail stroom in het dashboard voor e-mail stroom
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.custom:
- seo-marvel-apr2020
description: Beheerders kunnen leren hoe u het e-mail stroom status inzicht van de belangrijkste domein kunt gebruiken in het dashboard voor e-mail stroom in het nalevings centrum voor beveiliging & voor het oplossen van problemen met de e-mail stroom in hun e-mail domeinen.
ms.openlocfilehash: 6366e3aee0ab50096f1396776397c80fabc8aaf2
ms.sourcegitcommit: c04f1207cfaddac2a9abef38967c17d689756a96
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/06/2020
ms.locfileid: "46577743"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="5567f-103">Belangrijkste status inzicht in de e-mail stroom van het domein in het beveiligings & nalevings centrum</span><span class="sxs-lookup"><span data-stu-id="5567f-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

<span data-ttu-id="5567f-104">Met de **belangrijkste status van de e-mail stroom** van de e-mail in het Beveiligingscentrum van de e-mail in het compliance [-&](mail-flow-insights-v2.md) Beveiligingscentrum beschikt u over de huidige status voor de domeinen van uw organisatie in de voorwaarden voor de e-mail stroom.</span><span class="sxs-lookup"><span data-stu-id="5567f-104">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the Security & Compliance Center gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="5567f-105">Met deze functie kunt u problemen met domeinen identificeren en oplossen die problemen met de ***e-mail stroom*** kunnen veroorzaken (bijvoorbeeld om externe e-mail te ontvangen), met name domein vervaldatums of domeinen met onjuiste MX-records.</span><span class="sxs-lookup"><span data-stu-id="5567f-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![De widget hoofddomein stroom status in het dashboard voor e-mail stroom in de beveiligings & nalevings centrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="5567f-107">Wanneer u klikt op **Details weergeven** in de widget, verschijnt er een flyout met een **domein status** waarin meer Details voor de status van elk domein worden weergegeven:</span><span class="sxs-lookup"><span data-stu-id="5567f-107">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="5567f-108">**Domein**</span><span class="sxs-lookup"><span data-stu-id="5567f-108">**Domain**</span></span>
- <span data-ttu-id="5567f-109">**Vorige MX-record**</span><span class="sxs-lookup"><span data-stu-id="5567f-109">**Previous MX record**</span></span>
- <span data-ttu-id="5567f-110">**Huidige MX-record**</span><span class="sxs-lookup"><span data-stu-id="5567f-110">**Current MX record**</span></span>
- <span data-ttu-id="5567f-111">**Status van ontvangen e-mail**</span><span class="sxs-lookup"><span data-stu-id="5567f-111">**Email receiving status**</span></span>
- <span data-ttu-id="5567f-112">**Domein status**: een groen vinkje geeft de huidige MX-record aan (op het moment dat u hebt geklikt op de widget) komt overeen met de waarde die we hebben voor de record en het domein heeft een e-mail ontvangen in de afgelopen twee uur.</span><span class="sxs-lookup"><span data-stu-id="5567f-112">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="5567f-113">Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein geen e-mailbericht heeft ontvangen in de afgelopen 6 uur.</span><span class="sxs-lookup"><span data-stu-id="5567f-113">A red X indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="5567f-114">Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="5567f-114">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="5567f-115">Neem contact op met uw domeinregistratieservice of DNS-hostingservice om te zien of het domein is verlopen, of dat de MX-record van het domein onjuist is.</span><span class="sxs-lookup"><span data-stu-id="5567f-115">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="5567f-116">U kunt klikken op **meer weergeven** om dezelfde gegevens te bekijken voor meer domeinen.</span><span class="sxs-lookup"><span data-stu-id="5567f-116">You can click **View more** to see the same information for more domains.</span></span>

![Flyout Details in de e-mail stroom status van het belangrijkste domein](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="related-topics"></a><span data-ttu-id="5567f-118">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="5567f-118">Related topics</span></span>

<span data-ttu-id="5567f-119">Zie voor meer informatie over andere inzichten in het dashboard voor e-mail stroom de [e-mail stroom inzichten in het artikel over de beveiliging & nalevings centrum](mail-flow-insights-v2.md).</span><span class="sxs-lookup"><span data-stu-id="5567f-119">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
