---
title: Spam, niet-spam en phishingberichten rapporteren aan Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: c31406ea-2979-4fac-9288-f835269b9d2f
ms.collection:
- M365-security-compliance
description: Beheerders kunnen informatie krijgen over de verschillende manieren om goede en slechte berichten en bestanden te rapporteren aan Microsoft voor analyse.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a89ea8a41a31c9544284566fade0e603d48af759
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082814"
---
# <a name="report-messages-and-files-to-microsoft"></a>Berichten en bestanden rapporteren aan Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, hebben zowel gebruikers als beheerders verschillende methoden voor het rapporteren van e-mailberichten en bestanden aan Microsoft.

<br>

****

|Methode|Beschrijving|
|---|---|
|[Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden](admin-submission.md)|De aanbevolen rapportagemethode voor beheerders in organisaties met Exchange Online postvakken (niet beschikbaar in zelfstandige EOP).|
|[Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen](enable-the-report-message-add-in.md)|Werkt met Outlook en webversie van Outlook (voorheen bekend als Outlook Web App). <p> Afhankelijk van uw abonnement zijn berichten die gebruikers met de invoegvoegingen hebben gerapporteerd, beschikbaar in de portal Admin [Submissions](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and [Explorer](threat-explorer-views.md#email--submissions). <p> U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)
|[Fout-positieven en fout-negatieven rapporteren in Outlook](report-false-positives-and-false-negatives.md)|Verzend fout-positieven (goede e-mail die is geblokkeerd of verzonden naar de map Ongewenste e-mail) en onwaar negatieven (ongewenste e-mail of phish die in het Postvak IN is bezorgd) naar Exchange Online Protection (EOP) met de functie Rapportbericht.|
|[Berichten handmatig indienen bij Microsoft voor analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Handmatig bijgevoegde berichten verzenden naar specifieke Microsoft-e-mailadressen voor spam, geen spam en phishing.|
|[Regels voor e-mailstromen gebruiken om te zien wat gebruikers melden bij Microsoft](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)|Meer informatie over het maken van een regel voor e-mailstroom (ook wel transportregel genoemd) die u op de melding stelt wanneer gebruikers berichten rapporteren aan Microsoft voor analyse.|
|[Malware en niet-malware indienen bij Microsoft voor analyse](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Gebruik de Microsoft-beveiligingsinformatie site om bijlagen en andere bestanden in te dienen.|
|

Als de spam- of phishingberichten in quarantaine zijn geplaatst in plaats van bezorgd, kunnen gebruikers de berichten rapporteren aan Microsoft vanuit Quarantaine in de Microsoft 365 Defender portal. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in](find-and-release-quarantined-messages-as-a-user.md)Microsoft 365.

> [!NOTE]
> Gegevens uit inzendingen naar Microsoft bevinden zich in de Office 365 compliancegrens in Noord-Amerikaanse datacenters. De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te verbeteren.
