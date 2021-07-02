---
title: SKOS-verwijzing voor SharePoint-taxonomie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SKOS-verwijzing voor SharePoint-taxonomie
ms.openlocfilehash: 4c08073f453ef0b6a224829b7d4cb4034b74ed14
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228733"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a>SKOS-verwijzing voor SharePoint-taxonomie

Dit artikel bevat de RDF-vocabulaire die wordt gebruikt om [SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) te vertegenwoordigen en is gebaseerd op [SKOS](https://www.w3.org/TR/skos-primer/). Gebruik RDF [SCHILDPAD](https://www.w3.org/TR/turtle/)voor de serialisatie van deze RDF-syntaxis.

In de volgende tabel zie je de [SKOS](https://www.w3.org/TR/skos-primer/)- equivalenten voor de [SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) woordenlijst. SharePoint biedt geen ondersteuning voor [SKOS](https://www.w3.org/TR/skos-primer/) waarden zonder SharePoint-taxonomie equivalent.

|SharePoint-taxonomie|SKOS-equivalent|
|:-----------------|:--------------|
|sharepoint-taxonomy:Term|skos: concept|
|sharepoint-taxonomy:TermSet|skos:ConceptScheme|
|sharepoint-taxonomy:inTermSet|skos:inScheme|
|sharepoint-taxonomy:hasTopLevelTerm|skos:hasTopConcept|
|sharepoint-taxonomy:topLevelTermOf|skos:topConceptOf|
|sharepoint-taxonomy:defaultLabel|skos:prefLabel|
|sharepoint-taxonomy:termSetName|skos:prefLabel|
|sharepoint-taxonomy:propertyName|skos:prefLabel|
|sharepoint-taxonomy:otherLabel|skos:altLabel|
|sharepoint-taxonomy:description|skos:definition|
|sharepoint-taxonomy:parent|skos:broader|
|sharepoint-taxonomy:child|skos:narrower|

In de volgende tabel zie je de entiteiten van de SharePoint-taxonomie die is afgeleid van [OWL](https://www.w3.org/TR/owl2-primer/).

|SharePoint-taxonomie woordenlijst|Afgeleid van OWL|
|:-----------------------------|:----------------------|
|sharepoint-taxonomy:isAvailableForTagging|owl:datatypeproperty|
|sharepoint-taxonomy:SharedCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:LocalCustomPropertyForTerm|owl:ObjectProperty|
|sharepoint-taxonomy:CustomPropertyForTermSet|owl:ObjectProperty|

## <a name="sharepoint-taxonomy-vocabulary"></a>SharePoint-taxonomie woordenlijst

Een taxonomie is een formeel classificatiesysteem. In een taxonomie worden de woorden, labels en termen gegroepeerd die iets beschrijven. Vervolgens worden die groepen gerangschikt in een hiërarchie.

**sharepoint-taxonomy:Term**

Vertegenwoordigt een term of een trefwoord in een hiërarchie met beheerde metagegevens.

Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is de atomische eenheid van een SharePoint-[TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore). Elke [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) die behoort tot een [TermGroep](/dotnet/api/microsoft.sharepoint.taxonomy.group).

De syntaxis voor het definiëren van een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) is als volgt:

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

Er bestaat een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) verplicht binnen een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset). DefaultLabel is de naam van de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) zoals deze wordt weergegeven in de visuele weergave. De vereiste velden voor het definiëren van een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn:

- sharepoint-taxonomy:defaultLabel
- sharepoint-taxonomy:inTermSet

Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan:

- Hiërarchisch gerelateerd zijn aan een andere [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) die worden vermeld in zowel de [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) behoort tot dezelfde [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Meerdere onderliggende [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term), maar slechts één bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).
- Er is geen bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)gedefinieerd, als het een topLevelTermOf een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset)is.
- Een defaultLabel hebben, per [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.
- Niet bestaan als deze geen bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)bevat, en niet de topLevelTermOf een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset).
- Slechts een unieke defaultLabel op hetzelfde hiërarchische niveau hebben.

**sharepoint-taxonomy:TermSet**

Hiermee wordt een hiërarchische of vlakke set termobjecten aangeduid die worden aangeduid als een "Termset".

Zoals de naam suggereertt, is Termset een set [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term). Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore) moet deel uitmaken van een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Er kan geen [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) afzonderlijk bestaan.

De syntaxis voor het definiëren van een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

[TermSets](/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn logisch gegroepeerd in [TermGroups](/dotnet/api/microsoft.sharepoint.taxonomy.group). De vereiste velden voor het definiëren van een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn:

- sharepoint-taxonomy:termSetName

In het geval van het gegeven termSetName niet uniek is binnen de [TermGroup](/dotnet/api/microsoft.sharepoint.taxonomy.group), wordt aan het begin van de naam een nummer toegevoegd door SharePoint om de uniekheid van termSetName(s) te behouden.

**sharepoint-taxonomy:hasTopLevelTerm**

SharePoint gebruikt deze eigenschap om de hoogste [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) toe te wijzen aan de [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset), het ingangspunt van de hiërarchie met [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) in een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Dit is een inverse relatie met de SharePoint-taxonomie: topLevelTermOf.

De syntaxis voor het definiëren hiervan is:

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

> [!NOTE]
> Het is niet mogelijk om de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) op het hoogste niveau van een bovenliggend [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)te definiëren.

