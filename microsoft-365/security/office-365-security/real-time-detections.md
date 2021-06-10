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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300123"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="c37c3-103">Bedreigingsverkenner en basisbeginselen van realtime detecties</span><span class="sxs-lookup"><span data-stu-id="c37c3-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="c37c3-104">In dit artikel:</span><span class="sxs-lookup"><span data-stu-id="c37c3-104">In this article:</span></span>

- [<span data-ttu-id="c37c3-105">Verschillen tussen Threat Explorer en Realtime detecties</span><span class="sxs-lookup"><span data-stu-id="c37c3-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="c37c3-106">Vereiste licenties en machtigingen</span><span class="sxs-lookup"><span data-stu-id="c37c3-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="c37c3-107">Dit maakt deel uit van een reeks van drie artikelen over **Threat Explorer (Explorer),** **e-mailbeveiliging** **en** explorer- en **realtimedetecties** (zoals verschillen tussen de hulpprogramma's en machtigingen die nodig zijn om ze te kunnen gebruiken).</span><span class="sxs-lookup"><span data-stu-id="c37c3-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="c37c3-108">De andere twee artikelen in deze reeks zijn [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) en [E-mailbeveiliging met Threat Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="c37c3-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="c37c3-109">In dit artikel wordt uitgelegd wat het verschil is tussen het verkennen van bedreigingen en realtime detecties en de benodigde licenties en machtigingen.</span><span class="sxs-lookup"><span data-stu-id="c37c3-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="c37c3-110">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="c37c3-110">**Applies to**</span></span>
- [<span data-ttu-id="c37c3-111">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="c37c3-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="c37c3-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c37c3-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="c37c3-113">Als uw organisatie [Microsoft Defender](defender-for-office-365.md)voor Office 365 heeft en u de machtigingen [hebt,](#required-licenses-and-permissions)kunt u **Threat Explorer** (explorer) of **realtimedetecties** gebruiken om bedreigingen te detecteren en te corrigeren.</span><span class="sxs-lookup"><span data-stu-id="c37c3-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="c37c3-114">Ga in & **Beveiligingscentrum** naar **Bedreigingsbeheer** en kies **explorer**  of **realtime detecties.**</span><span class="sxs-lookup"><span data-stu-id="c37c3-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="c37c3-115">Met Microsoft Defender voor Office 365 Plan 2 ziet u:</span><span class="sxs-lookup"><span data-stu-id="c37c3-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="c37c3-116">Met Microsoft Defender voor Office 365 plan 1 ziet u:</span><span class="sxs-lookup"><span data-stu-id="c37c3-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Bedreigingsverkenner](../../media/threatmgmt-explorer.png)|![Detecties in realtime](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="c37c3-119">Met deze hulpmiddelen kunt u het volgende doen:</span><span class="sxs-lookup"><span data-stu-id="c37c3-119">With these tools, you can:</span></span>

- <span data-ttu-id="c37c3-120">Bekijk malware die is gedetecteerd door Microsoft 365 beveiligingsfuncties.</span><span class="sxs-lookup"><span data-stu-id="c37c3-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="c37c3-121">Bekijk phishing-URL en klik op vonnisgegevens.</span><span class="sxs-lookup"><span data-stu-id="c37c3-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="c37c3-122">Start een geautomatiseerd onderzoek en antwoordproces vanuit een weergave in Explorer.</span><span class="sxs-lookup"><span data-stu-id="c37c3-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="c37c3-123">Onderzoek schadelijke e-mail en meer.</span><span class="sxs-lookup"><span data-stu-id="c37c3-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="c37c3-124">Zie E-mailbeveiliging [met Threat Explorer voor meer informatie.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="c37c3-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="c37c3-125">Verschillen tussen Threat Explorer en Realtime detecties</span><span class="sxs-lookup"><span data-stu-id="c37c3-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="c37c3-126">*Realtime detecties* is een rapportagehulpmiddel dat beschikbaar is in Defender Office 365 plan 1.</span><span class="sxs-lookup"><span data-stu-id="c37c3-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="c37c3-127">*Threat Explorer* is een hulpprogramma voor het zoeken en herstellen van bedreigingen dat beschikbaar is in Defender Office 365 plan 2.</span><span class="sxs-lookup"><span data-stu-id="c37c3-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="c37c3-128">Met het rapport Realtimedetecties kunt u detecties in realtime bekijken.</span><span class="sxs-lookup"><span data-stu-id="c37c3-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="c37c3-129">Threat Explorer doet dit ook, maar biedt extra details voor een bepaalde aanval, zoals het markeren van aanvalscampagnes, [](automated-investigation-response-office.md)en biedt beveiligingsteams de mogelijkheid om bedreigingen te corrigeren (waaronder het starten van een geautomatiseerd onderzoek en antwoordonderzoek).</span><span class="sxs-lookup"><span data-stu-id="c37c3-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="c37c3-130">Een *weergave Alle e-mail* is beschikbaar in Threat Explorer, maar is niet opgenomen in het rapport Realtimedetecties.</span><span class="sxs-lookup"><span data-stu-id="c37c3-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="c37c3-131">Uitgebreide filtermogelijkheden en herstelacties zijn opgenomen in Threat Explorer.</span><span class="sxs-lookup"><span data-stu-id="c37c3-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="c37c3-132">Zie Microsoft Defender for [Office 365 Service Description: Feature availability across Defender for Office 365 plans voor meer informatie.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="c37c3-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="c37c3-133">Vereiste licenties en machtigingen</span><span class="sxs-lookup"><span data-stu-id="c37c3-133">Required licenses and permissions</span></span>

<span data-ttu-id="c37c3-134">U moet [Microsoft Defender hebben om Office 365](defender-for-office-365.md) explorer of realtime detecties te kunnen gebruiken:</span><span class="sxs-lookup"><span data-stu-id="c37c3-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="c37c3-135">Explorer is echter alleen opgenomen in Defender voor Office 365 Plan 2.</span><span class="sxs-lookup"><span data-stu-id="c37c3-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="c37c3-136">Het realtimedetectierapport is opgenomen in Defender voor Office 365 Plan 1.</span><span class="sxs-lookup"><span data-stu-id="c37c3-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="c37c3-137">Beveiligingsbewerkingsteams moeten licenties toewijzen voor alle gebruikers die moeten worden beveiligd door Defender voor Office 365 en zich ervan bewust zijn dat explorer- en realtimedetecties detectiegegevens weergeven voor gelicentieerde gebruikers.</span><span class="sxs-lookup"><span data-stu-id="c37c3-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="c37c3-138">Als u *Explorer-* of realtimedetecties wilt bekijken en gebruiken, moet u het volgende hebben:</span><span class="sxs-lookup"><span data-stu-id="c37c3-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="c37c3-139">Voor het Beveiligings- & compliancecentrum:</span><span class="sxs-lookup"><span data-stu-id="c37c3-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="c37c3-140">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="c37c3-140">Organization Management</span></span>
  - <span data-ttu-id="c37c3-141">Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory beheercentrum ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="c37c3-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="c37c3-142">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="c37c3-142">Security Reader</span></span>

- <span data-ttu-id="c37c3-143">Voor Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="c37c3-143">For Exchange Online:</span></span>

  - <span data-ttu-id="c37c3-144">Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="c37c3-144">Organization Management</span></span>
  - <span data-ttu-id="c37c3-145">View-Only Organisatiebeheer</span><span class="sxs-lookup"><span data-stu-id="c37c3-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="c37c3-146">View-Only Geadresseerden</span><span class="sxs-lookup"><span data-stu-id="c37c3-146">View-Only Recipients</span></span>
  - <span data-ttu-id="c37c3-147">Compliancebeheer</span><span class="sxs-lookup"><span data-stu-id="c37c3-147">Compliance Management</span></span>

<span data-ttu-id="c37c3-148">Zie de volgende bronnen voor meer informatie over rollen en machtigingen:</span><span class="sxs-lookup"><span data-stu-id="c37c3-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="c37c3-149">Machtigingen in het Beveiligings- en compliancecentrum</span><span class="sxs-lookup"><span data-stu-id="c37c3-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="c37c3-150">Functiemachtigingen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c37c3-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="c37c3-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="c37c3-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="c37c3-152">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="c37c3-152">More information</span></span>
- [<span data-ttu-id="c37c3-153">Threat Explorer verzamelt e-mailgegevens op de pagina e-mailentiteit</span><span class="sxs-lookup"><span data-stu-id="c37c3-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="c37c3-154">Schadelijke e-mail zoeken en onderzoeken die is bezorgd</span><span class="sxs-lookup"><span data-stu-id="c37c3-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="c37c3-155">Schadelijke bestanden weergeven die zijn gedetecteerd in SharePoint Online, OneDrive en Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c37c3-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="c37c3-156">Statusrapport bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="c37c3-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="c37c3-157">Geautomatiseerd onderzoek en antwoord in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c37c3-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)