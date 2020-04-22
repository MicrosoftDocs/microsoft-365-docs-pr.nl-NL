---
title: Overzicht van beveiligingsdashboards
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: fe0b9b8f-faa9-44ff-8095-4d1b2f507b74
ms.collection:
- M365-security-compliance
description: Gebruik het nieuwe beveiligingsdashboard om de status van Office 365-bedreigingsbeveiliging te controleren en beveiligingswaarschuwingen te bekijken en te reageren.
ms.openlocfilehash: 3b6d754505d0e23f1080520e66061b8f6fef523e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632515"
---
# <a name="security-dashboard"></a>Beveiligingsdashboard

## <a name="overview"></a>Overzicht

Met [het Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md) kan uw organisatie gegevensbescherming en compliance beheren. Ervan uitgaande dat u over de benodigde machtigingen beschikt, u met het beveiligingsdashboard uw status voor bedreigingsbeveiliging bekijken en beveiligingswaarschuwingen bekijken en reageren.

Bekijk de video om een overzicht te krijgen en lees dit artikel voor meer informatie.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Afhankelijk van wat het abonnement van uw organisatie bevat, bevat het beveiligingsdashboard verschillende widgets, zoals Threat Management Summary, Threat Protection Status, Global Weekly Threat Detections, Malware en meer, zoals beschreven in de volgende secties.

Ga naar **Dashboard voor beveiligingsbeheer** \> om het beveiligingsdashboard in het [Beveiligingscentrum & compliance](../../compliance/go-to-the-securitycompliance-center.md)te bekijken. **Dashboard**

> [!NOTE]
> U moet een globale beheerder, een beveiligingsbeheerder of een beveiligingslezer zijn om het beveiligingsdashboard te kunnen bekijken. Voor sommige widgets zijn extra machtigingen vereist om deze te bekijken. Zie [Machtigingen in het Security & Compliance Center](permissions-in-the-security-and-compliance-center.md)voor meer informatie.

## <a name="threat-management-summary"></a>Samenvatting bedreigingsbeheer

De widget Samenvatting bedreigingsbeheer vertelt u in één oogopslag hoe uw organisatie in de afgelopen zeven (7) dagen tegen bedreigingen is beschermd.

![Beveiligingsdashboard - widget overzicht skader voor bedreigingsbeheer](../../media/SecDash-ThreatMgmtSummary.png)

Welke informatie u ziet in het overzicht bedreigingsbeheer, is afhankelijk van wat u een abonnement bevat. In de volgende tabel wordt beschreven welke informatie is opgenomen voor Office 365 E3 en Office 365 E5.
|||
|---|---|
|**Office 365 E3**|**Office 365 E5**|
|Malwareberichten geblokkeerd<br/>Phishingberichten geblokkeerd<br>Berichten gerapporteerd door gebruikers<br><br><br><br>|Malwareberichten geblokkeerd<br>Phishingberichten geblokkeerd<br>Berichten gerapporteerd door gebruikers<br>Zero-day malware geblokkeerd<br>Geavanceerde phishing-berichten gedetecteerd<br>Schadelijke URL's geblokkeerd|
|

Als u het object Summary voor bedreigingsbeheer wilt bekijken of openen, moet u machtigingen hebben om rapporten over geavanceerde bedreigingsbeveiliging te bekijken. Zie [Welke machtigingen nodig zijn om de ATP-rapporten te bekijken voor](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)meer informatie.

## <a name="threat-protection-status"></a>Status bedreigingsbeveiliging

De Threat Protection Status widget toont threat protection effectiviteit met een trending en gedetailleerde weergave van phish en malware.

![Statuswidget voor bedreigingsbescherming](../../media/tpswidget.png)

De details zijn afhankelijk van de vraag of uw Microsoft 365-abonnement [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) met of zonder Office [365 Advanced Threat Protection](office-365-atp.md) (ATP) bevat.