**sharepoint-taxonomy:topLevelTermOf**

SharePoint-taxonomie: topLevelTermOf is de inverse van SharePoint-taxonomie: hasTopLevelTerm

De syntaxis voor het definiëren hiervan is:

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

**sharepoint-taxonomy:inTermSet**

Gebruik dit om een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) toe te wijzen aan een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan slechts bestaan in één [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset). SharePoint vereist deze eigenschap bij het[definiëren van een term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).

## <a name="required-labels"></a>Vereiste labels

Het is mogelijk dat je organisatie een zorgvuldige planning moet uitvoeren voordat je beheerde metagegevens gaat gebruiken. De hoeveelheid planning die je moet uitvoeren, hangt af van hoe formeel de taxonomie is. De functie is ook afhankelijk van de hoeveelheid besturingselementen die je wilt toepassen op metagegevens. Op elk niveau van de hiërarchie moet je de vereiste labels voor een Term of Termenset configureren.

Een term kan een of meer labels in de standaardtaal bevatten en nul of meer etiketten in de niet-standaardtaal. Als de term labels in een taal heeft, moet een van de labels het standaardlabel zijn.

**sharepoint-taxonomy:defaultLabel**

Gebruik dit standaard-lexicale label voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) die een verplichte parameter is voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). Gebruik om de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term)visueel te representeren.

De syntaxis voor het definiëren van standaard label is:

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

De defaultLabel bevat twee onderdelen: de tekenreeks en de taal. De taal moet een van de [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)- werktalen zijn. De defaultLabel moet uniek zijn voor alle [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) in dezelfde [TermSet](/dotnet/api/microsoft.sharepoint.taxonomy.termset) op hetzelfde hiërarchische niveau.

**sharepoint-taxonomy:termSetName**

Hiermee wordt de naam opgehaald en ingesteld voor het huidige Termenset-object.

Dit is het lexicale label voor een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset), in een [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal. Dit is een verplichte parameter voor een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset). Gebruik om de [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset)visueel te representeren.

De syntaxis voor het definiëren van een termSetName is:

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

**sharepoint-taxonomy:propertyName**

Hiermee wordt de eigenschapsnaam opgehaald en ingesteld voor het huidige Termenset-object.

Dit is het lexical-label voor een SharePoint-taxonomie: SharedCustomPropertyForTerm, SharePoint-taxonomie: LocalCustomPropertyForTerm en SharePoint-taxonomie: CustomPropertyForTermSet in een [TermStore](/dotnet/api/microsoft.sharepoint.taxonomy.termstore)-werktaal.

SharePoint-taxonomie: eigenschapnamen wordt behandeld als de sleutel van de CustomProperty.

De syntaxis voor het definiëren van een propetyName is:

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a>Optionele labels

Je kunt ook optionele labels toevoegen aan je taxonomie.

**sharepoint-taxonomy:otherLabel**

Dit is het alternatieve lexicale label voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).

De syntaxis voor het definiëren van otherLabel is:

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a>Semantische relaties

Taxonomie heeft hiërarchische en soms een simpele "gerelateerde term" associatieve relatie, maar enkele voorbeelden van "semantische relaties" of relaties met aangepaste voorwaarden.

**sharepoint-taxonomy:parent**

Hiermee wordt een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) op een andere [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term). Een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) kan een hoog niveau [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) van een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) zijn, maar als het niet zo is moet er een bovenliggende [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) zijn.

De syntaxis voor het definiëren van een bovenliggende term is:

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

Dit betekent dat TermA het bovenliggende en TermA het onderliggende.

**sharepoint-taxonomy:child**

Het object bevat een of meer onderliggende Termenset-instanties en kan worden geopend via de eigenschap TermSets. Deze klas biedt ook methoden voor het maken van nieuwe onderliggende Termenset-objecten. De machtigingen voor het bewerken van onderliggende termen en Termenset-exemplaren zijn opgegeven voor de groep.

Hiermee wordt een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) op een andere [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term).

De syntaxis voor het definiëren van een onderliggende term is:

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

Dit betekent dat TermA het bovenliggende en TermA het onderliggende.

## <a name="documentation-notes"></a>Documentatienotities

In deze sectie wordt de taxonomie besproken die wordt beschreven in de Naamruimte Microsoft.SharePoint-taxonomie.

**sharepoint-taxonomy:description**

Dit is een gedetailleerde uitleg van een [SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) vocabulaire-entiteit.

De syntaxis om een beschrijving toe te voegen is:

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a>Aangepaste eigenschappen

