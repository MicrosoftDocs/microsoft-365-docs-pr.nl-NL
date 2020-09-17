---
title: Een extractor maken (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: o365-administration
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het maken van een extractor
ms.openlocfilehash: 7219726fb385d0b67f7ee0614f5075ba226140ab
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950082"
---
# <a name="create-an-extractor-preview"></a>Een extractor maken (preview)
> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Voordat of nadat u een classificatiemodel hebt gemaakt om het identificeren en classificeren van specifieke documenttypen te automatiseren, kunt u ervoor kiezen om extra informatie toe te voegen aan uw model om bepaalde informatie uit deze documenten uit te pakken. U wilt bijvoorbeeld dat uw model niet alleen alle documenten voor het verlengen van een *contract* identificeert die aan de documentbibliotheek worden toegevoegd, maar ook de *begindatum* van de service voor elk document weergeven als kolom in de documentbibliotheek.

U moet een extractor maken voor elke entiteit in het document die u wilt extraheren. In ons voorbeeld willen we de *begindatum* van de service uitpakken voor elk document voor het *verlengen* van documenten dat door het model wordt geïdentificeerd. We willen een weergave in de documentbibliotheek van alle documenten voor het *verlengen* van documenten kunnen zien, met een kolom die de begindatum waarde van een service van elk document weergeeft.

> [!Note]
> Voordat u een Extractor maakt, moet u eerst de [voorbeeldbestanden toevoegen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) die u nodig hebt om het model te identificeren, zodat u de informatie die u wilt extraheren, kunt identificeren. Gebruik de voorbeeldbestanden die u hebt gebruikt om uw classificatie te maken.


## <a name="name-your-extractor"></a>Naam van de extractor

1. Klik op de startpagina van het model in de tegel **extracten maken en trainen** op **Train Extractor**.
2. Typ in het scherm **nieuwe entiteits Extractor** de naam van het extractor in het veld **nieuwe naam** van de extractie. We kunnen bijvoorbeeld de naam van de service **starten** wanneer we de begindatum van een service willen uitpakken uit elk document voor het verlengen van het contract.
3. Klik op **Maken**.

## <a name="add-a-label"></a>Een label toevoegen

De volgende stap is het markeren van de gegevens die u wilt extraheren in de voorbeeldbestanden van uw voorkeuren.

Als u de Extractor maakt, wordt de extractor-pagina geopend waarin u een lijst met voorbeeldbestanden ziet, waarbij het eerste bestand in de lijst wordt weergegeven in de viewer.

1. Selecteer de gegevens die u wilt extraheren uit de bestanden in de viewer. Als u bijvoorbeeld de *begindatum*van de service wilt extraheren, markeert u de datumwaarde voor de service in het eerste bestand (*maandag, 14 oktober 2019*). Klik vervolgens op **Opslaan**.  U ziet in de lijst met gelabelde voorbeelden onder de kolom **Label** de waarde weergave voor het bestand.
2. Selecteer **volgende bestand** om automatisch opslaan te selecteren en het volgende bestand te openen in de lijst in de Viewer of selecteer **Opslaan** en selecteer een ander bestand in de lijst met **gelabelde voorbeelden** .
3. Herhaal de stappen 1 en 2 in de viewer totdat u het label in vijf bestanden hebt opgeslagen.

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Een negatief voorbeeld toevoegen

Net als bij het toevoegen van een negatief voorbeeldbestand bij het maken van een classificatie, moet u een negatief voorbeeld toevoegen voor de extractor. Voor ons voorbeeld dient dit een bestand te zijn dat geen begindatum waarde voor een service bevat.

1. Selecteer in de lijst met **gelabelde voorbeelden** een negatief voorbeeld.
2. Selecteer in de viewer, bovenaan het artikel, de optie **geen label aanwezig**.
3. Klik op **Opslaan**.
 
Als u een label hebt met een label van vijf bestanden, wordt u in een banner weergegeven dat u kunt overstappen op de training. U kunt kiezen voor meer documenten of verder naar training. 

## <a name="add-an-explanation"></a>Een uitleg toevoegen

Voor ons voorbeeld maken we een uitleg met een beschrijving van de entiteits indeling zelf en variaties in de voorbeelddocumenten. U kunt bijvoorbeeld een datumwaarde in verschillende notaties, bijvoorbeeld:
- 10/14/2019
- 14 oktober 2019
- Maandag 14 oktober 2019
 

Om de *begindatum* van de service te identificeren, kunt u een patroon toelichting maken.

1. Selecteer in de sectie uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld *datum*).
2. Selecteer voor type de optie **patroon lijst**.
3. Voor de waarde moet u de datumvariant invullen zoals deze in de voorbeeldbestanden worden weergegeven. Als u bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, typt u eventuele variaties die in uw documenten kunnen worden weergegeven, zoals:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Selecteer **Opslaan**.


