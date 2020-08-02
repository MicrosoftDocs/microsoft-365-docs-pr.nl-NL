---
title: Een classificatie maken (Voorbeeld)
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
description: Meer informatie over het maken van een classificatie
ms.openlocfilehash: 029ac16310f8e95a69a713896b1109a778eb3b8d
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537222"
---
# <a name="create-a-classifier-preview"></a>Een classificatie maken (Voorbeeld)

> [!Note] 
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Een classificatie is een type model dat de identificatie en classificatie van een documenttype automatiseert. U bijvoorbeeld alle *contractverlengingsdocumenten* identificeren die aan uw documentbibliotheek zijn toegevoegd, zoals het volgende.

![Document contractverlenging](../media/content-understanding/contract-renewal.png)

Als u een classificatie maakt, wordt een nieuw [SharePoint-inhoudstype](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) gemaakt dat aan het model is gekoppeld.

Wanneer u de classificatie maakt, moet u *uitleg* maken die helpt bij het definiëren van het model door algemene gegevens op te merken die u consistent zou verwachten voor dit documenttype. 

U gebruikt voorbeelden van het documenttype ('voorbeeldbestanden') om uw model te helpen 'trainen' om bestanden te identificeren die hetzelfde inhoudstype hebben.

Als u een classificatie wilt maken, moet u het:
1. Geef uw model een naam
2. Uw voorbeeldbestanden toevoegen
3. Uw voorbeeldbestanden labelen
4. Een uitleg maken
5. Test uw model 

> [!Note]
> Hoewel een classificatie door uw model wordt gebruikt om documenttypen te identificeren en te classificeren, u er ook voor kiezen om specifieke stukjes informatie uit elk bestand te halen dat door het model wordt geïdentificeerd. U doet dit door een **afzuigkap** te maken om aan uw model toe te voegen, en dit wordt beschreven in [Een afzuigkap maken.](create-an-extractor.md)

## <a name="name-your-model"></a>Geef uw model een naam

De eerste stap is om uw model te maken in uw Content Center door het een naam te geven:

1. Klik in het Inhoudscentrum op **Nieuw**en klik vervolgens op **Een model maken**.
2. Typ in het **modelvenster Nieuw documentbegrip** in het veld **Naam** de naam van het model. Als we bijvoorbeeld contractverlengingsdocumenten willen identificeren, kunnen we dit model *contractverlenging een naam geven.*
3. Klik op **Maken**. Hiermee wordt een startpagina voor het model gemaakt.</br>

    ![Startpagina classificatiemodel](../media/content-understanding/model-home.png)

Wanneer u een model maakt, maakt u een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met algemene kenmerken en deelt een verzameling kolommen of metagegevens eigenschappen voor die bepaalde inhoud. SharePoint-inhoudstypen worden beheerd via de [galerie Inhoudstypen](). Wanneer we bijvoorbeeld het model maken, maken we een nieuw *inhoudstype voor contractverlenging.*

Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie Met SharePoint-inhoudstypen om het schema te gebruiken. Houd er rekening mee dat u weliswaar een bestaand inhoudstype gebruiken om het schema te gebruiken om te helpen bij de identificatie en classificatie, maar dat u uw model nog steeds moet trainen om informatie uit bestanden te extraheren die het identificeert.</br>

