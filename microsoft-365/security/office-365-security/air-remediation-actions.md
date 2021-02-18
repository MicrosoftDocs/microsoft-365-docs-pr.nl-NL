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
description: Meer informatie over herstelacties na geautomatiseerd onderzoek in Microsoft Defender voor Office 365.
ms.date: 02/09/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bef2fbd1e9e3d3525f9c274b5f9127acfb218396
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287123"
---
# <a name="remediation-actions-in-microsoft-defender-for-office-365"></a>Herstelacties in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="remediation-actions"></a>Herstelacties

Bedreigingsbeveiligingsfuncties in [Microsoft Defender voor Office 365](office-365-atp.md) omvatten bepaalde herstelacties. Dergelijke herstelacties kunnen het volgende omvatten:

- E-mailberichten of clusters zacht verwijderen
- URL blokkeren (time-of-click)
- Extern doorsturen van e-mail uitschakelen
- Delegering uitschakelen

In Microsoft Defender voor Office 365 worden herstelacties niet automatisch ondernomen. Herstelacties worden in plaats daarvan alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie.

## <a name="threats-and-remediation-actions"></a>Bedreigingen en herstelacties

Microsoft Defender voor Office 365 bevat herstelacties om verschillende bedreigingen aan te pakken. Geautomatiseerde onderzoeken leiden vaak tot een of meer herstelacties die moeten worden beoordeeld en goedgekeurd. In sommige gevallen leidt een geautomatiseerd onderzoek niet tot een specifieke herstelactie. Gebruik de richtlijnen in de volgende tabel om nader onderzoek te doen en de juiste acties te ondernemen.

