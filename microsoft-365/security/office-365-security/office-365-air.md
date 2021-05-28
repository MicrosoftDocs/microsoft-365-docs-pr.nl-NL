---
title: Geautomatiseerd onderzoek en antwoord in Microsoft Defender voor Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 01/29/2021
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
ms.openlocfilehash: 7632efb2014af9f55e9cad700bceeeabe555fb8b
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/28/2021
ms.locfileid: "52696572"
---
# <a name="automated-investigation-and-response-air-in-microsoft-defender-for-office-365"></a>Automated investigation and response (AIR) in Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender voor Office 365](defender-for-office-365.md) bevat krachtige mogelijkheden voor automatisch onderzoek en antwoord (AIR) die uw teamtijd en inspanning voor beveiligingsbewerkingen kunnen besparen. Wanneer waarschuwingen worden geactiveerd, is het aan uw beveiligingsteam om deze waarschuwingen te controleren, prioriteit te geven en hierop te reageren. Het kan overweldigend zijn om het volume van binnenkomende waarschuwingen bij te houden. Het automatiseren van een aantal van deze taken kan u helpen.

Met AIR kan uw beveiligingsteam efficiënter en effectiever werken. Air-mogelijkheden omvatten geautomatiseerde onderzoeksprocessen in reactie op bekende bedreigingen die vandaag de dag bestaan. Passende herstelacties wachten op goedkeuring, zodat uw beveiligingsteam effectief kan reageren op gedetecteerde bedreigingen. Met AIR kan uw beveiligingsteam zich richten op taken met een hogere prioriteit zonder belangrijke waarschuwingen uit het oog te verliezen die worden geactiveerd.

In dit artikel wordt het volgende beschreven:

