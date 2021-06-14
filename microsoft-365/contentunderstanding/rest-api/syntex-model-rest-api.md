---
title: REST API voor model voor documentbegrip in SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: reference
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: m365initiative-syntex
localization_priority: Priority
description: Overzicht van de REST API voor model voor documentbegrip in SharePoint Syntex.
ms.openlocfilehash: e661df76828db0d05f7c3492880259117b9f8bf1
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908087"
---
# <a name="sharepoint-syntex-document-understanding-model-rest-api"></a>REST API voor model voor documentbegrip in SharePoint Syntex

U kunt de SharePoint REST-interface gebruiken om een model voor documentbegrip te maken, om het model toe te passen op of te verwijderen uit een of meer bibliotheken, en om informatie over het model op te halen of bij te werken. 

De SharePoint Online (en SharePoint 2016 en hoger on-premises) REST-service ondersteunt het combineren van meerdere aanvragen tot één oproep aan de service met behulp van de optie OData $batch query. 

Zie voor meer informatie en koppelingen naar codevoorbeelden [Batchaanvragen maken met de REST API's](/sharepoint/dev/sp-add-ins/make-batch-requests-with-the-rest-apis).

## <a name="prerequisites"></a>Vereisten

Zorg ervoor dat u bekend bent met het volgende voordat u aan de slag gaat:

- [De SharePoint REST-service leren kennen](/sharepoint/dev/sp-add-ins/get-to-know-the-sharepoint-rest-service) 
- [Basisbewerkingen uitvoeren met SharePoint REST-eindpunten](/sharepoint/dev/sp-add-ins/complete-basic-operations-using-sharepoint-rest-endpoints)

## <a name="rest-commands"></a>REST-opdrachten

De volgende REST-opdrachten zijn beschikbaar voor het werken met Syntex-modellen voor documentbegrip:

- [Model maken](rest-createmodel-method.md): maakt een model en het gekoppelde inhoudstype.
- [GetByUniqueId](rest-getbyuniqueid-method.md): ontvangt of werkt informatie bij over een SharePoint Syntex-model voor documentbegrip.
- [GetByUniqueId](rest-getbytitle-method.md): ontvangt of werkt informatie bij over een SharePoint Syntex-model voor documentbegrip met behulp van de modeltitel.
- [Model toepassen](rest-applymodel-method.md): past (of synchroniseert) een getraind model voor documentbegrip toe op een of meer bibliotheken.
- [Informatie over model- en bibliotheekgegevens](rest-getmodelandlibraryinfo.md) : informatie over een model en de bibliotheek waar het is toegepast.
- [UpdateModelSettings](rest-updatemodelsettings-method.md): hiermee worden de beschikbare modelinstellingen (gekoppeld bewaarlabel en modelbeschrijving) bijgewerkt voor een SharePoint Syntex-model voor documentbegrip.
- [BatchDelete](rest-batchdelete-method.md): hiermee verwijdert u een toegepast model met documentbegrip uit een of meer bibliotheken.
- [Classificatieaanvraag maken](rest-createclassificationrequest.md): hiermee maakt u een aanvraag voor het classificeren van een opgegeven bestand of bestanden met behulp van het toegepaste model.

## <a name="scenarios"></a>Scenario's

Let op de volgende scenariovoorbeelden die geen intuïtieve methodenaam hebben. Raadpleeg dit artikel voor meer informatie.

Met de methode Model maken worden alleen het modelobject en het bijbehorende inhoudstype gemaakt. U moet het model eerst trainen in het inhoudscentrum voordat het op een bibliotheek kan worden toegepast.

De methode Model toepassen wordt gebruikt om het model in de doelbibliotheek zo te configureren dat documenten worden geclassificeerd en eventueel aanvullende informatie kan worden geëxtraheerd. Deze API ondersteunt ook het batchgewijs toepassen van het model op meerdere bibliotheken.

Met de methode Model verwijderen wordt het model alleen verwijderd uit een of meer bibliotheken waar het eerder is toegepast. Als u het model wilt verwijderen, moet het eerst worden verwijderd uit alle bibliotheken waar het is toegepast.


## <a name="see-also"></a>Zie ook

[Overzicht van documentbegrip](../document-understanding-overview.md)

