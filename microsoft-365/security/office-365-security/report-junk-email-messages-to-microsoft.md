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
ms.openlocfilehash: 8c87938a8716da36f027300d685f0caedcf69660
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52291125"
---
# <a name="report-messages-and-files-to-microsoft"></a>Berichten en bestanden rapporteren aan Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 organisaties met postvakken in Exchange Online of zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online-postvakken, hebben zowel gebruikers als beheerders verschillende methoden voor het rapporteren van e-mailberichten en bestanden aan Microsoft.

****

|Methode|Beschrijving|
|---|---|
|[Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden](admin-submission.md)|De aanbevolen rapportagemethode voor beheerders in organisaties met Exchange Online postvakken (niet beschikbaar in zelfstandige EOP).|
|[Het rapportbericht of de phishing-invoegvoegingen rapporteren inschakelen](enable-the-report-message-add-in.md)|Werkt met Outlook en Outlook op het web (voorheen bekend als Outlook Web App). <p> Afhankelijk van uw abonnement zijn berichten die gebruikers met de invoegvoegingen hebben gerapporteerd, beschikbaar in de portal Admin [Submissions,](admin-submission.md) [Automated investigation and response (AIR),](air-view-investigation-results.md)the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and Threat [Explorer](threat-explorer-views.md#email--submissions). <p> U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)
|[Fout-positieven en onwaar-negatieven rapporteren aan Outlook](report-false-positives-and-false-negatives.md)|Verzend fout-positieven (goede e-mail die is geblokkeerd of verzonden naar de map Ongewenste e-mail) en onwaar negatieven (ongewenste e-mail of phish die in het Postvak IN is bezorgd) naar Exchange Online Protection (EOP) met de functie Rapportbericht.|
|[Berichten handmatig indienen bij Microsoft voor analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Handmatig bijgevoegde berichten verzenden naar specifieke Microsoft-e-mailadressen voor spam, geen spam en phishing.|
|[Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Meer informatie over het maken van een regel voor e-mailstroom (ook wel transportregel genoemd) die u op de melding stelt wanneer gebruikers berichten rapporteren aan Microsoft voor analyse.|
|[Malware en niet-malware indienen bij Microsoft voor analyse](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Gebruik de Microsoft-beveiligingsinformatie site om bijlagen en andere bestanden in te dienen.|

Als de spam- of phishingberichten in quarantaine zijn geplaatst in plaats van bezorgd, kunnen gebruikers de berichten rapporteren aan Microsoft via de quarantaineportal in het Beveiligings- & Compliancecentrum. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in](find-and-release-quarantined-messages-as-a-user.md)Microsoft 365.

> [!NOTE]
> Gegevens uit inzendingen naar Microsoft bevinden zich in de Office 365 compliancegrens in Noord-Amerikaanse datacenters. De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te verbeteren.
