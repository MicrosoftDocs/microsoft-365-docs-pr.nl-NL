---
title: Een documentbegripmodel toepassen op een documentbibliotheek
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
description: Informatie over het toepassen van een gepubliceerd model op een SharePoint-documentbibliotheek.
ms.openlocfilehash: 17da1e37f72504ac5e0e26c0dd190efced08d285
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080770"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a>Een documentbegripmodel toepassen in Microsoft SharePoint Syntex

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

Na het publiceren van uw documentbegtipmodel kunt u het toepassen op een of meer SharePoint-documentbibliotheken in uw Microsoft 365-tenant.

> [!NOTE]
> U kunt het model alleen toepassen op documentbibliotheken waar u toegang toe heeft.


## <a name="apply-your-model-to-a-document-library"></a>Uw model toepassen op een documentbibliotheek.

U past als volgt een model toe op een SharePoint-documentbibliotheek:

1. Op de startpagina van het model selecteert u op tegel **Model toepassen op bibliotheken** de optie **Model publiceren**. U kunt ook **+Bibliotheek toevoegen** selecteren in het gedeelte **Bibliotheken met dit model**. </br>

    ![Model toevoegen aan bibliotheek](../media/content-understanding/apply-to-library.png)</br>

2. Vervolgens kunt u de SharePoint-site selecteren die de documentbibliotheek bevat waarop u het model wilt toepassen. Als de site niet in de lijst wordt weergegeven, gebruikt u het zoekvak om de site te vinden.</br>

    ![Een site selecteren](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > U moet beschikken over de machtiging *Lijst beheren* of *Machtiging voor bewerken* voor de documentbibliotheek waarop u het model toepast.</br>

3. Na het selecteren van de site selecteert u de documentbibliotheek waarop u het model wilt toepassen. Selecteer in het voorbeeld de documentbibliotheek *Documenten* van de site *Contoso Case Tracking*.</br>

    ![Een documentbibliotheek selecteren](../media/content-understanding/select-doc-library.png)</br>

4. Aangezien het model aan een inhoudstype is gekoppeld, worden het inhoudstype en de bijbehorende weergave met de labels die worden opgehaald, als kolommen toegevoegd wanneer u het model toepast. Deze weergave is de standaardweergave van de bibliotheek, maar u kunt ervoor kiezen om dit niet de standaardweergave te maken door **Geavanceerde instellingen** te selecteren en **Deze nieuwe weergave instellen als standaard** te deselecteren.</br>

    ![Documentbibliotheekweergave](../media/content-understanding/library-view.png)</br>

5. Selecteer **Toevoegen** om het model toe te passen op de bibliotheek. 
6. Op de startpagina van het model wordt in het gedeelte **Bibliotheken met dit model** de URL van de SharePoint-site weergegeven.</br>

    ![Geselecteerde bibliotheek](../media/content-understanding/selected-library.png)</br>

7. Ga naar de documentbibliotheek en controleer of de documentbibliotheekweergave van het model wordt weergegeven. U ziet dat wanneer u de informatieknop naast de naam van de documentbibliotheek selecteert, het bericht wordt weergegeven dat op de documentbibliotheek een model is toegepast.

    ![Informatieweergave](../media/content-understanding/info-du.png)</br> 

    U kunt **Actieve modellen weergeven** selecteren voor meer informatie over eventuele modellen die zijn toegepast op de documentbibliotheek.

8. In het deelvenster **Actieve modellen** ziet u de modellen die zijn toegepast op de documentbibliotheek. Selecteer een model voor meer informatie, zoals een beschrijving van het model, wie het model heeft gepubliceerd en of het model een retentielabel toepast op de bestanden die door het model worden geclassificeerd.

    ![Deelvenster Actieve modellen](../media/content-understanding/active-models.png)</br> 

Nadat u het model hebt toegepast op de documentbibliotheek, kunt u beginnen met het uploaden van documenten naar de site en bekijken van de resultaten.

Het model identificeert bestanden met het relevante inhoudstype en toont ze in de weergave. Als uw model extractoren bevat, worden in de weergave kolommen weergegeven voor de gegevens die u uit elk bestand haalt.

### <a name="apply-the-model-to-files-already-in-the-document-library"></a>Het model toepassen op bestanden die zich al in de documentbibliotheek bevinden

Terwijl een toegepast model alle bestanden verwerkt die naar de documentbibliotheek worden geüpload nadat het is toegepast, kunt u ook het volgende doen om het model uit te voeren op bestanden die al aanwezig waren in de documentbibliotheek voordat het model werd toegepast:

1. Selecteer in de documentbibliotheek de bestanden die u wilt laten verwerken door het model.
2. Nadat u bestanden hebt geselecteerd, wordt **Classificeren en extraheren** weergegeven op het lint van de documentbibliotheek. Selecteer **Classificeren en extraheren**.
3. De bestanden die u hebt geselecteerd, worden toegevoegd aan de verwerkingswachtrij.

      ![Classificeren en extraheren](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> Je kunt individuele documenten naar een bibliotheek kopiëren en ze toepassen op een model. Dit is echter niet mogelijk voor mappen.

### <a name="the-classification-date-field"></a>Het veld Classificatiedatum

Wanneer een SharePoint Syntex-model voor inhoudsbegrip of een formulierverwerkingsmodel wordt toegepast op een documentbibliotheek, wordt het veld <b>Classificatiedatum</b> opgenomen in het bibliotheekschema. Dit veld is standaard leeg, maar wanneer documenten door een model worden verwerkt en geclassificeerd, wordt dit veld bijgewerkt met de datum en tijd van voltooiing. 

   ![De kolom Classificatiedatum](../media/content-understanding/class-date-column.png)</br> 

Het veld Classificatiedatum wordt gebruikt door het [<b>Wanneer een bestand wordt geclassificeerd door een model voor inhoudsbegrip,</b> activeert u ](https://docs.microsoft.com/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) om een Power Automate-workflow uit te voeren nadat een Syntex-model voor inhoudsbegrip klaar is met het verwerken van een bestand en het veld Classificatiedatum is bijgewerkt.

   ![Trigger voor workflow](../media/content-understanding/trigger.png)</br>

De trigger <b>Wanneer een bestand wordt geclassificeerd door een model voor inhoudsbegrip</b> kan vervolgens worden gebruikt om een andere workflow te starten met behulp van uit het bestand geëxtraheerde gegevens.



## <a name="see-also"></a>Zie ook
[Een classificatie maken](create-a-classifier.md)

[Een extractor maken](create-an-extractor.md)

[Overzicht van documentbegrip](document-understanding-overview.md)


