---
title: Acties weergeven en beheren in het actiecentrum
description: Het actiecentrum gebruiken om herstelacties weer te zien en te beheren
keywords: actie, center, autoair, geautomatiseerd, onderzoek, antwoord, herstel
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
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 01/29/2021
ms.technology: m365d
ms.openlocfilehash: fe2c3d4112663b4046a9d503aefc45f832c6c143
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/08/2021
ms.locfileid: "50917102"
---
# <a name="view-and-manage-actions-in-the-action-center"></a>Acties weergeven en beheren in het actiecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

Bedreigingsbeveiligingsfuncties in Microsoft 365 Defender kunnen leiden tot bepaalde herstelacties. Dit zijn enkele voorbeelden:
- [Geautomatiseerde onderzoeken kunnen](mtp-autoir.md) leiden tot herstelacties die automatisch worden ondernomen of die moeten worden goedgekeurd.
- Antivirus-, antimalware- en andere functies voor bedreigingsbeveiliging kunnen leiden tot herstelacties, zoals het blokkeren van een bestand, URL of proces of het verzenden van een artefact naar quarantaine.
- Uw beveiligingsteam kan handmatig herstelacties uitvoeren, zoals [](advanced-hunting-overview.md) tijdens geavanceerde zoekacties of tijdens het onderzoeken van [waarschuwingen](investigate-alerts.md) of [incidenten.](investigate-incidents.md)

> [!NOTE]
> U moet de [juiste machtigingen hebben om](mtp-action-center.md#required-permissions-for-action-center-tasks) herstelacties goed te keuren of te weigeren. Zie Vereisten voor geautomatiseerd onderzoek en antwoord [in Microsoft 365 Defender](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)voor meer informatie.

## <a name="review-pending-actions-in-the-action-center"></a>Acties in behandeling bekijken in het Actiecentrum

Het is belangrijk om acties in behandeling zo snel mogelijk goed te keuren (of af te wijzen), zodat uw geautomatiseerde onderzoeken tijdig kunnen worden uitgevoerd en voltooid. 

![Een actie goedkeuren of weigeren](../../media/air-actioncenter-itemselected.png)

1. Ga naar [https://security.microsoft.com](https://security.microsoft.com) en meld u aan. 
2. Kies actiecentrum in het **navigatiedeelvenster.** 
3. Selecteer in het Actiecentrum **op** het tabblad In behandeling een item in de lijst. Het deelvenster Flyout wordt geopend.
4. Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:
   - Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.
   - Selecteer **Goedkeuren om** een actie in behandeling te starten.
   - Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.
   - Selecteer **Ga op zoek om** naar Geavanceerd zoeken te [gaan.](advanced-hunting-overview.md) 

## <a name="undo-completed-actions"></a>Voltooide acties ongedaan maken

Als u hebt vastgesteld dat een apparaat of bestand geen bedreiging is, kunt u herstelacties ongedaan maken die zijn ondernomen, ongeacht of deze acties automatisch of handmatig zijn ondernomen. In het actiecentrum op het tabblad **Geschiedenis** kunt u een van de volgende acties ongedaan maken:  

| Actiebron | Ondersteunde acties |
|:---|:---|
| - Geautomatiseerd onderzoek <br/>- Microsoft Defender Antivirus <br/>- Handmatige antwoordacties | - Apparaat isoleren <br/>- Codeuitvoering beperken <br/>- Een bestand in quarantaine plaatsen <br/>- Een registersleutel verwijderen <br/>- Een service stoppen <br/>- Een stuurprogramma uitschakelen <br/>- Een geplande taak verwijderen |

### <a name="undo-one-remediation-action"></a>Eén herstelactie ongedaan maken

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.
3. Selecteer Ongedaan maken in het deelvenster aan de rechterkant van **het scherm.**

### <a name="undo-multiple-remediation-actions"></a>Meerdere herstelacties ongedaan maken

1. Ga naar het Actiecentrum ( https://security.microsoft.com/action-center) en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken. Selecteer items met hetzelfde actietype. Er wordt een flyoutvenster geopend.
3. Selecteer ongedaan maken in het deelvenster Flyout.

### <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Een bestand verwijderen uit quarantaine op meerdere apparaten 

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine**.
3. Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.**

## <a name="next-steps"></a>Volgende stappen

- [De details en resultaten van een geautomatiseerd onderzoek weergeven](mtp-autoir-results.md)
- [Meer informatie over het verwerken van onwaar positieven/negatieven (als u er een krijgt)](mtp-autoir-report-false-positives-negatives.md)
