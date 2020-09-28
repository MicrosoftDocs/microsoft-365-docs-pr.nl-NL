---
title: Een extractor maken
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Meer informatie over het maken van een extractor in Microsoft SharePoint Syntex.
ms.openlocfilehash: 740df6769b3a1675e4e1691f84d164312b15567c
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295454"
---
# <a name="create-an-extractor-preview"></a>Een extractor maken (preview)

De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project. [Lees meer over project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL2G]

</br> 

Voordat of nadat u een classificatiemodel hebt gemaakt om het identificeren en classificeren van specifieke documenttypen te automatiseren, kunt u ervoor kiezen om extra informatie toe te voegen aan uw model om bepaalde informatie uit deze documenten uit te pakken. U wilt bijvoorbeeld dat uw model niet alleen alle documenten voor het vernieuwen van een *contract* toevoegt aan uw documentbibliotheek, maar u kunt ook de *begindatum* van de service voor elk document weergeven als een kolom in de documentbibliotheek.

U moet een extractor maken voor elke entiteit in het document die u wilt extraheren. In het voorbeeld wilt u de *begindatum* van de service uitpakken voor elk document voor het *verlengen* van documenten dat door het model wordt geïdentificeerd. Dit moet gebeuren wanneer u een weergave wilt weergeven in de documentbibliotheek van alle documenten voor het verlengen van het *contract* met een kolom met de begindatum waarde van een service voor elk document.

