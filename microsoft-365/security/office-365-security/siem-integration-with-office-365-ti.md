---
title: SIEM-integratie met Advanced Threat Protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 11/22/2019
ms.collection:
- M365-security-compliance
description: Integreer de SIEM-server van uw organisatie met Geavanceerde bedreigingsbeveiliging van Office 365 en gerelateerde bedreigingsgebeurtenissen in de API voor activiteitsbeheer van Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0527a998e7049960df840c7756ef5deaafaf5ade
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035270"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="12927-103">SIEM-integratie met Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12927-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="12927-104">Als uw organisatie een SIEM-server (Security Incident and Event Management) gebruikt, u Office 365 Advanced Threat Protection integreren met uw SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="12927-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="12927-105">Siem-integratie stelt u in staat om informatie, zoals malware of phish gedetecteerd door Office 365 Advanced Protection, weer te geven in uw SIEM-serverrapporten.</span><span class="sxs-lookup"><span data-stu-id="12927-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="12927-106">Als u SIEM-integratie wilt instellen, gebruikt u de [Office 365 Activity Management API.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)</span><span class="sxs-lookup"><span data-stu-id="12927-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="12927-107">De API voor activiteitsbeheer van Office 365 haalt informatie op over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit de Microsoft 365 voor Bedrijven- en Azure Active Directory-activiteitslogboeken van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="12927-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="12927-108">Het [Office 365 Advanced Threat Protection-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) werkt met Advanced Threat Protection, dus als uw organisatie het Office 365 Advanced Threat Protection Plan 1 of Plan 2 of Office 365 E5 heeft, u nog steeds dezelfde API gebruiken voor uw SIEM-serverintegratie.</span><span class="sxs-lookup"><span data-stu-id="12927-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span> 

<span data-ttu-id="12927-109">Als onderdeel van onze recente updates hebben we ook gebeurtenissen toegevoegd van geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 ATP Plan 2 in de Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="12927-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="12927-110">Naast het opnemen van gegevens over kernonderzoeksgegevens zoals ID, naam en status, bevat het ook informatie op hoog niveau over onderzoeksacties en entiteiten.</span><span class="sxs-lookup"><span data-stu-id="12927-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>   

<span data-ttu-id="12927-111">De SIEM-server of een ander vergelijkbaar systeem moet de **audit.general-werkbelasting** peilen om toegang te krijgen tot detectiegebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="12927-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="12927-112">Zie Aan [de slag met Office 365 Management API's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="12927-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="12927-113">Bovendien zijn de volgende waarden van **AuditLogRecordType** relevant voor Office 365 ATP-gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="12927-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="12927-114">Enum: AuditLogRecordType - Type: Edm.Int32</span><span class="sxs-lookup"><span data-stu-id="12927-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="12927-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="12927-115">AuditLogRecordType</span></span>

|<span data-ttu-id="12927-116">Value</span><span class="sxs-lookup"><span data-stu-id="12927-116">Value</span></span>|<span data-ttu-id="12927-117">Lidnaam</span><span class="sxs-lookup"><span data-stu-id="12927-117">Member name</span></span>|<span data-ttu-id="12927-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="12927-118">Description</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="12927-119">28</span><span class="sxs-lookup"><span data-stu-id="12927-119">28</span></span>|<span data-ttu-id="12927-120">ThreatIntelligence (ThreatIntelligence)</span><span class="sxs-lookup"><span data-stu-id="12927-120">ThreatIntelligence</span></span>|<span data-ttu-id="12927-121">Phishing- en malwaregebeurtenissen van Exchange Online Protection en Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="12927-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="12927-122">41</span><span class="sxs-lookup"><span data-stu-id="12927-122">41</span></span>|<span data-ttu-id="12927-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="12927-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="12927-124">ATP Safe Links time-of-block en blokkeer gebeurtenissen over schrijven van Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="12927-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="12927-125">47</span><span class="sxs-lookup"><span data-stu-id="12927-125">47</span></span>|<span data-ttu-id="12927-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="12927-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="12927-127">Gebeurtenissen op het gebied van phishing en malware voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams van Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="12927-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="12927-128">64</span><span class="sxs-lookup"><span data-stu-id="12927-128">64</span></span>|<span data-ttu-id="12927-129">AirInvestigation (AirInvestigation)</span><span class="sxs-lookup"><span data-stu-id="12927-129">AirInvestigation</span></span>|<span data-ttu-id="12927-130">Geautomatiseerde onderzoeks- en reactiegebeurtenissen, zoals onderzoeksdetails en relevante artefacten uit Office 365 Advanced Threat Protection Plan 2.</span><span class="sxs-lookup"><span data-stu-id="12927-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|


> [!IMPORTANT]
> <span data-ttu-id="12927-131">U moet een globale beheerder zijn of de beveiligingsbeheerdersrol hebben toegewezen voor het Security & Compliance Center om SIEM-integratie in te stellen met Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="12927-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="12927-132">Controlelogboekregistratie moet zijn ingeschakeld voor uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="12927-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="12927-133">Zie [Zoeken in het controlelogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)om hulp te krijgen.</span><span class="sxs-lookup"><span data-stu-id="12927-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="12927-134">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="12927-134">Related topics</span></span>

[<span data-ttu-id="12927-135">Dreigingsonderzoek en -antwoord in Office 365</span><span class="sxs-lookup"><span data-stu-id="12927-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="12927-136">Geautomatiseerd onderzoek en antwoord (AIR) in Office 365</span><span class="sxs-lookup"><span data-stu-id="12927-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="12927-137">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="12927-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="12927-138">Slimme rapporten en inzichten &amp; in het Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="12927-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)
  
[<span data-ttu-id="12927-139">Machtigingen in het &amp; Security Compliance Center</span><span class="sxs-lookup"><span data-stu-id="12927-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
  