![Geavanceerde instellingen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Uw voorbeeldbestanden toevoegen

Op de startpagina van het model u uw voorbeeldbestanden toevoegen die u nodig hebt om het model te trainen om uw documenttype te identificeren. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> Dezelfde bestanden moeten worden gebruikt voor zowel classificatie als [afzuigopleiding](create-an-extractor.md). U hebt altijd de optie om later meer toe te voegen, maar meestal moet u een volledige set voorbeeldbestanden toevoegen. U labelt wat om uw model te trainen en test de resterende niet-gelabelde modellen om de geschiktheid van het model te evalueren. 

Voor uw trainingsset wilt u zowel positieve als negatieve voorbeelden gebruiken:
- Positief voorbeeld: documenten die het documenttype vertegenwoordigen. Ze bevatten tekenreeksen en informatie die altijd in dit type document zou zitten.
- Negatief voorbeeld: documenten die het documenttype niet vertegenwoordigen.  Ze missen tekenreeksen en informatie die aanwezig moet zijn in dit type document.

U zult minstens vijf positieve voorbeelden en één negatieve voorbeelden willen gebruiken om uw model te trainen.  U zult extra degenen willen hebben om uw model na opleiding te testen.

Ga als voorbeeldbestanden toevoegen:

1. Klik op de startpagina van het model in de tegel **Voorbeeldbibliotheek bouwen** op **Bestanden toevoegen**.
2. Selecteer op de **voorbeeldbestanden selecteren voor uw modelpagina** uw voorbeeldbestanden uit de bibliotheek Voorbeeldbestanden in het Inhoudscentrum. Als je ze daar nog niet hebt geüpload, kun je ervoor kiezen om ze nu te uploaden door op **Uploaden** te klikken om ze de voorbeeldbestandsbibliotheek te verplaatsen.
3. Nadat u uw voorbeeldbestanden hebt geselecteerd die u wilt gebruiken om het model te trainen, klikt u op **Toevoegen**.

    ![Voorbeeldbestanden selecteren](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Uw voorbeeldbestanden labelen

Nadat u uw voorbeeldbestanden hebt toegevoegd, moet u ze vervolgens labelen als positieve voorbeelden of negatieve voorbeelden.

1. Klik op de startpagina van het model op de **tegel Bestanden classificeren en trainingsafbeelding uitvoeren** op **Classifier trainen**.
   Hiermee wordt de labelpagina weergegeven met een lijst van uw voorbeeldbestanden, waarbij het eerste bestand zichtbaar is in de viewer.
2. In de viewer ziet u boven aan het eerste voorbeeldbestand tekst met de vraag of het bestand een voorbeeld is van het model dat u zojuist hebt gemaakt. Als het een positief voorbeeld is, selecteert u **Ja**. Als het een negatief voorbeeld is, selecteert u **Nee**.
3. Selecteer in de lijst **Met gelabelde voorbeelden** aan de linkerkant extra bestanden die u als voorbeeld wilt gebruiken en label ze ook. 

    ![Startpagina classificatiemodel](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> Label ten minste vijf positieve voorbeelden, en een negatief voorbeeld. 

## <a name="create-an-explanation"></a>Een uitleg maken

De volgende stap is het maken van een uitleg op de pagina Trein.  Een verklaring is een hint of aanwijzing om het model te helpen begrijpen hoe dit document te herkennen. Onze documenten voor contractverlenging bevatten bijvoorbeeld altijd een *aanvraag voor aanvullende openbaarmakingstekstreeks.*

> [!Note]
> Wanneer u met uittreksers wordt gebruikt, wordt een uitleg gebruikt om de tekenreeks te identificeren die u uit het document wilt extraheren. 

Een verklaring maken:

1. Klik op de startpagina van het model op het tabblad **Trein** om naar de pagina Trein te gaan.
2. Op de pagina Trein ziet u in de sectie **Getrainde bestanden** een lijst met de voorbeeldbestanden die u eerder had gelabeld. Selecteer een van uw positieve bestanden in de lijst en deze wordt weergegeven in de viewer.
3. Klik in de sectie Uitleg op **Nieuw**en klik vervolgens op **Leeg**.
4. Op de pagina **Een uitleg** maken:</br>
    a. Typ de **naam** (bijvoorbeeld 'Openbaarmakingsblok').</br>
    b. Selecteer het **type**. In ons voorbeeld selecteren we **de lijst Met zinnen,** omdat we een tekenreeks toevoegen.</br>
    c. Typ de tekenreeks in het vak **Tekst hier.**  In ons voorbeeld voegen we 'Verzoek om aanvullende openbaarmaking' toe. U **gevalgevoelig** selecteren als de tekenreeks gevalgevoelig moet zijn.</br>
    d. Klik op **Opslaan**.

    ![Uitleg maken](../media/content-understanding/explanation.png) 
    
 
5.  Het model controleert nu of de uitleg die u hebt gemaakt goed genoeg was om uw resterende gelabelde voorbeeldbestanden correct te identificeren als positieve en negatieve voorbeelden. Controleer in de sectie Getrainde bestanden de kolom **Evaluatie** nadat de training is voltooid om de resultaten te bekijken.  De bestanden tonen een waarde van **Match** als de uitleg die u hebt gemaakt voldoende was om overeen te komen met wat u ze als (positief of negatief) had bestempeld.

    ![Uitleg maken](../media/content-understanding/match.png) 

Als u een **mismatch** ontvangt op uw gelabelde bestanden, moet u mogelijk een aanvullende uitleg maken om het model meer informatie te geven om het documenttype te identificeren. U op het bestand klikken om meer informatie te krijgen over waarom de mismatch heeft plaatsgevonden.

## <a name="test-your-model"></a>Test uw model

Als u een overeenkomst hebt ontvangen in uw gelabelde voorbeeldbestanden, u uw model nu testen op uw resterende niet-gelabelde voorbeeldbestanden.

1. Klik op de startpagina van het model op het tabblad **Testen.**  Hiermee wordt het model uitgevoerd op uw niet-gelabelde voorbeeldbestanden.
2. In de lijst **Bestanden testen** worden uw voorbeeldbestanden weergegeven en wordt weergegeven of het model voorspelde dat ze positieve of negatieve voorbeelden zijn. U deze informatie gebruiken om de effectiviteit van uw classificatie te bepalen bij het identificeren van uw documenten.

    ![Testen van niet-gelabelde bestanden](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>Zie ook
[Een afzuiger maken](create-an-extractor.md)</br>
[Overzicht van documentbegrip](document-understanding-overview.md)</br>
[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)</br>
[Een model toepassen](apply-a-model.md) 




