---
title: Uitlegtypen
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Meer informatie over uitlegtypen in Microsoft SharePoint Syntex
ms.openlocfilehash: 5187b27438f25db1a2714f1fbc7b31db6d060ccc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928398"
---
# <a name="introduction-to-explanation-types"></a>Inleiding tot uitlegtypen

Uitleg wordt gebruikt om de gegevens te definiëren die je wilt labelen en ophalen in je documentinformatie over modellen in Microsoft SharePoint Syntex. Bij het maken van een uitleg moet je een uitlegtype selecteren. In dit artikel vind je meer informatie over de verschillende uitlegtypen en hoe je deze kunt gebruiken. 

   ![Uitlegtypen](../media/content-understanding/explanation-types.png) 
   
Deze uitlegtypen zijn beschikbaar:

- **Frasenlijst**: Lijst met woorden, woordgroepen, getallen of andere tekens die je kunt gebruiken in het document of de gegevens die je wilt ophalen. De tekenreeks **Verwijzen naar Doctor** wordt bijvoorbeeld gebruikt in medische verwijsdocumenten die je identificeert.</br>

- **Patroonlijst**: lijst patronen met getallen, letters of andere tekens die je kunt gebruiken om de gegevens te identificeren die je wilt ophalen. Je kunt bijvoorbeeld het **Telefoonnummer** van de verwijsarts extraheren uit medische verwijsdocumenten die je identificeert.</br>

- **Proximity**: in dit artikel wordt beschreven hoe dicht toelichtingen bij elkaar liggen. Een patroonlijst van *straatnummer* wordt bijvoorbeeld direct weergeven voor de woordenlijst met *straatnamen* zonder tokens ertussen (je vind meer informatie over tokens verderop in dit artikel). Voor het type proximity moet je ten minste twee uitleggen in je model hebben, of de optie wordt uitgeschakeld. 
 
## <a name="phrase-list"></a>Woordenlijst

Het uitlegtype van een woordenlijst wordt meestal gebruikt om een document te identificeren en te classificeren via je model. Zoals wordt beschreven in het labelvoorbeeld *Verwijzende arts*, is het een tekenreeks met woorden, woordgroepen, getallen of tekens die consequent voorkomen in de documenten die je wilt herkennen.

Hoewel het geen eis is, kunt je je uitleg beter laten opvallen als de woordgroep die je wilt vastleggen zich op een consistente locatie in het document bevindt. Zo kan het label *Verwijzende arts* label zich in de eerste alinea van het document bevinden.

