---
title: Automatisch onderzoek en antwoorden in Microsoft Defender voor Office 365
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/28/2021
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Ga aan de slag met geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365.
ms.custom:
- air
- seo-marvel-mar2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee448e31ccbddbf1d1d5653614ec75fa94768b3b
ms.sourcegitcommit: f3059a0065496623e36e5a084cd2291e6b844597
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/28/2021
ms.locfileid: "50040530"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Automatisch onderzoek en automatisch onderzoek (AIR) in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

[Microsoft Defender voor Office 365](office-365-atp.md) bevat krachtige mogelijkheden voor geautomatiseerde onderzoeken en antwoorden (AIR) die uw teamtijd en inspanning voor beveiligingsbewerkingen kunnen besparen. Wanneer waarschuwingen worden geactiveerd, is het aan uw team voor beveiligingsbewerkingen om die waarschuwingen te controleren, een prioriteit te geven en hierop te reageren. Het bijhouden van het volume van binnenkomende meldingen kan overweldigend zijn. Het automatiseren van een aantal van deze taken kan helpen.

Met AIR kunnen uw team voor beveiligingsactiviteiten efficiënter en efficiënter werken. AIR-mogelijkheden omvatten geautomatiseerde onderzoeksprocessen in reactie op bekende bedreigingen die op dit moment bestaan. Juiste herstelacties wachten op goedkeuring, zodat het team voor beveiligingsbewerkingen effectief kan reageren op gedetecteerde bedreigingen. Met AIR kan uw team voor beveiligingsbewerkingen zich richten op taken met een hogere prioriteit zonder dat u belangrijke waarschuwingen ziet die worden geactiveerd.

In dit artikel worden de volgende artikelen beschreven:

