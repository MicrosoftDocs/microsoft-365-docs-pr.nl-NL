---
title: Uitleg typen
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over uitleg typen in Microsoft SharePoint Syntex
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295850"
---
# <a name="introduction-to-explanation-types"></a>Inleiding tot uitleg typen

Gebruik uitleg voor hulp bij het definiëren van de informatie die u wilt labelen en extraheren in uw document met de informatie over modellen voor Microsoft SharePoint Syntex. Wanneer u een uitleg maakt, moet u ervoor zorgen dat u een uitleg type selecteert. 

Dit artikel helpt u inzicht te krijgen in de verschillende typen uitleg en hoe deze worden gebruikt.

   ![Uitleg typen](../media/content-understanding/explanation-types.png) 
   
Deze uitleg typen zijn beschikbaar:

- **Woordgroepenlijst**: een lijst met woorden, woordgroepen, getallen of andere tekens die u kunt gebruiken in het document of de gegevens die u wilt ophalen. De tekstreeks die **verwijst** naar de tekstreeks, is bijvoorbeeld in alle medische verwijzingen die u identificeert.</br>

- **Patroon lijst**: een lijst met getallen, letters of andere tekens die u kunt gebruiken om de informatie die u extraheert te identificeren. U kunt bijvoorbeeld het **telefoonnummer** van de betreffende dokter extraheren uit elk document dat u identificeert voor de medische verwijzing.</br>

- **Proximity**: hierin wordt beschreven hoe u de uitleg dicht bij elkaar hebt. Zo wordt een patroon lijst voor een *straatnummer* direct weergegeven vóór de naam van de *straatnaam* , zonder tokens ertussen (u kunt verderop in dit artikel meer informatie over tokens vinden). 
 
## <a name="phrase-list"></a>Lijst met zinnen

Een beschrijving van de lijst met zinnen wordt meestal gebruikt voor het identificeren en classificeren van een document via uw model. Zoals beschreven in het voorbeeld van het *verwijzen van dokter* , is dit een reeks woorden, zinnen, getallen of tekens die consistent zijn in de documenten die u identificeert.

Hoewel u geen behoefte hebt, kunt u een betere succesvolle beschrijving krijgen als de woordgroep die u vastlegt, op een consistente locatie in het document staat. Het label van de *verwijzings dokter* kan bijvoorbeeld consistent zijn in de eerste alinea van het document.

