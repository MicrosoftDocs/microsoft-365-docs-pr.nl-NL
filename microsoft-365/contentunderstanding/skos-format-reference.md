---
title: SKOS-indelings overzicht voor SharePoint-taxonomie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
description: SKOS-indelings overzicht voor SharePoint-taxonomie
ms.openlocfilehash: eb228394b06b6e6027937ab105df7c0079875226
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295894"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SKOS-indelings overzicht voor SharePoint-taxonomie

Dit artikel bevat de RDF-vocabulaire die wordt gebruikt voor de weergave van de [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) en is gebaseerd op [skos](https://www.w3.org/TR/skos-primer/). Voor serialisatie van deze RDF-syntaxis gebruikt u RDF [TURTLE](https://www.w3.org/TR/turtle/).

In de volgende tabel worden de [skos](https://www.w3.org/TR/skos-primer/) -equivalenten voor de [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) terminologie weergegeven. SharePoint biedt geen ondersteuning voor [skos](https://www.w3.org/TR/skos-primer/) -waarden zonder SharePoint-taxonomie equivalent.

|SharePoint-taxonomie|SKOS-equivalent|
|:-----------------|:--------------|
|SharePoint-taxonomie: term|skos: concept|
|SharePoint-taxonomie: Termenset|skos:ConceptScheme|
|SharePoint-taxonomie: intermenset|skos: schema|
|SharePoint-taxonomie: hasTopLevelTerm|skos:hasTopConcept|
|SharePoint-taxonomie: topLevelTermOf|skos:topConceptOf|
|SharePoint-taxonomie: defaultLabel|skos:prefLabel|
|SharePoint-taxonomie: termSetName|skos:prefLabel|
|SharePoint-taxonomie: eigenschaps|skos:prefLabel|
|SharePoint-taxonomie: otherLabel|skos:altLabel|
|SharePoint-taxonomie: beschrijving|skos: definitie|
|SharePoint-taxonomie: bovenliggend element|skos: bredere|
|SharePoint-taxonomie: onderliggend|skos: smaller|

In de volgende tabel ziet u de entiteiten van de SharePoint-taxonomie van de SharePoint-taxonomie afgeleid van [Owl](https://www.w3.org/TR/owl2-primer/).

|Vocabulaire van SharePoint-taxonomie|Afgeleid van OWL|
|:-----------------------------|:----------------------|
|SharePoint-taxonomie: isAvailableForTagging|owl:datatypeproperty|
|SharePoint-taxonomie: SharedCustomPropertyForTerm|owl:ObjectProperty|
|SharePoint-taxonomie: LocalCustomPropertyForTerm|owl:ObjectProperty|
|SharePoint-taxonomie: CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>Vocabulaire van SharePoint-taxonomie

Een taxonomie is een formele classificatiesysteem. Een taxonomiegroepen de woorden, labels en voorwaarden die een beschrijving beschrijven en de groepen worden vervolgens ingedeeld in een hiërarchie.

**SharePoint-taxonomie: term**

Vertegenwoordigt een term of een trefwoord in een hiërarchie met beheerde metagegevens.

Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is de atoom eenheid van een SharePoint- [Archief](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Elke [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot een [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) die deel uitmaakt van een [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). 

De syntaxis voor het definiëren van een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is als volgt:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) voorkomt binnen een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel is de naam van de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zoals weergegeven in de visuele weergave. De verplichte velden voor het definiëren van een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn onder meer:

- SharePoint-taxonomie: defaultLabel
- SharePoint-taxonomie: intermenset

Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:

- Zorg dat u aan een andere [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) die niet wordt vermeld, [in een andere](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) term moet worden weer [gegeven.](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)
- Meerdere onderliggende [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)hebben, maar slechts één bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).
- Er is geen bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) gedefinieerd, als dit een topLevelTermOf is van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Eén defaultLabel [, per werk](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) woorden.
- Niet aanwezig als het geen bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)bevat, noch de TopLevelTermOf een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). 
- Alleen een unieke defaultLabel op hetzelfde hiërarchische niveau hebben.

**SharePoint-taxonomie: Termenset**

Voorbeeld van een hiërarchische of vlakke set termen objecten die een term ' Termset ' genoemd.

Aangezien de naamsuggesties geeft, is de Termset een set [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) moet deel uitmaken van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Er kan geen [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) apart worden opgenomen. 

De syntaxis voor het definiëren van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) luidt als volgt:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) worden logischerwijze samen gegroepeerd in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group). Het vereiste veld voor het definiëren van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) luidt als volgt:

- SharePoint-taxonomie: termSetName

In het geval van het opgegeven termSetName is er geen unieke waarde in de [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), voegt SharePoint een nummer toe aan het einde van de naam, zodat de uniekheid van termSetName (en) wordt gehandhaafd.

**SharePoint-taxonomie: hasTopLevelTerm**

