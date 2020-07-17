---
title: Inzicht in e-mailstroomstatus van hoofddomein
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
description: Beheerders kunnen meer te weten komen over het statusinzicht van de beste domeinmailstroom in het dashboard voor de &-naleving van de e-mailstroom.
ms.openlocfilehash: 22b0f8cefe8baacac682550126de55dcbf880d73
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818589"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="8f95c-103">Inzicht in e-mailstroomstatus van hoofddomein</span><span class="sxs-lookup"><span data-stu-id="8f95c-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="8f95c-104">Het statusinzicht voor de status van de **hoogste domeinmailstroom** geeft u de huidige status voor de domeinen van uw organisatie in termen van e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="8f95c-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="8f95c-105">Met dit inzicht u domeinen identificeren en oplossen die problemen ondervinden die van invloed zijn op ***de e-mailstroom*** (bijvoorbeeld niet in staat om externe e-mail te ontvangen), met name domeinverloop of domeinen met onjuiste MX-records.</span><span class="sxs-lookup"><span data-stu-id="8f95c-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Het inzicht in de status van de hoogste domeinstroom in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="8f95c-107">Wanneer u op **Details weergeven** in het inzicht klikt, verschijnt er een flyout die u meer details geeft voor de status van elk domein.</span><span class="sxs-lookup"><span data-stu-id="8f95c-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="8f95c-108">Een groen vinkje voor een domein geeft aan dat de huidige MX-record (wanneer u naar het dashboard voor e-mailstroomstatistieken hebt gebladerd) overeenkomt met de waarde die we hebben en dat het domein de afgelopen twee uur e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="8f95c-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="8f95c-109">Een rode x voor een domein geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="8f95c-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="8f95c-110">Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="8f95c-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="8f95c-111">Neem contact op met uw domeinregistrar of DNS-hostingservice om te zien of het domein is verlopen of dat de MX-record van het domein onjuist is.</span><span class="sxs-lookup"><span data-stu-id="8f95c-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![De flyout Details in het inzicht in de status van de status van de bovenste domeinstroom](../../media/domain-mail-flow-status-flyout.png)

## <a name="related-topics"></a><span data-ttu-id="8f95c-113">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="8f95c-113">Related topics</span></span>

<span data-ttu-id="8f95c-114">Zie [E-mailstroominzichten in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroominzichten in het dashboard voor e-mailstromen.</span><span class="sxs-lookup"><span data-stu-id="8f95c-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
