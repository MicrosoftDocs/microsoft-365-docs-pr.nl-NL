---
title: Het statusinzicht van de status van de topmailstroom
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
description: Beheerders kunnen meer te weten komen over het inzicht in de status van de domeinmailstroom in het dashboard voor e-mailstroom in het Security & Compliance Center.
ms.openlocfilehash: 42ce0545dad2804829d15572ce6e1f5a0ca6b49f
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42808809"
---
# <a name="top-domain-mail-flow-status-insight"></a><span data-ttu-id="0c619-103">Het statusinzicht van de status van de topmailstroom</span><span class="sxs-lookup"><span data-stu-id="0c619-103">Top domain mail flow status insight</span></span>

<span data-ttu-id="0c619-104">Het inzicht in de status van de **top-domeinmailstroom** geeft u de huidige status voor de domeinen van uw organisatie op het gebied van e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="0c619-104">The **Top domain mail flow status** insight gives you the current status for your organization's domains in terms of mail flow.</span></span> <span data-ttu-id="0c619-105">Met dit inzicht u domeinen identificeren en oplossen die problemen ondervinden met ***e-mailstromen*** (bijvoorbeeld geen externe e-mail kunnen ontvangen), met name domeinvervaldatums of domeinen met onjuiste MX-records.</span><span class="sxs-lookup"><span data-stu-id="0c619-105">This insight helps you identify and troubleshoot domains that are experiencing ***mail flow impacting*** issues (for example, unable to receive external email), especially domain expirations or domains with incorrect MX records.</span></span>

![Het inzicht in de status van de domeinstroom top in het dashboard voor e-mailstroom in het Security & Compliance Center](../../media/domain-mail-flow-status-selected.png)

<span data-ttu-id="0c619-107">Wanneer u op Details in het inzicht **weergeven** klikt, verschijnt er een flyout die u meer details voor de status van elk domein weergeeft.</span><span class="sxs-lookup"><span data-stu-id="0c619-107">When you click **View details** in the insight, a flyout appears that shows you more details for the status of each domain.</span></span>

<span data-ttu-id="0c619-108">Een groen vinkje voor een domein geeft de huidige MX-record aan (wanneer u naar het dashboard met de resultaten van de e-mailstroom hebt gebladerd) komt overeen met de waarde die we hebben geregistreerd en dat het domein de afgelopen twee uur e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0c619-108">A green check mark for a domain indicates the current MX record (when you browsed to the mail flow insights dashboard) matches the value we have on record, and that the domain has received email during the past two hours.</span></span>

<span data-ttu-id="0c619-109">Een rode x voor een domein geeft aan dat de MX-record is gewijzigd en dat het domein de afgelopen 6 uur geen e-mail heeft ontvangen.</span><span class="sxs-lookup"><span data-stu-id="0c619-109">A red x for a domain indicates the MX record has been changed, and that the domain has received no email during the past 6 hours.</span></span> <span data-ttu-id="0c619-110">Dit geeft waarschijnlijk aan dat uw domein is verlopen of dat de MX-record onjuist is bijgewerkt.</span><span class="sxs-lookup"><span data-stu-id="0c619-110">This likely indicates that your domain has expired, or that the MX record has been incorrectly updated.</span></span> <span data-ttu-id="0c619-111">Neem contact op met uw domeinregistrar of DNS-hostingservice om te zien of het domein is verlopen of of de MX-record van het domein onjuist is.</span><span class="sxs-lookup"><span data-stu-id="0c619-111">Check with your domain registrar or DNS hosting service to see if the domain has expired, or if the domain's MX record is incorrect.</span></span>

![De flyout details in het inzicht in de status van de hoogste domeinstroom](../../media/domain-mail-flow-status-flyout.png)

## <a name="see-also"></a><span data-ttu-id="0c619-113">Zie ook</span><span class="sxs-lookup"><span data-stu-id="0c619-113">See also</span></span>

<span data-ttu-id="0c619-114">Zie Inzichten in de [stroomstromen in het Security & Compliance Center](mail-flow-insights-v2.md)voor meer informatie over andere e-mailstroom-inzichten in het dashboard voor e-mailstroom.</span><span class="sxs-lookup"><span data-stu-id="0c619-114">For more information about other mail flow insights in the mail flow dashboard, see [Mail flow insights in the Security & Compliance Center](mail-flow-insights-v2.md).</span></span>
