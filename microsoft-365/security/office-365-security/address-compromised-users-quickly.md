---
title: Adres van gekromde gebruikersaccounts met geautomatiseerd onderzoek en reactie
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection, compromised
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
ms.date: 02/25/2020
description: Lees hoe u het proces voor het detecteren en adresseren van gekromde gebruikersaccounts kunt versnellen met behulp van geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365 Abonnement 2.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1dda8c9b4aec30fd35efa153aaf032eee23b5e8a
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288739"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Adres van gekromde gebruikersaccounts met geautomatiseerd onderzoek en reactie

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


[Microsoft Defender voor Office 365 Plan 2](office-365-atp.md#microsoft-defender-for-office-365-plan-1-and-plan-2) bevat krachtige mogelijkheden voor geautomatiseerde onderzoeken en antwoorden [(AIR).](office-365-air.md) Dergelijke mogelijkheden kunnen uw team voor beveiligingsbewerkingen veel tijd en moeite besparen bij het omgaan met bedreigingen. Microsoft blijft de beveiligingsmogelijkheden verbeteren. Onlangs zijn de AIR-mogelijkheden uitgebreid met een gekromde playbook voor gebruikersbeveiliging (momenteel in preview). Lees dit artikel voor meer informatie over de gekromde playbook voor gebruikersbeveiliging. En zie het blogbericht Sneller tijd om gebruikerscompromitteerd gedrag te detecteren en te beperken met Microsoft Defender voor [Office 365](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) voor meer informatie.

![Geautomatiseerd onderzoek voor een gecompromitteerd gebruiker](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Met de gekromde playbook voor gebruikersbeveiliging kan het beveiligingsteam van uw organisatie het volgende doen:

- Snelle detectie van gekromde gebruikersaccounts;

- Beperk het bereik van een inbreuk wanneer een account wordt gehackt; en

- Reageer effectiever en efficiënter op gecompromitteerde gebruikers.

## <a name="compromised-user-alerts"></a>Meldingen over gekromde gebruikers

Wanneer een gebruikersaccount is gehackt, treedt er atypisch of anomiaal gedrag op. Phishing- en spamberichten kunnen bijvoorbeeld intern worden verzonden vanuit een vertrouwd gebruikersaccount. Defender voor Office 365 kan dergelijke problemen herkennen in e-mailpatronen en samenwerkingsactiviteit in Office 365. Wanneer dit gebeurt, worden waarschuwingen geactiveerd en wordt de risicobeperking gestart.

Hier ziet u een waarschuwing die is geactiveerd vanwege verdachte e-mails die worden verzonden:

![Waarschuwing geactiveerd vanwege verdachte verzending van e-mailberichten](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

Hier is een voorbeeld van een waarschuwing die werd geactiveerd toen een limiet voor verzenden voor een gebruiker werd bereikt:

![Waarschuwing geactiveerd door verzenden limiet bereikt](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Een gekromde gebruiker onderzoeken en beantwoorden

Wanneer een gebruikersaccount niet meer werkt, worden waarschuwingen geactiveerd. En in sommige gevallen is dat gebruikersaccount geblokkeerd en kunnen er geen e-mailberichten meer worden verzonden totdat het probleem is opgelost door het beveiligingsteam van uw organisatie. In andere gevallen wordt een geautomatiseerd onderzoek gestart dat kan leiden tot aanbevolen acties die uw beveiligingsteam moet uitvoeren.

- [Beperkte gebruikers weergeven en onderzoeken](#view-and-investigate-restricted-users)

- [Details over geautomatiseerde onderzoeken weergeven](#view-details-about-automated-investigations)

> [!IMPORTANT]
> U moet de juiste machtigingen hebben om de volgende taken te kunnen uitvoeren. Zie [Vereiste machtigingen voor het gebruik van AIR-mogelijkheden.](office-365-air.md#required-permissions-to-use-air-capabilities)

### <a name="view-and-investigate-restricted-users"></a>Beperkte gebruikers weergeven en onderzoeken

U hebt een aantal opties voor het navigeren naar een lijst met beperkte gebruikers. U kunt bijvoorbeeld in het & Compliancecentrum voor  risicobeheer \> **beperkte** \> **gebruikers gaan.** In de volgende procedure wordt de navigatie beschreven met behulp van het **dashboard** Waarschuwingen, wat een goede manier is om verschillende soorten waarschuwingen te zien die mogelijk zijn geactiveerd.

1. Ga naar <https://protection.office.com> en meld u aan.

2. Kies Waarschuwingendashboard in **het navigatiedeelvenster.** \> 

3. Kies Beperkte **gebruikers in** de widget Overige **waarschuwingen.**

   ![Andere waarschuwingswidget](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Hiermee wordt de lijst met gebruikers met beperkingen geopend.

   ![Gebruikers met beperkingen in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Selecteer een gebruikersaccount in de lijst om details weer te geven en actie te ondernemen, zoals het [vrijgeven van de beperkte gebruiker.](removing-user-from-restricted-users-portal-after-spam.md)

### <a name="view-details-about-automated-investigations"></a>Details over geautomatiseerde onderzoeken weergeven

Wanneer een geautomatiseerd onderzoek is gestart, kunt u de details en resultaten bekijken in het & compliancecentrum. Ga naar **Onderzoeken van** \> **bedreigingsbeheer** en selecteer vervolgens een onderzoek om de details ervan weer te geven.

Zie Details van een onderzoek weergeven voor [meer informatie.](air-view-investigation-results.md)

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- **Blijf op de hoogte van uw waarschuwingen.** Zoals u weet, hoe langer een compromis wordt gedetecteerd, hoe groter de kans op enorme impact en kosten voor uw organisatie, klanten en partners. Vroegtijdige detectie en tijdige reactie zijn essentieel om bedreigingen te beperken, vooral wanneer het account van een gebruiker wordt gehackt.

- Automatisering helpt uw team voor beveiligingsbewerkingen om uw **beveiligingsbewerkingen te helpen, maar niet te vervangen.** Met geautomatiseerde onderzoeks- en antwoordmogelijkheden kan een gecompromitteerde gebruiker vroeg worden gedetecteerd, maar uw team voor beveiligingsbewerkingen moet waarschijnlijk een onderzoek uitvoeren en herstel uitvoeren. Hebt u hier hulp bij nodig? Zie [Acties beoordelen en goedkeuren.](air-review-approve-pending-completed-actions.md)

- **Vertrouw niet op een verdachte aanmeldingsmelding als enige indicator.** Als een gebruikersaccount is gehackt, kan er al dan niet een verdachte aanmeldingsmelding worden verstuurd. Soms is het de reeks activiteiten die plaatsvinden nadat een account is gekromd en dat een waarschuwing activeert. Wilt u meer weten over waarschuwingen? Zie [Beleidsregels voor waarschuwingen.](../../compliance/alert-policies.md)

## <a name="next-steps"></a>Volgende stappen

- [Bekijk de vereiste machtigingen voor het gebruik van AIR-mogelijkheden](office-365-air.md#required-permissions-to-use-air-capabilities)

- [Schadelijke e-mail zoeken en onderzoeken in Office 365](investigate-malicious-email-that-was-delivered.md)

- [Meer informatie over AIR in Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Ga naar de routekaart voor Microsoft 365 om te zien wat er binnenkort beschikbaar komt en uit te rollen](https://www.microsoft.com/microsoft-365/roadmap?filters=)
