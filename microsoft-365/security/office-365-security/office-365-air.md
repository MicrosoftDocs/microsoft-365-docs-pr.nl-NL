---
title: Aan de slag met automatisch onderzoek en antwoord in Microsoft Defender voor Office 365
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herstel, bedreiging, Geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/04/2020
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Ga aan de slag met het gebruik van geautomatiseerde onderzoek-en antwoord mogelijkheden in Microsoft Defender voor Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.openlocfilehash: 7e9b786a9d00a34f5e2e88a8481e82fa8425a501
ms.sourcegitcommit: 751dc531f0410ee075c179efe409a01664483ee2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/05/2020
ms.locfileid: "48925602"
---
# <a name="get-started-using-automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Aan de slag met geautomatiseerd onderzoek en antwoord (lucht) in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender voor Office 365](office-365-atp.md) bevat krachtige functies voor automatisch onderzoek en Reacties (lucht) waarmee u tijd en inspanningen van uw beveiligingsactiviteiten kunnen opslaan. Aangezien waarschuwingen worden geactiveerd, kunt u deze meldingen nakijken, van een prioriteit voorzien en hierop reageren. U kunt het volume van inkomende waarschuwingen overweldigen. Door sommige taken te automatiseren, kunt u het volgende doen. Met lucht kan uw beveiligingsteam zich richten op taken met een hoge prioriteit, zonder dat het zichtbaar is wanneer u belangrijke waarschuwingen gaat verliezen.

