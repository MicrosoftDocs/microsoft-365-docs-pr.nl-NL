---
title: Herstelacties controleren en beheren in Microsoft Defender voor Office 365
keywords: AIR, autoIR, Microsoft Defender for Endpoint, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365 plan 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: f0c42bef1b090412a7a6422fe029323b645e90df
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275070"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Herstelacties controleren en beheren in Office 365

Aangezien geautomatiseerde onderzoeken op e-& samenwerkingsinhoud resulteren  in vonnissen, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt. In Microsoft Defender voor Office 365 kunnen herstelacties bestaan uit:
- Een URL blokkeren (time-of-click)
- E-mailberichten of clusters verwijderen
- E-mail- of e-mailbijlagen quarantining
- Externe e-mail doorsturen uitschakelen

Deze herstelacties worden alleen uitgevoerd als uw beveiligingsbewerkingsteam deze goedkeurt. We raden u aan alle lopende acties zo snel mogelijk te bekijken en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid. In sommige gevallen kunt u een herstelactie ongedaan maken.

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="approve-or-reject-pending-actions"></a>Acties in behandeling goedkeuren (of weigeren)

1. Ga naar het Microsoft 365 beveiligingscentrum ( <https://security.microsoft.com> ) en meld u aan.
2. Selecteer actiecentrum in het **navigatiedeelvenster.**
3. Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.
4. Selecteer een item in de lijst. Het deelvenster Flyout wordt geopend. 
5. Bekijk de informatie in het flyoutvenster en volg een van de volgende stappen:
   - Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.
   - Selecteer **Goedkeuren om** een actie in behandeling te starten.
   - Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.

## <a name="undo-one-remediation-action"></a>Eén herstelactie ongedaan maken

1. Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.
3. Selecteer Ongedaan maken in het deelvenster aan de rechterkant van **het scherm.**

## <a name="undo-multiple-remediation-actions"></a>Meerdere herstelacties ongedaan maken

1. Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken. Selecteer items met hetzelfde actietype. Er wordt een flyoutvenster geopend.
3. Selecteer Ongedaan maken in het deelvenster Flyout.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Een bestand verwijderen uit quarantaine op meerdere apparaten

1. Ga naar het Actiecentrum <https://security.microsoft.com/action-center> () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine**.
3. Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer **vervolgens Ongedaan maken.**

## <a name="next-steps"></a>Volgende stappen

- [Bedreigingsverkenner gebruiken](threat-explorer.md)
- [Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Zie ook

- [Details en resultaten van een geautomatiseerd onderzoek weergeven in Office 365](air-view-investigation-results.md)
