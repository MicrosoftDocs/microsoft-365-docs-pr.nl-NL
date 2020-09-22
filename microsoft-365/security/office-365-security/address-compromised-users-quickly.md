---
title: Opgetaste gebruikersaccounts met een automatisch onderzoek en antwoord
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herbemiddeling, bedreiging, Geavanceerd, bedreiging, beveiliging, compromissen
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
description: Meer informatie over hoe u het proces voor het opsporen en adresseren van gebruikersaccounts met automatisch onderzoek en antwoord mogelijkheden in Office 365 Advanced Threat Protection (abonnement 2) kunt versnellen.
ms.openlocfilehash: fa648b33180cab7d70348dc4d1d6e64930ecff99
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48201229"
---
# <a name="address-compromised-user-accounts-with-automated-investigation-and-response"></a>Opgetaste gebruikersaccounts met een automatisch onderzoek en antwoord

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Office 365 Advanced Threat Protection Plan 2](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide#office-365-atp-plan-1-and-plan-2) bevat krachtige mogelijkheden voor [automatisch onderzoek en reacties](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (lucht). Een dergelijk vermogen kan uw bedrijfsactiviteiten team een veel tijd en een inspanning van bedreigingen bieden. Microsoft blijft de functionaliteit van beveiligingsfuncties verbeteren. Onlangs werden lucht mogelijkheden uitgebreid met een in de preview-versie Playbook (momenteel in preview-versie). Lees dit artikel voor meer informatie over de beveiligings Playbook van de aanvaller. En de snelheid van de blogberichten [kunnen detecteren en beantwoorden, en beantwoorden met Office 365 ATP](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Speed-up-time-to-detect-and-respond-to-user-compromise-and-limit/ba-p/977053) voor aanvullende informatie.

![Automatisch onderzoek voor een gemanipuleerde gebruiker](/microsoft-365/media/office365atp-compduserinvestigation.jpg)

Met de gemanipuleerde Playbook voor gebruikersbeveiliging kan het beveiligingsteam van uw organisatie:

- Het detecteren van gebruikersaccounts versnellen.

- U beperkt het reikwijdte van een schending wanneer een account wordt aangetast. en

- U kunt gebruikers effectiever en efficiënter beantwoorden.

## <a name="compromised-user-alerts"></a>Gebruikers waarschuwingen met compromissen

Wanneer er sprake is van een onveilig gedrag van een gebruikersaccount. Malafide en spamberichten kunnen bijvoorbeeld intern worden verzonden via een vertrouwd gebruikersaccount. Met Office 365 Advanced Threat Protection kunt u afwijkingen detecteren in e-mail patronen en activiteiten voor samenwerking in Office 365. Wanneer dit gebeurt, worden waarschuwingen geactiveerd en wordt het probleem met risicobeperking gestart.

Hier ziet u bijvoorbeeld een waarschuwing die werd geactiveerd vanwege verdachte e-mail die wordt verzonden:

![Waarschuwing veroorzaakt vanwege verdachte e-mail verzonden](/microsoft-365/media/office365atp-suspiciousemailsendalert.jpg)

En hier volgt een voorbeeld van een waarschuwing die werd geactiveerd wanneer een verzendings limiet voor een gebruiker is bereikt:

![Waarschuwing geactiveerd door limiet is bereikt](/microsoft-365/media/office365atp-sendinglimitreached.jpg)

## <a name="investigate-and-respond-to-a-compromised-user"></a>Een door een gebruiker gemanipuleerd onderzoek beantwoorden en beantwoorden

Wanneer een gebruikersaccount wordt gekraakt, worden waarschuwingen geactiveerd. In sommige gevallen is het niet mogelijk om verdere e-mailberichten te verzenden, zodat u geen e-mailberichten kunt verzenden totdat het probleem is verholpen door het team van het beveiligingsactiviteiten van uw organisatie. In andere gevallen begint een geautomatiseerd onderzoek waarmee de aanbevolen acties kunnen worden uitgevoerd die uw beveiligingsteam moet uitvoeren.

- [Gebruikers met beperkte toegang weergeven en onderzoeken](#view-and-investigate-restricted-users)

- [Details van geautomatiseerde onderzoeken weergeven](#view-details-about-automated-investigations)

> [!IMPORTANT]
> U moet de juiste machtigingen hebben om de volgende taken uit te voeren. Zie de [vereiste machtigingen voor het gebruik van lucht mogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities).

### <a name="view-and-investigate-restricted-users"></a>Gebruikers met beperkte toegang weergeven en onderzoeken

U kunt op een aantal manieren naar een lijst met gebruikers met beperkte toegang navigeren. In dit voorbeeld kunt u in het beveiligings & compliance de gebruikers **met**  >  **Review**  >  **beperkte toegang**controleren. In de volgende procedure wordt de navigatie in het dashboard **waarschuwingen** beschreven, wat een goede manier is om diverse soorten waarschuwingen te zien die mogelijk zijn geactiveerd.

1. Ga naar [https://protection.office.com](https://protection.office.com) en meld u aan.

2. Kies in het navigatiedeelvenster **meldingen**  >  **Dashboard**.

3. Kies in de **andere waarschuwings** widget de optie **gebruikers met beperkte beperkingen**.

   ![Andere meldingen](/microsoft-365/media/office365atp-otheralertswidget.jpg)

   Hiermee opent u de lijst met gebruikers met beperkte rechten.<br/>![Gebruikers met beperkingen in Office 365](/microsoft-365/media/office365atp-restrictedusers.jpg)

4. Selecteer een gebruikersaccount in de lijst om details weer te geven en actie te ondernemen, zoals [de beperkte gebruiker vrijgeven](https://docs.microsoft.com/microsoft-365/security/office-365-security/removing-user-from-restricted-users-portal-after-spam).

### <a name="view-details-about-automated-investigations"></a>Details van geautomatiseerde onderzoeken weergeven

Wanneer een geautomatiseerd onderzoek is begonnen, kunt u de details en resultaten bekijken in het beveiligings & nalevings centrum. Ga naar onderzoek voor **Threat Management**  >  **Investigations**en selecteer een onderzoek om de details ervan weer te geven.

Zie [Details van een onderzoek weergeven](https://docs.microsoft.com/microsoft-365/security/office-365-security/air-view-investigation-results)voor meer informatie.

## <a name="keep-the-following-points-in-mind"></a>Let op de volgende punten

- **Blijf op de hoogte van uw meldingen**. Aangezien u weet, loopt het langer een aanval niet, hoe groter de potentiële impact en kosten voor uw organisatie, klanten en partners. Vroegtijdige detectie en tijdig antwoord zijn essentieel voor het beperken van bedreigingen en vooral wanneer het account van een gebruiker wordt aangetast.

- **Automatisering assistt, maar het team van uw beveiligingsactiviteiten wordt niet vervangen**. Met de functie voor automatisch onderzoek en antwoord kunt u een gemanipuleerde gebruiker op een vroeg moment detecteren, maar het team van uw beveiligingsactiviteiten dient waarschijnlijk een oplossing te bieden voor onderzoek en herstel. Hebt u hulp nodig? Zie [acties controleren en goedkeuren](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air#review-and-approve-actions).

- **Vertrouw niet op een verdachte aanmeldingen als u maar wilt**. Als een gebruikersaccount wordt gekraakt, wordt dit mogelijk veroorzaakt door een verdachte inlog signaal. Soms is het de reeks activiteiten die zich voordoen nadat een account is geknoeid en een melding wordt geactiveerd. Wilt u meer weten over waarschuwingen? Zie [waarschuwings beleid](https://docs.microsoft.com/microsoft-365/compliance/alert-policies).

## <a name="next-steps"></a>Volgende stappen

- [Controleer de vereiste machtigingen voor het gebruik van lucht mogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air?view=o365-worldwide#required-permissions-to-use-air-capabilities)

- [Schadelijke e-mail zoeken en onderzoeken in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide)

- [Meer informatie over AIR in Microsoft Defender ATP](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Ga naar het Microsoft 365-wegwijzer om te zien wat er binnenkort beschikbaar is en rollen](https://www.microsoft.com/microsoft-365/roadmap?filters=)

