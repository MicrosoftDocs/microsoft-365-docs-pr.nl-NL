---
title: SIEM-integratie met Microsoft Defender voor Office 365
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: None
search.appverid:
- MET150
- MOE150
ms.assetid: eb56b69b-3170-4086-82cf-ba40a530fa1b
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integreer de SIEM-server van uw organisatie met Microsoft Defender voor Office 365 en gerelateerde bedreigingsgebeurtenissen in de Office 365 Activity Management-API.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f637750a31b5034d2ee1110ab0070fa6abcda49b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290391"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM-integratie met Microsoft Defender voor Office 365

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als uw organisatie een SIEM-server (Security Information and Event Management) gebruikt, kunt u Microsoft Defender voor Office 365 integreren met uw SIEM-server. U kunt deze integratie instellen met behulp van de [Activiteitenbeheer-API van Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference)

Met SIEM-integratie kunt u informatie, zoals malware of phish gedetecteerd door Microsoft Defender voor Office 365, bekijken in uw SIEM-serverrapporten.

- Zie het blog Tech Community voor een voorbeeld van SIEM-integratie met Microsoft Defender voor Office 365: Verbeter de effectiviteit van uw SOC met Defender voor Office 365 en de [O365 Management-API.](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)

- Zie het overzicht van office 365-beheer-API's voor meer informatie over de [Beheer-API's van Office 365.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Hoe SIEM-integratie werkt

De Office 365 Activity Management-API haalt informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op uit de Microsoft 365- en Azure Active Directory-activiteitslogboeken van uw organisatie. Als uw organisatie beschikt over Microsoft Defender voor Office 365-abonnement 1 of 2 of Office 365 E5, kunt u het schema van Microsoft Defender voor [Office 365 gebruiken.](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Onlangs zijn gebeurtenissen uit geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor [Office 365 Abonnement 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) toegevoegd aan de Office 365 Management Activity-API. De API bevat niet alleen gegevens over belangrijke onderzoeksgegevens, zoals id, naam en status, maar bevat ook belangrijke informatie over onderzoekacties en entiteiten.

De SIEM-server of een ander soortgelijk systeem controleert de **audit.general** workload om toegang te krijgen tot detectiegebeurtenissen. Zie Aan de slag [met Office 365-beheer-API's voor](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)meer informatie.

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

De volgende tabel bevat een overzicht van de waarden van **AuditLogRecordType** die relevant zijn voor Microsoft Defender voor Office 365-gebeurtenissen:

|Value|Lidnaam|Beschrijving|
|---|---|---|
|28|ThreatIntelligence|Phishing- en malwaregebeurtenissen van Exchange Online Protection en Microsoft Defender voor Office 365.|
|41|ThreatIntelligenceUrl|Met Veilige koppelingen worden gebeurtenissen van Microsoft Defender voor Office 365 geblokkeerd en geblokkeerd.|
|47|ThreatIntelligenceAtpContent|Phishing- en malwaregebeurtenissen voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams, van Microsoft Defender voor Office 365.|
|64|AirInvestigation|Automatische onderzoeks- en antwoordgebeurtenissen, zoals onderzoeksgegevens en relevante artefacten, van Microsoft Defender voor Office 365-abonnement 2.|
|

> [!IMPORTANT]
> U moet een globale beheerder zijn of de rol van beveiligingsbeheerder hebben toegewezen voor het beveiligings- &-compliancecentrum om SIEM-integratie met Microsoft Defender voor Office 365 in te stellen.
>
> Auditlogregistratie moet zijn ingeschakeld voor uw Microsoft 365-omgeving. Zie Zoeken in auditlogboek in- of uitschakelen voor [hulp bij dit.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Zie ook

[Dreigingsonderzoek en -antwoord in Office 365](office-365-ti.md)

[Automatisch onderzoek en automatisch onderzoek (AIR) in Office 365](automated-investigation-response-office.md)

