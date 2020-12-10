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
ms.openlocfilehash: 93ff1606130c60ceb46087d28bb26f9a6d27d330
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615658"
---
# <a name="siem-integration-with-microsoft-defender-for-office-365"></a>SIEM-integratie met Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Als in uw organisatie een server voor beveiliging en Gebeurtenissenbeheer (SIEM) wordt gebruikt, kunt u Microsoft Defender voor Office 365 integreren met uw SIEM-server. U kunt deze integratie instellen met de [API Office 365 activity management](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-reference).

Met de integratie van SIEM kunt u informatie weergeven, zoals malware of phishing die is gedetecteerd door Microsoft Defender for Office 365, in de SIEM-Server rapporten.

- Als u een voorbeeld wilt bekijken van de integratie van SIEM met Microsoft Defender for Office 365, raadpleegt u [de tech Community-Blog: Verbeter de effectiviteit van uw Soc met Defender voor Office 365 en de O365-beheer-API](https://techcommunity.microsoft.com/t5/microsoft-security-and/improve-the-effectiveness-of-your-soc-with-office-365-atp-and/ba-p/1525185).

- Zie voor meer informatie over de Office 365-beheer-Api's [overzicht van office 365 Management-api's](https://docs.microsoft.com/office/office-365-management-api/office-365-management-apis-overview).

## <a name="how-siem-integration-works"></a>De werking van SIEM-integratie

De API Office 365 activity management haalt informatie op over gebruikers-, beheer-, systeem-en beleidsacties en gebeurtenissen uit de logboeken van Microsoft 365 en Azure Active Directory-activiteiten van uw organisatie. Als uw organisatie Microsoft Defender voor Office 365 (abonnement 1) of 2, of Office 365 E5 bevat, kunt u het [Microsoft Defender for office 365-schema](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema#office-365-advanced-threat-protection-and-threat-investigation-and-response-schema)gebruiken.

Onlangs werden gebeurtenissen van geautomatiseerde onderzoek-en antwoord mogelijkheden in [Microsoft Defender voor Office 365-abonnement 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) toegevoegd aan de Office 365 Management Activity API. Naast gegevens over informatie over het kern onderzoek, zoals ID, naam en status, bevat de API ook hoog-niveau informatie over onderzoeks-en entiteits activiteiten.

De controle op de SIEM-server of een ander soortgelijk systeem controleert de **audit. General** -werklast voor toegang tot detectie gebeurtenissen. Zie aan de [slag met Office 365 Management api's](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)voor meer informatie.

## <a name="enum-auditlogrecordtype---type-edmint32"></a>Enum: AuditLogRecordType-type: EDM. Int32

### <a name="auditlogrecordtype"></a>AuditLogRecordType

De volgende tabel bevat een overzicht van de waarden van **AuditLogRecordType** die relevant zijn voor gebeurtenissen van Microsoft Defender for Office 365:

|Value|Lidnaam|Beschrijving|
|---|---|---|
|30|ThreatIntelligence|Phishing en malware van gebeurtenissen via Exchange Online Protection en Microsoft Defender voor Office 365.|
|41|ThreatIntelligenceUrl|Veilige koppelingen de time-out van het blokkeren en negeren van gebeurtenissen in Microsoft Defender voor Office 365.|
|47|ThreatIntelligenceAtpContent|Phishing en malware-gebeurtenissen voor bestanden in SharePoint Online, OneDrive voor bedrijven en Microsoft teams, van Microsoft Defender voor Office 365.|
|64|Onderzoek|Geautomatiseerd onderzoek en antwoord gebeurtenissen, zoals onderzoek Details en relevante artefacten, uit Microsoft Defender voor Office 365, abonnement 2.|
|

> [!IMPORTANT]
> U moet een hoofdbeheerder zijn of de rol van beveiligingsbeheerder toegewezen hebben voor de beveiligings & voor nalevings centrum voor het instellen van SIEM-integratie met Microsoft Defender voor Office 365.
>
> U moet de controlelogboekregistratie inschakelen voor uw Microsoft 365-omgeving. Als u hulp nodig hebt, raadpleegt u de [zoekfunctie voor auditlogboeken in-of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="see-also"></a>Zie ook

[Dreigingsonderzoek en -antwoord in Office 365](office-365-ti.md)

[Geautomatiseerd onderzoek en antwoord (lucht) in Office 365](automated-investigation-response-office.md)

