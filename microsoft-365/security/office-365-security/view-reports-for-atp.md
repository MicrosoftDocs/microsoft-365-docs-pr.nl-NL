---
title: Rapporten voor geavanceerde bedreigingsbeveiliging weergeven
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
description: Rapporten voor Geavanceerde bedreigingsbeveiliging van Office 365 zoeken en gebruiken in het Security &amp; Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 4210ea30457215f9adc2984f24f161dc94985873
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434078"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Rapporten voor geavanceerde bedreigingsbeveiliging van Office 365 weergeven

Office 365 Advanced Threat Protection (ATP)-organisaties (bijvoorbeeld Microsoft 365 E5-abonnementen of ATP-abonnement 1- of ATP-abonnement 2-add-ons) bevatten verschillende beveiligingsrapporten. Als u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-atp-reports)beschikt, u deze rapporten bekijken in het Security & Compliance Center door naar **Dashboard Rapporten** te gaan \> **Dashboard**. Als u rechtstreeks naar het dashboard van rapporten wilt gaan, opent <https://protection.office.com/insightdashboard> u .

![Het dashboard Rapporten in het Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>Rapport over geavanceerde bedreigingsbeveiligingsbestandstypen

In **het rapport Rapport Advanced Threat Protection-bestandstypen** ziet u het type bestanden dat door [ATP Safe Attachments](atp-safe-attachments.md)als kwaadaardig is gedetecteerd.

 De totale weergave van het rapport maakt het mogelijk om 90 dagen te filteren, terwijl de detailweergave slechts 10 dagen filtering mogelijk maakt.

Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** \> **Dashboard** en selecteert u **Office ATP-bestandstypen**. Open <https://protection.office.com/reportv2?id=ATPFileReport> .

![Office ATP-bestandstypen widget in het dashboard Rapporten](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het [rapport Advanced Threat Protection message disposition](#advanced-threat-protection-message-disposition-report).

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>Rapportweergave voor het rapport Geavanceerde bedreigingsbeveiligingsbestandstypen

De volgende weergaven zijn beschikbaar:

- **Gegevens bekijken op: Bestand**: De grafiek bevat de volgende informatie:

  - **Schadelijke Excel-bijlagen**
  - **Schadelijke Flash-bijlagen**
  - **Schadelijke PDF-bijlagen**
  - **Schadelijke PowerPoint-bijlagen**
  - **Schadelijke URL's**
  - **Bijlagen voor kwaadaardig Woord**
  - **Kwaadaardige uitvoerbare bijlagen**
  - **Anderen**

  Wanneer u op een bepaalde dag (gegevenspunt) zweeft, u de verdeling zien van typen schadelijke bestanden die zijn gedetecteerd door [ATP Safe Attachments](atp-safe-attachments.md) en [anti-malwarebescherming in EOP.](anti-malware-protection.md)

  ![Bestandsweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-file-view.png)

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

- **Gegevens bekijken op: Bericht**: De grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten gecontroleerd**
  - **Vervangen door dynamische e-mailbezorging:** zie [Dynamische levering en previewing met ATP Safe Attachments](dynamic-delivery-and-previewing.md).

  ![Berichtweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-message-view.png)

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde waarden voor het dispositie van berichten die beschikbaar zijn in de grafiek en de extra **waarde van berichten.**

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>Tabelweergave details voor het rapport Geavanceerde bestandstypen voor bedreigingsbeveiliging

Als u op **tabel Details weergeven**klikt, biedt het rapport een bijna realtime weergave van alle klikken die de afgelopen tien dagen binnen de organisatie plaatsvinden. De weergegeven informatie is afhankelijk van de grafiek waar u naar keek:

- **Gegevens bekijken op: Bestand:**

  - **Datum**
  - **Adres van de geadresseerde**
  - **Adres afzender**
  - **Bericht-id**: beschikbaar in het kopveld **Bericht-ID** in de berichtkop en moet uniek zijn. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaakjes).
  - **Bestand**

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

- **Gegevens bekijken op: Bericht:**

  - **Datum**
  - **Adres van de geadresseerde**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **Filters**klikt, u de resultaten wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde waarden voor het dispositie van berichten die beschikbaar zijn in de grafiek en de extra **waarde van berichten.**

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="advanced-threat-protection-message-disposition-report"></a>Advanced Threat Protection message disposition report Advanced Threat Protection message disposition report Advanced Threat Protection

Het **ATP-bericht dispositie** rapport toont u de acties die zijn genomen voor e-mailberichten die zijn gedetecteerd als met kwaadaardige inhoud.

Als u het rapport wilt bekijken, opent u het [Beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** \> **Dashboard** en selecteert u **Office ATP-berichtweergave**. Open <https://protection.office.com/reportv2?id=ATPMessageReport> .

![Object office 365 ATP-bericht dispositie in het dashboard Rapporten](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het [rapport Geavanceerde bedreigingsbeveiligingsbestandstypen.](#advanced-threat-protection-file-types-report)

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>Rapportweergave voor het rapport Geavanceerde bedreigingsbeveiliging

De volgende weergaven zijn beschikbaar:

- **Gegevens bekijken op: Bericht**: De grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten gecontroleerd**
  - **Vervangen door dynamische e-mailbezorging:** zie [Dynamische levering en previewing met ATP Safe Attachments](dynamic-delivery-and-previewing.md).

  ![Berichtweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-message-view.png)

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde waarden voor het dispositie van berichten die beschikbaar zijn in de grafiek en de extra **waarde van berichten.**

- **Gegevens bekijken op: Bestand**: De grafiek bevat de volgende informatie:

  - **Schadelijke Excel-bijlagen**
  - **Schadelijke Flash-bijlagen**
  - **Schadelijke PDF-bijlagen**
  - **Schadelijke PowerPoint-bijlagen**
  - **Schadelijke URL's**
  - **Bijlagen voor kwaadaardig Woord**
  - **Kwaadaardige uitvoerbare bijlagen**
  - **Anderen**

  Wanneer u op een bepaalde dag (gegevenspunt) zweeft, u de verdeling zien van typen schadelijke bestanden die zijn gedetecteerd door [ATP Safe Attachments](atp-safe-attachments.md) en [anti-malwarebescherming in EOP.](anti-malware-protection.md)

  ![Bestandsweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-file-view.png)

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>Tabelweergave details voor het rapport Geavanceerde bedreigingsbeveiliging

Als u op **tabel Details weergeven**klikt, biedt het rapport een bijna realtime weergave van alle klikken die de afgelopen tien dagen binnen de organisatie plaatsvinden. De weergegeven informatie is afhankelijk van de grafiek waar u naar keek:

- **Gegevens bekijken op: Bericht:**

  - **Datum**
  - **Adres van de geadresseerde**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **Filters**klikt, u de resultaten wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde waarden voor het dispositie van berichten die beschikbaar zijn in de grafiek en de extra **waarde van berichten.**

- **Gegevens bekijken op: Bestand:**

  - **Datum**
  - **Adres van de geadresseerde**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="threat-protection-status-report"></a>Statusrapport voor bedreigingsbescherming

Het **statusrapport voor bedreigingsbescherming** is één weergave die informatie over schadelijke inhoud en schadelijke e-mail samenbrengt die is gedetecteerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Office 365 ATP. Zie [Statusrapport Bedreigingsbeveiliging voor](view-email-security-reports.md#threat-protection-status-report)meer informatie .

## <a name="url-threat-protection-report"></a>URL-melding voor bedreigingsbeveiliging

Het **URL-waarschuwingsrapport voor bedreigingsbeveiliging** biedt overzichten en trendweergaven voor gedetecteerde bedreigingen en acties die zijn uitgevoerd op URL-klikken als onderdeel van [ATP Safe Links](atp-safe-links.md). In dit rapport worden geen klikgegevens van gebruikers weergegeven waarbij het toegepaste beleid Voor veilige koppelingen de optie **Klikken van gebruikers niet bijhouden** is geselecteerd.

Als u het rapport wilt bekijken, opent u het [Beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** en \> **Dashboard** selecteert u **URL-beveiligingsrapport**. Open <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![URL-beveiligingsrapportobject in het dashboard Rapporten](../../media/url-protection-report-widget.png)

> [!NOTE]
> Dit is een *beveiligingstrendrapport,* wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen. Als gevolg hiervan zijn de gegevens in de geaggregeerde weergave hier niet in realtime beschikbaar, maar de gegevens in de tabelweergave details zijn, dus u een lichte discrepantie tussen de twee weergaven zien.

### <a name="report-view-for-the-url-threat-protection-report"></a>Rapportweergave voor het URL-waarschuwingsrapport voor bedreiging

Het **URL-dreigingsbeveiligingsrapport** bevat twee geaggregeerde weergaven die eenmaal per vier uur worden vernieuwd en waarin gegevens van de afgelopen 90 dagen worden weergegeven:

- **URL-klikbeveiligingsactie:** geeft het aantal URL-klikken weer door gebruikers in de organisatie en de resultaten van de klik:

  - **Geblokkeerd**
  - **Geblokkeerd en doorgeklikt**
  - **Doorgeklikt tijdens de scan**

  Een klik geeft aan dat de gebruiker via de blokpagina naar de kwaadaardige website heeft geklikt (beheerders kunnen doorklikken uitschakelen in het beleid voor veilige koppelingen).

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - De beschikbare klikbeveiligingsacties, plus de waarde **Die u toestaat** om informatie te zien voor alle URL-klikken (niet alleen geblokkeerde klikken).

  ![URL klik op de actieweergave voor beveiliging in het url-dreigingsbeveiligingsrapport](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL-klik op toepassing**: geeft het aantal URL-klikken weer door toepassingen die Office 365 ATP Safe Links ondersteunen:

  - **E-mailclient**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Overige**

  Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - De beschikbare toepassingen.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Tabelweergave details voor het URL-dreigingsbeveiligingsrapport

Als u op **tabel Details weergeven**klikt, geeft het rapport een bijna realtime weergave van alle klikken die de afgelopen zeven dagen binnen de organisatie plaatsvinden met de volgende details:

- **Kliktijd**
- **Gebruiker**
- **Url**
- **Actie**
- **App**

Als u op **Filters** klikt in de tabelweergave details, u filteren op dezelfde criteria als in de rapportweergave, en ook op **domeinen** of **geadresseerden,** gescheiden door komma's.

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="additional-reports-to-view"></a>Aanvullende rapporten om weer te geven

Naast de ATP-rapporten die in dit onderwerp worden beschreven, zijn er nog verschillende rapporten beschikbaar, zoals beschreven in de volgende tabel:

|Rapport|Onderwerp|
|---|---|
|**Explorer** (ATP Plan 2) of **real-time detecties** (ATP Plan 1)|[Bedreigingsverkenner (en realtime detecties)](threat-explorer.md)|
|**E-mailbeveiligingsrapporten,** zoals het rapport Top senders and recipients, het spoofmailrapport en het rapport Spamdetecties.|[E-mailbeveiligingsrapporten weergeven in het Security & Compliance Center](view-email-security-reports.md)|
|**E-mailstroomrapporten**, zoals het rapport Doorsturen, het statusrapport Mailflow en het rapport Top afzenders en ontvangers.|[E-mailstroomrapporten weergeven in het Security & Compliance Center](view-mail-flow-reports.md)|
|**URL-trace voor ATP Safe Links** (alleen PowerShell). De uitvoer van deze cmdlet toont u de resultaten van ATP Safe Links acties in de afgelopen zeven dagen.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Mail verkeersresultaten voor EOP en ATP** (alleen PowerShell). De uitvoer van deze cmdlet bevat informatie over domein, datum, gebeurtenistype, richting, actie en aantal berichten.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport) <br/><br/> |
|**Rapporten over e-maildetails voor EOP- en ATP-detecties** (alleen PowerShell). De uitvoer van deze cmdlet bevat details over schadelijke bestanden of URL's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Welke machtigingen zijn nodig om de ATP-rapporten weer te geven?

Als u de in dit onderwerp beschreven rapporten wilt weergeven en gebruiken, **moet u een passende rol hebben toegewezen voor zowel het Security Compliance Center als het &amp; Exchange-beheercentrum.**

- Voor het Security & Compliance Center moet een van de volgende rollen zijn toegewezen:

  - Organisatiebeheer
  - Beveiligingsbeheerder (dit kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Beveiligingsoperator (dit kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Beveiligingslezer

- Voor Exchange Online moet u een van de volgende rollen hebben toegewezen in het Exchange-beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell):](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)

  - Organisatiebeheer
  - Alleen-weergeven organisatiebeheer
  - Rol alleen weergeven ontvangers
  - Compliance Management

Zie de volgende bronnen voor meer informatie:

- [Rapporten in het beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)

- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>Wat als de rapporten geen gegevens weergeven?

Als u geen gegevens ziet in uw ATP-rapporten, controleert u dubbel of uw beleid correct is ingesteld. Uw organisatie moet [atp-beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) en [atp-veilige bijlagen hebben](set-up-atp-safe-attachments-policies.md) gedefinieerd om atp-beveiliging op zijn plaats te krijgen. Zie ook [anti-spam en anti-malware bescherming in Office 365](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Verwante onderwerpen

[Slimme rapporten en inzichten in het Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)
  
[Rolmachtigingen (Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
