---
title: Verwijzing naar aangepaste filters voor gevoelige informatie
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: In dit artikel wordt een lijst weergegeven met de filters die kunnen worden gecodeerd in aangepaste gevoelige informatietypen.
ms.openlocfilehash: 6dfa562d581f14c0b1ac41c4ce803e2367a94636
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322568"
---
# <a name="custom-sensitive-information-type-filters-reference"></a>Verwijzing naar aangepaste filters voor het type gevoelige informatie

In Microsoft kunt u filters of extra controles definiëren terwijl u een aangepaste, gevoelige informatietypen (SIT) maakt.

## <a name="list-of-supported-filters-and-use-cases"></a>Lijst met ondersteunde filters en use cases

### <a name="alldigitssame-exclude"></a>AllDigitsSame Exclude

Beschrijving: Hiermee kunt u overeenkomsten uitsluiten die alle cijfers als dubbele cijfers hebben, zoals 111111111111 of 111-111-111-111

Filters definiëren
```xml
<Filters id="ssn_filters">
    <Filter type="AllDigitsSameFilter"></Filter>
</Filters>
```

Het gebruiken in een regelpakket op entiteitsniveau
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85"  filters="ssn_filters">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

Het gebruiken in een regelpakket op het patroonniveau
```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="ssn_filters">
        <IdMatch idRef="Func_ssn" />
      </Pattern>
</Entity>
```

### <a name="textmatchfilter-startswith"></a>TextMatchFilter StartsWith 

Beschrijving: Hiermee kunt u de begintekens voor de entiteit definiëren. Het heeft twee varianten, inclusief en uitsluiten.

Als u bijvoorbeeld de getallen wilt uitsluiten die beginnen met 0500, 91, 091, 010 in een lijst als deze:

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

u kunt deze xml gebruiken

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>
</Filters>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```
Als u bijvoorbeeld de getallen wilt opnemen die beginnen met 0500, 91, 091, 0100 in een lijst als deze: 

- 0500-4500-027
- 91564721450
- 91-8523697410
- 700-8956-7844
- 1000-3265-9874
- 0100-7892-3012

u kunt deze xml gebruiken

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction="StartsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-endswith"></a>TextMatchFilter EndsWith 

Beschrijving: Hiermee kunt u de eindtekens voor de entiteit definiëren. 

Als u bijvoorbeeld de getallen wilt uitsluiten die eindigen met 0500.91.091, 0100 in een lijst als deze:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

u kunt deze xml gebruiken

```xml
<Filters id="phone_number_filters_exc">
    <Filter type="TextMatchFilter" direction="EndsWith" logic="Exclude" textProcessorId="Keyword_false_positives_sw">
</Filter>

  <Keyword id="Keyword_false_positives_sw">
    <Group matchStyle="string">
      <Term>0500</Term>
      <Term>91</Term>
      <Term>091</Term>
      <Term>0100</Term>
    </Group>
  </Keyword>
```

Als u bijvoorbeeld de getallen die eindigen met 0500, 91, 091, 0100, wilt opnemen in een lijst als deze:

- 1234567891
- 1234-5678-0091
- 1234.4567.7091
- 1234-8091-4564

u kunt deze xml gebruiken

```xml
<Filters id="phone_filters_inc">
    <Filter type="TextMatchFilter" direction=" EndsWith" logic="Include" textProcessorId="Keyword_false_positives_sw">
</Filter>
```

### <a name="textmatchfilter-full"></a>TextMatchFilter Full

Beschrijving: Hiermee kunt u bepaalde overeenkomsten verbieden om te voorkomen dat deze de regel activeren. Sluit bijvoorbeeld 411111111111111111111 uit in de lijst met geldige creditcardwedstrijden.

Als u bijvoorbeeld creditcardnummers zoals 41111111111111111111111 en 32418910311111 wilt uitsluiten in een lijst als deze:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

u kunt deze xml gebruiken

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Full" logic="Exclude" textProcessorId="Keyword_false_positives_full">
</Filter>

  <Keyword id="Keyword_false_positives_full">
    <Group matchStyle="string">
      <Term>4111111111111111</Term>
      <Term>3241891031113111</Term>
    </Group>
  </Keyword>
```

Als u bijvoorbeeld creditcardnummers zoals 411111111111111111111111 en 3241891031113111 wilt opnemen in een lijst als deze:

- 4485 3647 3952 7352
- 4111111111111111
- 3241891031113111

u kunt deze xml gebruiken

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_false_positives_full">
</Filter>
```

### <a name="textmatchfilter-prefix"></a>TextMatchFilter Voorvoegsel

Beschrijving: Hiermee kunt u de voorgaande tekens definiëren die altijd moeten worden opgenomen of uitgesloten. Als creditcardnummer bijvoorbeeld wordt voorafgegaan door 'Order-id:' verwijdert u de overeenkomst uit de geldige overeenkomsten.

Als u bijvoorbeeld telefoonnummers wilt uitsluiten  die een  Telefoon hebben en mij bellen bij tekenreeksen vóór het telefoonnummer, in een lijst als deze:

- telefoonnummer 091-8974-653278
- Telefoon 45-124576532-123
- 45-124576532-123

u kunt deze xml gebruiken

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_prefix">
</Filter>
  <Keyword id="Keyword_false_positives_prefix">
    <Group matchStyle="string">
      <Term>phone number</Term>
      <Term>call me at</Term>
    </Group>
  </Keyword>
```

