---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Tijdens en na een geautomatiseerd onderzoek kunt u de resultaten en de belangrijkste resultaten bekijken
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, details, herstel, autoair
search.appverid: met150
ms.prod: m365-security
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.technology: m365d
ms.openlocfilehash: c050683bb3ed052ae4752ffdee66fe51fb99b88b
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930364"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Details en resultaten van een geautomatiseerd onderzoek

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Wanneer een geautomatiseerd onderzoek plaatsvindt in Microsoft 365 Defender, zijn details over dat onderzoek beschikbaar tijdens en na het proces van geautomatiseerd onderzoek. Als u de [benodigde machtigingen hebt,](mtp-action-center.md#required-permissions-for-action-center-tasks)kunt u deze details bekijken in een weergave met details van het onderzoek. De detailweergave voor onderzoek bevat de actuele status en de mogelijkheid om acties die in behandeling zijn goed te keuren. 

![Details van onderzoek](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>De weergave met onderzoeksgegevens openen

U kunt de weergave met onderzoeksgegevens op een van de volgende manieren openen:
- [Een item selecteren in het Actiecentrum](#select-an-item-in-the-action-center)
- [Een onderzoek selecteren op een pagina met incidentdetails](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Een item selecteren in het Actiecentrum

Gebruik het Actiecentrum om acties weer te  geven die in behandeling zijn (op het tabblad In behandeling) of die al zijn goedgekeurd (op het **tabblad** Geschiedenis). 

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies Actiecentrum in het **navigatiedeelvenster.** 

3. Selecteer een item **op het** tabblad In behandeling **of** Geschiedenis. Als u de [benodigde machtigingen hebt,](mtp-action-center.md#required-permissions-for-action-center-tasks)kunt u acties in behandeling goedkeuren (of weigeren).

### <a name="open-an-investigation-from-an-incident-details-page"></a>Een onderzoek openen vanaf een pagina met details van een incident

Gebruik een pagina met incidentgegevens om gedetailleerde informatie over een incident weer te geven, inclusief waarschuwingen die informatie hebben geactiveerd over getroffen apparaten, gebruikersaccounts of postvakken.

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies Incidenten in het **navigatiedeelvenster.** 

3. Selecteer een item in de lijst om de weergave met details van het incident te openen.<br/>![Details van incident](../../media/mtp-incidentdetails-tabs.png)

4. Selecteer op **het tabblad Onderzoeken** een onderzoek in de lijst.

## <a name="investigation-details"></a>Details van onderzoek

Gebruik de weergave met onderzoeksgegevens om activiteiten uit het verleden, de huidige en in behandeling die betrekking hebben op een onderzoek te bekijken. De weergave met onderzoeksgegevens lijkt op de volgende afbeelding:

![Details van onderzoek](../../media/mtp-air-investdetails.png)

In de weergave Details van onderzoek kunt u informatie zien in de grafiek Onderzoek,  **Waarschuwingen,**  **Apparaten,** **Identiteiten,** Belangrijkste **bevindingen,** Entiteiten, **Logboek** en Acties in behandeling, die in de volgende tabel worden beschreven.

| Tab | Beschrijving |
|--------|--------|
| **Onderzoeksgrafiek**   | Biedt een visuele weergave van het onderzoek. Hiermee worden entiteiten en lijsten met gevonden bedreigingen weergegeven, samen met waarschuwingen en of er acties wachten op goedkeuring.<br/>U kunt op een item in de grafiek klikken om meer details weer te geven. Als u bijvoorbeeld op het pictogram **Bedreigingen gevonden** klikt, gaat u naar het tabblad **Belangrijke resultaten.** |
| **Waarschuwingen**    | Hier worden waarschuwingen vermeld die aan het onderzoek zijn gekoppeld. Waarschuwingen kunnen afkomstig zijn van functies voor risicobeveiliging op de computer van een gebruiker, in Office-apps, Cloud App-beveiliging en andere functies van Microsoft 365 Defender.|
| **Apparaten** | Vermeldt machines die zijn opgenomen in het onderzoek, samen met het herstelniveau.|
| **Belangrijkste resultaten**  | Hier vindt u de resultaten van het onderzoek, samen met de status en acties die zijn ondernomen of in behandeling zijn. U kunt acties in behandeling goedkeuren voor apparaten en identiteiten op dit tabblad.|
| **Entiteiten**  | Bevat gebruikersactiviteiten, bestanden, processen, services, stuurprogramma's, IP-adressen en persistentiemethoden die aan het onderzoek zijn gekoppeld, samen met de status en de ondernomen acties.|
|**Logboek**    | Biedt een gedetailleerde weergave van alle stappen die zijn ondernomen tijdens het onderzoek, samen met de status.|
| **Acties in behandeling** | Hier worden items vermeld waarvoor goedkeuring is vereist om verder te gaan.|

## <a name="next-steps"></a>Volgende stappen

- [Acties met betrekking tot geautomatiseerd onderzoek en antwoorden goedkeuren of weigeren](mtp-autoir-actions.md)
- [Herstelacties bekijken](mtp-remediation-actions.md)
