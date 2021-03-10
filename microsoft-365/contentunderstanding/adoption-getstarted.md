---
title: 'Microsoft SharePoint Syntex: Aan de slag'
description: Leer hoe u SharePoint Syntex gebruikt en implementeert in uw organisatie om u te helpen bij het oplossen van uw zakelijke problemen.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597056"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex: Aan de slag

De intelligente inhoudsservices die beschikbaar zijn in SharePoint Syntex, zien er drie uit:

- **Inhoudskennis: ai-modellen** zonder code maken om informatie te classificeren en extraheren uit inhoud om automatisch metagegevens toe te passen op kennisdetectie en hergebruik. Meer informatie over informatie [over het begrijpen van inhoud.](document-understanding-overview.md)
- **Inhoudsverwerking:** Automatiseer het vastleggen, ingestion en categoriseren van inhoud en stroomlijn inhoudsgerichte processen met Power Automate. Meer informatie over [inhoudsverwerking.](form-processing-overview.md)
- **Inhouds compliance:** Beheer en beheer inhoud om de beveiliging en het beheermodel te verbeteren met integratie met Microsoft Information Protection.

Met nieuwe AI-services en -mogelijkheden kunt u inhoudskennis en classificatie-apps rechtstreeks in de inhoudsbeheerstroom maken met SharePoint Syntex. Er zijn twee verschillende manieren om uw inhoud te begrijpen. Het modeltype dat u gebruikt is gebaseerd op de bestandsindeling en use case:

| Formulierverwerking | Documentkennis |
|:-------|:-------|
| Gemaakt vanuit documentbibliotheek. | Gemaakt in het inhoudscentrum, onderdeel van SharePoint Syntex. |
| Model gemaakt in AI Builder. | Model gemaakt in native interface. |
| Wordt gebruikt voor semi-gestructureerde bestandsindelingen. | Wordt gebruikt voor ongestructureerde bestandsindelingen. |
| Classificatie in te stellen. | Trainable classifier with optional extractors. |
| Beperkt tot één bibliotheek. | Kan op meerdere bibliotheken worden toegepast. |
| Train on PDF, JPG, PNG format, total 50 MB/500 pp. | Train op PDF-, Office- of e-mailbestanden van 5-10, inclusief negatieve voorbeelden. |

Zie Verschil tussen het begrip van documenten en formulierverwerkingsmodellen voor een completere vergelijking van [de mogelijkheden.](difference-between-document-understanding-and-form-processing-model.md)

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Scenario's voor pilotbedrijf identificeren om te optimaliseren

Om u voor te bereiden op het gebruik van SharePoint Syntex in uw organisatie, moet u eerst de scenario's begrijpen waarin dit nuttig zal zijn. Aan de hand van het 'waarom' kunt u bepalen welk model er nodig is en hoe u uw organisatie kunt structureren op basis van waar het model wordt toegepast. Hier zijn enkele scenario's waarin documentkennis uw organisatie kan helpen:

- **Inhoudsverwerking:** Procescontracten, werkverklaringen en andere formulier-achtige documenten. Gebruik de informatie over de formulieren, train het model om de velden te begrijpen en toe te geven, en voer vervolgens uw formulieren uit om de gegevens automatisch te verzamelen. Zie Formulierverwerkingsoverzicht [voor meer informatie.](form-processing-overview.md)
- **Factuuranalyse:** Haal de relevante details uit uw facturen en zorg ervoor dat ze voldoen aan het beleid of op de juiste manier worden verwerkt.

Denk na over manieren waarop SharePoint Syntex uw organisatie kan helpen:

- Bedrijfsprocessen automatiseren
- De nauwkeurigheid van zoekopdrachten verbeteren
- Nalevingsrisico's beheren

Stel uzelf de volgende vragen wanneer u bedenkt welke zakelijke scenario's u moet overwegen:

- Is er een echt probleem opgelost?
- Wordt deze veel gebruikt of heeft deze brede impact?
- Is het verkrijgen mogelijk?
- Kunt u succes meten?

Geef prioriteit aan scenario's op basis van impact en gebruiksgemak. Maak uw oorspronkelijke focusgebied meer impactscenario's die ook eenvoudig kunnen worden geïmplementeerd. Stel lagere impactscenario's op die moeilijk kunnen worden geïmplementeerd.

Gebruik de volgende voorbeeldscenario's om ideeën te vragen over hoe u SharePoint Syntex kunt gebruiken in uw organisatie.

### <a name="scenario-track-data-from-invoices-with-form-processing"></a>Scenario: Gegevens van facturen bijhouden met formulierverwerking

U kunt bijvoorbeeld een proces instellen met SharePoint Syntex en Power Automate om facturen bij te houden en te bewaken.

