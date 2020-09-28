---
title: Een classificatie maken
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
description: Leer hoe u een classificatie maakt
ms.openlocfilehash: 29b2a4775bec12649c66b4cb4a07fe5f0fc93ae2
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294900"
---
# <a name="create-a-classifier-in-microsoft-sharepoint-syntex"></a>Een classificatie maken in Microsoft SharePoint Syntex

De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project. [Lees meer over project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Een classificatie is een type model dat u kunt gebruiken om de identificatie en classificatie van een documenttype te automatiseren. U kunt bijvoorbeeld alle documenten voor het verlengen van een *contract* voor de documentbibliotheek identificeren, zoals wordt weergegeven in de volgende afbeelding.

![Document voor vernieuwing van contract](../media/content-understanding/contract-renewal.png)

Als u een classificatie maakt, kunt u een nieuw [SharePoint-inhouds type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) maken dat is gekoppeld aan het model.

Wanneer u de classificatie maakt, moet u *uitleg* maken om het model te definiëren. Op deze manier kunt u algemene gegevens noteren waarvan u denkt dat deze het documenttype voortdurend moet vinden. 

Gebruik voorbeelden van het documenttype (' voorbeelden van bestanden ') om uw model te identificeren om bestanden met hetzelfde inhoudstype te identificeren.

Als u een classificatie wilt maken, moet u het volgende doen:
1. Geef een naam op voor uw model.
2. Voeg uw voorbeeldbestanden toe.
3. Voorzie uw voorbeeldbestanden van een label.
4. Maak een uitleg.
5. Test uw model.

> [!NOTE]
> Hoewel uw model gebruikmaakt van een classificatie voor het identificeren en classificeren van documenttypen, kunt u ook kiezen voor het verzamelen van specifieke gegevens uit een bestand dat door het model wordt geïdentificeerd. Dit doet u door een **Extractor** te maken om aan uw model toe te voegen. Zie [een extractor maken](create-an-extractor.md).

## <a name="name-your-model"></a>De naam van uw model wijzigen

Voor het maken van uw model moet u de eerste stap een naam geven:

1. Selecteer in het inhouds centrum de optie **Nieuw**en **Maak vervolgens een model**.
2. Typ in het vak Naam van **Nieuw document** de naam van het model in het veld **naam** . Als u bijvoorbeeld documenten voor het verlengen van de contracten wilt identificeren, kunt u de naam van het model voor het *vernieuwen*van het model opgeven.
3. Kies **Create**. Hiermee maakt u een startpagina voor het model.</br>

    ![Startpagina van het classificatiemodel](../media/content-understanding/model-home.png)

Wanneer u een model maakt, maakt u ook een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud. SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen](https://support.microsoft.com/office/create-or-customize-a-site-content-type-27eb6551-9867-4201-a819-620c5658a60f). Als u het model maakt voor dit voorbeeld, maakt u een nieuw inhoudstype voor het verlengen van een *contract* .

Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken. Houd er rekening mee dat u met een bestaand inhoudstype het schema kunt gebruiken voor het identificeren en classificeren van een bestaand inhoudstype zodat u de gegevens kunt ophalen uit de bestanden die worden geïdentificeerd.</br>

![Geavanceerde instellingen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Voorbeeldbestanden toevoegen

Voeg op de startpagina van het model uw voorbeelden van bestanden toe die u nodig hebt om het model te leren bieden ter identificatie van uw documenttype. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!NOTE]
> U dient dezelfde bestanden te gebruiken voor de training Classifier en [Extractor](create-an-extractor.md). U hebt altijd de mogelijkheid om later meer toe te voegen, maar u voegt meestal een volledige set voorbeeldbestanden toe. Voorzie wat van een deel van uw model en test de resterende ongelabelde producten om de geschiktheid van het model te beoordelen. 

Voor de set training wilt u zowel positieve als negatieve voorbeelden gebruiken:
- Positief voorbeeld: documenten die het documenttype aangeven. Dit bevat tekenreeksen en informatie over dit type document.
- Negatief voorbeeld: documenten die niet het documenttype vertegenwoordigen. Dit ontbreken tekenreeksen en gegevens die in dit type document moeten worden weergegeven.

Zorg ervoor dat u ten minste vijf positieve voorbeelden en minstens één negatief voorbeeld gebruikt om het model te leren bieden.  U wilt nog meer items maken om uw model na het trainingsproces te testen.

Voorbeeldbestanden toevoegen:

1. Klik op de startpagina van het model in de tegel **voorbeeld bibliotheek opbouwen** op **bestanden toevoegen**.
2. Selecteer op de pagina **voorbeeldbestanden voor uw model selecteren** de voorbeeldbestanden uit de voorbeeldbestanden bibliotheek in het inhouds centrum. Als u deze niet al had geüpload, kunt u deze nu uploaden door te klikken op **uploaden** om de bestanden te verplaatsen.
3. Selecteer **toevoegen**nadat u de voorbeeldbestanden hebt geselecteerd die u wilt gebruiken voor het trainen van het model.

    ![Voorbeeldbestanden selecteren](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Een label opgeven voor voorbeeldbestanden

Wanneer u voorbeeldbestanden hebt toegevoegd, moet u deze als een positief of negatief voorbeeld markeren.

1. Klik op de startpagina van het model op de tegel **bestanden classificeren en training uitvoeren** op **classificatie voor trainer**.
   Hiermee wordt de etiket pagina weergegeven met een overzicht van de voorbeeldbestanden, waarbij het eerste bestand zichtbaar is in de viewer.
2. In de viewer boven aan het eerste voorbeeldbestand ziet u tekst met de vraag of het bestand een voorbeeld is van het model dat u zojuist hebt gemaakt. Als het om een positief voorbeeld gaat, selecteert u **Ja**. Als het om een negatief voorbeeld gaat, selecteert u **Nee**.
3. Selecteer in de lijst met **gelabelde voorbeelden** aan de linkerkant extra bestanden die u als voorbeeld wilt gebruiken, en voorzie ze van een label. 

    ![Startpagina classificatie](../media/content-understanding/classifier-home-page.png) 


> [!NOTE]
> Etiketten van minimaal vijf positieve voorbeelden en een negatief voorbeeld. 

## <a name="create-an-explanation"></a>Een uitleg maken

De volgende stap is een uitleg over het maken van een uitleg op de pagina van de trein. Met een uitleg wordt het model vertrouwd met het herkennen van het document. De documenten voor het verlengen van het contract bevatten bijvoorbeeld altijd een *aanvraag voor aanvullende informatie over de verschaffings* tekst.

> [!Note]
> Wanneer u deze gebruikt met uitpaknen, wordt met een uitleg de tekenreeks aangegeven die u uit het document wilt extraheren. 

Een uitleg maken:

1. Op de startpagina van het model, selecteert u het tabblad **trein** om naar de pagina training te gaan.
2. Op de pagina Train, in de sectie met uitbesteieve **bestanden** , ziet u een lijst met de voorbeeldbestanden die u eerder hebt gelabeld. Selecteer een van de positieve bestanden in de lijst en wordt weergegeven in de viewer.
3. Selecteer in de sectie uitleg de optie **Nieuw** en selecteer **leeg**.
4. Op de pagina **een uitleg maken** :</br>
    a. Typ de **naam** (bijvoorbeeld ' uitschaffings blok ').</br>
    b. Selecteer het **type**. Voorbeeld: Selecteer **phrase List**, aangezien u een tekenreeks toevoegt.</br>
    c. Typ in het vak **Typ hier** de tekenreeks. Voorbeeld van het toevoegen van een aanvraag voor aanvullende informatie. U kunt onderscheid maken tussen **hoofd** letters en kleine letters in de tekenreeks.</br>
    d. Klik op **Opslaan**.

    ![Uitleg maken](../media/content-understanding/explanation.png) 
    
 
5. Het model controleert nu of de uitleg die u hebt gemaakt goed genoeg was om de resterende gelabelde voorbeeldbestanden correct te identificeren, met een positief en negatief voorbeeld. Selecteer in de sectie opgeleid files de kolom **evaluatie** nadat de training is voltooid om de resultaten te bekijken. De bestanden bevatten de **gezochte**waarde, als de door u gemaakte uitleg voldoende is voor de naam van het bestand dat u als positief of negatief hebt aangemerkt.

    ![Waarde vergelijken](../media/content-understanding/match.png) 

Als u een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u mogelijk een extra uitleg maken om het model meer informatie te verschaffen ter identificatie van het documenttype. Als dit het geval is, klikt u op het bestand om meer informatie weer te geven over de reden waarom de fout is opgetreden.

## <a name="test-your-model"></a>Uw model testen

Als u een overeenkomst met de gelabelde voorbeeldbestanden hebt ontvangen, kunt u de naam van uw model testen in de resterende voorbeeldbestanden met bijschriften.

1. Selecteer op de startpagina van het model het tabblad **testen** .  Hiermee voert u het model uit op uw niet-gelabelde voorbeeldbestanden.
2. In de lijst **bestanden testen** worden de voorbeeldbestanden weergegeven en wordt weergegeven of het model met de voor spelling positief of negatief is. Met deze informatie kunt u de effectiviteit van uw classificatie voor het identificeren van documenten bepalen.

    ![Test van bestanden zonder label](../media/content-understanding/test-on-files.png) 

## <a name="see-also"></a>Zie ook
[Een extractor maken](create-an-extractor.md)</br>
[Overzicht van document](document-understanding-overview.md)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)</br>
[Een model toepassen](apply-a-model.md) 
