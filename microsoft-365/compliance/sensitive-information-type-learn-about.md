---
title: Meer informatie over typen gevoelige informatie
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: In dit artikel wordt een overzicht gegeven van gevoelige informatietypen en hoe ze gevoelige informatie detecteren, zoals sociale zekerheid, creditcard- of bankrekeningnummers om gevoelige items te identificeren
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453619"
---
# <a name="learn-about-sensitive-information-types"></a>Meer informatie over typen gevoelige informatie

Het identificeren en classificeren van gevoelige items die onder uw organisatiebeheer vallen, is de eerste stap in de [discipline Informatiebeveiliging.](./information-protection.md)  Microsoft 365 biedt drie manieren om items te identificeren, zodat ze kunnen worden geclassificeerd:

- handmatig door gebruikers
- geautomatiseerde patroonherkenning, zoals gevoelige informatietypen
- [machine learning](classifier-learn-about.md)

Gevoelige informatietypen zijn classificaties op basis van patronen. Ze detecteren gevoelige informatie, zoals sociale zekerheid, creditcard- of bankrekeningnummers om gevoelige items te identificeren, zie Definities van [entiteitstypen gevoelige informatie](sensitive-information-type-entity-definitions.md)

## <a name="sensitive-information-types-are-used-in"></a>Gevoelige informatietypen worden gebruikt in

