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
ms.date: 06/10/2021
ms.openlocfilehash: 987771616acfd2f2faf425e525505b320155388e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108533"
---
# <a name="review-and-manage-remediation-actions-in-office-365"></a>Herstelacties controleren en beheren in Office 365

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)

Aangezien geautomatiseerde onderzoeken op e-& samenwerkingsinhoud resulteren  in vonnissen, zoals Schadelijk of *Verdacht,* worden bepaalde herstelacties gemaakt. In Microsoft Defender voor Office 365 kunnen herstelacties bestaan uit:

- E-mailberichten of clusters verwijderen
- Externe e-mail doorsturen uitschakelen

Deze herstelacties worden alleen uitgevoerd als uw beveiligingsbewerkingsteam deze goedkeurt. We raden u aan alle lopende acties zo snel mogelijk te bekijken en goed te keuren, zodat uw geautomatiseerde onderzoeken tijdig worden voltooid. In sommige gevallen kunt u ingediende acties opnieuw overwegen.  U moet deel uitmaken van de zoekfunctie & voordat u acties ondernomen.

## <a name="approve-or-reject-pending-actions"></a>Acties in behandeling goedkeuren (of weigeren)
Er zijn vier verschillende manieren om acties voor automatisch onderzoek te vinden en uit te voeren:

- [Incidentwachtrij](https://security.microsoft.com/incidents)
- [Actiecentrum](https://security.microsoft.com/action-center/pending)
- Onderzoek zelf (toegankelijk via Incident of vanuit een waarschuwing)
- [Wachtrij voor onderzoeken en herstelonderzoeken](https://security.microsoft.com/airinvestigation)

## <a name="incident-queue"></a>Incidentwachtrij

1. Open de Microsoft 365 Defender portal <https://security.microsoft.com> () en meld u aan.
2. Selecteer in het navigatiedeelvenster **Incidenten & waarschuwingen > incidenten.**
3. Selecteer een incidentnaam om de overzichtspagina te openen.
4. Selecteer het **tabblad Bewijs en** antwoord.
5. Selecteer een item in de lijst. Het zijvenster wordt geopend.
6. In het zijdeelvenster kunt u acties goedkeuren of afwijzen.

## <a name="investigation-queue"></a>Onderzoekswachtrij

1. Open de Microsoft 365 Defender portal <https://security.microsoft.com> () en meld u aan.
2. Navigeer vanaf de pagina waarschuwingen/incidenten.
3. Ga op de pagina Onderzoek naar het **tabblad Acties in behandeling.**
4. Selecteer een item in de lijst. Het zijvenster wordt geopend.
5. In het zijdeelvenster kunt u acties goedkeuren of afwijzen.

## <a name="action-center"></a>Actiecentrum

1. Open de Microsoft 365 Defender portal <https://security.microsoft.com> () en meld u aan.
2. Selecteer actiecentrum in het **navigatiedeelvenster.**
3. Bekijk op **het** tabblad In behandeling de lijst met acties die wachten op goedkeuring.
   - Selecteer **Onderzoekspagina openen voor** meer informatie over het onderzoek.
   - Selecteer **Goedkeuren om** een actie in behandeling te starten.
   - Selecteer **Weigeren om** te voorkomen dat een actie in behandeling wordt ondernomen.

## <a name="investigation-and-remediation-investigations-queue"></a>Wachtrij voor onderzoeken en herstelonderzoeken

1. Open de Microsoft 365 Defender portal <https://security.microsoft.com> () en meld u aan.
2. Open lopende onderzoeken.
3. Ga op de pagina Onderzoek naar het **tabblad Acties in behandeling.**
4. Selecteer een item in de lijst. Het zijvenster wordt geopend.
5. In het zijdeelvenster kunt u acties goedkeuren of afwijzen.

## <a name="change-or-undo-one-remediation-action"></a>Eén herstelactie wijzigen of ongedaan maken

Er zijn twee verschillende manieren om ingediende acties te herzien:

- Via het [geïntegreerde actiecentrum](https://security.microsoft.com/action-center).
- Hoewel het [Office actiecentrum](https://security.microsoft.com/threatincidents).

## <a name="change-or-undo-through-the-unified-action-center"></a>Wijzigen of ongedaan maken via het geïntegreerde actiecentrum

1. Ga naar het [geïntegreerde actiecentrum](https://security.microsoft.com/action-center) en meld u aan.
2. Selecteer op **het** tabblad Geschiedenis een actie die u wilt wijzigen of ongedaan wilt maken.
3. Selecteer in het deelvenster aan de rechterkant van het scherm de juiste actie (naar **postvak IN** **gaan,** naar ongewenste e-mail gaan, naar **verwijderde items** gaan, soft **delete** of **hard delete).**

## <a name="change-or-undo-through-the-office-action-center"></a>Wijzigen of ongedaan maken via het Office actiecentrum

1. Ga naar het [Office actiecentrum](https://security.microsoft.com/threatincidents) en meld u aan.
2. Selecteer de juiste herstel.
3. Klik in het zijdeelvenster op de vermelding voor e-mailinzendingen en wacht totdat de lijst wordt geladen.
4. Wacht tot de knop Actie bovenaan staat en selecteer de knop Actie om het actietype te wijzigen.
5. Hierdoor worden de juiste acties aan de dag 2010 genomen.

## <a name="next-steps"></a>Volgende stappen

- [Bedreigingsverkenner gebruiken](threat-explorer.md)
- [Beheer/handmatige acties](remediate-malicious-email-delivered-office-365.md)
- [Fout-positieven/negatieven rapporteren in geautomatiseerde onderzoeks- en antwoordmogelijkheden](air-report-false-positives-negatives.md)

## <a name="see-also"></a>Zie ook

- [Details en resultaten van een geautomatiseerd onderzoek weergeven in Office 365](air-view-investigation-results.md)
