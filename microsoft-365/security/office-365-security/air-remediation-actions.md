---
title: Herstelacties na een geautomatiseerd onderzoek in Microsoft Defender voor Office 365
keywords: AIR, autoIR, ATP, automatisch, onderzoek, antwoord, herstel, bedreiging, Geavanceerd, bedreiging, bescherming
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
description: Meer informatie over herstelacties volgen na geautomatiseerd onderzoek in Microsoft Defender voor Office 365.
ms.date: 01/21/2021
ms.custom:
- air
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 39032cb187b2654b6ae03c048e706afb665a8761
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939298"
---
# <a name="remediation-actions-following-automated-investigation-in-microsoft-defender-for-office-365"></a>Herstelacties na een geautomatiseerd onderzoek in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="remediation-actions"></a>Herstelacties

[Geautomatiseerd onderzoek en antwoord mogelijkheden](office-365-air.md) in [Microsoft Defender voor Office 365](office-365-atp.md) bevatten bepaalde herstelbewerkingen. Wanneer een automatisch onderzoek wordt uitgevoerd of is voltooid, ziet u meestal een of meer herstelacties die moeten worden goedgekeurd door het team van uw beveiligingsactiviteiten. Dit kunt u onder andere oplossen door de volgende handelingen uit te voeren:

- E-mailberichten of clusters voor zacht verwijderen
- URL blokkeren (time-of-klik)
- Externe e-mail doorsturen uitschakelen
- Delegering uitschakelen

> [!NOTE]
> In Microsoft Defender voor Office 365 leveren geautomatiseerde onderzoeken geen resultaten die automatisch worden uitgevoerd. Herstelacties worden alleen uitgevoerd na goedkeuring van het team van uw organisatie beveiligings.

## <a name="threats-and-remediation-actions"></a>Acties voor bedreigingen en herstel

De tabel in deze sectie bevat een overzicht van bedreigingen en bijbehorende herstelacties in Microsoft Defender voor Office 365. In sommige gevallen levert een geautomatiseerd onderzoek geen specifieke herstelactie op. Uw team van beveiligingsactiviteiten kan verder onderzoeken en de juiste acties ondernemen zoals beschreven in de onderstaande tabel.

