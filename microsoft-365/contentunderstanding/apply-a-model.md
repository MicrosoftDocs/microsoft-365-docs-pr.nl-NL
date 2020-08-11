---
title: Een document in overeenstemming brengen met een documentbibliotheek (preview)
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
description: Meer informatie over het toepassen van een model op een SharePoint-documentbibliotheek.
ms.openlocfilehash: 0658710704273ed04e9f2067413d1141773ef4aa
ms.sourcegitcommit: a3a5dc541b0c971608cc86ef480509c25a13ca60
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/10/2020
ms.locfileid: "46612678"
---
# <a name="apply-a-document-understanding-model-preview"></a>Een document met informatie over model toepassen (preview)

> [!Note] 
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Nadat u het document hebt gepubliceerd, kunt u dit toepassen op een SharePoint-documentbibliotheek in uw Microsoft 365-Tenant.

> [!Note]
> U kunt alleen het model toepassen op documentbibliotheken waartoe u toegang hebt.


## <a name="apply-your-model-to-a-document-library"></a>Uw model toepassen op een documentbibliotheek.

Uw model toepassen op een SharePoint-documentbibliotheek:

1. Selecteer op de startpagina van het model op de tegel **model toepassen op bibliotheken** de optie **model publiceren**. U kunt ook in de sectie **bibliotheken met behulp van deze model** sectie **+ bibliotheek toevoegen** selecteren. </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. Vervolgens kunt u de SharePoint-site met de documentbibliotheek selecteren waarop u het model wilt toepassen. Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om het te vinden.</br>

    ![Selecteer een site](../media/content-understanding/site-search.png)</br>

    > [!Note]
    > U moet beschikken over machtigingen voor *lijst beheren* of rechten *bewerken* voor de documentbibliotheek waarop u het model wilt toepassen.</br>

3. Wanneer u de site hebt geselecteerd, moet u de documentbibliotheek selecteren waarop u het model wilt toepassen. In dit voorbeeld selecteren we de documentbibliotheek *documenten* op de site van *Contoso zaken bijhouden* .</br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. Aangezien het model is gekoppeld aan een inhoudstype, wordt er een weergave gemaakt voor het inhoudstype waarvan de etiketten zijn uitgepakt als kolommen wanneer u deze toepast op de bibliotheek. Deze weergave is standaard de standaardweergave van een bibliotheek, maar u kunt er ook voor kiezen om de standaardweergave niet te gebruiken door **Geavanceerde instellingen** te selecteren en **deze nieuwe weergave als standaard wilt instellen**.</br>

    ![Bibliotheek weergave](../media/content-understanding/library-view.png)</br>

5. Selecteer **toevoegen** om het model op de bibliotheek toe te passen. 
6. Op de startpagina van het model, in de sectie **bibliotheken met dit model** , wordt de URL naar de SharePoint-site weergegeven.</br>

    ![Bibliotheek weergave](../media/content-understanding/selected-library.png)</br>

7. Ga naar de documentbibliotheek en zorg ervoor dat de documentbibliotheek van het model wordt weergegeven. Als u de knop informatie naast de naam van de documentbibliotheek selecteert, ziet u dat u in een bericht ziet dat uw model is toegepast op de documentbibliotheek.

    ![Bibliotheek weergave](../media/content-understanding/info-du.png)</br> 


Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en de resultaten bekijken.

Het model identificeert alle bestanden met het bijbehorende inhoudstype van het model en geeft ze weer in uw weergave. Als uw model uitpaknen bevat, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand uitpakt.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Het model toepassen op al uw bestanden in de documentbibliotheek

Wanneer een toegepast model alle bestanden die zijn geüpload naar de documentbibliotheek, uitvoert, kunt u ook het volgende doen om het model uit te voeren op bestanden die al waren opgenomen in de documentbibliotheek voordat het model wordt toegepast:

1. Selecteer in de documentbibliotheek de bestanden die u wilt laten verwerken door uw model.
2. Nadat u de bestanden hebt geselecteerd, worden **classificeerder en extract** weergegeven op het lint van de documentbibliotheek. Selecteer **classificeren en uitpakken**.
3. De bestanden die u hebt geselecteerd, worden toegevoegd aan de wachtrij, zodat u deze kunt verwerken.

      ![Classificeren en uitpakken](../media/content-understanding/extract-classify.png)</br> 





## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)</br>
[Een extractor maken](create-an-extractor.md)</br>
[Overzicht van document](document-understanding-overview.md)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)  




