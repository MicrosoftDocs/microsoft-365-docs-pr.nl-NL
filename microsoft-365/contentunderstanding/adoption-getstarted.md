---
title: 'Microsoft SharePoint Syntex: Aan de slag'
description: Meer informatie over het gebruik en implementeren SharePoint Syntex in uw organisatie om u te helpen uw zakelijke problemen op te lossen.
ms.author: samanro
author: samanro
manager: pamgreen
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
ms.openlocfilehash: 8a5442fcf8dd50cdee6be97ba7c9bbf5e21408a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288153"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex: Aan de slag

Denk aan de intelligente inhoudsservices die beschikbaar zijn in SharePoint Syntex als drie onderdelen:

- **Inhoudskennis:** Maak AI-modellen zonder code voor het classificeren en extraheren van informatie uit inhoud om metagegevens automatisch toe te passen voor kennisdetectie en hergebruik. Meer informatie over [het begrijpen van inhoud.](document-understanding-overview.md)
- **Inhoudsverwerking:** Automatiseer het vastleggen, opnemen en categoriseren van inhoud en stroomlijn inhoudsgerichte processen met behulp van Power Automate. Meer informatie over [inhoudsverwerking.](form-processing-overview.md)
- **Naleving van inhoud:** Beheer en beheer inhoud om de beveiliging en het beheer te verbeteren met integratie in Microsoft Information Protection.

Met nieuwe AI-services en -mogelijkheden kunt u apps voor inhoudskennis en classificatie rechtstreeks in de inhoudsbeheerstroom bouwen met SharePoint Syntex. Er zijn twee verschillende manieren om uw inhoud te begrijpen. Het modeltype dat u gebruikt, is gebaseerd op bestandsindeling en use case:

| Formulierverwerking | Documentbegrip |
|:-------|:-------|
| Gemaakt vanuit documentbibliotheek. | Gemaakt in het inhoudscentrum, onderdeel van SharePoint Syntex. |
| Model gemaakt in AI builder. | Model gemaakt in de eigen interface. |
| Wordt gebruikt voor semi-gestructureerde bestandsindelingen. | Wordt gebruikt voor ongestructureerde bestandsindelingen. |
| Settable classifier. | Trainable classifier with optional extractors. |
| Beperkt tot één bibliotheek. | Kan worden toegepast op meerdere bibliotheken. |
| Train op PDF, JPG, PNG-indeling, totaal 50 MB/500 pp. | Trainen op 5 tot 10 pdf-, Office- of e-mailbestanden, inclusief negatieve voorbeelden. |