- De [algehele stroom van AIR](#the-overall-flow-of-air);
- [Air krijgen](#how-to-get-air); en
- De [vereiste machtigingen voor](#required-permissions-to-use-air-capabilities) het configureren of gebruiken van AIR-mogelijkheden.

Dit artikel bevat ook [de volgende stappen](#next-steps)en informatiebronnen voor meer informatie.

## <a name="the-overall-flow-of-air"></a>De algehele stroom van AIR

Er wordt een waarschuwing geactiveerd en een beveiligings playbook start een geautomatiseerd onderzoek, wat resulteert in resultaten van bevindingen en aanbevolen acties. Hier is de algehele stroom van AIR, stap voor stap:

1. Een geautomatiseerd onderzoek wordt op een van de volgende manieren gestart:

   - Een [waarschuwing wordt geactiveerd door](#which-alert-policies-trigger-automated-investigations) iets verdachts in e-mail (zoals een bericht, bijlage, URL of gekromd gebruikersaccount). Er wordt een incident gemaakt en er wordt een automatisch onderzoek gestart.

     --- of ---

   - Een beveiligingsanalist [start een geautomatiseerd onderzoek](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) terwijl u [Bedreigingsverkenner gebruikt.](threat-explorer.md)

2. Terwijl een geautomatiseerd onderzoek wordt uitgevoerd, worden er aanvullende gegevens verzameld over het e-mailbericht in kwestie en entiteiten die aan die e-mail zijn gerelateerd. Dergelijke entiteiten kunnen bestanden, URL's en geadresseerden bevatten.  Het bereik van het onderzoek kan toenemen naarmate nieuwe en gerelateerde waarschuwingen worden geactiveerd.

3. Tijdens en na een geautomatiseerd onderzoek zijn [details en resultaten](air-view-investigation-results.md) beschikbaar. De resultaten [omvatten aanbevolen acties](air-remediation-actions.md) die kunnen worden ondernomen om te reageren op bedreigingen die zijn gevonden en te herstellen. Daarnaast is er een [playbook-logboek beschikbaar](air-view-investigation-results.md#playbook-log) waarin alle onderzoeksactiviteiten worden bij houden.

4. Het team voor beveiligingsbewerkingen bekijkt [de resultaten](air-view-investigation-results.md)en aanbevelingen van het onderzoek en kan herstelacties goedkeuren [of afwijzen.](air-review-approve-pending-completed-actions.md)

5. Als herstelacties in behandeling worden goedgekeurd (of geweigerd), wordt het geautomatiseerde onderzoek voltooid.

> [!IMPORTANT]
> In Microsoft Defender voor Office 365 worden er niet automatisch herstelacties ondernomen. Herstelacties worden alleen ondernomen na goedkeuring door het beveiligingsteam van uw organisatie.
>
> AIR-mogelijkheden besparen uw teamtijd voor beveiligingsactiviteiten door herstelacties te identificeren en de details te verstrekken die nodig zijn om een weloverwogen beslissing te nemen.

Tijdens en na elk geautomatiseerd onderzoek kan uw team voor beveiligingsbewerkingen het volgende doen:

- [Details weergeven van een waarschuwing in verband met een onderzoek](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)

- [De details van een onderzoek weergeven](air-view-investigation-results.md#view-details-of-an-investigation)

- [Acties beoordelen en goedkeuren als gevolg van een onderzoek](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Zie Air werkt voor [een gedetailleerder overzicht.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Air krijgen

AIR-mogelijkheden zijn inbegrepen in [Microsoft Defender voor Office 365,](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2)mits uw beleid en waarschuwingen zijn geconfigureerd. Als u hier hulp bij nodig hebt, volgt u de richtlijnen in Beveiligen [tegen](protect-against-threats.md) bedreigingen om de volgende beveiligingsinstellingen in te stellen of te configureren:

1. [Auditlogregistratie](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off) (moet zijn ingeschakeld)

2. [Antimalwarebeleid](protect-against-threats.md#part-1---anti-malware-protection)

3. [Bescherming tegen antiphishing](protect-against-threats.md#part-2---anti-phishing-protection)

4. [Antispambeveiliging.](protect-against-threats.md#part-3---anti-spam-protection)

5. [Veilige koppelingen en veilige bijlagen.](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)

6. [Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams.](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)

7. [Automatisch nul-uurs purge voor e-mail.](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Controleer ook het waarschuwingsbeleid van uw [organisatie,](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)met name het standaardbeleid in de categorie [Bedreigingsbeheer.](https://docs.microsoft.com/microsoft-365/compliance/alert-policies?default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welk waarschuwingsbeleid activeert automatische onderzoeken?

Microsoft 365 biedt veel ingebouwde beleidsregels voor waarschuwingen die helpen misbruik van Exchange-beheerdersmachtigingen, malwareactiviteit, potentiële externe en interne bedreigingen en risico's voor informatiebeheer te identificeren. Een aantal van [de standaardbeleidsregels voor](https://docs.microsoft.com/microsoft-365/compliance/alert-policies#default-alert-policies) waarschuwingen kan automatische onderzoeken activeren. In de volgende tabel worden de waarschuwingen beschreven die geautomatiseerde onderzoeken activeren, de ernst ervan in het Microsoft 365-beveiligingscentrum en hoe deze worden gegenereerd:

|Waarschuwing|Ernst|Hoe de waarschuwing wordt gegenereerd|
|:---|:---|:---|
|Er is een mogelijk schadelijke URL-klik gedetecteerd|**Hoog**|Deze waarschuwing wordt gegenereerd wanneer een van de volgende optreedt: <ul><li>Een gebruiker die is beveiligd door [veilige koppelingen](atp-safe-links.md) in uw organisatie, klikt op een schadelijke koppeling</li><li>Wijzigingen in wijzigingen aan wijzigingen in URL's worden aangegeven met Microsoft Defender voor Office 365</li><li>Gebruikers vervangen waarschuwingspagina's voor veilige koppelingen (op basis van het beleid voor veilige koppelingen [van uw organisatie).](set-up-atp-safe-links-policies.md)</li></ul> <p> Zie Beleid voor veilige koppelingen instellen voor meer informatie over gebeurtenissen die deze waarschuwing [activeren.](set-up-atp-safe-links-policies.md)|
|Een e-mailbericht wordt door een gebruiker gerapporteerd als malware of phish|**Informatie**|Deze waarschuwing wordt gegenereerd wanneer gebruikers in uw organisatie berichten als [phishing-e-mail](enable-the-report-message-add-in.md) melden met behulp van de invoegapp Bericht rapporteren of de invoeg voor [phishing melden.](enable-the-report-phish-add-in.md)|
|E-mailberichten met malware worden verwijderd na bezorging|**Informatie**|Deze waarschuwing wordt gegenereerd wanneer e-mailberichten met malware worden bezorgd in postvakken in uw organisatie. Als deze gebeurtenis optreedt, verwijdert Microsoft de geïnfecteerde berichten uit Exchange Online-postvakken met [auto purge van nul uur.](zero-hour-auto-purge.md)|
|E-mailberichten met phish-URL's worden na bezorging verwijderd|**Informatie**|Deze waarschuwing wordt gegenereerd wanneer berichten met phish worden bezorgd in postvakken in uw organisatie. Als deze gebeurtenis optreedt, verwijdert Microsoft de geïnfecteerde berichten uit Exchange Online-postvakken met [auto purge van nul uur.](zero-hour-auto-purge.md)|
|Er worden verdachte patronen voor het verzenden van e-mailberichten gedetecteerd|**Gemiddeld**|Deze waarschuwing wordt gegenereerd wanneer iemand in uw organisatie verdachte e-mailberichten heeft verzonden en het risico loopt dat het verzenden van e-mail wordt beperkt. Dit is een vroegtijdige waarschuwing voor gedrag dat erop kan duiden dat het account is gehackt, maar niet ernstig genoeg is om de gebruiker te beperken. <p> Hoewel het zelden gebeurt, kan een waarschuwing die door dit beleid wordt gegenereerd, een afwijking zijn. Het is echter een goed idee om te controleren of het [gebruikersaccount is gehackt.](responding-to-a-compromised-email-account.md)|
|Een gebruiker kan geen e-mail verzenden|**Hoog**|Deze waarschuwing wordt gegenereerd wanneer iemand in uw organisatie geen uitgaande e-mail kan verzenden. Dit is meestal het resultaat wanneer een [e-mailaccount wordt gehackt.](responding-to-a-compromised-email-account.md) <p> Zie Geblokkeerde gebruikers verwijderen uit de portal voor beperkte gebruikers [in Microsoft 365](removing-user-from-restricted-users-portal-after-spam.md)voor meer informatie over beperkte gebruikers.|
|

> [!TIP]
> Zie Beleidsregels voor waarschuwingen in het [Microsoft 365-compliancecentrum](https://docs.microsoft.com/microsoft-365/compliance/alert-policies)voor meer informatie over waarschuwingsbeleid of het bewerken van de standaardinstellingen.

## <a name="required-permissions-to-use-air-capabilities"></a>Vereiste machtigingen voor het gebruik van AIR-mogelijkheden

Machtigingen worden verleend via bepaalde rollen, zoals de rollen die in de volgende tabel worden beschreven:

|Taak|Vereiste rol(en)|
|---|---|
|AIR-functies instellen|Een van de volgende rollen: <ul><li>Globale beheerder</li><li>Beveiligingsbeheerder</li></ul> <p> Deze rollen kunnen worden toegewezen in [Azure Active Directory of](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) in het & [Compliancecentrum.](permissions-in-the-security-and-compliance-center.md)|
|Een geautomatiseerd onderzoek starten <p> --- of --- <p> Aanbevolen acties goedkeuren of weigeren|Een van de volgende rollen, toegewezen in [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) of in het & [Compliancecentrum:](permissions-in-the-security-and-compliance-center.md) <ul><li>Globale beheerder</li><li>Beveiligingsbeheerder</li><li>Beveiligingsoperator</li><li>Beveiligingslezer <br> --- en --- </li><li>Zoeken en purge (deze rol is alleen toegewezen in het [& Compliancecentrum.](permissions-in-the-security-and-compliance-center.md) Mogelijk moet u hier een nieuwe rollengroep maken en de rol Zoeken en purge toevoegen aan die nieuwe rollengroep.</li></ul>|
|

## <a name="required-licenses"></a>Vereiste licenties

[Licenties van Microsoft Defender voor Office 365 Abonnement 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) moeten worden toegewezen aan:

- Beveiligingsbeheerders (inclusief globale beheerders)
- Het team voor beveiligingsbewerkingen van uw organisatie (inclusief beveiligingslezers en personen met de rol **Zoeken en purge)**
- Eindgebruikers

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek bekijken](air-view-investigation-results.md#view-details-of-an-investigation)

- [Acties in behandeling controleren en goedkeuren](air-remediation-actions.md)

## <a name="see-also"></a>Zie ook

- [Automatisch onderzoek en herstel in Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Automatisch onderzoek en antwoorden in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir)
