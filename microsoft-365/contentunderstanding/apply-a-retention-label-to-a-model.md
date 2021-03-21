---
title: Een retentietag toepassen op een model
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: In dit artikel wordt uitgelegd hoe je een retentietag kunt toepassen op een model in SharePoint Syntex
ms.openlocfilehash: 796130bfa967663b5696f49279154cfe9b16f703
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925366"
---
# <a name="apply-a-retention-label-to-a-model-in-sharepoint-syntex"></a>Je kunt een retentietag toepassen op een model in Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


Je kunt eenvoudig een [retentietag](../compliance/retention.md) toepassen op een model in Microsoft SharePoint Syntex. Je kan dit voor documentbegripmodellen en formulierverwerkingsmodellen doen.

Met retentietags kan je retentie-instellingen toepassen op de documenten die door je modellen worden geïdentificeerd.  Bijvoorbeeld: u wilt dat uw model niet alleen alle documenten met *verzekeringskennisgevingen* die naar uw documentbibliotheek worden geüpload identificeert, maar ook een retentietag *zakelijk* aanbrengt, zodat deze documenten niet uit de documentbibliotheek kunnen worden verwijderd gedurende de opgegeven periode (bijvoorbeeld de komende vijf maanden).

Je kunt een bestaande retentietag toepassen op je model via de modelinstellingen op de startpagina van het model. 