Zie Verschillen tussen documentkennis en formulierverwerkingsmodellen voor een completere vergelijking van [de mogelijkheden.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Testscenario's identificeren om te optimaliseren

Als u zich wilt voorbereiden SharePoint Syntex in uw organisatie, moet u eerst de scenario's begrijpen waarin deze nuttig zijn. Het 'waarom' helpt bepalen welk model nodig is en hoe u uw organisatie structureert op basis van waar het model wordt toegepast. Hier zijn een paar scenario's waarin het begrijpen van documenten uw organisatie kan helpen:

- **Inhoudsverwerking:** Procescontracten, werkafschriften en andere formulier-achtige documenten. Neem de formulieren op, train het model om de velden te begrijpen en toe te geven en voer de formulieren door om de gegevens automatisch te verzamelen. Zie Formulierverwerkingsoverzicht [voor meer informatie.](form-processing-overview.md)
- **Factuuranalyse:** Haal de relevante gegevens uit uw facturen en zorg ervoor dat ze voldoen aan het beleid of op de juiste manier worden verwerkt.

Denk na over manieren SharePoint Syntex uw organisatie kan helpen:

- Bedrijfsprocessen automatiseren
- Zoeknauwkeurigheid verbeteren
- Compliancerisico's beheren

Als u bedenkt welke zakelijke scenario's u moet overwegen, stelt u zich de volgende vragen:

- Lost dit een echt probleem op?
- Wordt het veel gebruikt of heeft het een grote impact?
- Is het verkrijgbaar?
- Kunt u succes meten?

Geef prioriteit aan scenario's op basis van impact en implementatiegemak. Maak uw eerste focusgebied groter effectscenario's die ook eenvoudig kunnen worden geïmplementeerd. Geef prioriteit aan scenario's met lagere effecten die moeilijk te implementeren zijn.

Gebruik de [voorbeeldscenario's en gebruik cases om](adoption-scenarios.md) ideeën te vragen over hoe u uw SharePoint Syntex in uw organisatie kunt gebruiken.

## <a name="identify-roles--responsibilities"></a>Rollen en & verantwoordelijkheden identificeren

Bepalen wie in uw organisatie de modellen gaat maken en beheren? Mogelijk gaat het om de volgende rollen:

| SharePoint/Knowledge Admin | Power Platform-beheerder | Knowledge manager | Modeleigenaar |
|:-------|:-------|:-------|:-------|
| AAD-rol| AAD-rol | AAD-rol | Kampioenen |
| Formulierverwerking configureren | Algemene gegevensserviceomgeving configureren voor formulierverwerking | Gebruiksgevallen verzamelen | Zakelijke gebruiksgevallen verzamelen |
| Inhoudscentra en machtigingen beheren| AIB-tegoed kopen en toewijzen | Best practices opstellen en modelanalyses bekijken | Modellen maken en toepassen |

Knowledge manager, Eigenaar van bedrijfsprocessen en eigenaar van inhoudsmodellen maken voorbeeldmodellen en maken de acceptatie in de organisatie voor.
Anderen die mogelijk betrokken zijn: Compliancebeheerder, Taxonomiebeheerders.

Waar worden de modellen gebouwd en toegepast? Zijn er bestaande processen of opslagplaatsen die kunnen worden verbeterd?

- Formulierverwerking: bepaal welke sites actie voor formulierverwerking krijgen.
- Documentkennis: U kunt meerdere inhoudscentra maken voor verschillende zakelijke gebieden.

## <a name="strategic-positioning"></a>Strategische positionering

Werk samen met belanghebbenden om ervoor te zorgen dat ze zijn afgestemd op de strategie voor het gebruik van SharePoint Syntex. Onderzoek en geef de volgende informatiebronnen om u te helpen bij deze positionering:

- Bedrijfsresultaten:
  - Mogelijke fiscale resultaten
  - Mogelijke resultaten van flexibiliteit
  - Sjabloon voor bedrijfsresultaten
- Stakeholders/Exec sponsor buy-in/alignment
  - Business case decks
  - Financiële modellen
  - Bedrijfsbereidheid - cultuur

## <a name="identify-stakeholders"></a>Belanghebbenden identificeren

Identificeer de belanghebbenden voor uw project.

|Rol |Verantwoordelijkheden |Department |
|:-------|:-------|:--------|
| Executive sponsor(s)   | Visie en waarden op hoog niveau communiceren met het bedrijf   |  Uitvoerend leiderschap   |
| Project lead(en) | Toezicht houden op het volledige proces voor het uitvoeren en uitrollen van de lancering | Project beheer |
| Kennisbeheerders| De inhoudscentra maken en beheren | IT of andere afdeling|
| Inhoudsmanagers en modeleigenaars| Use cases verzamelen en modellen maken en toepassen | Elke afdeling|
| Kampioenen | Hulp bij het evangeliseren en beheren van bezwaarafhandeling | Elke afdeling (personeel) |
| Tenantbeheerder | Instellingen op tenantniveau configureren | IT-afdeling|
| Power Platform-beheerder| Veelgebruikte omgeving voor gegevensservices configureren | IT-afdeling|

> [!Note]
> Hoewel we u adviseren om elk van deze rollen tijdens de implementatie te laten vervullen, is het mogelijk dat u ze niet allemaal nodig hebt om aan de slag te gaan met uw geïdentificeerde oplossing.

## <a name="readiness-checklist"></a>Controlelijst gereedheid

Als u klaar wilt zijn voor het implementeren SharePoint Syntex, moet u het volgende doen:

![Gereedheid voor inhoudskennis](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. De eindtoestand plannen
    - Documentkennismodellen zijn de middelen, niet het einde.
    - Plan voor het benutten van de waarde van geëxtraheerde metagegevens met:
      - Zoeken
      - Opmaak filteren en weergeven
      - Compliance
      - Automatisering
2. Identificeren
    - Inzicht in bestaande functies voor informatiearchitectuur en inhoudsbeheer.
    - Zijn bestaande inhoudstypen goede kandidaten voor modellen?
    - Welke bestaande processen worden verbeterd met metagegevens?
3. Design
    - Ontwerp uw benadering van informatiearchitectuur, beheerde metagegevens en inhoudstypen.
    - Ontwerp het proces voor definitie, creatie, beheer.

## <a name="engage-your-organization"></a>Uw organisatie betrekken

1. Identificeer ringhouders, bevestig scenario's en ontwikkel projectplannen.
1. Instellingen configureren en licenties toepassen.
1. Begin bewust te worden en training te volgen: wervingskampioenen.
1. Rol in fasen uit.  
1. Feedback verzamelen en itereren.
1. Naarmate het gebruik toeneemt, wordt het plan voor eventuele AI Builder-tegoeden zo nodig groter.

## <a name="see-also"></a>Zie ook

[Scenario's en use cases voor SharePoint Syntex](adoption-scenarios.md)
