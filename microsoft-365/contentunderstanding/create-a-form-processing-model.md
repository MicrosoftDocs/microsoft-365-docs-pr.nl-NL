---
title: Een formulier verwerkings model maken (preview)
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
description: Maak een formulier verwerkings model in Project cortex.
ms.openlocfilehash: 733baf24d8a484571ba9882fdda2633dc2ce0504
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612772"
---
# <a name="create-a-form-processing-model-preview"></a>Een formulier verwerkings model maken (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).

Met [AI Builder](https://docs.microsoft.com/ai-builder/overview) : een functie in Microsoft PowerApps-project cortex gebruikers kunnen rechtstreeks een [formulier verwerkings model](form-processing-overview.md) maken vanuit een SharePoint-documentbibliotheek. 

Het maken van een formulier voor formulier verwerkings modellen omvat het volgende:
 - Stap 1: het verwerkings model maken om het inhoudstype te maken
 - Stap 2: voorbeeldbestanden toevoegen en analyseren
 - Stap 3: de formuliervelden selecteren
 - Stap 4: uw model trainen en testen
 - Stap 5: uw model publiceren
 - Stap 6: uw model gebruiken


## <a name="requirements"></a>Vereisten

U kunt alleen een formulier verwerkings model maken in SharePoint-documentbibliotheken waarin dit is ingeschakeld. Als het verwerken van formulieren is ingeschakeld, kunt u de **AI Builder** **' een formulier verwerkings model maken '** weergeven in het menu **automatisch** in de documentbibliotheek.  Neem contact op met uw beheerder als u de verwerking voor de documentbibliotheek wilt inschakelen.

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a>Stap 1: een formulier verwerkings model maken

De eerste stap bij het maken van een formulier verwerkings model is het noemen van het maken van het nieuwe inhoudstype en het maken van een nieuwe weergave van de documentbibliotheek.

1. Selecteer in de documentbibliotheek het menu **automatiseren** , selecteer **AI Builder**en selecteer vervolgens **een formulier verwerkings model maken**.

    ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>
2. Typ in het deelvenster **Nieuw model voor formulier verwerkings model** in het veld **naam** een naam voor uw model (bijvoorbeeld *aankoop orders*).

    ![Nieuw model voor formulierverwerking](../media/content-understanding/new-form-model.png)</br> 

3. Wanneer u een formulier verwerkings model maakt, maakt u een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met gemeenschappelijke kenmerken en deel een verzameling kolommen of metagegevenseigenschappen voor die specifieke inhoud. SharePoint-inhoudstypen worden beheerd via de [Galerie met inhoudstypen]().

    Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie SharePoint-inhoudstypen om het schema te gebruiken. 

4. Uw model maakt een nieuwe weergave in uw documentbibliotheek voor de opgehaalde gegevens. Als u de standaardweergave niet wilt, schakelt u **de optie de weergave als standaard instellen**uit.
5. Selecteer **maken**.


## <a name="step-2-add-and-analyze-documents"></a>Stap 2: documenten toevoegen en analyseren

Nadat u uw nieuwe formulier verwerkings model hebt gemaakt, wordt in de browser een nieuwe PowerApps AI Builder-formulier verwerkings model geopend. Op deze pagina kunt u voorbeelddocumenten toevoegen en analyseren. </br>

> [!Note]
> Zie de [vereisten voor invoerdocumenten voor formulieren bewerken en optimaliseren](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)voor meer informatie over het gebruik van voorbeeldbestanden. 

   ![Power apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. Klik op **documenten toevoegen** om voorbeelddocumenten toe te voegen die worden geanalyseerd om te bepalen welke benoemde waardeparen kunnen worden opgehaald. U kunt **uploaden vanaf de lokale opslag**, **SharePoint**of **Azure-blobopslag**kiezen. U dient ten minste vijf bestanden te gebruiken om te kunnen oefenen.
2. Na het toevoegen van uw bestanden, selecteert u **analyseren** om te controleren of alle bestanden algemeen zijn. Dit kan enkele minuten duren voordat u klaar bent.</br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. Nadat de gegevens zijn geanalyseerd, klikt u in de pagina **Selecteer de formuliervelden die u wilt opslaan** op het bestand om de gevonden velden weer te geven.</br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Stap 3: de formuliervelden selecteren

Nadat u uw documenten hebt geanalyseerd voor velden, kunt u nu zien welke velden zijn gevonden en welke velden u wilt opslaan. Opgeslagen velden worden als kolommen weergegeven in de documentbibliotheekweergave van uw model en worden de waarden weergegeven die uit elk document worden opgehaald.

1. Op de volgende pagina wordt een van de voorbeeldbestanden weergegeven en worden alle gemeenschappelijke velden gemarkeerd die automatisch door het systeem zijn gedetecteerd. </br>

    ![Formuliervelden selecteren](../media/content-understanding/select-fields-page.png)</br> 

2. Selecteer de velden die u wilt opslaan en schakel het selectievakje in om uw selectie te bevestigen. In het inkooporder model kunt u bijvoorbeeld kiezen voor de velden *date*, *po*en *Total* .  U kunt er ook voor kiezen om de naam van een veld te wijzigen. </br>

    ![Selecteer PO #](../media/content-understanding/po.png)</br> 

3. Als een veld niet door de analyse is gedetecteerd, kunt u er nog steeds voor kiezen om het toe te voegen. Selecteer de gegevens die u wilt extraheren en typ in het vak Naam de naam die u wilt opgeven. Selecteer vervolgens de cheque. Houd er rekening mee dat u de niet-gevonden velden in de resterende voorbeeldbestanden moet bevestigen.
4. Klik op **velden bevestigen** nadat u de velden hebt geselecteerd die u wilt opslaan. </br>
 
    ![Velden bevestigen](../media/content-understanding/confirm-fields.png)</br> 
 
5. Op de pagina **Selecteer de formuliervelden die u wilt opslaan** , wordt het aantal velden weergegeven dat u hebt geselecteerd. Selecteer **Gereed**.

## <a name="step-4-train-and-test-your-model"></a>Stap 4: uw model trainen en testen

Nadat u de velden hebt geselecteerd die u wilt opslaan, kunt u het model met de **overzichtspagina model** leren trainen en testen.

1. Op de pagina **model samenvatting** wordt de opgeslagen velden weergegeven in de sectie **geselecteerde velden** . Selecteer **training** om de training te beginnen op uw voorbeeldbestanden. Dit kan een paar minuten duren.</br>
    ![Velden bevestigen](../media/content-understanding/select-fields-train.png)</br> 
2. Wanneer de melding wordt weergegeven dat de training is voltooid, selecteert u **Ga naar details pagina**. 
3. Op de pagina **model Details** kunt u kiezen hoe u het model gaat gebruiken door **snel testen**te selecteren. Hiermee kunt u bestanden slepen en neerzetten naar de pagina om te zien of de velden zijn gevonden.

## <a name="step-5-publish-your-model"></a>Stap 5: uw model publiceren



1. Als u tevreden bent over de resultaten van uw model, selecteert u **publiceren** om het beschikbaar te maken voor gebruik.
2. Wanneer het model is gepubliceerd, selecteert **u model gebruiken**. Hiermee wordt een PowerAutomate-stroom gemaakt die wordt uitgevoerd in uw SharePoint-documentbibliotheek, en worden de velden die in het model zijn gevonden, uitgepakt. Selecteer **Create flow**.  
3. Wanneer u klaar bent, wordt het bericht weergegeven dat **uw stroom is gemaakt**.
 
 
## <a name="step-6-use-your-model"></a>Stap 6: uw model gebruiken

Nadat u uw model hebt gepubliceerd en de PowerAutomate-stroom hebt gemaakt, kunt u uw model gebruiken in de SharePoint-documentbibliotheek.

1. Wanneer u uw model hebt gepubliceerd, selecteert u **Ga naar SharePoint** om naar de documentbibliotheek te gaan.
2. In de modelweergave van uw documentbibliotheek ziet u dat de velden die u nu als kolommen hebt geselecteerd, worden weergegeven.</br>

    ![Document bibliotheek met toegepast model](../media/content-understanding/doc-lib-view.png)</br> 

    Daarnaast wordt in de koppeling informatie naast **documenten** aangegeven dat een model voor formulierverwerking op deze documentbibliotheek is toegepast.

    ![Opgehaalde](../media/content-understanding/info-button.png)</br>  

3. Upload bestanden naar de documentbibliotheek. Alle bestanden die het model identificeert terwijl het inhoudstype het inhoudstype bevat, worden weergegeven in de weergave en worden de opgehaalde gegevens in de kolommen weergegeven.</br>

    ![Opgehaalde](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a>Zie ook
  
[De documentatie voor Power Automatiseer](https://docs.microsoft.com/power-automate/)</br>
[Training: bedrijfsprestaties verbeteren met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




