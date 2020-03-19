---
title: In behandeling zijnde acties goedkeuren of afwijzen na een geautomatiseerd onderzoek
description: Het Onderhoudscentrum gebruiken om acties te beheren met betrekking tot geautomatiseerd onderzoek en respons
keywords: actie, centrum, autoair, geautomatiseerd, onderzoek, respons, sanering
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
ms.openlocfilehash: 725d22629d2c81a0edf8f329602214afddde6511
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808464"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>In behandeling zijnde acties goedkeuren of afwijzen na een geautomatiseerd onderzoek

**Van toepassing op:**
- Microsoft-bedreigingsbeveiliging

Wanneer een geautomatiseerd onderzoek wordt uitgevoerd, kan dit resulteren in een of meer [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) waarvoor goedkeuring nodig is. Een cluster van e-mailberichten moet bijvoorbeeld worden verwijderd of een bestand in quarantaine moet mogelijk worden verwijderd. Het is belangrijk om in afwachting van acties zo snel mogelijk goed te keuren (of af te wijzen), zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid. 

> [!TIP]
> Als u denkt dat er iets is gemist of verkeerd is gedetecteerd door geautomatiseerde onderzoeks- en reactiefuncties in Microsoft Threat Protection, laat het ons dan weten! Zie [Hoe valse positieven/negatieven in geautomatiseerde onderzoeks- en reactiemogelijkheden (AIR) kunnen worden gemeld in Microsoft Threat Protection.](mtp-autoir-report-false-positives-negatives.md)

Lopende acties kunnen worden beoordeeld en goedgekeurd met behulp van het [actiecentrum](#review-a-pending-action-in-the-action-center) of de [weergave onderzoeksdetails](#review-a-pending-action-in-the-investigation-details-view).

> [!NOTE]
> U moet [over de juiste machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks) beschikken om herstelacties goed te keuren of af te wijzen.

## <a name="review-a-pending-action-in-the-action-center"></a>Een actie in behandeling controleren in het actiecentrum

1. Ga [https://security.microsoft.com](https://security.microsoft.com) naar en meld je aan. 

2. Kies In het navigatiedeelvenster de optie **Actiecentrum**. 

3. Selecteer in het Onderhoudscentrum op het tabblad **In behandeling** een item in de lijst. 

    - Als u een item selecteert in de kolom **Onderzoeksnummer,** wordt de pagina met onderzoeksdetails geopend. Daar u de resultaten van het onderzoek bekijken en vervolgens de aanbevolen actie goedkeuren of afwijzen.
 
    - Als u een rij in de lijst selecteert, wordt er een flyout geopend, waar u informatie over dat item bekijken. <br/>![Een actie goedkeuren of afwijzen](../../media/air-actioncenter-itemselected.png)<br/>Gebruik de koppelingen om een bijbehorende waarschuwing of een onderzoek weer te geven en de actie goed te keuren of af te wijzen.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Een lopende actie in de weergave onderzoeksdetails bekijken

![Onderzoeksdetails](../../media/mtp-air-investdetails.png)

1. Selecteer op een pagina [met onderzoeksdetails](mtp-autoir-results.md) het tabblad **In behandeling zijnde acties** (of **Acties).**

2. Selecteer een item in de lijst en kies **Goedkeuren** of **Weigeren**.

## <a name="next-steps"></a>Volgende stappen

- [Meer informatie over het actiecentrum](mtp-action-center.md)

- [Meer informatie over incidenten](incidents-overview.md)

- [Meer informatie over jagen](advanced-hunting-overview.md)
