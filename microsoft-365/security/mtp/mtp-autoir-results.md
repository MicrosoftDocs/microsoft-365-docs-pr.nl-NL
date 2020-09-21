---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Wanneer u een geautomatiseerde onderzoek doet, kunt u de resultaten en de belangrijkste bevindingen bekijken
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, Details, herbemiddeling, autoair
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: 62d33c57606aad81607164b1f068c6f6d91063c2
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962297"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Details en resultaten van een geautomatiseerd onderzoek

**Van toepassing op:**
- Microsoft Threat Protection

Wanneer er een geautomatiseerd onderzoek plaatsvindt in Microsoft Threat Protection, is er informatie over dat onderzoek beschikbaar via en na het geautomatiseerde onderzoek proces. Als u de [benodigde machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks)hebt, kunt u deze gegevens bekijken in de weergave Details van onderzoek. De weergave onderzoek Details biedt u de actuele status en de mogelijkheid om alle in behandeling zijnde acties goed te keuren. 

![Details van onderzoek](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>De weergave onderzoek Details openen

U kunt de weergave Details van onderzoek op een van de volgende manieren openen:
- [Selecteer een item in het Actiecentrum](#select-an-item-in-the-action-center)
- [Selecteer een onderzoek op de pagina Details van incident](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Selecteer een item in het Actiecentrum

Gebruik het Actiecentrum om acties weer te geven die goedkeuring in behandeling zijn (op het tabblad **in behandeling** ) of die al is goedgekeurd (op het tabblad **geschiedenis** ). 

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies in het navigatiedeelvenster de optie **Onderhoudscentrum**. 

3. Selecteer een item op het tabblad **Onverwerkt** of **geschiedenis** . Als u over de [juiste machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks)beschikt, kunt u acties die in behandeling zijn, goedkeuren of weigeren.

### <a name="open-an-investigation-from-an-incident-details-page"></a>Een onderzoek openen op de pagina Details van incident

Gebruik een pagina met incident Details om gedetailleerde informatie over een incident te bekijken, waaronder waarschuwingen die informatie hebben geactiveerd over de betreffende apparaten, gebruikersaccounts of postvakken.

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies in het navigatiedeelvenster de optie **incidenten**. 

3. Selecteer een item in de lijst om de weergave incident details te openen.<br/>![Details van incident](../../media/mtp-incidentdetails-tabs.png)

4. Selecteer op het tabblad **onderzoek** een onderzoek in de lijst.

## <a name="investigation-details"></a>Details van onderzoek

U kunt de weergave Details van onderzoek gebruiken om eerdere, huidige en activiteiten activiteiten te zien die betrekking hebben op een onderzoek. De weergave onderzoek Details lijkt op de volgende afbeelding:

![Details van onderzoek](../../media/mtp-air-investdetails.png)

In de weergave Details van onderzoek kunt u informatie weergeven over de tabbladen **onderzoek grafiek**, **waarschuwingen**, **apparaten**, **identiteiten**, **belangrijke bevindingen**, **entiteiten**, **Logboeken**en **acties in behandeling** , zoals in de volgende tabel wordt beschreven.

|Tabblad    |Beschrijving |
|--------|--------|
|Onderzoek grafiek    |Geeft een visuele voorstelling van het onderzoek. Geeft een voorbeeld weer van de weergave van de bedreigingen en lijsten<br/>U kunt op een item in de grafiek klikken om meer informatie weer te geven. Als u bijvoorbeeld op het pictogram **bedreigingen gevonden** klikt, gaat u naar het tabblad **belangrijkste bevindingen** . |
|Waarschuwingen |Hier vindt u een overzicht van de waarschuwingen bij het onderzoek. Waarschuwingen zijn afkomstig van functies voor bedreigingsbeveiliging op de computer van een gebruiker, in Office-apps, de beveiliging van Cloud apps en andere functies van Microsoft 365 Threat Protection.|
|Apparaten|Lijst met machines die in het onderzoek zijn opgenomen, samen met het herstelniveau.|
|Belangrijkste bevindingen   |Dit bevat een overzicht van de resultaten van het onderzoek samen met de status en de beschikbare acties of in behandeling. Op dit tabblad kunt u acties in behandeling voor apparaten en identiteiten goedkeuren.|
|Onderzoeksinstellingen   |Hier vindt u een lijst van gebruikersactiviteiten, bestanden, processen, services, Stuurprogramma's, IP-adressen, en permanente methoden voor het onderzoek, en over de status van de uitgevoerde acties.|
|Inloggen    |Een gedetailleerde weergave van alle stappen die tijdens het onderzoek zijn verricht, en de status.|
|Acties in behandeling    |Een lijst met items die moeten worden goedgekeurd om te worden voortgezet.|

## <a name="next-steps"></a>Volgende stappen

- [Acties met betrekking tot een automatisch onderzoek en antwoord goedkeuren of afwijzen](mtp-autoir-actions.md)

