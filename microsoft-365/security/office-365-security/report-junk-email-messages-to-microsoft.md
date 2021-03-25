---
title: Spam, niet-spam en phishingberichten rapporteren aan Microsoft
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
ms.openlocfilehash: 64b5708194d7597b8a2b1a84b51f2196415e56ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204715"
---
# <a name="report-messages-and-files-to-microsoft"></a>Berichten en bestanden rapporteren aan Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken, hebben zowel gebruikers als beheerders verschillende methoden voor het rapporteren van e-mailberichten en bestanden aan Microsoft.

****

|Methode|Beschrijving|
|---|---|
|[Beheerdersinzending gebruiken om verdachte spam, phish, URL's en bestanden naar Microsoft te verzenden](admin-submission.md)|De aanbevolen rapportagemethode voor beheerders in organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP).|
|[De invoegtoepassing Bericht rapporteren inschakelen](enable-the-report-message-add-in.md)|Werkt met de webversie van Outlook en Outlook (voorheen bekend als Outlook Web App). <p> Afhankelijk van uw abonnement zijn berichten die gebruikers hebben gerapporteerd met de invoegvoeging beschikbaar in de portal Admin [Submissions](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and Threat [Explorer](threat-explorer-views.md#email--submissions). <p> U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)
|[De invoegtoepassing Phishing rapporteren inschakelen](enable-the-report-phish-add-in.md)|Werkt met de webversie van Outlook en Outlook (voorheen bekend als Outlook Web App). <p> Afhankelijk van uw abonnement zijn berichten die gebruikers hebben gerapporteerd met de invoegvoeging beschikbaar in de portal Admin [Submissions](admin-submission.md), [Automated investigation and response (AIR) results](air-view-investigation-results.md), the [User-reported messages report](view-email-security-reports.md#user-reported-messages-report), and Threat [Explorer](threat-explorer-views.md#email--submissions). <p> U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)|
|[De invoegversie voor het rapporteren van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken](junk-email-reporting-add-in-for-microsoft-outlook.md)|Werkt alleen in Outlook.|
|[Ongewenste e-mail en phishing-e-mail rapporteren in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Gebruik de ingebouwde mogelijkheden in de webversie van Outlook voor organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP). <p> Berichten die gebruikers rapporteren, zijn beschikbaar in [de portal Beheerdersinzendingen.](admin-submission.md) <p> U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)|
|[Ongewenste e-mail en phishing-e-mail rapporteren in Outlook voor iOS en Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Gebruik de ingebouwde mogelijkheden in Outlook voor iOS en Android voor organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP). <p> Berichten die gebruikers rapporteren, zijn beschikbaar in [de portal Beheerdersinzendingen.](admin-submission.md) <p> U kunt gerapporteerde berichten zo configureren dat ze worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzendingen voor meer informatie.](user-submission.md)|
|[Berichten handmatig indienen bij Microsoft voor analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Handmatig bijgevoegde berichten verzenden naar specifieke Microsoft-e-mailadressen voor spam, geen spam en phishing.|
|[Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Meer informatie over het maken van een regel voor e-mailstroom (ook wel transportregel genoemd) die u op de melding stelt wanneer gebruikers berichten rapporteren aan Microsoft voor analyse.|
|[Malware en niet-malware indienen bij Microsoft voor analyse](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Gebruik de Microsoft Security Intelligence-site om bijlagen en andere bestanden in te dienen.|

Als de spam- of phishingberichten in quarantaine zijn geplaatst in plaats van bezorgd, kunnen gebruikers de berichten rapporteren aan Microsoft via de quarantaineportal in het Beveiligings- & Compliancecentrum. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in Microsoft 365](find-and-release-quarantined-messages-as-a-user.md)voor meer informatie.

> [!NOTE]
> Gegevens uit inzendingen naar Microsoft bevinden zich in de nalevingsgrens van Office 365 in Noord-Amerikaanse datacenters. De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te verbeteren.
