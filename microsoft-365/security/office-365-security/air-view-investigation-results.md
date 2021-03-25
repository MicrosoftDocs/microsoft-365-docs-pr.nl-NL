---
title: De resultaten van een geautomatiseerd onderzoek weergeven in Microsoft 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, herstel, acties
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 kunt u de resultaten en belangrijkste bevindingen bekijken.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8bf18a9fb80805581a1439b3965a664fd0868248
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204264"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Details en resultaten van een geautomatiseerd onderzoek in Microsoft 365

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Wanneer een [geautomatiseerd onderzoek](office-365-air.md) plaatsvindt in Microsoft Defender voor [Office 365,](defender-for-office-365.md)zijn details over dat onderzoek beschikbaar tijdens en na het geautomatiseerde onderzoeksproces. Als u de benodigde machtigingen hebt, kunt u deze gegevens bekijken in het Microsoft 365-beveiligingscentrum. Onderzoeksdetails bieden u de actuele status en de mogelijkheid om in behandeling zijnde acties goed te keuren.

> [!TIP]
> Bekijk de nieuwe, geïntegreerde onderzoekspagina in het Microsoft 365-beveiligingscentrum. Zie [(NIEUW!) voor meer informatie. Geïntegreerde onderzoekspagina](../defender/m365d-autoir-results.md#new-unified-investigation-page).

## <a name="investigation-status"></a>Onderzoeksstatus

De onderzoeksstatus geeft de voortgang van de analyse en acties aan. Terwijl het onderzoek wordt uitgevoerd, wordt de status gewijzigd om aan te geven of er bedreigingen zijn gevonden en of acties zijn goedgekeurd.

|Status|Beschrijving|
|:---|:---|
|**Starten**|Het onderzoek is gestart en het wachten is om te starten.|
|**Uitvoeren**|Het onderzoeksproces is gestart en is aan de gang. Deze status treedt ook op wanneer [acties in behandeling](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) zijn goedgekeurd.|
|**Geen bedreigingen gevonden**|Het onderzoek is voltooid en er zijn geen bedreigingen (gebruikersaccount, e-mailbericht, URL of bestand) geïdentificeerd. <p> **TIP**: Als u vermoedt dat er iets is gemist (zoals een onwaar negatief), kunt u actie ondernemen met [Threat Explorer.](threat-explorer.md)|
|**Gevonden bedreigingen**|Het geautomatiseerde onderzoek heeft problemen gevonden, maar er zijn geen specifieke herstelacties om deze problemen op te lossen. <p> De **status Bedreigingen** gevonden kan optreden wanneer een bepaald type gebruikersactiviteit is geïdentificeerd, maar er zijn geen opschoningsacties beschikbaar. Voorbeelden hiervan zijn een van de volgende gebruikersactiviteiten: <br/>- Een DLP-gebeurtenis [(Data Loss Prevention)](../../compliance/data-loss-prevention-policies.md)<br/>- Een e-mail verzenden van een afwijking<br/>- Verzonden malware<br/>- Verzonden phish <p> Bij het onderzoek zijn geen schadelijke URL's, bestanden of e-mailberichten gevonden die moeten worden opgelost en zijn er geen postvakactiviteiten die moeten worden opgelost, zoals het uitschakelen van doorsturen of delegeren. <p> **TIP**: Als u vermoedt dat er iets is gemist (zoals een onwaar negatief), kunt u dit onderzoeken en actie ondernemen met [Threat Explorer.](threat-explorer.md)|
|**Beëindigd door systeem**|Het onderzoek is gestopt. Een onderzoek kan om verschillende redenen stoppen: <br/>- De lopende acties van het onderzoek zijn verlopen. Acties in behandeling zijn een time-out na het wachten op goedkeuring voor een week.<br/>- Er zijn te veel acties. Als er bijvoorbeeld te veel gebruikers op kwaadaardige URL's klikken, kan dit de mogelijkheid van het onderzoek overschrijden om alle analysen uit te voeren, zodat het onderzoek wordt stopgezet.<p> **TIP**: Als een onderzoek stopt voordat er acties zijn ondernomen, kunt u [Threat Explorer](threat-explorer.md) gebruiken om bedreigingen te vinden en aan te pakken.|
|**Actie in behandeling**|Het onderzoek heeft een bedreiging gevonden, zoals een schadelijke e-mail, een kwaadaardige URL of een riskante postvakinstelling, en een actie om deze bedreiging te herstellen wacht op [goedkeuring.](air-review-approve-pending-completed-actions.md) <p> De **status Actie in** behandeling wordt geactiveerd wanneer een bedreiging met een bijbehorende actie wordt gevonden. De lijst met lopende acties kan echter toenemen naarmate een onderzoek wordt uitgevoerd. Bekijk de details van het onderzoek om te zien of andere items nog moeten worden voltooid.|
|**Herstel**|Het onderzoek is voltooid en alle herstelacties zijn goedgekeurd (aangegeven als volledig hersteld). <p> **OPMERKING:** Goedgekeurde herstelacties kunnen fouten bevatten waardoor de acties niet kunnen worden ondernomen. Ongeacht of herstelacties zijn voltooid, wordt de onderzoeksstatus niet gewijzigd. Bekijk de details van het onderzoek.|
|**Gedeeltelijk gesaneerd**|Het onderzoek heeft geleid tot herstelacties, en sommige zijn goedgekeurd en voltooid. Andere acties zijn nog in [behandeling.](air-review-approve-pending-completed-actions.md)|
|**Mislukt**|Ten minste één onderzoeksanalyser liep tegen een probleem aan waarbij het niet goed kon worden voltooid. <p> **OPMERKING:** Als een onderzoek mislukt nadat herstelacties zijn goedgekeurd, zijn de herstelacties mogelijk nog steeds gelukt. Bekijk de onderzoeksdetails. |
|**Wachtrij door beperking**|Er wordt een onderzoek in een wachtrij gehouden. Wanneer andere onderzoeken zijn voltooid, worden in wachtrijen onderzoeken gestart. Beperking helpt slechte serviceprestaties te voorkomen.  <p> **TIP**: Acties in behandeling kunnen het aantal nieuwe onderzoeken beperken. Zorg ervoor dat u [in behandeling zijnde acties goedkeurt (of weigert).](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Beëindigd door beperking**|Als een onderzoek te lang in de wachtrij wordt gehouden, wordt het gestopt. <p> **TIP**: U kunt [een onderzoek starten vanuit Threat Explorer.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Details van een onderzoek weergeven

1. Ga naar het Microsoft 365-beveiligingscentrum <https://security.microsoft.com> () en meld u aan.
2. Selecteer actiecentrum in het **navigatiedeelvenster.**
3. Selecteer een actie **op de** **tabbladen** In behandeling of Geschiedenis. Het deelvenster Flyout wordt geopend.
4. Selecteer in het deelvenster Flyout de optie **Onderzoekspagina openen.** 
5. Gebruik de verschillende tabbladen voor meer informatie over het onderzoek.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Details weergeven over een waarschuwing in verband met een onderzoek

Bepaalde soorten waarschuwingen leiden tot automatisch onderzoek in Microsoft 365. Zie waarschuwingsbeleidsregels voor automatische onderzoeken voor [meer informatie.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Ga naar het Microsoft 365-beveiligingscentrum <https://security.microsoft.com> () en meld u aan.
2. Selecteer actiecentrum in het **navigatiedeelvenster.**
3. Selecteer een actie **op de** **tabbladen** In behandeling of Geschiedenis. Het deelvenster Flyout wordt geopend.
4. Selecteer in het deelvenster Flyout de optie **Onderzoekspagina openen.** 
5. Selecteer het **tabblad Waarschuwingen** om een lijst weer te geven met alle waarschuwingen die aan dat onderzoek zijn gekoppeld.
6. Selecteer een item in de lijst om het flyoutvenster te openen. Daar kunt u meer informatie over de waarschuwing bekijken.

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- E-mailtellingen worden berekend op het moment van het onderzoek en sommige tellingen worden opnieuw berekend wanneer u flyouts voor onderzoeken opent (op basis van een onderliggende query).

- De e-mailtellingen die worden  weergegeven voor de e-mailclusters op het tabblad E-mail en de e-mailhoeveelheid die wordt weergegeven op cluster flyout, worden berekend op het moment van onderzoek en worden niet gewijzigd.

- Het aantal e-mailberichten  dat wordt weergegeven onder aan het tabblad E-mail van de flyout van het e-mailcluster en het aantal e-mailberichten dat wordt weergegeven in Explorer, is een weerspiegeling van de e-mailberichten die zijn ontvangen na de eerste analyse van het onderzoek.

  Een e-mailcluster met een oorspronkelijke hoeveelheid van 10 e-mailberichten zou dus een totaal van 15 e-mailberichten laten zien wanneer er nog vijf e-mailberichten binnenkomen tussen de onderzoeksanalysefase en wanneer de beheerder het onderzoek controleert. Oude onderzoeken kunnen ook hogere tellingen laten zien dan explorerquery's laten zien, omdat gegevens in Microsoft Defender voor Office 365 Plan 2 na zeven dagen verlopen voor proefversies en na 30 dagen voor betaalde licenties.

  Het weergeven van zowel het aantal historische als de huidige tellingen in verschillende weergaven wordt uitgevoerd om het e-maileffect op het moment van het onderzoek aan te geven en de huidige impact tot het moment waarop de hersteltijd wordt uitgevoerd.

- In de context van e-mail ziet u mogelijk een volume-afwijkingsbedreiging als onderdeel van het onderzoek. Een volume-afwijking geeft een piek aan in vergelijkbare e-mailberichten rond de onderzoeksgebeurtenistijd in vergelijking met eerdere periodes. Een piek in e-mailverkeer, samen met bepaalde kenmerken (bijvoorbeeld onderwerp- en afzenderdomein, body-overeenkomst en afzender-IP) is een typisch voorbeeld van het begin van e-mailcampagnes of -aanvallen. Bulk-, spam- en legitieme e-mailcampagnes hebben echter vaak dezelfde kenmerken.

- Volumeafwijkingen vormen een potentiële bedreiging en kunnen daarom minder ernstig zijn in vergelijking met malware- of phish-bedreigingen die worden geïdentificeerd met anti-virusprogramma's, detonatie of schadelijke reputatie.

- U hoeft niet elke actie goed te keuren. Als u het niet eens bent met de aanbevolen actie of als  uw organisatie bepaalde typen acties niet kiest, kunt u ervoor kiezen om de acties te negeren of ze gewoon te negeren en geen actie te ondernemen.

- Als u alle acties goedkeurt en/of afwijst, kan het onderzoek volledig worden afgerond (de status wordt hersteld), terwijl sommige acties onvolledig blijven, waardoor de onderzoeksstatus verandert in een gedeeltelijk herstelde status.

## <a name="next-steps"></a>Volgende stappen

- [Lopende acties controleren en goedkeuren](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
