---
title: Overzicht van beveiligings dashboard
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
ms.custom:
- seo-marvel-apr2020
description: Gebruik het nieuwe beveiligings dashboard om de status van de Bedreigingsbeveiliging van Office 365 te controleren en beveiligingswaarschuwingen weer te geven en te ondernemen.
ms.openlocfilehash: 1bef6d0496c39d5157bbc40893d2710e89d1c734
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200071"
---
# <a name="security-dashboard"></a>Beveiligings dashboard

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


## <a name="basic-functions-and-how-to-open-security-dashboard"></a>Basisfuncties en beveiligings dashboard openen

Met de [beveiligings & nalevings centrum](../../compliance/go-to-the-securitycompliance-center.md) kan uw organisatiegegevens bescherming en compliance beheren. Als u de benodigde machtigingen hebt, kunt u met het beveiligings dashboard de status van Bedreigingsbeveiliging controleren en ook de beveiligingswaarschuwingen weergeven en Toep treden.

Bekijk de video om een overzicht te krijgen en lees dit artikel voor meer informatie.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1VV3o]

Afhankelijk van wat het abonnement van uw organisatie is, bevat het beveiligings dashboard diverse widgets, zoals het overzicht van risicobeheer, de status van Bedreigingsbeveiliging, globale wekelijkse bedreigingen detectie, malware en meer, zoals beschreven in de volgende secties.

Als u het beveiligings dashboard wilt weergeven, gaat u naar het hulpmiddel voor het **beheer van bedreigingen** van [beveiligings &](../../compliance/go-to-the-securitycompliance-center.md) \> **Dashboard**.

> [!NOTE]
> U moet een globale beheerder, een beveiligingsbeheerder of een beveiligings lezer zijn om het beveiligings dashboard te kunnen bekijken. Voor sommige objecten hebt u extra machtigingen nodig om weer te geven. Zie voor meer informatie [machtigingen in de beveiligings & nalevings centrum](permissions-in-the-security-and-compliance-center.md).

## <a name="threat-management-summary"></a>Overzicht van risicobeheer

De widget beknopte bedreigings beheer vertelt u in één oogopslag hoe uw organisatie is beveiligd tegen bedreigingen in de afgelopen zeven (7) dagen.

![Beveiligings Dashboard: overzicht van de widget risicobeheer](../../media/SecDash-ThreatMgmtSummary.png)

De informatie die u in het overzicht van risicobeheer ziet, is afhankelijk van het abonnement dat u hebt inbegrepen. In de volgende tabel wordt beschreven welke informatie is opgenomen in Office 365 E3 en Office 365 E5.

|Office 365 E3|Office 365 E5|
|---|---|
|Malware-berichten geblokkeerd<br/>Malafide berichten geblokkeerd<br>Berichten aangegeven door gebruikers<br><br><br><br>|Malware-berichten geblokkeerd<br>Malafide berichten geblokkeerd<br>Berichten aangegeven door gebruikers<br>Malware blokkeren op nul dagen<br>Geavanceerde phishingberichten gevonden<br>Geblokkeerde schadelijke Url's|

Als u de functie voor het risicobeheer wilt weergeven of gebruiken, moet u beschikken over machtigingen voor het weergeven van de rapporten over de geavanceerde beveiliging van bedreigingen. Zie [de bewaarde machtigingen voor het weergeven van de ATP-rapporten](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)voor meer informatie.

## <a name="threat-protection-status"></a>Status van bedreigingsbeveiliging

De widget bedreigings bescherming toont de effectiviteit van bedreiging voor een overzicht van de effectiviteit en malware van de bedreiging.

![Widget status van bedreigings bescherming](../../media/tpswidget.png)

De details zijn afhankelijk van het feit of uw Microsoft 365-abonnement [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) omvat of zonder [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP).

