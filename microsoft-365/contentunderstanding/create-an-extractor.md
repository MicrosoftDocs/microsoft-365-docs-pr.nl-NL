---
title: Een extractor maken
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Lees hoe je een Extractor kunt maken in Microsoft SharePoint Syntex.
ms.openlocfilehash: d68cc8b8c337c1ae6740eb5775576a54279b8389
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321807"
---
# <a name="create-an-extractor-preview"></a>Een extractor maken (Voorbeeld)


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Vóór of na het maken van een classificatiemodel voor het automatiseren van de identificatie en classificatie van specifieke documenttypen, kun je desgewenst extra uittreksels toevoegen aan je model om specifieke informatie uit deze documenten te halen. Het is bijvoorbeeld mogelijk dat je wilt dat je model niet alleen wordt herkend aan *alle* documenten die worden toegevoegd aan de documentbibliotheek, maar je kunt ook de *service-begindatum* voor elk document weergeven als een kolomwaarde in de documentbibliotheek.

Je moet een extractor maken voor elke entiteit in het document die je wilt ophalen. In ons voorbeeld willen we de  **begindatum van de service**extraheren voor elke  **contractvernieuwing** -document dat door het model wordt geïdentificeerd. We willen een weergave kunnen zien in de documentbibliotheek van alle **contract** documenten, met een kolom waarin de **begindatum van de service** van elk document wordt weergegeven. 

> [!NOTE]
> Als je een extractor wilt maken, gebruik je dezelfde bestanden die je eerder hebt geüpload om de classificatie te trainen. 

## <a name="name-your-extractor"></a>Een naam voor de Extractor geven

1. Klik op de startpagina van het model op **Train Extractor** in de tegel **Extractor maken en trainen**.
2. Typ in het scherm **New entiteit Extractor** de naam van je extractor in het veld **Nieuwe extractorname**. Als je bijvoorbeeld de **begindatum van de service** wilt wijzigen als je de begindatum van de service wilt ophalen uit elk document voor het verlengen van een contract. Je kunt er ook voor kiezen om een eerder gemaakte kolom opnieuw te gebruiken (bijvoorbeeld een kolom met beheerde metagegevens).
3. Klik op **Maken**.

## <a name="add-a-label"></a>Een label toevoegen

De volgende stap bestaat uit het label van de entiteit die je wilt ophalen in de voorbeeldbestanden van de training.

Als je de Extractor maakt, wordt de extractor-pagina geopend. Hier zie je een lijst met je voorbeeldbestanden, met het eerste bestand in de lijst die wordt weergegeven in de viewer.

1. Selecteer in de viewer de gegevens die je wilt ophalen uit de bestanden. Als je bijvoorbeeld de *begindatum van service*wilt ophalen, markeer je de datumwaarde in het eerste bestand (*maandag, 14 oktober 2019*). en klik dan op **Opslaan**.  De weergave van de waarde wordt weergegeven in het bestand in de lijst voorbeelden met een bijschrift onder de **labelkolom**.
2. Selecteer **Volgende bestand** om automatisch op te slaan en het volgende bestand te openen in de lijst in de viewer. Of selecteer **Opslaan** en selecteer een ander bestand van de lijst **Gelabelde voorbeelden**.
3. Herhaal stap 1 en 2 in de viewer en herhaal dit totdat je het label in alle vijf bestanden hebt opgeslagen.

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 

 
Wanneer je vijf bestanden hebt voorzien van een label, wordt een melding weergegeven met de mededeling dat je wilt overstappen op de training. Je kunt ervoor kiezen om meer documenten beter te labelen of verder te gaan met de training. 

## <a name="add-an-explanation"></a>Voeg een uitleg toe

In ons voorbeeld gaan we een uitleg maken met een aanwijzing voor de indeling van de label zelf en de variaties in de voorbeelddocumenten. Een datum kan bijvoorbeeld worden weergegeven in een aantal verschillende notaties:
- 10/14/2019
- 14 oktober 2019
- Maandag 14 oktober 2019
 

Als je de *begindatum van de service* wilt identificeren kun je een uitleg bij het patroon maken.

1. In de sectie uitleg selecteer je **Nieuw** en type een naam (bijvoorbeeld, *Leeg*).
2. Selecteer bij type **Patroonlijst**.
3. Geef bij waarde de datumvariant op zoals deze wordt weergegeven in de voorbeeldbestanden. Als je bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, geef je de variaties op die worden weergegeven in je documenten, zoals:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Kies **Opslaan**.

