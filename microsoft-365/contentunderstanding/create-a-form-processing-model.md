---
title: Een formulierverwerkingsmodel maken (Voorbeeld)
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
description: Maak een formulierverwerkingsmodel in Project Cortex.
ms.openlocfilehash: d3ca64ff5923e95704b72fd748884549a18624a3
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540140"
---
# <a name="create-a-form-processing-model-preview"></a>Een formulierverwerkingsmodel maken (Voorbeeld)

> [!Note] 
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

Met behulp van [AI Builder](https://docs.microsoft.com/ai-builder/overview) - een functie in Microsoft PowerApps - kunnen Project Cortex-gebruikers rechtstreeks vanuit een SharePoint-documentbibliotheek een [formulierverwerkingsmodel](form-processing-overview.md) maken. 

Het maken van een formulierverwerkingsmodel omvat het volgende:
 - Stap 1: Het van-verwerkingsmodel maken om het inhoudstype te maken
 - Stap 2: Voorbeeldbestanden toevoegen en analyseren
 - Stap 3: Uw formuliervelden selecteren
 - Stap 4: Train en test je model
 - Stap 5: Uw model publiceren
 - Stap 6: Gebruik uw model


## <a name="requirements"></a>Vereisten

U alleen een formulierverwerkingsmodel maken in SharePoint-documentbibliotheken waarin het is ingeschakeld. Als formulierverwerking is ingeschakeld, u de **AI Builder** **'Een formulierverwerkingsmodel maken'** zien onder het menu **Automatiseren** in uw documentbibliotheek.  Als de verwerking in de documentbibliotheek is ingeschakeld, neemt u contact op met de beheerder.

 ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>


## <a name="step-1-create-a-form-processing-model"></a>Stap 1: Een formulierverwerkingsmodel maken

De eerste stap bij het maken van een formulierverwerkingsmodel is de naam te geven om het nieuwe inhoudstype te definiëren en er een nieuwe documentbibliotheekweergave voor te maken.

1. Selecteer in de documentbibliotheek het menu **Automatiseren,** selecteer **AI Builder**en selecteer **vervolgens Een formulierverwerkingsmodel maken.**

    ![Een AI Builder-model maken](../media/content-understanding/create-ai-builder-model.png)</br>
2. Typ in het deelvenster Modellen van **het nieuwe formulierverwerkingsmodel** in het veld **Naam** een naam voor uw model (bijvoorbeeld *Inkooporders).*

    ![Nieuw formulierverwerkingsmodel](../media/content-understanding/new-form-model.png)</br> 

3. Wanneer u een formulierverwerkingsmodel maakt, maakt u een nieuw SharePoint-inhoudstype. Een SharePoint-inhoudstype vertegenwoordigt een categorie documenten met algemene kenmerken en deelt een verzameling kolommen of metagegevens eigenschappen voor die bepaalde inhoud. SharePoint-inhoudstypen worden beheerd via de [galerie Inhoudstypen]().

    Selecteer **Geavanceerde instellingen** als u dit model wilt toewijzen aan een bestaand inhoudstype in de galerie Met SharePoint-inhoudstypen om het schema te gebruiken. 

4. Uw model maakt een nieuwe weergave in uw documentbibliotheek voor uw uitgepakte gegevens. Als u niet wilt dat deze in de standaardweergave wordt weergegeven, schakelt u **de optie De weergave als standaard instellen uit.**
5. Selecteer **Maken**.


## <a name="step-2-add-and-analyze-documents"></a>Stap 2: Documenten toevoegen en analyseren

Nadat u uw nieuwe formulierverwerkingsmodel hebt gemaakt, opent uw browser een nieuwe PowerApps AI Builder-formulierverwerkingsmodelpagina. Op deze pagina u uw voorbeelddocumenten toevoegen en analyseren. </br>

> [!Note]
> Zie de vereisten voor het [invoerdocument en de optimalisatietips voor formulierverwerkingsmodel](https://docs.microsoft.com/ai-builder/form-processing-model-requirements)bij het zoeken naar bijvoorbeeld bestanden. 

   ![Power Apps AI Builder](../media/content-understanding/powerapps.png)</br> 
 

1. Klik **op Documenten toevoegen** om voorbeelddocumenten toe te voegen die worden geanalyseerd om te bepalen welke benoemde waardeparen kunnen worden geëxtraheerd. U **kiezen uit Uploaden vanuit lokale opslag,** **SharePoint**of **Azure Blob-opslag.** U moet ten minste vijf bestanden gebruiken voor training.
2. Nadat u uw bestanden hebt toegevoegd, selecteert u **Analyseren** om te controleren op alle algemene informatie die alle bestanden zijn. Houd er rekening mee dat dit enkele minuten kan duren.</br> 
 
    ![Bestanden analyseren](../media/content-understanding/analyze.png)</br> 

3. Nadat ze zijn geanalyseerd, klikt u in de **pagina Formuliervelden selecteren die u wilt opslaan** op het bestand om de gedetecteerde velden weer te geven.</br>

    ![Formuliervelden selecteren](../media/content-understanding/select-form-fields.png)</br> 

## <a name="step-3-select-your-form-fields"></a>Stap 3: Uw formuliervelden selecteren

Nadat u uw documenten voor velden hebt geanalyseerd, u nu zien welke velden zijn gevonden en welke velden u wilt opslaan. Opgeslagen velden worden weergegeven als kolommen in de documentbibliotheekweergave van uw model en geven de waarden weer die uit elk document zijn geëxtraheerd.

1. Op de volgende pagina wordt een van uw voorbeeldbestanden weergegeven en worden alle veelvoorkomende velden weergegeven die automatisch door het systeem zijn gedetecteerd. </br>

    ![Formuliervelden selecteren](../media/content-understanding/select-fields-page.png)</br> 

2. Selecteer de velden die u wilt opslaan en schakel het selectievakje in om uw selectie te bevestigen. In het model Inkooporder u er bijvoorbeeld voor kiezen om de velden *Datum,* *PO*en *Totaal* te selecteren.  Houd er rekening mee dat u er ook voor kiezen om de naam van een veld te wijzigen als u dat wilt. </br>

    ![Po selecteren #](../media/content-understanding/po.png)</br> 

3. Als een veld niet is gedetecteerd door analyse, u er nog steeds voor kiezen om het toe te voegen. Markeer de informatie die u wilt extraheren en typ in het vak Naam in de naam die u wilt opgeven. Selecteer vervolgens de cheque. Houd er rekening mee dat u onontdekte velden in uw resterende voorbeeldbestanden moet bevestigen.
4. Klik **op Velden bevestigen** nadat u de velden hebt geselecteerd die u wilt opslaan. </br>
 
    ![Velden bevestigen](../media/content-understanding/confirm-fields.png)</br> 
 
5. Op de **pagina Formuliervelden selecteren die u wilt opslaan,** wordt het aantal velden weergegeven dat u hebt geselecteerd. Selecteer **Gereed**.

## <a name="step-4-train-and-test-your-model"></a>Stap 4: Train en test je model

Nadat u de velden hebt geselecteerd die u wilt opslaan, u op de pagina **Modeloverzicht** uw model trainen en testen.

1. Op de pagina **Modeloverzicht** worden de opgeslagen velden weergegeven in de sectie **Geselecteerde velden.** Selecteer **Trainen** om te beginnen met trainen in uw voorbeeldbestanden. Houd er rekening mee dat dit enkele minuten kan duren.</br>
    ![Velden bevestigen](../media/content-understanding/select-fields-train.png)</br> 
2. Wanneer u de melding ziet die de training heeft voltooid, selecteert u **Pagina Ga naar details**. 
3. Op de pagina **Modeldetails** u ervoor kiezen om te testen hoe uw model werkt door **snelle test**te selecteren. Hiermee u bestanden naar de pagina slepen en neerzetten en kijken of de velden worden gedetecteerd.

## <a name="step-5-publish-your-model"></a>Stap 5: Uw model publiceren



1. Als u tevreden bent met de resultaten van uw model, selecteert u **Publiceren** om het beschikbaar te maken voor gebruik.
2. Selecteer Na de publicatie van het model **het model gebruiken**. Hiermee wordt een PowerAutomate-stroom gemaakt die wordt uitgevoerd in uw SharePoint-documentbibliotheek en de velden die in het model zijn geïdentificeerd, wordt geëxtraheerd. Selecteer **Stroom maken**.  
3. Wanneer voltooid, ziet u het bericht **Uw stroom is gemaakt**.
 
 
## <a name="step-6-use-your-model"></a>Stap 6: Gebruik uw model

Nadat u uw model hebt gepubliceerd en de PowerAutomate-stroom hebt gemaakt, u uw model gebruiken in uw SharePoint-documentbibliotheek.

1. Nadat u uw model hebt gepubliceerd, selecteert u **Ga naar SharePoint** om naar uw documentbibliotheek te gaan.
2. Let er in de modelweergave van de documentbibliotheek op dat de velden die u hebt geselecteerd nu als kolommen worden weergegeven.</br>

    ![Documentbibliotheek met toegepast model](../media/content-understanding/doc-lib-view.png)</br> 

    Houd er ook rekening mee dat de informatiekoppeling naast **Documenten** er rekening mee houdt dat een formulierverwerkingsmodel wordt toegepast op deze documentbibliotheek.

    ![Uitgepakt](../media/content-understanding/info-button.png)</br>  

3. Bestanden uploaden naar uw documentbibliotheek. Alle bestanden die het model identificeert als het inhoudstype, geven een lijst van de bestanden in uw weergave en geven de uitgepakte gegevens in de kolommen weer.</br>

    ![Uitgepakt](../media/content-understanding/doc-lib-done.png)</br>  



## <a name="see-also"></a>Zie ook
  
[Documentatie voor energie automatiseren](https://docs.microsoft.com/power-automate/)</br>
[Training: Verbeter de bedrijfsprestaties met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




