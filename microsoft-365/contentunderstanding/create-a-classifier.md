---
title: Een classificatie maken (preview)
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Leer hoe u een classificatie maakt
ms.openlocfilehash: 088770ace8914b583b184c78c3ce110d9d68b4c7
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612606"
---
# <a name="create-a-classifier-preview"></a>Een classificatie maken (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CL0R]  

</br>

Een classificatie is een type model waarmee identificatie en classificatie van een documenttype worden geautomatiseerd. U kunt bijvoorbeeld alle documenten voor het verlengen van een *contract* identificeren die zijn toegevoegd aan de documentbibliotheek, zoals hieronder beschreven.

![Document voor vernieuwing van contract](../media/content-understanding/contract-renewal.png)

Als u een classificatie maakt, wordt een nieuw [SharePoint-inhouds type](https://docs.microsoft.com/sharepoint/governance/content-type-and-workflow-planning#content-type-overview) gemaakt dat aan het model wordt gekoppeld.

Wanneer u de classificatie maakt, moet u *uitleg* maken waarmee u het model kunt definiëren door veelvoorkomende gegevens te laten opvallen die u op een consistente manier voor dit documenttype wilt vinden. 

U gebruikt voorbeelden van het documenttype (' voorbeelden van bestanden ') om het model ' Train ' om te helpen met het identificeren van bestanden met hetzelfde inhoudstype.

Als u een classificatie wilt maken, moet u het volgende doen:
1. De naam van uw model wijzigen
2. Voorbeeldbestanden toevoegen
3. Een label opgeven voor voorbeeldbestanden
4. Een uitleg maken
5. Uw model testen 

> [!Note]
> Hoewel een classificatie wordt gebruikt door uw model voor het identificeren en classificeren van documenttypen, kunt u er ook voor kiezen bepaalde gegevens uit te trekken van elk bestand dat door het model wordt geïdentificeerd. U doet dit door een **Extractor** te maken om aan uw model toe te voegen, en wordt beschreven in [een extractor maken](create-an-extractor.md).

## <a name="name-your-model"></a>De naam van uw model wijzigen

De eerste stap bestaat uit het maken van een model in uw inhouds centrum door het een naam te geven:

1. Klik in uw inhouds centrum op **Nieuw**en klik vervolgens op **een model maken**.
2. Typ in het vak Naam van **Nieuw document** in het veld **naam** de naam van het model. Voor ons voorbeeld, als we documenten verlengen, kunnen we de verlenging van dit model in de naam van het *contract*aangeven.
3. Klik op **Maken**. Vervolgens maakt u een startpagina voor het model.</br>

    ![Startpagina van het classificatiemodel](../media/content-understanding/model-home.png)

Wanneer u een model maakt, maakt u een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud. SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen](). Voor ons voorbeeld, wanneer we het model maken, maken we een nieuw inhoudstype voor het verlengen van een *contract* .

Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken. Houd er rekening mee dat u met een bestaand inhoudstype het schema van het schema kunt gebruiken voor het identificeren en classificeren van een bestaand inhoudstype dat u het model nog moet trainen om informatie op te halen uit de bestanden die wordt geïdentificeerd.</br>

![Geavanceerde instellingen](../media/content-understanding/advanced-settings.png)

## <a name="add-your-example-files"></a>Voorbeeldbestanden toevoegen

Op de startpagina van het model kunt u voorbeelden van bestanden toevoegen die u nodig hebt om het model te leren bieden ter identificatie van uw documenttype. </br>
</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4D0iX] 

</br>

> [!Note]
> U moet dezelfde bestanden gebruiken voor de training Classifier en [Extractor](create-an-extractor.md). U kunt altijd later meer toevoegen aan een extra optie, maar meestal moet u een volledige set voorbeeldbestanden toevoegen. U maakt een etiket voor uw model en test de resterende ongelabelde producten om de geschiktheid van het model te beoordelen. 

Voor de Trainingsset wilt u met beide positieve voorbeelden en de negatieve voorbeelden het volgende doen:
- Positief voorbeeld: documenten die het documenttype aangeven. De persoon bevat tekenreeksen en informatie over dit type document.
- Negatief voorbeeld: documenten die niet het documenttype vertegenwoordigen.  Er ontbreken tekenreeksen en informatie die in dit type document moeten worden weergegeven.

U wilt minimaal vijf positieve voorbeelden en één negatief voorbeeld gebruiken om het model te leren bieden.  U wilt nog meer vragen om uw model te testen na de training.

Voorbeeldbestanden toevoegen:

1. Klik op de startpagina van het model op de tegel **voorbeeld bibliotheek opbouwen** op **bestanden toevoegen**.
2. Selecteer op de pagina **voorbeeldbestanden voor uw model selecteren** de voorbeeldbestanden uit de voorbeeldbestanden bibliotheek in het inhouds centrum. Als u deze niet al had geüpload, kunt u ervoor kiezen om ze nu te uploaden door te klikken op **uploaden** om de bestanden te verplaatsen.
3. Selecteer **toevoegen**nadat u de voorbeeldbestanden hebt geselecteerd die u wilt gebruiken voor het trainen van het model.

    ![Voorbeeldbestanden selecteren](../media/content-understanding/select-sample.png) 

