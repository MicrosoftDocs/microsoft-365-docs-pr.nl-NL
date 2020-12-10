---
title: Rapporten van Defender for Office 365 weergeven in het Dashboard rapporten
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
description: Rapporten voor Microsoft Defender voor Office 365 zoeken en gebruiken in het beveiligings & nalevings centrum.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2818362eea4071430bb2c784ceb0ce0eeb970a79
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615574"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Rapporten van Defender for Office 365 weergeven in het Dashboard rapporten in het nalevings centrum voor beveiligings &

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Bedrijven van Microsoft Defender voor Office 365 (bijvoorbeeld Microsoft 365 E5-abonnementen of Microsoft Defender voor Office 365-abonnement 1 of Microsoft Defender voor Office 365 abonnement 2-uitbreidingen) bevatten diverse beveiligingsrapporten. Als u de [benodigde machtigingen](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)hebt, kunt u deze rapporten weergeven in het compliance-beveiligings & door  naar het \> **Dashboard** rapporten te gaan. Open om rechtstreeks naar het Dashboard rapporten te gaan <https://protection.office.com/insightdashboard> .

![Het Dashboard rapporten in het nalevings centrum voor beveiligings &](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Rapport met bestandstypen voor Defender voor Office 365

In het rapport met het **rapport bestandstypen voor 365 van** wordt weergegeven welk type bestanden als schadelijk voor [veilige bijlagen](atp-safe-attachments.md)is gedetecteerd.

 De geaggregeerde weergave van het rapport mag 90 dagen filteren, terwijl de detailweergave alleen 10 dagen van filteren toestaat.

Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u de **bestandstypen voor Defender voor Office 365**. Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPFileReport> .

![Widget voor Office 365-bestandstypen in het Dashboard rapporten](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het rapport voor het wijzigen van het bericht in de [Defender for Office 365](#defender-for-office-365-message-disposition-report).

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Rapportweergave voor het rapport van het bestandstype voor Defender voor Office 365

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

  ![Bestandsweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

- **Gegevens weergeven op: bericht**: de grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten gecontroleerd**
  - **Vervangen door dynamische e-mail bezorging**: Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.

  ![Berichtenweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>De tabel weergave Details voor het rapport voor de bestandsindelingen voor Defender voor Office 365

Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen. Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:

- **Gegevens uit een bestand weergeven**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-id**: beschikbaar in het veld **bericht-id-** header in de berichtkop en moet uniek zijn. Een Voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Let op de punthaken).
  - **Bestand**

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

- **Gegevens weergeven op: bericht**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.

Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.

## <a name="defender-for-office-365-message-disposition-report"></a>Rapport over afwezigheid voor Office 365-bericht

In het rapport vrije voorkeuren voor **ATP-berichten** ziet u de acties die zijn ondernomen voor e-mailberichten die zijn gevonden met schadelijke inhoud.

Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u **Defender for Office 365 bericht dispositioning**. Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=ATPMessageReport> .

![De widget voor Office 365 voor het verplaatsen van berichten in het Dashboard rapporten](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het [rapport met bestandstypen van de Defender voor Office 365](#defender-for-office-365-file-types-report).

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Rapportweergave voor het rapport over het wijzigen van de berichten voor de Defender voor Office 365

De volgende weergaven zijn beschikbaar:

- **Gegevens weergeven op: bericht**: de grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten gecontroleerd**
  - **Vervangen door dynamische e-mail bezorging**: Zie [dynamische bezorging in beleidsregels voor veilige bijlagen](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)voor meer informatie.

  ![Berichtenweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

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

  ![Bestandsweergave in het rapport voor de bestandsindelingen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Weergave Details van het bericht voor het wijzigen van de weergave van het bericht voor Defender voor Office 365

Als u klikt op **Details tabel weergeven**, biedt het rapport een vrijwel realtime weergave van alle klikken die in de organisatie plaatsvinden voor de afgelopen 10 dagen. Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u bekijkt:

- **Gegevens weergeven op: bericht**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **filters** klikt, kunt u de resultaten wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Hetzelfde bericht voor het vrijmaken van een bericht, dat beschikbaar is in de grafiek, en de bijkomende **berichten doorgegeven** waarde.

- **Gegevens uit een bestand weergeven**:

  - **Datum**
  - **Adres van ontvanger**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - De waarden van het bestandstype die zichtbaar zijn in de grafiek.

Als u wilt teruggaan naar de weergave rapporten, klikt u op **rapport weergeven**.

## <a name="mail-latency-report"></a>Rapport over e-mail latentie

In het **rapport e-mail latentie** ziet u een geaggregeerde weergave van de bezorgings latentie en de detonatie latentie binnen uw organisatie. De levertijden voor e-mail in de service zijn van invloed op een aantal factoren en de absolute bezorgings tijd in seconden is vaak geen goede indicatie van het succes of een probleem. Een traag tijdstip van levering op één dag wordt mogelijk beschouwd als een gemiddelde levertijd op een andere dag, of omgekeerd. In het **rapport e-mail latentie** wordt geprobeerd berichten te bezorgen op basis van statistische gegevens over de waargenomen bezorgings tijden van andere berichten:

- **50e percentiel**: dit is het middelste punt voor de bezorgings tijd van berichten. U kunt deze waarde als gemiddelde bezorgings tijd beschouwen.
- **negentigste percentiel**: Hiermee wordt een hoge latentie aangegeven voor de bezorging van berichten. Slechts 10% van de berichten duurde langer dan de waarde voor levering.
- **99th percentiel**: Hiermee wordt de beste latentie voor de bezorging van berichten aangegeven.

De client-en netwerklatentie zijn niet opgenomen.

Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het **rapport e-mail latentie**. Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/mailLatencyReport?viewid=P50> .

![Widget e-mail latentie rapporten in het Dashboard rapporten](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Rapportweergave voor het rapport latentie van e-mail latentie

Wanneer u het rapport opent, wordt standaard het tabblad **50e percentiel** geselecteerd.

Deze weergave bevat standaard een grafiek die is geconfigureerd met de volgende filters:

- **Datum**: de laatste 7 dagen
- **Berichtenweergave**:
  - Detonatie berichten

In dit diagram ziet u berichten die zijn ingedeeld in de volgende categorieën:

- **E-mail bezorgings latentie**
- **Detonatie latentie**

Wanneer u de muisaanwijzer boven een categorie in de grafiek houdt, ziet u een uitsplitsing van de latentie in elke categorie.

![Rapport over e-mail latentie](../../media/mail-latency-report.png)

Als u op **filter** in de rapportweergave klikt, kunt u de resultaten wijzigen met de volgende filters:

- Alle berichten
- Berichten die bijlagen of Url's bevatten

Als u op het tabblad **negentigste percentielen** of het tabblad **99th percentiel** wordt geklikt, worden dezelfde standaardfilters uit de weergave **50e percentiel** gebruikt.

### <a name="details-table-view-for-the-mail-latency-report"></a>Weergave Details van het rapport met e-mail latentie

De volgende informatie wordt weergegeven in de tabel weergave Details:

- **Datum**
- **Waarden liggen tussen**
- **Aantal berichten**
- **Totale latentie**

![Details van e-mail latentie rapporten](../../media/mail-latency-report-details.png)

In het voorgaande wordt aangegeven dat het gemiddelde latentie van alle verzonden en deliete berichten **108,033** seconden is gedurende 2 november.

De tabel Details bevat dezelfde informatie op elk tabblad.

## <a name="threat-protection-status-report"></a>Statusrapport bedreigingsbeveiliging

Het rapport **status van bedreigingsbeveiliging** is één weergave waarin informatie wordt verzameld over schadelijke inhoud en ongewenste E-mail die wordt gedetecteerd en geblokkeerd via [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Microsoft Defender voor Office 365. Zie [statusrapport bedreigingsbeveiliging](view-email-security-reports.md#threat-protection-status-report)voor meer informatie.

## <a name="url-threat-protection-report"></a>Rapport over URL Threat Protection

Het **rapport URL Threat Protection** biedt samenvattings-en trend weergaven voor bedreigingen die worden gedetecteerd en acties die worden uitgevoerd op URL-klikken als onderdeel van [veilige koppelingen](atp-safe-links.md). Dit rapport hoeft niet te klikken op gegevens van gebruikers waar voor het beleid voor veilige koppelingen de optie **gebruiker niet bijhouden** is ingeschakeld.

Als u het rapport wilt weergeven, opent u het [beveiligings & nalevings centrum](https://protection.office.com), gaat u naar **rapporten** \> **Dashboard** en selecteert u het **rapport URL-beveiliging**. Open om rechtstreeks naar het rapport te gaan <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

![De widget URL-beveiligingsrapport in het Dashboard rapporten](../../media/url-protection-report-widget.png)

> [!NOTE]
> Dit is een *beveiligingsrapport* voor trends, wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen. De gegevens in de samengevoegde weergave zijn daardoor niet in realtime beschikbaar, maar de gegevens in de tabel weergave Details is dus een lichte discrepantie tussen de twee weergaven.

### <a name="report-view-for-the-url-threat-protection-report"></a>Rapportweergave voor het rapport URL Threat Protection

Het rapport **URL Threat Protection** heeft twee geaggregeerde weergaven die elke vier uur worden vernieuwd met de gegevens voor de laatste 90 dagen:

- **URL klik op beschermings actie**: toont het aantal gebruikers in de organisatie op basis van de URL en de resultaten van de Klik op:

  - **Geblokkeerd** (de gebruiker is geblokkeerd voor het navigeren naar de URL)
  - **Geblokkeerde en geklikt door**
  - **Door de scan geklikt**

  Met een klik wordt aangegeven dat de gebruiker heeft geklikt op de blok pagina voor de schadelijke website (beheerders kunnen de klik-en-beleidsregels uitschakelen in beleidsregels voor veilige koppelingen).

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

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

  Als u op **filters** klikt, kunt u het rapport met de volgende filters wijzigen:

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

Naast de rapporten die in dit onderwerp worden beschreven, zijn er nog enkele andere rapporten beschikbaar, zoals beschreven in de volgende tabel:

****

|Rapport|Rond|
|---|---|
|**Explorer** (Microsoft Defender voor Office 365 abonnement 2) of **realtime detecties** (Microsoft Defender voor Office 365 abonnement 1)|[Bedreigingsverkenner (en realtime detecties)](threat-explorer.md)|
|**Beveiligingsrapporten voor e-mail**, zoals het rapport belangrijkste afzenders en geadresseerden, het rapport spoofberichten en het rapport detectie van ongewenste e-mail.|[Beveiligingsrapporten voor e-mail weergeven in het beveiligings & nalevings centrum](view-email-security-reports.md)|
|**E-mail stroom rapporten**, zoals het doorsturen van rapporten, het rapport status van de mail stroom en het rapport meest voorkomende afzenders en geadresseerden.|[De e-mail stroom rapporten weergeven in het beveiligings & nalevings centrum](view-mail-flow-reports.md)|
|**URL-tracering voor veilige koppelingen** (alleen PowerShell). De uitvoer van deze cmdlet toont u de resultaten van acties van veilige koppelingen in de afgelopen zeven dagen.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Resultaten van e-mail verkeer voor EOP en Microsoft Defender voor Office 365** (alleen PowerShell). De uitvoer van deze cmdlet bevat informatie over domein, datum, evenement type, richting, actie en aantal berichten.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**E-mail detailrapporten voor EOP en Defender voor Office 365 detectie** (alleen PowerShell). De uitvoer van deze cmdlet bevat details over schadelijke bestanden of Url's, phishing-pogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Welke machtigingen zijn vereist voor het weergeven van de rapporten van de Defender for Office 365?

Voor het weergeven en gebruiken van de rapporten die in dit onderwerp worden beschreven, moet u lid zijn van een van de volgende rollen groepen in het compliance-& Beveiligingscentrum:

- **Organisatiebeheer**
- **Beveiligingsbeheerder**
- **Beveiligings lezer**
- **Algemene lezer**

Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

**Opmerking**: door gebruikers toe te voegen aan de bijbehorende rol van Azure Active Directory in het microsoft 365-Beheercentrum geeft u gebruikers de vereiste machtigingen in de beveiligings & nalevings centrum _en_ machtigingen voor andere functies in Microsoft 365. Raadpleeg [Over beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) voor meer informatie.

## <a name="what-if-the-reports-arent-showing-data"></a>Wat moet ik doen als de rapporten geen gegevens weergeven?

Als u geen gegevens ziet in uw 365-rapporten van Defender for Office, controleert u of uw beleidsregels correct zijn ingesteld. Als u wilt dat de beveiliging van Defender voor Office 365 op de juiste plek is geconfigureerd, moet uw organisatie beleidsregels voor [veilige koppelingen](set-up-atp-safe-links-policies.md) en een beleid voor veilige [bijlagen](set-up-atp-safe-attachments-policies.md) definiëren. Zie ook [antispam en bescherming tegen malware](anti-spam-and-anti-malware-protection.md).

## <a name="related-topics"></a>Verwante onderwerpen

[Slimme rapporten en inzichten in het nalevings centrum voor beveiligings &](reports-and-insights-in-security-and-compliance.md)

[Rolmachtigingen (Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
