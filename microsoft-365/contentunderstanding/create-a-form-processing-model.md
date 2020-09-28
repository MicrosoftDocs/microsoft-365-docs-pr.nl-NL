---
title: Een formulier verwerkings model maken
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
description: Maak een formulier verwerkings model in Microsoft SharePoint Syntex.
ms.openlocfilehash: f61dbad837173c412daefb7285c4abff10a01817
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295476"
---
# <a name="create-a-form-processing-model-in-microsoft-sharepoint-syntex"></a>Een formulier verwerkings model maken in Microsoft SharePoint Syntex

De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project. [Lees meer over project cortex](https://aka.ms/projectcortex).

Met [AI Builder](https://docs.microsoft.com/ai-builder/overview) : een functie in Microsoft PowerApps-project cortex gebruikers kunnen rechtstreeks een [formulier verwerkings model](form-processing-overview.md) maken vanuit een SharePoint-documentbibliotheek. 

Het maken van een formulier voor formulier verwerkings modellen omvat het volgende:
 - Stap 1: het verwerkings model maken om het inhoudstype te maken
 - Stap 2: voorbeeldbestanden toevoegen en analyseren
 - Stap 3: de formuliervelden selecteren
 - Stap 4: uw model trainen en testen
 - Stap 5: uw model publiceren
 - Stap 6: uw model gebruiken

## <a name="requirements"></a>Vereisten

U kunt alleen een formulier verwerkings model maken in SharePoint-documentbibliotheken waarvoor dit is ingeschakeld. Als het verwerken van formulieren is ingeschakeld, kunt u de **AI Builder** **' een formulier verwerkings model maken '** weergeven in het menu **automatisch** in de documentbibliotheek.  Als u de verwerking voor de documentbibliotheek wilt inschakelen, moet u contact opnemen met de SharePoint-beheerder.

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>

## <a name="step-1-create-a-form-processing-model"></a>Stap 1: een formulier verwerkings model maken

De eerste stap bij het maken van een formulier voor formulier verwerkings modellen is het maken van een naam en het maken van het nieuwe inhoudstype en het maken van een nieuwe weergave van een documentbibliotheek.

1. Selecteer in de documentbibliotheek het menu **automatisch** , selecteer **AI Builder**en selecteer vervolgens **een formulier verwerkings model maken**.

    ![Een model maken](../media/content-understanding/create-ai-builder-model.png)</br>

2. Typ in het deelvenster **Nieuw model voor formulier verwerkings model** in het veld  **naam** een naam voor uw model (bijvoorbeeld *aankoop orders*).

    ![Nieuw model voor formulierverwerking](../media/content-understanding/new-form-model.png)</br> 

3. Wanneer u een formulier verwerkings model maakt, maakt u een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud. SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen]().

    Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken. 

4. Uw model maakt een nieuwe weergave in uw documentbibliotheek voor de opgehaalde gegevens. Als u de standaardweergave niet wilt, schakelt u **de optie de weergave als standaard instellen**uit.

5. Selecteer **maken**.

## <a name="step-2-add-and-analyze-documents"></a>Stap 2: documenten toevoegen en analyseren

Nadat u uw nieuwe formulier verwerkings model hebt gemaakt, wordt in de browser een nieuwe PowerApps AI Builder-formulier verwerkings model geopend. Op deze pagina kunt u voorbeelddocumenten toevoegen en analyseren. </br>

> [!NOTE]
> Zie de [vereisten voor invoerdocumenten voor formulieren bewerken en optimaliseren](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)voor meer informatie over het gebruik van voorbeeldbestanden. 

   ![Power apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 
1. Selecteer **documenten toevoegen** om voorbeelddocumenten toe te voegen om te beginnen met het toevoegen van de benoemde waardeparen die kunnen worden opgehaald. U kunt vervolgens uploaden kiezen **van lokale opslag**, **SharePoint**-of **Azure-blobopslag**. U dient ten minste vijf bestanden te gebruiken om te kunnen oefenen.

2. Wanneer u bestanden hebt toegevoegd, selecteert u **analyseren** om te controleren of de gegevens in het algemeen worden weergeven. Het kan een paar minuten duren voordat u klaar bent.</br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. Nadat de bestanden zijn geanalyseerd, selecteert u het bestand in de pagina **Selecteer de formuliervelden die u wilt opslaan** in het bestand om de gevonden velden weer te geven.</br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Stap 3: de formuliervelden selecteren

Nadat u de documenten voor velden hebt geanalyseerd, kunt u nu de gevonden velden zien en de bestanden identificeren die u wilt opslaan. Opgeslagen velden worden als kolommen weergegeven in de documentbibliotheekweergave van uw model en tonen de waarden die uit elk document worden opgehaald.

1. Op de volgende pagina ziet u een van de voorbeeldbestanden en worden alle gemeenschappelijke velden gemarkeerd die automatisch door het systeem zijn gedetecteerd. </br>

    ![Pagina met velden selecteren](../media/content-understanding/select-fields-page.png)</br> 

2. Selecteer de velden die u wilt opslaan en schakel het selectievakje in om uw selectie te bevestigen. Kies in het inkooporder model bijvoorbeeld de velden *datum*, *po*en *totaal* .  U kunt er ook voor kiezen om de naam van een veld te wijzigen. </br>

    ![Selecteer PO #](../media/content-understanding/po.png)</br> 

3. Als een veld niet door de analyse is gedetecteerd, kunt u er nog steeds voor kiezen om het toe te voegen. Selecteer de gegevens die u wilt extraheren en typ in het vak Naam de naam van de gewenste gegevens. Schakel vervolgens het selectievakje in. Houd er rekening mee dat u niet-gevonden velden in de resterende voorbeeldbestanden moet bevestigen.

4. Klik op **velden bevestigen** nadat u de velden hebt geselecteerd die u wilt opslaan. </br>
 
    ![Velden bevestigen na selecteren van velden](../media/content-understanding/confirm-fields.png)</br> 
 
5. Op de pagina **Selecteer de formuliervelden die u wilt opslaan** , wordt het aantal velden weergegeven dat u hebt geselecteerd. Selecteer **Gereed**.

## <a name="step-4-train-and-test-your-model"></a>Stap 4: uw model trainen en testen

Nadat u de velden hebt geselecteerd die u wilt opslaan, kunt u uw model trainen en testen met de **overzichtspagina model** .

1. Op de pagina **model samenvatting** wordt de opgeslagen velden weergegeven in de sectie **geselecteerde velden** . Selecteer **training** om de training te beginnen op uw voorbeeldbestanden. Dit kan een paar minuten duren.</br>

     ![De velden training selecteren](../media/content-understanding/select-fields-train.png)</br> 

2. Wanneer de melding wordt weergegeven dat de training is voltooid, selecteert u **Ga naar details pagina**. 

3. Op de pagina **model Details** kunt u kiezen hoe u het model gaat gebruiken door **snel testen**te selecteren. Hiermee kunt u bestanden slepen en neerzetten naar de pagina om te zien of de velden zijn gevonden.

    ![Velden bevestigen](../media/content-understanding/select-fields-train.png)</br> 

2. Wanneer de melding wordt weergegeven dat de training is voltooid, selecteert u **Ga naar details pagina**. 

3. Op de pagina **model Details** kiest u of u de werking van uw model wilt testen door **snel testen**te selecteren. Hiermee kunt u bestanden slepen en neerzetten naar de pagina om te zien of de velden zijn gevonden.

## <a name="step-5-publish-your-model"></a>Stap 5: uw model publiceren

1. Als u tevreden bent over de resultaten van uw model, selecteert u **publiceren** om het beschikbaar te maken voor gebruik.

2. Wanneer het model is gepubliceerd, selecteert **u model gebruiken**. Hiermee maakt u een PowerAutomate-stroom die kan worden uitgevoerd in uw SharePoint-documentbibliotheek en worden de velden die in het model zijn gevonden, uitgepakt en selecteert u **stroom maken**.
  
3. Wanneer u klaar bent, wordt het bericht weergegeven dat **uw stroom is gemaakt**.
 
## <a name="step-6-use-your-model"></a>Stap 6: uw model gebruiken

Nadat u uw model hebt gepubliceerd en de PowerAutomate-stroom hebt gemaakt, kunt u uw model gebruiken in de SharePoint-documentbibliotheek.

1. Wanneer u uw model hebt gepubliceerd, selecteert u **Ga naar SharePoint** om naar de documentbibliotheek te gaan.

2. In de modelweergave documentbibliotheek ziet u dat de velden die u nu als kolommen hebt geselecteerd, worden weergegeven.</br>

    ![Gesolliciteerd document bibliotheek model](../media/content-understanding/doc-lib-view.png)</br> 

3. De koppeling informatie naast **documenten** die een model voor formulierverwerking op deze documentbibliotheek toepast.

    ![Knop Info](../media/content-understanding/info-button.png)</br>  

4. Upload bestanden naar de documentbibliotheek. Alle bestanden die het model als het inhoudstype identificeert, worden weergegeven in de bestanden in de weergave en de opgehaalde gegevens in de kolommen.</br>

    ![Gereed](../media/content-understanding/doc-lib-done.png)</br>  

## <a name="see-also"></a>Zie ook
  
[De documentatie voor Power Automatiseer](https://docs.microsoft.com/power-automate/)</br>
[Training: bedrijfsprestaties verbeteren met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
