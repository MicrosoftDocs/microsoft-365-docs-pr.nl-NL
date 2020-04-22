---
title: Rapporten weergeven voor Office 365 Advanced Threat Protection, malwarerapporten, phish-rapporten, gecompromitteerde accounts, URL-beveiligingsstatus, bedreigingsrapportage, meldingen van bedreigingen
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
description: Rapporten zoeken en gebruiken voor Geavanceerde bedreigingsbeveiliging &amp; van Office 365 in het Security Compliance Center.
ms.openlocfilehash: 09e2f4be133d395b738219b3a280f08b915030e0
ms.sourcegitcommit: d4d082292dc711a579fe925ad989ea54ec2e27f4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/22/2020
ms.locfileid: "43708497"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Rapporten weergeven voor geavanceerde bedreigingsbeveiliging van Office 365

Als uw organisatie [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) heeft en u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-atp-reports)beschikt, u verschillende ATP-rapporten gebruiken in het Security &amp; Compliance Center. (Ga naar **Dashboard Rapporten** \> **.)**

![Het &amp; dashboard van het Security Compliance Center kan u helpen te zien waar Advanced Threat Protection werkt](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

ATP-rapporten bevatten het volgende:

- [Statusrapport risicobeveiliging](#threat-protection-status-report)
- [ATP-bestandstyperapport](#atp-file-types-report)
- [ATP-rapport over berichtverwerking](#atp-message-disposition-report)
- [realtime detecties of Explorer](threat-explorer.md) (afhankelijk van of u Office 365 ATP Plan 1 of 2 hebt)
- ... [en meer](#additional-reports-to-view).

Lees dit artikel om een overzicht te krijgen van ATP-rapporten en hoe deze te gebruiken.

## <a name="threat-protection-status-report"></a>Statusrapport risicobeveiliging

Het rapport **Status van bedreigingsbescherming** is één weergave die informatie samenbrengt over schadelijke inhoud en schadelijke e-mail die wordt gedetecteerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Office [365 ATP.](office-365-atp.md) Dit rapport is handig voor het bekijken van detecties in de loop van de tijd (tot 90 dagen) en stelt beveiligingsbeheerders in staat om trends te identificeren of te bepalen of beleid aanpassingen nodig heeft.

Het rapport biedt een geaggregeerdaantal van unieke e-mailberichten met schadelijke inhoud, zoals bestanden of website-adressen (URL's) die werden geblokkeerd door de anti-malware-engine, [zero-hour automatische zuivering (ZAP) en ATP-functies](zero-hour-auto-purge.md)zoals [ATP Safe Links,](atp-safe-links.md) [ATP Safe Attachments](atp-safe-attachments.md)en [ATP anti-phishing](set-up-anti-phishing-policies.md).

Filters en uitsplitsingen van de informatie zorgen voor meer gedetailleerde categorisaties van de informatie in dit rapport. Specifiek, er is een 'break down by' menu opgenomen voor **E-mail** \> **Phish** en **E-mail** \> **Malware weergaven**. Het zal de gegevens opsplitsen in:

|||
|---|---|
|Op detectietype|Welk beleid heeft geholpen deze bedreigingen op te vangen?|
|Door detectietechnologie|Welke onderliggende Microsoft-technologie ving de dreiging?|
|Op leveringsstatus|Wat is er gebeurd met de e-mailberichten gedetecteerd als bedreigingen?|
|

> [!TIP]
> Zowel de e-mail > Phish | Malware weergaven hebben gedetailleerde uitsplitsingen voor de detectie technologieën getoond, met categorieën zoals *ATP-gegenereerde bestandsreputatie*, *File detonatie*, *URL-detonatie*, *Anti-spoof: DMARC mislukking*, bijvoorbeeld, nuttig bij het lokaliseren van precies welke functie leidde uw organisatie om bedreigingen te vangen.

![Dropdown van de Status van bedreigingsstatus toont 'break down by'.](../../media/tp-threatProtectStatRpt-BreakDownBy.png)

Deze weergaven geven u de mogelijkheid om te exporteren, via een knop klik (in **E-mail** \> **Phish**, **E-mail** \> **Malware**, en **Content** \> **Malware** weergaven). De geaggregeerde gegevens die naar uw computer worden geëxporteerd, kunnen worden geopend in Excel.

![In deze afbeelding wordt Exporteren als een optie weergegeven in het menu voor de weergave Malware, precies tussen Planning maken en Rapport aanvragen.](../../media/tp-threatProtectStatRpt-BreakDownByExport.png)

**Opmerking:** Het maximum aantal items dat kan worden geëxporteerd voor **Phish** en **Malware** is iets minder dan 10000. Als u een weergave exporteert, worden alleen de meest recente 10000 vermeldingen geëxporteerd.

In de overzichts- en e-mailsweergave worden binnen enkele uren na de verwerking informatie weergegeven in plaats van binnen 24 uur (vraag opnieuw. verhoogde snelheden hier is een duidelijk signaal)!

> [!NOTE]
> Een rapport over de status van bedreigingsbescherming is beschikbaar voor klanten die [Office 365 ATP](office-365-atp.md) of [Exchange Online Protection](exchange-online-protection-eop.md) (EOP) hebben; De informatie die wordt weergegeven in het rapport Status bedreigingsstatus voor ATP-klanten zal echter waarschijnlijk andere gegevens bevatten dan wat EOP-klanten kunnen zien. Het rapport Statusstatus bedreigingsbeveiliging voor ATP-klanten bevat bijvoorbeeld informatie over [schadelijke bestanden die zijn gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.](atp-for-spo-odb-and-teams.md) Dergelijke informatie is specifiek voor ATP, dus klanten die EOP hebben maar geen ATP, zien deze gegevens niet in hun rapport over de status van bedreigingsbescherming.

Als u het rapport Status bedreigingsbeveiliging wilt weergeven, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar de **status bedreigingsbeveiliging** **van het** \> **dashboard** \> rapporten .

![ATP Threat Protection Status rapport](../../media/6bdd41eb-62e0-423b-9fd4-d1d5baf0cbd5.png)

Als u een dag lang een gedetailleerde status wilt krijgen, zweeft u over de grafiek.

![ATP Threat Protection Status gegevens voor een dag](../../media/d5c2c6ad-c002-4985-a032-c866e46fdea8.png)

Standaard worden in het rapport Status bedreigingsbeveiliging gegevens van de afgelopen zeven dagen weergegeven. U echter **filters** kiezen en het datumbereik wijzigen om gegevens maximaal 90 dagen weer te geven. (Als u een proefabonnement gebruikt, bent u mogelijk beperkt tot 30 dagen aan gegevens.)

![Filters voor atp-statusstatusvan de bescherming van bedreigingen](../../media/4f703369-642b-402b-9758-b9c828283410.png)

U ook het menu Gegevens per menu **weergeven** gebruiken om te wijzigen welke informatie in het rapport wordt weergegeven.

![Opties weergeven voor het rapport STATUSvan ATP-dreigingsbescherming](../../media/4959bf8c-d192-4542-b00b-184e101e7513.png)

## <a name="url-protection-status-report"></a>Rapport URL-beveiligingsstatus

Dit rapport is gebaseerd op gegevens verzameld, en bedreigingen gedetecteerd, per klik (terwijl de meeste andere e-mail bedreiging gerelateerde rapporten zijn per bericht gegevens). Dit rapport is ontworpen om bedreigingen weer te geven die afkomstig zijn van hyperlinks in e-mailberichten en documenten, per klik. Er zijn twee weergaven:

|||
|---|---|
|Actie voor URL-klikbeveiliging|Bekijk het aantal geblokkeerde, geblokkeerde maar overschreven URL's met een doorklik door een gebruiker, wordt overschreven met een doorklik door een gebruiker en toegestaan.|
|URL klik per toepassing|Bekijk de toepassing van waaruit op de URL is geklikt.|
|

In de detailstabel u meer informatie zien over kliktijd en gebruikersinformatie. Houd tot slot rekening met het rapport URL-beveiligingsstatus toont de functie Bescherming tegen ATP Safe Links, zodat alleen klanten die ATP Safe Links hebben ingeschakeld, gegevens in dit rapport zien.

> [!NOTE]
> Dit is een *trendrapport voor bescherming,* wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen. Rapportage is hier niet in realtime beschikbaar. Voor realtime URL-klikgegevens blijft u URL-trace gebruiken.

## <a name="atp-file-types-report"></a>ATP-bestandstyperapport

Het rapport **ATP-bestandstypen** toont u het type bestanden dat is gedetecteerd als kwaadaardig door [ATP-veilige bijlagen.](atp-safe-attachments.md)

Als u dit rapport wilt bekijken, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar **ATP-bestandstypen** **rapporten** \> **dashboard** \> .

![ATP-bestandstyperapport](../../media/6e3f5d33-79aa-4b2d-938c-6ef135d9e54c.png)
  
Wanneer u over een bepaalde dag zweeft, u de uitsplitsing zien van typen schadelijke bestanden die zijn gedetecteerd door [ATP Safe Attachments](atp-safe-attachments.md) en [anti-spam &amp; anti-malware bescherming.](anti-spam-and-anti-malware-protection.md)
  
![Rapportgegevens van ATP-bestandstypen voor een dag](../../media/10d18428-699a-41d2-a73e-be3a8214ada1.png)

## <a name="atp-message-disposition-report"></a>ATP-rapport over berichtverwerking

Het rapport **ATP-berichtdispositie** toont u de acties die zijn uitgevoerd voor e-mailberichten die zijn gedetecteerd als schadelijke inhoud.

Als u dit rapport wilt bekijken, gaat u in het [Security &amp; Compliance Center](https://protection.office.com)naar Het **DASHBOARD** \> **ATP-berichtdispositie**van **rapporten** \> .

![Rapport over de dispositie van ATP-berichten](../../media/b0ff65c4-53d3-496d-bafa-8937a5eb69e5.png)

Wanneer u de boventoon over een balk in de grafiek zweeft, u zien welke acties zijn uitgevoerd voor gedetecteerde e-mail voor die dag.

![GEGEVENS over atp-berichtdispositie voor een dag](../../media/68d2beb8-4b30-48c4-8ba6-5e8ab88ae456.png)

## <a name="additional-reports-to-view"></a>Aanvullende rapporten om te bekijken

Naast de atp-rapporten die in dit artikel worden beschreven, zijn er nog verschillende andere rapporten beschikbaar, zoals beschreven in de volgende tabel:

|||
|---|---|
|**Rapport(en)**|**Details**|
|**Explorer-** of **realtimedetecties:**(Office 365 ATP Plan 2-klanten hebben Explorer; Klanten van Office 365 ATP Plan 1 hebben realtime detecties.)|[Bedreigingsverkenner (en realtime detecties)](threat-explorer.md)|
|**E-mailbeveiligingsrapporten,** zoals een rapport Top afzenders en geadresseerden, een SpoofMailrapport en een rapport over spamdetecties.|[E-mailbeveiligingsrapporten weergeven in het Security &amp; Compliance Center](view-email-security-reports.md)|
|**URL-trace van ATP Safe Links**: (Dit is een rapport dat u genereert met PowerShell.) Dit rapport toont de resultaten van ATP Safe Links acties in de afgelopen zeven (7) dagen.|[Get-UrlTrace-cmdlet-verwijzing](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-urltrace)|
|**EOP- en ATP-resultaten**: (Dit is een aangepast rapport dat u genereert met PowerShell). Dit rapport bevat informatie, zoals Domein, Datum, Gebeurtenistype, Richting, Actie en Aantal berichten.|[Get-MailTrafficATPReport-cmdlet-verwijzing](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-mailtrafficatpreport)|
|**EOP- en ATP-detecties**: (Dit is een aangepast rapport dat u genereert met PowerShell). Dit rapport bevat details over schadelijke bestanden of URL's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.|[Get-MailDetailATPReport-cmdlet-verwijzing](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Welke machtigingen zijn nodig om de ATP-rapporten te bekijken?

Als u de in dit artikel beschreven rapporten wilt bekijken en gebruiken, **moet u een geschikte rol hebben toegewezen voor zowel het Security &amp; Compliance Center als het Exchange-beheercentrum.**

- Voor het &amp; Security Compliance Center moet u een van de volgende rollen toegewezen hebben:

  - Organisatiebeheer
  - Beveiligingsbeheerder (dit kan worden toegewezen in het[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory-beheercentrum ( ))
  - Beveiligingsoperator (dit kan worden toegewezen in het[https://aad.portal.azure.com](https://aad.portal.azure.com)Azure Active Directory-beheercentrum ( ))
  - Beveiligingslezer

- Voor Exchange Online moet u een van de volgende rollen[https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)hebben toegewezen in het Exchange-beheercentrum ( ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)

  - Organisatiebeheer
  - Organisatiebeheer alleen weergeven
  - Functie Alleen-weergaveontvangers
  - Compliance Management

Zie de volgende bronnen voor meer informatie:

- [Machtigingen in het &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md)

- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>Wat gebeurt er als de rapporten geen gegevens weergeven?

Als u geen gegevens in uw ATP-rapporten ziet, controleert u of uw beleid correct is ingesteld. Uw organisatie moet beschikken [over atp-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) en beleid voor veilige [bevestigingen van ATP](set-up-atp-safe-attachments-policies.md) dat is gedefinieerd om de ATP-bescherming te kunnen gebruiken. Zie ook [antispam- en anti-malwarebeveiliging in Office 365](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Verwante onderwerpen

[Rapporten en inzichten &amp; in het Security Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Een planning maken voor een &amp; rapport in het Security Compliance Center](create-a-schedule-for-a-report.md)

[Een aangepast rapport instellen en &amp; downloaden in het Security Compliance Center](set-up-and-download-a-custom-report.md)

[Machtigingen voor rollen (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