Als u bijvoorbeeld exemplaren  met creditcard- en **kaartnummerreeksen** vóór het creditcardnummer wilt opnemen, in een lijst als deze:

- Creditcard 45-124576532-123 
- 45-124576532-123 (mogelijk telefoonnummer)

u kunt deze xml gebruiken

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_prefix">
</Filter>

  <Keyword id="Keyword_true_positives_prefix">
    <Group matchStyle="string">
      <Term>credit card</Term>
      <Term>card #</Term>
    </Group>
  </Keyword
```

### <a name="textmatchfilter-suffix"></a>TextMatchFilter-achtervoegsel

Beschrijving: Hiermee kunt u de volgende tekens definiëren die altijd moeten worden opgenomen of uitgesloten. Als creditcardnummer bijvoorbeeld wordt gevolgd door '/xuid' verwijdert u de overeenkomst uit de geldige overeenkomsten.

Als er bijvoorbeeld nog vijf exemplaren van vier cijfers als achtervoegsel in een lijst als volgende voorkomen:

- 1234-5678-9321 4500 9870 6321 48925566
- 1234-5678-9321

u kunt deze xml gebruiken

```xml
<Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Regex_false_positives_suffix">
</Filter>

  <Regexid="Regex_false_positives_suffix">(\d{4}){5,}</Regex>
```
Als u bijvoorbeeld exemplaren wilt uitsluiten als ze worden gevolgd door **/xuidsuffix,** zoals in deze lijst:

- 1234-5678-9321 /xuid
- 1234-5678-9321

u kunt deze xml gebruiken

''xml <Filters id="cc_number_filters_exc">
    <Filter type="TextMatchFilter" direction="Prefix" logic="Exclude" textProcessorId="Keyword_false_positives_suffix">
</Filter>

  <Keyword id="Keyword_false_positives_suffix"> <Group matchStyle="string">
      <Term>/xuid</Term>
    </Group> </Keyword>
```

For example, to include an occurrence only if it is followed by **cvv** or **expires**, like two in this list:

- 45-124576532-123 
- 45-124576532-123  cvv 966
- 45-124576532-123  expires 03/23

you can use this xml

```xml
<Filters id="cc_filters_inc">
    <Filter type="TextMatchFilter" direction="Full" logic="Include" textProcessorId="Keyword_true_positives_suffix">
</Filter>

  <Keyword id="Keyword_true_positives_suffix">
    <Group matchStyle="string">
      <Term>cvv</Term>
      <Term>expires</Term>
    </Group>
  </Keyword>
```

## <a name="using-filters-in-rule-packages"></a>Filters gebruiken in regelpakketten

Filters kunnen worden gedefinieerd op de hele SIT of op een patroon. Hier zijn enkele voorbeelden van codefragmenten. 

### <a name="at-sensitive-information-type-level"></a>Op het niveau van het type gevoelige informatie

Filters bij Entity - heeft betrekking op alle onderliggende patronen

De filters worden toegepast op **alle** exemplaren die zijn geclassificeerd door een van de patronen in die entiteit/ het gevoelige type

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
```

### <a name="at-the-individual-pattern-of-the-sensitive-information-type-level"></a>Op het afzonderlijke patroon van het niveau van het gevoelige informatietype

Filtert alleen op het patroonniveau.

Het filter wordt toegepast op de exemplaren die overeenkomen met het patroon.

```xml
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85"  filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Keyword_cc_verification" />
      </Pattern>
</Entity>
```


### <a name="at-sensitive-information-type-level-and-an-additional-filter-on-some-of-the-patterns-of-that-entity"></a>Op het niveau van het type gevoelige informatie en een extra filter op een aantal patronen van die entiteit

Filters bij Entity + pattern

De filters worden toegepast op **alle** exemplaren die zijn geclassificeerd door een van de patronen in die entiteit/ het gevoelige type. Het filter op patroonniveau filtert de exemplaren die overeenkomen met dat patroon.

```xml
<Entity id="6443b88f-2808-482a-8e1a-3ae5026645e1" patternsProximity="300" recommendedConfidence="85" filters="CompositeFiltersAtEntityLevel">
      <Pattern confidenceLevel="85" filters="CompositeFiltersAtPattern">
        <IdMatch idRef="Regex_denmark_id" />
      </Pattern>
</Entity>
``` 

 

## <a name="more-information"></a>Meer informatie

- [Meer informatie over preventie van gegevensverlies](dlp-learn-about-dlp.md)

- [Definities van entiteiten van het type vertrouwelijke gegevens](sensitive-information-type-entity-definitions.md)

- [Doel van de DLP-functies](what-the-dlp-functions-look-for.md)
