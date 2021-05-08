---
title: Overzicht van beveiligingsdashboard
f1.keywords:
- NOCSH
ms.author: siosulli
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Gebruik het nieuwe beveiligingsdashboard om de Office 365 status van bedreigingsbeveiliging te bekijken en beveiligingswaarschuwingen weer te geven en op te treden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 71c077853c8dbb68b78c8073f650bcb2df4d1b9a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246451"
---
# <a name="security-dashboard"></a>Beveiligingsdashboard

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Basisfuncties en het openen van beveiligingsdashboard

Met [het beveiligings- & compliancecentrum](../../compliance/microsoft-365-compliance-center.md) kan uw organisatie gegevensbescherming en compliance beheren. Ervan uitgaande dat u de benodigde machtigingen hebt, kunt u met het beveiligingsdashboard uw status van bedreigingsbeveiliging bekijken en beveiligingswaarschuwingen bekijken en handelen.

Bekijk de video om een overzicht te krijgen en lees dit artikel voor meer informatie.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Afhankelijk van wat het abonnement van uw organisatie bevat, bevat het beveiligingsdashboard verschillende widgets, zoals Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware en meer, zoals beschreven in de volgende secties.

Als u het beveiligingsdashboard wilt weergeven, gaat u in [& Beveiligingscentrum](../../compliance/microsoft-365-compliance-center.md)naar **Dashboard voor bedreigingsbeheer.** \> 

> [!NOTE]
> U moet een globale beheerder, een beveiligingsbeheerder of een beveiligingslezer zijn om het beveiligingsdashboard te kunnen bekijken. Voor sommige widgets zijn extra machtigingen vereist om deze weer te geven. Zie Machtigingen in het Beveiligings- & [compliancecentrum voor meer informatie.](permissions-in-the-security-and-compliance-center.md)

## <a name="threat-management-summary"></a>Overzicht van bedreigingsbeheer

In de widget Overzicht van bedreigingsbeheer ziet u in één oogopslag hoe uw organisatie de afgelopen zeven (7) dagen is beveiligd tegen bedreigingen.

![Beveiligingsdashboard - Widget Overzicht van bedreigingsbeheer](../../media/SecDash-ThreatMgmtSummary.png)

De informatie die u ziet in het overzicht bedreigingsbeheer, is afhankelijk van wat u in uw abonnement hebt. In de volgende tabel wordt beschreven welke informatie is opgenomen voor Office 365 E3 en Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Malwareberichten geblokkeerd<br>Phishingberichten geblokkeerd<br>Berichten die door gebruikers zijn gerapporteerd<br><br><br><br>|Malwareberichten geblokkeerd<br>Phishingberichten geblokkeerd<br>Berichten die door gebruikers zijn gerapporteerd<br>Zero-day malware geblokkeerd<br>Geavanceerde phishingberichten gedetecteerd<br>Kwaadaardige URL's geblokkeerd|

