---
title: Details en resultaten van een geautomatiseerd onderzoek
description: Tijdens en na een geautomatiseerd onderzoek u de resultaten en de belangrijkste bevindingen
keywords: geautomatiseerd, onderzoek, resultaten, analyseren, details, sanering, autoair
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
ms.openlocfilehash: 6b3bc068e5da99e02a64463891e32d137c448d64
ms.sourcegitcommit: 133bf7936e5ef1a4d06998429d0d01096bda929f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42805916"
---
# <a name="details-and-results-of-an-automated-investigation"></a>Details en resultaten van een geautomatiseerd onderzoek

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

Wanneer een geautomatiseerd onderzoek plaatsvindt in Microsoft Threat Protection, zijn details over dat onderzoek beschikbaar tijdens en na het geautomatiseerde onderzoeksproces. Als u over de [benodigde machtigingen beschikt,](mtp-action-center.md#required-permissions-for-action-center-tasks)u deze gegevens bekijken in een weergave met onderzoeksdetails. De weergave Onderzoeksgegevens biedt u een up-to-date status en de mogelijkheid om lopende acties goed te keuren. 

![Details van het onderzoek](../../media/mtp-air-investdetails.png)

## <a name="open-the-investigation-details-view"></a>De weergave Onderzoeksdetails openen

U de weergave onderzoeksgegevens openen met behulp van een van de volgende methoden:
- [Een item selecteren in het onderhoudscentrum](#select-an-item-in-the-action-center)
- [Een onderzoek selecteren op een pagina met informatie over incidenten](#open-an-investigation-from-an-incident-details-page)

### <a name="select-an-item-in-the-action-center"></a>Een item selecteren in het onderhoudscentrum

Gebruik het actiecentrum om acties weer te geven die in behandeling zijn (op het tabblad **In behandeling)** of die al zijn goedgekeurd (op het tabblad **Geschiedenis).** 

1. Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan. 

2. Kies in het navigatiedeelvenster **het onderhoudscentrum**. 

3. Selecteer op het tabblad **Inbehandeling** of **Geschiedenis** een item. Als u over de [benodigde machtigingen beschikt,](mtp-action-center.md#required-permissions-for-action-center-tasks)u lopende acties goedkeuren (of afwijzen).

### <a name="open-an-investigation-from-an-incident-details-page"></a>Een onderzoek openen vanaf een pagina met informatie over incidenten

Gebruik een pagina met incidentgegevens om gedetailleerde informatie over een incident weer te geven, inclusief waarschuwingen die zijn geactiveerd voor informatie over getroffen apparaten, gebruikersaccounts of postvakken.

1. Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan. 

2. Kies **incidenten**in het navigatiedeelvenster. 

3. Selecteer een item in de lijst om de weergave incidentdetails te openen.<br/>![Incidentdetails](../../media/mtp-incidentdetails-tabs.png)

4. Selecteer op het tabblad **Onderzoeken** een onderzoek in de lijst.

## <a name="investigation-details"></a>Details van het onderzoek

Gebruik de weergave Onderzoeksgegevens om eerdere, huidige en in behandeling zijnde activiteiten met betrekking tot een onderzoek te bekijken. De weergave Onderzoeksdetails lijkt op de volgende afbeelding:

![Details van het onderzoek](../../media/mtp-air-investdetails.png)

In de weergave Onderzoekdetails u informatie zien in de grafiek **Onderzoek**, **Waarschuwingen**, **Apparaten**, **Identiteiten**, **Belangrijkste bevindingen**, **Entiteiten,** **Logboek**en In **behandeling zijnde acties,** beschreven in de volgende tabel.

|Tab    |Beschrijving |
|--------|--------|
|Onderzoeksgrafiek    |Geeft een visuele weergave van het onderzoek. Hiermee worden entiteiten en lijsten weergegeven die worden gevonden, samen met waarschuwingen en of acties wachten op goedkeuring.<br/>U op een item in de grafiek klikken om meer details weer te geven. Als u bijvoorbeeld op het pictogram **Bedreigingen hebt gevonden,** gaat u naar het tabblad **Belangrijkste bevindingen.** |
|Waarschuwingen |Geeft lijsten met waarschuwingen die aan het onderzoek zijn gekoppeld. Waarschuwingen kunnen afkomstig zijn van functies voor bedreigingsbeveiliging op de machine van een gebruiker, in Office-apps, Cloud App-beveiliging en andere functies voor bedreigingsbeveiliging van Microsoft 365.|
|Apparaten|Lijsten machines die in het onderzoek zijn opgenomen, samen met het saneringsniveau.|
|Belangrijkste bevindingen   |Geeft een overzicht van de resultaten van het onderzoek, samen met de status en de genomen acties of in behandeling zijnde. U lopende acties voor apparaten en identiteiten op dit tabblad goedkeuren.|
|Entiteiten   |Hiermee worden gebruikersactiviteiten, bestanden, processen, services, stuurprogramma's, IP-adressen en persistentiemethoden weergegeven die aan het onderzoek zijn gekoppeld, samen met de status en de genomen acties.|
|Log    |Geeft een gedetailleerd overzicht van alle stappen die tijdens het onderzoek zijn genomen, samen met de status.|
|Lopende acties    |Hiermee worden items weergegeven waarvoor goedkeuring nodig is.|

## <a name="next-steps"></a>Volgende stappen

- [Een overzicht van machtigingen voor het actiecentrum](mtp-action-center.md#required-permissions-for-action-center-tasks)

- [Acties in verband met geautomatiseerd onderzoek en respons goedkeuren of afwijzen](mtp-autoir-actions.md)

