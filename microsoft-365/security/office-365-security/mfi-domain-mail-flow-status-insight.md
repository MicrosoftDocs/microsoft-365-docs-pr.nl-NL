---
title: Het belangrijkste inzicht in de status van de domein-e-mailstroom in het dashboard E-mailstroom
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
description: Beheerders kunnen in het beveiligings- & Compliancecentrum in het dashboard E-mailstroom het belangrijkste inzicht in de status van de domeinstroomstroom gebruiken om problemen met de e-mailstroom met betrekking tot hun MX-records op te lossen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df0f571d29d72b23e7b2e210b61a4fb1676175aa
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150205"
---
# <a name="top-domain-mail-flow-status-insight-in-the-security--compliance-center"></a><span data-ttu-id="1d8ca-103">Belangrijkste inzicht in de status van de domein-e-mailstroom in het & compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="1d8ca-103">Top domain mail flow status insight in the Security & Compliance Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="1d8ca-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="1d8ca-104">**Applies to**</span></span>
- [<span data-ttu-id="1d8ca-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="1d8ca-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="1d8ca-106">Microsoft Defender voor Office 365-abonnement 1 en abonnement 2</span><span class="sxs-lookup"><span data-stu-id="1d8ca-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="1d8ca-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1d8ca-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1d8ca-108">Het **belangrijkste inzicht in de status** van de domeinstroomstroom in het dashboard E-mailstroom in het beveiligings- & [compliancecentrum](https://protection.office.com) geeft u de huidige status van de e-mailstroom voor uw organisatie. [](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="1d8ca-108">The **Top domain mail flow status** insight in the [Mail flow dashboard](mail-flow-insights-v2.md) in the [Security & Compliance Center](https://protection.office.com) gives you the current mail flow status for your organization.</span></span>

<span data-ttu-id="1d8ca-109">Met dit inzicht kunt u domeinen identificeren en oplossen die problemen met ***de e-mailstroom*** ondervinden.</span><span class="sxs-lookup"><span data-stu-id="1d8ca-109">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow*** issues.</span></span> <span data-ttu-id="1d8ca-110">Het domein kan bijvoorbeeld geen externe e-mail ontvangen omdat het domein is verlopen of omdat het domein een onjuiste MX-record heeft.</span><span class="sxs-lookup"><span data-stu-id="1d8ca-110">For example, the domain is unable to receive external email because the domain has expired or the domain has an incorrect MX record.</span></span>

![De belangrijkste widget voor de domeinstroomstatus in het dashboard E-mailstroom in het & Compliancecentrum](../../media/mfi-top-domain-mail-flow-status-widget.png)

<span data-ttu-id="1d8ca-112">Wanneer u op **Details weergeven** in de widget klikt, wordt een **flyout** voor de domeinstatus weergegeven met meer details over de status van elk domein:</span><span class="sxs-lookup"><span data-stu-id="1d8ca-112">When you click **View details** in the widget, a **Domain status** flyout appears that shows you more details for the status of each domain:</span></span>

- <span data-ttu-id="1d8ca-113">**Domein**</span><span class="sxs-lookup"><span data-stu-id="1d8ca-113">**Domain**</span></span>
- <span data-ttu-id="1d8ca-114">**Vorige MX-record**</span><span class="sxs-lookup"><span data-stu-id="1d8ca-114">**Previous MX record**</span></span>
- <span data-ttu-id="1d8ca-115">**Huidige MX-record**</span><span class="sxs-lookup"><span data-stu-id="1d8ca-115">**Current MX record**</span></span>
- <span data-ttu-id="1d8ca-116">**Status van e-mail die wordt ontvangen**</span><span class="sxs-lookup"><span data-stu-id="1d8ca-116">**Email receiving status**</span></span>
- <span data-ttu-id="1d8ca-117">**Domeinstatus:** een groen vinkje geeft aan dat de huidige MX-record (op het moment dat u op de widget hebt geklikt) overeenkomt met de waarde die is op registreren en dat het domein de afgelopen twee uur e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1d8ca-117">**Domain status**: A green check mark indicates the current MX record (at the time you clicked on the widget) matches the value we have on record, and the domain has received email during the past two hours.</span></span>

  <span data-ttu-id="1d8ca-118">Een rode X geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="1d8ca-118">A red X indicates the MX record has been changed, and the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="1d8ca-119">Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="1d8ca-119">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="1d8ca-120">Neem contact op met uw domeinregistrar of de DNS-hostingservice om te controleren of het domein is verlopen of dat de MX-record van het domein onjuist is.</span><span class="sxs-lookup"><span data-stu-id="1d8ca-120">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

<span data-ttu-id="1d8ca-121">U kunt op **Meer weergeven** klikken om dezelfde informatie voor meer domeinen weer te geven.</span><span class="sxs-lookup"><span data-stu-id="1d8ca-121">You can click **View more** to see the same information for more domains.</span></span>

![Flyout Details in het statusinzicht van de e-mailstroom van het hoogste domein](../../media/mfi-top-domain-mail-flow-status-view-details.png)

## <a name="see-also"></a><span data-ttu-id="1d8ca-123">Zie ook</span><span class="sxs-lookup"><span data-stu-id="1d8ca-123">See also</span></span>

<span data-ttu-id="1d8ca-124">Zie inzichten in de e-mailstroom in het beveiligings- en compliancecentrum voor meer informatie & [inzichten in het dashboard E-mailstroom.](mail-flow-insights-v2.md)</span><span class="sxs-lookup"><span data-stu-id="1d8ca-124">For information about other insights in the Mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
