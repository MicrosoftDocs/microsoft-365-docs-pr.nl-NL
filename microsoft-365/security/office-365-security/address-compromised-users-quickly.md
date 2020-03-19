---
title: Gecompromitteerde gebruikersaccounts aanpakken met geautomatiseerd onderzoek en respons in Office 365 Advanced Threat Protection
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, reactie, sanering, bedreigingen, geavanceerd, bedreiging, bescherming, gecompromitteerd
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
description: Lees hoe u het proces van het detecteren en aanpakken van gecompromitteerde gebruikersaccounts versnellen met geautomatiseerde onderzoeks- en responsmogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: e5444b0b628be9acba029829b6fbb275b9c2f554
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/26/2020
ms.locfileid: "42808856"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Gecompromitteerde gebruikersaccounts aanpakken met geautomatiseerd onderzoek en respons

[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) bevat krachtige automatische [onderzoeks- en responsmogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR). Dergelijke mogelijkheden kunnen uw beveiligingsteam veel tijd en moeite besparen om bedreigingen aan te pakken. Microsoft blijft de beveiligingsmogelijkheden verbeteren. Onlangs werden air-mogelijkheden verbeterd met een gecompromitteerde gebruikersbeveiligingsplaybook (momenteel in preview). Lees dit artikel voor meer informatie over de gecompromitteerde gebruiker beveiliging playbook. En zie de blogpost Versnel de tijd om het compromis van gebruikers [op te sporen en erop te reageren en het bereik van inbreuken met Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) te beperken voor meer informatie.

![Geautomatiseerd onderzoek voor een gecompromitteerde gebruiker](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Het gecompromitteerde playbook voor gebruikersbeveiliging stelt het beveiligingsteam van uw organisatie in staat om:

- De detectie van gecompromitteerde gebruikersaccounts versnellen;

- Beperk de omvang van een inbreuk wanneer een account wordt gecompromitteerd; En 

- Reageer effectiever en efficiënter op gecompromitteerde gebruikers.

## <a name="compromised-user-alerts"></a>Gecompromitteerde gebruikerswaarschuwingen

Wanneer een gebruikersaccount is gecompromitteerd, treedt atypisch of afwijkend gedrag op. Phishing- en spamberichten kunnen bijvoorbeeld intern worden verzonden vanuit een vertrouwd gebruikersaccount. Office 365 Advanced Threat Protection kan dergelijke afwijkingen in e-mailpatronen en samenwerkingsactiviteiten in Office 365 detecteren. Wanneer dit gebeurt, worden waarschuwingen geactiveerd en begint het proces voor het beperken van bedreigingen.

Hier is bijvoorbeeld een waarschuwing die is geactiveerd vanwege het verzenden van verdachte e-mail:

![Waarschuwing geactiveerd vanwege het verzenden van verdachte e-mail](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

En hier is een voorbeeld van een waarschuwing die is geactiveerd toen een verzendlimiet werd bereikt voor een gebruiker:

![Waarschuwing geactiveerd door bereikte verzendlimiet](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Een gecompromitteerde gebruiker onderzoeken en erop reageren

Wanneer een gebruikersaccount is gecompromitteerd, worden waarschuwingen geactiveerd. En in sommige gevallen wordt dat gebruikersaccount geblokkeerd en kan geen verdere e-mailberichten worden verzonden totdat het probleem is opgelost door het beveiligingsteam van uw organisatie. In andere gevallen begint een geautomatiseerd onderzoek dat kan leiden tot aanbevolen acties die uw beveiligingsteam moet uitvoeren.

- [Beperkte gebruikers weergeven en onderzoeken](#view-and-investigate-restricted-users)

- [Details over geautomatiseerde onderzoeken weergeven](#view-details-about-automated-investigations)

> [!IMPORTANT]
> U moet over de juiste machtigingen beschikken om de volgende taken uit te voeren. Zie [Vereiste machtigingen voor het gebruik van AIR-mogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Beperkte gebruikers weergeven en onderzoeken

U hebt een paar opties om naar een lijst met beperkte gebruikers te navigeren. In het Office 365 Security & Compliance Center u bijvoorbeeld naar**Beperkte gebruikers**van **Threat management** > **Review** > gaan. De volgende procedure beschrijft navigatie met behulp van het dashboard **Waarschuwingen,** wat een goede manier is om verschillende soorten waarschuwingen te zien die mogelijk zijn geactiveerd.

1. Ga [https://protection.office.com](https://protection.office.com) naar en meld je aan.

2. Kies**in**het navigatiedeelvenster **Dashboard Waarschuwingen** > .

3. Kies in de widget **Andere waarschuwingen** de optie **Beperkte gebruikers**.<br/>
   ![Andere waarschuwingen widget](/microsoft-365/media/office365atp-otheralertswidget.jpg)<br/>
   Hiermee wordt de lijst met beperkte gebruikers geopend.<br/>![Beperkte gebruikers in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg) 

4. Selecteer een gebruikersaccount in de lijst om details weer te geven en actie te ondernemen, zoals [het vrijgeven van de beperkte gebruiker](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam). 

### <a name="view-details-about-automated-investigations"></a>Details over geautomatiseerde onderzoeken weergeven

Wanneer een geautomatiseerd onderzoek is gestart, u de details en resultaten ervan bekijken in het Office 365 Security & Compliance Center. Ga naar**Onderzoeken** **naar bedreigingsbeheer** > en selecteer vervolgens een onderzoek om de details ervan te bekijken.

Zie [Details van een onderzoek weergeven](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results)voor meer informatie.

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- **Blijf op de hoogte van uw waarschuwingen.** Zoals u weet, hoe langer een compromis onopgemerkt blijft, hoe groter het potentieel voor wijdverspreide impact en kosten voor uw organisatie, klanten en partners. Vroegtijdige detectie en tijdige respons zijn van cruciaal belang om bedreigingen te beperken, en vooral wanneer het account van een gebruiker is gecompromitteerd. 

- **Automatisering helpt, maar vervangt niet, uw security operations team.** Geautomatiseerde onderzoeks- en reactiemogelijkheden kunnen een gecompromitteerde gebruiker al vroeg detecteren, maar uw beveiligingsteam zal waarschijnlijk moeten deelnemen en wat onderzoek en herstel moeten doen. Heb je hier hulp bij nodig? Zie [Acties controleren en goedkeuren](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Vertrouw niet op een verdachte inlogwaarschuwing als uw enige indicator.** Wanneer een gebruikersaccount is gecompromitteerd, kan het al dan niet leiden tot een verdachte inlogmelding. Soms is het de reeks activiteiten die plaatsvinden nadat een account is gecompromitteerd die een waarschuwing activeert. Wilt u meer weten over waarschuwingen? Zie [Waarschuwingsbeleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Volgende stappen

- [Bekijk de vereiste machtigingen om AIR-mogelijkheden te gebruiken](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Schadelijke e-mail zoeken en onderzoeken in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Meer informatie over AIR in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Bezoek de Microsoft 365 Roadmap om te zien wat er binnenkort komt en uit te rollen](https://www.microsoft.com/microsoft-365/roadmap?filters=)

