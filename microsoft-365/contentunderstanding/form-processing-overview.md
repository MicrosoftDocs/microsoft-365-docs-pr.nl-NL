---
title: Overzicht van formulierverwerking (preview)
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
description: Meer informatie over het verwerken van formulieren in Project cortex.
ms.openlocfilehash: 44ae5d9cbfbabc5615a751dba5f6c13290fc7b35
ms.sourcegitcommit: 57b37a3ce40f205c7320d5be1a0d906dd492b863
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/08/2020
ms.locfileid: "47405626"
---
# <a name="form-processing-overview-preview"></a>Overzicht van formulierverwerking (preview)
> [!Note]
> De inhoud in dit artikel is bedoeld voor project cortex private preview. [Lees meer over project cortex](https://aka.ms/projectcortex).

Project cortex gebruikt Microsoft PowerApps [AI Builder Builder](https://docs.microsoft.com/ai-builder/overview) -formulierverwerking voor het maken van modellen binnen SharePoint-documentbibliotheken.
U kunt de formulierverwerking van de AI-opbouwfunctie gebruiken om AI-modellen te maken die gebruikmaken van machine learning Technology om sleutel-/waardeparen te identificeren en te extraheren uit gestructureerd of gedeeltelijk gestructureerde documenten, zoals formulieren en facturen.

Bedrijven ontvangen vaak grote hoeveelheden en van diverse bronnen, zoals e-mail, Fax, e-mailadres of persoon. Door deze documenten te verwerken en handmatig in te voeren in de database, kan dit veel tijd in beslag nemen. Met AI voor het extraheren van de tekst, sleutel-/waardeparen en tabellen uit uw documenten, wordt dit proces door de formulierverwerking geautomatiseerd. 

U kunt bijvoorbeeld een formulier voor formulier verwerkings modellen maken waarmee alle documenten voor de aankooporders worden geïdentificeerd die worden geüpload naar de documentbibliotheek. Met een van de aankooporders kunt u specifieke gegevens die belangrijk voor u zijn, ophalen en weergeven, zoals *ko-nummer*, *datum*of *totale kosten*.

U gebruikt voorbeeldbestanden om uw model uit te leggen en te definiëren welke gegevens uit het formulier worden opgehaald. De lay-out van uw document wordt geleerd door een training voor uw model. U hebt maar vijf formulier documenten nodig om aan de slag te gaan. Met de AI-opbouwfunctie worden de voorbeeldbestanden geanalyseerd voor de paren met sleutelwaarden en kunt u deze handmatig identificeren.  Met de AI-opbouwfunctie kunt u de nauwkeurigheid van uw model testen op uw voorbeeldbestanden.

Wanneer u uw model hebt opgetraind en gepubliceerd, kunt u het gebruiken om een stroom [automatisering](https://docs.microsoft.com/power-automate/getting-started)te maken. De stroom wordt uitgevoerd wanneer een bestand wordt geüpload naar de SharePoint-documentbibliotheek en gegevens worden opgehaald die in het model zijn gevonden. De opgehaalde gegevens worden weergegeven in kolommen in de documentbibliotheekweergave van uw model.

Een beheerder van Office 365 moet de [formulierverwerking inschakelen](https://docs.microsoft.com/microsoft-365/contentunderstanding/set-up-content-understanding?view=o365-worldwide#to-set-up-content-understanding) voor de SharePoint-documentbibliotheek, zodat gebruikers [een formulier verwerkings model kunnen maken](create-a-form-processing-model.md) .



## <a name="see-also"></a>Zie ook
  
[De documentatie voor Power Automatiseer](https://docs.microsoft.com/power-automate/)</br>
[Een formulier verwerkings model maken](create-a-form-processing-model.md)</br>
[Overzicht van document](document-understanding-overview.md)</br>
[Training: bedrijfsprestaties verbeteren met AI Builder](https://docs.microsoft.com/learn/paths/improve-business-performance-ai-builder/?source=learn)</br>




