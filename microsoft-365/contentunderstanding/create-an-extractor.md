---
title: Een afzuigkap maken (Voorbeeld)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het maken van een afzuigkap
ms.openlocfilehash: 76cb17df069c6905080baabb0b57d765fe5cc94c
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540104"
---
# <a name="create-an-extractor-preview"></a>Een afzuigkap maken (Voorbeeld)
> [!Note] 
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Voor of nadat u een classificatiemodel hebt gemaakt om de identificatie en classificatie van specifieke documenttypen te automatiseren, u er optioneel voor kiezen om afzuigers toe te voegen aan uw model om specifieke informatie uit deze documenten te verwijderen. U wilt bijvoorbeeld dat uw model niet alleen alle *contractverlengingsdocumenten* identificeert die aan uw documentbibliotheek zijn toegevoegd, maar ook de *begindatum van* de service voor elk document weergeven als kolom in de documentbibliotheek.

U moet een afzuigkap maken voor elke entiteit in het document dat u wilt extraheren. In ons voorbeeld willen we de *begindatum* van de service extraheren voor elk document *voor contractverlenging* dat wordt geïdentificeerd door het model. We willen een weergave kunnen zien in de documentbibliotheek van alle documenten *voor contractverlenging,* met een kolom met de datum waarde van de begindatum van de service van elk document.

> [!Note]
> Voordat u een afzuigkap maakt, moet u [uw voorbeeldbestanden toevoegen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier?view=o365-worldwide#add-your-example-files) die u nodig hebt om het model te trainen om de informatie te identificeren die u wilt extraheren. Gebruik dezelfde voorbeeldbestanden die u hebt gebruikt om uw classificatie te maken.


## <a name="name-your-extractor"></a>Geef uw afzuiger een naam

1. Klik op de startpagina van het model in de tegel **Extrahers maken en trainen** op **Treinextracor**.
2. Typ in het scherm **Nieuwe entiteitsafzuig** de naam van uw afzuigkap in het veld **Nieuwe afzuignaam.** We kunnen het bijvoorbeeld **de begindatum van de service** benoemen als we de begindatum van de service uit elk document voor contractverlenging willen halen.
3. Klik op **Maken**.

## <a name="add-a-label"></a>Een label toevoegen

De volgende stap is het labelen van de informatie die u wilt extraheren in uw voorbeeldtrainingsbestanden.

Als u de uitzuigkap maakt, opent u de uitzuigpagina waarin u een lijst met uw voorbeeldbestanden ziet, waarbij het eerste bestand in de lijst in de viewer wordt weergegeven.

1. Selecteer in de viewer de gegevens die u uit de bestanden wilt halen. Als u bijvoorbeeld de *servicedatum start*wilt extraheren, markeert u de datumwaarde hiervoor in het eerste bestand *(maandag 14 oktober 2019).* Klik vervolgens op **Opslaan**.  U ziet de waardeweergave voor het bestand in de lijst Met gelabelde voorbeelden onder de kolom **Label.**
2. Selecteer **Volgende bestand** om automatisch te worden weergegeven en open het volgende bestand in de lijst in de viewer of u **Opslaan** selecteren en een ander bestand selecteren in de lijst **Met gelabelde voorbeelden.**
3. Herhaal in de viewer stap 1 en 2 en doe dit totdat u het label in vijf bestanden hebt opgeslagen.

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 


### <a name="add-a-negative-example"></a>Een negatief voorbeeld toevoegen

Net als bij het toevoegen van een negatief voorbeeldbestand bij het maken van een classificatie, moet u een negatief voorbeeld voor de afzuigkap toevoegen. Voor ons voorbeeld moet het een bestand zijn dat geen begindatumwaarde van de service bevat.

1. Selecteer in de lijst **Met gelabelde voorbeelden** een negatief voorbeeld.
2. Selecteer in de viewer boven aan het artikel **Geen label aanwezig**.
3. Klik op **Opslaan**.
 
Zodra u vijf bestanden hebt gelabeld, wordt er een meldingsbanner weergegeven waarin u wordt geïnformeerd om over te gaan tot training. U ervoor kiezen om meer documenten of vooraf aan de opleiding. 

## <a name="add-an-explanation"></a>Een uitleg toevoegen

We gaan bijvoorbeeld een uitleg maken die een hint geeft over de entiteitsindeling zelf en variaties die deze in de voorbeelddocumenten kan hebben. Een datumwaarde kan bijvoorbeeld in een aantal verschillende indelingen zijn, zoals:
- 10/14/2019
- 14 oktober 2019
- Maandag 14 oktober 2019
 

Om de *startdatum van* de service te identificeren, u een patroonuitleg maken.

1. Selecteer in de sectie Uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld *Datum).*
2. Selecteer voor tekst **de lijst Patroon**.
3. Voor de waarde moet u de datumvariatie ops geven zoals deze in de voorbeeldbestanden worden weergegeven. Als u bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, voert u eventuele wijzigingen in die in uw documenten kunnen worden weergegeven, zoals:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Klik op **Opslaan**.