Als hoofdlettergevoeligheid een vereiste is voor het identificeren van uw etiket, kunt u dit in uw uitleg opgeven door het selectievakje **alleen exact hoofdlettergebruik** in te schakelen.

   ![Hoofdlettergevoeligheid](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Patroon lijsten

Een patroon lijsttype is vooral handig als u een uitleg maakt waarmee informatie wordt geïdentificeerd en opgehaald uit een document. Dit wordt meestal weergegeven in verschillende notaties, zoals datums, telefoonnummers of creditcardnummers. Zo kan een datum worden weergegeven in verschillende notaties (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020, enzovoort). Door een patroon lijst te definiëren, wordt uw uitleg efficiënter gemaakt door eventuele variaties te vastleggen in de gegevens die u wilt identificeren en uitpakken. 

Voor het voorbeeld van het **telefoonnummer** pakt u het telefoonnummer voor elke verzorgde dokter uit met alle medische Referral documenten die door het model worden geïdentificeerd. Wanneer u de uitleg maakt, selecteert u het lijsttype patroon om de verschillende opmaken toe te staan die u mogelijk verwacht te retourneren.

   ![Lijst met opvultekens voor telefoonnummers](../media/content-understanding/pattern-list.png)

Voor dit voorbeeld selecteert u het selectievakje **willekeurig cijfer uit 0-9** . Als u deze optie selecteert, wordt de waarde ' 0 ' in de lijst patroon herkend als een cijfer van 0 tot en met 9.

   ![Willekeurig cijfer uit 0-9](../media/content-understanding/digit-identity.png)

Als u een patroon lijst maakt met teksttekens, selecteert u ook de **letter van a-z** . Als u deze optie selecteert, wordt elk willekeurig teken dat in de lijst patroon wordt gebruikt, herkend als een willekeurig teken van ' a ' tot ' z '.

Als u bijvoorbeeld een lijst met **datum** patronen maakt en u er zeker van wilt zijn dat de datumnotatie *1 januari 2020* wordt herkend, moet u het volgende doen:
- Voeg *AAA 0, 0000* en *AAA 00, 0000* toe aan de lijst patroon.
- Zorg ervoor dat **de letter van a-z** ook is geselecteerd.

   ![Een willekeurige letter van a-z](../media/content-understanding/any-letter.png)

Daarnaast hebt u de mogelijkheid om het selectievakje **alleen exact hoofdlettergebruik** in te schakelen in de lijst patroon. Voor het voorbeeld van de datum als u de eerste letter van de maand moet worden gekapitaliseerd, moet u het volgende doen:

- Voeg *AAA 0, 0000* en *AAA 00, 0000* toe aan de lijst patroon.
- Zorg ervoor dat u ook **exact de juiste hoofdletters** selecteert.

   ![Alleen exact hoofdlettergebruik](../media/content-understanding/exact-caps.png)

> [!NOTE]
> In plaats van een uitleg van de patroon lijst handmatig te maken, gebruikt u de [uitleg bibliotheek]() om vooraf gemaakte patroon lijstsjablonen te gebruiken voor veelgebruikte patroon lijst, zoals *datum*, *telefoonnummer*, *creditcardnummer*, enzovoort. 

## <a name="proximity"></a>Buurt 

Het type uitleg bij de buurt helpt uw modelgegevens te identificeren door te definiëren hoe u een ander stuk van de gegevens wilt opslaan. In uw model hebt u bijvoorbeeld twee uitleg gedefinieerd met een naam voor het *adres* en het *telefoonnummer*van de klant. 

U ziet ook dat telefoonnummers van klanten altijd voor het adres van de klant worden weergegeven. 

Alex Wilburn<br>
555-555-5555<br>
Eén Microsoft-manier<br>
Redmond, WA 98034<br>

Gebruik de uitleg van de nabijheid van het nummer om aan te geven hoe ver u wilt dat het nummer van de telefoon wordt aangegeven in uw documenten.

   ![Uitleg over proximity](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Wat zijn tokens?

Als u het type proximity uitleg wilt gebruiken, begrijpt u wat een token is, aangezien het aantal tokens de afstand tussen de Proximity-uitleg en de een andere uitleg.  

Een token is een doorlopend bereik (geen spaties of leestekens) van letters en cijfers. Een spatie is geen token. Elk leesteken is een token. In de volgende tabel ziet u enkele voorbeelden van het bepalen van het aantal tokens in een woordgroep.

|Zinnen|Aantal tokens|Uitleg|
|--|--|--|
|`Dog`|1|Eén woord zonder leestekens of spaties.|
|`RMT33W`|1|Een record-locator-nummer. Het is mogelijk dat er cijfers en letters zijn, maar geen leestekens.|
|`425-555-5555`|vijf|Een telefoonnummer. Elk interpunctie is één token, dus  `425-555-5555` moet u 5 tokens hebben:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7,5|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Het uitleg type proximity configureren

Voor het voorbeeld moet u de nabijheids instelling configureren, zodat we het bereik van het aantal tokens opgeven dat door het *telefoon* *nummer wordt* uitgelegd.

U ziet dat het minimale bereik 0 is omdat er geen tokens zijn tussen het telefoonnummer en het adres.

Sommige telefoonnummers in de voorbeelddocumenten worden echter met *(mobiel)* toegevoegd.

Nestor Wilke<br>
111-111-1111 (mobiel)<br>
Eén Microsoft-manier<br>
Redmond, WA 98034<br>

Er zijn drie tokens in *(mobiele nummers)*:

|Zinnen|Aantal tokens|
|--|--|
|(|1|
|mobiele|3|
|)|driefasig|

Configureer de nabijheids instelling voor een bereik van 0 tot en met 3.

   ![Voorbeeld van proximity](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a>De uitleg bibliotheek gebruiken

Hoewel u handmatig verschillende waarden voor de patroon lijst voor uw uitleg kunt toevoegen, kunt u het beste gebruikmaken van de vooraf gemaakte sjablonen die u aan u hebt verstrekt in de uitleg bibliotheek.

In plaats van alle variaties voor *datum*handmatig toe te voegen, gebruikt u de sjabloon patroon lijst voor *datum*die al een aantal waarden voor patroon lijsten omvat:</br>

   ![Uitleg bibliotheek](../media/content-understanding/explanation-template.png)</br>
 
De uitleg bibliotheek bevat een aantal veelgestelde beschrijvingen van patroon lijsten, waaronder:</br>

- Einddatum</br>
- Datum (getal)</br>
- Fase</br>
- Nummer</br>
- Telefoonnummer</br>
- Postcode</br>
- Eerste woord van de zin</br>
- Credit Card</br>
- Sofi-nummer</br>

Houd er rekening mee dat de uitleg bibliotheek ook sjablonen bevat voor uitleg over de lijst met zinnen, waaronder:
- Einde van de zin
- Meerdere

#### <a name="to-use-a-template-from-the-explanation-library"></a>Een sjabloon uit de uitleg bibliotheek gebruiken

1. Selecteer in het gedeelte **uitleg** van de **Train** -pagina van uw model de optie **Nieuw**en selecteer vervolgens **een sjabloon op basis van een sjabloon**.</br>

   ![Maken op basis van sjabloon](../media/content-understanding/from-template.png)</br>

2.  Selecteer op de pagina met **uitleg sjablonen** de uitleg die u wilt gebruiken en selecteer vervolgens **toevoegen**.</br>

       ![Een sjabloon selecteren](../media/content-understanding/phone-template.png)</br>

3. De gegevens voor de sjabloon die u hebt geselecteerd, worden weergegeven op de pagina **een uitleg maken** . Bewerk, indien nodig, de naam van de uitleg en voeg items toe aan of verwijder ze uit de lijst patroon. </br> 

   ![Sjabloon bewerken](../media/content-understanding/phone-template-live.png)</br>

4. Selecteer **Opslaan**wanneer u klaar bent.