In SharePoint wordt deze eigenschap gebruikt om de meest voorkomende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in de [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)toe te wijzen, wat het invoerpunt is voor de structuur van [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Dit is een inverse relatie naar SharePoint-Taxonomy: topLevelTermOf. 

De syntaxis voor de definiëren hiervan luidt als volgt:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> U kunt de bovenste [termijn](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) van een bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)niet definiëren.

**SharePoint-taxonomie: topLevelTermOf**

SharePoint-taxonomie: topLevelTermOf is de inverse van SharePoint-taxonomie: hasTopLevelTerm

De syntaxis voor de definiëren hiervan luidt als volgt:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**SharePoint-taxonomie: intermenset**

Hiermee kunt u een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) toewijzen aan een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan maar in één [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)bestaan. SharePoint vereist deze eigenschap voor [het definiëren van een term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Vereiste labels

Het kan handig zijn voor de planning van uw organisatie voordat u beheerde metagegevens gaat gebruiken. Welke planning u moet doen, is afhankelijk van de manier waarop u de taxonomie moet afmaken. Dit hangt ook af van de hoeveel besturingselementen u de metagegevens wilt leggen. Op elk niveau van de hiërarchie moet u de vereiste LABLES configureren voor een term of Termenset.

Een term kan een of meer labels in de standaardtaal bevatten, en de waarden 0 of meer zijn niet in de standaardtaal. Als de term labels bevat in een taal, moet een van de labels het standaardlabel zijn.

**SharePoint-taxonomie: defaultLabel**

Gebruik dit standaard-lexicale label voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) die een vereiste parameter is voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Wordt gebruikt om de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)visueel aan te duiden.

De syntaxis voor het definiëren van een defaultLabel is:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

De defaultLabel bevat twee onderdelen, namelijk de tekenreeks en de taalcode. De taal moet een van [de werktalen voor het werk](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) woorden zijn. De defaultLabel moet uniek zijn voor alle [termen](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in dezelfde [termset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), op hetzelfde hiërarchische niveau.

**SharePoint-taxonomie: termSetName**

Haalt de naam van het huidige Termset-object op en stelt dit in.

Dit is het lexicale etiket voor een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), [in de werk](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) taal van een werkwoord. Dit is een vereiste parameter voor een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset). Voor het visueel vertegenwoordigen van een [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).

De syntaxis voor het definiëren van een termSetName is:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**SharePoint-taxonomie: eigenschaps**

Hiermee wordt de naam van de eigenschap voor het huidige Termset-object opgehaald en ingesteld.

Dit is het lexicale etiket voor een SharePoint-taxonomie: SharedCustomPropertyForTerm, SharePoint-taxonomie: LocalCustomPropertyForTerm en SharePoint-taxonomie: CustomPropertyForTermSet in een werkgebied van een werk [Archief](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) .

De SharePoint-taxonomie: eigenschapnaam wordt behandeld als de sleutel van de CustomProperty.

De syntaxis voor het definiëren van een propetyName is:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Optionele labels

U kunt ook optionele etiketten toevoegen aan de taxonomie.

**SharePoint-taxonomie: otherLabel**

Dit is het alternatieve lexicale etiket voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). 

De syntaxis voor het definiëren van een otherLabel is:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Semantische relaties

Taxonomieën hebben hiërarchische en soms een eenvoudige, gerelateerde term ' gekoppelde term ', maar er zijn een aantal ' semantische relaties ' of aangepaste relaties. 

**SharePoint-taxonomie: bovenliggend element**

Hiermee verlegt u deze hiërarchische [termijn](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) met een andere [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term). Een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) kan een topniveau van [een](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)zijn, maar in de praktijk moet de term geen bovenliggende [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)hebben. 

De syntaxis voor het definiëren van een bovenliggend element luidt als volgt:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Dat betekent dat TermA1 bovenliggende Terma heeft. Ook betekent dit dat TermA1 het kind is van Terma. Relatie tussen bovenliggende en onderliggende items is een inversible-relatie.

**SharePoint-taxonomie: onderliggend**

Het object bevat een of meer onderliggende exemplaren van de Termenset, en deze kunnen worden geopend via de eigenschap TermSets. Deze klasse biedt ook methoden voor het maken van nieuwe onderliggende Termenset-objecten. Machtigingen voor het bewerken van onderliggende termen en Termenset-exemplaren zijn opgegeven voor de groep. 

Hiermee verlegt u deze hiërarchische [termijn](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) met een andere [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).

De syntaxis voor het definiëren van een kind luidt als volgt:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Dat betekent dat Terma onderliggend TermA1. Ook betekent dit dat Terma de bovenliggende relatie van TermA1 bovenliggend-kind is een inversible-relatie.

## <a name="documentation-notes"></a>Documentatie over documentatie

In deze sectie wordt de taxonomie uitvoerig besproken in de naamruimte Microsoft. SharePoint. Taxonomy.

**SharePoint-taxonomie: beschrijving**

Dit is een gedetailleerde uitleg van de entiteiten van een [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) . 

