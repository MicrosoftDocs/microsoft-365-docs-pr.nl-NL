---
title: Een proefversie van Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Meer informatie over het plannen en uitvoeren van een proefprogramma voor SharePoint Syntex in uw organisatie.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327090"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Een proefversie van Microsoft SharePoint Syntex

In dit artikel wordt beschreven hoe u een proefprogramma kunt instellen en uitvoeren om SharePoint Syntex implementeren in uw organisatie. Daarnaast worden aanbevolen aanbevolen aanbevolen procedures voor de proefversie.

## <a name="sign-up-for-a-trial"></a>Registreren voor een proefabonnement

De proefversie van SharePoint Syntex biedt 30 dagen toegang tot 300 gebruikers.

> [!NOTE]
> Er worden maximaal 300 gebruikers opgenomen in de proefversie om ervoor te zorgen dat er automatisch 1 miljoen AI Builder-tegoeden worden toegevoegd. U hoeft geen 300 gebruikers op te nemen voor een proefabonnement om te slagen.

U kunt de proefversie van een van de volgende bronnen krijgen:

- De [SharePoint Syntex productpagina](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- De [Microsoft 365-beheercentrum](https://admin.microsoft.com)
    1.  Meld u aan bij het [Microsoft 365-beheercentrum](https://admin.microsoft.com).
    2.  Ga naar   >  **Factureringsaankoopservices.**
    3.  Schuif omlaag naar de **sectie Invoegtoepassingen.**
    4.  Selecteer op SharePoint Syntex tegel **Details.**
    5.  Selecteer **Gratis proefversie downloaden.**
    6.  Als u de proefversie wilt bevestigen, volgt u de resterende wizardstappen.

U moet een globale Microsoft 365 of factureringsbeheerder zijn om een proefabonnement te activeren.

### <a name="who-should-be-involved-in-a-trial"></a>Wie moet betrokken zijn bij een proefversie

|Rol  |Activiteit  |
|---------|---------|
|Microsoft 365 globale beheerder of factureringsbeheerder    |     De proefversie activeren en licenties toewijzen    |
|Microsoft 365 globale beheerder of SharePoint beheerder     |   Inhoudscentra SharePoint Syntex configureren en maken      |
|Zakelijke gebruikers     |    Modelbouw en testen     |

### <a name="before-you-activate-a-trial"></a>Voordat u een proefabonnement activeert

Als u een proefabonnement SharePoint Syntex plannen, moet u rekening houden met de volgende factoren:

- De meest zinvolle tests worden uitgevoerd op scenario's en gegevens in de 'echte wereld'.
- U kunt een proefversie van een SharePoint Syntex slechts eenmaal per tenant activeren.

Een test- of demo-tenant kan worden gebruikt als een 'dry run' om de activeringsstappen en beheerbesturingselementen te doorlopen. Maar het is waarschijnlijk het beste om modelbouw te evalueren op een productie-tenant.

Als u de waarde van een proefabonnement op een productie-tenant wilt maximaliseren, zijn planning en zakelijke betrokkenheid essentieel. U moet een of meer zakelijke gebieden betrekken om drie-tot-zes gebruiksgevallen te identificeren die mogelijk kunnen worden aangepakt door SharePoint Syntex. Deze gebruiksgevallen moeten:

- Neem scenario's op die kunnen worden opgelost met het formulierverwerkingsmodel of het documentkennismodel.
- Hebt u een duidelijk inzicht in het doel van eventuele geëxtraheerde metagegevens; u kunt bijvoorbeeld opmaak of automatisering weergeven met behulp van Power Automate. Hoewel SharePoint Syntex is gericht op het classificeren van documenten en het extraheren van metagegevens, is de waarde die u wilt kwantificeren wat deze metagegevens in staat stelt.
- Gebaseerd zijn op een gedefinieerde set gegevens; bijvoorbeeld specifieke SharePoint sites of bibliotheken. Een veelvoorkomende misvatting van SharePoint Syntex is dat algemene doelmodellen kunnen worden toegepast op alle organisatie-inhoud. Een nauwkeurigere weergave is dat modellen zijn gemaakt om specifieke zakelijke problemen op specifieke locaties op te lossen.

Al deze gebruiksgevallen zijn mogelijk niet geschikt voor SharePoint Syntex. Het doel van een kwaliteitsproef is niet om te bewijzen dat SharePoint Syntex alle scenario's past. In plaats daarvan moet de proefversie u helpen de waarde van het product beter te begrijpen.

Identificeer voor elk van de geplande gebruiksgevallen gebruikers die onderwerpexperts zijn in de gerelateerde inhoud of het bijbehorende proces. Het maken van SharePoint Syntex modellen is gericht op domeinexperts in de inhoud, in plaats van op IT-professionals of ontwikkelaarsbronnen.

## <a name="activate-a-trial"></a>Een proefversie activeren

Wanneer u een proefabonnement start, moet u het volgende doen:

- Licenties toewijzen aan de relevante gebruikers.
- Voer [extra installatie van SharePoint Syntex.](set-up-content-understanding.md)
    - Mogelijk wilt u extra [inhoudscentra maken.](create-a-content-center.md)

Nadat de proefversie is geactiveerd, kunt u modellen maken en bestanden verwerken. Zie [richtlijnen voor het maken van modellen.](create-a-content-center.md)

## <a name="during-a-trial"></a>Tijdens een proefabonnement

Proefperioden zijn beperkt, dus het is het beste om in eerste instantie te kijken of SharePoint Syntex documenten kan classificeren en metagegevens voor de gedefinieerde gebruiksgevallen kunt extraheren. Nadat de proefperiode is afgelopen, kunt u evalueren hoe de metagegevens kunnen worden gebruikt.

## <a name="after-a-trial"></a>Na een proefversie

Op basis van het resultaat van de proefversie kunt u bepalen of u doorgaat met het productiegebruik van SharePoint Syntex.

### <a name="proceed-to-production-use"></a>Ga verder met het gebruik van de productie

Om de continuïteit van de service te waarborgen, moet u het vereiste aantal licenties kopen en deze licenties toewijzen aan gebruikers. Proefgebruikers die aan het einde van de proefperiode geen volledige licentie hebben, kunnen hun SharePoint Syntex.

Mogelijk moet u een schatting maken van het verwachte gebruik van formulieren voor het verwerken en plannen van de verwachte hoeveelheid AI Builder-tegoed. Zie De [ai-opbouwcapaciteit schatten die voor u het](https://powerapps.microsoft.com/ai-builder-calculator/)beste bij u is.

### <a name="dont-proceed-to-production-use"></a>Ga niet verder met het gebruik van de productie

Als u na de proefversie geen licenties koopt:

- U kunt geen nieuwe modellen maken.
- Bibliotheken met modellen worden niet meer automatisch geclassificeerd of modellen extraheren.
- Eerder geclassificeerde bestanden of geëxtraheerde metagegevens worden niet beïnvloed. 
- Inhoudscentra en documentkennismodellen worden niet automatisch verwijderd. Deze blijven beschikbaar voor gebruik als u besluit om in de toekomst licenties te kopen.
- Formulierenverwerkingsmodellen worden opgeslagen in het exemplaar Common Data Services (CDS) van de standaardOmgeving van Power Platform. Deze kunnen worden gebruikt met toekomstige licenties voor SharePoint Syntex of met AI Builder-mogelijkheden in het Power Platform.

## <a name="see-also"></a>Zie ook

[Microsoft SharePoint Syntex: Aan de slag](adoption-getstarted.md)