- De [algehele stroom van AIR](#the-overall-flow-of-air);
- [Air krijgen;](#how-to-get-air) en
- De [vereiste machtigingen voor](#required-permissions-to-use-air-capabilities) het configureren of gebruiken van AIR-mogelijkheden.
- Wijzigingen die binnenkort worden doorgevoerd in uw beveiligingscentrum

Dit artikel bevat ook [de volgende stappen](#next-steps)en informatiebronnen voor meer informatie.

## <a name="the-overall-flow-of-air"></a>De algehele stroom van AIR

Er wordt een waarschuwing geactiveerd en een beveiligingss playbook start een geautomatiseerd onderzoek, wat resulteert in bevindingen en aanbevolen acties. Hier is de algehele stroom van AIR, stap voor stap:

1. Een geautomatiseerd onderzoek wordt op een van de volgende manieren gestart:
   - Een [waarschuwing wordt geactiveerd door iets](#which-alert-policies-trigger-automated-investigations) verdachts in e-mail (zoals een bericht, bijlage, URL of een gekromd gebruikersaccount). Er wordt een incident gemaakt en er wordt een geautomatiseerd onderzoek gestart. of
   - Een [beveiligingsanalist start een geautomatiseerd onderzoek tijdens](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer) het gebruik van Threat [Explorer.](threat-explorer.md)
2. Terwijl een geautomatiseerd onderzoek wordt uitgevoerd, worden gegevens verzameld over de e-mail in kwestie en entiteiten die betrekking hebben op die e-mail. Dergelijke entiteiten kunnen bestanden, URL's en geadresseerden bevatten. Het bereik van het onderzoek kan toenemen naarmate nieuwe en gerelateerde waarschuwingen worden geactiveerd.
3. Tijdens en na een geautomatiseerd onderzoek zijn [details en resultaten](air-view-investigation-results.md) beschikbaar om te bekijken. Resultaten zijn [onder andere aanbevolen](air-remediation-actions.md) acties die kunnen worden ondernomen om te reageren op en eventuele gevonden bedreigingen te corrigeren.
4. Uw beveiligingsteam bekijkt de [onderzoeksresultaten en](air-view-investigation-results.md)aanbevelingen en keurt herstelacties [goed of weigert.](air-review-approve-pending-completed-actions.md)
5. Aangezien herstelacties in behandeling zijn goedgekeurd (of geweigerd), wordt het geautomatiseerde onderzoek voltooid.

In Microsoft Defender voor Office 365 worden er geen herstelacties automatisch ondernomen. Herstelacties worden alleen ondernomen na goedkeuring door het beveiligingsteam van uw organisatie. Air-mogelijkheden besparen uw teamtijd voor beveiligingsbewerkingen door herstelacties te identificeren en de details te verstrekken die nodig zijn om een weloverwogen beslissing te nemen.

Tijdens en na elk geautomatiseerd onderzoek kan uw beveiligingsteam:

- [Details weergeven over een waarschuwing in verband met een onderzoek](air-view-investigation-results.md#view-details-about-an-alert-related-to-an-investigation)
- [De resultaten van een onderzoek weergeven](air-view-investigation-results.md#view-details-of-an-investigation)
- [Acties beoordelen en goedkeuren als gevolg van een onderzoek](air-review-approve-pending-completed-actions.md)

> [!TIP]
> Zie Hoe AIR werkt voor een [uitgebreider overzicht.](automated-investigation-response-office.md)

## <a name="how-to-get-air"></a>Air krijgen

Air-mogelijkheden zijn opgenomen in [Microsoft Defender voor Office 365](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2), mits uw beleid en waarschuwingen zijn geconfigureerd. Hebt u hulp nodig? Volg de richtlijnen in [Beschermen tegen bedreigingen om](protect-against-threats.md) de volgende beveiligingsinstellingen in te stellen of te configureren:

- [Auditregistratie](../../compliance/turn-audit-log-search-on-or-off.md) (moet zijn ingeschakeld)
- [Anti-malwarebeleid](protect-against-threats.md#part-1---anti-malware-protection-in-eop)
- [Bescherming tegen phishing](protect-against-threats.md#part-2---anti-phishing-protection)
- [Beveiliging tegen ongewenste e-mail](protect-against-threats.md#part-3---anti-spam-protection-in-eop)
- [Safe Koppelingen en Safe bijlagen](protect-against-threats.md#part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365)
- [Veilige bijlagen voor SharePoint, OneDrive en Microsoft Teams](protect-against-threats.md#part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on)
- [Auto purge van nul uur voor e-mail](protect-against-threats.md#zero-hour-auto-purge-for-email-in-eop)

Controleer bovendien het waarschuwingsbeleid van uw [organisatie,](../../compliance/alert-policies.md)met name het standaardbeleid in de categorie [Bedreigingsbeheer.](../../compliance/alert-policies.md#default-alert-policies)

## <a name="which-alert-policies-trigger-automated-investigations"></a>Welk waarschuwingsbeleid activeert geautomatiseerde onderzoeken?

Microsoft 365 bevat veel ingebouwde waarschuwingsbeleidsregels die helpen bij het identificeren Exchange beheerdersmachtigingen misbruik, malwareactiviteit, potentiële externe en interne bedreigingen en risico's voor informatiebeheer. Verschillende van de [standaardwaarschuwingsbeleidsregels](../../compliance/alert-policies.md#default-alert-policies) kunnen geautomatiseerde onderzoeken activeren. In de volgende tabel worden de waarschuwingen beschreven die automatisch onderzoek in gang zetten, de ernst ervan in het Microsoft 365 beveiligingscentrum en hoe deze worden gegenereerd:

|Waarschuwing|Ernst|Hoe de waarschuwing wordt gegenereerd|
|---|---|---|
|Er is een potentieel schadelijke URL-klik gedetecteerd|**Hoog**|Deze waarschuwing wordt gegenereerd wanneer een van de volgende problemen optreedt: <ul><li>Een gebruiker die is beveiligd [Safe koppelingen](safe-links.md) in uw organisatie klikt op een schadelijke koppeling</li><li>Vonniswijzigingen voor URL's worden geïdentificeerd door Microsoft Defender voor Office 365</li><li>Gebruikers overschrijven Safe waarschuwingspagina's voor koppelingen (op basis van het beleid [Safe koppelingen van uw organisatie).](set-up-safe-links-policies.md)</li></ul> <p> Zie Beleidsregels voor koppelingen instellen Safe voor meer informatie over gebeurtenissen [die deze waarschuwing activeren.](set-up-safe-links-policies.md)|
|Een e-mailbericht wordt door een gebruiker gerapporteerd als malware of phish|**Informatief**|Deze waarschuwing wordt gegenereerd wanneer gebruikers in uw organisatie berichten rapporteren als [phishing-e-mail](enable-the-report-phish-add-in.md)met behulp van de [invoeging Rapportbericht](enable-the-report-message-add-in.md) of de invoeging Phishing melden.|
|E-mailberichten met malware worden na bezorging verwijderd|**Informatief**|Deze waarschuwing wordt gegenereerd wanneer e-mailberichten met malware worden bezorgd in postvakken in uw organisatie. Als deze gebeurtenis optreedt, verwijdert Microsoft de geïnfecteerde berichten uit Exchange Online postvakken met [automatische nul-uurs purge](zero-hour-auto-purge.md).|
|E-mailberichten met phish-URL's worden na bezorging verwijderd|**Informatief**|Deze waarschuwing wordt gegenereerd wanneer berichten met phish worden bezorgd in postvakken in uw organisatie. Als deze gebeurtenis optreedt, verwijdert Microsoft de geïnfecteerde berichten uit Exchange Online postvakken met [automatische nul-uurs purge](zero-hour-auto-purge.md).|
|Verdachte e-mail verzenden patronen worden gedetecteerd|**Gemiddeld**|Deze waarschuwing wordt gegenereerd wanneer iemand in uw organisatie verdachte e-mailberichten heeft verzonden en het risico bestaat dat het verzenden van e-mail wordt beperkt. De waarschuwing is een vroegtijdige waarschuwing voor gedrag dat kan aangeven dat het account is gecompromitteerd, maar niet ernstig genoeg om de gebruiker te beperken. <p> Hoewel dit zeldzaam is, kan een waarschuwing die door dit beleid wordt gegenereerd, een afwijking zijn. Het is echter een goed idee om te [controleren of het gebruikersaccount is gehackt.](responding-to-a-compromised-email-account.md)|
|Een gebruiker mag geen e-mail verzenden|**Hoog**|Deze waarschuwing wordt gegenereerd wanneer iemand in uw organisatie geen uitgaande e-mail mag verzenden. Deze waarschuwing is meestal het resultaat wanneer een [e-mailaccount wordt gehackt.](responding-to-a-compromised-email-account.md) <p> Zie Geblokkeerde gebruikers verwijderen uit de portal Beperkte gebruikers [in](removing-user-from-restricted-users-portal-after-spam.md)Microsoft 365.|
|

> [!TIP]
> Zie Waarschuwingsbeleid in het Microsoft 365 compliancecentrum voor meer informatie over waarschuwingsbeleid of het bewerken [van de standaardinstellingen.](../../compliance/alert-policies.md)

## <a name="required-permissions-to-use-air-capabilities"></a>Vereiste machtigingen voor het gebruik van AIR-mogelijkheden

Machtigingen worden verleend via bepaalde rollen, zoals de machtigingen die in de volgende tabel worden beschreven:

|Taak|Rol(en) vereist|
|---|---|
|AIR-functies instellen|Een van de volgende rollen: <ul><li>Globale beheerder</li><li>Beveiligingsbeheerder</li></ul> <p> Deze rollen kunnen worden toegewezen [in](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Azure Active Directory of in het [compliancecentrum & Beveiligingscentrum.](permissions-in-the-security-and-compliance-center.md)|
|Een geautomatiseerd onderzoek starten <p> --- of --- <p> Aanbevolen acties goedkeuren of weigeren|Een van de volgende rollen, toegewezen [in](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) Azure Active Directory of in het [compliancecentrum & beveiliging:](permissions-in-the-security-and-compliance-center.md) <ul><li>Globale beheerder</li><li>Beveiligingsbeheerder</li><li>Beveiligingsoperator</li><li>Beveiligingslezer <br> --- en --- </li><li>Zoeken en zuiveren (deze rol wordt alleen toegewezen in het [beveiligings- & Compliancecentrum](permissions-in-the-security-and-compliance-center.md). Mogelijk moet u daar een nieuwe rollengroep maken en de rol Zoeken en zuiveren toevoegen aan die nieuwe rollengroep.</li></ul>|

## <a name="required-licenses"></a>Vereiste licenties

[Microsoft Defender voor Office 365 abonnement 2-licenties](defender-for-office-365.md#microsoft-defender-for-office-365-plan-1-and-plan-2) moet worden toegewezen aan:

- Beveiligingsbeheerders (inclusief globale beheerders)
- Het beveiligingsteam van uw organisatie (inclusief beveiligingslezers en personen met de rol Zoeken **en** zuiveren)
- Eindgebruikers

## <a name="changes-are-coming-soon-in-your-security-center"></a>Wijzigingen worden binnenkort doorgevoerd in uw beveiligingscentrum

Als u air-mogelijkheden al gebruikt in Microsoft Defender voor Office 365, ziet u enkele wijzigingen in het verbeterde [Microsoft 365 beveiligingscentrum.](../defender/overview-security-center.md)

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="Unified Action Center":::

Het nieuwe en verbeterde beveiligingscentrum brengt AIR-mogelijkheden samen in [Microsoft Defender voor](defender-for-office-365.md) Office 365 en in Microsoft Defender voor [Eindpunt.](../defender-endpoint/automated-investigations.md) Met deze updates en verbeteringen kan jouw beveiligingsteam informatie bekijken over geautomatiseerde onderzoeken en herstelacties in e-mail, samenwerkingsinhoud, gebruikersaccounts en apparaten, allemaal op één plaats.

> [!TIP]
> Het nieuwe Microsoft 365 <https://security.microsoft.com> () vervangt de volgende centra:
>
> - Office 365 Beveiligings- & compliancecentrum ( <https://protection.office.com> )
> - Microsoft Defender-beveiligingscentrum ( <https://securitycenter.windows.com> )
>
> Naast het wijzigen van de URL is er een nieuw uiterlijk, ontworpen om uw beveiligingsteam een gestroomlijnde ervaring te geven, met zichtbaarheid voor meer detecties van bedreigingen op één plaats.

### <a name="what-to-expect"></a>Wat u kunt verwachten

In de volgende tabel vindt u wijzigingen en verbeteringen die worden doorgevoerd in AIR in Microsoft Defender voor Office 365.

|Item|Wat verandert er?|
|---|---|
|**Pagina Onderzoeken**|De **bijgewerkte pagina Onderzoeken** komt beter overeen met wat u ziet in [Microsoft Defender voor Eindpunt.](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations) U ziet enkele algemene opmaak- en stijlwijzigingen die zijn afgestemd op de nieuwe, geïntegreerde **weergave Onderzoeken.** De onderzoeksgrafiek heeft bijvoorbeeld een meer geïntegreerde indeling.|
|**Tabblad Gebruikers**|Het **tabblad Gebruikers** is nu het tabblad **Postvakken.** Details over gebruikers worden weergegeven op het **tabblad Postvak.**|
|**Tabblad E-mail**|Het **tabblad E-mail** is verwijderd. Ga naar **het tabblad Entiteiten** om een lijst met e-mail- en e-mailclusteritems te bekijken.|
|**Tabblad Entiteiten**|Het **tabblad Entiteiten** heeft een tab-in-tabstijl die een overzichtsweergave bevat en de mogelijkheid om te filteren op entiteitstype. Het **tabblad Entiteiten** bevat nu naast de optie Openen in **Verkenner** ook de optie Ga op zoek naar.  U kunt nu [Threat Explorer of geavanceerd](threat-explorer.md) zoeken [gebruiken](../defender-endpoint/advanced-hunting-overview.md) om entiteiten en bedreigingen te zoeken en op resultaten te filteren.|
|**Tabblad Acties**|Het tabblad **Bijgewerkte** acties bevat nu een tabblad **Acties in** behandeling en een **tabblad Actiesgeschiedenis.** Acties kunnen worden goedgekeurd (of geweigerd) in een zijvenster dat wordt geopend wanneer u een actie in behandeling selecteert.|
|**Tabblad Bewijs**|Een nieuw **tabblad Bewijs** toont de belangrijkste entiteitsbetuigingen die betrekking hebben op acties. Acties met betrekking tot elk bewijs kunnen worden goedgekeurd (of geweigerd) in een zijvenster dat wordt geopend wanneer u een actie in behandeling selecteert.|
|**Actiecentrum**|Het **bijgewerkte Actiecentrum** () brengt lopende en voltooide acties samen [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) op e-mail, apparaten en identiteiten. Zie Actiecentrum voor meer informatie. (Zie Actiecentrum voor meer [informatie.)](../defender/m365d-action-center.md)|
|**Pagina Incidenten**|De **pagina** Incidenten correleert nu meerdere onderzoeken samen om een beter overzicht van onderzoeken te bieden. ([Meer informatie over incidenten](../defender/incidents-overview.md).)|
|

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek bekijken](air-view-investigation-results.md#view-details-of-an-investigation)
- [Lopende acties controleren en goedkeuren](air-remediation-actions.md)