De syntaxis voor het toevoegen van een beschrijving luidt als volgt:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Aangepaste eigenschappen

Hiermee wordt het verzamelen van aangepaste eigenschappen objecten voor het huidige term object in de alleen-lezen woordenlijst opgehaald.

Aangepaste eigenschappen zijn combinaties van sleutelwaarden die kunnen worden gedefinieerd voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), zodat de beschrijving van de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)verder wordt. SharePoint geeft de sleutel van de aangepaste eigenschap aan met de Help van eigenschapnaam.

**SharePoint-taxonomie: CustomPropertyForTermSet**

De syntaxis voor de definiëren hiervan luidt als volgt:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**SharePoint-taxonomie: SharedCustomPropertyForTerm**

Als de aangepaste eigenschap voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) moet worden getransporteerd met de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), moet u deze eerst definiëren onder SharedCustomPropertyForTerm wanneer u [de term vervolgens ergens anders](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) opnieuw gebruikt.

De syntaxis voor de definiëren hiervan luidt als volgt:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**SharePoint-taxonomie: LocalCustomPropertyForTerm**

Als u de aangepaste eigenschap voor een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) niet samen met de [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)hoeft te gebruiken, moet u deze eerst definiëren onder LocalCustomPropertyForTerm wanneer u [de term vervolgens ergens anders](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) opnieuw gebruikt.

De syntaxis voor de definiëren hiervan luidt als volgt:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Gegevenseigenschappen

U kunt op elk niveau van de hiërarchie bepaalde gegevenseigenschappen configureren voor een term of Termenset.

**SharePoint-taxonomie: isAvailableForTagging**

Hiermee kunt u opgeven of een [term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of [termenset](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) beschikbaar is in de SharePoint-lijsten en-bibliotheken.  

Dit is de syntaxis voor dit:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domein en bereik

In de volgende tabel wordt de naam van het domein en het bereik van de SharePoint-taxonomie voor de taxonomie beschreven

|Predikaten/werkwoord|Zinloos|Domein|Kleurovergangsbereik|
|:--------------|:------|:-----|:----|
inbegripset|In de termenset|Onder|Termenset|
inTermGroup|In de groep termen|Termenset|TermGroup|
topLevelTermOf|Is bovenste niveau term|Onder|Termenset|
hasTopLevelTerm|Heeft een bovenste termijn|Termenset|Onder|
termSetName|Termenset heeft naam|Onder|Letterlijke tekst|
defaultLabel|De term heeft een standaardlabel|Onder|Letterlijke tekst|
otherLabel|De term heeft een ander label|Onder|Letterlijke tekst|
eigenschaps|Heeft eigenschaps label|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Booleaanse waarde, tekenreeks, integer, decimaal, dubbel|
|beschrijving|Heeft een beschrijving|Alles|Letterlijke tekst|
|site|Heeft bovenliggend element|Onder|Onder|
|kinderen|Heeft een kind|Onder|Onder|
|isAvailableForTagging|Is beschikbaar voor labelen|Term, Termenset|Booleaanse waarde|
|SharedCustomPropertyForTerm|Heeft een gedeelde aangepaste eigenschap|Onder|Booleaanse waarde, tekenreeks, integer, decimaal, dubbel|
|LocalCustomPropertyForTerm|Heeft lokale aangepaste eigenschap|Onder|Booleaanse waarde, tekenreeks, integer, decimaal, dubbel|
|CustomPropertyForTermSet|Heeft een aangepaste eigenschap|Termenset|Booleaanse waarde, tekenreeks, integer, decimaal, dubbel|

[Skos](https://www.w3.org/TR/skos-primer/) geldige Scenario's die [SharePoint-taxonomie](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) niet toestaan:

- Hiërarchische redundantie: een [skos](https://www.w3.org/TR/skos-primer/) -concept kan tegelijk worden bijgevoegd aan diverse bredere concepten, maar een SharePoint-taxonomie: de term mag maar één SharePoint-taxonomie hebben: ouder, dus cyclische afhankelijkheid, van voorwaarden is ook niet toegestaan.
- Zwevende termen zijn niet toegestaan in de SharePoint-taxonomie. Elke SharePoint-taxonomie: een term moet bestaan uit een SharePoint-taxonomie: de naam van de SharePoint-taxonomie: topLevelTermOf een Termenset.
- SharePoint-taxonomie biedt geen ondersteuning voor koppelieve betrekkingen.
- SharePoint-taxonomie biedt alleen ondersteuning voor twee typen hiërarchierelaties – SharePoint-Taxonomy: Parent en SharePoint-Taxonomy: kind. 
- In tegenstelling tot [skos](https://www.w3.org/TR/skos-primer/) wordt de hiërarchische relatie in de woordenlijst van de SharePoint-taxonomie slechts met termen binnen dezelfde termset vastgelegd.

## <a name="see-also"></a>Zie ook

[Een termenset importeren met een op SKOS gebaseerde indeling](import-term-set-skos.md)

