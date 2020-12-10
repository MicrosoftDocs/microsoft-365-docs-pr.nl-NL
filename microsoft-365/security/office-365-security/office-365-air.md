---
title: Automatisch onderzoek en antwoord in Microsoft Defender voor Office 365
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herstel, bedreiging, Geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/05/2020
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
ms.openlocfilehash: 8b6ef712e2e90e6798f16c54bc82f99590dbea42
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49614832"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Geautomatiseerd onderzoek en antwoord (lucht) in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender voor Office 365](office-365-atp.md) bevat krachtige functies voor automatisch onderzoek en Reacties (lucht) waarmee u tijd en inspanningen van uw beveiligingsactiviteiten kunnen opslaan. Aangezien waarschuwingen worden geactiveerd, kunt u deze meldingen nakijken, van een prioriteit voorzien en hierop reageren. U kunt het volume van inkomende waarschuwingen overweldigen. Door sommige taken te automatiseren, kunt u het volgende doen.

AIR zorgt ervoor dat uw beveiligingsteam efficiënter en effectiever functioneert. De lucht mogelijkheden zijn geautomatiseerde onderzoek processen in antwoord naar bekende bedreigingen die vandaag zijn. Juiste herstelacties wachten op goedkeuring, zodat het team van uw beveiligingsactiviteiten effectief kan reageren op ontdekte bedreigingen. Met lucht kan uw beveiligingsteam zich richten op taken met een hoge prioriteit, zonder dat het zichtbaar is wanneer u belangrijke waarschuwingen gaat verliezen.

In dit artikel worden de volgende artikelen beschreven:

