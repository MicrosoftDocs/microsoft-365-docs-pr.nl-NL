---
title: Overzicht formulierverwerking
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Informatie over formulierverwerking in Microsoft SharePoint Syntex
ms.openlocfilehash: bbdf318b7d0c4a9f58cc79453dfaaf0daf5b9a5c
ms.sourcegitcommit: b06a4f21da247edb03fdf6a01eafb7d4fb387b33
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48333898"
---
# <a name="form-processing-overview"></a>Overzicht formulierverwerking

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex maakt gebruik van de formulierverwerking van Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) om modellen te maken in SharePoint-documentbibliotheken.

U kunt de formulierverwerking van AI Builder gebruiken om AI-modellen te maken die gebruikmaken van machine-learningtechnologie om sleutel-waardeparen en tabelgegevens te identificeren en te extraheren uit gestructureerde of semi-gestructureerde documenten, zoals formulieren en facturen.

Organisaties ontvangen vaak grote hoeveelheden facturen afkomstig uit verschillende bronnen, zoals post, fax, e-mail, enzovoort. Het verwerken van deze documenten en het handmatig invoeren ervan in een database kan veel tijd in beslag nemen. Door kunstmatige intelligentie te gebruiken om de tekst, sleutel-waardeparen en tabellen uit uw documenten te halen, automatiseert de formulierverwerking dit proces. 

> [!NOTE]
> Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](https://docs.microsoft.com/microsoft-365/contentunderstanding/adoption-getstarted#form-processing-scenario-example) voor meer informatie over scenariovoorbeelden voor formulierverwerking.

U kunt bijvoorbeeld een formulierverwerkingsmodel maken dat alle inkooporderdocumenten identificeert die naar de documentbibliotheek worden geüpload. Vanuit elke inkooporder kunt u vervolgens specifieke belangrijke gegevens halen en weergeven, zoals *PO-nummer*, *Datum* en *Totale kosten*.

![Documentbibliotheekweergave](../media/content-understanding/doc-lib-done.png)</br>  

U kunt voorbeeldbestanden gebruiken om uw model te trainen en de informatie te definiëren die u uit het formulier wilt halen. De indeling van het document wordt geleerd door uw model te trainen. Het model leert hoe het gegevens uit soortgelijke locaties in uw formulieren kan halen, omdat die een vergelijkbare gestructureerde indeling hebben. 

U hebt minimaal vijf formulierdocumenten nodig om aan de slag te gaan. AI Builder analyseert uw voorbeeldbestanden voor sleutel-waardeparen en u identificeert vervolgens handmatig de items die niet zijn gedetecteerd.  Met AI Builder kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.

Nadat u het model hebt getraind en gepubliceerd, gebruikt u het om een [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) te maken die wordt uitgevoerd nadat een bestand is geüpload naar de SharePoint-documentbibliotheek. Vervolgens extraheert het de gegevens die zijn geïdentificeerd in het model. De geëxtraheerde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.

U gebruikt voorbeeldbestanden om uw model te trainen en de informatie te definiëren die u uit het formulier wilt halen. De indeling van het document wordt geleerd door het model te trainen. U hebt slechts vijf documenten nodig om aan de slag te gaan. AI Builder analyseert uw voorbeeldbestanden voor sleutel-waardeparen en u kunt ook handmatig de items identificeren die niet zijn gedetecteerd.  Met AI Builder kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.

Nadat u het model hebt getraind en gepubliceerd, maakt het model een [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started). Deze flow wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint -documentbibliotheek, waarbij de gegevens die zijn geïdentificeerd in het model worden geëxtraheerd. De geëxtraheerde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.

Een Office 365-beheerder moet [formulierverwerking inschakelen](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek, zodat gebruikers in staat zijn daarin een [formulierverwerkingsmodel te maken](create-a-form-processing-model.md).



## <a name="see-also"></a>Zie ook
  
[Power Automate-documentatie](https://docs.microsoft.com/power-automate/)

[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)

[Overzicht van documentbegrip](document-understanding-overview.md)

[Training: zakelijke prestaties verbeteren met AI-Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)