### <a name="use-the-explanation-library"></a>De bibliotheek Uitleg gebruiken

Voor het maken van uitleg voor zaken als datums is het veel gemakkelijker om de uitlegbibliotheek te gebruiken dan om alle varianten handmatig in te voeren. De uitlegbibliotheek is een set vooraf gebouwde woord- en patroonuitleg. De bibliotheek probeert alle indelingen voor algemene woordgroepen of patroonlijsten te bieden, zoals datums, telefoonnummers, postcode en vele andere. 

Voor ons voorbeeld *van de startdatum van* de service is het efficiënter om de vooraf gebouwde uitleg voor *Datum* in de uitlegbibliotheek te gebruiken:

1. Selecteer **In**de sectie Uitleg ,** selecteer **Nieuw**en selecteer **Vervolgens Uit uitlegbibliotheek**.
2. Selecteer **Datum**in de uitlegbibliotheek. U alle datumvariaties bekijken die worden herkend.
3. Kies **Toevoegen**.</br>

    ![Uitlegbibliotheek](../media/content-understanding/explanation-library.png) 

4. Op de pagina **Een uitleg maken** worden de velden automatisch ingevuld met de *datumgegevens* uit de uitlegbibliotheek. Klik op **Opslaan**.</br>

    ![Uitlegbibliotheek](../media/content-understanding/date-explanation-library.png) 

 
## <a name="train-the-model"></a>Train het model 

Het opslaan van uw uitleg zal beginnen met de training. Als uw model voldoende informatie heeft om de gegevens uit uw gelabelde voorbeeldbestanden te extraheren, ziet u elk bestand met het label **Match**.  

![Uitlegbibliotheek](../media/content-understanding/match2.png) 

Als de uitleg niet genoeg informatie heeft om de gegevens te vinden die u wilt extraheren, wordt elk bestand gelabeld met **Mismatch**. U op de verkeerde bestanden klikken om meer informatie te zien over waarom er een mismatch was.


## <a name="add-another-explanation"></a>Een andere uitleg toevoegen

Vaak is de mismatch een indicatie dat de uitleg die we hebben gegeven niet genoeg informatie heeft verstrekt om de begindatum van de service te extraheren die overeenkomt met onze gelabelde bestanden. Mogelijk moet u het bewerken of een andere uitleg toevoegen.

We merken bijvoorbeeld dat de *begindatum van* de tekenreeks Service altijd voorafgaat aan de werkelijke waarde. Om de startdatum van de service te identificeren, kunnen we een woordgroepsverklaring maken.

1. Selecteer in de sectie Uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld *voorvoegselreeks).*
2. Selecteer Voor tekst **de lijst Zinsgroepen**.
3. Gebruik *de begindatum van* de service als waarde.
4. Klik op **Opslaan**.

    ![Uitlegbibliotheek](../media/content-understanding/prefix-string.png) 


## <a name="train-the-model"></a>Train het model

Het opslaan van uw uitleg zal de training opnieuw beginnen, dit keer met behulp van beide uitleg in ons voorbeeld. Als uw model voldoende informatie heeft om de gegevens uit uw gelabelde voorbeeldbestanden te extraheren, ziet u elk bestand met het label **Match**. 

Als u opnieuw een **Mismatch** ontvangt op uw gelabelde bestanden, moet u mogelijk een andere uitleg maken om het model meer informatie te geven om het documenttype te identificeren of om wijzigingen aan te brengen in uw bestaande bestanden.

## <a name="test-your-model"></a>Test uw model

Als u een overeenkomst hebt ontvangen in uw gelabelde voorbeeldbestanden, u uw model nu testen op uw resterende niet-gelabelde voorbeeldbestanden.

1. Klik op de startpagina van het model op het tabblad **Testen.**  Hiermee wordt het model uitgevoerd op uw niet-gelabelde voorbeeldbestanden.
2. In de lijst **Bestanden testen** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model de informatie kan extraheren die u nodig hebt. U deze informatie gebruiken om de effectiviteit van uw classificatie te bepalen bij het identificeren van uw documenten.

    ![Testen op uw bestanden](../media/content-understanding/test-filies-extractor.png) 

## <a name="see-also"></a>Zie ook
  




