---
title: Overzicht van formulierverwerking (Voorbeeld)
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
description: Meer informatie over formulierverwerking in Project Cortex.
ms.openlocfilehash: 9709c8170f5dc6ce0edbeb2d90cb4e1f6d759c64
ms.sourcegitcommit: 3a47efcbdf3d2b39caa2798ea5be806839b05ed1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/01/2020
ms.locfileid: "46540056"
---
# <a name="form-processing-overview-preview"></a>Overzicht van formulierverwerking (Voorbeeld)
> [!Note]
> De inhoud in dit artikel is voor Project Cortex Private Preview. [Lees meer over Project Cortex](https://aka.ms/projectcortex).

Project Cortex gebruikt de formulierverwerking van Microsoft PowerApps [AI Builder](https://docs.microsoft.com/ai-builder/overview) om modellen te maken in SharePoint-documentbibliotheken.
U AI Builder-formulierverwerking gebruiken om AI-modellen te maken die machine learning-technologie gebruiken om paren met een sleutelwaarde en tabelgegevens te identificeren en te extraheren uit gestructureerde of semi-gestructureerde documenten, zoals formulier en facturen.

Bedrijven ontvangen facturen vaak in grote hoeveelheden en uit verschillende bronnen, zoals e-mail, fax, e-mail of persoonlijk. Het verwerken van deze documenten en het handmatig invoeren van deze documenten in uw database kan een aanzienlijke hoeveelheid tijd in beslag nemen. Door AI te gebruiken om de tekst, sleutel/waardeparen en tabellen uit uw documenten te extraheren, automatiseert formulierverwerking dit proces. 

U bijvoorbeeld een formulierverwerkingsmodel maken waarmee alle aankooporderdocumenten worden geïdentificeerd die naar de documentbibliotheek zijn geüpload. En uit elke inkooporder u specifieke gegevens extraheren en weergeven die voor u belangrijk zijn, zoals *PO-nummer,* *datum*of *totale kosten*.

U gebruikt voorbeeldbestanden om uw model te trainen en de informatie te definiëren die uit uw formulier moet worden gehaald. De lay-out van uw document wordt geleerd door uw model te trainen. Je hebt slechts vijf formulierdocumenten nodig om aan de slag te gaan. AI-gebouw analyseert uw voorbeeldbestanden voor paren met een sleutelwaarde en u ook handmatig bestanden identificeren die mogelijk niet zijn gedetecteerd.  Met AI-bouwer u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.

Nadat u uw model hebt getraind en gepubliceerd, maakt u een [Power Automate Flow](https://docs.microsoft.com/power-automate/getting-started) die wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint-documentbibliotheek en gegevens extrahert die in het model zijn geïdentificeerd. De uitgepakte gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.

Een Office 365-beheerder moet [formulierverwerking](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek inschakelen zodat gebruikers [er een formulierverwerkingsmodel](create-a-form-processing-model.md) in kunnen maken.



## <a name="see-also"></a>Zie ook
  
[Documentatie voor energie automatiseren](https://docs.microsoft.com/power-automate/)</br>
[Een formulierverwerkingsmodel maken](create-a-form-processing-model.md)</br>
[Overzicht van documentbegrip](document-understanding-overview.md)</br>
[Training: Verbeter de bedrijfsprestaties met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




