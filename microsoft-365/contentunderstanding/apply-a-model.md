---
title: Een document met modellen op een documentbibliotheek toepassen
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
description: Meer informatie over het toepassen van een model op een SharePoint-documentbibliotheek
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295488"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Een document met model toepassen in Microsoft SharePoint Syntex

De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project. [Lees meer over project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Nadat u het document hebt gepubliceerd, kunt u dit toepassen op een SharePoint-documentbibliotheek in uw Microsoft 365-Tenant.

> [!NOTE]
> U kunt alleen het model toepassen op documentbibliotheken waartoe u toegang hebt.


## <a name="apply-your-model-to-a-document-library"></a>Uw model toepassen op een documentbibliotheek.

Uw model toepassen op een SharePoint-documentbibliotheek:

1. Selecteer op de startpagina van het model in de tegel **model toepassen op bibliotheken** de optie **model publiceren**. U kunt ook in de sectie **bibliotheken met behulp van deze model** sectie **+ bibliotheek toevoegen** selecteren. </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. Selecteer de SharePoint-site met de documentbibliotheek waarop u het model wilt toepassen. Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om het te vinden.</br>

    ![Selecteer een site](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > U moet beschikken over machtigingen voor *lijst beheren* of rechten *bewerken* voor de documentbibliotheek waarop u het model wilt toepassen.</br>

3. Wanneer u de site hebt geselecteerd, selecteert u de documentbibliotheek waarop u het model wilt toepassen. Selecteer de documentbibliotheek van de *documenten* in het voorbeeld op de site voor het *bijhouden van hoofdletters* .</br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. Aangezien het model is gekoppeld aan een inhoudstype, wordt er een weergave gemaakt voor het inhoudstype waarvan de etiketten worden weergegeven als kolommen wanneer u deze toepast op de bibliotheek. Deze weergave is standaard de standaardweergave van een bibliotheek, maar u kunt er ook voor kiezen om de standaardweergave niet te gebruiken door **Geavanceerde instellingen** te selecteren en **deze nieuwe weergave als standaard wilt instellen**.</br>

    ![Bibliotheek weergave](../media/content-understanding/library-view.png)</br>

5. Selecteer **toevoegen** om het model op de bibliotheek toe te passen. 
6. Op de startpagina van het model, in de sectie **bibliotheken met dit model** , ziet u de URL naar de weergegeven SharePoint-site.</br>

    ![Geselecteerde bibliotheek](../media/content-understanding/selected-library.png)</br>

7. Ga naar de documentbibliotheek en zorg ervoor dat de documentbibliotheek van het model wordt weergegeven. Als u de knop informatie naast de naam van de documentbibliotheek selecteert, wordt een bericht weergegeven dat uw model is toegepast op de documentbibliotheek.

    ![Informatie weergave](../media/content-understanding/info-du.png)</br> 


Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.

Het model identificeert alle bestanden met het bijbehorende inhoudstype van het model en toont ze in de weergave. Als het model uitpaknen bevat, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand wilt extraheren.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Het model toepassen op al uw bestanden in de documentbibliotheek

Hoewel een toegepast model alle bestanden die zijn geüpload naar de documentbibliotheek, wordt verwerkt nadat dit is toegepast, kunt u ook het volgende doen om het model uit te voeren op bestanden die al bestaan in de documentbibliotheek voordat het model wordt toegepast:

1. Selecteer in de documentbibliotheek de bestanden die u wilt laten verwerken door uw model.
2. Nadat u de bestanden hebt geselecteerd, worden **classificeerder en extract** weergegeven op het lint van de documentbibliotheek. Selecteer **classificeren en uitpakken**.
3. De bestanden die u hebt geselecteerd, worden toegevoegd aan de wachtrij, zodat u deze kunt verwerken.

      ![Classificeren en uitpakken](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)</br>
[Een extractor maken](create-an-extractor.md)</br>
[Overzicht van document](document-understanding-overview.md)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)  
