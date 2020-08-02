---
title: Een documentinzichtmodel toepassen op een documentbibliotheek (Voorbeeld)
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
description: Meer informatie over het toepassen van een gepubliceerd model op een SharePoint-documentbibliotheek.
ms.openlocfilehash: 7e5f3f02c2679769515b27026918a15c901c896e
ms.sourcegitcommit: ea5e2f85bd6b609658545b120c7e08789b9686fd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46537252"
---
# <a name="apply-a-document-understanding-model-preview"></a>Een documentbegripmodel toepassen (voorbeeld)

> [!Note] 
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Nadat u het model voor het begrijpen van documenten hebt gepubliceerd, u dit toepassen op een SharePoint-documentbibliotheek in uw Microsoft 365-tenant.

> [!Note]
> U het model alleen toepassen op documentbibliotheken waar u toegang toe hebt.


## <a name="apply-your-model-to-a-document-library"></a>Pas uw model toe op een documentbibliotheek.

Ga als voorbeeld van uw model naar een SharePoint-documentbibliotheek:

1. Selecteer op de startpagina van het model op de tegel **Model toepassen** op bibliotheken de optie **Model publiceren**. U **ook +Bibliotheek toevoegen** in de **bibliotheken selecteren met deze modelsectie.** </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. U vervolgens de SharePoint-site selecteren die de documentbibliotheek bevat waarop u het model wilt toepassen. Als de site niet wordt weergegeven in de lijst, gebruikt u het zoekvak om deze te zoeken.</br>

    ![Een site selecteren](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > U moet *machtigingen voor lijst beheren* of De rechten voor de documentbibliotheek *waarop* u het model toepast, bewerken.</br>

3. Nadat u de site hebt geselecteerd, moet u de documentbibliotheek selecteren waarop u het model wilt toepassen. In het voorbeeld selecteren we de documentbibliotheek *Documenten* op de *contoso-site voor het bijhouden van de aanvraag.*</br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. Aangezien het model is gekoppeld aan een inhoudstype, wordt bij het toepassen van het model een weergave gemaakt voor het inhoudstype met de labels die u als kolommen hebt geëxtraheerd. Deze weergave is standaard de standaardweergave van de bibliotheek, maar u er optioneel voor kiezen om deze niet de standaardweergave te laten zijn door **Geavanceerde instellingen** te selecteren en deze nieuwe weergave **als standaard**instellen uit te stellen.</br>

    ![Bibliotheekweergave](../media/content-understanding/library-view.png)</br>

5. Selecteer **Toevoegen** om het model toe te passen op de bibliotheek. 
6. Op de startpagina van het model, in de **sectie Bibliotheken met dit model,** ziet u de URL naar de SharePoint-site vermeld.</br>

    ![Bibliotheekweergave](../media/content-understanding/selected-library.png)</br>

7. Ga naar uw documentbibliotheek en zorg ervoor dat u zich in de documentbibliotheekweergave van het model bevindt. U zult merken dat als u de informatieknop naast de naam van de documentbibliotheek selecteert, er een bericht wordt weergegeven dat uw model is toegepast op de documentbibliotheek.

    ![Bibliotheekweergave](../media/content-understanding/info-du.png)</br> 


Nadat u het model hebt toegepast op de documentbibliotheek, u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.

Het model identificeert alle bestanden met het bijbehorende inhoudstype van het model en geeft deze in uw weergave weer. Als uw model uitstanden heeft, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand haalt.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Het model toepassen op bestanden die al in de documentbibliotheek staan

Hoewel een toegepast model alle bestanden verwerkt die naar de documentbibliotheek zijn geüpload nadat het is toegepast, u ook het volgende uitvoeren om het model uit te voeren op bestanden die al in de documentbibliotheek bestonden voordat het model werd toegepast:

1. Selecteer in uw documentbibliotheek de bestanden die u door uw model wilt verwerken.
2. Nadat u uw bestanden hebt geselecteerd, wordt **Classificeren en extraheren** weergegeven op het lint van de documentbibliotheek. Selecteer **Classificeren en uitpakken**.
3. De geselecteerde bestanden worden toegevoegd aan de wachtrij die moet worden verwerkt.

      ![Classificeren en extraheren](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)</br>
[Een afzuiger maken](create-an-extractor.md)</br>
[Overzicht van documentbegrip](document-understanding-overview.md)</br>
[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)  




