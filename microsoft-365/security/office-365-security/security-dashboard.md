---
title: Overzicht van beveiligingsdashboards
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gebruik het nieuwe beveiligingsdashboard om de status van Bedreigingsbeveiliging in Office 365 te controleren en beveiligingswaarschuwingen weer te geven en er actie op te ondernemen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 72743f1b052d39ac4762dffc0b3e3e694befa8bc
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "50288321"
---
# <a name="security-dashboard"></a>Beveiligingsdashboard

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Basisfuncties en het openen van het beveiligingsdashboard

Met [het & compliancecentrum kan](../../compliance/go-to-the-securitycompliance-center.md) uw organisatie gegevensbescherming en naleving beheren. Als u de benodigde machtigingen hebt, kunt u met het beveiligingsdashboard de status van bedreigingsbeveiliging bekijken en beveiligingswaarschuwingen bekijken en in actie brengen.

Bekijk de video voor een overzicht en lees dit artikel voor meer informatie.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Afhankelijk van het abonnement van uw organisatie bevat het beveiligingsdashboard verschillende widgets, zoals Bedreigingsbeheeroverzicht, Status van bedreigingsbeveiliging, Globale wekelijkse bedreigingsdetectie, malware en meer, zoals in de volgende secties.

Als u het beveiligingsdashboard wilt bekijken, gaat u in het & [Compliancecentrum](../../compliance/go-to-the-securitycompliance-center.md)naar Dashboard voor **bedreigingsbeheer.** \> 

> [!NOTE]
> U moet een globale beheerder, een beveiligingsbeheerder of een beveiligingslezer zijn om het beveiligingsdashboard te kunnen bekijken. Voor sommige widgets zijn extra machtigingen vereist om ze te kunnen bekijken. Zie Machtigingen in het beveiligings- en & [voor meer informatie.](permissions-in-the-security-and-compliance-center.md)

## <a name="threat-management-summary"></a>Overzicht van bedreigingsbeheer

Met de widget Bedreigingsbeheeroverzicht ziet u in één oogopslag hoe uw organisatie de afgelopen zeven (7) dagen is beveiligd tegen bedreigingen.

![Security Dashboard - Threat Management Summary widget](../../media/SecDash-ThreatMgmtSummary.png)

De informatie die u in het overzicht van Bedreigingsbeheer ziet, is afhankelijk van wat uw abonnement omvat. In de volgende tabel wordt beschreven welke gegevens zijn opgenomen voor Office 365 E3 en Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Geblokkeerde malwareberichten<br>Phishing-berichten geblokkeerd<br>Berichten die door gebruikers zijn gerapporteerd<br><br><br><br>|Geblokkeerde malwareberichten<br>Phishing-berichten geblokkeerd<br>Berichten die door gebruikers zijn gerapporteerd<br>Zero-day malware geblokkeerd<br>Geavanceerde phishingberichten gedetecteerd<br>Schadelijke URL's geblokkeerd|

Als u de overzichtswidget Bedreigingsbeheer wilt weergeven of openen, moet u machtigingen hebben om Defender voor Office 365-rapporten weer te geven. Zie Welke machtigingen zijn nodig om Defender voor [Office 365-rapporten](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)weer te geven voor meer informatie?

## <a name="threat-protection-status"></a>Status van bedreigingsbeveiliging

De widget Status van bedreigingsbeveiliging toont effectiviteit van bedreigingsbeveiliging met een trending en gedetailleerde weergave van phish en malware.

![Widget Status van bedreigingsbeveiliging](../../media/tpswidget.png)

De details zijn afhankelijk van of uw Microsoft 365-abonnement [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) omvat met of zonder Microsoft Defender voor Office [365.](office-365-atp.md)

