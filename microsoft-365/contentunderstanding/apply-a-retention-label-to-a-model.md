---
title: Een Bewaar label toepassen op een document wat model
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: In dit artikel wordt uitgelegd hoe u een Bewaar label toepast op een document dat het model van een document begrijpt.
ms.openlocfilehash: 26ad64906c0e2a311d8b244e8e1596a8b975cc15
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294916"
---
# <a name="apply-a-retention-label-to-a-document-understanding-model"></a>Een Bewaar label toepassen op een document wat model

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

U kunt eenvoudig een [Bewaar label](https://docs.microsoft.com/microsoft-365/compliance/retention) toepassen op een document met beinformatie over model in Microsoft SharePoint Syntex.

Met labels voor bewaarbeleid kunt u bewaarinstellingen toepassen op de documenten die uw document begrijpt.  U wilt bijvoorbeeld dat uw model alleen de documenten van de *verzekerings kennisgeving* die wordt geüpload naar de documentbibliotheek identificeert, maar u kunt ook een Bewaar code voor een *bedrijf* toepassen, zodat deze documenten niet kunnen worden verwijderd uit de documentbibliotheek voor de opgegeven tijdsperiode (bijvoorbeeld de volgende vijf maanden).

U kunt een al bestaand Bewaar label toepassen op uw document met behulp van de modelinstellingen op de startpagina van uw model. 

> [!Important]
> Voor Bewaar etiketten die u kunt gebruiken om uw inhoud toe te passen, moeten ze worden [gemaakt en gepubliceerd in het nalevings centrum van Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/create-apply-retention-labels#how-to-create-and-publish-retention-labels).

## <a name="to-add-a-retention-label-to-a-document-understanding-model"></a>Een Bewaar label toevoegen aan een document wat is het model

1. Selecteer op de startpagina van model de optie **modelinstellingen**.</br>
2. Selecteer in de sectie **model instellingen**in de sectie **beveiliging en compliance** het menu **Bewaar label** om een lijst weer te geven van de Bewaar etiketten die beschikbaar zijn om te worden toegepast op het model.</br>
 ![Menu Bewaar label](../media/content-understanding/retention-labels-menu.png)</br> 
3. Selecteer het Bewaar label dat u wilt toepassen op het model en selecteer vervolgens **Opslaan**.</br>

Na het toepassen van het Bewaar etiket op uw model, kunt u dit toepassen op een van de volgende dingen:
- Nieuwe documentbibliotheek
- Document bibliotheek waarmee het model al wordt toegepast
 
## <a name="apply-the-retention-label-to-a-document-library-to-which-the-model-is-already-applied"></a>Het label voor bewaarbeleid toepassen op een documentbibliotheek waarmee het model al wordt toegepast

Als het document al is toegepast op een documentbibliotheek, kunt u het volgende doen om uw Bewaar etiket-update te synchroniseren zodat u deze op de documentbibliotheek kunt toepassen:</br>

1. Selecteer op de startpagina van uw model in de sectie **bibliotheken met dit model** de documentbibliotheek waarop u de update voor het Bewaar label wilt toepassen. </br> 
2. Selecteer **synchroniseren**. </br>
 ![Model synchroniseren](../media/content-understanding/sync-model.png)</br> 


Nadat u de update hebt geïnstalleerd en de update hebt gesynchroniseerd met uw model, kunt u het volgende doen:

1. Klik in het inhouds centrum, in de sectie **bibliotheken met dit model** , op de bibliotheek waarop uw bijgewerkte model is toegepast. </br>
2. Selecteer in de weergave Documentbibliotheek het informatiepictogram om de modeleigenschappen te controleren.</br>  
3. Selecteer het bijgewerkte model in de lijst **actieve modellen** .</br>
4. In het gedeelte **Bewaar label** ziet u de naam van het toegepaste Bewaar etiket.</br>


Op de paginaweergave van uw model in de documentbibliotheek wordt een nieuwe **Bewaar label** kolom weergegeven.  Aangezien bestanden worden geclassificeerd op basis van het inhoudstype van de modelsite en deze weergeven in de bibliotheek weergave, wordt in de kolom Bewaar etiket ook de naam van het Bewaar label weergegeven dat op het model is toegepast.


Alle *verzekerings kennisgevingen* die uw model identificeert, zien er *ook het* bedrijfsbewaar label voor, zodat ze gedurende vijf maanden niet uit de documentbibliotheek kunnen worden verwijderd. Als er wordt gevraagd of u het bestand uit de documentbibliotheek wilt verwijderen, wordt er een foutbericht weergegeven met de melding dat dit niet is toegestaan vanwege het toegepaste Bewaar etiket.

## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)</br>
[Een extractor maken](create-an-extractor.md)</br>
[Overzicht van document](document-understanding-overview.md)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)  
