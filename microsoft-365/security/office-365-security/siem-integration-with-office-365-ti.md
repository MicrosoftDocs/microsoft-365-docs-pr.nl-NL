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
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM-integratie met Advanced Threat Protection

Als uw organisatie een SIEM-server (Security Incident and Event Management) gebruikt, u Office 365 Advanced Threat Protection integreren met uw SIEM-server. Siem-integratie stelt u in staat om informatie, zoals malware of phish gedetecteerd door Office 365 Advanced Protection, weer te geven in uw SIEM-serverrapporten. Als u SIEM-integratie wilt instellen, gebruikt u de [Office 365 Activity Management API.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference) 

De API voor activiteitsbeheer van Office 365 haalt informatie op over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen uit de Microsoft 365 voor Bedrijven- en Azure Active Directory-activiteitslogboeken van uw organisatie. Het [Office 365 Advanced Threat Protection-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) werkt met Advanced Threat Protection, dus als uw organisatie het Office 365 Advanced Threat Protection Plan 1 of Plan 2 of Office 365 E5 heeft, u nog steeds dezelfde API gebruiken voor uw SIEM-serverintegratie. 

Als onderdeel van onze recente updates hebben we ook gebeurtenissen toegevoegd van geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 ATP Plan 2 in de Office 365 Management Activity API. Naast het opnemen van gegevens over kernonderzoeksgegevens zoals ID, naam en status, bevat het ook informatie op hoog niveau over onderzoeksacties en entiteiten.   

De SIEM-server of een ander vergelijkbaar systeem moet de **audit.general-werkbelasting** peilen om toegang te krijgen tot detectiegebeurtenissen. Zie Aan [de slag met Office 365 Management API's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie. Bovendien zijn de volgende waarden van **AuditLogRecordType** relevant voor Office 365 ATP-gebeurtenissen:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Type: Edm.Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

|Value|Lidnaam|Beschrijving|
|:-----|:-----|:-----|
|28|ThreatIntelligence (ThreatIntelligence)|Phishing- en malwaregebeurtenissen van Exchange Online Protection en Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|ATP Safe Links time-of-block en blokkeer gebeurtenissen over schrijven van Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Gebeurtenissen op het gebied van phishing en malware voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams van Office 365 Advanced Threat Protection.|
|64|AirInvestigation (AirInvestigation)|Geautomatiseerde onderzoeks- en reactiegebeurtenissen, zoals onderzoeksdetails en relevante artefacten uit Office 365 Advanced Threat Protection Plan 2.|


> [!IMPORTANT]
> U moet een globale beheerder zijn of de beveiligingsbeheerdersrol hebben toegewezen voor het Security & Compliance Center om SIEM-integratie in te stellen met Office 365 Advanced Threat Protection.<br/>Controlelogboekregistratie moet zijn ingeschakeld voor uw Microsoft 365-omgeving. Zie [Zoeken in het controlelogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)om hulp te krijgen.

## <a name="related-topics"></a>Verwante onderwerpen

[Dreigingsonderzoek en -antwoord in Office 365](office-365-ti.md)

[Geautomatiseerd onderzoek en antwoord (AIR) in Office 365](automated-investigation-response-office.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Slimme rapporten en inzichten &amp; in het Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Machtigingen in het &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
