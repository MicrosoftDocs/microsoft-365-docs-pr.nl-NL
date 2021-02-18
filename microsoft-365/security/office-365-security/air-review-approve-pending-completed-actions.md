---
title: Herstelacties in Microsoft Defender voor Office 365 bekijken en beheren
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
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
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en antwoordmogelijkheden in Microsoft Defender voor Office 365 Abonnement 2.
ms.technology: mdo
ms.prod: m365-security
ms.date: 01/29/2021
ms.openlocfilehash: a11e9ee6a4c2426951fe2b4aa4f2dd08d1931f1c
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287111"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Herstelacties in Office 365 bekijken en beheren

Wanneer geautomatiseerde onderzoeken op e-& resultaten van samenwerking  resulteren in resultaten, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt. In Microsoft Defender voor Office 365 kunnen herstelacties optreden:
- Een URL blokkeren (time-of-click)
- E-mailberichten of clusters zacht verwijderen
- E-mail- of e-mailbijlagen quarantining
- Extern doorsturen van e-mail uitschakelen

Deze herstelacties worden pas ondernomen als het beveiligingsteam ze goedkeurt. We raden u aan acties die in behandeling zijn zo snel mogelijk te beoordelen en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid. In sommige gevallen kunt u een herstelactie ongedaan maken.

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="approve-or-reject-pending-actions"></a>Acties in behandeling goedkeuren (of weigeren)

1. Ga naar het Microsoft 365-beveiligingscentrum [https://security.microsoft.com](https://security.microsoft.com) ) en meld u aan.
2. Selecteer Actiecentrum in het **navigatiedeelvenster.**
3. Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.
4. Selecteer een item in de lijst. Het deelvenster flyout wordt geopend. 
5. Controleer de informatie in het deelvenster Flyout en ga op een van de volgende stappen te werk:
   - Selecteer **De pagina Onderzoek openen om** meer details over het onderzoek te bekijken.
   - Selecteer **Goedkeuren om** een actie in behandeling te starten.
   - Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.

## <a name="undo-one-remediation-action"></a>Eén herstelactie ongedaan maken

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een actie die u ongedaan wilt maken.
3. Selecteer Ongedaan maken in het deelvenster aan de rechterkant van het **scherm.**

## <a name="undo-multiple-remediation-actions"></a>Meerdere herstelacties ongedaan maken

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis de acties die u ongedaan wilt maken. Zorg ervoor dat u items met hetzelfde actietype selecteert. Er wordt een flyoutvenster geopend.
3. Selecteer Ongedaan maken in het deelvenster Flyout.

## <a name="to-remove-a-file-from-quarantine-across-multiple-devices"></a>Een bestand uit quarantaine verwijderen op meerdere apparaten

1. Ga naar het Actiecentrum [https://security.microsoft.com/action-center](https://security.microsoft.com/action-center) () en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een bestand met het bestand Actietype **Quarantaine.**
3. Selecteer in het deelvenster aan de rechterkant van het scherm meer exemplaren van dit bestand toepassen op **X** en selecteer vervolgens **Ongedaan maken.**

## <a name="next-steps"></a>Volgende stappen

- [Bedreigingsverkenner gebruiken](threat-explorer.md)
- [Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Zie ook

- [Details en resultaten van een geautomatiseerd onderzoek in Office 365 weergeven](air-view-investigation-results.md)
