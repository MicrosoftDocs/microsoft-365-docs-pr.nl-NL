---
title: Acties die in behandeling zijn, goedkeuren of weigeren na een geautomatiseerd onderzoek
description: Onderhoudscentrum gebruiken voor het beheren van acties met betrekking tot een automatisch onderzoek en antwoord
keywords: actie, centrum, autoair, automatisch, onderzoek, antwoord, herstel
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
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 09/16/2020
ms.openlocfilehash: ed0b9afa576f65d33cd9a49dfacd96ffaf173d28
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846530"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Acties die in behandeling zijn, goedkeuren of weigeren na een geautomatiseerd onderzoek

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Wanneer een geautomatiseerd onderzoek wordt uitgevoerd, kan dit resulteren in een of meer [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) die moeten worden goedgekeurd om verder te gaan. Als u bijvoorbeeld een cluster van e-mailberichten wilt verwijderen, of als u een bestand met quarantaine wilt verwijderen, moet u het bestand mogelijk verwijderen. Het is belangrijk dat u de in behandeling zijnde acties zo snel mogelijk goedkeurt (of afwijst), zodat uw geautomatiseerde onderzoek op een redelijke manier kan worden voortgezet en voltooid. 

> [!TIP]
> Laat het ons weten als u denkt dat er een probleem is opgetreden met een automatisch onderzoek en antwoord functies in Microsoft 365 Defender. Lees [hoe u in Microsoft 365 Defender onjuiste positieve en negatieve functies kunt melden voor automatisch onderzoek en Reacties (lucht)](mtp-autoir-report-false-positives-negatives.md).

Acties die in behandeling zijn, kunnen worden gecontroleerd en goedgekeurd met behulp van het [Onderhoudscentrum](#review-a-pending-action-in-the-action-center) of de [weergave Details van onderzoek](#review-a-pending-action-in-the-investigation-details-view).

> [!NOTE]
> U moet de [juiste machtigingen](mtp-action-center.md#required-permissions-for-action-center-tasks) hebben om herstelacties goed te keuren of te weigeren.

## <a name="review-a-pending-action-in-the-action-center"></a>Een actie in behandeling nakijken in het Actiecentrum

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies in het navigatiedeelvenster de optie **Onderhoudscentrum**. 

3. In het Actiecentrum selecteert u een item in de lijst op het tabblad **in behandeling** . 

    - Als u een item selecteert in de kolom **onderzoek nummer** , wordt de pagina Details van onderzoek geopend. Daar kunt u de resultaten van het onderzoek bekijken en de aanbevolen actie vervolgens goedkeuren of weigeren.
 
    - Als u een rij in de lijst selecteert, wordt er een flyout geopend waarin u informatie over dat item kunt weergeven. <br/>![Een actie goedkeuren of afwijzen](../../media/air-actioncenter-itemselected.png)<br/>Gebruik de koppelingen om een gekoppelde waarschuwing of een onderzoek te bekijken, en om de actie goed te keuren of te weigeren.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Een actie in behandeling nakijken in de weergave Details van onderzoek

![Details van onderzoek](../../media/mtp-air-investdetails.png)

1. Selecteer op de pagina [Details van onderzoek](mtp-autoir-results.md) het tabblad **acties in behandeling** (of **acties** ). Items die in behandeling zijn, worden hier weergegeven.

2. Selecteer een item in de lijst en kies vervolgens **goedkeuren** of **weigeren**.

## <a name="next-steps"></a>Volgende stappen

- [De details en resultaten van een geautomatiseerd onderzoek weergeven](mtp-autoir-results.md)
- [In-en uitzoomen op onjuiste positief en negatief onderzoek en antwoord mogelijkheden](mtp-autoir-report-false-positives-negatives.md)
