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
description: Integreer de SIEM-server van uw organisatie met Microsoft Defender voor Office 365 en gerelateerde bedreigingsgebeurtenissen in de Office 365 Activity Management API.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a456ee970015aea5936ae86ec009cb2ff46e99c2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058494"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM-integratie met Microsoft Defender voor Office 365

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als uw organisatie een SIEM-server (Security Information and Event Management) gebruikt, kunt u Microsoft Defender voor Office 365 integreren met uw SIEM-server. U kunt deze integratie instellen met de [Office 365 Activity Management API.](/office/office-365-management-api/office-365-management-activity-api-reference)

Met SIEM-integratie kunt u informatie, zoals malware of phish gedetecteerd door Microsoft Defender voor Office 365, weergeven in uw SIEM-serverrapporten.

- Zie Tech Community blog: Improve the Effectiveness of your [SOC with Defender for Office 365 and the O365 Management API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185)(De effectiviteit van uw soc verbeteren met Defender voor Office 365 en de O365 Management API) voor een voorbeeld van SIEM-integratie met Microsoft Defender voor Office 365.

- Zie Overzicht van Office 365 Management API's voor meer informatie over de [Office 365 Management-API's.](/office/office-365-management-api/office-365-management-apis-overview)

## <a name="how-siem-integration-works"></a>Hoe SIEM-integratie werkt

De Office 365 Activity Management API haalt informatie over gebruikers-, beheerders-, systeem- en beleidsacties en -gebeurtenissen op uit de activiteitenlogboeken van Microsoft 365 en Azure Active Directory van uw organisatie. Als uw organisatie Microsoft Defender voor Office 365-abonnement 1 of 2 of Office 365 E5 heeft, kunt u het [Microsoft Defender voor Office 365-schema gebruiken.](/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)

Onlangs zijn gebeurtenissen uit geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor [Office 365 Plan 2](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) toegevoegd aan de Office 365 Management Activity API. De API bevat niet alleen gegevens over kernonderzoeksgegevens, zoals id, naam en status, maar bevat ook informatie op hoog niveau over onderzoeksacties en entiteiten.

De SIEM-server of een ander soortgelijk systeem peilt de **audit.general-werkbelasting** om toegang te krijgen tot detectiegebeurtenissen. Zie Aan de slag [met Office 365 Management API's](/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie.

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType - Type: Edm.Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

In de volgende tabel worden de waarden van **AuditLogRecordType** samengevat die relevant zijn voor Microsoft Defender voor Office 365-gebeurtenissen:

|Value|Lidnaam|Beschrijving|
|---|---|---|
|28|ThreatIntelligence|Phishing- en malwaregebeurtenissen van Exchange Online Protection en Microsoft Defender voor Office 365.|
|41|ThreatIntelligenceUrl|Veilige koppelingen time-of-block en blokkeren overschrijven gebeurtenissen van Microsoft Defender voor Office 365.|
|47|ThreatIntelligenceAtpContent|Phishing- en malwaregebeurtenissen voor bestanden in SharePoint Online, OneDrive voor Bedrijven en Microsoft Teams, van Microsoft Defender voor Office 365.|
|64|AirInvestigation|Automatische onderzoeks- en antwoordgebeurtenissen, zoals onderzoeksdetails en relevante artefacten, van Microsoft Defender voor Office 365 Plan 2.|
|

> [!IMPORTANT]
> U moet een globale beheerder zijn of de rol van beveiligingsbeheerder hebben toegewezen voor het Beveiligings- & Compliancecentrum om SIEM-integratie in te stellen met Microsoft Defender voor Office 365.
>
> Auditregistratie moet zijn ingeschakeld voor uw Microsoft 365-omgeving. Zie Zoeken in auditlogboek in- of uitschakelen voor [hulp bij dit alles.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="see-also"></a>Zie ook

[Dreigingsonderzoek en -antwoord in Office 365](office-365-ti.md)

[Automatisch onderzoek en antwoord (AIR) in Office 365](automated-investigation-response-office.md)