|Als uw abonnement...|U ziet deze details|
|---|---|
|EOP, maar niet Microsoft Defender voor Office 365|Schadelijke e-mail die is gedetecteerd en geblokkeerd door EOP.<p> Zie [het rapport Threat Protection Status (EOP).](view-email-security-reports.md#threat-protection-status-report)|
|Microsoft Defender voor Office 365|Schadelijke inhoud en schadelijke e-mail gedetecteerd en geblokkeerd door EOP en Defender voor Office 365 <p> Geaggregeerd aantal unieke [e-mailberichten](zero-hour-auto-purge.md)met schadelijke inhoud die wordt geblokkeerd door de antimalware-engine, automatische nul-uurs purge en Defender voor Office 365-functies (waaronder [veilige](atp-safe-links.md) [koppelingen,](atp-safe-attachments.md)veilige bijlagen en [anti-phishing in Defender voor Office 365).](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) <p> Zie [het statusrapport Van bedreigingsbeveiliging.](view-reports-for-atp.md#threat-protection-status-report)|

Als u de widget Status van bedreigingsbeveiliging wilt weergeven of openen, moet u machtigingen hebben om Defender voor Office 365-rapporten weer te geven. Zie Welke machtigingen zijn nodig om Defender voor [Office 365-rapporten](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports) weer te geven voor meer informatie?

## <a name="global-weekly-threat-detections"></a>Globale wekelijkse bedreigingsdetectie

De widget Globale wekelijkse bedreigingsdetectie laat zien hoeveel bedreigingen er zijn gedetecteerd in e-mailberichten in de afgelopen zeven (7) dagen.

![Algemene widget Wekelijkse bedreigingsdetectie](../../media/globalweeklythreatdetections.png)

De meetwaarden worden berekend zoals wordt beschreven in de volgende tabel:

|Metrisch|De berekening|
|---|---|
|Gescande berichten|Het aantal gescande e-mailberichten vermenigvuldigd met het aantal geadresseerden|
|Bedreigingen gestopt|Aantal e-mailberichten dat is geïdentificeerd als malware, vermenigvuldigd met het aantal geadresseerden|
|Geblokkeerd door [Defender voor Office 365 ](office-365-atp.md)|Het aantal e-mailberichten dat wordt geblokkeerd door Defender voor Office 365 vermenigvuldigd met het aantal geadresseerden|
|Verwijderd na levering|Het aantal berichten dat is verwijderd [met automatisch](zero-hour-auto-purge.md) verwijderen van nul uur vermenigvuldigd met het aantal geadresseerden|

## <a name="malware"></a>Malware

Malwarewidgets bevatten informatie over malwaretrends en malwarefamilietypen in de afgelopen zeven (7) dagen.

![Malwaretrends en -familietypen](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Inzichten

Inzichten bevatten niet alleen belangrijke punten die u moet bekijken, maar ook aanbevelingen en acties die u kunt overwegen.

![Slimme inzichten](../../media/smartinsights.png)

Zo kunt u bijvoorbeeld zien dat phishing-e-mailberichten worden bezorgd omdat sommige gebruikers de opties voor ongewenste e-mail hebben uitgeschakeld. Zie Rapporten en inzichten in het beveiligings- en compliancecentrum voor meer informatie & [inzichten.](reports-and-insights-in-security-and-compliance.md)

## <a name="threat-investigation-and-response"></a>Bedreigingsonderzoek en reactie

Als het abonnement van uw organisatie Microsoft Defender voor  [Office 365 Plan 2](office-365-ti.md)bevat, bevat uw beveiligingsdashboard een sectie met geavanceerd onderzoek naar bedreigingen en reactiehulpprogramma's. Deze hulpprogramma's [omvatten geautomatiseerde onderzoeks- en antwoordmogelijkheden.](automated-investigation-response-office.md) Automatisch onderzoek en antwoorden kunnen handig zijn in scenario's zoals het snel aanpakken van [gekromde gebruikersaccounts.](address-compromised-users-quickly.md)

Zie Aan de slag met Automatisch onderzoek en reactie [(AIR) in Office 365 voor meer informatie.](office-365-air.md)

## <a name="trends"></a>Trends

Onder aan het beveiligingsdashboard ziet u een **sectie Trends,** waarin de e-mailstroomtrends voor uw organisatie worden samengevat. Rapporten bevatten informatie over e-mail die is gecategoriseerd als spam, malware, phishingpogingen en goede e-mail. Klik op een tegel om meer gedetailleerde informatie in het rapport weer te geven.

![De sectie Trends bevat een overzicht van e-mailstroomtrends voor de organisatie](../../media/trends.png)

En als het abonnement van uw organisatie Defender voor [Office 365 Plan 2](office-365-ti.md)bevat, bevat deze sectie ook een rapport met recente waarschuwingen voor bedreigingsbeheer waarmee uw beveiligingsteam beveiligingswaarschuwingen met hoge prioriteit kan bekijken en er actie op kan ondernemen. 

Als u de widget Verzonden en ontvangen e-mail wilt weergeven of openen, moet u machtigingen hebben om Defender voor Office 365-rapporten weer te geven. Zie Welke machtigingen zijn nodig om Defender voor [Office 365-rapporten](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)weer te geven voor meer informatie?

Als u de widget Recente bedreigingsbeheerwaarschuwingen wilt weergeven of openen, moet u machtigingen hebben om waarschuwingen weer te geven. Zie VOOR MEER INFORMATIE DE [VEREISTE TOEGANGSSTRUCTUUR-machtigingen om waarschuwingen weer te geven.](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)

## <a name="related-topics"></a>Verwante onderwerpen

[Beveiligingsrapporten voor e-mail weergeven in het & compliancecentrum](view-email-security-reports.md)

[Rapporten voor Microsoft Defender voor Office 365 weergeven](view-reports-for-atp.md)

[Defender voor Office 365](office-365-atp.md)

[Bedreigingsonderzoek en -reactie voor Office 365](office-365-ti.md)