Hiermee haal je een verzameling aangepaste eigenschapsobjecten op voor de huidige objectterm uit de alleen-lezen woordenlijst.

Aangepaste eigenschappen zijn sleutelwaarden paren die kunnen worden gedefinieerd voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset), om de beschrijving van de [Termen](/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) te bevorderen. SharePoint geeft de sleutel van de aangepaste eigenschap aan met behulp van propertyName.

**sharepoint-taxonomy:CustomPropertyForTermSet**

De syntaxis voor het definiëren hiervan is:

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

**sharepoint-taxonomy:SharedCustomPropertyForTerm**

Als de aangepaste eigenschap voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) moet worden meegenomen aan de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), moet je de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) vervolgens op de gewenste locatie definiëren onder SharedCustomPropertyForTerm.

De syntaxis voor het definiëren hiervan is:

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
**sharepoint-taxonomy:LocalCustomPropertyForTerm**

Als de aangepaste eigenschap voor een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) niet moet worden meegenomen met de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term), moet je de [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) vervolgens op de gewenste locatie definiëren onder LocalCustomPropertyForTerm.

De syntaxis voor het definiëren hiervan is:

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a>Gegevenseigenschappen

Op elk niveau van de hiërarchie moet je de specifieke gegevenseigenschappen voor een Term of Termenset configureren.

**sharepoint-taxonomy:isAvailableForTagging**

Gebruik deze instelling om op te geven of een [Term](/dotnet/api/microsoft.sharepoint.taxonomy.term) of een [Termenset](/dotnet/api/microsoft.sharepoint.taxonomy.termset) die beschikbaar is in SharePoint-lijsten en - bibliotheken.

De syntaxis voor dit is als volgt:

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a>Domein en bereik

In de volgende tabel vind je een beschrijving van het domein en het bereik van de SharePoint-taxonomie woordenlijst.

|Predikaten/werkwoord|Betekenis|Domein|Bereik|
|:--------------|:------|:-----|:----|
inTermSet|In Termenset|Term|Termenset|
inTermGroup|In termgroep|TermSet|TermGroup|
topLevelTermOf|Is het hoogste niveau van|Term|TermSet|
hasTopLevelTerm|Heeft het hoogste niveau term|Termenset|Term|
termSetName|Termenset heeft naam|Term|Letterlijke tekst zonder opmaak|
defaultLabel|Term heeft een standaardlabel|Term|Letterlijke tekst zonder opmaak|
otherLabel|Term heeft een ander label|Term|Letterlijke tekst zonder opmaak|
propertyName|Heeft eigenschapslabel|SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet |Boolean, String, Integer, Decimal, Double|
|beschrijving|Heeft beschrijving|Alle|Letterlijke tekst zonder opmaak|
|Bovenliggend|Heeft bovenliggend element|Term|Term|
|onderliggend element|Heeft onderliggend element|Term|Term|
|isAvailableForTagging|Is beschikbaar voor labelen|Term, Termenset|Booleaanse waarde|
|SharedCustomPropertyForTerm|Heeft aangepaste eigenschap gedeeld|Term|Boolean, String, Integer, Decimal, Double|
|LocalCustomPropertyForTerm|Heeft lokale aangepaste eigenschap|Term|Boolean, String, Integer, Decimal, Double|
|CustomPropertyForTermSet|Heeft aangepaste eigenschap|TermSet|Boolean, String, Integer, Decimal, Double|

[SKOS](https://www.w3.org/TR/skos-primer/) geldige scenario's die [ SharePoint-taxonomie](/dotnet/api/microsoft.sharepoint.taxonomy) niet is toegestaan:

- Hiërarchische redundantie - een [SKOS](https://www.w3.org/TR/skos-primer/) concept kan tegelijk met meerdere bredere concepten worden bijgevoegd, maar een SharePoint-taxonomie: kan slechts één SharePoint-taxonomie bevatten: bovenliggend, dus cyclische afhankelijkheid van termen is ook niet toegestaan.
- Zwevende termen zijn niet toegestaan in SharePoint-taxonomie. Elke sharepoint-taxonomie:Term moet een sharepoint-taxonomie:parent hebben of moet de sharepoint-taxonomie:topLevelTermOf a TermSet zijn.
- SharePoint-taxonomie biedt geen ondersteuning voor associatierelaties.
- SharePoint-taxonomie is alleen geschikt voor 2 typen hiërarchische relaties: SharePoint-taxonomie: bovenliggende en SharePoint-taxonomie: onderliggend.
- In tegenstelling tot [SKOS](https://www.w3.org/TR/skos-primer/) de hiërarchische relatie in de SharePoint-taxonomie-vocabulaire, kan de hiërarchische relatie alleen tot stand worden gebracht met termen binnen de Termenset.

## <a name="see-also"></a>Zie ook

[Een termenset met een SKOS-indeling importeren](import-term-set-skos.md)