|||
|---|---|
|**Als uw abonnement...**|**U ziet deze details**|
|EOP maar niet Office 365 ATP|Kwaadaardige e-mail die werd gedetecteerd en geblokkeerd door EOP.<br><br> Zie [Statusrapport bedreigingsbescherming (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Office 365 ATP|Schadelijke inhoud en schadelijke e-mail gedetecteerd en geblokkeerd door EOP en Office 365 ATP<br><br>Geaggregeerde telling van unieke e-mailberichten met schadelijke inhoud geblokkeerd door de anti-malware-engine, [zero-hour automatische zuivering, en ATP-functies](zero-hour-auto-purge.md)(met inbegrip [van veilige links,](atp-safe-links.md) [veilige bijlagen,](atp-safe-attachments.md)en [ATP anti-phishing](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)).<br><br>Zie [Rapport over de status van bedreigingsbescherming (ATP).](view-reports-for-atp.md#threat-protection-status-report)|
|

Als u het object Statusstatus bedreiging wilt bekijken of openen, moet u machtigingen hebben om rapporten over geavanceerde bedreigingsbeveiliging te bekijken. Zie [Welke machtigingen nodig zijn om de ATP-rapporten te bekijken voor](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)meer informatie.

## <a name="global-weekly-threat-detections"></a>Wereldwijde wekelijkse dreigingsdetecties

De widget Global Weekly Threat Detections laat zien hoeveel bedreigingen er de afgelopen zeven (7) dagen in e-mailberichten zijn gedetecteerd.

![Global Weekly Threat Detections widget](../../media/globalweeklythreatdetections.png)

De statistieken worden berekend zoals beschreven in de volgende tabel:

|||
|---|---|
|**Metrische**|**Hoe het wordt berekend**|
|Berichten gescand|Aantal gescande e-mailberichten vermenigvuldigd met het aantal geadresseerden|
|Bedreigingen gestopt|Aantal e-mailberichten dat is geïdentificeerd als malware vermenigvuldigd met het aantal ontvangers|
|Geblokkeerd door [ATP](office-365-atp.md)|Aantal e-mailberichten geblokkeerd door ATP vermenigvuldigd met het aantal ontvangers|
|Verwijderd na levering|Aantal berichten dat is verwijderd met automatische zuivering van [nul uur](zero-hour-auto-purge.md) vermenigvuldigd met het aantal geadresseerden|
|

## <a name="malware"></a>Malware

Malware widgets tonen details over malware trends en malware familie types in de afgelopen zeven (7) dagen.

![Malwaretrends en gezinstypen](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Inzichten

Inzichten komen niet alleen aan de oppervlakte van belangrijke kwesties die u moet bekijken, ze bevatten ook aanbevelingen en acties om rekening mee te houden.

![Slimme inzichten](../../media/smartinsights.png)

U ziet bijvoorbeeld dat phishing-e-mailberichten worden bezorgd omdat sommige gebruikers hun opties voor ongewenste e-mail hebben uitgeschakeld. Zie [Rapporten en inzichten in het Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)voor meer informatie over hoe inzichten werken.

## <a name="threat-investigation-and-response"></a>Onderzoek naar bedreigingen en respons

Als het abonnement van uw organisatie [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)bevat, heeft uw beveiligingsdashboard een sectie met geavanceerde hulpprogramma's voor bedreigingsonderzoek en -respons. Het beveiligingsteam van uw organisatie kan de informatie in deze sectie gebruiken om nieuwe campagnes te begrijpen, bedreigingen te onderzoeken en incidenten te beheren.

![Threat intelligence helpt u bij het begrijpen van aanvallen gericht op uw organisatie](../../media/threatintelwidget.png)

## <a name="trends"></a>Trends

Onderaan het beveiligingsdashboard staat een sectie **Trends,** waarin de trends in de e-mailstroom voor uw organisatie worden samengevat. Rapporten bevatten informatie over e-mail gecategoriseerd als spam, malware, phishing-pogingen en goede e-mail. Klik op een tegel om meer gedetailleerde informatie in het rapport weer te geven.

![De sectie Trends geeft een overzicht van de trends in de e-mailstroom voor de organisatie](../../media/trends.png)

En als het abonnement van uw organisatie [Office 365 Advanced Threat Protection Plan 2](office-365-ti.md)bevat, beschikt u in dit gedeelte ook over een rapport met recente **waarschuwingen voor waarschuwingen** voor bedreigingenbeheer waarmee uw beveiligingsteam beveiligingswaarschuwingen met hoge prioriteit kan bekijken en uitvoeren.

Als u de widget Verzonden en ontvangen e-mail wilt bekijken of openen, moet u machtigingen hebben om rapporten over geavanceerde bedreigingsbeveiliging te bekijken. Zie [Welke machtigingen nodig zijn om de ATP-rapporten te bekijken voor](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)meer informatie.

Als u het object Recente waarschuwingen voor bedreigingsbeheerwaarschuwingen wilt weergeven of openen, moet u machtigingen hebben om waarschuwingen weer te geven. Zie [RBAC-machtigingen die nodig zijn om waarschuwingen weer te geven](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts)voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

[E-mailbeveiligingsrapporten weergeven in het Security & Compliance Center](view-email-security-reports.md)

[Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365](view-reports-for-atp.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Office 365-dreigingsonderzoek en -reactie](office-365-ti.md)
