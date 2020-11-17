---
title: Een retentietag toepassen op een documentbegripmodel
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: In dit artikel wordt uitgelegd hoe u een retentietag kunt toepassen op een documentbegripmodel
ms.openlocfilehash: 2e6d300b63a173d01488406485cffa44fab4278e
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087473"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Een retentietag toepassen op een documentbegripmodel

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4GydO]  

</br>


U kunt eenvoudig een [retentietag](https://docs.microsoft.com/microsoft-365/compliance/retention) toepassen op een documentbegripmodel in Microsoft SharePoint Syntex.

Met retentietags kunt u retentie-instellingen toepassen op de documenten die door uw documentbegripmodellen worden geïdentificeerd.  Bijvoorbeeld: u wilt dat uw model niet alleen alle documenten met *verzekeringskennisgevingen* die naar uw documentbibliotheek worden geüpload identificeert, maar ook een retentietag *zakelijk* aanbrengt, zodat deze documenten niet uit de documentbibliotheek kunnen worden verwijderd gedurende de opgegeven periode (bijvoorbeeld de komende vijf maanden).

U kunt een bestaande retentietag toepassen op uw documentbegripmodel via de modelinstellingen op de startpagina van uw model. 

> [!Important]
> Als u wilt dat retentietags beschikbaar zijn voor uw inhoudsbegripmodel, moeten deze worden [gemaakt en gepubliceerd in het Microsoft 365-compliancecentrum](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

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

## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)

[Een extractor maken](create-an-extractor.md)

[Overzicht van documentbegrip](document-understanding-overview.md)