> [!Important]
> Als je wilt dat retentietags beschikbaar zijn voor je documentbegripmodel, moeten deze [aangemaakt en gepubliceerd worden in het Microsoft 365-compliancecentrum](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Een retentietag toepassen op een documentbegripmodel

1. Selecteren **Modelinstellingen** op de startpagina van het model.</br>
2. Selecteer in **Modelinstellingen**, in het gedeelte **Beveiliging en compliance**, het menu **Retentietag** om een lijst met retentietags weer te geven die beschikbaar zijn om toe te passen op het model.</br>
 ![Menu Retentietag](../media/content-understanding/retention-labels-menu.png)</br> 
3. Selecteer de retentietag die u wilt toepassen op het model en selecteer **Opslaan**.</br>

Nadat u de retentietag hebt toegepast op uw model, kunt u het toepassen op een:
- Nieuwe documentbibliotheek
- Documentbibliotheek waarop het model al is toegepast
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>De retentietag toepassen op een documentbibliotheek waarop het model al is toegepast

Als uw documentbegripmodel al is toegepast op een documentbibliotheek, kunt u het volgende doen om de retentietagupdate te synchroniseren en toe te passen op de documentbibliotheek:</br>

1. Selecteer op de startpagina van het model in het gedeelte **Bibliotheken met dit model** de documentbibliotheek waarop u de retentietagupdate wilt toepassen. </br> 
2. Selecteer **Synchroniseren**. </br>
 ![Model synchroniseren](../media/content-understanding/sync-model.png)</br> 


Nadat u de update hebt toegepast en gesynchroniseerd met uw model, kunt u het volgende doen:

1. Klik in het inhoudscentrum in het gedeelte **Bibliotheken met deze model** op de bibliotheek waarop het bijgewerkte model is toegepast. </br>
2. Selecteer in de documentbibliotheekweergave het informatiepictogram om de modeleigenschappen te bekijken.</br>  
3. Selecteer in de lijst **Actieve modellen** het bijgewerkte model.</br>
4. In het gedeelte **Retentietag** wordt de naam van de toegepaste retentietag weergegeven.</br>


Op de pagina met de weergave van uw model in uw documentbibliotheek wordt er een nieuwe kolom **Retentietag** weergegeven.  Omdat uw model bestanden classificeert die het identificeert als het relevante inhoudstype en ze vermeldt in de bibliotheekweergave, bevat de kolom Retentietag ook de naam van de retentietag die via het model is toegepast.


Bijvoorbeeld: op alle *verzekeringskennisgevingen* die uw model identificeert, wordt ook de retentietag *zakelijk* toegepast, zodat ze gedurende vijf maanden lang niet uit de documentenbibliotheek kunnen worden verwijderd. Als geprobeerd wordt het bestand uit de documentbibliotheek te verwijderen, wordt een foutbericht weergegeven met de mededeling dat het niet is toegestaan vanwege de toegepaste retentietag.

## <a name="to-add-a-retention-label-to-a-form-processing-model"></a>Een retentietag toepassen op een formulierverwerkingsmodel

> [!Important]
> Als je wilt dat retentietags beschikbaar zijn voor je formulierverwerkingsmodel, moeten deze [aangemaakt en gepubliceerd worden in het Microsoft 365-compliancecentrum](../compliance/create-apply-retention-labels.md#how-to-create-and-publish-retention-labels).

Je kan een retentietag toepassen op een formulierverwerkingsmodel wanneer je een model maakt of je kan het toepassen op een bestaand model.

### <a name="to-add-a-retention-label-when-you-create-a-form-processing-model"></a>Een retentietag toepassen wanneer je een formulierverwerkingsmodel maakt

1. Wanneer je een [nieuw formulierverwerkingsmodel maakt](./create-a-form-processing-model.md), kies <b>Geavanceerde instellingen.</b>
2. In <b>Geavanceerde instellingen</b>, in de sectie <b>Retentietag</b>, selecteer het menu en selecteer vervolgens de retentietag die je wilt toepassen op het model.</b>

 
     ![Toevoegen aan een nieuw formulierverwerkingsmodel](../media/content-understanding/retention-label-forms.png)</br>

3.  Nadat je de overige modelinstellingen afgewerkt hebt, selecteer <b>Aanmaken</b> om jouw model te maken.

### <a name="to-add-a-retention-label-to-an-existing-form-processing-model"></a>Een retentietag toepassen op een bestaand formulierverwerkingsmodel

Een retentietag toevoegen aan een bestaand formulierverwerkingsmodel kan op verschillende manieren:
- Via het Automatiseren-menu in de documentbibliotheek
- Via de actieve modellen-instellingen in de documentbibliotheek 


#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-through-the-automate-menu"></a>Een retentietag toepassen op een bestaand formulierverwerkingsmodel via het Automatiseren-menu

Je kan een retentietag aan een bestaand formulierverwerkingsmodel dat je bezit, toevoegen via het Automatiseren-menu in de documentbibliotheek, waarop het model wordt toegepast.


1. In je documentbibliotheek, waarop het formulierverwerkingsmodel wordt toegepast, kies je het menu <b>Automatiseren</b>, kies <b>AI-opbouwfunctie</b> en kies vervolgens <b>Informatie over formulierverwerkingsmodel weergeven</b>.

   ![Automatiseren-menu](../media/content-understanding/automate-menu.png)</br>

2. In de informatie over het model, in de sectie <b>Retentietag</b>, selecteer de retentietag die je wilt toepassen.  Selecteer vervolgens <b>Opslaan</b>.

     ![Toevoegen aan een bestaand formulierverwerkingsmodel](../media/content-understanding/retention-label-model-details.png)</br> 

#### <a name="to-add-a-retention-label-to-an-existing-form-processing-model-in-the-active-model-settings"></a>Een retentietag toevoegen aan een bestaand formulierverwerkingsmodel in de actieve modelinstellingen

Je kan een retentietag aan een bestaand formulierverwerkingsmodel dat je bezit, toevoegen via de actieve modelinstellingen in de documentbibliotheek, waarop het model wordt toegepast.

1. In de SharePoint documentbibliotheek waarop het model wordt toegepast, selecteer het pictogram<b>Actieve modellen weergeven</b> en selecteer vervolgens <b>Actieve modellen weergeven</b>.</b>

   ![Actieve modellen weergeven](../media/content-understanding/info-du.png)</br> 

2. In <b>Actieve modellen</b>, selecteer het formulierverwerkingsmodel waarop je de retentietag wilt toepassen.

     ![Informatie over model](../media/content-understanding/retention-label-model-details.png)</br> 


3. In de informatie over het model, in de sectie <b>Retentietag</b>, selecteer de retentietag die je wilt toepassen.  Selecteer vervolgens <b>Opslaan</b>.

> [!NOTE]
> Enkel de eigenaar van het model kan bewerkingen maken in het deelvenster modelinstellingen. 


## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)

[Een extractor maken](create-an-extractor.md)

[Overzicht van documentbegrip](document-understanding-overview.md)