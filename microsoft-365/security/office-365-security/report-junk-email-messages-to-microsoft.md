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
description: Beheerders kunnen meer te weten komen over de verschillende manieren waarop ze goede en slechte berichten en bestanden voor analyse bij Microsoft kunnen rapporteren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 21c733945256386ff9543b372badaa6f2302171b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288089"
---
# <a name="report-messages-and-files-to-microsoft"></a>Berichten en bestanden rapporteren aan Microsoft

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In Microsoft 365-organisaties met postvakken in Exchange Online of zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken hebben zowel gebruikers als beheerders verschillende methoden voor het rapporteren van e-mailberichten en bestanden naar Microsoft.

****

|Methode|Beschrijving|
|---|---|
|[Inzending door beheerder gebruiken om verdachte spam, phish, URL's en bestanden bij Microsoft in te dienen](admin-submission.md)|De aanbevolen rapportagemethode voor beheerders in organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP).|
|[De invoegtoepassing Bericht rapporteren inschakelen](enable-the-report-message-add-in.md)|Werkt met Outlook en de webversie van Outlook (voorheen Bekend als Outlook Web App). <p> Afhankelijk van uw abonnement zijn berichten die gebruikers bij de invoeging hebben gerapporteerd, beschikbaar in de [](view-email-security-reports.md#user-reported-messages-report)beheerportal, de resultaten van Automatisch onderzoek en antwoorden [(AIR),](air-view-investigation-results.md)het rapport Met de gebruiker gerapporteerde berichten en [Bedreigingsverkenner.](threat-explorer-views.md#email--submissions) [](admin-submission.md) <p> U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)
|[De invoegtoepassing Phishing rapporteren inschakelen](enable-the-report-phish-add-in.md)|Werkt met Outlook en de webversie van Outlook (voorheen Bekend als Outlook Web App). <p> Afhankelijk van uw abonnement zijn berichten die gebruikers bij de invoeging hebben gerapporteerd, beschikbaar in de [](view-email-security-reports.md#user-reported-messages-report)portal Admin Submissions, de resultaten van Automatisch onderzoek en antwoorden [(AIR),](air-view-investigation-results.md)het rapport Met de gebruiker gerapporteerde berichten en [Bedreigingsverkenner.](threat-explorer-views.md#email--submissions) [](admin-submission.md) <p> U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)|
|[De invoegversie voor rapportage van ongewenste e-mail voor Microsoft Outlook installeren en gebruiken](junk-email-reporting-add-in-for-microsoft-outlook.md)|Werkt alleen in Outlook.|
|[Ongewenste e-mail en phishing-e-mail melden in de webversie van Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md)|Gebruik de ingebouwde mogelijkheden in de webversie van Outlook voor organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP). <p> Berichten die gebruikers melden, zijn beschikbaar in [de portal Voor het indienen van beheerders.](admin-submission.md) <p> U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)|
|[Ongewenste e-mail en phishing-e-mail melden in Outlook voor iOS en Android](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)|Gebruik de ingebouwde mogelijkheden in Outlook voor iOS en Android voor organisaties met Exchange Online-postvakken (niet beschikbaar in zelfstandige EOP). <p> Berichten die gebruikers melden, zijn beschikbaar in [de portal Voor het indienen van beheerders.](admin-submission.md) <p> U kunt gerapporteerde berichten configureren om te worden gekopieerd of omgeleid naar een postvak dat u opgeeft. Zie Beleidsregels voor [gebruikersinzending voor meer informatie.](user-submission.md)|
|[Berichten handmatig naar Microsoft verzenden voor analyse](submit-spam-non-spam-and-phishing-scam-messages-to-microsoft-for-analysis.md)|Stuur handmatig bijgevoegde berichten naar specifieke Microsoft-e-mailadressen voor spam, geen spam en phishing.|
|[Regels voor e-mailstromen gebruiken om te zien wat je gebruikers melden bij Microsoft](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)|Lees hoe u een e-mailstroomregel (ook wel transportregel genoemd) maakt die u waarschuwt wanneer gebruikers berichten naar Microsoft rapporteren voor analyse.|
|[Malware en niet-malware bij Microsoft indienen voor analyse](submitting-malware-and-non-malware-to-microsoft-for-analysis.md)|Gebruik de Microsoft Security Intelligence-site om bijlagen en andere bestanden in te dienen.|

Als de spam- of phishingberichten in quarantaine zijn geplaatst in plaats van bezorgd, kunnen gebruikers de berichten aan Microsoft rapporteren vanuit de portal Quarantaine in het & Compliancecentrum. Zie Berichten in quarantaine zoeken en vrijgeven als [gebruiker in Microsoft 365 voor meer informatie.](find-and-release-quarantined-messages-as-a-user.md)

> [!NOTE]
> Gegevens van inzendingen naar Microsoft bevinden zich in de nalevingsgrens van Office 365 in het Noord-Amerikaanse datacenter. De gegevens worden beoordeeld door analisten van het technische team om de effectiviteit van de filters te helpen verbeteren.