### <a name="use-the-explanation-library"></a>De uitleg bibliotheek gebruiken

Voor het maken van uitleg voor zaken als datums, is het veel eenvoudiger om de uitleg bibliotheek te gebruiken dan voorhand matige invoer van alle variaties. De uitleg bibliotheek is een set vooraf gedefinieerde tekst en patroon toelichting. De bibliotheek probeert alle indelingen te geven voor veelgebruikte woordgroepen of patroon lijsten, zoals datums, telefoonnummers, postcode en vele andere. 

Voor het voorbeeld van de *begindatum* van een service is het efficiënter om de vooraf samengestelde uitleg voor *datum* in de uitleg bibliotheek te gebruiken:

1. Selecteer in de **sectie uitleg**de optie **Nieuw**en selecteer vervolgens **uit uitleg bibliotheek**.
2. Selecteer **datum**in de uitleg bibliotheek. U kunt alle variaties van de datum weergeven die worden herkend.
3. Kies **Toevoegen**.</br>

    ![Uitleg bibliotheek](../media/content-understanding/explanation-library.png) 

4. Op de pagina **een uitleg maken** worden in de datuminformatie uit de uitleg bibliotheek de velden automatisch *bijgewerkt* . Selecteer **Opslaan**.</br>

    ![Uitleg bibliotheek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Het model trainen 

Als u uw uitleg opslaat, begint de training. Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de **naam van het**bestand.  

![Uitleg bibliotheek](../media/content-understanding/match2.png) 

Als de uitleg niet voldoende informatie bevat om de gegevens te vinden die u wilt extraheren, wordt elk bestand aangeduid met een **overeenkomende**naam. U kunt op de niet-gerelateerde bestanden klikken om meer informatie weer te geven over de reden waarom het niet klopt.


## <a name="add-another-explanation"></a>Nog een uitleg toevoegen

Vaak is de door u verstrekte uitleg niet voldoende informatie verstrekt om de begindatum waarde van de service uit te pakken, zodat deze overeenkomt met de gelabelde bestanden. Mogelijk moet u deze bewerken of een andere uitleg toevoegen.

Voor ons voorbeeld ziet u dat de tekst *van de begindatum van* de tekenreeks altijd voorafgaat aan de werkelijke waarde. Om de begindatum van de service te identificeren, kunnen we een uitleg van de zinnen maken.

1. Selecteer in de sectie uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld de prefix- *tekenreeks*).
2. Selecteer in het vak Type de optie **phrase**.
3. Gebruik de *begindatum van de service* als de waarde.
4. Selecteer **Opslaan**.

    ![Uitleg bibliotheek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Het model trainen

Als u uw uitleg opslaat, wordt deze keer opnieuw gestart met beide uitleg in ons voorbeeld. Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de **naam van het**bestand. 

Als u weer een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u mogelijk een andere uitleg maken om het documenttype te identificeren of om wijzigingen aan te brengen in de bestaande mappen.

## <a name="test-your-model"></a>Uw model testen

Als u een overeenkomst met de gelabelde voorbeeldbestanden hebt ontvangen, kunt u de naam van uw model testen in de resterende voorbeeldbestanden met bijschriften.

1. Klik op de startpagina van het model op het tabblad **testen** .  Het model wordt uitgevoerd in uw niet-gelabelde voorbeeldbestanden.
2. In de lijst **test bestanden** worden de voorbeeldbestanden weergegeven en wordt weergegeven of de gegevens die u nodig hebt, in het model kunnen worden opgehaald. U kunt deze gegevens gebruiken om de effectiviteit van uw classificatie voor het identificeren van uw documenten te bepalen.

    ![Uw bestanden testen](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Zie ook
  