> [!NOTE]
> Voordat u een Extractor maakt, moet u de [voorbeeldbestanden toevoegen](https://docs.microsoft.com/microsoft-365/contentunderstanding/create-a-classifier#add-your-example-files) om het model te leren bieden om de informatie die u wilt extraheren te identificeren. Gebruik de voorbeeldbestanden die u hebt gebruikt om uw classificatie te maken.

## <a name="name-your-extractor"></a>Naam van de extractor

1. Klik op de startpagina van het model in de tegel **extracten maken en trainen** op **Train Extractor**.
2. Typ in het scherm **nieuwe entiteits Extractor** de naam van het extractor in het veld **nieuwe naam** van de extractie. Als u bijvoorbeeld de naam van de service starten als u de begindatum van de service wilt extraheren uit het document **voor het verlengen** van het contract.
3. Klik op **Maken**.

## <a name="add-a-label"></a>Een label toevoegen

De volgende stap is het markeren van de gegevens die u wilt extraheren in de voorbeeldbestanden van uw voorkeuren.

Door de Extractor te maken opent u de extractor-pagina. Hier ziet u een overzicht van de voorbeeldbestanden, waarbij het eerste bestand in de lijst wordt weergegeven in de viewer.

1. Selecteer de gegevens die u wilt extraheren uit de bestanden in de viewer. Als u bijvoorbeeld de *begindatum*van de service wilt extraheren, markeert u de datumwaarde in het eerste bestand (*maandag, 14 oktober 2019*). en klikt u vervolgens op **Opslaan**.  De weergave van de waarde in het bestand wordt weergegeven in de lijst met gelabelde voorbeelden, onder de kolom **etiket** .
2. Selecteer **volgende bestand** om automatisch op te slaan en het volgende bestand in de lijst in de viewer te openen. Of selecteer **Opslaan** en selecteer vervolgens een ander bestand in de lijst met **gelabelde voorbeelden** .
3. Herhaal de stappen 1 en 2 in de viewer en herhaal dit tot u het etiket in de vijf bestanden hebt opgeslagen.

    ![Geavanceerde instellingen](../media/content-understanding/select-service-start-date.png) 

### <a name="add-a-negative-example"></a>Een negatief voorbeeld toevoegen

Net zoals bij het toevoegen van een negatief voorbeeldbestand bij het maken van een classificatie, moet u een negatieve steekproef toevoegen voor de extractor. Dit moet een bestand zijn dat geen datumwaarde ' service start ' bevat.

1. Selecteer in de lijst met **gelabelde voorbeelden** een negatief voorbeeld.
2. Selecteer in de viewer boven aan het artikel de optie **geen label aanwezig**.
3. Klik op **Opslaan**.
 
Wanneer u vijf bestanden hebt gelabeld, wordt een melding weergegeven met de mededeling dat u wilt overstappen op de training. U kunt kiezen voor meer documenten of verder naar training. 

## <a name="add-an-explanation"></a>Een uitleg toevoegen

Voorbeeld: u maakt een uitleg met een beschrijving van de entiteits indeling zelf en variaties in de voorbeelddocumenten. U kunt bijvoorbeeld een datumwaarde in verschillende notaties, bijvoorbeeld:
- 10/14/2019
- 14 oktober 2019
- Maandag 14 oktober 2019
 

Om de *begindatum* van de service te identificeren, maakt u een patroon toelichting.

1. Selecteer in de sectie uitleg de optie **Nieuw** en typ een naam (bijvoorbeeld *datum*).
2. Selecteer bij type de optie **patroon lijst**.
3. Voer bij waarde de datum variatie in zoals ze worden weergegeven in de voorbeeldbestanden. Als u bijvoorbeeld datumnotaties hebt die worden weergegeven als 0/00/0000, typt u variaties die in uw documenten worden weergegeven, zoals:
    - 0/0/0000
    - 0/00/0000
    - 00/0/0000
    - 00/00/0000
4. Kies **Opslaan**.

### <a name="use-the-explanation-library"></a>De uitleg bibliotheek gebruiken

Voor het maken van uitleg voor items, zoals datums, is het eenvoudiger om de uitleg bibliotheek te gebruiken dan voorhand matige invoer van alle variaties. De uitleg bibliotheek is een set vooraf gedefinieerde tekst en patroon toelichting. De bibliotheek biedt alle indelingen voor veelgebruikte woordgroepen of patroon lijsten, zoals datums, telefoonnummers, postcode, enzovoort. 

Voor het voorbeeld van de *service begint* , is het efficiënter om de vooraf samengestelde uitleg voor *datum* in de uitleg bibliotheek te gebruiken:

1. Selecteer in de **sectie uitleg**de optie **Nieuw**en selecteer vervolgens **uit uitleg bibliotheek**.
2. Selecteer **datum**in de uitleg bibliotheek. U kunt alle variaties van een ondersteunde datum weergeven.
3. Kies **Toevoegen**.</br>

    ![Uitleg bibliotheek](../media/content-understanding/explanation-library.png) 

4. Op de pagina **een uitleg maken** worden in de *datum* informatie uit de uitleg bibliotheek automatisch de velden ingevuld. Kies **Opslaan**.</br>

    ![Einddatum](../media/content-understanding/date-explanation-library.png) 

## <a name="train-the-model"></a>Het model trainen 

Uw uitleg opslaan start de training. Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de **naam van het**bestand.  

![Doet](../media/content-understanding/match2.png) 

Als de uitleg niet voldoende informatie bevat om de gegevens te vinden die u wilt extraheren, wordt elk bestand aangeduid met een **overeenkomende**naam. U kunt op de niet- **gerelateerde** bestanden klikken om meer informatie weer te geven over de reden waarom het niet klopt.


## <a name="add-another-explanation"></a>Nog een uitleg toevoegen

Vaak is de door u verstrekte uitleg niet voldoende informatie verstrekt om de begindatum waarde van de service uit te pakken, zodat deze overeenkomt met de gelabelde bestanden. Mogelijk moet u deze bewerken of een andere uitleg toevoegen.

In het voorbeeld ziet u dat de *begindatum van* de tekenreeks vóór de daadwerkelijke waarde voorafgaat. Om de begindatum van de service te identificeren, moet u een uitdrukking maken die wordt uitgelegd.

1. Selecteer in de sectie uitleg de optie **Nieuw**en typ een naam (bijvoorbeeld de prefix- *tekenreeks*).
2. Selecteer in het vak Type de optie **phrase**.
3. Gebruik de *begindatum van de service* als de waarde.
4. Kies **Opslaan**.

    ![Prefix-reeks](../media/content-understanding/prefix-string.png) 

## <a name="train-the-model-again"></a>Het model opnieuw trainen

Wanneer u de uitleg opslaat, wordt de training opnieuw gestart, op deze manier de uitleg van beide uitleg in het voorbeeld. Als uw model voldoende informatie bevat voor het extraheren van de gegevens uit de voorbeeldbestanden met labels, wordt elk bestand weergegeven met de naam van de **treffer**. 

Als u weer een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u waarschijnlijk een andere uitleg maken om het documenttype te identificeren of om wijzigingen aan te brengen in het voorbeeldmodel.

## <a name="test-your-model"></a>Uw model testen

Als u een overeenkomst ontvangt met de gelabelde voorbeeldbestanden, kunt u uw model nu testen in de resterende voorbeeldbestanden met de naam.

1. Klik op de startpagina van het model op het tabblad **testen** .  Hiermee voert u het model uit op uw niet-gelabelde voorbeeldbestanden.
2. In de lijst **bestanden testen** worden de voorbeeldbestanden weergegeven om aan te geven of de gegevens die u nodig hebt, kunnen worden uitgepakt in het model. Met deze informatie kunt u de effectiviteit van uw classificatie voor het identificeren van documenten bepalen.

    ![Uw bestanden testen](../media/content-understanding/test-filies-extractor.png) 