Als hoofdlettergevoeligheid een vereiste is bij het identificeren van je label, kun je met het woordenlijsttype in uw uitleg opgeven door het selectievakje **Alleen exacte kapitalisatie** in te schakelen.

   ![Onderscheid tussen hoofdletters en kleine letters](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a>Patroonlijsten

Een patroonlijst is met name handig wanneer je een uitleg maakt waarmee gegevens uit een document worden geïdentificeerd en opgehaald. Deze worden meestal weergegeven in verschillende indelingen, zoals datums, telefoonnummers of creditcardnummers. Een datum kan bijvoorbeeld worden weergegeven in een aantal verschillende notaties (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 1 januari 2020, enzovoort). Door een patroonlijst te definiëren, kun je je efficiënter identificeren door eventuele variaties in de gegevens vast te leggen die je probeert vast te stellen en op te halen. 

Voor het voorbeeld **Telefoonnummer** moet je het telefoonnummer voor elke verwijzende arts ophalen uit alle Medische Verwijzingsdocumenten die door het model worden geïdentificeerd. Wanneer je de uitleg maakt, selecteer je het patroonlijsttype om de verschillende indelingen toe te staan die mogelijk naar verwachting worden geretourneerd.

   ![Patroonlijst telefoonnummers](../media/content-understanding/pattern-list.png)

Voor dit voorbeeld selecteert u het selectievakje **een cijfer van 0-9** als u elke ' 0 ' waarde die in de patroonlijst wordt gebruikt, wilt herkennen aan een cijfer van 0 tot en met 9.

   ![Een willekeurig cijfer van 0-9](../media/content-understanding/digit-identity.png)

Als u een patroonlijst maakt die teksttekens bevat, selecteert u het selectievakje **een letter van a-z** om elk teken dat wordt gebruikt in de patroonlijst te herkennen aan een teken van a tot en met z.

Als je bijvoorbeeld een patroonlijst **Datum** maakt en je ervoor wilt zorgen dat een datumnotatie wordt ondersteund zoals *2020 1 januari*, moet je het volgende doen:
- Voeg *AAA 0, 0000* en *AAA 00, 0000* aan de patroonlijst toe.
- Zorg ervoor dat **Een willekeurige letter van a-z** is geselecteerd.

   ![Een letter van a-z](../media/content-understanding/any-letter.png)

Als je hoofdlettereisen in je patroonlijst hebt, kun je ook het selectievakje **Alleen exact hoofdlettergebruik** selecteren. Als de eerste letter van de maand moet worden gekapitaliseerd, moet je het volgende doen:

- Voeg *Aaa 0, 0000* en *AAA 00, 0000* aan de patroonlijst toe.
- Zorg ervoor dat **Alleen exact hoofdlettergebruik** ook is geselecteerd.

   ![Alleen exact hoofdlettergebruik](../media/content-understanding/exact-caps.png)

> [!NOTE]
> Gebruik in plaats van het handmatig maken van een uitleg voor patroonlijsten de [uitlegbibliotheek](#use-explanation-templates) voor het gebruik van vooraf gemaakte patroonlijstsjablonen voor een algemene patroonlijst, zoals *datum*, *telefoonnummer*, *creditcardnummer*, enzovoort.

## <a name="proximity"></a>Proximity 

Met het Proximity-uitlegtype kan je model identificeren met behulp van hoe dichtbij een ander stukje gegevens is. Bijvoorbeeld, in je model heb je twee verklaringen gedefinieerd waaraan zowel het *huisnummer* als *telefoonnummer* zijn gelabeld. 

Je ziet ook dat de telefoonnummers van klanten altijd voor het huisnummer worden weergegeven. 

Alex Wilburn<br>
555-555-5555<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Gebruik de proximity-uitleg om te bepalen hoe ver de uitleg van een telefoonnummer is zodat u het huisnummer in je documenten beter kunt identificeren.

   ![Proximity-uitleg](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a>Wat zijn tokens?

Voor het gebruik van het Proximity-uitlegtype moet je weten wat een token is, omdat het aantal tokens is hoe de proximity-uitleg de afstand tussen een verklaring en een andere meet. Een token is een doorlopende reeks (geen spaties of interpunctie) van letters en cijfers. 

In de volgende tabel zie je enkele voorbeelden van hoe je het aantal tokens in een woordgroep kunt vaststellen.

|Woordengroep|Aantal tokens|Uitleg|
|--|--|--|
|`Dog`|1|Eén woord zonder leesteken of spatie.|
|`RMT33W`|1|Een record locatornummer. Het mag cijfers en letters bevatten, maar geen leestekens.|
|`425-555-5555`|5|Een telefoonnummer. Elk leesteken bestaat uit één token, zodat `425-555-5555` 5 tokens zou zijn:<br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|7|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a>Het proximity-uitlegtype configureren

Voor het voorbeeld configureer je de proximity-instelling zodanig dat je het aantal tokens kunt definiëren in *Telefoonnummer*-uitleg afkomstig van de *Huisnummer*-uitleg. Je ziet dat het minimumbereik “0“ is omdat er geen tokens zijn tussen het telefoonnummer en het huisnummer.

Sommige telefoonnummers in de voorbeelddocumenten worden echter toegevoegd met *(mobiel)*.

Wander Kuijken<br>
111-111-1111 (mobiel)<br>
One Microsoft Way<br>
Redmond, WA 98034<br>

Er zijn drie tokens in *(mobiel)*:

|Woordengroep|Aantal tokens|
|--|--|
|(|1|
|Mobiel|2|
|)|3|

Configureer de proximity-instelling voor een bereik van 0 tot en met 3.

   ![Voorbeeld van proximity](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a>Configureren waar woordgroepen voorkomen in het document

Wanneer u een uitleg maakt, wordt standaard in het hele document gezocht naar de woordgroep die u wilt extraheren. U kunt echter de geavanceerde instelling <b>Waar deze woordgroepen voorkomen</b> gebruiken om een specifieke locatie in het document te isoleren waar een woordgroep voorkomt. Dit is handig in situaties waarin soortgelijke gevallen van een woordgroep ergens anders in het document kunnen worden weergegeven en u wilt ervoor zorgen dat de juiste is geselecteerd. Wanneer we kijken naar ons voorbeelddocument voor medische verwijzing, wordt de **Verwijzende arts** altijd in de eerste alinea van het document vermeld. Met de instelling <b>Waar deze woordgroepen voorkomen</b> kunt u in dit voorbeeld de uitleg zo configureren dat alleen in het begin van het document naar dit label wordt gezocht, of op een andere locatie waar dit kan voorkomen.

   ![Instelling Waar deze woordgroepen voorkomen](../media/content-understanding/phrase-location.png)</br>

U kunt kiezen uit de volgende opties voor deze instelling:

- Overal in het bestand: in het hele document wordt naar de woordgroep gezocht.
- Begin van het bestand: het document wordt vanaf het begin tot aan de locatie van de woordgroep doorzocht.</br> 
   ![Begin van bestand](../media/content-understanding/beginning-of-file.png)</br>
In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen. De waarde van <b>Eindpositie</b> wordt bijgewerkt om het aantal tokens weer te geven dat het geselecteerde gebied bevat. U kunt de waarde van de Eindpositie ook bijwerken om het geselecteerde gebied aan te passen.</br>
   ![Vak Begin van bestandspositie](../media/content-understanding/beginning-box.png)</br>

- Einde van het bestand: het document wordt vanaf het eind tot aan de locatie van de woordgroep doorzocht.</br> 
   ![Einde van bestand](../media/content-understanding/end-of-file.png)</br>
In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen. De waarde van <b>Beginpositie</b> wordt bijgewerkt om het aantal tokens weer te geven dat het geselecteerde gebied bevat. U kunt de waarde van de Beginpositie ook bijwerken om het geselecteerde gebied aan te passen.</br> 
   ![Vak Einde van bestand](../media/content-understanding/end-box.png)</br>
- Aangepast bereik: in een bepaald bereik binnen het document wordt gezocht naar de locatie van de woordgroep.</br> 
   ![Aangepast bereik](../media/content-understanding/custom-file.png)</br>
In de viewer kunt u het selectievakje handmatig aanpassen zodat de locatie van de woordgroep wordt opgenomen. Voor deze instelling moet u een <b>Beginpositie</b> en een <b>Eindpositie</b> selecteren. Deze waarden geven het aantal tokens aan vanaf het begin van het document. Hoewel u deze waarden handmatig kunt invoeren, is het eenvoudiger om het selectievakje handmatig aan te passen in de viewer.</br> 
   
## <a name="use-explanation-templates"></a>Uitlegsjablonen gebruiken

Je kan handmatig verschillende frasenlijstwaarden toevoegen voor je uitleg, maar het kan eenvoudiger door sjablonen te gebruiken die aangeboden worden in de uitlegbibliotheek.

Je kunt bijvoorbeeld in plaats van alle variaties voor *Datum* handmatig toe te voegen, de frasenlijstsjabloon gebruiken voor *Datum*, die al een aantal frasenlijstwaarden bevat:</br>

   ![Uitlegbibliotheek](../media/content-understanding/explanation-template.png)</br>
 
De uitlegbibliotheek bevat een aantal veelgebruikte beschrijvingen van de frasenlijst, waaronder:</br>

- Datum</br>
- Datum (getal)</br>
- Tijd</br>
- Nummer</br>
- Percentage</br>
- Telefoonnummer</br>
- Postcode</br>
- Eerste woord of zin</br>
- Afgelopen zin</br>
- Creditcard</br>
- Sofi-nummer</br>
- Selectievakje</br>
- Valuta</br>
- E-mail CC</br>
- E-mail datum</br>
- E-mail groet</br>
- E-mail ontvanger</br>
- E-mail afzender</br>
- E-mail onderwerp</br>

De uitlegbibliotheek bevat ook drie automatische sjabloontypen die binnen de gegevens werken die je gelabeld hebt in je voorbeeldbestanden:

- After-label: De woorden of karakters die voorkomen na de labels in de voorbeeldbestanden.</br>
- Before-label: De woorden of karakters die voorkomen voor de labels in de voorbeeldbestanden.</br>
- Labels: Tot maximaal de eerste 10 karakters van de voorbeeldbestanden.</br>

Automatische sjablonen werken bijvoorbeeld zoals in het volgende voorbeeldbestand waar we de before-label-uitlegsjabloon gebruiken om het model meer informatie te geven zodat we tot een nauwkeurigere overeenkomst komen.

   ![Voorbeeldbestand](../media/content-understanding/before-label.png)</br>

Als je het before-label-uitlegsjabloon selecteert, zoekt het de eerste groep woorden die voorkomen vóór het label in je voorbeeldbestanden. In het voorbeeld is het woord dat geïdentificeerd werd ‘Vanaf’.

   ![Before-labelsjabloon](../media/content-understanding/before-label-explanation.png)</br>

Je kan een uitleg voor een sjabloon maken door <b>Toevoegen</b> te selecteren.  Aanvullende woorden worden geïdentificeerd en toegevoegd aan de frasenlijst naargelang je meer voorbeeldbestanden toevoegt.

   ![Het label toevoegen](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a>Een sjabloon gebruiken uit de uitlegbibliotheek

1. Ga naar het gedeelte **Uitleg** van de **Train**-pagina van je model en selecteer **Nieuwe** en selecteer vervolgens **Van een sjabloon**.</br>

   ![Before-label toevoegen](../media/content-understanding/from-template.png)</br>

2.  Selecteer op de pagina **Uitlegsjablonen** de uitleg die je wilt gebruiken en selecteer vervolgens **Toevoegen**.</br>

       ![Selecteer een sjabloon](../media/content-understanding/phone-template.png)</br>

3. De informatie voor de sjabloon die je hebt geselecteerd, wordt weergegeven op de pagina **Een uitleg maken**. Bewerk zo nodig de naam van de uitleg en voeg items toe of verwijder items uit de frasenlijst. </br> 

   ![Sjabloon bewerken](../media/content-understanding/phone-template-live.png)</br>

4. Selecteer **Opslaan** wanneer je klaar bent.