## <a name="label-your-example-files"></a>Een label opgeven voor voorbeeldbestanden

Wanneer u voorbeeldbestanden hebt toegevoegd, moet u deze als een positief voorbeeld of met een negatief voorbeeld markeren.

1. Klik op de startpagina van het model op de tegel **bestanden classificeren en training uitvoeren** op **classificatie voor trainer**.
   Hiermee wordt de etiket pagina weergegeven met een overzicht van de voorbeeldbestanden, waarbij het eerste bestand zichtbaar is in de viewer.
2. In de viewer, boven aan het eerste voorbeeldbestand, ziet u tekst met de vraag of het bestand een voorbeeld is van het model dat u zojuist hebt gemaakt. Als het om een positief voorbeeld gaat, selecteert u **Ja**. Als het om een negatief voorbeeld gaat, selecteert u **Nee**.
3. Selecteer in de lijst met **gelabelde voorbeelden** aan de linkerkant extra bestanden die u als voorbeeld wilt gebruiken, en voorzie ze ook van een etiket. 

    ![Startpagina van het classificatiemodel](../media/content-understanding/classifier-home-page.png) 


> [!Note]
> Etiketten van minimaal vijf positieve voorbeelden en een negatief voorbeeld. 

## <a name="create-an-explanation"></a>Een uitleg maken

De volgende stap is het maken van een uitleg op de pagina Train.  Een uitleg is een tip of aanwijzingen om het model te leren kennen hoe u dit document kunt herkennen. Onze documenten voor het verlengen van een contract bevatten bijvoorbeeld altijd een *aanvraag voor aanvullende informatie over de verschaffings* tekst.

> [!Note]
> Wanneer u deze gebruikt met uitpaknen, wordt een uitleg gebruikt om de tekenreeks te identificeren die u uit het document wilt extraheren. 

Een uitleg maken:

1. Ga naar de startpagina van het model en klik op het tabblad **trein** om naar de pagina Train te gaan.
2. Op de pagina Train in de sectie met **begeleide bestanden** ziet u een lijst met de voorbeeldbestanden die u eerder hebt gelabeld. Selecteer een van uw positieve bestanden in de lijst en wordt weergegeven in de viewer.
3. Klik in de sectie uitleg op **Nieuw**en klik vervolgens op **leeg**.
4. Op de pagina **een uitleg maken** :</br>
    a. Typ de **naam** (bijvoorbeeld ' uitschaffings blok ').</br>
    b. Selecteer het **type**. Voor ons voorbeeld selecteren we een **lijst met zinnen**, aangezien we een tekenreeks toevoegen.</br>
    c. Typ in het vak **Typ hier** de tekenreeks.  Voor ons voorbeeld voegen we "aanvraag voor aanvullende informatie" toe. U kunt onderscheid maken tussen **hoofd** letters en kleine letters in de tekenreeks.</br>
    d. Klik op **Opslaan**.

    ![Uitleg maken](../media/content-understanding/explanation.png) 
    
 
5.  In het model wordt nu gecontroleerd of de door u gemaakte uitleg goed genoeg is om uw resterende gelabelde voorbeeldbestanden correct te identificeren als positieve en negatieve voorbeelden. Selecteer in de sectie met begeleide bestanden de kolom **evaluatie** nadat de training is voltooid om de resultaten te bekijken.  De bestanden geven de **overeenkomende** waarde weer als de door u gemaakte uitleg voldoende is voor de naam van het bestand dat u als (positief of negatief) hebt opgegeven.

    ![Uitleg maken](../media/content-understanding/match.png) 

Als u een **niet-overeenkomend** bestand met gelabelde bestanden ontvangt, moet u mogelijk een extra uitleg maken om het model meer informatie te verschaffen ter identificatie van het documenttype. U kunt op het bestand klikken voor meer informatie over waarom de niet-overeenkomende fout is opgetreden.

## <a name="test-your-model"></a>Uw model testen

Als u een overeenkomst met de gelabelde voorbeeldbestanden hebt ontvangen, kunt u de naam van uw model testen in de resterende voorbeeldbestanden met bijschriften.

1. Klik op de startpagina van het model op het tabblad **testen** .  Het model wordt uitgevoerd in uw niet-gelabelde voorbeeldbestanden.
2. In de lijst **bestanden testen** worden de voorbeeldbestanden weergegeven en wordt weergegeven als een voorbeeld van het model wordt voorspeld voor een positief of negatief voorbeeld. U kunt deze gegevens gebruiken om de effectiviteit van uw classificatie voor het identificeren van uw documenten te bepalen.

    ![Test van bestanden zonder label](../media/content-understanding/test-on-files.png) 



## <a name="see-also"></a>Zie ook
[Een extractor maken](create-an-extractor.md)</br>
[Overzicht van document](document-understanding-overview.md)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)</br>
[Een model toepassen](apply-a-model.md) 