|Als uw abonnement dit omvat...|Deze gegevens worden weergegeven|
|---|---|
|EOP, maar niet Office 365 ATP|Schadelijke e-mail die is gedetecteerd en geblokkeerd door EOP.<br><br> Zie [status rapport Threat Protection (EOP)](view-email-security-reports.md#threat-protection-status-report).|
|Office 365 ATP|Schadelijke inhoud en kwaadaardige e-mail detectie en geblokkeerde e-mail door EOP en Office 365 ATP<br><br>Totaal aantal unieke e-mailberichten met schadelijke inhoud geblokkeerd door de anti-malware-engine, [automatisch opschonen van Zero uur](zero-hour-auto-purge.md)en ATP-functies (waaronder [veilige koppelingen](atp-safe-links.md), [veilige bijlagen](atp-safe-attachments.md)en [ATP anti-phishing](set-up-anti-phishing-policies.md#exclusive-settings-in-atp-anti-phishing-policies)).<br><br>Zie [statusrapport Threat Protection (ATP)](view-reports-for-atp.md#threat-protection-status-report).|

U moet beschikken over machtigingen voor het weergeven van de rapporten over de Bedreigingsbeveiliging als u de widget beveiligings status van bedreiging wilt weergeven of gebruiken. Voor meer informatie raadpleegt [u de machtigingen die nodig zijn voor het weergeven van de ATP-rapporten?](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)

## <a name="global-weekly-threat-detections"></a>Wereldwijde detectie van wekelijkse bedreiging

De widget wereldwijde detectie van wekelijkse bedreiging laat zien hoeveel bedreigingen zijn gedetecteerd in e-mailberichten in de afgelopen zeven (7) dagen.

![Algemene wekelijkse bedreiging detectie-widget](../../media/globalweeklythreatdetections.png)

De meetwaarden worden berekend zoals wordt beschreven in de volgende tabel:

|Gegevens|De berekening|
|---|---|
|Gescande berichten|Aantal gescande e-mailberichten vermenigvuldigd met het aantal geadresseerden|
|Bedreigingen beëindigd|Het aantal e-mailberichten dat wordt aangegeven met malware vermenigvuldigd met het aantal geadresseerden|
|Geblokkeerd door [ATP](office-365-atp.md)|Aantal e-mailberichten die zijn geblokkeerd door ATP, vermenigvuldigd met het aantal geadresseerden|
|Verwijderd na levering|Aantal verwijderde berichten door een [0 uur automatisch wissen](zero-hour-auto-purge.md) vermenigvuldigd met het aantal geadresseerden|

## <a name="malware"></a>Malware

Widgets van malware toont details over trends van malware en familie van malware in de afgelopen zeven (7) dagen.

![Trends en familie types van malware](../../media/malwarewidgetatpe5.png)

## <a name="insights"></a>Inzichten

Voor inzichten die u niet alleen moet nakijken, bevatten ze ook aanbevelingen en acties waarmee u rekening moet houden.

![Slimme inzichten](../../media/smartinsights.png)

U ziet bijvoorbeeld dat e-mailberichten van phishingberichten worden bezorgd omdat sommige gebruikers hun opties voor ongewenste e-mail hebben uitgeschakeld. Zie [rapporten en inzichten in het beveiligings & nalevings centrum](reports-and-insights-in-security-and-compliance.md)voor meer informatie over de werking van inzichten.

## <a name="threat-investigation-and-response"></a>Threat onderzoek en-antwoord

Als het abonnement van uw organisatie  [Office 365 Advanced Threat Protection](office-365-ti.md)(abonnement 2) bevat, bevat uw beveiligings Dashboard een sectie met geavanceerde functies voor onderzoek en antwoorden. Dit zijn [geautomatiseerde onderzoek-en antwoord mogelijkheden](automated-investigation-response-office.md). Geautomatiseerd onderzoek en reactie kunnen handig zijn in scenario's, zoals het doorlopen van [gebruikersaccounts met compromissen](address-compromised-users-quickly.md).

Zie [aan de slag met geautomatiseerd onderzoek en antwoord (lucht) in Office 365](office-365-air.md)voor meer informatie.

## <a name="trends"></a>Duidelijk

Onder in het beveiligings dashboard is een sectie **trends** , een overzicht van de trends van een e-mail stroom voor uw organisatie. Rapporten bevatten informatie over e-mailberichten die zijn gecategoriseerd als spam, malware, phishing en goede e-mail. Klik op een tegel om meer gedetailleerde informatie weer te geven in het rapport.

![De sectie trends bevat een overzicht van de trends van een e-mail stroom voor de organisatie](../../media/trends.png)

En als het abonnement van uw organisatie [Office 365 Advanced Threat Protection](office-365-ti.md)(abonnement 2) bevat, hebt u ook een recent rapport met **meldingen over risicobeheer** in deze sectie waarmee uw beveiligingsteam op de hoogte wordt gesteld van beveiligingsmeldingen met een hoge prioriteit.

Als u de widget verzonden en ontvangen E-mail wilt weergeven of openen, moet u beschikken over machtigingen voor het weergeven van de rapporten over de geavanceerde beveiliging van bedreigingen. Zie [de bewaarde machtigingen voor het weergeven van de ATP-rapporten](view-reports-for-atp.md#what-permissions-are-needed-to-view-the-atp-reports)voor meer informatie.

Als u de recente widget meldingen van bedreigings beheer wilt weergeven of gebruiken, moet u beschikken over machtigingen voor het weergeven van waarschuwingen. Zie voor meer informatie de [rechten voor het weergeven van waarschuwingen](../../compliance/alert-policies.md#rbac-permissions-required-to-view-alerts).

## <a name="related-topics"></a>Verwante onderwerpen

[Beveiligingsrapporten voor e-mail weergeven in het beveiligings & nalevings centrum](view-email-security-reports.md)

[Rapporten weergeven voor Office 365 Advanced Threat Protection](view-reports-for-atp.md)

[Office 365 Advanced Threat Protection](office-365-atp.md)

[Office 365 Threat onderzoek en-antwoord](office-365-ti.md)
