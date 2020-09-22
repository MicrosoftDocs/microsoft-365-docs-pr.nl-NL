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
ms.date: 08/21/2020
ms.collection:
- M365-security-compliance
description: Integreer de SIEM-server van uw organisatie met Office 365 Advanced Threat Protection en gerelateerde bedreigingen voor gebeurtenissen in de beheer-API van Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cfb76485fec8eca2f2b62da59fa2d18a56177bba
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48203647"
---
# <a name="siem-integration-with-advanced-threat-protection"></a>SIEM-integratie met Advanced Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als uw organisatie gebruikmaakt van een beveiligingsincident en SIEM server, kunt u Office 365 Advanced Threat Protection (Office 365 ATP) integreren met uw SIEM-server. U kunt deze integratie instellen met de [API Office 365 activity management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference). 

Met de integratie van SIEM kunt u informatie weergeven, zoals malware of phishing die is gedetecteerd door Office 365 ATP, in de SIEM-Server rapporten. 

- Als u een voorbeeld wilt bekijken van de integratie van SIEM met Office 365 ATP, raadpleegt u [de tech Community-Blog: de effectiviteit van uw Soc verbeteren met office 365 ATP en de O365-beheer API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Zie voor meer informatie over de Office 365-beheer-Api's [overzicht van office 365 Management-api's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>De werking van SIEM-integratie

De API Office 365 activity management haalt informatie op over gebruikers-, beheer-, systeem-en beleidsacties en gebeurtenissen uit de logboeken van Microsoft 365 en Azure Active Directory-activiteiten van uw organisatie. Als uw organisatie Office 365 ATP, abonnement 1 of 2 of Office 365 E5 heeft, kunt u gebruikmaken van het [office 365 ATP-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema).  

Onlangs werden gebeurtenissen van geautomatiseerde onderzoek-en antwoord mogelijkheden in [Office 365 ATP-abonnement 2](office-365-atp.md#office-365-atp-plan-1-and-plan-2) toegevoegd aan de Office 365 Management Activity API. Naast gegevens over informatie over het kern onderzoek, zoals ID, naam en status, bevat de API ook hoog-niveau informatie over onderzoeks-en entiteits activiteiten.

De controle op de SIEM-server of een ander soortgelijk systeem controleert de **audit. General** -werklast voor toegang tot detectie gebeurtenissen. Zie aan de [slag met Office 365 Management api's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie. 


## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-type: EDM. Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

De volgende tabel bevat een overzicht van de waarden van **AuditLogRecordType** die relevant zijn voor Office 365 ATP-gebeurtenissen:

|Value|Lidnaam|Beschrijving|
|---|---|---|
|30|ThreatIntelligence|Phishing en malware van gebeurtenissen via Exchange Online Protection en Office 365 ATP.|
|41|ThreatIntelligenceUrl|Voor veilige koppelingen voor ATP en gebeurtenissen negeren in Office 365 ATP.|
|47|ThreatIntelligenceAtpContent|Phishing en malware-gebeurtenissen voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams in Office 365 ATP.|
|64|Onderzoek|Geautomatiseerd onderzoek en antwoord gebeurtenissen, zoals onderzoek Details en relevante artefacten, uit Office 365 ATP-abonnement 2.|
|

> [!IMPORTANT]
> U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder toegewezen hebben voor de beveiligings & voor de beveiligingsfuncties voor het instellen van SIEM-integratie met Office 365 Advanced Threat Protection.<br/>U moet de controlelogboekregistratie inschakelen voor uw Microsoft 365-omgeving. Als u hulp nodig hebt, raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Zie ook

[Dreigingsonderzoek en -antwoord in Office 365](office-365-ti.md)

[Geautomatiseerd onderzoek en antwoord (lucht) in Office 365](automated-investigation-response-office.md)


