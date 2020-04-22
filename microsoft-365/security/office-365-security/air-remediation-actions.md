---
title: Herstelacties in geautomatiseerd onderzoek en reactie van Microsoft 365
keywords: AIR, autoIR, ATP, geautomatiseerd, onderzoek, respons, sanering, bedreigingen, geavanceerd, bedreiging, bescherming
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
description: Meer informatie over herstelacties in geautomatiseerde onderzoeks- en reactiemogelijkheden in Office 365 Advanced Threat Protection Plan 2.
ms.openlocfilehash: 8dfb203cfdae179d8d88842a2d2b55aeab2e17fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634650"
---
# <a name="remediation-actions-in-microsoft-365"></a>Herstelacties in Microsoft 365

## <a name="remediation-actions"></a>Herstelacties

[Geautomatiseerde onderzoeks- en reactiemogelijkheden](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 omvatten bepaalde herstelacties. Wanneer een geautomatiseerd onderzoek wordt uitgevoerd of is voltooid, ziet u doorgaans een of meer herstelacties waarvoor goedkeuring door uw beveiligingsteam nodig is om door te gaan. Dergelijke saneringsacties kunnen het volgende omvatten:

- E-mailberichten of clusters verwijderen van soft
- URL blokkeren (kliktijd)
- Extern doorsturen van e-mail uitschakelen
- Delegatie uitschakelen

> [!NOTE]
> In Office 365 ATP worden geautomatiseerde onderzoeken niet automatisch verholpen. Herstelacties worden alleen uitgevoerd na goedkeuring door het beveiligingsteam van uw organisatie.

## <a name="threats-and-remediation-actions"></a>Bedreigingen en saneringsacties

In de volgende tabel worden bedreigingen en passende herstelacties in Office 365 ATP samengevat. In sommige gevallen leidt een geautomatiseerd onderzoek niet tot een specifieke saneringsactie. Uw beveiligingsteam kan verder onderzoek doen naar en passende acties ondernemen zoals beschreven in de onderstaande tabel.

||||
|---|---|---|
|**Categorie**|**Bedreiging/risico**|**Herstelactie(en)**|
|E-mail|Malware| E-mail/cluster verwijderen van zachte verwijderen <br/><br/>Als meer dan een handvol e-mailberichten in een cluster malware bevatten, wordt het cluster als kwaadaardig beschouwd.|
|E-mail|Kwaadaardige URL<br/>(Er is een kwaadaardige URL gedetecteerd door [Office 365 ATP Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/how-atp-safe-links-works).)|E-mail/cluster verwijderen van zachte verwijderen <br/><br/>E-mail die een kwaadaardige URL bevat, wordt als kwaadaardig beschouwd.|
|E-mail|Phish| E-mail/cluster verwijderen van zachte verwijderen <br/><br/>Als meer dan een handvol e-mailberichten in een cluster phishing-pogingen bevatten, wordt het cluster beschouwd als phish.|
|E-mail|Zapped phish <br/>(E-mailberichten zijn bezorgd en [gezapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge).)|E-mail/cluster verwijderen van zachte verwijderen <br/><br/>Rapporten zijn beschikbaar om zapped berichten te bekijken. [Kijk of ZAP een bericht en veelgestelde vragen heeft verplaatst.](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge#how-to-see-if-zap-moved-your-message)|
|E-mail|Gemiste phish e-mail [gemeld](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in) door een gebruiker| [Geautomatiseerd onderzoek naar aanleiding van het rapport van de gebruiker](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office#example-a-user-reported-phish-message-launches-an-investigation-playbook)|
|E-mail|Volumeanomalie <br/>(Recente e-mailhoeveelheden overschrijden de vorige 7-10 dagen voor overeenkomende criteria.)|Geautomatiseerd onderzoek leidt niet tot een specifieke in behandeling zijnde actie. <br/><br/>Volume anomalie is geen duidelijke bedreiging, maar is slechts een indicatie van grotere e-mail volumes in de afgelopen dagen in vergelijking met de laatste 7-10 dagen. Hoewel dit kan wijzen op mogelijke problemen, bevestiging is nodig in termen van kwaadaardige uitspraken of een handmatige herziening van e-mailberichten / clusters. Zie [Verdachte e-mail zoeken en verwijderen die is bezorgd.](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered#find-and-delete-suspicious-email-that-was-delivered)|
|E-mail|Geen bedreigingen gevonden <br/>(Het systeem heeft geen bedreigingen gevonden op basis van bestanden, url's of analyse van e-mailclustervonnissen.)|Geautomatiseerd onderzoek leidt niet tot een specifieke in behandeling zijnde actie. <br/><br/>Bedreigingen gevonden en [zapped](https://docs.microsoft.com/microsoft-365/security/office-365-security/zero-hour-auto-purge) nadat een onderzoek is voltooid worden niet weerspiegeld in de numerieke bevindingen van een onderzoek, maar dergelijke bedreigingen zijn zichtbaar in [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer).|
|Gebruiker|Een gebruiker heeft op een kwaadaardige URL geklikt <br/>(Een gebruiker navigeerde naar een pagina die later kwaadaardig bleek te zijn, of een gebruiker omzeilde een [waarschuwingspagina voor veilige koppelingen](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-warning-pages) om naar een schadelijke pagina te gaan.)|Geautomatiseerd onderzoek leidt niet tot een specifieke in behandeling zijnde actie. <br/><br/>Gebruik Threat Explorer om [gegevens over URL's weer te geven en op vonnissen te klikken.](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer#view-data-about-phishing-urls-and-click-verdict) <br/><br/>Als uw organisatie [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)gebruikt, u overwegen de gebruiker te [onderzoeken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) om te bepalen of zijn account is gecompromitteerd.|
|Gebruiker|Een gebruiker verzendt malware/phish|Geautomatiseerd onderzoek leidt niet tot een specifieke in behandeling zijnde actie. <br/><br/>De gebruiker rapporteert mogelijk malware/phish of iemand kan [de gebruiker spoofen](https://docs.microsoft.com/microsoft-365/security/office-365-security/anti-spoofing-protection) als onderdeel van een aanval. Gebruik [Threat Explorer](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer) om e-mail met [malware](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--malware) of [phish](https://docs.microsoft.com/microsoft-365/security/office-365-security/threat-explorer-views#email--phish)te bekijken en te verwerken.|
|Gebruiker|E-mail doorsturen <br/>(Regels voor het doorsturen van mailboxen zijn geconfigureerd, die kunnen worden gebruikt voor gegevensexfiltratie.)|Doorstuurregel verwijderen <br/><br/>Gebruik [e-mailstroominzichten](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2), waaronder het [rapport Automatisch doorgestuurde berichten,](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-auto-forwarded-messages-report)om meer specifieke details over doorgestuurde e-mail weer te geven.|
|Gebruiker|Regels voor e-maildelegatie <br/>(Een gebruikersaccount heeft delegatie ingesteld.)|Dedelegatieregel verwijderen <br/><br/> Als uw organisatie [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/)gebruikt, u overwegen de gebruiker te [onderzoeken](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/investigate-user) die de delegatietoestemming krijgt.|
|Gebruiker|Gegevensexfiltratie<br/>(Een gebruiker heeft het [DLP-beleid](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)voor e-mail of het delen van bestanden geschonden .)|Geautomatiseerd onderzoek leidt niet tot een specifieke in behandeling zijnde actie. <br/><br/>[DLP-rapporten bekijken en actie ondernemen](https://docs.microsoft.com/microsoft-365/compliance/view-the-dlp-reports).|
|Gebruiker|Afwijkende e-mail verzenden <br/>(Een gebruiker heeft onlangs meer e-mail verzonden dan tijdens de vorige 7-10 dagen.)|Geautomatiseerd onderzoek leidt niet tot een specifieke in behandeling zijnde actie. <br/><br/>Het verzenden van veel e-mail is niet kwaadaardig op zichzelf; de gebruiker heeft mogelijk gewoon e-mail verzonden naar een grote groep ontvangers voor een gebeurtenis. Als u het onderzoek wilt onderzoeken, gebruikt u [de e-mailstroominzichten,](https://docs.microsoft.com/microsoft-365/security/office-365-security/mail-flow-insights-v2)waaronder het rapport van de [e-mailstroomkaart](https://docs.microsoft.com/microsoft-365/security/office-365-security/mfi-mail-flow-map-report) om te bepalen wat er aan de hand is en actie te ondernemen.|
|

## <a name="next-steps"></a>Volgende stappen

- [Details en resultaten van een geautomatiseerd onderzoek weergeven in Microsoft 365](air-view-investigation-results.md)

- [In behandeling zijnde of voltooide herstelacties weergeven na een geautomatiseerd onderzoek in Microsoft 365](air-review-approve-pending-completed-actions.md)


## <a name="related-articles"></a>Verwante artikelen

- [Geautomatiseerd onderzoek in Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [Meer informatie over Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)