---
title: Herstelacties in Microsoft Defender voor Office 365
keywords: AIR, autoIR, ATP, automated, investigation, response, remediation, threats, advanced, threat, protection
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
description: Meer informatie over herstelacties na automatisch onderzoek in Microsoft Defender voor Office 365.
ms.date: 02/09/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fa4e2d6656ec430edc221ab94cac494e1ec0ca98
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059077"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Herstelacties in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="remediation-actions"></a>Herstelacties

Bedreigingsbeveiligingsfuncties in [Microsoft Defender voor Office 365 bevatten](defender-for-office-365.md) bepaalde herstelacties. Dergelijke herstelacties kunnen bestaan uit:

- E-mailberichten of clusters zacht verwijderen
- URL blokkeren (time-of-click)
- Externe e-mail doorsturen uitschakelen
- Delegering uitschakelen

In Microsoft Defender voor Office 365 worden herstelacties niet automatisch ondernomen. In plaats daarvan worden herstelacties alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie.

## <a name="threats-and-remediation-actions"></a>Bedreigingen en herstelacties

Microsoft Defender voor Office 365 bevat herstelacties om verschillende bedreigingen aan te pakken. Geautomatiseerde onderzoeken leiden vaak tot een of meer herstelacties die moeten worden beoordeeld en goedgekeurd. In sommige gevallen resulteert een geautomatiseerd onderzoek niet in een specifieke herstelactie. Als u de juiste acties wilt onderzoeken en uitvoeren, gebruikt u de richtlijnen in de volgende tabel.