- De [algehele stroom van lucht](#the-overall-flow-of-air);
- [Hoe u lucht verzorgt](#how-to-get-air); en
- De [vereiste machtigingen](#required-permissions-to-use-air-capabilities) voor het configureren of gebruiken van lucht capaciteiten.

Dit artikel bevat ook [volgende stappen](#next-steps)en bronnen voor meer informatie.

## <a name="the-overall-flow-of-air"></a>De totale luchtstroom

Er wordt een waarschuwing gegeven en een beveiligings Playbook start een geautomatiseerd onderzoek, wat leidt tot bevindingen en aanbevolen acties. Dit is de algemene stroom van lucht, stap voor stap:

1. Een geautomatiseerd onderzoek wordt op een van de volgende manieren gestart:

   - Een [waarschuwing wordt geactiveerd](#which-alert-policies-trigger-automated-investigations) door iets verdacht in een e-mail (zoals een bericht, bijlage, URL of gemanipuleerd gebruikersaccount). Er wordt een incident gemaakt en een geautomatiseerd onderzoek begint.

     ------

   - Een beveiligings analist [Start een automatisch onderzoek](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) tijdens het gebruik van de [Threat Explorer](threat-explorer.md).

2. Tijdens een geautomatiseerde onderzoek wordt er extra informatie verzameld over het e-mailbericht in kwestie en de entiteiten die aan die e-mail zijn gekoppeld. Deze entiteiten kunnen bestanden, Url's en geadresseerden bevatten.  Het vernieuwings bereik kan toenemen omdat er nieuwe en gerelateerde waarschuwingen worden geactiveerd.

3. Tijdens en na een geautomatiseerd onderzoek zijn er [gegevens en resultaten](air-view-investigation-results.md) beschikbaar voor weergave. Resultaten omvatten [aanbevolen acties](air-remediation-actions.md) die kunnen worden uitgevoerd om bedreigingen te beantwoorden en te herstellen. Daarnaast is er een [Playbook-logboek](air-view-investigation-results.md#playbook-log) beschikbaar waarmee alle onderzoekactiviteiten worden bijgehouden.

4. Uw team van beveiligingsactiviteiten beoordeelt het [onderzoek resultaat en aanbevelingen](air-view-investigation-results.md), en [keurt of weigert herstelacties](air-review-approve-pending-completed-actions.md).

5. Wanneer herstelacties in behandeling zijn goedgekeurd (of afgekeurd), is het geautomatiseerde onderzoek voltooid.

> [!IMPORTANT]
> In Microsoft Defender voor Office 365 worden geen herstelacties automatisch uitgevoerd. Herstelacties worden alleen uitgevoerd na goedkeuring van het beveiligingsteam van uw organisatie.
>
> LUCHT capaciteiten Sla uw beveiligingsactiviteiten voor het team op door herstel activiteiten te identificeren en de details te verstrekken die nodig zijn om een weloverwogen beslissing te nemen.

Wanneer u een geautomatiseerd onderzoek doet, kan uw beveiligingsteam:

- [Details weergeven van een waarschuwing die is gerelateerd aan een onderzoek](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [De resultaten gegevens van een onderzoek weergeven](air-view-investigation-results.md#view-details-of-an-investigation)

- [Acties controleren en goedkeuren als gevolg van een onderzoek](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Zie de [werking van lucht](automated-investigation-response-office.md)voor een gedetailleerde beschrijving.

## <a name="how-to-get-air"></a>Hoe u lucht verzorgt

U kunt in [Microsoft Defender voor Office 365](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)lucht functies opnemen, mits uw beleidsregels en waarschuwingen zijn geconfigureerd. Als u hulp nodig hebt, volgt u de richtlijnen in [beveiliging tegen bedreigingen](protect-against-threats.md) om de volgende beveiligingsinstellingen in te stellen of te configureren:

1. [Controlelogboekregistratie](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (moet worden ingeschakeld)

2. [Antimalwarebeleid](protect-against-threats.md#part-1---anti-malware-protection)

3. [Antiphishing-bescherming](protect-against-threats.md#part-2---anti-phishing-protection)

4. [Spam bescherming](protect-against-threats.md#part-3---anti-spam-protection).

5. [Veilige koppelingen en veilige bijlagen](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365).

6. [Veilige bijlagen voor SharePoint, OneDrive en Microsoft teams](protect-against-threats.md#part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on).

7. [Uur per uur automatisch wissen voor e-mail](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop).

Zorg er ook voor dat u het [waarschuwings beleid van uw organisatie](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)controleert, met name het [standaardbeleid in de categorie risicobeheer](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies).

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welke waarschuwings beleidsregels activeren geautomatiseerd onderzoek?

Microsoft 365 biedt een groot aantal ingebouwde waarschuwingen waarmee beheerdersmachtigingen van Exchange kunnen identificeren, schadelijke activiteiten, potentiële externe en interne bedreigingen en informatiebeheer Risico's. Een aantal [standaard waarschuwings beleidsregels](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) kan automatisch onderzoek activeren. In de volgende tabel vindt u een beschrijving van de waarschuwingen waarmee automatisch onderzoek en de ernst ervan worden geactiveerd in het Microsoft 365-Beveiligingscentrum en hoe deze worden gegenereerd:

|Bericht|Ernst|Hoe de waarschuwing wordt gegenereerd|
|---|---|---|
|Er is een mogelijk schadelijke URL gevonden|**Hoog**|U ontvangt deze waarschuwing als u een van de volgende handelingen doet: <ul><li>Een gebruiker die is beveiligd door [veilige koppelingen](atp-safe-links.md) in uw organisatie op een schadelijke koppeling</li><li>Verdict wijzigingen voor Url's worden geïdentificeerd door Microsoft Defender voor Office 365</li><li>Gebruikers negeren waarschuwings pagina's voor veilige koppelingen (op basis van het [beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md)van uw organisatie).</li></ul> <p> Zie [beleid voor veilige koppelingen instellen](set-up-atp-safe-links-policies.md)voor meer informatie over gebeurtenissen waarmee deze melding wordt geactiveerd.|
|Een e-mailbericht wordt door een gebruiker gemeld als malware of phishing|**Informatieve**|Deze melding wordt gegenereerd wanneer gebruikers in uw organisatie berichten als malafide rapporteren via de [invoegtoepassing berichten rapporteren](enable-the-report-message-add-in.md).|
|E-mailberichten met malware worden verwijderd na levering|**Informatieve**|Deze waarschuwing wordt gegenereerd wanneer u e-mailberichten met malware bezorgt voor postvakken in uw organisatie. Als deze gebeurtenis zich voordoet, verwijdert Microsoft de geïnfecteerde berichten uit postvakken van Exchange Online met [automatisch wissen van uur uur](zero-hour-auto-purge.md).|
|E-mailberichten met phishing-Url's worden verwijderd na levering|**Informatieve**|Deze waarschuwing wordt gegenereerd wanneer berichten met phishing worden afgeleverd bij postvakken in uw organisatie. Als deze gebeurtenis zich voordoet, verwijdert Microsoft de geïnfecteerde berichten uit postvakken van Exchange Online met [automatisch wissen van uur uur](zero-hour-auto-purge.md).|
|Verdachte patronen voor het verzenden van e-mail worden gedetecteerd|**Medium**|Deze melding wordt gegenereerd wanneer iemand in uw organisatie verdacht e-mailbericht heeft gestuurd en risico loopt dat e-mail wordt verzonden. Dit is een vroegtijdige waarschuwing voor gedrag dat kan betekenen dat de account is aangetast, maar niet zo sterk genoeg om de gebruiker te beperken. <p> Hoewel dit niet het geval is, kan een waarschuwing die door dit beleid is gegenereerd, een afwijkend zijn. Het is echter wel een goed idee om te [controleren of het gebruikersaccount is aangetast](responding-to-a-compromised-email-account.md).|
|Een gebruiker mag geen e-mail verzenden|**Hoog**|Deze melding wordt gegenereerd wanneer iemand in uw organisatie beperkingen heeft voor het verzenden van uitgaande e-mail. Dit levert meestal een [e-mailaccount in gevaar](responding-to-a-compromised-email-account.md). <p> Zie voor meer informatie over beperkte gebruikers [Geblokkeerde gebruikers verwijderen uit de portal met beperkte gebruikers in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md).|
|

> [!TIP]
> Als u meer wilt weten over waarschuwings beleidsregels of de standaardinstellingen bewerken, raadpleegt u [waarschuwings beleid in het Microsoft 365 compliance Center](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="required-permissions-to-use-air-capabilities"></a>Vereiste machtigingen voor het gebruik van lucht mogelijkheden

Machtigingen worden toegekend via bepaalde rollen, zoals de functies die in de volgende tabel worden beschreven:

|Taak|Vereiste functie (s)|
|---|---|
|LUCHT functies instellen|Een van de volgende rollen: <ul><li>Globale beheerder</li><li>Beveiligingsbeheerder</li></ul> <p> U kunt deze rollen toewijzen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het [beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).|
|Een automatisch onderzoek starten <p> ------ <p> Aanbevolen acties goedkeuren of afwijzen|Een van de volgende rollen, toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het [beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md): <ul><li>Globale beheerder</li><li>Beveiligingsbeheerder</li><li>Beveiligings lezer <br> ---en--- </li><li>Zoeken en wissen (deze rol wordt alleen toegewezen in het [nalevings centrum voor de beveiliging &](permissions-in-the-security-and-compliance-center.md). U moet mogelijk een nieuwe rolgroep maken en de rol zoeken en permanent toevoegen aan deze nieuwe rollen groep toevoegen.</li></ul>|
|

## <a name="required-licenses"></a>Vereiste licenties

[Microsoft Defender voor Office 365-abonnement 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) -licenties moet worden toegewezen aan:

- Beveiligingsbeheerders (waaronder globale beheerders)
- Het bedrijfsactiviteiten team van uw organisatie (met inbegrip van beveiligings lezers en de functies met de rol **zoeken en wissen** )
- Eindgebruikers

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek weergeven](air-view-investigation-results.md#view-details-of-an-investigation)

- [In behandeling zijnde acties controleren en goedkeuren](air-remediation-actions.md)

## <a name="see-also"></a>Zie ook

- [Automatisch onderzoek en herstel in Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatisch onderzoek en antwoord in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