|Categorie|Bedreiging/risico|Herstelactie (s)|
|:---|:---|:---|
|E-mail|Malware|E-mail/cluster met zachte verwijdering <br> Als meer dan een aantal e-mailberichten in een cluster malware bevat, wordt het cluster geacht schadelijk te zijn.|
|E-mail|Schadelijke URL <br> (Een schadelijke URL is gedetecteerd door [veilige koppelingen in Microsoft Defender for Office 365](atp-safe-links.md)).|E-mail/cluster met zachte verwijdering <p> E-mail met een schadelijke URL wordt geacht schadelijk te zijn.|
|E-mail|Phishing|E-mail/cluster met zachte verwijdering <br> Als meer dan een aantal e-mailberichten in een cluster phishingberichten bevat, wordt het cluster als phishing beschouwd.|
|E-mail|Zapped phishing <br> (E-mailberichten zijn bezorgd en [zapped](zero-hour-auto-purge.md).)|E-mail/cluster met zachte verwijdering <p> Rapporten kunnen worden gebruikt om zapped-berichten te bekijken. [Kijk of zap een bericht en veelgestelde vragen verplaatste](zero-hour-auto-purge.md#how-to-see-if-zap-moved-your-message).|
|E-mail|E-mail met gemiste phishing door een gebruiker [gemeld](enable-the-report-message-add-in.md)|[Automatisch onderzoek geactiveerd door het rapport van de gebruiker](automated-investigation-response-office.md#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-mail|Volume afwijkend <br> (Recente e-mail hoeveelheden zijn groter dan de vorige 7-10 dagen voor vergelijkingscriteria.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <p> Volume afwijkend is geen duidelijke bedreiging, maar wel een opgave van groter e-mail volume in de afgelopen dagen vergeleken met de laatste 7-10 dagen. Hoewel volume afwijkingen de mogelijkheid kunnen geven om potentiële problemen op te lossen, is de bevestiging vereist in termen van kwaadaardige Verdicts of een handmatige beoordeling van e-mailberichten/clusters. Zie [verdachte E-mail vinden die is afgeleverd](investigate-malicious-email-that-was-delivered.md#find-suspicious-email-that-was-delivered).|
|E-mail|Geen bedreigingen gevonden <br> (Het systeem heeft geen bedreigingen gevonden op basis van bestanden, url's of analyses van e-mail cluster Verdicts.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <p> Bedreigingen gevonden en [zapped](zero-hour-auto-purge.md) na voltooiing van een onderzoek zijn niet doorgevoerd in de numerieke bevindingen van een onderzoek, maar deze bedreigingen zijn zichtbaar in de [bedreigings Verkenner](threat-explorer.md).|
|Gebruiker|Een gebruiker heeft op een schadelijke URL geklikt <br> (Een gebruiker heeft genavigeerd naar een pagina die later schadelijk is of een gebruiker een [waarschuwingspagina voor veilige koppelingen](atp-safe-links.md#warning-pages-from-safe-links) heeft genegeerd om een kwaadaardige pagina te openen.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <p> Gebruik de bedreigings Verkenner om [gegevens over url's weer te geven en klik op Verdicts](threat-explorer.md#view-phishing-url-and-click-verdict-data). <p> Als uw organisatie [Microsoft Defender for endpoints](https://docs.microsoft.com/windows/security/threat-protection/)gebruikt, kunt u overwegen om [de gebruiker](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) te vragen om te bepalen of het account van de gebruiker is aangetast.|
|Gebruiker|Een gebruiker verzendt malware/phishing|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <p> De gebruiker meldt mogelijk malware/phishing of iemand kan [de gebruiker spoofen](anti-spoofing-protection.md) als onderdeel van een aanval. Met behulp van de [bedreigings Verkenner](threat-explorer.md) kunt u e-mail met [malware](threat-explorer-views.md#email--malware) of [phishing](threat-explorer-views.md#email--phish)weergeven en verwerken.|
|Gebruiker|E-mail doorsturen <br> (Regels voor het doorsturen van postvakken zijn geconfigureerd, die kunnen worden gebruikt voor data-exfiltration.)|Doorstuurregel verwijderen <p> Met behulp van de [inzichten voor e-mail stromen](mail-flow-insights-v2.md), waaronder het [rapport automatische doorgestuurde berichten](mfi-auto-forwarded-messages-report.md), kunt u specifiekere details van doorgestuurde e-mail weergeven.|
|Gebruiker|Regels voor e-mail delegering <br> (Het account van een gebruiker heeft delegering ingesteld.)|Machtigingsregel verwijderen <p> Als uw organisatie [Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/)gebruikt, kunt u [het beste de gebruikers](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) van wie u de machtiging voor delegering krijgt, onderzoeken.|
|Gebruiker|Data-exfiltration <br> (Een gebruiker schendt het [DLP-beleid](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)voor het delen van e-mailberichten of bestanden.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <p> [DLP-rapporten weergeven en actie ondernemen](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Gebruiker|Afwijkende e-mail verzonden <br> (Een gebruiker heeft onlangs meer e-mail verzonden dan tijdens de vorige 7-10 dagen.)|Geautomatiseerd onderzoek resulteert niet in een specifieke actie in behandeling. <p> Het verzenden van een grote hoeveelheid e-mailbericht is niet vanzelf schadelijk. de gebruiker heeft mogelijk alleen e-mail verzonden naar een grote groep geadresseerden voor een gebeurtenis. Als u wilt onderzoeken, gebruikt u [inzichten over e-mail](mail-flow-insights-v2.md)stromen, waaronder het rapport van de [e-mail stroom](mfi-mail-flow-map-report.md) , om te bepalen wat er gebeurt en wat er gebeurt.|
|

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek in Microsoft Defender voor Office 365 weergeven](air-view-investigation-results.md)

- [In behandeling zijnde of voltooide herstelacties bekijken na een geautomatiseerd onderzoek in Microsoft Defender voor Office 365](air-review-approve-pending-completed-actions.md)

## <a name="related-articles"></a>Verwante artikelen

- [Meer informatie over een geautomatiseerd onderzoek in Microsoft Defender voor eindpunten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Meer informatie over mogelijkheden in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)