In dit artikel worden de volgende artikelen beschreven:
- De [algehele stroom van lucht](#the-overall-flow-of-air);
- [Hoe u lucht verzorgt](#how-to-get-air); en 
- De [vereiste machtigingen](#required-permissions-to-use-air-capabilities) voor het configureren of gebruiken van lucht capaciteiten. 

## <a name="the-overall-flow-of-air"></a>De totale luchtstroom

Er wordt een waarschuwing gegeven en een beveiligings Playbook start een geautomatiseerd onderzoek, wat leidt tot bevindingen en aanbevolen acties. Dit is de algemene stroom van lucht, stap voor stap:

1. Een geautomatiseerd onderzoek wordt op een van de volgende manieren gestart:

   - Een [waarschuwing](https://docs.microsoft.com/microsoft-365/compliance/alert-policies) wordt geactiveerd door iets verdacht in een e-mail (zoals een bericht, bijlage of URL). Er wordt een incident gemaakt. Afhankelijk van het type incident, wordt er een [beveiligings Playbook](automated-investigation-response-office.md#security-playbooks) uitgevoerd, waarna een geautomatiseerd onderzoek wordt gestart. 

     ------
   
   - Een beveiligings analist [Start een automatisch onderzoek](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) tijdens het gebruik van de [Threat Explorer](threat-explorer.md).

2. Tijdens een geautomatiseerde onderzoek wordt er extra informatie verzameld over het e-mailbericht in kwestie en de entiteiten die aan die e-mail zijn gekoppeld. Deze entiteiten kunnen bestanden, Url's en geadresseerden bevatten.  Het vernieuwings bereik kan toenemen omdat er nieuwe en gerelateerde waarschuwingen worden geactiveerd.

3. Tijdens en na een geautomatiseerd onderzoek zijn er [gegevens en resultaten](air-view-investigation-results.md) beschikbaar voor weergave. Resultaten omvatten [aanbevolen acties](air-remediation-actions.md) die kunnen worden uitgevoerd om bedreigingen te beantwoorden en te herstellen. Daarnaast is er een [Playbook-logboek](air-view-investigation-results.md#playbook-log) beschikbaar waarmee alle onderzoekactiviteiten worden bijgehouden.


4. Uw team van beveiligingsactiviteiten beoordeelt het [onderzoek resultaat en aanbevelingen](air-view-investigation-results.md), en [keurt of weigert herstelacties](air-review-approve-pending-completed-actions.md). 

5. Wanneer herstelacties in behandeling zijn goedgekeurd (of afgekeurd), is het geautomatiseerde onderzoek voltooid.

> [!IMPORTANT]
> In Microsoft Defender voor Office 365 worden geen herstelacties automatisch uitgevoerd. Herstelacties worden alleen uitgevoerd na goedkeuring van het beveiligingsteam van uw organisatie. U kunt echter de tijd van uw beveiligingsactiviteiten in uw organisatie opslaan door herstelacties aan te duiden en de benodigde informatie te verstrekken om een weloverwogen beslissing te nemen.

Wanneer u een geautomatiseerd onderzoek doet, kan uw beveiligingsteam:

- [Details weergeven van een waarschuwing die is gerelateerd aan een onderzoek](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [De resultaten gegevens van een onderzoek weergeven](air-view-investigation-results.md#view-details-of-an-investigation)

- [Acties controleren en goedkeuren als gevolg van een onderzoek](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Zie de [werking van lucht](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)voor een gedetailleerde beschrijving.

## <a name="how-to-get-air"></a>Hoe u lucht verzorgt

U kunt in [Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2)lucht functies opnemen, mits uw beleidsregels en waarschuwingen zijn geconfigureerd. Als u hulp nodig hebt, volgt u de richtlijnen in [beveiliging tegen bedreigingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats) om de volgende beveiligingsinstellingen in te stellen of te configureren: 

1. [Controlelogboekregistratie](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (moet worden ingeschakeld)

2. [Antimalwarebeleid](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-1---anti-malware-protection)

3. [Antiphishing-bescherming](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-2---anti-phishing-protection)
   
4. [Spam bescherming](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-3---anti-spam-protection).
   
5. [Veilige koppelingen en veilige bijlagen](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).
   
6. [Veilige bijlagen voor SharePoint, OneDrive en Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).
   
7. [Uur per uur automatisch wissen voor e-mail](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?zero-hour-auto-purge-for-email-in-eop).

Zorg er ook voor dat u het [waarschuwings beleid van uw organisatie](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)controleert, met name het [standaardbeleid in de categorie risicobeheer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies). 

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welke waarschuwings beleidsregels activeren geautomatiseerd onderzoek?

Microsoft 365 biedt een groot aantal ingebouwde waarschuwingen waarmee beheerdersmachtigingen van Exchange kunnen identificeren, schadelijke activiteiten, potentiële externe en interne bedreigingen en informatiebeheer Risico's. Een aantal [standaard waarschuwings beleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan automatisch onderzoek activeren. Deze omvatten de volgende:

- Er is een potentieel schadelijke URL klik gedetecteerd
- Een e-mailbericht wordt door een gebruiker gemeldd als phishing
- E-mailberichten met malware worden verwijderd na levering
- E-mailberichten met phishing-Url's worden verwijderd na levering
- Verdachte patronen voor het verzenden van e-mail worden gedetecteerd
- Een gebruiker mag geen e-mail verzenden

## <a name="required-permissions-to-use-air-capabilities"></a>Vereiste machtigingen voor het gebruik van lucht mogelijkheden

Machtigingen worden toegekend via bepaalde rollen, zoals de functies die in de volgende tabel worden beschreven: 

|Taak |Vereiste functie (s) |
|--|--|
|LUCHT functies instellen |Een van de volgende rollen: <br/>-Globale beheerder<br/>-Beveiligingsbeheerder <br/>U kunt deze rollen toewijzen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het [beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). |
|Aanbevolen acties goedkeuren of afwijzen|Een van de volgende rollen, toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het [beveiligings & nalevings centrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center):<br/>-Globale beheerder <br/>-Beveiligingsbeheerder<br/>-Beveiligings lezer <br/>---en---<br/>-Zoeken en wissen (deze rol wordt alleen toegewezen in het [nalevings centrum voor de beveiliging &](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center). Mogelijk moet u een nieuwe rolgroep maken en de rol zoeken en permanent toevoegen aan de nieuwe rollen groep toevoegen.)

## <a name="required-licenses"></a>Vereiste licenties

[Voor Microsoft Defender voor Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#office-365-atp-plan-1-and-plan-2) -licenties moet worden toegewezen:
- Beveiligingsbeheerders (waaronder globale beheerders)
- Het bedrijfsactiviteiten team van uw organisatie (met inbegrip van beveiligings lezers en de functies met de rol zoeken en wissen)
- Eindgebruikers


## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek weergeven](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results#view-details-of-an-investigation)

- [In behandeling zijnde acties controleren en goedkeuren](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-remediation-actions)

## <a name="related-articles"></a>Verwante artikelen

- [Automatisch onderzoek en herstel in Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatisch onderzoek en antwoord in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