|Categorie|Bedreiging/risico|Herstelactie(en)|
|:---|:---|:---|
|E-mail|Malware|E-mail/cluster zacht verwijderen <p> Als meer dan een handjevol e-mailberichten in een cluster malware bevat, wordt het cluster als schadelijk beschouwd.|
|E-mail|Schadelijke URL<br/>(Er is een schadelijke URL gedetecteerd door [Veilige koppelingen](safe-links.md).)|E-mail/cluster zacht verwijderen <br/>URL blokkeren (tijd-van-klikverificatie)<p> E-mail met een schadelijke URL wordt beschouwd als schadelijk.|
|E-mail|Phish|E-mail/cluster zacht verwijderen <p> Als meer dan een handjevol e-mailberichten in een cluster phishingpogingen bevat, wordt het hele cluster beschouwd als een phishingpoging.|
|E-mail|Zapped phish <br>(E-mailberichten zijn bezorgd en vervolgens [ge zapped](zero-hour-auto-purge.md).)|E-mail/cluster zacht verwijderen <p>Rapporten zijn beschikbaar om gezapeerde berichten weer te geven. [Kijk of ZAP een bericht en veelgestelde vragen heeft verplaatst.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|E-mail|Gemiste phish-e-mail [die door](enable-the-report-message-add-in.md) een gebruiker is gerapporteerd|[Automatisch onderzoek dat is gestart door het rapport van de gebruiker](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-mail|Volume-afwijking <br> (Recente e-mailhoeveelheden overschrijden de vorige 7-10 dagen voor overeenkomende criteria.)|Automatisch onderzoek resulteert niet in een specifieke actie in behandeling. <p>Volume-afwijking is geen duidelijke bedreiging, maar is slechts een indicatie van grotere e-mailvolumes in de afgelopen dagen ten opzichte van de laatste 7-10 dagen. <p>Hoewel een groot aantal e-mailberichten potentiële problemen kan aangeven, is bevestiging nodig in termen van schadelijke uitspraken of een handmatige controle van e-mailberichten/clusters. Zie [Verdachte e-mail zoeken die is bezorgd.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|E-mail|Geen bedreigingen gevonden <br> (Het systeem heeft geen bedreigingen gevonden op basis van bestanden, URL's of analyse van e-mailcluster-vonnissen.)|Automatisch onderzoek resulteert niet in een specifieke actie in behandeling. <p>Bedreigingen die zijn [gevonden](zero-hour-auto-purge.md) en ge zapped nadat een onderzoek is voltooid, worden niet weerspiegeld in de numerieke bevindingen van een onderzoek, maar dergelijke bedreigingen zijn wel te zien in [Threat Explorer.](threat-explorer.md)|
|Gebruiker|Een gebruiker heeft op een schadelijke URL geklikt <br> (Een gebruiker is naar een pagina genavigeerd die later [](safe-links.md#warning-pages-from-safe-links) schadelijk bleek te zijn, of een gebruiker heeft een waarschuwingspagina voor veilige koppelingen overgeslagen om naar een schadelijke pagina te gaan.)|Automatisch onderzoek resulteert niet in een specifieke actie in behandeling. <p>URL blokkeren (time-of-click) <p>Gebruik Threat Explorer om [gegevens over URL's weer te geven en op vonnissen te klikken.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Als uw organisatie [Microsoft Defender voor](/windows/security/threat-protection/) [](/microsoft-365/security/defender-endpoint/investigate-user) Eindpunt gebruikt, kunt u de gebruiker onderzoeken om te bepalen of zijn of haar account is gehackt.|
|Gebruiker|Een gebruiker verstuurt malware/phish|Automatisch onderzoek resulteert niet in een specifieke actie in behandeling. <p> De gebruiker meldt mogelijk malware/phish of iemand kan de gebruiker [spoofen](anti-spoofing-protection.md) als onderdeel van een aanval. Gebruik [Threat Explorer om](threat-explorer.md) e-mail met malware of phish [te](threat-explorer-views.md#email--malware) bekijken en [te verwerken.](threat-explorer-views.md#email--phish)|
|Gebruiker|E-mail doorsturen <br> (Regels voor het doorsturen van postvakken zijn geconfigureerd, die kunnen worden gebruikt voor gegevensuitfiltratie.)|Regel voor doorsturen verwijderen <p> Gebruik [e-mailstroominzichten](mail-flow-insights-v2.md), waaronder het [rapport Automatisch verzonden](mfi-auto-forwarded-messages-report.md)berichten, om meer specifieke details over doorgestuurde e-mail weer te geven.|
|Gebruiker|Regels voor e-maildelegering <br> (Het account van een gebruiker heeft delegering ingesteld.)|Delegeringsregel verwijderen <p> Als uw organisatie [Microsoft Defender voor](/windows/security/threat-protection/) [](/microsoft-365/security/defender-endpoint/investigate-user) Eindpunt gebruikt, kunt u de gebruiker onderzoeken die de machtiging voor delegering krijgt.|
|Gebruiker|Gegevens exfiltration <br> (Een gebruiker heeft DLP-beleidsregels voor e-mail of het delen van [bestanden geschonden](../../compliance/data-loss-prevention-policies.md).)|Automatisch onderzoek resulteert niet in een specifieke actie in behandeling. <p> [DLP-rapporten weergeven en actie ondernemen](../../compliance/view-the-dlp-reports.md).|
|Gebruiker|Afwijkende e-mail verzenden <br> (Een gebruiker heeft onlangs meer e-mail verzonden dan tijdens de vorige 7-10 dagen.)|Automatisch onderzoek resulteert niet in een specifieke actie in behandeling. <p> Het verzenden van een groot aantal e-mailberichten is op zichzelf niet schadelijk. de gebruiker heeft mogelijk alleen e-mail verzonden naar een grote groep geadresseerden voor een gebeurtenis. Als u dit wilt onderzoeken, gebruikt u inzichten [in de](mail-flow-insights-v2.md)e-mailstroom, inclusief het rapport [E-mailstroomkaart](mfi-mail-flow-map-report.md) om te bepalen wat er aan de hand is en actie te ondernemen.|

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek weergeven in Microsoft Defender voor Office 365](air-view-investigation-results.md)
- [Lopende of voltooide herstelacties weergeven na een geautomatiseerd onderzoek in Microsoft Defender voor Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwante artikelen

- [Meer informatie over geautomatiseerd onderzoek in Microsoft Defender voor Eindpunt](/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Meer informatie over mogelijkheden in Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender)
