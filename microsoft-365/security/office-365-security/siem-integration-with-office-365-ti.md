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
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM-integratie met Advanced Threat Protection

Als uw organisatie gebruikmaakt van een beveiligingsincident en SIEM server, kunt u Office 365 Advanced Threat Protection integreren met uw SIEM-server. Met de integratie van SIEM kunt u informatie weergeven, zoals malware of phishing die is gedetecteerd door Office 365 Advanced Protection, in de SIEM-Server rapporten. Voor het instellen van de SIEM-integratie gebruikt u de [API Office 365 activity management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

De API Office 365 activity management haalt informatie op over gebruikers-, beheer-, systeem-en beleidsacties en gebeurtenissen uit de logboeken van Microsoft 365 voor bedrijven en Azure Active Directory-activiteiten van uw organisatie. Het [schema Office 365 Advanced Threat Protection](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema) werkt met Advanced Threat Protection, dus als uw organisatie beschikt over het Office 365 Advanced Threat Protection-abonnement 1 of abonnement 2 of Office 365 E5, kunt u dezelfde API gebruiken voor de integratie van de Siem-server.

Als onderdeel van onze recente updates hebben we ook gebeurtenissen toegevoegd van automatisch onderzoek en antwoord mogelijkheden in Office 365 ATP-abonnement 2 binnen de Office 365 Management Activity API. Naast gegevens over informatie over het kern onderzoek, zoals ID, naam en status, bevat deze informatie ook op hoog niveau voor onderzoekactiviteiten en-entiteiten.

De controle op de SIEM-server of een ander soortgelijk systeem moet de controle navragen **. algemeen** verzoek om detectie gebeurtenissen te verkrijgen. Zie [aan de slag met Office 365 Management api's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie. Daarnaast zijn de volgende waarden van **AuditLogRecordType** relevant voor Office 365-ATP-gebeurtenissen:

### <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-type: EDM. Int32

#### <a name="auditlogrecordtype"></a>AuditLogRecordType

****

|Value|Lidnaam|Beschrijving|
|---|---|---|
|30|ThreatIntelligence|Phishing en malware-gebeurtenissen van Exchange Online Protection en Office 365 Advanced Threat Protection.|
|41|ThreatIntelligenceUrl|Functie voor veilige koppelingen voor ATP en negeren van gebeurtenissen van Office 365 Advanced Threat Protection.|
|47|ThreatIntelligenceAtpContent|Phishing-en malware-gebeurtenissen voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams van Office 365 Advanced Threat Protection.|
|64|Onderzoek|Geautomatiseerd onderzoek en antwoord gebeurtenissen, zoals onderzoek Details en relevante artefacten uit Office 365 Advanced Threat Protection-abonnement 2.|
|

> [!IMPORTANT]
> U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder toegewezen hebben voor de beveiligings & voor de beveiligingsfuncties voor het instellen van SIEM-integratie met Office 365 Advanced Threat Protection.<br/>U moet de controlelogboekregistratie inschakelen voor uw Microsoft 365-omgeving. Als u hulp nodig hebt, raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="related-topics"></a>Verwante onderwerpen

[Dreigingsonderzoek en -antwoord in Office 365](office-365-ti.md)

[Geautomatiseerd onderzoek en antwoord (lucht) in Office 365](automated-investigation-response-office.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Slimme rapporten en inzichten in het beveiligings &amp; Conformiteitscentrum](reports-and-insights-in-security-and-compliance.md)

[Machtigingen in het beveiligings &amp; Conformiteitscentrum](permissions-in-the-security-and-compliance-center.md)
