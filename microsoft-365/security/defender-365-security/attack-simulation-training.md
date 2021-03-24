---
title: Een phishing-aanval simuleren met Microsoft Defender voor Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Beheerders kunnen leren hoe ze phishingaanvallen kunnen simuleren en hun gebruikers kunnen trainen op phishingpreventie met behulp van training voor aanvalssimulatie in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.openlocfilehash: 27279f927a15ea94ae84112ffdc23d88ea42d2ff
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059001"
---
# <a name="simulate-a-phishing-attack"></a>Een phishing-aanval simuleren

Met training voor aanvalssimulatie in Microsoft Defender voor Office 365 kunt u goedaardige cyberaanvallensimulaties uitvoeren op uw organisatie om uw beveiligingsbeleid en -procedures te testen, en uw werknemers trainen om hun bekendheid te vergroten en hun gevoeligheid voor aanvallen te verminderen. In dit artikel wordt u beschreven hoe u een gesimuleerde phishing-aanval maakt met behulp van training voor een aanvalssimulatie.

Zie Aan de slag met de trainingstraining [Aanvalssimulatie](attack-simulation-training-get-started.md)voor informatie over de training voor aanvalssimulaties.

Als u een gesimuleerde phishing-aanval wilt starten, opent u het [Microsoft 365-beveiligingscentrum,](https://security.microsoft.com/)gaat u naar E-mail **& samenwerking** Aanvalssimulatietraining en gaat u naar het tabblad \>  [**Simulaties.**](https://security.microsoft.com/attacksimulator?viewid=simulations)

Selecteer **onder Simulaties** de **optie + Een simulatie starten.**

![Een simulatieknop starten in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-launch.png)

> [!NOTE]
> Op elk moment tijdens het maken van de simulatie kunt u opslaan en sluiten om de simulatie op een later tijdstip te blijven configureren.

## <a name="selecting-a-social-engineering-technique"></a>Een social engineering-techniek selecteren

Selecteer uit 4 verschillende technieken, samengesteld uit het [MITRE ATT-&CK® framework.](https://attack.mitre.org/techniques/enterprise/) Er zijn verschillende payloads beschikbaar voor verschillende technieken:

- **Referentiesoogst** probeert referenties te verzamelen door gebruikers naar een bekende website te nemen met invoervakken om een gebruikersnaam en wachtwoord in te dienen.
- **Malwarebijlage** voegt een schadelijke bijlage toe aan een bericht. Wanneer de gebruiker de bijlage opent, wordt willekeurige code uitgevoerd die de aanvaller helpt het apparaat van het doel te compromitteerden.
- **Koppeling in bijlage** is een type referentieoogst hybride. Een aanvaller voegt een URL in een e-mailbijlage in. De URL in de bijlage volgt dezelfde techniek als referentieoogst.
- **Als u een koppeling naar malware** maakt, wordt een willekeurige code uitgevoerd van een bestand dat wordt gehost op een bekende service voor het delen van bestanden. Het bericht dat naar de gebruiker wordt verzonden, bevat een koppeling naar dit schadelijke bestand. Het bestand openen en de aanvaller helpen het apparaat van het doel te compromitteerden.
- **De URL van** Station by is de plaats waar de schadelijke URL in het bericht de gebruiker naar een vertrouwde website brengt die in stilte codecode op het apparaat van de gebruiker wordt uitgevoerd en/of installeert.

> [!TIP]
> Als u op **Details weergeven klikt** in de beschrijving van elke techniek, worden meer informatie en de simulatiestappen voor de techniek weergegeven.
>
> ![Simulatiestappen voor de oogst van referenties in de training voor aanvalssimulatie in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-sim-steps.png)

Nadat u de techniek hebt geselecteerd en op Volgende hebt **geklikt,** geeft u de simulatie een naam en eventueel een beschrijving.

## <a name="selecting-a-payload"></a>Een laadvermogen selecteren

Vervolgens moet u een payload selecteren in de bestaande payloadcatalogus.

Payloads hebben een aantal gegevenspunten om u te helpen kiezen:

- **Klikfrequentie** telt hoeveel personen op deze payload hebben geklikt.
- **Voorspelde snelheid** van compromissen voorspelt het percentage personen dat wordt gecompromitteerd door deze payload op basis van historische gegevens voor het laadvermogen in Microsoft Defender voor Office 365-klanten.
- **Met gestarte simulaties** wordt het aantal keren geteld dat deze payload is gebruikt in andere simulaties.
- **Complexiteit ,** beschikbaar via **filters,** wordt berekend op basis van het aantal indicatoren binnen de payload waarin wordt aangestuurd op een aanval. Meer indicatoren leiden tot een lagere complexiteit.
- **Bron**, beschikbaar via **filters**, geeft aan of de payload is gemaakt op uw tenant of deel uitmaakt van de bestaande payloadcatalogus van Microsoft (globaal).

![Geselecteerde payload in de training voor aanvalssimulatie in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-select-payload.png)

Selecteer een laadvermogen in de lijst om een voorbeeld van de payload te bekijken met aanvullende informatie.

Als u uw eigen payload wilt maken, leest u [een payload maken voor training voor aanvalssimulatie.](attack-simulation-training-payloads.md)

## <a name="audience-targeting"></a>Doelgroeptargeting

Nu is het tijd om het publiek van deze simulatie te selecteren. U kunt ervoor kiezen om **alle gebruikers in uw organisatie op te** nemen of alleen specifieke gebruikers en groepen op te **nemen.**

Wanneer u ervoor kiest om **alleen specifieke gebruikers en groepen** op te nemen, kunt u het volgende doen:

- **Voeg gebruikers** toe, waarmee u de zoekfunctie voor uw tenant kunt gebruiken, evenals geavanceerde zoek- en filtermogelijkheden, zoals gebruikers die de afgelopen drie maanden niet zijn getarget door een simulatie.
  ![Gebruikersfilters in training voor aanvalssimulatie in microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-user-targeting.png)
- **Met Importeren uit CSV** kunt u een vooraf gedefinieerde set gebruikers importeren voor deze simulatie.

## <a name="assigning-training"></a>Training toewijzen

Het is raadzaam om training toe te wijzen voor elke simulatie, omdat werknemers die een training volgen, minder gevoelig zijn voor soortgelijke aanvallen.

U kunt ervoor kiezen om training aan u toe te laten of zelf cursussen en modules te selecteren.

Selecteer de **einddatum van de** training om ervoor te zorgen dat werknemers hun training tijdig voltooien.

> [!NOTE]
> Als u ervoor kiest om zelf cursussen en modules te selecteren, kunt u nog steeds de aanbevolen inhoud en alle beschikbare cursussen en modules zien.
>
> ![Aanbevolen training toevoegen in training voor aanvalssimulatie in het Microsoft 365-beveiligingscentrum](../../media/attack-sim-preview-add-training.png)

In de volgende stappen moet  u trainingen toevoegen als u ervoor hebt gekozen om deze zelf te selecteren en uw trainingslandingspagina aan te passen. U kunt een voorbeeld van de landingspagina van de training bekijken en de koptekst en de hoofdtekst ervan wijzigen.

## <a name="launch-details-and-review"></a>Details starten en controleren

Nu alles is geconfigureerd, kunt u deze simulatie direct starten of plannen voor een latere datum. U moet ook kiezen wanneer u deze simulatie wilt beëindigen. We stoppen met het vastleggen van de interactie met deze simulatie na de geselecteerde tijd.

**Schakel regiobewuste tijdzonebezorging** in om gesimuleerde aanvalsberichten te leveren aan uw werknemers tijdens hun werkuren op basis van hun regio.

Wanneer u klaar bent, klikt u op **Volgende** en bekijkt u de details van de simulatie. Klik op **Bewerken** op een van de onderdelen om terug te gaan en de details te wijzigen die moeten worden gewijzigd. Wanneer u klaar bent, klikt u op **Verzenden.**
