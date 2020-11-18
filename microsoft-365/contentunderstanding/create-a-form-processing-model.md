---
title: Een formulierverwerkingsmodel maken
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Maak een formulierverwerkingmodel in Microsoft SharePoint Syntex.
ms.openlocfilehash: aed918d899fe7c5e3c49b733d2411c178e9b98d0
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087689"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Maak een formulierverwerkingmodel in Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GnhN]  

</br>

Met [AI-Builder](https://docs.microsoft.com/ai-builder/overview) - een functie in Microsoft PowerApps - SharePoint-gebruikers kunnen een [formulierverwerkingsmodel](form-processing-overview.md) rechtstreeks vanuit een SharePoint-documentbibliotheek. 

Het maken van een formulierverwerkingsmodel omvat het volgende:
 - Stap 1: maak het formulierverwerkingsmodel om het inhoudstype te maken
 - Stap 2: voorbeeldbestanden toevoegen en analyseren
 - Stap 3: de formuliervelden selecteren
 - Stap 4: trainen testen van je model
 - Stap 5: uw model publiceren
 - Stap 6: uw model gebruiken

## <a name="requirements"></a>Vereisten

Je kunt alleen een model voor formulierverwerking maken in de SharePoint-documentbibliotheken waarvoor het model is ingeschakeld. Als formulierverwerking is ingeschakeld, zie je **AI Builder** **Een formulierverwerkingsmodel maken** onder het menu **Automate** in de documentbibliotheek. Als je verwerking wilt inschakelen voor jouw documentbibliotheek, moet je contact opnemen met je SharePoint-beheerder.

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Stap 1: Een formulierverwerkingsmodel maken

De eerste stap bij het maken van een formulierverwerkingsmodel is het een naam te geven, het nieuwe inhoudstype te definiëren en de bijbehorende nieuwe documentbibliotheekweergave te maken.

1. Selecteer in de documentbibliotheek het menu **Automatisch openen**, selecteer **AI-Builder** en selecteer vervolgens **Een formulierverwerkingsmodel maken**.

    ![Een model kiezen](../media/content-understanding/create-ai-builder-model.png)</br>

2. Typ in het deelvenster **Nieuw formulierverwerkingsmodel** in het veld **naam** een naam voor je model (bijvoorbeeld *aankoop orders*).

    ![Nieuw formulierverwerkingsmodel](../media/content-understanding/new-form-model.png)</br> 

3. Wanneer je een formulierverwerkingsmodel maakt, maak je een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype is een categorie documenten die gemeenschappelijke kenmerken hebben en die een verzameling kolommen of metagegevenseigenschappen delen voor de desbetreffende inhoud. SharePoint-inhoudstypen worden beheerd via de [galerie met inhoudstypen]().

    Selecteer **Geavanceerde instellingen** als je dit model wilt toewijzen aan een bestaand inhoudstype in de SharePoint-galerie met inhoudstypen om het bijbehorende schema te gebruiken. 

4. In de documentbibliotheek wordt een nieuwe weergave gemaakt voor de geëxtraheerde gegevens. Als je deze weergave niet als standaardweergave wilt gebruiken, schakel je **De weergave instellen als standaard** uit.

5. Selecteer **Maken**.

## <a name="step-2-add-and-analyze-documents"></a>Stap 2: Documenten toevoegen en analyseren

Nadat je een nieuw model voor formulierverwerking hebt gemaakt, wordt in de browser een pagina geopend voor het nieuwe PowerApps Al Builder-formulierverwerkingsmodel. Op deze pagina kun je voorbeelddocumenten toevoegen en analyseren. </br>

> [!NOTE]
> Als je voorbeeldbestanden zoekt om te gebruiken, raadpleeg je de [vereisten en optimalisatietips voor invoerdocumenten voor formulierverwerkingsmodellen](https://docs.microsoft.com/ai-builder/form-processing-model-requirements). 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. Selecteer **Documenten toevoegen** om voorbeelddocumenten toe te voegen die worden geanalyseerd om te bepalen welke benoemde waardeparen kunnen worden geëxtraheerd. Je kunt vervolgens **Uploaden van lokale opslag**, **SharePoint** of **Azure Blob-opslag** kiezen. Je moet ten minste vijf bestanden gebruiken voor de training.

2. Nadat je bestanden hebt toegevoegd, selecteer je **Analyseren** om te controleren op gemeenschappelijke in alle bestanden. Dit kan enkele minuten duren.</br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. Nadat de bestanden zijn geanalyseerd, selecteer je in **de formuliervelden die je wilt opslaan** pagina selecteer je het bestand om de gevonden velden weer te geven.</br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Stap 3: De formuliervelden selecteren

Nadat je de documenten voor velden hebt geanalyseerd, zie je nu de velden die zijn gevonden en identificeer je de velden die je wilt opslaan. Opgeslagen velden worden als kolommen weergegeven in de documentbibliotheekweergave van je model en bevatten de waarden die voor elk document zijn geëxtraheerd.

1. Op de volgende pagina wordt een van de voorbeeldbestanden weergegeven en zijn alle gemeenschappelijke velden gemarkeerd die automatisch zijn gedetecteerd met het systeem. </br>

    ![Pagina voor veldselectie](../media/content-understanding/select-fields-page.png)</br> 

2. Selecteer de velden die je wilt opslaan en schakel het selectievakje in om de selectie te bevestigen. In het Purchase Order-model selecteer je bijvoorbeeld de velden *Date*, *PO* en *Total*. Je kunt er ook voor kiezen om de naam van een veld te wijzigen. </br>

    ![PO # selecteren](../media/content-understanding/po.png)</br> 

3. Als een veld niet is gedetecteerd tijdens de analyse, kun je het nog steeds toevoegen. Markeer de gegevens die je wilt extraheren en typ in het naamvak de gewenste naam. Schakel het selectievakje vervolgens in. Je moet niet-gedetecteerde velden in de resterende voorbeeldbestanden bevestigen.

4. Klik op **Velden bevestigen** nadat je de velden hebt geselecteerd die je wilt opslaan. </br>
 
    ![Velden bevestigen na veldselectie](../media/content-understanding/confirm-fields.png)</br> 
 
5. Op de pagina **Selecteer de formuliervelden die u wilt opslaan** wordt het aantal velden weergegeven dat je hebt geselecteerd. Selecteer **Gereed**.

## <a name="step-4-train-and-test-your-model"></a>Stap 4: Het model trainen en testen

Nadat je de velden hebt geselecteerd die je wilt opslaan, kun je op de pagina **Modelsamenvatting** het model trainen en testen.

1. Op de pagina **Modelsamenvatting** worden de opgeslagen velden weergegeven in de sectie **Geselecteerde velden**. Selecteer **Trainen** om te beginnen met de training voor jouw voorbeeldbestanden. Het kan enkele minuten duren voordat dit is voltooid.</br>

     ![Velden selecteren voor training](../media/content-understanding/select-fields-train.png)</br> 

2. Wanneer je het bericht ziet dat de training is voltooid, selecteer je **Naar detailpagina gaan**. 

3. Op de pagina **Modeldetails** kun je testen hoe jouw model werkt door **Snelle test** te selecteren. Hiermee kun je bestanden slepen en neerzetten naar de pagina en nagaan of de velden worden gedetecteerd.

    ![Velden bevestigen](../media/content-understanding/select-fields-train.png)</br> 

2. Wanneer je het bericht ziet dat de training is voltooid, selecteer je **Naar detailpagina gaan**. 

3. Op de pagina **Modeldetails** kun je testen hoe jouw model werkt door **Snelle test** te selecteren. Hiermee kun je bestanden slepen en neerzetten naar de pagina en nagaan of de velden worden gevonden.

## <a name="step-5-publish-your-model"></a>Stap 5: Het model publiceren

1. Als je tevreden bent over de resultaten van je model, selecteer je **Publiceren** om het beschikbaar te maken voor gebruik.

2. Nadat het model is gepubliceerd, selecteer je **Model gebruiken**. Hiermee maak je een PowerAutomate-stroom die kan worden uitgevoerd in jouw SharePoint-documentbibliotheek, waarna de velden worden geëxtraheerd die in het model zijn geïdentificeerd. Selecteer vervolgens **Stroom maken**.
  
3. Wanneer je klaar bent, zie je het bericht **Uw stroom is gemaakt**.
 
## <a name="step-6-use-your-model"></a>Stap 6: uw model gebruiken

Na het publiceren van je model en het maken van de PowerAutomate-stroom, kun je je model gebruiken in je SharePoint-documentbibliotheek.

1. Na het publiceren van je model selecteer je **Ga naar SharePoint** om naar de documentbibliotheek te gaan.

2. Je ziet dat de velden die je hebt geselecteerd nu als kolommen worden weergegeven in de documentbibliotheek model.</br>

    ![Document bibliotheekmodel toegepast](../media/content-understanding/doc-lib-view.png)</br> 

3. Zoals je ziet, zie je in de koppelingsinformatie naast **Documenten** notities die op deze documentbibliotheek worden toegepast.

    ![Knop Info](../media/content-understanding/info-button.png)</br>  

4. Upload bestanden naar jouw documentbibliotheek. Alle bestanden die in het model worden geïdentificeerd voor het bijbehorende inhoudstype, worden weergegeven in de weergave en de geëxtraheerde gegevens worden weergegeven in de kolommen.</br>

    ![Gereed](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Zie ook
  
[Power Automate-documentatie](https://docs.microsoft.com/power-automate/)

[Training: zakelijke prestaties verbeteren met AI-Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
