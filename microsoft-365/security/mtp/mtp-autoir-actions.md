---
title: Acties die in behandeling zijn na een geautomatiseerd onderzoek goedkeuren of weigeren
description: Het Actiecentrum gebruiken om acties te beheren met betrekking tot geautomatiseerd onderzoek en antwoorden
keywords: actie, center, autoair, geautomatiseerd, onderzoek, reactie, herstel
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
ms.date: 12/09/2020
ms.technology: m365d
ms.openlocfilehash: 3776dea4a5a24f4695a5c617325af14f1f03494f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930376"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>Acties die in behandeling zijn na een geautomatiseerd onderzoek goedkeuren of weigeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Wanneer een geautomatiseerd onderzoek wordt uitgevoerd, kan dit leiden tot een of meer [herstelacties](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions) waarvoor goedkeuring is vereist om verder te gaan. Bijvoorbeeld: een cluster e-mailberichten moet mogelijk worden verwijderd of een in quarantaine geplaatst bestand moet worden verwijderd. Het is belangrijk dat u acties in behandeling zo snel mogelijk goed (of afkeurt) zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid. 

> [!TIP]
> Als u denkt dat er iets is gemist of ten onrechte is gedetecteerd door geautomatiseerde onderzoeks- en antwoordfuncties in Microsoft 365 Defender, laat het ons dan weten. Zie Hoe u fout-positieven/negatieven rapporteert in mogelijkheden voor geautomatiseerd onderzoek en reactie [(AIR) in Microsoft 365 Defender.](mtp-autoir-report-false-positives-negatives.md)

Acties die in behandeling zijn, kunnen worden beoordeeld en goedgekeurd in het [Actiecentrum](#review-a-pending-action-in-the-action-center) of in de [weergave met details van het onderzoek.](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> U moet de [juiste machtigingen hebben om](mtp-action-center.md#required-permissions-for-action-center-tasks) herstelacties goed of af te keuren. Zie Vereisten voor geautomatiseerd onderzoek en antwoorden [in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)voor meer informatie.

## <a name="review-a-pending-action-in-the-action-center"></a>Een actie in behandeling controleren in het Actiecentrum

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 

2. Kies Actiecentrum in het **navigatiedeelvenster.** 

3. Selecteer een item in de lijst in **het** actiecentrum op het tabblad In behandeling. 

    - Als u een item selecteert in de kolom **Voor onderzoek,** wordt de pagina met details van het onderzoek geopend. Daar kunt u de resultaten van het onderzoek bekijken en vervolgens de aanbevolen actie goedkeuren of weigeren.
 
    - Als u een rij in de lijst selecteert, wordt een flyout geopend waarin u informatie over dat item kunt bekijken. <br/>![Een actie goedkeuren of weigeren](../../media/air-actioncenter-itemselected.png)<br/>Gebruik de koppelingen om een bijbehorende waarschuwing of een onderzoek weer te geven en de actie goed of af te keuren.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>Een actie in behandeling bekijken in de weergave details van het onderzoek

![Details van onderzoek](../../media/mtp-air-investdetails.png)

1. Selecteer op [een detailpagina voor](mtp-autoir-results.md) onderzoek het tabblad **Acties** in behandeling. Items die nog moeten worden goedgekeurd, worden hier weergegeven.

2. Selecteer een item in de lijst en kies Vervolgens **Goedkeuren** of **Weigeren.**

## <a name="undo-completed-actions"></a>Voltooide acties ongedaan maken

Als u hebt vastgesteld dat een apparaat of bestand geen bedreiging is, kunt u herstelacties ongedaan maken die zijn gemaakt, ongeacht of deze acties automatisch of handmatig zijn gemaakt. In het actiecentrum kunt u op het **tabblad Geschiedenis** de volgende acties ongedaan maken:  

| Actiebron | Ondersteunde acties |
|:---|:---|
| - Automatisch onderzoek <br/>- Microsoft Defender Antivirus <br/>- Acties voor handmatige antwoorden | - Apparaat isoleren <br/>- Uitvoering van code beperken <br/>- Een bestand in quarantaine plaatsen <br/>- Een registersleutel verwijderen <br/>- Een service stoppen <br/>- Een stuurprogramma uitschakelen <br/>- Een geplande taak verwijderen |

### <a name="to-undo-a-remediation-action"></a>Een herstelactie ongedaan maken

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.

2. Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.

3. Selecteer Ongedaan maken in het deelvenster aan de rechterkant van het **scherm.**

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Een bestand uit quarantaine verwijderen op meerdere apparaten 

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.

2. Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine.**

3. Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand op Toepassen op **X** en selecteer vervolgens **Ongedaan maken.**

## <a name="next-steps"></a>Volgende stappen

- [De details en resultaten van een geautomatiseerd onderzoek weergeven](mtp-autoir-results.md)
- [Fout-positieven/negatieven in geautomatiseerde onderzoeks- en antwoordmogelijkheden verwerken](mtp-autoir-report-false-positives-negatives.md)