> [!NOTE]
> Zie [Uitlegtypen](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview)voor meer informatie over uitlegtypen.  


### <a name="use-the-explanation-library"></a>De Uitlegbibliotheek gebruiken

Voor het maken van toelichtingen voor items als datums, is het eenvoudiger om [de uitlegbibliotheek te gebruiken](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-the-explanation-library) dan om alle variaties handmatig in te voeren. De uitlegbibliotheek is een set vooraf gedefinieerde frasen en patroonverklaringen. De bibliotheek biedt alle indelingen voor veelgebruikte woordenlijsten of patroonlijsten, zoals datums, telefoonnummers en postcodes. 

Voor het voorbeeld*Begindatum van de service* is het efficiënter om de vooraf gedefinieerde uitleg voor *Datum* te gebruiken in de uitlegbibliotheek:

1. In de **Sectie uitleg** selecteer je **Nieuw** en vervolgens **Uit Uitlegbibliotheek**.
2. Uit de uitlegbibliotheek, selecteer **Datum**. Je kunt alle datumvariaties weergeven die worden herkend.
3. Kies **Toevoegen**.</br>

    ![Uitlegbibliotheek](../media/content-understanding/explanation-library.png) 

4. Op de pagina **een uitleg maken** wordt de *Datum* informatie uit de uitlegbibliotheek automatisch ingevuld op de velden. Kies **Opslaan**.</br>

    ![Datum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a>Het model trainen 

Je uitleg start de training opslaan. Als je model voldoende gegevens heeft om de gegevens uit de voorbeeldbestanden met een label te halen, zie je elk bestand dat is gemarkeerd met **Overeenkomst**.  

![Match](../media/content-understanding/match2.png) 

Als er niet voldoende informatie is om de gegevens te vinden die je wilt ophalen, krijgt elk bestand de aanduiding **Komt niet overeen**. Je kunt klikken op de **Bestanden die niet overeenkomen**, om meer informatie weer te geven over de reden waarom er geen overeenkomt was.


## <a name="add-another-explanation"></a>Nog een uitleg toevoegen

Het niet-overeenkomen is vaak een aanwijzing dat de uitleg die we hebben verstrekt niet voldoende gegevens heeft verstrekt om de waarde van de begindatum van de service te halen om te voldoen aan de gelabelde bestanden. Mogelijk moet je het bewerken of nog een uitleg toevoegen.

In ons voorbeeld ziet u dat de tekenreeks *Begindatum van de service van* altijd vóór de werkelijke waarde begint. Als je de begindatum van de service wilt identificeren moet je een uitleg bij de frase maken.

1. In de sectie uitleg selecteer je **Nieuw** en type een naam (bijvoorbeeld, *Voorvoegseltekenreeks*).
2. Voor het type selecteer je **Woordenlijst**.
3. De *Begindatum van de service van* als waarde gebruiken.
4. Kies **Opslaan**.

    ![Voorvoegseltekenreeks](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a>Het model nogmaals trainen

Door de uitleg op te slaan, wordt de training opnieuw gestart en deze keer worden met beide uitleggen in het voorbeeld gebruikt. Als je model voldoende gegevens heeft om de gegevens uit de voorbeeldbestanden met een label te halen, zie je elk bestand dat is gemarkeerd met **Overeenkomst**. 

Als je opnieuw een **Komt niet overeen** op je gelabelde bestanden ontvangt, moet je waarschijnlijk nog een uitleg maken om het model meer informatie te geven om het documenttype te identificeren, of je kunt wijzigingen aanbrengen in je bestaande bestanden.

## <a name="test-your-model"></a>Test je model.

Als je een overeenkomst hebt gekregen met de gelabelde voorbeeldbestanden, kun je nu je model testen op de andere niet-gelabelde voorbeeldbestanden. Dit is een handige stap voor het evalueren van de "geschiktheid" of het voorbereiding van het model voordat dit wordt gebruikt, door het te testen op bestanden die het model nog niet heeft gezien.

1. Op de startpagina van het model klik je op het tabblad **Testen**.  Hiermee wordt het model uitgevoerd op de niet-gelabelde voorbeeldbestanden.
2. In de lijst **Testbestanden** worden de voorbeeldbestanden weergegeven om aan te geven of de gegevens die je nodig hebt, door het model kunnen worden opgehaald. Gebruik deze informatie om de effectiviteit van je classificatie bij het identificeren van je documenten vast te stellen.

    ![Op je bestanden testen](../media/content-understanding/test-filies-extractor.png) 