1. Stel een bibliotheek in voor de opslag van de factuurdocumenten.
1. Train het model om velden in de documenten te herkennen.
1. Extraheren de velden die u wilt bijhouden in een lijst.
1. Stel een stroom in om u op de hoogte te stellen voor specifieke gebeurtenissen, zoals:
    - Er is een nieuwe factuur toegevoegd.
    - De einddatum van een factuur is voorbij.
    - Een factuur is voor een bedrag dat groter is dan het bedrag voor automatische goedkeuring.

![Facturen bijhouden en controleren met SharePoint Syntex en Power Automate](../media/content-understanding/process-invoices-flow.png)

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Bespaar tijd en geld door automatisch gegevens op te halen uit de facturen in plaats van dat u dit handmatig doet.
- Verminder potentiële fouten en zorg voor betere naleving door werkstromen te gebruiken om facturen te controleren en u op de hoogte te stellen van eventuele problemen.

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a>Scenario: informatie van contracten bijhouden met inzicht in documenten

U kunt bijvoorbeeld een proces instellen voor het vaststellen van contracten die uw bedrijf heeft met andere bedrijven of personen. Stel een model in om belangrijke gegevens op te halen uit die contracten, zoals de naam van de klant, kosten, datums of andere belangrijke informatie, en voeg de gegevens toe aan de bibliotheek als velden die u snel kunt bekijken. Pas een bewaarlabel toe op de documentbibliotheek om ervoor te zorgen dat contracten niet kunnen worden verwijderd vóór een bepaalde periode, zodat de regels van uw bedrijf op de juiste manier worden nageleefd.

1. Begin in het inhoudscentrum en maak een nieuw documentkennismodel voor contracten.
1. Upload voorbeelddocumenten voor positieve en negatieve voorbeelden en voer vervolgens de training uit om contractdocumenten te identificeren en de resultaten te bekijken.
1. Train de extractor om velden in de contracten te identificeren, zoals de naam, kosten en datum van de klant, en test vervolgens de extractor.
1. Wanneer het model klaar is, moet u het model toepassen op een bibliotheek waar u contracten kunt uploaden.
1. Een bewaarlabel toepassen op het datumveld, zodat contracten voor een periode in de bibliotheek worden bewaard.

![Contracten bijhouden en bewaken met SharePoint Syntex en bewaarlabels](../media/content-understanding/process-contracts-flow.png)

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Bespaar tijd en geld door gegevens automatisch op te halen uit de contracten in plaats van dat u dat handmatig doet.
- Zorg voor betere naleving door bewaarlabels te gebruiken om ervoor te zorgen dat de contracten op de juiste manier worden behouden.

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a>Scenario: Vermijd risico's met processen voor recordbeheer, documentbeheer en naleving op basis van SharePoint Syntex

Risico's verkleinen is een veelvoorkomende doelstelling voor de meeste bedrijven. Mogelijk hebt u het volgende nodig:

- Een betere manier om informatiebeheer voor uw tenant te bieden/af te dwingen.
- Ter verbetering van het systeem voor de classificatie van documenten, e-mailberichten en andere vormen van communicatie die worden beschouwd als 'records' voor projecten.
- Om ontvangstbevestigingen, contracten, en meer te controleren, om ervoor te zorgen dat het bedrijfsbeleid wordt nageleefd.
- Om ervoor te zorgen dat projecten alle documentatie hebben die nodig is voor naleving.

Stel enkele processen voor naleving van SharePoint Syntex in om documenten en formulieren die een beter beheermodel nodig hebben, vast te leggen en op de juiste manier te classificeren, te controleren en te markeren. U kunt op SharePoint Syntex vertrouwen om inhoud automatisch te classificeren in plaats van dat u op eindgebruikers vertrouwt om handmatig een label te geven of het nalevingsteam om handmatig beheerregels en archivering toe te passen. En u kunt een vereenvoudigde zoekervaring inschakelen, gegevensvolumes beheren, recordbeheer en bewaarbeleid toepassen, zorgen voor naleving en best practices voor archiveren en opslokken.

Wanneer u dit scenario automatiseert, kunt u zich veilig voelen:

- Naleving wordt gehandhaafd en het risico wordt beperkt.
- Taxonomie- en recordbeheer wordt consistent en nauwkeurig toegepast.
- Inhoudsvolumes worden beheerd.
- Werknemers kunnen eenvoudig de juiste informatie vinden in de juiste context.

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a>Scenario: Gegevens uit eerder niet-toegankelijke documenten vastleggen

