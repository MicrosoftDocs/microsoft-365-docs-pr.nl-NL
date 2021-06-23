---
title: Basisbeginselen voor bedreigingsverkenner en realtimedetectie in Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Gebruik Explorer- of realtimedetecties om bedreigingen efficiënt te onderzoeken en te beantwoorden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083186"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="f0c55-103">Basisprincipes van Explorer- en realtimedetecties</span><span class="sxs-lookup"><span data-stu-id="f0c55-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="f0c55-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="f0c55-104">**Applies to**</span></span>
- [<span data-ttu-id="f0c55-105">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="f0c55-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="f0c55-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f0c55-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="f0c55-107">In dit artikel:</span><span class="sxs-lookup"><span data-stu-id="f0c55-107">In this article:</span></span>

- [<span data-ttu-id="f0c55-108">Verschillen tussen Explorer- en realtimedetecties</span><span class="sxs-lookup"><span data-stu-id="f0c55-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="f0c55-109">Vereiste licenties en machtigingen</span><span class="sxs-lookup"><span data-stu-id="f0c55-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="f0c55-110">Dit maakt deel uit van een reeks van drie artikelen over **Verkenner (ook** wel Threat Explorer genoemd), **e-mailbeveiliging** **en** basisprincipes van Explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken).</span><span class="sxs-lookup"><span data-stu-id="f0c55-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="f0c55-111">De andere twee artikelen in deze reeks zijn [Bedreigingsjacht in Verkenner](threat-hunting-in-threat-explorer.md) en [E-mailbeveiliging met Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="f0c55-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="f0c55-112">In dit artikel wordt uitgelegd wat het verschil is tussen Explorer- en realtimedetectierapportage en de benodigde licenties en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="f0c55-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="f0c55-113">Als uw organisatie [Microsoft Defender](defender-for-office-365.md)voor Office 365 heeft en u de machtigingen [hebt,](#required-licenses-and-permissions)kunt u **Explorer** (ook wel **Threat Explorer** genoemd) of **realtimedetecties** gebruiken om bedreigingen te detecteren en te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="f0c55-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="f0c55-114">Ga in Microsoft 365 Defender portal ( ) naar E-mail & samenwerking en kies explorer of <https://security.microsoft.com>   **realtime detecties.** </span><span class="sxs-lookup"><span data-stu-id="f0c55-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="f0c55-115">Met deze hulpmiddelen kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="f0c55-115">With these tools, you can:</span></span>

- <span data-ttu-id="f0c55-116">Bekijk malware die is gedetecteerd door Microsoft 365 beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="f0c55-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="f0c55-117">Bekijk phishing-URL en klik op vonnisgegevens.</span><span class="sxs-lookup"><span data-stu-id="f0c55-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="f0c55-118">Start een geautomatiseerd onderzoek en antwoordproces vanuit een weergave in Explorer.</span><span class="sxs-lookup"><span data-stu-id="f0c55-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="f0c55-119">Onderzoek schadelijke e-mail en meer.</span><span class="sxs-lookup"><span data-stu-id="f0c55-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="f0c55-120">Zie E-mailbeveiliging [met Explorer voor meer informatie.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="f0c55-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="f0c55-121">Verschillen tussen Explorer- en realtimedetecties</span><span class="sxs-lookup"><span data-stu-id="f0c55-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="f0c55-122">*Realtime detecties* is een rapportagehulpmiddel dat beschikbaar is in Defender Office 365 plan 1.</span><span class="sxs-lookup"><span data-stu-id="f0c55-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="f0c55-123">*Threat Explorer* is een hulpprogramma voor het zoeken en herstellen van bedreigingen dat beschikbaar is in Defender Office 365 plan 2.</span><span class="sxs-lookup"><span data-stu-id="f0c55-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="f0c55-124">Met het rapport Realtimedetecties kunt u detecties in realtime bekijken.</span><span class="sxs-lookup"><span data-stu-id="f0c55-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="f0c55-125">Threat Explorer doet dit ook, maar biedt extra details voor een bepaalde aanval, zoals het markeren van aanvalscampagnes, [](automated-investigation-response-office.md)en biedt beveiligingsteams de mogelijkheid om bedreigingen te corrigeren (waaronder het starten van een geautomatiseerd onderzoek en antwoordonderzoek).</span><span class="sxs-lookup"><span data-stu-id="f0c55-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="f0c55-126">Een *weergave Alle e-mail* is beschikbaar in Threat Explorer, maar is niet opgenomen in het rapport Realtimedetecties.</span><span class="sxs-lookup"><span data-stu-id="f0c55-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="f0c55-127">Uitgebreide filtermogelijkheden en herstelacties zijn opgenomen in Threat Explorer.</span><span class="sxs-lookup"><span data-stu-id="f0c55-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="f0c55-128">Zie Microsoft Defender for [Office 365 Service Description: Feature availability across Defender for Office 365 plans voor meer informatie.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="f0c55-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="f0c55-129">Vereiste licenties en machtigingen</span><span class="sxs-lookup"><span data-stu-id="f0c55-129">Required licenses and permissions</span></span>

<span data-ttu-id="f0c55-130">U moet [Microsoft Defender hebben om Office 365](defender-for-office-365.md) explorer of realtime detecties te kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="f0c55-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="f0c55-131">Explorer is alleen opgenomen in Defender voor Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="f0c55-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="f0c55-132">Het realtimedetectierapport is opgenomen in Defender voor Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="f0c55-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="f0c55-133">Beveiligingsbewerkingsteams moeten licenties toewijzen voor alle gebruikers die moeten worden beveiligd door Defender voor Office 365 en zich ervan bewust zijn dat explorer- en realtimedetecties detectiegegevens weergeven voor gelicentieerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="f0c55-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="f0c55-134">Als u *Explorer-* of realtimedetecties wilt bekijken en gebruiken, hebt u de volgende machtigingen nodig:</span><span class="sxs-lookup"><span data-stu-id="f0c55-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="f0c55-135">In Defender voor Office 365:</span><span class="sxs-lookup"><span data-stu-id="f0c55-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="f0c55-136">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="f0c55-136">Organization Management</span></span>
  - <span data-ttu-id="f0c55-137">Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory beheercentrum ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="f0c55-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="f0c55-138">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="f0c55-138">Security Reader</span></span>
- <span data-ttu-id="f0c55-139">In Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="f0c55-139">In Exchange Online:</span></span>
  - <span data-ttu-id="f0c55-140">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="f0c55-140">Organization Management</span></span>
  - <span data-ttu-id="f0c55-141">View-Only Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="f0c55-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="f0c55-142">View-Only Geadresseerden</span><span class="sxs-lookup"><span data-stu-id="f0c55-142">View-Only Recipients</span></span>
  - <span data-ttu-id="f0c55-143">Compliancebeheer</span><span class="sxs-lookup"><span data-stu-id="f0c55-143">Compliance Management</span></span>

<span data-ttu-id="f0c55-144">Zie de volgende artikelen voor meer informatie over rollen en machtigingen:</span><span class="sxs-lookup"><span data-stu-id="f0c55-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="f0c55-145">Machtigingen in de Microsoft 365 Defender-portal</span><span class="sxs-lookup"><span data-stu-id="f0c55-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="f0c55-146">Machtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="f0c55-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="f0c55-147">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="f0c55-147">More information</span></span>

- [<span data-ttu-id="f0c55-148">Threat Explorer verzamelt e-mailgegevens op de pagina e-mailentiteit</span><span class="sxs-lookup"><span data-stu-id="f0c55-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="f0c55-149">Schadelijke e-mail zoeken en onderzoeken die is bezorgd</span><span class="sxs-lookup"><span data-stu-id="f0c55-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="f0c55-150">Schadelijke bestanden weergeven die zijn gedetecteerd in SharePoint Online, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f0c55-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="f0c55-151">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="f0c55-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="f0c55-152">Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f0c55-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
