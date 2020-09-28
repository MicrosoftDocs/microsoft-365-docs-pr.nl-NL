---
title: Overzicht van formulierverwerking
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
description: Meer informatie over het verwerken van formulieren in Microsoft SharePoint Syntex
ms.openlocfilehash: 518bc13017762bbe21420a81726e89c9c327834d
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295174"
---
# <a name="form-processing-overview-preview"></a>Overzicht van formulierverwerking (preview)

De inhoud in dit artikel is bedoeld voor de cortex van de private preview van project. [Lees meer over project cortex](https://aka.ms/projectcortex).

Project cortex gebruikt Microsoft PowerApps [AI Builder Builder](https://docs.microsoft.com/ai-builder/overview) -formulierverwerking voor het maken van modellen binnen SharePoint-documentbibliotheken.

U kunt de formulierverwerking van de AI-opbouwfunctie gebruiken om AI-modellen te maken die gebruikmaken van machine learning Technology om sleutel-/waardeparen te identificeren en te extraheren uit gestructureerd of gedeeltelijk gestructureerde documenten, zoals formulieren en facturen.

Gebruik de verwerking van AI Builder-formulieren om AI-modellen te maken die gebruikmaken van machine learning (ML) technologie om sleutel-/waardeparen te identificeren en te extraheren uit gestructureerde of gedeeltelijk gestructureerde documenten, zoals formulier en facturen.

Organisaties ontvangen vaak binnen grote hoeveelheden grote hoeveelheden, zoals e-mail, Fax, e-mail, etc. Door deze documenten te verwerken en handmatig in te voeren in een database, kan dit veel tijd in beslag nemen. Door AI te gebruiken om de tekst, sleutel-/waardeparen en tabellen van uw documenten uit te pakken, wordt dit proces geautomatiseerd door formulierverwerking. 

U kunt bijvoorbeeld een formulier verwerkings model maken waarin alle documenten voor de aankooporder worden aangegeven die worden geüpload naar de documentbibliotheek. Vanuit elke aankooporder kunt u vervolgens specifieke gegevens die belangrijk voor u zijn, extraheren en weergeven, zoals *ko-nummer*, *datum*of *totale kosten*.

U kunt ook voorbeeldbestanden gebruiken om uw model uit te leggen en te definiëren welke gegevens uit het formulier worden opgehaald. De lay-out van uw document wordt geleerd door een training voor uw model. U moet minimaal vijf formulier documenten maken om aan de slag te gaan. Met AI-samenstellen worden de voorbeeldbestanden geanalyseerd voor paren met sleutelwaarden en worden deze handmatig geïdentificeerd.  Met de AI-opbouwfunctie kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.

Nadat u uw model hebt ondertraind en gepubliceerd, kunt u het gebruiken om een [stroom](https://docs.microsoft.com/power-automate/getting-started) te maken die wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint-documentbibliotheek. Vervolgens haalt u de gegevens op die in het model zijn aangegeven. De opgehaalde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.

U gebruikt voorbeeldbestanden om uw model uit te leggen en te definiëren welke gegevens uit het formulier worden opgehaald. De lay-out van uw document wordt geleerd door een training voor uw model. U hebt maar vijf formulier documenten nodig om aan de slag te gaan. Met de functie AI-samenstellen worden de voorbeeldbestanden geanalyseerd voor de paren van sleutelwaarden en kunt u deze handmatig identificeren.  Met de AI-opbouwfunctie kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.

Wanneer u uw model hebt opgetraind en gepubliceerd, kunt u het gebruiken om een stroom [automatisering](https://docs.microsoft.com/power-automate/getting-started)te maken. De stroom wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint-documentbibliotheek en gegevens worden opgehaald die in het model zijn gevonden. De opgehaalde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.

Een beheerder van Office 365 moet de [formulierverwerking inschakelen](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek, zodat gebruikers [een formulier verwerkings model kunnen maken](create-a-form-processing-model.md) .

## <a name="see-also"></a>Zie ook
  
[De documentatie voor Power Automatiseer](https://docs.microsoft.com/power-automate/)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)</br>
[Overzicht van document](document-understanding-overview.md)</br>
[Training: bedrijfsprestaties verbeteren met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>
