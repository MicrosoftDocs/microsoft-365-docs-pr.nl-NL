---
title: SIEM-integratie met Microsoft Defender voor Office 365
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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integreer de SIEM-server van uw organisatie met Microsoft Defender for Office 365 en gerelateerde bedreigingen gebeurtenissen in de beheer-API van Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 185e6e816cfff4131d7b5af11c4e3ea9cf94b338
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48843574"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a><span data-ttu-id="2e6c1-103">SIEM-integratie met Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="2e6c1-103">SIEM integration with Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="2e6c1-104">Als in uw organisatie een server voor beveiliging en Gebeurtenissenbeheer (SIEM) wordt gebruikt, kunt u Microsoft Defender voor Office 365 integreren met uw SIEM-server.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-104">If your organization is using a security information and event management (SIEM) server, you can integrate Microsoft Defender for Office 365 with your SIEM server.</span></span> <span data-ttu-id="2e6c1-105">U kunt deze integratie instellen met de [API Office 365 activity management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span><span class="sxs-lookup"><span data-stu-id="2e6c1-105">You can set up this integration by using the [Office 365 Activity Management API](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).</span></span> 

<span data-ttu-id="2e6c1-106">Met de integratie van SIEM kunt u informatie weergeven, zoals malware of phishing die is gedetecteerd door Microsoft Defender for Office 365, in de SIEM-Server rapporten.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-106">SIEM integration enables you to view information, such as malware or phish detected by Microsoft Defender for Office 365, in your SIEM server reports.</span></span> 

- <span data-ttu-id="2e6c1-107">Als u een voorbeeld wilt bekijken van de integratie van SIEM met Microsoft Defender for Office 365, raadpleegt u [de tech Community-Blog: Verbeter de effectiviteit van uw Soc met Defender voor Office 365 en de O365-beheer-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span><span class="sxs-lookup"><span data-stu-id="2e6c1-107">To see an example of SIEM integration with Microsoft Defender for Office 365, see [Tech Community blog: Improve the Effectiveness of your SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).</span></span>

- <span data-ttu-id="2e6c1-108">Zie voor meer informatie over de Office 365-beheer-Api's [overzicht van office 365 Management-api's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span><span class="sxs-lookup"><span data-stu-id="2e6c1-108">To learn more about the Office 365 Management APIs, see [Office 365 Management APIs overview](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).</span></span>

## <a name="how-siem-integration-works"></a><span data-ttu-id="2e6c1-109">De werking van SIEM-integratie</span><span class="sxs-lookup"><span data-stu-id="2e6c1-109">How SIEM integration works</span></span>

<span data-ttu-id="2e6c1-110">De API Office 365 activity management haalt informatie op over gebruikers-, beheer-, systeem-en beleidsacties en gebeurtenissen uit de logboeken van Microsoft 365 en Azure Active Directory-activiteiten van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-110">The Office 365 Activity Management API retrieves information about user, admin, system, and policy actions and events from your organization's Microsoft 365 and Azure Active Directory activity logs.</span></span> <span data-ttu-id="2e6c1-111">Als uw organisatie Microsoft Defender voor Office 365 (abonnement 1) of 2, of Office 365 E5 bevat, kunt u het [Microsoft Defender for office 365-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-111">If your organization has Microsoft Defender for Office 365 Plan 1 or 2, or Office 365 E5, you can use the [Microsoft Defender for Office 365 schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).</span></span>  

<span data-ttu-id="2e6c1-112">Onlangs werden gebeurtenissen van geautomatiseerde onderzoek-en antwoord mogelijkheden in [Microsoft Defender voor Office 365-abonnement 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) toegevoegd aan de Office 365 Management Activity API.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-112">Recently, events from automated investigation and response capabilities in [Microsoft Defender for Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) were added to the Office 365 Management Activity API.</span></span> <span data-ttu-id="2e6c1-113">Naast gegevens over informatie over het kern onderzoek, zoals ID, naam en status, bevat de API ook hoog-niveau informatie over onderzoeks-en entiteits activiteiten.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-113">In addition to including data about core investigation details such as ID, name and status, the API also contains high-level information about investigation actions and entities.</span></span>

<span data-ttu-id="2e6c1-114">De controle op de SIEM-server of een ander soortgelijk systeem controleert de **audit. General** -werklast voor toegang tot detectie gebeurtenissen.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-114">The SIEM server or other similar system polls the **audit.general** workload to access detection events.</span></span> <span data-ttu-id="2e6c1-115">Zie aan de [slag met Office 365 Management api's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-115">To learn more, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span> 

## <a name="enum-auditlogrecordtype---type-edmint32"></a><span data-ttu-id="2e6c1-116">Enum: AuditLogRecordType-type: EDM. Int32</span><span class="sxs-lookup"><span data-stu-id="2e6c1-116">Enum: AuditLogRecordType - Type: Edm.Int32</span></span>

### <a name="auditlogrecordtype"></a><span data-ttu-id="2e6c1-117">AuditLogRecordType</span><span class="sxs-lookup"><span data-stu-id="2e6c1-117">AuditLogRecordType</span></span>

<span data-ttu-id="2e6c1-118">De volgende tabel bevat een overzicht van de waarden van **AuditLogRecordType** die relevant zijn voor gebeurtenissen van Microsoft Defender for Office 365:</span><span class="sxs-lookup"><span data-stu-id="2e6c1-118">The following table summarizes the values of **AuditLogRecordType** that are relevant for Microsoft Defender for Office 365 events:</span></span>

|<span data-ttu-id="2e6c1-119">Waarde</span><span class="sxs-lookup"><span data-stu-id="2e6c1-119">Value</span></span>|<span data-ttu-id="2e6c1-120">Lidnaam</span><span class="sxs-lookup"><span data-stu-id="2e6c1-120">Member name</span></span>|<span data-ttu-id="2e6c1-121">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="2e6c1-121">Description</span></span>|
|---|---|---|
|<span data-ttu-id="2e6c1-122">30</span><span class="sxs-lookup"><span data-stu-id="2e6c1-122">28</span></span>|<span data-ttu-id="2e6c1-123">ThreatIntelligence</span><span class="sxs-lookup"><span data-stu-id="2e6c1-123">ThreatIntelligence</span></span>|<span data-ttu-id="2e6c1-124">Phishing en malware van gebeurtenissen via Exchange Online Protection en Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-124">Phishing and malware events from Exchange Online Protection and Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2e6c1-125">41</span><span class="sxs-lookup"><span data-stu-id="2e6c1-125">41</span></span>|<span data-ttu-id="2e6c1-126">ThreatIntelligenceUrl</span><span class="sxs-lookup"><span data-stu-id="2e6c1-126">ThreatIntelligenceUrl</span></span>|<span data-ttu-id="2e6c1-127">Veilige koppelingen de time-out van het blokkeren en negeren van gebeurtenissen in Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-127">Safe Links time-of-block and block override events from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2e6c1-128">47</span><span class="sxs-lookup"><span data-stu-id="2e6c1-128">47</span></span>|<span data-ttu-id="2e6c1-129">ThreatIntelligenceAtpContent</span><span class="sxs-lookup"><span data-stu-id="2e6c1-129">ThreatIntelligenceAtpContent</span></span>|<span data-ttu-id="2e6c1-130">Phishing en malware-gebeurtenissen voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams, van Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-130">Phishing and malware events for files in SharePoint Online, OneDrive for Business, and Microsoft Teams, from Microsoft Defender for Office 365.</span></span>|
|<span data-ttu-id="2e6c1-131">64</span><span class="sxs-lookup"><span data-stu-id="2e6c1-131">64</span></span>|<span data-ttu-id="2e6c1-132">Onderzoek</span><span class="sxs-lookup"><span data-stu-id="2e6c1-132">AirInvestigation</span></span>|<span data-ttu-id="2e6c1-133">Geautomatiseerd onderzoek en antwoord gebeurtenissen, zoals onderzoek Details en relevante artefacten, uit Microsoft Defender voor Office 365, abonnement 2.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-133">Automated investigation and response events, such as investigation details and relevant artifacts, from Microsoft Defender for Office 365 Plan 2.</span></span>|
|

> [!IMPORTANT]
> <span data-ttu-id="2e6c1-134">U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder toegewezen hebben voor de beveiligings & voor nalevings centrum voor het instellen van SIEM-integratie met Microsoft Defender voor Office 365.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-134">You must be a global administrator or have the security administrator role assigned for the Security & Compliance Center to set up SIEM integration with Microsoft Defender for Office 365.</span></span><br/><span data-ttu-id="2e6c1-135">U moet de controlelogboekregistratie inschakelen voor uw Microsoft 365-omgeving.</span><span class="sxs-lookup"><span data-stu-id="2e6c1-135">Audit logging must be turned on for your Microsoft 365 environment.</span></span> <span data-ttu-id="2e6c1-136">Als u hulp nodig hebt, raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).</span><span class="sxs-lookup"><span data-stu-id="2e6c1-136">To get help with this, see [Turn audit log search on or off](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2e6c1-137">Zie ook</span><span class="sxs-lookup"><span data-stu-id="2e6c1-137">See also</span></span>

[<span data-ttu-id="2e6c1-138">Dreigingsonderzoek en -antwoord in Office 365</span><span class="sxs-lookup"><span data-stu-id="2e6c1-138">Office 365 threat investigation and response</span></span>](office-365-ti.md)

[<span data-ttu-id="2e6c1-139">Geautomatiseerd onderzoek en antwoord (lucht) in Office 365</span><span class="sxs-lookup"><span data-stu-id="2e6c1-139">Automated investigation and response (AIR) in Office 365</span></span>](automated-investigation-response-office.md)

