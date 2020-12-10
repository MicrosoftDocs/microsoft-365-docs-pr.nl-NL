---
title: Een phishing-aanval simuleren met Microsoft Defender voor
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Leer hoe u phishing-aanvallen simuleert en gebruikers traint voor phishing met aanvals training in Microsoft Defender voor Office 365.
ms.openlocfilehash: 8f5f457f60c81fe961282f33bb8c37f4d9e27aab
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616102"
---
# <a name="simulate-a-phishing-attack"></a>Een malafide aanval simuleren

Met behulp van aanval met aanvals Simulator via Microsoft Defender voor Office 365 kunt u kwaadaardige, kwaadaardige aanvallen uitvoeren op uw organisatie om uw beveiligingsbeleid en-praktijken te testen en de werknemers van uw organisatie de mogelijkheid te bieden om de aandacht te vestigen op aanvallen. Met behulp van een malafide aanval met behulp van een aanval via een aanval met behulp van een aanval via een aanval

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Als u een gesimuleerde malafide aanval wilt starten, gaat u naar het [Microsoft 365-Beveiligingscentrum](https://security.microsoft.com/). Klik onder **e-mail & samenwerken** op **aanvals Simulator** en schakel over naar het tabblad [**simulaties**](https://security.microsoft.com/attacksimulator?viewid=simulations) .

Selecteer onder **simulaties** **de optie + een simulatie starten**.

![Een simulatie knop starten in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> U kunt op elk gewenst moment tijdens het maken van een simulatie de mogelijkheid opslaan en sluiten om de simulatie op een later tijdstip verder te configureren.

## <a name="selecting-a-social-engineering-technique"></a>Een maatschappelijke techniek selecteren

Selecteer een van de vier verschillende technieken, met een curator van de [Mitre ATT&a® Framework](https://attack.mitre.org/techniques/enterprise/). Verschillende nettoladingen zijn beschikbaar voor verschillende technieken.

- **Credential oogst** probeert referenties te verzamelen van medewerkers door ze te nemen aan een bekende website met invoervakken om een gebruikersnaam en wachtwoord in te dienen.
- **Bijlage met schadelijke software** voegt een kwaadaardige bijlage toe aan een bericht. Bij het openen van deze bijlage worden enkele willekeurige code uitgevoerd waarmee de aanvaller het apparaat van de doel kan bereiken.
- **Koppeling in bijlage** is een type referentie oogst waartoe hybride. Een aanvaller voegt een URL in een e-mailbijlage in. De URL in de bijlage volgt dezelfde methode als de oogst van de Credential.
- **Koppeling naar malware** voert een willekeurige code uit vanuit een bestand dat wordt gehost op een bekende site voor het delen van bestanden. Er wordt een koppeling naar dit schadelijke bestand toegevoegd aan het bericht dat naar de bestemming is verzonden en met de opdracht door erop te klikken wordt het bestand uitgevoerd en helpt de kwaadwillende persoon het apparaat van de doel te betrekken.

> [!TIP]
> Als u in de beschrijving van elke methode op **Details weergeven** klikt, wordt er meer informatie weergegeven over de techniek en de bewerkingsstappen voor die methode.
>
> ![Simulatie stappen voor het verzamelen van referenties binnen een aanvals training in Microsoft 365 Beveiligingscentrum](../../media/attack-sim-preview-sim-steps.png)

Wanneer u de techniek hebt geselecteerd en op volgende hebt geklikt, geeft u op de **volgende** wijze uw simulatie een naam en eventueel een beschrijving.

## <a name="selecting-a-payload"></a>Een nettolading selecteren

Vervolgens moet u een nettolading selecteren in de reeds bestaande nettolading.

Nettoladingen bevatten een aantal gegevenspunten waarmee u kunt kiezen:

- **Klik op rente** telt het aantal personen dat op deze nettolading heeft geklikt.
- Voor **speld** percentage voor speling voorspelt, voorspelt het percentage personen die in deze nettolading worden aangetast op basis van historische gegevens voor deze nettolading voor Microsoft Defender voor Office 365-klanten.
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
