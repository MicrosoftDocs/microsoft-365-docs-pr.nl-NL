---
title: SIEM-integratie met Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integreer de SIEM-server van uw organisatie met Microsoft Defender voor Office 365 en gerelateerde bedreigingsgebeurtenissen in de Office 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3d6bbacb4a64060ecd03cbb28eee3256f41827e
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929777"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="cf7a0-103">SIEM-integratie met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cf7a0-103">SIEM integration with Microsoft Defender for Office 365</span></span>

<span data-ttu-id="cf7a0-104">**Van toepassing op**</span><span class="sxs-lookup"><span data-stu-id="cf7a0-104">**Applies to**</span></span>
- [<span data-ttu-id="cf7a0-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="cf7a0-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="cf7a0-106">Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="cf7a0-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="cf7a0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cf7a0-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="cf7a0-108">Als uw organisatie een SIEM-server (Security Information and Event Management) gebruikt, kunt u Microsoft Defender voor Office 365 integreren met uw SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-108">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="cf7a0-109">U kunt deze integratie instellen met behulp van de [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="cf7a0-109">You can set up this integration by using the [Office 365 Activity Management API](/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="cf7a0-110">Met SIEM-integratie kunt u informatie, zoals malware of phish die is gedetecteerd door Microsoft Defender voor Office 365, weergeven in uw SIEM-serverrapporten.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-110">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span>

- <span data-ttu-id="cf7a0-111">Zie Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API (Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and [the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)) voor een voorbeeld van SIEM-integratie met Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-111">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="cf7a0-112">Zie voor meer informatie over Office 365 [management-API's Office 365 Overzicht van beheer-API's.](/office/office-365-management-api/office-365-management-apis-overview)</span><span class="sxs-lookup"><span data-stu-id="cf7a0-112">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="cf7a0-113">Hoe SIEM-integratie werkt</span><span class="sxs-lookup"><span data-stu-id="cf7a0-113">How SIEM integration works</span></span>

<span data-ttu-id="cf7a0-114">De Office 365 Activity Management API haalt informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op uit de activiteitenlogboeken van uw organisatie Microsoft 365 en Azure Active Directory activiteitenlogboeken.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-114">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="cf7a0-115">Als uw organisatie Microsoft Defender voor Office 365 plan 1 of 2 of Office 365 E5 heeft, kunt u het Microsoft Defender-schema Office 365 [gebruiken.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)</span><span class="sxs-lookup"><span data-stu-id="cf7a0-115">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>

<span data-ttu-id="cf7a0-116">Onlangs zijn gebeurtenissen uit geautomatiseerde onderzoeks- en antwoordmogelijkheden in [Microsoft Defender voor Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) toegevoegd aan de Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-116">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="cf7a0-117">De API bevat niet alleen gegevens over kernonderzoeksgegevens, zoals id, naam en status, maar bevat ook informatie op hoog niveau over onderzoeksacties en entiteiten.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-117">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="cf7a0-118">De SIEM-server of een ander soortgelijk systeem peilt de **audit.general-werkbelasting** om toegang te krijgen tot detectiegebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-118">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="cf7a0-119">Zie Aan de slag [met Office 365 Management API's voor meer informatie.](/office/office-365-management-api/get-started-with-office-365-management-apis)</span><span class="sxs-lookup"><span data-stu-id="cf7a0-119">To learn more, see [Get started with Office 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="cf7a0-120">Enum: AuditLogRecordType - Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="cf7a0-120">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="cf7a0-121">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="cf7a0-121">AuditLogRecordType</span></span>

<span data-ttu-id="cf7a0-122">In de volgende tabel worden de waarden van **AuditLogRecordType** samengevat die relevant zijn voor Microsoft Defender voor Office 365 gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="cf7a0-122">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="cf7a0-123">Waarde</span><span class="sxs-lookup"><span data-stu-id="cf7a0-123">Value</span></span>|<span data-ttu-id="cf7a0-124">Lidnaam</span><span class="sxs-lookup"><span data-stu-id="cf7a0-124">Member name</span></span>|<span data-ttu-id="cf7a0-125">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="cf7a0-125">Description</span></span>|
|---|---|---|
|<span data-ttu-id="cf7a0-126">28</span><span class="sxs-lookup"><span data-stu-id="cf7a0-126">28</span></span>|<span data-ttu-id="cf7a0-127">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="cf7a0-127">ThreatIntelligence</span></span>|<span data-ttu-id="cf7a0-128">Phishing- en malwaregebeurtenissen van Exchange Online Protection en Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-128">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cf7a0-129">41</span><span class="sxs-lookup"><span data-stu-id="cf7a0-129">41</span></span>|<span data-ttu-id="cf7a0-130">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="cf7a0-130">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="cf7a0-131">Safe Koppelingen time-of-block en blokkeren overschrijven gebeurtenissen van Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-131">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cf7a0-132">47</span><span class="sxs-lookup"><span data-stu-id="cf7a0-132">47</span></span>|<span data-ttu-id="cf7a0-133">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="cf7a0-133">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="cf7a0-134">Phishing- en malwaregebeurtenissen voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams, van Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-134">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="cf7a0-135">64</span><span class="sxs-lookup"><span data-stu-id="cf7a0-135">64</span></span>|<span data-ttu-id="cf7a0-136">AirInvestigation</span><span class="sxs-lookup"><span data-stu-id="cf7a0-136">AirInvestigation</span></span>|<span data-ttu-id="cf7a0-137">Automatische onderzoeks- en antwoordgebeurtenissen, zoals onderzoeksdetails en relevante artefacten, van Microsoft Defender voor Office 365 plan 2.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-137">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="cf7a0-138">U moet een globale beheerder zijn of de rol van beveiligingsbeheerder hebben toegewezen voor de Microsoft 365 Defender-portal om SIEM-integratie met Microsoft Defender in te stellen voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-138">You must be a global administrator or have the security administrator role assigned for the Microsoft 365 Defender portal to set up SIEM integration with Microsoft Defender for Office 365.</span></span>
>
> <span data-ttu-id="cf7a0-139">Auditregistratie moet zijn ingeschakeld voor uw Microsoft 365 omgeving.</span><span class="sxs-lookup"><span data-stu-id="cf7a0-139">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="cf7a0-140">Zie Zoeken in auditlogboek in- of uitschakelen voor [hulp bij dit alles.](../../compliance/turn-audit-log-search-on-or-off.md)</span><span class="sxs-lookup"><span data-stu-id="cf7a0-140">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="cf7a0-141">Zie ook</span><span class="sxs-lookup"><span data-stu-id="cf7a0-141">See also</span></span>

[<span data-ttu-id="cf7a0-142">Dreigingsonderzoek en -antwoord in Office 365</span><span class="sxs-lookup"><span data-stu-id="cf7a0-142">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="cf7a0-143">Automatisch onderzoek en antwoord (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="cf7a0-143">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)