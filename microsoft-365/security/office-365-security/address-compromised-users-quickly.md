---
title: Gecompromitteerde gebruikersaccounts aanpakken met geautomatiseerd onderzoek en antwoord
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming, gecompromitteerd
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
ms.date: 02/25/2020
description: Lees hoe u het proces van het detecteren en aanpakken van gecompromitteerde gebruikersaccounts versnellen met geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 60e9009ff77ebb58794ad7feaf522e1c6efc3039
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635770"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Gecompromitteerde gebruikersaccounts aanpakken met geautomatiseerd onderzoek en antwoord

[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) bevat krachtige mogelijkheden voor geautomatiseerd onderzoek en [respons](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR). Dergelijke mogelijkheden kunnen uw beveiligingsteam veel tijd en moeite besparen bij het omgaan met bedreigingen. Microsoft blijft de beveiligingsmogelijkheden verbeteren. Onlangs zijn air-mogelijkheden verbeterd met een gecompromitteerde beveiligingsplaybook voor gebruikers (momenteel in preview). Lees dit artikel voor meer informatie over het gecompromitteerde beveiligingsplaybook voor gebruikers. En zie de blogpost Versnel de [tijd om compromissen van gebruikers te detecteren en erop te reageren en het bereik van inbreuken met Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) te beperken voor meer informatie.

![Geautomatiseerd onderzoek voor een gecompromitteerde gebruiker](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Met de gecompromitteerde gebruikersbeveiligingsplaybook kan het beveiligingsteam van uw organisatie:

- De detectie van gecompromitteerde gebruikersaccounts versnellen;

- Beperk de omvang van een inbreuk wanneer een account wordt gecompromitteerd; En 

- Reageren op gecompromitteerde gebruikers effectiever en efficiënter.

## <a name="compromised-user-alerts"></a>Gecompromitteerde gebruikerswaarschuwingen

Wanneer een gebruikersaccount is gecompromitteerd, treedt atypisch of afwijkend gedrag op. Phishing- en spamberichten kunnen bijvoorbeeld intern worden verzonden vanuit een vertrouwd gebruikersaccount. Geavanceerde bedreigingsbeveiliging van Office 365 kan dergelijke afwijkingen in e-mailpatronen en samenwerkingsactiviteiten in Office 365 detecteren. Wanneer dit gebeurt, worden waarschuwingen geactiveerd en begint het proces voor het beperken van bedreigingen.

Hier is bijvoorbeeld een waarschuwing die is geactiveerd vanwege het verzenden van verdachte e-mails:

![Waarschuwing geactiveerd vanwege verdacht e-mailverzenden](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

En hier is een voorbeeld van een waarschuwing die werd geactiveerd toen een verzendlimiet voor een gebruiker werd bereikt:

![Waarschuwing geactiveerd door verzendlimiet bereikt](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Een gecompromitteerde gebruiker onderzoeken en erop reageren

Wanneer een gebruikersaccount is gecompromitteerd, worden waarschuwingen geactiveerd. En in sommige gevallen wordt dat gebruikersaccount geblokkeerd en wordt het niet meer verzonden naar e-mailberichten totdat het probleem is opgelost door het beveiligingsteam van uw organisatie. In andere gevallen begint een geautomatiseerd onderzoek dat kan resulteren in aanbevolen acties die uw beveiligingsteam moet uitvoeren.

- [Beperkte gebruikers weergeven en onderzoeken](#view-and-investigate-restricted-users)

- [Details over geautomatiseerde onderzoeken weergeven](#view-details-about-automated-investigations)

> [!IMPORTANT]
> U moet over de juiste machtigingen beschikken om de volgende taken uit te voeren. Zie [Vereiste machtigingen voor het gebruik van AIR-mogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Beperkte gebruikers weergeven en onderzoeken

U hebt een paar opties om naar een lijst met beperkte gebruikers te navigeren. In het Security & Compliance Center u bijvoorbeeld naar Gebruikers met**Review** > **beperkte**beoordeling van **het risicobeheer** > gaan. De volgende procedure beschrijft navigatie met behulp van het **dashboard Waarschuwingen,** wat een goede manier is om verschillende soorten waarschuwingen te zien die mogelijk zijn geactiveerd.

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan.

2. Kies in het navigatiedeelvenster **het dashboard Waarschuwingen** > **Dashboard**.

3. Kies **Beperkt gebruikers**in de widget **Andere waarschuwingen** .<br/>
   ![Widget Andere waarschuwingen](/microsoft-365/media/office365atp-otheralertswidget.jpg)<br/>
   Hiermee wordt de lijst met beperkte gebruikers geopend.<br/>![Beperkte gebruikers in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg) 

4. Selecteer een gebruikersaccount in de lijst om details weer te geven en actie te ondernemen, zoals [het vrijgeven van de beperkte gebruiker.](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam) 

### <a name="view-details-about-automated-investigations"></a>Details over geautomatiseerde onderzoeken weergeven

Wanneer een geautomatiseerd onderzoek is gestart, u de details en resultaten zien in het Security & Compliance Center. Ga naar **Threat management** > **Investigations**en selecteer vervolgens een onderzoek om de details te bekijken.

Zie [Details van een onderzoek weergeven](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results)voor meer informatie.

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- **Blijf op de hoogte van uw waarschuwingen.** Zoals u weet, hoe langer een compromis onopgemerkt blijft, hoe groter het potentieel voor wijdverspreide impact en kosten voor uw organisatie, klanten en partners. Vroegtijdige detectie en tijdige respons zijn van cruciaal belang om bedreigingen te beperken, en vooral wanneer het account van een gebruiker wordt gecompromitteerd. 

- **Automatisering helpt, maar vervangt niet uw security operations team.** Geautomatiseerde onderzoeks- en reactiemogelijkheden kunnen een gecompromitteerde gebruiker al vroeg detecteren, maar uw beveiligingsteam zal waarschijnlijk moeten deelnemen en wat onderzoek en herstel moeten uitvoeren. Heb je hier hulp bij nodig? Zie [Acties controleren en goedkeuren](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Vertrouw niet op een verdachte aanmeldingswaarschuwing als uw enige indicator.** Wanneer een gebruikersaccount is gecompromitteerd, kan het al dan niet leiden tot een verdachte aanmeldingswaarschuwing. Soms is het de reeks activiteiten die plaatsvinden nadat een account is gecompromitteerd, waardoor een waarschuwing wordt geactiveerd. Wilt u meer weten over waarschuwingen? Zie [Waarschuwingsbeleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Volgende stappen

- [Controleer de vereiste machtigingen voor het gebruik van AIR-mogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Schadelijke e-mail zoeken en onderzoeken in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Meer informatie over AIR in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Bezoek de Microsoft 365 Roadmap om te zien wat er binnenkort komt en uitrol](https://www.microsoft.com/microsoft-365/roadmap?filters=)

