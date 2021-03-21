---
title: Overzicht formulierverwerking
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
description: Informatie over formulierverwerking in Microsoft SharePoint Syntex
ms.openlocfilehash: 84aeb7c4e3fc850e5e4c2336e576ff3bce3ecf4b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928306"
---
# <a name="form-processing-overview"></a>Overzicht formulierverwerking

 ![AI Builder](../media/content-understanding/ai-builder.png)</br>

Microsoft SharePoint Syntex maakt gebruik van de formulierverwerking van Microsoft PowerApps [AI Builder](/ai-builder/overview) om modellen te maken in SharePoint-documentbibliotheken.

U kunt de formulierverwerking van AI Builder gebruiken om AI-modellen te maken die gebruikmaken van machine-learningtechnologie om sleutel-waardeparen en tabelgegevens te identificeren en te extraheren uit gestructureerde of semi-gestructureerde documenten, zoals formulieren en facturen.

Organisaties ontvangen vaak grote hoeveelheden facturen afkomstig uit verschillende bronnen, zoals post, fax, e-mail, enzovoort. Het verwerken van deze documenten en het handmatig invoeren ervan in een database kan veel tijd in beslag nemen. Door kunstmatige intelligentie te gebruiken om de tekst, sleutel-waardeparen en tabellen uit uw documenten te halen, automatiseert de formulierverwerking dit proces. 

> [!NOTE]
> Zie [Ingebruikname van SharePoint Syntex: introductiehandleiding](./adoption-getstarted.md#form-processing-scenario-example) voor meer informatie over scenariovoorbeelden voor formulierverwerking.

U kunt bijvoorbeeld een formulierverwerkingsmodel maken dat alle inkooporderdocumenten identificeert die naar de documentbibliotheek worden geüpload. Vanuit elke inkooporder kunt u vervolgens specifieke belangrijke gegevens halen en weergeven, zoals *PO-nummer*, *Datum* en *Totale kosten*.

![Documentbibliotheekweergave](../media/content-understanding/doc-lib-done.png)</br>  

U gebruikt voorbeeldbestanden om uw model te trainen en de informatie te definiëren die u uit het formulier wilt halen. De indeling van het document wordt geleerd door het model te trainen. U hebt slechts vijf documenten nodig om aan de slag te gaan. AI Builder analyseert uw voorbeeldbestanden voor sleutel-waardeparen en u kunt ook handmatig de items identificeren die niet zijn gedetecteerd.  Met AI Builder kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.

Nadat u het model hebt getraind en gepubliceerd, maakt het model een [Power Automate Flow](/power-automate/getting-started). Deze flow wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint -documentbibliotheek, waarbij de gegevens die zijn geïdentificeerd in het model worden geëxtraheerd. De geëxtraheerde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.

Een Office 365-beheerder moet [formulierverwerking inschakelen](./set-up-content-understanding.md#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek, zodat gebruikers in staat zijn daarin een [formulierverwerkingsmodel te maken](create-a-form-processing-model.md). Je kunt de sites selecteren tijdens de installatie of na de configuratie van de beheerinstellingen.

### <a name="file-limitations"></a>Bestandbeperkingen

Als je formulierverwerkingsmodellen gebruikt, let dan op de [vereisten en beperkingen voor bestandgebruik](/ai-builder/form-processing-model-requirements).

### <a name="multi-geo-environments"></a>Multi-geo-omgevingen

Bij het instellen van SharePoint Syntex in een [Microsoft 365 Multi-Geo-omgeving](../enterprise/microsoft-365-multi-geo.md), kunt u het alleen configureren voor het gebruik van formulierverwerking op de centrale locatie. Als u de formulierverwerking op een satellietlocatie wilt gebruiken, neem dan contact op met Microsoft-ondersteuning.






## <a name="see-also"></a>Zie ook
  
[Power Automate-documentatie](/power-automate/)

[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)

[Overzicht van documentbegrip](document-understanding-overview.md)

[Training: zakelijke prestaties verbeteren met AI-Builder](/learn/paths/improve-business-performance-ai-builder/?source=learn)