|Categorie|Bedreiging/risico|Herstelactie(en)|
|:---|:---|:---|
|E-mail|Malware|E-mail/cluster zacht verwijderen <p> Als meer dan een aantal e-mailberichten in een cluster malware bevatten, wordt het cluster als schadelijk beschouwd.|
|E-mail|Schadelijke URL<br/>(Er is een schadelijke URL gedetecteerd door [veilige koppelingen](atp-safe-links.md).)|E-mail/cluster zacht verwijderen <br/>URL blokkeren (verificatie met tijd-van-klik)<p> E-mail met een schadelijke URL wordt als schadelijk beschouwd.|
|E-mail|Phishing|E-mail/cluster zacht verwijderen <p> Als meer dan een aantal e-mailberichten in een cluster phishing-pogingen bevatten, wordt het hele cluster beschouwd als een poging tot phishing.|
|E-mail|Zapped phish <br>(E-mailberichten zijn bezorgd en vervolgens [gezap.)](zero-hour-auto-purge.md)|E-mail/cluster zacht verwijderen <p>Rapporten zijn beschikbaar om gezapde berichten te bekijken. [Kijk of ZAP een bericht en veelgestelde vragen heeft verplaatst.](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message)|
|E-mail|Gemiste phish-e-mail [gerapporteerd](enable-the-report-message-add-in.md) door een gebruiker|[Automatisch onderzoek op basis van het gebruikersrapport](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-mail|Volume van afwijking <br> (Recente hoeveelheden e-mailberichten overschrijden de vorige 7-10 dagen voor overeenkomende criteria.)|Automatisch onderzoek heeft geen specifieke actie in behandeling. <p>Volume-anomaly is geen duidelijke bedreiging, maar is slechts een indicatie van grotere e-mailvolumes in de afgelopen dagen in vergelijking met de laatste 7-10 dagen. <p>Hoewel een grote hoeveelheid e-mail mogelijke problemen kan aangeven, is bevestiging nodig in termen van schadelijke programma's of een handmatige controle van e-mailberichten/clusters. Zie [Verdachte e-mails zoeken die zijn bezorgd.](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered)|
|E-mail|Geen bedreigingen gevonden <br> (Het systeem heeft geen bedreigingen gevonden op basis van bestanden, URL's of analyse van e-mailclusteranalyses.)|Automatisch onderzoek heeft geen specifieke actie in behandeling. <p>Bedreigingen die worden [gevonden en ge zapped](zero-hour-auto-purge.md) nadat een onderzoek is voltooid, worden niet weergegeven in de numerieke bevindingen van een onderzoek, maar dergelijke bedreigingen zijn wel te zien in [Bedreigingsverkenner.](threat-explorer.md)|
|Gebruiker|Een gebruiker heeft op een schadelijke URL geklikt <br> (Een gebruiker is naar een pagina genavigeerd die later [](atp-safe-links.md#warning-pages-from-safe-links) schadelijk is gevonden of een gebruiker heeft een waarschuwingspagina voor veilige koppelingen overgeslagen om naar een schadelijke pagina te gaan.)|Automatisch onderzoek heeft geen specifieke actie in behandeling. <p>URL blokkeren (time-of-click) <p>Gebruik [Bedreigingsverkenner om gegevens over URL's weer te geven en klik op sjablonen.](threat-explorer.md#view-phishing-url-and-click-verdict-data) <p>Als uw organisatie [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/)gebruikt, kunt u de gebruiker onderzoeken [om](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) te bepalen of zijn of haar account is gehackt.|
|Gebruiker|Een gebruiker verstuurt malware/phish|Automatisch onderzoek heeft geen specifieke actie in behandeling. <p> De gebruiker kan malware/phish melden of iemand kan de gebruiker [spoofen als](anti-spoofing-protection.md) onderdeel van een aanval. Gebruik [Bedreigingsverkenner](threat-explorer.md) om e-mail met [malware](threat-explorer-views.md#email--malware) of phish te bekijken en [te verwerken.](threat-explorer-views.md#email--phish)|
|Gebruiker|E-mail doorsturen <br> (Regels voor het doorsturen van postvakken zijn geconfigureerd, die kunnen worden gebruikt voor gegevensverbestanding.)|Doorsturenregel verwijderen <p> Gebruik [inzichten in de e-mailstroom,](mail-flow-insights-v2.md)waaronder het rapport Automatisch vooruitgestuurde berichten, om specifiekere details over doorgestuurde e-mail weer te geven. [](mfi-auto-forwarded-messages-report.md)|
|Gebruiker|Regels voor e-maildelegering <br> (Voor het account van een gebruiker is delegatie ingesteld.)|De overdrachtsregel verwijderen <p> Als uw organisatie [Microsoft Defender voor](https://docs.microsoft.com/windows/security/threat-protection/) [](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) eindpunt gebruikt, kunt u de gebruiker onderzoeken die de machtiging voor delegatie krijgt.|
|Gebruiker|Gegevens exfiltration <br> (Een gebruiker heeft DLP-beleidsregels voor e-mail of bestandsdeling [geschonden.)](../../compliance/data-loss-prevention-policies.md)|Automatisch onderzoek heeft geen specifieke actie in behandeling. <p> [Bekijk DLP-rapporten en onderneemt actie.](../../compliance/view-the-dlp-reports.md)|
|Gebruiker|Afwijkende e-mail verzenden <br> (Een gebruiker heeft onlangs meer e-mailberichten verzonden dan tijdens de vorige 7-10 dagen.)|Automatisch onderzoek heeft geen specifieke actie in behandeling. <p> Het verzenden van een grote hoeveelheid e-mail is niet op zichzelf schadelijk; De gebruiker kan alleen e-mail hebben verzonden naar een grote groep geadresseerden voor een gebeurtenis. Om dit te onderzoeken, gebruikt u [inzichten in](mail-flow-insights-v2.md)de e-mailstroom, inclusief het rapport voor de [e-mailstroomkaart,](mfi-mail-flow-map-report.md) om te bepalen wat er gebeurt en hoe u actie onderneemt.|

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek weergeven in Microsoft Defender voor Office 365](air-view-investigation-results.md)
- [Acties in behandeling of voltooide herstelacties weergeven na een geautomatiseerd onderzoek in Microsoft Defender voor Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwante artikelen

- [Meer informatie over geautomatiseerd onderzoek in Microsoft Defender voor Eindpunt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)
- [Meer informatie over mogelijkheden in Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)
