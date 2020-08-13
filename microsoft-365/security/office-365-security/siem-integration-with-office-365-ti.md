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
description: Integreer de SIEM-server van uw organisatie met Office 365 Advanced Threat Protection en gerelateerde bedreigingen voor gebeurtenissen in de beheer-API van Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3ed2efd2b59397853623ffcec93e8011793ab43
ms.sourcegitcommit: fa8e488936a36e4b56e1252cb4061b5bd6c0eafc
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/13/2020
ms.locfileid: "46656597"
---
# <a name="siem-integration-with-advanced-threat-protection"></a><span data-ttu-id="3be0c-103">SIEM-integratie met Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3be0c-103">SIEM integration with Advanced Threat Protection</span></span>

<span data-ttu-id="3be0c-104">Als uw organisatie gebruikmaakt van een beveiligingsincident en SIEM server, kunt u Office 365 Advanced Threat Protection integreren met uw SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="3be0c-104">If your organization is using a security incident and event management (SIEM) server, you can integrate Office 365 Advanced Threat Protection with your SIEM server.</span></span> <span data-ttu-id="3be0c-105">Met de integratie van SIEM kunt u informatie weergeven, zoals malware of phishing die is gedetecteerd door Office 365 Advanced Protection, in de SIEM-Server rapporten.</span><span class="sxs-lookup"><span data-stu-id="3be0c-105">SIEM integration enables you to view information, such as malware or phish detected by Office 365 Advanced Protection, in your SIEM server reports.</span></span> <span data-ttu-id="3be0c-106">Voor het instellen van de SIEM-integratie gebruikt u de [API Office 365 activity management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="3be0c-106">To set up SIEM integration, you use the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span>

<span data-ttu-id="3be0c-107">De API Office 365 activity management haalt informatie op over gebruikers-, beheer-, systeem-en beleidsacties en gebeurtenissen uit de logboeken van Microsoft 365 voor bedrijven en Azure Active Directory-activiteiten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3be0c-107">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 for business and Azure Active Directory activity logs.</span></span> <span data-ttu-id="3be0c-108">Het [schema Office 365 Advanced Threat Protection](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) werkt met Advanced Threat Protection, dus als uw organisatie beschikt over het Office 365 Advanced Threat Protection-abonnement 1 of abonnement 2 of Office 365 E5, kunt u dezelfde API gebruiken voor de integratie van de Siem-server.</span><span class="sxs-lookup"><span data-stu-id="3be0c-108">The [Office 365 Advanced Threat Protection schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) works with Advanced Threat Protection, so if your organization has the Office 365 Advanced Threat Protection Plan 1 or Plan 2 or Office 365 E5, you can still use that same API for your SIEM server integration.</span></span>

<span data-ttu-id="3be0c-109">Als onderdeel van onze recente updates hebben we ook gebeurtenissen toegevoegd van automatisch onderzoek en antwoord mogelijkheden in Office 365 ATP-abonnement 2 binnen de Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="3be0c-109">As part of our recent updates, we have also added events from automated investigation and response capabilities in Office 365 ATP Plan 2 within the Office 365 Management Activity API.</span></span> <span data-ttu-id="3be0c-110">Naast gegevens over informatie over het kern onderzoek, zoals ID, naam en status, bevat deze informatie ook op hoog niveau voor onderzoekactiviteiten en-entiteiten.</span><span class="sxs-lookup"><span data-stu-id="3be0c-110">In addition to including data about core investigation details such as ID, name and status, it also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="3be0c-111">De controle op de SIEM-server of een ander soortgelijk systeem moet de controle navragen **. algemeen** verzoek om detectie gebeurtenissen te verkrijgen.</span><span class="sxs-lookup"><span data-stu-id="3be0c-111">The SIEM server or other similar system should poll the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="3be0c-112">Zie [aan de slag met Office 365 Management api's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3be0c-112">To learn more see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> <span data-ttu-id="3be0c-113">Daarnaast zijn de volgende waarden van **AuditLogRecordType** relevant voor Office 365-ATP-gebeurtenissen:</span><span class="sxs-lookup"><span data-stu-id="3be0c-113">In addition, the following values of **AuditLogRecordType** are relevant for Office 365 ATP events:</span></span>

### <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="3be0c-114">Enum: AuditLogRecordType-type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="3be0c-114">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

#### <a name="auditlogrecordtype"></a><span data-ttu-id="3be0c-115">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="3be0c-115">AuditLogRecordType</span></span>

****

|<span data-ttu-id="3be0c-116">Value</span><span class="sxs-lookup"><span data-stu-id="3be0c-116">Value</span></span>|<span data-ttu-id="3be0c-117">Lidnaam</span><span class="sxs-lookup"><span data-stu-id="3be0c-117">Member name</span></span>|<span data-ttu-id="3be0c-118">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="3be0c-118">Description</span></span>|
|---|---|---|
|<span data-ttu-id="3be0c-119">30</span><span class="sxs-lookup"><span data-stu-id="3be0c-119">28</span></span>|<span data-ttu-id="3be0c-120">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="3be0c-120">ThreatIntelligence</span></span>|<span data-ttu-id="3be0c-121">Phishing en malware-gebeurtenissen van Exchange Online Protection en Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3be0c-121">Phishing and malware events from Exchange Online Protection and Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="3be0c-122">41</span><span class="sxs-lookup"><span data-stu-id="3be0c-122">41</span></span>|<span data-ttu-id="3be0c-123">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="3be0c-123">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="3be0c-124">Functie voor veilige koppelingen voor ATP en negeren van gebeurtenissen van Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3be0c-124">ATP Safe Links time-of-block and block override events from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="3be0c-125">47</span><span class="sxs-lookup"><span data-stu-id="3be0c-125">47</span></span>|<span data-ttu-id="3be0c-126">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="3be0c-126">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="3be0c-127">Phishing-en malware-gebeurtenissen voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams van Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3be0c-127">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams from Office 365 Advanced Threat Protection.</span></span>|
|<span data-ttu-id="3be0c-128">64</span><span class="sxs-lookup"><span data-stu-id="3be0c-128">64</span></span>|<span data-ttu-id="3be0c-129">Onderzoek</span><span class="sxs-lookup"><span data-stu-id="3be0c-129">AirInvestigation</span></span>|<span data-ttu-id="3be0c-130">Geautomatiseerd onderzoek en antwoord gebeurtenissen, zoals onderzoek Details en relevante artefacten uit Office 365 Advanced Threat Protection-abonnement 2.</span><span class="sxs-lookup"><span data-stu-id="3be0c-130">Automated investigation and response events, such as investigation details and relevant artifacts from Office 365 Advanced Threat Protection Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="3be0c-131">U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder toegewezen hebben voor de beveiligings & voor de beveiligingsfuncties voor het instellen van SIEM-integratie met Office 365 Advanced Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="3be0c-131">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Office 365 Advanced Threat Protection.</span></span><br/><span data-ttu-id="3be0c-132">U moet de controlelogboekregistratie inschakelen voor uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="3be0c-132">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="3be0c-133">Als u hulp nodig hebt, raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="3be0c-133">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3be0c-134">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="3be0c-134">Related topics</span></span>

[<span data-ttu-id="3be0c-135">Dreigingsonderzoek en -antwoord in Office 365</span><span class="sxs-lookup"><span data-stu-id="3be0c-135">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="3be0c-136">Geautomatiseerd onderzoek en antwoord (lucht) in Office 365</span><span class="sxs-lookup"><span data-stu-id="3be0c-136">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

[<span data-ttu-id="3be0c-137">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="3be0c-137">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)

[<span data-ttu-id="3be0c-138">Slimme rapporten en inzichten in het beveiligings &amp; Conformiteitscentrum</span><span class="sxs-lookup"><span data-stu-id="3be0c-138">Smart reports and insights in the Security &amp; Compliance Center</span></span>](reports-and-insights-in-security-and-compliance.md)

[<span data-ttu-id="3be0c-139">Machtigingen in het beveiligings &amp; Conformiteitscentrum</span><span class="sxs-lookup"><span data-stu-id="3be0c-139">Permissions in the Security &amp; Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
