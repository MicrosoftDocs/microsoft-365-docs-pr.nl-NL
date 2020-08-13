---
title: Herstelacties in Microsoft 365 automatisch onderzoek en antwoord
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herstel, bedreiging, Geavanceerd, bedreiging, bescherming
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Meer informatie over herstelacties in het automatisch onderzoek en de antwoord mogelijkheden in Office 365 Advanced Threat Protection-abonnement 2.
ms.openlocfilehash: 761ae38250dc084a248203dd78b66ed18ea9c401
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653375"
---
# <a name="remediation-actions-in-microsoft-365"></a>Herstelacties in Microsoft 365

## <a name="remediation-actions"></a>Herstelacties

[Geautomatiseerd onderzoek-en antwoord](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) vermogen (lucht) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) plan 2 bevat bepaalde herstelbewerkingen. Wanneer een automatisch onderzoek wordt uitgevoerd of is voltooid, ziet u meestal een of meer herstelacties die moeten worden goedgekeurd door het team van uw beveiligingsactiviteiten. Dit kunnen de volgende herstelbewerkingen zijn:

- E-mailberichten of clusters voor zacht verwijderen
- URL blokkeren (time-of-klik)
- Externe e-mail doorsturen uitschakelen
- Delegering uitschakelen

> [!NOTE]
> In Office 365 ATP worden geautomatiseerde onderzoeken niet automatisch hersteld. Herstelacties worden alleen uitgevoerd na goedkeuring van het beveiligingsteam van uw organisatie.

## <a name="threats-and-remediation-actions"></a>Acties voor bedreigingen en herstel

De volgende tabel bevat een overzicht van bedreigingen en de juiste herstelacties in Office 365 ATP. In sommige gevallen levert een geautomatiseerd onderzoek geen specifieke herstelactie op. Uw team van beveiligingsactiviteiten kan verder onderzoeken en de juiste acties ondernemen zoals beschreven in de onderstaande tabel.

****

|Categorie|Bedreiging/risico|Herstelactie (s)|
|---|---|---|
|E-mail|Malware|E-mail/cluster met zachte verwijdering <br/><br/>Als meer dan een aantal e-mailberichten in een cluster malware bevat, wordt het cluster geacht schadelijk te zijn.|
|E-mail|Schadelijke URL<br/>(Een schadelijke URL is gedetecteerd door [Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works)met behulp van ATP voor veilige koppelingen.)|E-mail/cluster met zachte verwijdering <br/><br/>E-mail met een schadelijke URL wordt geacht schadelijk te zijn.|
|E-mail|Phishing|E-mail/cluster met zachte verwijdering <br/><br/>Als meer dan een aantal e-mailberichten in een cluster phishingberichten bevat, wordt het cluster beschouwd als phishing.|
|E-mail|Zapped phishing <br/>(E-mailberichten zijn bezorgd en [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|E-mail/cluster met zachte verwijdering <br/><br/>Rapporten kunnen worden gebruikt om zapped-berichten te bekijken. [Kijk of zap een bericht en veelgestelde vragen verplaatste](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message).|
|E-mail|E-mail met gemiste phishing door een gebruiker [gemeld](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)|[Automatisch onderzoek geactiveerd door het rapport van de gebruiker](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-mail|Volume afwijkend <br/>(Recente e-mail hoeveelheden zijn groter dan de vorige 7-10 dagen voor vergelijkingscriteria.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <br/><br/>Volume afwijkend is geen duidelijke bedreiging, maar wel een opgave van groter e-mail volume in de afgelopen dagen vergeleken met de laatste 7-10 dagen. Hoewel dit kan leiden tot mogelijke problemen, is de bevestiging vereist in termen van kwaadaardige Verdicts of een handmatige revisie van e-mailberichten/clusters. Zie [verdachte E-mail zoeken en verwijderen die is afgeleverd](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered).|
|E-mail|Geen bedreigingen gevonden <br/>(Het systeem heeft geen bedreigingen gevonden op basis van bestanden, url's of analyses van e-mail cluster Verdicts.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <br/><br/>Bedreigingen gevonden en [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) na voltooiing van een onderzoek zijn niet doorgevoerd in de numerieke bevindingen van een onderzoek, maar deze bedreigingen zijn zichtbaar in de [bedreigings Verkenner](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Gebruiker|Een gebruiker heeft op een schadelijke URL geklikt <br/>(Een gebruiker heeft genavigeerd naar een pagina die later schadelijk is of een gebruiker een [waarschuwingspagina voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) heeft genegeerd om een kwaadaardige pagina te openen.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <br/><br/>Gebruik de bedreigings Verkenner om [gegevens over url's weer te geven en klik op Verdicts](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict). <br/><br/>Als in uw organisatie [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)wordt gebruikt, kunt u overwegen om [de gebruiker](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) te vragen om te bepalen of het account van de gebruiker is aangetast.|
|Gebruiker|Een gebruiker verzendt malware/phishing|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <br/><br/>De gebruiker meldt mogelijk malware/phishing of iemand kan [de gebruiker spoofen](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) als onderdeel van een aanval. Met behulp van de [bedreigings Verkenner](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) kunt u e-mail met [malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) of [phishing](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)weergeven en verwerken.|
|Gebruiker|E-mail doorsturen <br/>(Regels voor het doorsturen van postvakken zijn geconfigureerd, die kunnen worden gebruikt voor data-exfiltration.)|Doorstuurregel verwijderen <br/><br/>Met behulp van de [inzichten voor e-mail stromen](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), waaronder het [rapport automatisch doorgestuurde berichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report), kunt u meer specifieke informatie over doorgestuurde e-mail weergeven.|
|Gebruiker|Regels voor e-mail delegering <br/>(Het account van een gebruiker heeft delegering ingesteld.)|Machtigingsregel verwijderen <br/><br/> Als in uw organisatie [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)wordt gebruikt, kunt u [de gebruiker](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) die de machtiging voor delegering krijgt, onderzoeken.|
|Gebruiker|Data-exfiltration<br/>(Een gebruiker schendt het [DLP-beleid](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)voor het delen van e-mailberichten of bestanden.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <br/><br/>[DLP-rapporten weergeven en actie ondernemen](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Gebruiker|Afwijkende e-mail verzonden <br/>(Een gebruiker heeft onlangs meer e-mail verzonden dan tijdens de vorige 7-10 dagen.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <br/><br/>Het verzenden van een heleboel e-mailberichten is niet vanzelf schadelijk. de gebruiker heeft mogelijk alleen e-mail verzonden naar een grote groep geadresseerden voor een gebeurtenis. Als u wilt onderzoeken, gebruikt u [inzichten over e-mail](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)stromen, waaronder het rapport van de [e-mail stroom](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) , om te bepalen wat er gebeurt en wat er gebeurt.|
|

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek in Microsoft 365 weergeven](air-view-investigation-results.md)

- [In behandeling zijnde of voltooide herstelacties bekijken na een geautomatiseerd onderzoek in Microsoft 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwante artikelen

- [Geautomatiseerd onderzoek in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Meer informatie over Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)