De meeste organisaties bevatten grote opslagplaatsen van juridische documenten, beleidsregels, contracten, HR-documenten en beheerrichtlijnen. Gebruik deze gegevens om waardevolle informatie op te halen, zoals projecten, gebruiksinformatie, thema's, personen, geografische gebieden, en dergelijke.

Een HR-directeur moet bijvoorbeeld snel toegang hebben tot alle HR-documenten, inclusief cv's, HR-beleid en andere formulieren. En ze willen snel de benodigde informatie uit cv's en andere HR-gerelateerde documenten identificeren zonder de documenten handmatig te moeten doorzenden. Ze zijn op zoek naar een oplossing waarmee ze snel de informatie kunnen vinden die ze nodig hebben, zonder handmatig te hoeven kijken naar duizenden cv's, HR-beleidsregels en andere documentatie die verspreid kan zijn over verschillende sites.

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Ontsluit kennis van digitale inhoud.
- Classificeer HR-beleid, cv's, verkoopdocumenten, technische blauwdrukken, accountplannen en extraheer informatie.
- Vind snel de juiste informatie of het document dat u zoekt.
- Krijg direct toegang tot de meest recente informatie.
- Zoektijden verminderen.

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a>Scenario: De gegevensverwerking verbeteren om inzichten te krijgen & analyses

Een farmaceutisch bedrijf kan bijvoorbeeld SharePoint Syntex gebruiken om informatie op te halen uit FDA-documenten om vragen van leidinggevenden te beantwoorden. Als u de antwoorden gemakkelijker toegankelijk hebt, kunt u de benodigde tijd voor het produceren van deze antwoorden verminderen en de beschikbaarheid van gegevens vergroten om accuratere antwoorden op vragen van het management te genereren.

Een projectmanager moet bijvoorbeeld snel antwoord geven op productgerelateerde vragen van mijn managementteam. Ze moeten informatie en metrische gegevens met betrekking tot query's vinden in één samengevoegd dashboard. Ze zijn op zoek naar een oplossing die de informatie haalt die ze nodig hebben uit productlabels, productpalets en andere materialen, en genereert een geconsolideerd rapport dat ze kunnen gebruiken bij het rapporteren aan hun leiderschapsteam.

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Verminder de tijd om antwoorden te maken.
- De beschikbaarheid van gegevens vergroten.
- Geef nauwkeurigere antwoorden.

### <a name="scenario-automate-order-processing"></a>Scenario: Verwerking van order automatiseren

Met SharePoint Syntex kunt u de tijd beperken van de handmatige verwerking van klantorders. U kunt bijvoorbeeld orders van fax, e-mail of papier uploaden naar SharePoint via OCR-verwerking en vervolgens de metagegevens uit die orders extraheren, zodat u er met behulp van geautomatiseerde processen aan kunt voldoen.

Een toeleveringsmanager wil bijvoorbeeld fouten beperken die worden veroorzaakt door handmatige gegevensinvoer. Ze willen handmatige controle en gegevensinvoer van binnenkomende klantorders (papier, fax of e-mail) voorkomen om fouten in bedrijfssystemen te beperken. Ze willen een oplossing die AI- en machine learning-technieken toepassen om binnenkomende orderinformatie te valideren, kerngegevens op te halen en automatisch in hun ERP-systeem te pushen voor orderuitvulling en afstemming.

Wanneer u dit scenario automatiseert, kunt u ervoor zorgen dat:

- De nauwkeurigheid van de order en verzending neemt toe.
- De kosten of heffingen die verband houden met order- of verzendfouten, worden verlaagd.
- Vertragingen in facturering of vertragingen nemen af.
- Personeelskosten worden verlaagd.

### <a name="scenario-simplify-visa-renewal-process"></a>Scenario: Het verlengingsproces voor visa vereenvoudigen

SharePoint Syntex kan u helpen herinneringen en verlengingen te automatiseren voor belangrijke contractinformatie. Een HR-directeur moet er bijvoorbeeld voor zorgen dat de visa's van werknemers up-to-date zijn en/of op tijd worden verlengd. Ze willen mensen een eenvoudig en intuïtief proces bieden voor het bijwerken van hun Visa. Ze hebben een oplossing nodig om verlengingsdatums op te halen uit contracten en werknemers automatisch herinneringen te sturen wanneer hun verlengingsdatums nadert.

Wanneer u dit scenario automatiseert, kunt u ervoor zorgen dat:

- Niet-nalevingsniveaus worden beperkt.
- Het aantal handmatige herinneringen wordt verminderd.
- Het aantal boetes voor niet-naleving wordt verminderd.

## <a name="identify-roles--responsibilities"></a>Rollen en & identificeren

Bepalen wie in uw organisatie de modellen gaat bouwen en beheren? Mogelijk zijn hierbij de volgende rollen betrokken:

| SharePoint/Knowledge Admin | Beheer van Het Power-platform | Knowledge Manager | Modeleigenaar |
|:-------|:-------|:-------|:-------|
| AAD-rol| AAD-rol | AAD-rol | Kampioenen |
| Formulierverwerking configureren | Veelgebruikte gegevensserviceomgeving configureren voor de verwerking van formuliergegevens | Use cases verzamelen | Bedrijfsgebruiks zaken verzamelen |
| Inhoudscentra en machtigingen beheren| AIB-tegoed kopen en toewijzen | Best practices opstellen en modelanalyses bekijken | Modellen maken en toepassen |

Knowledge Manager, Eigenaar van bedrijfsproces en eigenaar van inhoudsmodel maken voorbeeldmodellen en acceptatie van kampioenen in de organisatie.
Andere betrokken zijn: beheerder voor naleving, taxonomiebeheerders.

Waar worden de modellen gemaakt en toegepast? Zijn er bestaande processen of opslagplaatsen die kunnen worden verbeterd?

- Formulierverwerking: bepaal welke sites de bewerking Formulier kunnen krijgen.
- Documentkennis: U kunt meerdere inhoudscentra voor verschillende bedrijfsgebieden maken.

## <a name="strategic-positioning"></a>Strategische plaatsing

Werk samen met belanghebbenden om ervoor te zorgen dat ze zijn afgestemd op de strategie voor het gebruik van SharePoint Syntex. Onderzoek en geef de volgende informatiebronnen ter hulp bij deze plaatsing:

- Bedrijfsresultaten:
  - Mogelijke fiscale resultaten
  - Mogelijke flexibelere resultaten
  - Sjabloon voor bedrijfsresultaat
- Belanghebbenden/Exec sponsor buy-in/alignment
  - Business case decks
  - Financiële modellen
  - Gereedheid voor het bedrijf - cultuur

## <a name="identify-stakeholders"></a>Belanghebbenden identificeren

Identificeer de belanghebbenden voor uw project.

|Rol |Verantwoordelijkheden |Department |
|:-------|:-------|:--------|
| Executive sponsor(s)   | Een gezichtsvermogen en waarden op hoog niveau communiceren met het bedrijf   |  Leidinggevenden   |
| Project lead(s) | Toezicht houden op het volledige implementatie- en implementatieproces van de lancering | Projectmanagement |
| Kennisbeheerders| De inhoudcentra maken en beheren | IT of andere afdeling|
| Inhoudsbeheerders en modeleigenaars| Use cases verzamelen en modellen maken en toepassen | Elke afdeling|
| Kampioenen | Helpt bij het onder de beter te onderscheden en beheren van afhandeling van aanstootgevende gegevens | Elke afdeling (personeel) |
| Tenantbeheerder | Instellingen op tenantniveau configureren | IT-afdeling|
| Beheerder van Power Platform| Veelvoorkomende omgeving voor gegevensservices configureren | IT-afdeling|

> [!Note]
> Hoewel we aanraden dat elk van deze rollen is uitgevoerd tijdens uw implementatie, kunnen u vinden dat u ze niet allemaal nodig hebt om aan de slag te gaan met uw geïdentificeerde oplossing.

## <a name="readiness-checklist"></a>Controlelijst Gereedheid

Als u zich wilt voorbereiden op het implementeren van SharePoint Syntex, moet u:

![Gereedheid voor inhoudskennis](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. De eindtoestand plannen
    - Modellen voor documentkennis zijn de middelen, niet het einde.
    - Maak gebruik van de waarde van uitgepakte metagegevens met:
      - Zoeken
      - Filteren en opmaak weergeven
      - Compliance
      - Automatisering
2. Identificeren
    - Inzicht krijgen in de bestaande informatiearchitectuur en het gebruik van functies voor inhoudsbeheer.
    - Zijn er bestaande inhoudstypen goede kandidaten voor modellen?
    - Welke bestaande processen worden verbeterd door metagegevens?
3. Design
    - Uw benadering van de informatiearchitectuur, beheerde metagegevens en inhoudstypen ontwerpen
    - Ontwerp het proces voor definitie, maken en beheren.

## <a name="engage-your-organization"></a>Uw organisatie betrekken

1. Identificeer de houders, bevestig scenario's en ontwikkel een projectplan.
1. Configureer instellingen en pas licenties toe.
1. Begin met mensen om u te bewust te maken en training te krijgen : wervings champions.
1. Rol deze gefaseer uit.  
1. Verzamel feedback en itereren.
1. Naarmate het gebruik steeds verder toeneemt, wordt uw AI Builder-tegoed zo nodig beter.