- [Preventiebeleid voor gegevensverlies](dlp-learn-about-dlp.md)
- [Gevoeligheidslabels](sensitivity-labels.md)
- [Retentielabels](retention.md)
- [Intern risicobeheer](insider-risk-management.md)
- [Communicatiecompliance](communication-compliance.md)
- [Beleid voor automatisch labelen](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [Privacybeheer (preview)](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a>Basisonderdelen van een type gevoelige informatie

Elke entiteit van het type gevoelige informatie wordt gedefinieerd door deze velden:

- naam: de manier waarop naar het type gevoelige informatie wordt verwezen
- beschrijving: beschrijft wat het type gevoelige informatie zoekt
- patroon: Een patroon definieert wat een gevoelige informatietype detecteert. Deze bestaat uit de volgende onderdelen
    - Primair element: het hoofdelement dat het gevoelige informatietype zoekt. Het kan een normale **expressie zijn** met of zonder een checksumvalidatie, een **trefwoordlijst,** een woordenlijst **met** trefwoorden of een **functie.**
    - Ondersteunend element: elementen die fungeren als ondersteunend bewijs om het vertrouwen van de overeenkomst te vergroten. Trefwoord 'SSN' bijvoorbeeld in de nabijheid van een SSN-getal. Het kan een normale expressie zijn met of zonder een checksumvalidatie, trefwoordlijst, trefwoordwoordenlijst.
    - Betrouwbaarheidsniveau: betrouwbaarheidsniveaus (hoog, gemiddeld, laag) geven aan hoeveel ondersteunend bewijs samen met het primaire element is gevonden. Hoe meer ondersteunend bewijs een item bevat, hoe groter het vertrouwen dat een overeenkomend item de gevoelige informatie bevat die u zoekt.
    - Nabijheid: aantal tekens tussen primair en ondersteunend element

![Diagram van ondersteunende gegevens en nabijheidsmarge](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

Meer informatie over betrouwbaarheidsniveaus in deze video


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a>Voorbeeld van het type gevoelige informatie


## <a name="argentina-national-identity-dni-number"></a>Argentinië national identity (DNI) number

### <a name="format"></a>Opmaak

Acht cijfers gescheiden door perioden

### <a name="pattern"></a>Patroon

Acht cijfers:
- twee cijfers
- een punt
- drie cijfers
- een punt
- drie cijfers

### <a name="checksum"></a>Checksum

Nee

### <a name="definition"></a>Definitie

Een DLP-beleid heeft een gemiddeld vertrouwen dat dit type gevoelige informatie is gedetecteerd als dit binnen een nabijheid van 300 tekens:
- De normale expressie Regex_argentina_national_id inhoud die overeenkomt met het patroon.
- Er wordt een trefwoord Keyword_argentina_national_id gevonden.

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a>Trefwoorden

#### <a name="keyword_argentina_national_id"></a>Keyword_argentina_national_id

- Nationale identiteitsnummer argentinië 
- Identiteit 
- Identificatie nationale identiteitskaart 
- DNI 
- NIC National Registry of Persons 
- Documento Nacional de Identidad 
- Registro Nacional de las Personas 
- Identidad 
- Identificación 

### <a name="more-on-confidence-levels"></a>Meer informatie over betrouwbaarheidsniveaus

In een entiteitsdefinitie van het type gevoelige informatie **geeft** betrouwbaarheidsniveau aan hoeveel ondersteunend bewijs wordt gedetecteerd naast het primaire element. Hoe meer ondersteunend bewijs een item bevat, hoe groter het vertrouwen dat een overeenkomend item de gevoelige informatie bevat die u zoekt. Overeenkomsten met een hoog betrouwbaarheidsniveau bevatten bijvoorbeeld meer ondersteunend bewijs in de nabijheid van het primaire element, terwijl overeenkomsten met een laag betrouwbaarheidsniveau in de nabijheid weinig tot geen ondersteunend bewijs bevatten. 

Een hoog betrouwbaarheidsniveau retourneert de minste onwaar-positieven, maar kan leiden tot meer onwaar negatieven. Lage of gemiddelde betrouwbaarheidsniveaus retourneert meer onwaar-positieve waarden, maar weinig tot nul onwaar negatieven.

- **weinig vertrouwen:** waarde van 65, overeenkomende items bevat de minste onwaar negatieven, maar de meeste onwaar positieven. Lage betrouwbaarheid retourneert alle overeenkomsten met lage, gemiddelde en hoge betrouwbaarheid.
- **gemiddeld vertrouwen:** waarde van 75, overeenkomende items bevat een gemiddelde hoeveelheid onwaar-positieven en onwaar negatieven. Gemiddeld vertrouwen retourneert alle gemiddelde en hoge betrouwbaarheids matches.  
- **hoog vertrouwen:** waarde van 85, overeenkomende items bevat de minste onwaar-positieven, maar de meeste onwaar negatieven. Hoog vertrouwen geeft alleen overeenkomsten met hoog vertrouwen als rendement.  

Gebruik patronen met een hoog betrouwbaarheidsniveau met lage tellingen, bijvoorbeeld vijf tot tien, en lage betrouwbaarheidspatronen met hogere tellingen, bijvoorbeeld 20 of meer.

> [!NOTE]
> Als u bestaande beleidsregels of aangepaste gevoelige informatietypen (SIT's) hebt gedefinieerd met behulp van betrouwbaarheidsniveaus op basis van een getal (ook bekend als nauwkeurigheid), worden deze automatisch aan de drie afzonderlijke betrouwbaarheidsniveaus toegesneden. weinig vertrouwen, gemiddeld vertrouwen en veel vertrouwen in de gebruikersinterface van het Beveiligings- en compliancecentrum.
> - Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus tussen 76 en 100 worden in kaart gebracht op hoog vertrouwen. 
> - Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus tussen 66 en 75 worden in kaart gebracht op gemiddeld vertrouwen.
> - Alle beleidsregels met minimale nauwkeurigheid of aangepaste SIT-patronen met betrouwbaarheidsniveaus kleiner dan of gelijk aan 65, worden in kaart gebracht aan lage betrouwbaarheid. 

## <a name="creating-custom-sensitive-information-types"></a>Aangepaste gevoelige informatietypen maken

Als u aangepaste gevoelige informatietypen wilt maken in het beveiligings- & compliancecentrum, kunt u kiezen uit verschillende opties:

- **De gebruikersinterface gebruiken** U kunt een aangepast type gevoelige informatie instellen met behulp van de gebruikersinterface & compliancecentrum. Met deze methode kunt u gewone expressies, trefwoorden en woordenlijsten voor trefwoorden gebruiken. Zie Een aangepast type gevoelige informatie maken voor [meer informatie.](create-a-custom-sensitive-information-type.md)

- **EDM gebruiken** U kunt aangepaste gevoelige informatietypen instellen met de classificatie Exact Data Match (EDM). Met deze methode kunt u een dynamisch type gevoelige informatie maken met behulp van een beveiligde database die u regelmatig kunt vernieuwen. Zie [Een aangepast type gevoelige informatie maken met de classificatie Exacte gegevensmatch.](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

- **PowerShell gebruiken** U kunt aangepaste gevoelige informatietypen instellen met PowerShell. Hoewel deze methode complexer is dan het gebruikersinterface, hebt u meer configuratieopties. Zie [Een aangepast type gevoelige informatie maken in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).



> [!NOTE]
> Verbeterde betrouwbaarheidsniveaus zijn beschikbaar voor direct gebruik in preventie van gegevensverlies voor Microsoft 365-services, Microsoft Information Protection voor Microsoft 365-services, Communicatie compliance, informatiebeheer en recordsbeheer.
> Microsoft 365 Information Protection ondersteunt nu dubbele bytetekensettalen voor:
> - Vereenvoudigd Chinees
> - Traditioneel Chinees
> - Korean
> - Japanese
> 
> Deze ondersteuning is beschikbaar voor typen gevoelige informatie. Zie [Ondersteuning voor Information Protection voor releaseopmerkingen bij dubbel-bytetekensets (preview)](mip-dbcs-relnotes.md) voor meer informatie.

> [!TIP]
> Om patronen te detecteren die Chinese/Japanse karakters en enkelbyte karakters bevatten of om patronen te detecteren die Chinees/Japans en Engels bevatten, definieert u twee varianten van het trefwoord of de regex.
> 
> Om bijvoorbeeld een trefwoord als "机密的document" te detecteren, gebruikt u twee varianten van het trefwoord; een met een spatie tussen de Japanse en Engelse tekst en een andere zonder een spatie tussen de Japanse en Engelse tekst. De trefwoorden die in de SIT moeten worden toegevoegd, moeten dus "机密的 document" en "机密的document" zijn. Evenzo moeten twee varianten worden gebruikt om een zin "東京オリンピック2020" te detecteren; "東京オリンピック 2020" en "東京オリンピック2020".
> 
> Tijdens het maken van een regex met behulp van een dubbel byteafbreekstreepje of een dubbele byteperiode, moet u ervoor zorgen dat beide tekens, zoals één, een afbreekstreepje of een punt in een regex. Hier volgt een voorbeeld van een regex ter referentie:
>    - (?<!\d)([４][０-９]{3}[\-?\－\t]*[０-９]{4}
>
> Het is raadzaam tekenreeksmatch te gebruiken in plaats van woordmatch in een trefwoordlijst.

## <a name="for-further-information"></a>Voor meer informatie
- [Entiteitsdefinities voor het type gevoelige informatie](sensitive-information-type-entity-definitions.md)
- [Een aangepast type gevoelige informatie maken](create-a-custom-sensitive-information-type.md)
- [Een aangepast type gevoelige informatie maken in PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)

Zie Informatiebeveiliging implementeren voor privacyregels voor gegevens met [](../solutions/information-protection-deploy.md) Microsoft 365 (aka.ms/m365dataprivacy).

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
