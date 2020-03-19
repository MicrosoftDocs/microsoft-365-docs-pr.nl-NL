---
title: Geautomatiseerd onderzoek en respons (AIR) in Office 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, reactie, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Aan de slag met geautomatiseerde onderzoeks- en responsmogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.custom: air
ms.openlocfilehash: 45a2bc0e581916493a0170a5f86c152d02403efe
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826347"
---
# <a name="automated-investigation-and-response-air-in-office-365"></a>Geautomatiseerd onderzoek en respons (AIR) in Office 365

[Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) Plan 2 bevat krachtige automatische onderzoeks- en responsmogelijkheden (AIR) waarmee uw beveiligingsteam tijd en moeite kan besparen. Aangezien waarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te controleren, te prioriteren en te beantwoorden. Het bijhouden van het aantal binnenkomende waarschuwingen kan overweldigend zijn. Het automatiseren van een deel van dit kan helpen. Met AIR kan uw beveiligingsteam zich richten op taken met een hogere prioriteit zonder waarschuwingen uit het oog te verliezen die worden geactiveerd.

In dit artikel wordt de [algehele luchtstroom](#the-overall-flow-of-air) van AIR beschreven, hoe u AIR [kunt krijgen](#how-to-get-air)en de vereiste [machtigingen](#required-permissions-to-use-air-capabilities) om AIR-mogelijkheden te configureren of te gebruiken. 

## <a name="the-overall-flow-of-air"></a>De totale luchtstroom van AIR

Op een hoog niveau wordt een waarschuwing geactiveerd en wordt een beveiligingsplaybook gestart en geautomatiseerd onderzoek gestart, wat resulteert in bevindingen en aanbevelingen. Hier is de totale stroom van AIR, stap voor stap:

1. Een geautomatiseerd onderzoek wordt gestart op een van de volgende manieren:

   - Een [waarschuwing](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) wordt geactiveerd door een Office-gebeurtenis, waardoor een incident wordt gemaakt. Afhankelijk van het type incident start een [beveiligingsplaybook](automated-investigation-response-office.md#security-playbooks) een geautomatiseerd onderzoek. 

     --- of ---
   
   - Een beveiligingsanalist [start een geautomatiseerd onderzoek](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) tijdens het gebruik van Threat [Explorer.](threat-explorer.md)

2. Terwijl een geautomatiseerd onderzoek wordt uitgevoerd, verzamelt het aanvullende gegevens over de e-mail in kwestie en entiteiten met betrekking tot die e-mail. Dergelijke entiteiten kunnen bestanden, URL's en ontvangers bevatten.  Het bereik van het onderzoek kan toenemen naarmate nieuwe en gerelateerde waarschuwingen worden geactiveerd.

3. Tijdens en na een geautomatiseerd onderzoek zijn [details en resultaten](air-view-investigation-results.md) te bekijken. De resultaten omvatten [aanbevolen acties](air-remediation-actions.md) die kunnen worden ondernomen om te reageren en eventuele bedreigingen die zijn gevonden, te herstellen. Daarnaast is er een [playbooklogboek](air-view-investigation-results.md#playbook-log) beschikbaar dat alle onderzoeksactiviteiten bijhoudt.

    Als uw organisatie een aangepaste rapportageoplossing of een oplossing van derden gebruikt, u [de API voor beheeractiviteit van Office 365 gebruiken](air-custom-reporting.md) om informatie over geautomatiseerde onderzoeken en bedreigingen weer te geven.

4. Uw beveiligingsteam beoordeelt de [onderzoeksresultaten en aanbevelingen](air-view-investigation-results.md)en [keurt herstelacties goed of weigert deze.](air-review-approve-pending-completed-actions.md) 

    Aangezien in behandeling zijnde saneringsacties worden goedgekeurd (of afgewezen), wordt het geautomatiseerde onderzoek voltooid.

> [!NOTE]
> In Office 365 ATP worden geen herstelacties automatisch uitgevoerd. Herstelacties worden alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie. 

Tijdens en na een geautomatiseerd onderzoeksproces kan uw beveiligingsteam het volgende doen:

- [Details over een waarschuwing met betrekking tot een onderzoek weergeven](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Bekijk de resultaten van een onderzoek](air-view-investigation-results.md#view-details-of-an-investigation)

- [Acties beoordelen en goedkeuren naar aanleiding van een onderzoek](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Zie [Hoe air werkt voor](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)meer informatie .

## <a name="how-to-get-air"></a>Hoe krijg je LUCHT

Office 365 AIR-mogelijkheden zijn opgenomen in [Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2). Uw [Office 365 ATP-beleid moet](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) echter worden geconfigureerd om AIR te laten werken zoals verwacht. Zorg er bovendien voor dat u het [waarschuwingsbeleid van](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)uw organisatie controleert en mogelijk configureert. 

Office 365 biedt veel ingebouwde waarschuwingsbeleid waarmee misbruik, malwareactiviteit, potentiële externe en interne bedreigingen en risico's voor informatiebeheer kunnen worden geïdentificeerd. Een aantal van de [standaard waarschuwingsbeleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan leiden tot geautomatiseerde onderzoeken. Deze omvatten de volgende:

- Een mogelijk kwaadaardige URL-klik wordt gedetecteerd

- Een e-mailbericht wordt gerapporteerd door een gebruiker als phish

- E-mailberichten met malware worden verwijderd na levering

- E-mailberichten met phish URL's worden verwijderd na levering

- Verdachte e-mailverzendende patronen worden gedetecteerd

- Een gebruiker mag geen e-mail verzenden

[Meer informatie over waarschuwingen en AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Vereiste machtigingen voor het gebruik van AIR-mogelijkheden

Machtigingen worden verleend via bepaalde rollen, zoals die in de volgende tabel worden beschreven: 

|Taak |Rol(en) vereist |
|--|--|
|Air-functies instellen |Een van de volgende rollen: <br/>- Global Administrator<br/>- Beveiligingsbeheerder <br/>Deze rollen kunnen worden toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het Office [365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Aanbevolen acties goedkeuren of afwijzen|Een van de volgende rollen, toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het Office [365 Security & Compliance Center):](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)<br/>- Global Administrator <br/>- Beveiligingsbeheerder<br/>- Beveiligingslezer <br/>--- en ---<br/>- Zoeken en wissen (deze rol wordt alleen toegewezen in het [Office 365 Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Mogelijk moet u daar een nieuwe rolgroep maken en de rol Zoeken en wissen toevoegen aan die nieuwe rolgroep.)

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek bekijken](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [Lopende acties bekijken en goedkeuren](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Verwante artikelen

- [Geautomatiseerd onderzoek en herstel in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Geautomatiseerd onderzoek en reactie in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
