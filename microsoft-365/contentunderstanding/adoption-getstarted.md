---
title: 'Microsoft SharePoint Syntex-acceptatie: aan de slag'
description: Lees hoe u SharePoint Syntex in uw organisatie kunt gebruiken en implementeren om uw zakelijke problemen te verhelpen.
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 95e1ad15a62762c8b28203e178d4d4ae7906e38a
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760240"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a>Microsoft SharePoint Syntex-acceptatie: aan de slag

U vindt meer informatie over de intelligente inhouds Services in SharePoint Syntex, met drie gedeelten:

- Meer informatie **over:** het maken van niet-gecodeerde AI-modellen om gegevens van inhoud te classificeren en te extraheren, zodat ze automatisch metagegevens kunnen toepassen voor ontdekking en hergebruiken. Meer informatie over het [begrijpen van inhoud](document-understanding-overview.md).
- **Inhoudsverwerking:** Automatiseren van de vastlegging, ingestie en categorisatie van inhoud en gestroomlijnd processen met behulp van energie automatisering. Meer informatie over [inhoudsverwerking](form-processing-overview.md).
- **Inhouds naleving:** Beheer de inhoud en beheer deze om de beveiliging en governance te verbeteren met de integratie met Microsoft-gegevensbescherming.

Met de nieuwe AI-Services en-functies kunt u de inhoud van de apps met behulp van SharePoint Syntex samenstellen en classificeren.

|Handmatige invoer| Formulierverwerking | Documenten begrijpen |
|:-------|:--------|:--------|
| Gegevensinvoer en arbeidsintensief op inhoud. | U kunt bestanden identificeren en gegevens extraheren uit gestructureerde of gedeeltelijk gestructureerde documenten, zoals formulieren of facturen. |  Identificeer en extraheer gegevens uit niet-gestructureerde documenten, zoals letters of contracten, waarbij de tekst entiteiten die u wilt extraheren, zich bevinden in zinnen of bepaalde gebieden van het document. |
| Activiteit.   |  Aangepast, bijgestaan.  | Kant-en-klare, automatisch. |
| Personen die het werk doen. | In het bezit zijn van de experts van de materie. | Kmo's zijn minder gemoeid. |

De volgende tabel bevat informatie over de beschikbaarheid en licenties voor SharePoint Syntex:

| Formulierverwerking | Documenten begrijpen |
|:-------|:-------|
| Het verwerken van formulieren is afhankelijk van het Power platform. <br>Zie [beschikbaarheid van Power platform](https://dynamics.microsoft.com/geographic-availability/)voor informatie over wereldwijde beschikbaarheid voor Power platform en AI Builder. | Beschikbaar in alle regio's. |
| Maakt gebruik van AI Builder-tegoeden.<br>U kunt een tegoed kopen in batches van 1M.<br>Als er 300 + SharePoint Syntex-licenties zijn aangeschaft, worden de tegoeden van 1 m inbegrepen.<br>met beantwoord van 1-en-tegoed kan de verwerking van 2000 bestands pagina's worden verwerkt. | Modellen werken op alle Latijnse alfabetische talen. Naast Engels: Duits, Zweeds, Frans, Spaans, Italiaans en Portugees. |
| Ingericht met de standaardgegevens service omgeving van common data. | Heeft geen beperkingen voor de capaciteit. |

Zie licenties voor de [AI Builder-licentie](https://docs.microsoft.com/ai-builder/administer-licensing)voor meer informatie over de krediet en eenheden van AI Builder.

Er zijn twee verschillende manieren om uw inhoud te begrijpen. Het modeltype dat u gebruikt, is gebaseerd op de bestandsindeling en de use-case:

| Formulierverwerking | Documenten begrijpen |
|:-------|:-------|
| Gemaakt op basis van documentbibliotheek. | Aangemaakt in het inhouds centrum, onderdeel van SharePoint Syntex. |
| Model gemaakt met AI Builder. | Model gemaakt in de eigen interface. |
| Wordt gebruikt voor semi-gestructureerde bestandsindelingen. | Wordt gebruikt voor niet-gestructureerde bestandsindelingen. |
| Instelbare Classifier. | Train bare Classifier met optionele extracten. |
| Niet toegestaan voor één bibliotheek. | Kan worden toegepast op meerdere bibliotheken. |
| Training voor PDF, JPG, PNG-indeling, totale 50 MB/500 pag. | Training voor 5-10 PDF-, Office-of e-mail bestanden, met inbegrip van negatieve voorbeelden. |

SharePoint Syntex is geïntegreerd met compliance-functies van Microsoft 365, zoals:

- Labels voor bewaarbeleid waarmee een record beleid wordt gedefinieerd op basis van de ouderdom van documenten of externe gebeurtenissen.
- Coderings labels waarmee DLP, versleuteling, delen en regels voor voorwaardelijke toegang worden ingesteld.

Gebruikers kunnen labels toepassen of ze kunnen automatisch worden toegepast op SharePoint Syntex AI-modellen. Met analyse-en bestands abonnementen kunt u het beheer van labels en het gebruik van labels op een schaal bepalen.

## <a name="identify-pilot-business-scenarios-to-optimize"></a>Scenario's voor prototype bedrijven identificeren die u wilt optimaliseren

Voor de voorbereiding voor het gebruik van SharePoint Syntex in uw organisatie moet u eerst inzicht krijgen in de scenario's waarin dit nuttig is. In dit geval kunt u bepalen welk model u nodig hebt en hoe u uw organisatie kunt structureren op basis van de locatie waar het model wordt toegepast. Hier volgen een paar scenario's waarin u kunt zien hoe u in een document kunt werken:

- Inhoudsverwerking: contracten, overzichten van werk en andere Form-achtige documenten bewerken. Laat de formulieren opdoen, Train het model om de velden te begrijpen en toe te wijzen en voer vervolgens uw formulieren uit om automatisch de gegevens te verzamelen. Zie [overzicht van formulierverwerking](form-processing-overview.md)voor meer informatie.
- Factuur analyse: Haal de relevante gegevens uit uw facturen op en zorg ervoor dat ze voldoen aan het beleid of worden afgehandeld.

Denk na over de manieren waarop SharePoint Syntex uw organisatie kan helpen:

- Bedrijfsprocessen automatiseren
- De nauwkeurigheid van zoeken verbeteren
- Nalevings risico beheren

### <a name="form-processing-scenario-example"></a>Voorbeeld van scenario voor formulierverwerking

U kunt bijvoorbeeld een proces instellen met behulp van SharePoint Syntex en de functies voor automatiserings automatisering om facturen bij te houden en te bewaken.

1. Een bibliotheek instellen voor het opslaan van de factuurdocumenten.
1. Train het model om velden in de documenten te herkennen.
1. Pak de velden in die u wilt bijhouden in een lijst.
1. Een stroom instellen om u op de hoogte te stellen van bepaalde gebeurtenissen, bijvoorbeeld:
    - Een nieuwe factuur wordt toegevoegd.
    - Er staat een factuur na de vervaldatum.
    - Een factuur is voor een bedrag dat groter is dan het automatisch goedkeuringsbedrag.

![Facturen bijhouden en controleren met behulp van SharePoint Syntex en Powers automatiseren](../media/content-understanding/process-invoices-flow.png)

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Bespaar tijd en geld door automatisch gegevens te extraheren uit de facturen in plaats van deze handmatig uit te voeren.
- Verminder mogelijke fouten en zorg voor een betere naleving met behulp van werkstromen om op de facturen te handelen en u op de hoogte te stellen van eventuele problemen.

### <a name="document-understanding-scenario-example"></a>Voorbeeld van het scenario scenario van document

Als ander voorbeeld kunt u een proces instellen voor de manier waarop contracten worden geïdentificeerd die uw bedrijf met andere bedrijven of particulieren heeft. U kunt een model instellen voor het extraheren van belangrijke informatie uit deze contracten, zoals de naam van de client, kosten, datums of andere belangrijke informatie, en voeg deze toe aan de bibliotheek als velden die u snel kunt bekijken. U kunt ook een Bewaar label toepassen op de documentbibliotheek, zodat u zeker weet dat de contracten vóór een bepaalde tijd niet kunnen worden verwijderd voor de juiste naleving van de bedrijfsregels.

1. Begin in het inhouds centrum en maak een nieuw document en maak informatie over het model voor contracten.
1. Bekijk voorbeelddocumenten voor positieve en negatieve voorbeelden en voer vervolgens de training uit om documenten met contracten te identificeren en de resultaten te bekijken.
1. Train de extractor voor het identificeren van velden in de contracten, zoals de naam van de klant, de kosten en de datum, en test vervolgens de extractor.
1. Wanneer het model is voltooid, past u het model toe op een bibliotheek waar u contracten kunt uploaden.
1. Een Bewaar label toepassen op het datumveld, zodat contracten in de bibliotheek bewaard blijven voor de tijdsduur die uw organisatie nodig heeft voor contracten.

![Contracten bijhouden en bijhouden met labels van SharePoint Syntex en bewaren](../media/content-understanding/process-contracts-flow.png)

Wanneer u dit scenario automatiseert, kunt u het volgende doen:

- Bespaar tijd en geld door automatisch gegevens uit de contracten te extraheren in plaats van deze handmatig uit te voeren.
- Zorg voor een betere naleving door labels te gebruiken om ervoor te zorgen dat de contracten op de juiste wijze worden bewaard.

### <a name="tips-for-identifying-scenarios"></a>Tips voor het identificeren van scenario's

U kunt de volgende vragen stellen wanneer u overweegt welke bedrijfsscenario's u moet nemen:

- Wordt een echt probleem opgelost?
- Wordt deze veel gebruikt of hebt u algemene impact?
- Is dit een verkrijgbare?
- Kunt u succes meten?

Scenario's prioriteren op basis van impact en gemakkelijke implementatie. Zorg dat de scenario's voor het eerste focus gebied hoger zijn dan de scenario's die u ook gemakkelijk kunt implementeren. De prioriteit van scenario's voor minder impact die moeilijk te implementeren zijn.

## <a name="identify-roles--responsibilities"></a>Rollen & verantwoordelijkheden identificeren

Bepalen wie in uw organisatie de modellen gaat maken en beheren? Dit kunnen de volgende rollen zijn:

| SharePoint/Knowledge-beheerder | Power platform-beheerder | Knowledge Manager | Model eigenaar |
|:-------|:-------|:-------|:-------|
| AAD-rol| Rollen toevoegen | AAD-rol | Leiders |
| Formulierverwerking configureren | Algemene gegevensservice omgeving configureren voor formulierverwerking | Gebruik zaken verzamelen | Zakelijke gebruiks kwesties verzamelen |
| Inhouds afdelingen en machtigingen beheren| AIB-tegoed kopen en toewijzen | Best practices opstellen en model analyses beoordelen | Modellen maken en toepassen |

De eigenaar van de Business-Manager, de bedrijfs procedure en de eigenaar van het inhoudsmodel maken voorbeeld modellen en de aanneming van de inhoud van de organisatie.
Deelnemers met compliance beheerder, taxonomie beheerders.

Waar worden de modellen gemaakt en toegepast? Zijn er bestaande processen of opslaglocaties die kunnen worden verbeterd?

- Formulierverwerking: Bepaal welke sites de formulier verwerkings actie krijgen.
- Meer informatie over het maken van documenten: u kunt meerdere inhouds centra maken voor verschillende gebieden in de onderneming.

## <a name="strategic-positioning"></a>Strategische plaatsing

Werk met belanghebbenden om ervoor te zorgen dat ze zijn uitgelijnd op de strategie voor het gebruik van SharePoint Syntex. Onderzoek en voer de volgende bronnen in voor hulp bij deze plaatsing:

- Bedrijfsresultaten:
  - Potentiële fiscale resultaten
  - Potentiële resultaten van flexibiliteit
  - Sjabloon zakelijk resultaat
- Voor uitkopen/uitvullen met belanghebbenden/exec
  - Hoofdletters voor bedrijven
  - Financiële modellen
  - Bedrijfs gereedheids-cultuur

## <a name="identify-stakeholders"></a>Belanghebbenden identificeren

Identificeer de belanghebbenden voor uw project.

|Rol |Verplichtingen |Department |
|:-------|:-------|:--------|
| Onderdirecteur (en)   | De visie en de waarden op hoog niveau met het bedrijf communiceren   |  Uitvoerend leiderschap   |
| Project potentiële klanten | Toezicht houden op het hele proces voor het uitvoeren van uitvoering en implementatie | Project Management |
| Kennis beheerders| Inhouds centra maken en beheren | IT of een andere afdeling|
| Inhoudsbeheerders en model eigenaren| Use cases verzamelen en modellen maken en toepassen | Afdeling|
| Leiders | Ondersteuning voor evangelize en beheren van objecten | Afdeling (personeel) |
| Tenant beheerder | Instellingen op tenantniveau configureren | IT-afdeling|
| Power platform-beheerder| Algemene gegevensservice omgeving configureren | IT-afdeling|

> [!Note]
> Hoewel het u aan deze rollen wordt voldaan, is het raadzaam dat u dit niet nodig hebt om aan de slag te gaan met de geïdentificeerde oplossing.

## <a name="readiness-checklist"></a>Controlelijst voor gereedheidscontrole

Als u wilt beginnen met de implementatie van SharePoint Syntex, moet u het volgende doen:

![Gereedheids voor informatie over inhoud](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. De eindtoestand plannen
    - Document wat betekent dat modellen niet het einde zijn.
    - Plan de waarde van opgehaalde metagegevens te bundelen met:
      - Vinden
      - Filteren en opmaak weergeven
      - Compliance
      - Automatiseringsinvoegtoepassingen
2. Aanduiding
    - Inzicht in de bestaande informatiearchitectuur en het gebruik van inhoudsbeheer.
    - Bestaan bestaande inhoudstypen goede kandidaten voor modellen?
    - Welke bestaande processen worden verbeterd met metagegevens?
3. Design
    - De aanpak van de Information Architecture, beheerde metagegevens en inhoudstypen ontwerpen
    - Ontwerp het proces voor definitie, maken, beheer.

## <a name="engage-your-organization"></a>Deelnemen aan uw organisatie

1. Identificeer de houders van een aandeel, bevestig scenario's en maak projectplan.
1. Instellingen configureren en licenties toepassen.
1. Begin met bewustmaking en training: werven leiders.
1. Rollen in fasen.  
1. Verzamel feedback en herhaal.
1. Het gebruik van een programma voor AI Builder wordt zo nodig uitgebreid.
