---
title: SIEM-integratie met geavanceerde bedreigingsbeveiliging van Office 365
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
description: Integreer de SIEM-server van uw organisatie met Office 365 Advanced Threat Protection en gerelateerde bedreigingsgebeurtenissen in de Office 365 Activity Management API.
ms.openlocfilehash: 8a870e02a37ea7f4961d0b8dc42a49cb59d2bace
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42811323"
---
# <a name="siem-integration-with-office-365-advanced-threat-protection"></a>SIEM-integratie met geavanceerde bedreigingsbeveiliging van Office 365

Als uw organisatie een SIEM-server (Security Incident and Event Management) gebruikt, u Office 365 Advanced Threat Protection integreren met uw SIEM-server. Siem-integratie stelt u in staat om informatie, zoals malware of phish gedetecteerd door Office 365 Advanced Protection, te bekijken in uw SIEM-serverrapporten. Als u SIEM-integratie wilt instellen, gebruikt u de [API voor activiteitenbeheer van Office 365](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

De OFFICE 365 Activity Management API haalt informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op uit de activiteitenlogboeken office 365 en Azure Active Directory van uw organisatie. Het [Office 365 Advanced Threat Protection-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) werkt met Advanced Threat Protection, dus als uw organisatie het Office 365 Advanced Threat Protection Plan 1 of Plan 2 of Office 365 E5 heeft, u nog steeds dezelfde API gebruiken voor uw SIEM-serverintegratie. 

Als onderdeel van onze recente updates hebben we ook gebeurtenissen van geautomatiseerde onderzoeks- en responsmogelijkheden toegevoegd in Office 365 ATP Plan 2 in de Office 365 Management Activity API. Naast het opnemen van gegevens over kernonderzoeksgegevens zoals ID, naam en status, bevat het ook informatie op hoog niveau over onderzoeksacties en entiteiten.   

De SIEM-server of een ander vergelijkbaar systeem moet de **audit.algemene** werkbelasting peilen om toegang te krijgen tot detectiegebeurtenissen. Zie Aan de [slag met De API's voor Office 365 Management](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis). Daarnaast zijn de volgende waarden van **AuditLogRecordType** relevant voor Office 365 ATP-gebeurtenissen:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Type: Edm.Int32

#### <a name="auditlogrecordtype"></a>ControleLogRecordType

|Value|Lidnaam|Beschrijving|
|:-----|:-----|:-----|
|28|ThreatIntelligence|Phishing- en malwaregebeurtenissen van Exchange Online Protection en Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|ATP Safe Links time-of-block en block override gebeurtenissen van Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Gebeurtenissen in phishing en malware voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams vanuit Geavanceerde bedreigingsbeveiliging van Office 365.|
|64|Luchtonderzoek|Geautomatiseerde onderzoeks- en reactiegebeurtenissen, zoals onderzoeksgegevens en relevante artefacten uit Office 365 Advanced Threat Protection Plan 2.|


> [!IMPORTANT]
> U moet een globale beheerder van Office 365 zijn of de rol van beveiligingsbeheerder hebben toegewezen voor het Security & Compliance Center om SIEM-integratie in te stellen met Office 365 Advanced Threat Protection.<br/>Controlelogboekregistratie moet zijn ingeschakeld voor uw Office 365-omgeving. Zie Zoeken in [of uit voor office 365-controlelogboeken in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor hulp bij deze hulp.

## <a name="related-topics"></a>Verwante onderwerpen

[Onderzoek en reactie van office 365-dreiging](office-365-ti.md)

[Geautomatiseerd onderzoek en respons (AIR) in Office 365](automated-investigation-response-office.md)

[Geavanceerde bedreigingsbeveiliging van Office 365](office-365-atp.md)

[Slimme rapporten en inzichten in het &amp; Office 365 Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Permissions in the Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
  
