---
title: Een phishing-aanval simuleren met Microsoft Defender voor Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen een malafide aanval simuleren en hun gebruikers trainen via phishing met behulp van simulatie gerichte training in Microsoft Defender voor Office 365.
ms.openlocfilehash: e7582b1f74266d988ecdf8f6dac49019699e2bc1
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794254"
---
# <a name="simulate-a-phishing-attack"></a>Een malafide aanval simuleren

Simulatie van simulatie aanval in Microsoft Defender voor Office 365 biedt u de mogelijkheid kwaadaardige cyberattack simulaties te doen in uw organisatie om uw beveiligingsbeleid en-procedures te testen en uw werknemers uit te breiden zodat ze zich kunnen beschermen. In dit artikel wordt u stapsgewijs begeleid bij het maken van een simulatie aanval met simulatie van aanval.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Als u een gesimuleerde malafide aanval wilt starten, opent u het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/), gaat u naar de training voor **e-mail & samenwerking** van een \> **aanval** en gaat u naar het tabblad [**simulaties**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

Selecteer onder **simulaties** **de optie + een simulatie starten**.

![Een simulatie knop starten in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> U kunt op elk gewenst moment tijdens het maken van een simulatie de werktijd opslaan en sluiten om de simulatie later verder te configureren.

## <a name="selecting-a-social-engineering-technique"></a>Een maatschappelijke techniek selecteren

Selecteer een van de vier verschillende technieken, met een curator van de [Mitre ATT&a® Framework](https://attack.mitre.org/techniques/enterprise/). Verschillende nettoladingen zijn beschikbaar voor verschillende technieken:

- **Credential oogst** probeert referenties te verzamelen door gebruikers te laten weten dat ze een bekende, op een bekende, juiste website met invoervakken voor het verzenden van een gebruikersnaam en wachtwoord in te voeren.
- **Bijlage met schadelijke software** voegt een kwaadaardige bijlage toe aan een bericht. Wanneer de gebruiker de bijlage opent, wordt willekeurige code uitgevoerd die de aanvaller helpt het apparaat van de doel te manipuleren.
- **Koppeling in bijlage** is een type referentie oogst waartoe hybride. Een aanvaller voegt een URL in een e-mailbijlage in. De URL in de bijlage volgt dezelfde methode als de oogst van de Credential.
- **Koppeling naar malware** voert sommige willekeurige code uit vanuit een bestand dat wordt gehost op een bekende bestands Sharing-service. Het bericht dat naar de gebruiker is verzonden, bevat een koppeling naar dit schadelijke bestand. Het bestand wordt geopend en Help de kwaadwillende persoon kan zich betrekken bij het doelapparaat.

> [!TIP]
> Door te klikken op **Details weergeven** in de beschrijving van de verschillende technieken, worden aanvullende informatie en de simulatie stappen voor de techniek weergegeven.
>
> ![Simulatie stappen voor het verzamelen van referenties binnen een aanvals training in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-sim-steps.png)

Wanneer u de techniek hebt geselecteerd en op **volgende** hebt geklikt, geeft u een simulatie een naam en eventueel een beschrijving.

## <a name="selecting-a-payload"></a>Een nettolading selecteren

Vervolgens moet u een nettolading selecteren in de reeds bestaande nettolading.

Nettoladingen bevatten een aantal gegevenspunten waarmee u kunt kiezen:

- **Klik op rente** telt het aantal personen dat op deze nettolading heeft geklikt.
- Voor **speld** percentage voor speling voorspelt, voorspelt het percentage personen dat met deze nettolading wordt geknoeid op basis van historische gegevens voor de nettolading van Microsoft Defender voor Office 365-klanten.
- **Gestarte simulaties** Hiermee wordt het aantal keren geteld dat deze nettolading in andere simulaties werd gebruikt.
- De **complexiteit**, die beschikbaar is via **filters**, wordt berekend op basis van het aantal indicatoren binnen de nettolading, wat er op de computer een aanval van maakt. Meer indicatoren leiden tot een lagere complexiteit.
- **Bron**, beschikbaar via **filters**, geeft aan of de nettolading is gemaakt met de Tenant of dat deze deel uitmaakt van de reeds bestaande nettoladingen catalogus van Microsoft (globaal).

![Geselecteerde nettolading binnen aanval simulatie training in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-select-payload.png)

Selecteer een nettolading in de lijst als u een voorbeeld van de nettolading met aanvullende informatie hierover wilt weergeven.

Als u uw eigen nettolading wilt maken, raadpleegt u [een nettolading maken voor de training voor simulatie van aanval](attack-simulation-training-payloads.md).

## <a name="audience-targeting"></a>Doelgroepen

Nu is het tijd om het publiek van deze simulatie te selecteren. U kunt ervoor kiezen om **alle gebruikers in uw organisatie** op te nemen of **alleen bepaalde gebruikers en groepen toe te voegen**.

Wanneer u ervoor kiest om **alleen bepaalde gebruikers en groepen toe te voegen,** hebt u de volgende mogelijkheden:

- **Voeg gebruikers toe**, zodat u kunt zoeken naar uw Tenant en de functies voor Geavanceerd zoeken en filteren, zoals het doel van gebruikers die niet zijn gericht op een simulatie in de afgelopen drie maanden.
  ![Gebruiker filteren bij simulatie van aanval in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-user-targeting.png)
- **Met importeren vanuit CSV** kunt u een vooraf gedefinieerde set gebruikers voor deze simulatie importeren.

## <a name="assigning-training"></a>Training toewijzen

U wordt geadviseerd training voor elke simulatie toe te wijzen, aangezien de werknemers die training volgen minder gevoelig zijn voor soortgelijke aanvallen.

U kunt ervoor kiezen om training voor u te laten voor u of voor de cursus zelf trainingen en modules te selecteren.

Selecteer de **einddatum** van de opleiding om ervoor te zorgen dat werknemers op een redelijke manier hun training kunnen voltooien.

> [!NOTE]
> Als u ervoor kiest cursussen en modules zelf te selecteren, kunt u de aanbevolen inhoud wel en alle beschikbare cursussen en modules weergeven.
>
> ![Aanbevolen training toevoegen in simulatie simulatie van aanval in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-add-training.png)

In de volgende stappen dient u **trainingen toe te voegen** als u ervoor hebt gekozen om zelf een training te selecteren en de landingspagina aan te passen. U kunt een voorbeeld bekijken van de pagina voor het aanbrengen van een opleiding en ook de koptekst en de tekst ervan wijzigen.

## <a name="launch-details-and-review"></a>Details starten en controleren

Nu alles is geconfigureerd, kunt u deze simulatie direct starten of plannen voor een latere datum. U moet ook kiezen wanneer u deze simulatie wilt beëindigen. We zullen niet langer de interactie met deze simulatie na de geselecteerde tijd beëindigen.

**Ondersteuning voor regio detectie van tijdzones** voor de levering van de gesimuleerde aanvals berichten voor uw werknemers gedurende hun werktijden op basis van hun regio.

Wanneer u klaar bent, klikt u op **volgende** en controleert u de details van uw simulatie. Klik op **bewerken** bij een van de onderdelen om terug te gaan en de gegevens te wijzigen die moeten worden gewijzigd. Klik vervolgens op **verzenden**.
