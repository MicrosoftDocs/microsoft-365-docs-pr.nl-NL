---
title: De resultaten van een geautomatiseerd onderzoek in Microsoft 365 weergeven
keywords: AIR, autoIR, ATP, automated, investigation, remediation, actions
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
description: Tijdens en na een geautomatiseerd onderzoek in Microsoft 365 kunt u de resultaten en belangrijke resultaten bekijken.
ms.date: 01/29/2021
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2d6d4a710878d65462110f317cafeeef64617667
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406686"
---
# <a name="details-and-results-of-an-automated-investigation-in-microsoft-365"></a>Details en resultaten van een geautomatiseerd onderzoek in Microsoft 365

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Wanneer een [geautomatiseerd onderzoek plaatsvindt](office-365-air.md) in [Microsoft Defender voor Office 365,](office-365-atp.md)zijn details over dat onderzoek beschikbaar tijdens en na het proces voor geautomatiseerd onderzoek. Als u de benodigde machtigingen hebt, kunt u die details bekijken in het Microsoft 365-beveiligingscentrum. Onderzoekgegevens verstrekken u de actuele status en de mogelijkheid om acties die in behandeling zijn goed te keuren.

> [!TIP]
> Bekijk de nieuwe, geïntegreerde onderzoekspagina in het Microsoft 365-beveiligingscentrum. Zie [(NIEUW!) voor meer informatie. Geïntegreerde onderzoekspagina.](../mtp/mtp-autoir-results.md#new-unified-investigation-page)

## <a name="investigation-status"></a>Status van onderzoek

De onderzoeksstatus geeft de voortgang van de analyse en acties aan. Terwijl het onderzoek wordt uitgevoerd, worden statuswijzigingen gewijzigd om aan te geven of er bedreigingen zijn gevonden en of acties zijn goedgekeurd.

|Status|Beschrijving|
|:---|:---|
|**Starten**|Het onderzoek is geactiveerd en wacht op het starten van het onderzoek.|
|**Wordt uitgevoerd**|Het onderzoek is gestart en is in gang gezet. Deze status treedt ook op wanneer [acties in behandeling](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions) zijn goedgekeurd.|
|**Geen bedreigingen gevonden**|Het onderzoek is voltooid en er zijn geen bedreigingen (gebruikersaccount, e-mailbericht, URL of bestand) geïdentificeerd. <p> **TIP:** Als u vermoedt dat er iets is gemist (zoals een fout-negatief), kunt u actie ondernemen met [Bedreigingsverkenner.](threat-explorer.md)|
|**Bedreigingen gevonden**|Tijdens dit automatische onderzoek zijn problemen aangetroffen, maar er zijn geen specifieke herstelacties om deze problemen op te lossen. <p> De **status Bedreigingen** gevonden kan optreden wanneer een bepaald type gebruikersactiviteit is geïdentificeerd, maar er zijn geen opschoonacties beschikbaar. Voorbeelden hiervan zijn de volgende gebruikersactiviteiten: <br/>- Een gebeurtenis [voor preventie van gegevensverlies](../../compliance/data-loss-prevention-policies.md) (DLP)<br/>- Een e-mailbericht waarin een afwijking wordt verzonden<br/>- Verzonden malware<br/>- Phish verzonden <p> Het onderzoek heeft geen schadelijke URL's, bestanden of e-mailberichten gevonden om te herstellen en geen postvakactiviteit die kan worden opgelost, zoals het uitschakelen van doorsturen of delegatie. <p> **TIP:** Als u vermoedt dat er iets is gemist (zoals een fout-negatief), kunt u dit onderzoeken en actie ondernemen met [Bedreigingsverkenner.](threat-explorer.md)|
|**Beëindigd door systeem**|Het onderzoek is gestopt. Een onderzoek kan om verschillende redenen worden gestopt: <br/>- De acties in behandeling van het onderzoek zijn verlopen. Acties in behandeling komen uit nadat ze één week moeten worden goedgekeurd.<br/>- Er zijn te veel acties. Als er bijvoorbeeld te veel gebruikers op schadelijke URL's klikken, kan het onderzoek de mogelijkheid overschrijden om alle analysen uit te voeren, zodat het onderzoek wordt stopgezet.<p> **TIP:** Als een onderzoek wordt stopgezet voordat er acties zijn uitgevoerd, kunt u Bedreigingsverkenner gebruiken om bedreigingen te zoeken en te adresseert. [](threat-explorer.md)|
|**Actie in behandeling**|Het onderzoek heeft een bedreiging gevonden, zoals een schadelijke e-mail, een schadelijke URL of een riskante postvakinstelling, en een actie voor het herstellen van deze bedreiging wacht op [goedkeuring.](air-review-approve-pending-completed-actions.md) <p> De **status Actie** in behandeling wordt geactiveerd wanneer een bedreiging met een bijbehorende actie wordt gevonden. De lijst met acties in behandeling kan tijdens het uitvoeren van een onderzoek echter worden uitgebreid. Bekijk details van onderzoek om te zien of andere items nog moeten worden voltooid.|
|**Remediated**|Het onderzoek is voltooid en alle herstelacties zijn goedgekeurd (zoals volledig hersteld). <p> **OPMERKING:** Goedgekeurde herstelacties kunnen fouten bevatten die verhinderen dat de acties worden ondernomen. De status van het onderzoek verandert niet, ongeacht of herstelacties zijn voltooid. Details van onderzoek weergeven.|
|**Gedeeltelijk herstel**|Het onderzoek heeft geleid tot herstelacties en sommige zijn goedgekeurd en voltooid. Andere acties zijn nog [in behandeling.](air-review-approve-pending-completed-actions.md)|
|**Mislukt**|Ten minste één onderzoeksanalyse heeft een probleem gelopen waarbij het niet correct kon worden voltooid. <p> **OPMERKING:** Als een onderzoek mislukt nadat herstelacties zijn goedgekeurd, zijn de herstelacties mogelijk toch geslaagd. Bekijk de details van het onderzoek. |
|**In wachtrij door beperken**|Er wordt een onderzoek in een wachtrij geplaatst. Wanneer andere onderzoeken zijn voltooid, begint een onderzoek in de wachtrij. Beperken helpt slechte serviceprestaties te voorkomen.  <p> **TIP:** Acties in behandeling kunnen beperken hoeveel nieuwe onderzoeken kunnen worden uitgevoerd. Zorg ervoor dat [u acties in behandeling goedkeurt (of afkeurt).](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)|
|**Beëindigd door beperking**|Als een onderzoek te lang in de wachtrij wordt gehouden, stopt het. <p> **TIP:** u kunt [een onderzoek starten vanuit Bedreigingsverkenner.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)|
|

## <a name="view-details-of-an-investigation"></a>Details van een onderzoek weergeven

1. Ga naar het Microsoft 365-beveiligingscentrum <https://security.microsoft.com> () en meld u aan.
2. Selecteer Actiecentrum in het **navigatiedeelvenster.**
3. Selecteer een actie **op** het tabblad **In** behandeling of Geschiedenis. Het deelvenster flyout wordt geopend.
4. Selecteer onderzoekspagina openen in het **flyoutvenster.** 
5. Gebruik de verschillende tabbladen voor meer informatie over het onderzoek.

## <a name="view-details-about-an-alert-related-to-an-investigation"></a>Details weergeven van een waarschuwing in verband met een onderzoek

Bepaalde soorten waarschuwingen activeren automatisch onderzoek in Microsoft 365. Zie waarschuwingsbeleid dat automatische [onderzoeken activeert voor meer informatie.](office-365-air.md#which-alert-policies-trigger-automated-investigations)

1. Ga naar het Microsoft 365-beveiligingscentrum <https://security.microsoft.com> () en meld u aan.
2. Selecteer Actiecentrum in het **navigatiedeelvenster.**
3. Selecteer een actie **op** het tabblad **In** behandeling of Geschiedenis. Het deelvenster flyout wordt geopend.
4. Selecteer onderzoekspagina openen in het **flyoutvenster.** 
5. Selecteer het **tabblad** Waarschuwingen om een lijst weer te geven met alle waarschuwingen die aan dat onderzoek zijn gekoppeld.
6. Selecteer een item in de lijst om het flyoutvenster te openen. Daar kunt u meer informatie over de waarschuwing bekijken.

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- E-mailtellingen worden berekend op het moment van het onderzoek en sommige tellingen worden opnieuw berekend wanneer u flyouts voor onderzoek opent (op basis van een onderliggende query).

- De e-mailtellingen die worden  weergegeven voor de e-mailclusters op het tabblad E-mail en de waarde van de hoeveelheid e-mail die wordt weergegeven op een cluster flyout, worden berekend op het moment van onderzoek en veranderen niet.

- Het aantal e-mailberichten  dat wordt weergegeven onder aan het tabblad E-mail van de flyout van het e-mailcluster en het aantal e-mailberichten dat in Verkenner wordt weergegeven, komt overeen met e-mailberichten die zijn ontvangen na de eerste analyse van het onderzoek.

  Zo zou een e-mailcluster met een oorspronkelijk aantal van tien e-mailberichten in totaal 15 e-mailberichten tonen als er nog vijf e-mailberichten binnenkomen tussen de analysefase van het onderzoek en het moment waarop de beheerder het onderzoek bekijkt. Op dezelfde manier kunnen oude onderzoeken hogere tellingen weergeven dan het aantal verkenner-query's, omdat gegevens in Microsoft Defender voor Office 365 Abonnement 2 na zeven dagen verlopen voor proefversies en na 30 dagen voor betaalde licenties.

  Het aantal historische en huidige tellingen in verschillende weergaven wordt weergegeven om de invloed van de e-mail op het moment van onderzoek en de huidige impact aan te geven totdat het herstel is uitgevoerd.

- In de context van e-mail ziet u mogelijk een volume-anomaly threat als onderdeel van het onderzoek. Een volume-afwijking duidt op een prikker in soortgelijke e-mailberichten rond het tijdstip van de onderzoeksgebeurtenis in vergelijking met eerdere periodes. Een prikker in e-mailverkeer, samen met bepaalde kenmerken (bijvoorbeeld domein van onderwerp en afzender, overeenkomsten tussen de lichaamsdelen en afzender-IP) is het begin van e-mailcampagnes of aanvallen. Bulk-, spam- en legitieme e-mailcampagnes delen deze kenmerken echter vaak.

- Volume-malware vormt een mogelijke bedreiging en kan dienovereenkomstig minder ernstig zijn in vergelijking met malware- of phish-bedreigingen die worden geïdentificeerd met antivirusprogramma's, detonatie of schadelijke reputatie.

- U hoeft niet elke actie goed te keuren. Als u niet akkoord gaat met de aanbevolen actie of als uw organisatie  bepaalde typen acties niet kiest, kunt u ervoor kiezen om de acties te weigeren of deze gewoon te negeren en geen actie te ondernemen.

- Als u alle acties goedkeurt en/of afwijst, wordt het onderzoek volledig gesloten (de status wordt hersteld), terwijl sommige acties onvolledige resultaten van de status van het onderzoek veranderen in een gedeeltelijk herstelde status.

## <a name="next-steps"></a>Volgende stappen

- [Acties in behandeling controleren en goedkeuren](air-review-approve-pending-completed-actions.md#approve-or-reject-pending-actions)
