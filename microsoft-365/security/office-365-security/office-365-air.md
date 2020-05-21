---
title: Geautomatiseerd onderzoek en respons (AIR) - Aan de slag
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
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
description: Aan de slag met geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.custom: air - seo-marvel-mar2020
ms.openlocfilehash: c2020c3d46fcf17194e2560af53d9a26fca30629
ms.sourcegitcommit: f6840dfcfdbcadc53cda591fd6cf9ddcb749d303
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/20/2020
ms.locfileid: "44327828"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-office-365"></a>Aan de slag met Automated Investigation and Response (AIR) in Office 365

[Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) Plan 2 bevat krachtige mogelijkheden voor geautomatiseerd onderzoek en respons (AIR) die uw beveiligingsactiviteiten tijd en moeite kunnen besparen. Als waarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te controleren, te prioriteren en erop te reageren. Het bijhouden van het volume van de inkomende waarschuwingen kan overweldigend zijn. Het automatiseren van een deel van dit kan helpen. Met AIR kan uw beveiligingsteam zich richten op taken met een hogere prioriteit zonder waarschuwingen uit het oog te verliezen die worden geactiveerd.

In dit artikel wordt de [algehele luchtstroom](#the-overall-flow-of-air) beschreven, hoe air en de [vereiste machtigingen](#required-permissions-to-use-air-capabilities) kunnen worden [gegeven](#how-to-get-air)om AIR-mogelijkheden te configureren of te gebruiken. 

## <a name="the-overall-flow-of-air"></a>De totale stroom van AIR

Op een hoog niveau wordt een waarschuwing geactiveerd en start een beveiligingsplaybook een geautomatiseerd onderzoek, wat resulteert in bevindingen en aanbevelingen. Hier is de totale stroom van AIR, stap voor stap:

1. Een geautomatiseerd onderzoek wordt op een van de volgende manieren gestart:

   - Er wordt een [waarschuwing](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) geactiveerd door een Office-gebeurtenis, waardoor een incident ontstaat. Afhankelijk van het type incident start een [beveiligingsplaybook](automated-investigation-response-office.md#security-playbooks) een geautomatiseerd onderzoek. 

     --- of ---
   
   - Een beveiligingsanalist [start een geautomatiseerd onderzoek](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) tijdens het gebruik van Threat [Explorer.](threat-explorer.md)

2. Terwijl een geautomatiseerd onderzoek wordt uitgevoerd, verzamelt het aanvullende gegevens over de e-mail in kwestie en entiteiten met betrekking tot die e-mail. Dergelijke entiteiten kunnen bestanden, URL's en geadresseerden bevatten.  Het bereik van het onderzoek kan toenemen naarmate nieuwe en gerelateerde waarschuwingen worden geactiveerd.

3. Tijdens en na een geautomatiseerd onderzoek zijn [details en resultaten](air-view-investigation-results.md) te bekijken. De resultaten omvatten [aanbevolen acties](air-remediation-actions.md) die kunnen worden ondernomen om te reageren en eventuele bedreigingen te herstellen die zijn gevonden. Daarnaast is er een [draaiboeklogboek](air-view-investigation-results.md#playbook-log) beschikbaar dat alle onderzoeksactiviteiten bijhoudt.

    Als uw organisatie een aangepaste rapportageoplossing of een oplossing van derden gebruikt, u [de Office 365 Management Activity API gebruiken](air-custom-reporting.md) om informatie over geautomatiseerde onderzoeken en bedreigingen weer te geven.

4. Uw team beveiligingsoperaties bekijkt de [onderzoeksresultaten en -aanbevelingen](air-view-investigation-results.md)en [keurt herstelacties goed of verwerpt deze.](air-review-approve-pending-completed-actions.md) 

    Aangezien lopende herstelacties worden goedgekeurd (of afgewezen), wordt het geautomatiseerde onderzoek voltooid.

> [!NOTE]
> In Office 365 ATP worden automatisch geen herstelacties uitgevoerd. Herstelacties worden alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie. 

Tijdens en na een geautomatiseerd onderzoeksproces kan uw beveiligingsteam het volgende doen:

- [Details weergeven over een waarschuwing met betrekking tot een onderzoek](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [Bekijk de resultaten van een onderzoek](air-view-investigation-results.md#view-details-of-an-investigation)

- [Acties beoordelen en goedkeuren naar aanleiding van een onderzoek](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Zie [Hoe AIR werkt](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)voor meer informatie.

## <a name="how-to-get-air"></a>Hoe air te krijgen

Office 365 AIR-mogelijkheden zijn opgenomen in [Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2). Uw [Office 365 ATP-beleid moet](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) echter worden geconfigureerd om AIR te laten werken zoals verwacht. Zorg er bovendien voor dat u het [waarschuwingsbeleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)van uw organisatie controleert en mogelijk configureert. 

Microsoft 365 biedt veel ingebouwde waarschuwingsbeleidsregels waarmee misbruik van Exchange-beheerders, malware-activiteiten, potentiële externe en interne bedreigingen en risico's voor informatiebeheer kunnen worden geïdentificeerd. Verschillende [standaardwaarschuwingsbeleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kunnen leiden tot geautomatiseerde onderzoeken. Deze omvatten de volgende:

- Een mogelijk kwaadaardige URL-klik wordt gedetecteerd

- Een e-mailbericht wordt door een gebruiker gerapporteerd als phish

- E-mailberichten met malware worden verwijderd na levering

- E-mailberichten met phish-URL's worden na levering verwijderd

- Verdachte e-mailverzendpatronen worden gedetecteerd

- Een gebruiker mag geen e-mail verzenden

[Meer informatie over waarschuwingen en AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office).

## <a name="required-permissions-to-use-air-capabilities"></a>Vereiste machtigingen voor het gebruik van AIR-mogelijkheden

Machtigingen worden verleend via bepaalde rollen, zoals die welke worden beschreven in de volgende tabel: 

|Taak |Vereiste rol(en) |
|--|--|
|Air-functies instellen |Een van de volgende rollen: <br/>- Globale beheerder<br/>- Beveiligingsbeheerder <br/>Deze rollen kunnen worden toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het Security & Compliance [Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Aanbevolen acties goedkeuren of afwijzen|Een van de volgende rollen, toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het Security & Compliance [Center):](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center)<br/>- Globale beheerder <br/>- Beveiligingsbeheerder<br/>- Beveiligingslezer <br/>--- en ---<br/>- Zoeken en verwijderen (deze rol wordt alleen toegewezen in het [Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Mogelijk moet u daar een nieuwe rolgroep maken en de rol Zoeken en verwijderen toevoegen aan die nieuwe rolgroep.)

[Office 365 ATP Plan 2-licenties](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) moeten worden toegewezen aan:
- Beveiligingsbeheerders (inclusief globale beheerders)
- Het beveiligingsteam van uw organisatie (inclusief beveiligingslezers en mensen met de rol Zoeken en verwijderen)
- Eindgebruikers

Bovendien moet [het Office 365 ATP-beleid](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) worden gedefinieerd en toegepast om bescherming te kunnen bieden.

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek bekijken](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [In behandeling zijnde acties controleren en goedkeuren](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Verwante artikelen

- [Geautomatiseerd onderzoek en herstel in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Geautomatiseerd onderzoek en reactie in Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