Als u de widget Overzicht van bedreigingsbeheer wilt bekijken of openen, moet u over machtigingen voor het weergeven van Defender voor Office 365 rapporten. Zie Welke machtigingen zijn nodig voor het weergeven van de Defender voor Office 365 [rapporten? voor meer informatie.](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="threat-protection-status"></a>Status van bedreigingsbeveiliging

De widget Bedreigingsbeveiligingsstatus toont de effectiviteit van bedreigingsbeveiliging met een trending en gedetailleerde weergave van phish en malware.

![Statuswidget bedreigingsbeveiliging](../../media/tpswidget.png)

De details zijn afhankelijk van of [](exchange-online-protection-overview.md) uw Microsoft 365 abonnement Exchange Online Protection (EOP) met of zonder Microsoft Defender voor [Office 365.](defender-for-office-365.md)

|Als uw abonnement...|U ziet deze details|
|---|---|
|EOP maar niet Microsoft Defender voor Office 365|Schadelijke e-mail die is gedetecteerd en geblokkeerd door EOP.<p> Zie [Threat Protection Status report (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Microsoft Defender voor Office 365|Schadelijke inhoud en schadelijke e-mail gedetecteerd en geblokkeerd door EOP en Defender voor Office 365 <p> Samengevoegd aantal unieke [e-mailberichten](zero-hour-auto-purge.md)met schadelijke inhoud die is geblokkeerd door de anti-malware-engine, automatische nuluursre purge en Defender voor Office 365-functies (waaronder [Safe Koppelingen,](safe-links.md) [Safe Bijlagen](safe-attachments.md)en [Anti-phishing in Defender voor Office 365).](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) <p> Zie [Statusrapport bedreigingsbeveiliging](view-reports-for-mdo.md#threat-protection-status-report).|

Als u de widget Status van bedreigingsbeveiliging wilt bekijken of openen, moet u over machtigingen voor het weergeven van Defender voor Office 365 rapporten. Zie Welke machtigingen zijn nodig voor het weergeven van de Defender voor Office 365 [rapporten?](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

## <a name="global-weekly-threat-detections"></a>Globale wekelijkse bedreigingsdetecties

De widget Globale wekelijkse bedreigingsdetecties laat zien hoeveel bedreigingen in e-mailberichten zijn gedetecteerd in de afgelopen zeven (7) dagen.

![Global Weekly Threat Detections widget](../../media/globalweeklythreatdetections.png)

De metrische gegevens worden berekend zoals beschreven in de volgende tabel:

|Metrische|Berekenings- en berekenings-|
|---|---|
|Gescande berichten|Aantal gescande e-mailberichten vermenigvuldigd met het aantal geadresseerden|
|Bedreigingen gestopt|Aantal e-mailberichten dat is geïdentificeerd als malware, vermenigvuldigd met het aantal geadresseerden|
|Geblokkeerd door [Defender voor Office 365](defender-for-office-365.md)|Aantal e-mailberichten geblokkeerd door Defender voor Office 365 vermenigvuldigd met het aantal geadresseerden|
|Verwijderd na de bezorging|Aantal berichten verwijderd door [automatische nul-uurs purge](zero-hour-auto-purge.md) vermenigvuldigd met het aantal geadresseerden|

## <a name="malware"></a>Malware

Malwarewidgets bevatten details over malwaretrends en malwarefamilietypen in de afgelopen zeven (7) dagen.

![Malwaretrends en gezinstypen](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Inzichten

Inzichten die u niet alleen moet bekijken, maar ook aanbevelingen en acties die u moet overwegen.

![Slimme inzichten](../../media/smartinsights.png)

U ziet bijvoorbeeld dat phishing-e-mailberichten worden bezorgd omdat sommige gebruikers hun opties voor ongewenste e-mail hebben uitgeschakeld. Zie Rapporten en inzichten in het beveiligings- & compliancecentrum voor meer [informatie over hoe inzichten werken.](reports-and-insights-in-security-and-compliance.md)

## <a name="threat-investigation-and-response"></a>Bedreigingsonderzoek en -reactie

Als het abonnement van uw organisatie Microsoft Defender voor Office 365 [plan 2](office-365-ti.md)bevat, bevat uw beveiligingsdashboard een sectie met geavanceerde hulpprogramma's voor onderzoek naar bedreigingen en antwoordhulpmiddelen. Deze hulpprogramma's [omvatten geautomatiseerde onderzoeks- en antwoordmogelijkheden.](automated-investigation-response-office.md) Geautomatiseerde onderzoeken en antwoorden kunnen nuttig zijn in scenario's, zoals het snel aanpakken van [gecompromitteerde gebruikersaccounts.](address-compromised-users-quickly.md)

Zie Aan de slag met Geautomatiseerde onderzoeken en [antwoorden (AIR) in](office-365-air.md)Office 365.

## <a name="trends"></a>Trends

Onder aan het beveiligingsdashboard ziet u een **sectie Trends,** waarin e-mailstroomtrends voor uw organisatie worden samengevat. Rapporten bevatten informatie over e-mail die is gecategoriseerd als spam, malware, phishingpogingen en goede e-mail. Klik op een tegel om meer gedetailleerde informatie in het rapport weer te geven.

![De sectie Trends bevat een overzicht van e-mailstroomtrends voor de organisatie](../../media/trends.png)

En als het abonnement van uw organisatie Defender voor [Office 365 Plan 2](office-365-ti.md)bevat, bevat deze sectie ook een rapport Met waarschuwingen voor recent bedreigingsbeheer waarmee uw beveiligingsteam beveiligingswaarschuwingen met hoge prioriteit kan bekijken en actie kunnen ondernemen. 

Als u de widget Verzonden en ontvangen e-mail wilt bekijken of openen, moet u over machtigingen voor het weergeven van Defender voor Office 365 rapporten. Zie Welke machtigingen zijn nodig voor het weergeven van de Defender voor Office 365 [rapporten? voor meer informatie.](view-reports-for-mdo.md#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)

Als u de widget Recente bedreigingsbeheerwaarschuwingen wilt bekijken of openen, moet u machtigingen hebben om waarschuwingen weer te geven. Zie [RBAC-machtigingen die nodig zijn om](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)waarschuwingen weer te geven voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

[E-mailbeveiligingsrapporten weergeven in het beveiligings- & compliancecentrum](view-email-security-reports.md)

[Rapporten weergeven voor Microsoft Defender voor Office 365](view-reports-for-mdo.md)

[Defender voor Office 365](defender-for-office-365.md)

[Office 365 Bedreigingsonderzoek en -reactie](office-365-ti.md)