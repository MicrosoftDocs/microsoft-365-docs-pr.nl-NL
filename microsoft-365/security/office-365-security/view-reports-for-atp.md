---
title: Rapporten weergeven voor geavanceerde Bedreigingsbeveiliging
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Rapporten voor Office 365 Advanced Threat Protection zoeken en gebruiken in het beveiligings &amp; compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e2bb4b0248294589b3e6e7a1a095e4f63d47d8e2
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48446297"
---
# <a name="view-reports-for-office-365-advanced-threat-protection"></a>Rapporten weergeven voor Office 365 Advanced Threat Protection

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Office 365 Advanced Threat Protection (ATP)-organisaties (bijvoorbeeld Microsoft 365 E5-abonnementen of ATP abonnement 1 of ATP plan 2-uitbreidingen) bevatten diverse beveiligingsrapporten. Als u de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-atp-reports)hebt, kunt u deze rapporten weergeven in het compliance-beveiligings & door **Reports** naar het \> **Dashboard**rapporten te gaan. Open om rechtstreeks naar het Dashboard rapporten te gaan <https://protection.office.com/insightdashboard> .

![Het Dashboard rapporten in het nalevings centrum voor beveiligings &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="advanced-threat-protection-file-types-report"></a>Rapport over bestandstypen Advanced Threat Protection

In het rapport **Geavanceerde bedreigings beveiligingstypen** wordt weergegeven welk type bestanden als schadelijk voor [veilige bijlagen](atp-safe-attachments.md)is gedetecteerd.

 De geaggregeerde weergave van het rapport mag 90 dagen filteren, terwijl de detailweergave alleen 10 dagen van filteren toestaat.

Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u de **bestandstypen Office-ATP**. Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPFileReport> .

![De objecttypen Office ATP in het Dashboard rapporten](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het [rapport Advanced Threat Protection](#advanced-threat-protection-message-disposition-report).

### <a name="report-view-for-the-advanced-threat-protection-file-types-report"></a>Rapportweergave voor het rapport Advanced Threat Protection-bestandstypen

De volgende weergaven zijn beschikbaar:

- **Gegevens weergeven op: bestand**: de grafiek bevat de volgende informatie:

  - **Schadelijke Excel-bijlagen**
  - **Schadelijke Flash-bijlagen**
  - **Schadelijke PDF-bijlagen**
  - **Schadelijke PowerPoint-bijlagen**
  - **Schadelijke Url's**
  - **Schadelijke Word-bijlagen**
  - **Schadelijke bijlagen met uitvoerbaar bestand**
  - **Gezien**

  Wanneer u de muisaanwijzer over een bepaalde dag (gegevenspunt) houdt, ziet u een overzicht van de typen schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen](atp-safe-attachments.md) en [beveiliging tegen malware in EOP](anti-malware-protection.md).

  ![Bestandsweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-file-view.png)

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

- **Gegevens weergeven op: bericht**: de grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten gecontroleerd**
  - **Vervangen door dynamische e-mail bezorging**: Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.

  ![Berichtenweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-message-view.png)

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.

### <a name="details-table-view-for-the-advanced-threat-protection-file-types-report"></a>De tabel weergave Details voor het rapport Advanced Threat Protection-bestandstypen

Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen. Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:

- **Gegevens uit een bestand weergeven**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-id**: beschikbaar in het veld **bericht-id-** header in de berichtkop en moet uniek zijn. Een Voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Let op de punthaken).
  - **Bestand**

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

- **Gegevens weergeven op: bericht**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **filters**klikt, kunt u de resultaten wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.

Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.

## <a name="advanced-threat-protection-message-disposition-report"></a>Rapport over berichtverwerking Advanced Threat Protection

In het rapport vrije voorkeuren voor **ATP-berichten** ziet u de acties die zijn ondernomen voor e-mailberichten die zijn gevonden met schadelijke inhoud.

Als u het rapport wilt weergeven, opent u het [beveiligings & compliance](https://protection.office.com), gaat u naar **Reports** \> **Dashboard** rapporten en selecteert u **Office ATP-bericht dispositioneren**. Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPMessageReport> .

![De widget Office 365 ATP-bericht voor het verplaatsen van berichten in het Dashboard rapporten](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het [rapport Advanced Threat Protection-bestandstypen](#advanced-threat-protection-file-types-report).

### <a name="report-view-for-the-advanced-threat-protection-message-disposition-report"></a>Rapportweergave voor het rapport over het wijzigen van het bericht voor geavanceerde Bedreigingsbeveiliging

De volgende weergaven zijn beschikbaar:

- **Gegevens weergeven op: bericht**: de grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten gecontroleerd**
  - **Vervangen door dynamische e-mail bezorging**: Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.

  ![Berichtenweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-message-view.png)

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.

- **Gegevens weergeven op: bestand**: de grafiek bevat de volgende informatie:

  - **Schadelijke Excel-bijlagen**
  - **Schadelijke Flash-bijlagen**
  - **Schadelijke PDF-bijlagen**
  - **Schadelijke PowerPoint-bijlagen**
  - **Schadelijke Url's**
  - **Schadelijke Word-bijlagen**
  - **Schadelijke bijlagen met uitvoerbaar bestand**
  - **Gezien**

  Wanneer u de muisaanwijzer over een bepaalde dag (gegevenspunt) houdt, ziet u een overzicht van de typen schadelijke bestanden die zijn gedetecteerd door [veilige bijlagen](atp-safe-attachments.md) en [beveiliging tegen malware in EOP](anti-malware-protection.md).

  ![Bestandsweergave in het rapport ATP-bestandstypen](../../media/atp-file-types-report-file-view.png)

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

### <a name="details-table-view-for-the-advanced-threat-protection-message-disposition-report"></a>Weergave Details voor het rapport over het wijzigen van het bericht voor geavanceerde Bedreigingsbeveiliging

Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen. Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:

- **Gegevens weergeven op: bericht**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **filters**klikt, kunt u de resultaten wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.

- **Gegevens uit een bestand weergeven**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.

## <a name="threat-protection-status-report"></a>Statusrapport bedreigingsbeveiliging

Het rapport **status van bedreigingsbeveiliging** is één weergave waarin informatie wordt verzameld over schadelijke inhoud en ongewenste e-mail die wordt geblokkeerd en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Office 365. Zie [statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)voor meer informatie.

## <a name="url-threat-protection-report"></a>Rapport over URL Threat Protection

Het **rapport URL Threat Protection** biedt samenvattings-en trend weergaven voor bedreigingen die worden gedetecteerd en acties die worden uitgevoerd op URL-klikken als onderdeel van [veilige koppelingen](atp-safe-links.md). Dit rapport hoeft niet te klikken op gegevens van gebruikers waar voor het beleid voor veilige koppelingen de optie **gebruiker niet bijhouden** is ingeschakeld.

Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het **rapport URL-beveiliging**. Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![De widget URL-beveiligingsrapport in het Dashboard rapporten](../../media/url-protection-report-widget.png)

> [!NOTE]
> Dit is een *beveiligingsrapport*voor trends, wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen. De gegevens in de samengevoegde weergave zijn daardoor niet in realtime beschikbaar, maar de gegevens in de tabel weergave Details is dus een lichte discrepantie tussen de twee weergaven.

### <a name="report-view-for-the-url-threat-protection-report"></a>Rapportweergave voor het rapport URL Threat Protection

Het rapport **URL Threat Protection** heeft twee geaggregeerde weergaven die elke vier uur worden vernieuwd met de gegevens voor de laatste 90 dagen:

- **URL klik op beschermings actie**: toont het aantal gebruikers in de organisatie op basis van de URL en de resultaten van de Klik op:

  - **Geblokkeerd** (de gebruiker is geblokkeerd voor het navigeren naar de URL)
  - **Geblokkeerde en geklikt door**
  - **Door de scan geklikt**

  Met een klik wordt aangegeven dat de gebruiker heeft geklikt op de blok pagina voor de schadelijke website (beheerders kunnen de klik-en-beleidsregels uitschakelen in beleidsregels voor veilige koppelingen).

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De beschikbare klikken op beschermings acties plus de **toegestane** waarde (de gebruiker heeft de mogelijkheid om naar de URL te gaan).

  ![URL klik op beschermings actie weergave in het rapport URL Threat Protection](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL klik op toepassing**: hier ziet u het aantal te klikken voor de URL door toepassingen die ondersteuning bieden voor veilige koppelingen:

  - **E-mailclient**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Overige**

  Als u op **filters**klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De beschikbare toepassingen.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Weergave Details van het rapport URL Threat Protection

Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die binnen de organisatie plaatsvinden voor de laatste 7 dagen, met de volgende informatie:

- **Klik op tijd**
- **Gebruiker**
- **URL**
- **Actierij**
- **App**

Als u in de weergave Details op **filters** klikt, kunt u filteren op dezelfde criteria als in de rapportweergave, en ook op **domeinen** of **geadresseerden** , gescheiden door komma's.

Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.

## <a name="additional-reports-to-view"></a>Extra rapporten om weer te geven

Naast de in dit onderwerp beschreven ATP-rapporten, zijn er nog enkele andere rapporten beschikbaar, zoals wordt beschreven in de volgende tabel:

****

|Rapport|Rond|
|---|---|
|**Verkenner** (ATP abonnement 2) of **realtime-detecties** (ATP abonnement 1)|[Bedreigingsverkenner (en realtime detecties)](threat-explorer.md)|
|**Beveiligingsrapporten voor e-mail**, zoals het rapport belangrijkste afzenders en geadresseerden, het rapport spoofberichten en het rapport detectie van ongewenste e-mail.|[Beveiligingsrapporten voor e-mail weergeven in het beveiligings & nalevings centrum](view-email-security-reports.md)|
|**E-mail stroom rapporten**, zoals het doorsturen van rapporten, het rapport status van de mail stroom en het rapport meest voorkomende afzenders en geadresseerden.|[De e-mail stroom rapporten weergeven in het beveiligings & nalevings centrum](view-mail-flow-reports.md)|
|**URL-tracering voor veilige koppelingen** (alleen PowerShell). De uitvoer van deze cmdlet toont u de resultaten van acties van veilige koppelingen in de afgelopen zeven dagen.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Resultaten van e-mail verkeer voor EOP en ATP** (alleen PowerShell). De uitvoer van deze cmdlet bevat informatie over domein, datum, evenement type, richting, actie en aantal berichten.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**E-mail detailrapporten voor EOP en ATP-detectie** (alleen PowerShell). De uitvoer van deze cmdlet bevat details over schadelijke bestanden of Url's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-atp-reports"></a>Welke machtigingen zijn vereist voor het weergeven van de ATP-rapporten?

Voor het weergeven en gebruiken van de rapporten die in dit onderwerp worden beschreven, **moet u beschikken over de juiste rol die is toegewezen aan het beveiligings &amp; compliance en het Beheercentrum van Exchange**.

- Voor het beveiligings & nalevings centrum moet een van de volgende rollen zijn toegewezen:

  - Organisatiebeheer
  - Beveiligingsbeheerder (deze kan worden toegewezen in het Azure Active Directory-beheercentrum ( [https://aad.portal.azure.com](https://aad.portal.azure.com) ))
  - Beveiligings operator (dit kan worden toegewezen in het Azure Active Directory-beheercentrum [https://aad.portal.azure.com](https://aad.portal.azure.com) )
  - Beveiligings lezer

- Voor Exchange Online moet u beschikken over een van de volgende rollen die zijn toegewezen in het Exchange-Beheercentrum ( [https://outlook.office365.com/ecp](https://outlook.office365.com/ecp) ) of met PowerShell-cmdlets (Zie [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)):

  - Organisatiebeheer
  - Organisatiebeheer alleen weergeven
  - Rollen View-Only geadresseerden
  - Nalevings beheer

Zie de volgende bronnen voor meer informatie:

- [Machtigingen in het Beveiligings- en compliancecentrum](permissions-in-the-security-and-compliance-center.md)

- [Functiemachtigingen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="what-if-the-reports-arent-showing-data"></a>Wat moet ik doen als de rapporten geen gegevens weergeven?

Als u geen gegevens ziet in uw vrije voorraadrapporten, controleert u of uw beleidsregels correct zijn ingesteld. Als u wilt dat uw organisatie [beleidsregels voor beveiliging en beveiliging](set-up-atp-safe-links-policies.md) van [bijlagen](set-up-atp-safe-attachments-policies.md) bevat Zie ook [antispam en bescherming tegen malware](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Verwante onderwerpen

[Slimme rapporten en inzichten in het nalevings centrum voor beveiligings &](reports-and-insights-in-security-and-compliance.md)
  
[Rolmachtigingen (Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
