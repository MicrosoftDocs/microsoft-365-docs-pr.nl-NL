---
title: Defender voor Office 365-rapporten weergeven in het dashboard Rapporten
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: e47e838c-d99e-4c0b-b9aa-e66c4fae902f
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Zoek en gebruik rapporten voor Microsoft Defender voor Office 365 in het & compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e3e5d48f6ac8f6246b65761f5728405c37333d71
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286595"
---
# <a name="view-defender-for-office-365-reports-in-the-reports-dashboard-in-the-security--compliance-center"></a>Defender voor Office 365-rapporten weergeven in het dashboard Rapporten in het & compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft Defender voor Office 365-organisaties (bijvoorbeeld Microsoft 365 E5-abonnementen of Microsoft Defender voor Office 365-abonnement 1 of invoegtoepassingen voor Microsoft Defender voor Office 365 Abonnement 2) bevatten diverse beveiligingsrapporten. Als u de [benodigde machtigingen hebt,](#what-permissions-are-needed-to-view-the-defender-for-office-365-reports)kunt u deze rapporten bekijken in het beveiligings- & Compliancecentrum door naar rapportendashboard **te** \> **gaan.** Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://protection.office.com/insightdashboard> .

![Het dashboard Rapporten in het beveiligings- & compliancecentrum](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="defender-for-office-365-file-types-report"></a>Rapport over bestandstypen voor Defender voor Office 365

In het rapport bestandstypenrapport Defender voor **Office 365** ziet u het type bestanden dat door veilige bijlagen als schadelijk [is gedetecteerd.](atp-safe-attachments.md)

 In de samengevoegde weergave van het rapport kunt u 90 dagen filteren, terwijl in de detailweergave slechts tien dagen kan worden gefilterd.

Als u het rapport wilt bekijken, opent u  het & [compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u Defender voor \>  **Office 365-bestandstypen.** Als u rechtstreeks naar het rapport wilt gaan, opent <https://protection.office.com/reportv2?id=ATPFileReport> u .

![Defender voor Office 365-widgets voor bestandstypen in het dashboard Rapporten](../../media/atp-file-types-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het rapport voor berichtverplaatsing van Defender voor [Office 365.](#defender-for-office-365-message-disposition-report)

### <a name="report-view-for-the-defender-for-office-365-file-types-report"></a>Rapportweergave voor het rapport Bestandstypen van Defender voor Office 365

De volgende weergaven zijn beschikbaar:

- **Gegevens weergeven met: Bestand:** de grafiek bevat de volgende informatie:

  - **Schadelijke Excel-bijlagen**
  - **Kwaadaardige Flash-bijlagen**
  - **Schadelijke PDF-bijlagen**
  - **Schadelijke PowerPoint-bijlagen**
  - **Schadelijke URL's**
  - **Schadelijke Word-bijlagen**
  - **Schadelijke uitvoerbare bijlagen**
  - **Overige**

  Wanneer u de muisaanwijzer op een bepaalde dag (gegevenspunt) beweegt, [](atp-safe-attachments.md) ziet u een uitsplitsing van de typen schadelijke bestanden die zijn gedetecteerd door veilige bijlagen en beveiliging tegen [malware in EOP.](anti-malware-protection.md)

  ![Bestandsweergave in het rapport Bestandstypen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

- **Gegevens weergeven met: Bericht:** de grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten bewaakt**
  - **Vervangen door Dynamische bezorging van** e-mail: Zie Dynamische bezorging [in beleidsregels voor veilige bijlagen voor meer informatie.](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Berichtweergave in het rapport Bestandstypen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde waarden voor berichtafzet die beschikbaar zijn in de grafiek en de extra waarde **voor de doorgegeven berichten.**

### <a name="details-table-view-for-the-defender-for-office-365-file-types-report"></a>Detailtabelweergave voor het rapport Bestandstypen van Defender voor Office 365

Als u op **de tabel Details weergeven** klikt, biedt het rapport een weergave in realtime van alle klikken die de afgelopen tien dagen binnen de organisatie plaatsvinden. Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u hebt weergegeven:

- **Gegevens weergeven op: Bestand:**

  - **Datum**
  - **Adres van geadresseerde**
  - **Adres afzender**
  - **Bericht-id:** deze is beschikbaar in het **koptekstveld Bericht-id** in de berichtkop en moet uniek zijn. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).
  - **Bestand**

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

- **Gegevens weergeven op: Bericht:**

  - **Datum**
  - **Adres van geadresseerde**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **Filters klikt,** kunt u de resultaten wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde waarden voor berichtafzet die beschikbaar zijn in de grafiek en de extra waarde **voor de doorgegeven berichten.**

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="defender-for-office-365-message-disposition-report"></a>Rapport over berichtverwerking voor Defender voor Office 365

In het rapport voor het **verwijderen van ATP-berichten** ziet u de acties die zijn uitgevoerd voor e-mailberichten die zijn vastgesteld als schadelijke inhoud.

Als u het rapport wilt bekijken, opent u  het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u Defender voor \>  Office **365-berichtverplaatsing.** Als u rechtstreeks naar het rapport wilt gaan, opent <https://protection.office.com/reportv2?id=ATPMessageReport> u .

![Widget voor berichtverplaatsing van Defender voor Office 365 in het dashboard Rapporten](../../media/atp-message-disposition-report-widget.png)

> [!NOTE]
> De informatie in dit rapport is ook beschikbaar in het rapport bestandstypen [Defender voor Office 365.](#defender-for-office-365-file-types-report)

### <a name="report-view-for-the-defender-for-office-365-message-disposition-report"></a>Rapportweergave voor het rapport voor berichtverplaatsing van Defender voor Office 365

De volgende weergaven zijn beschikbaar:

- **Gegevens weergeven met: Bericht:** de grafiek bevat de volgende informatie:

  - **Toegang blokkeren**
  - **Berichten vervangen**
  - **Berichten bewaakt**
  - **Vervangen door Dynamische bezorging van** e-mail: Zie Dynamische bezorging [in beleidsregels voor veilige bijlagen voor meer informatie.](atp-safe-attachments.md#dynamic-delivery-in-safe-attachments-policies)

  ![Berichtweergave in het rapport Bestandstypen van Defender voor Office 365](../../media/atp-file-types-report-message-view.png)

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde waarden voor berichtafzet die beschikbaar zijn in de grafiek en de extra waarde **voor de doorgegeven berichten.**

- **Gegevens weergeven met: Bestand:** de grafiek bevat de volgende informatie:

  - **Schadelijke Excel-bijlagen**
  - **Kwaadaardige Flash-bijlagen**
  - **Schadelijke PDF-bijlagen**
  - **Schadelijke PowerPoint-bijlagen**
  - **Schadelijke URL's**
  - **Schadelijke Word-bijlagen**
  - **Schadelijke uitvoerbare bijlagen**
  - **Overige**

  Wanneer u de muisaanwijzer op een bepaalde dag (gegevenspunt) beweegt, [](atp-safe-attachments.md) ziet u een uitsplitsing van de typen schadelijke bestanden die zijn gedetecteerd door veilige bijlagen en beveiliging tegen [malware in EOP.](anti-malware-protection.md)

  ![Bestandsweergave in het rapport Bestandstypen van Defender voor Office 365](../../media/atp-file-types-report-file-view.png)

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

### <a name="details-table-view-for-the-defender-for-office-365-message-disposition-report"></a>Detailtabelweergave voor het rapport voor berichtafzet van Defender voor Office 365

Als u op **de tabel Details weergeven** klikt, biedt het rapport een weergave in realtime van alle klikken die de afgelopen tien dagen binnen de organisatie plaatsvinden. Welke informatie wordt weergegeven, is afhankelijk van de grafiek die u hebt weergegeven:

- **Gegevens weergeven op: Bericht:**

  - **Datum**
  - **Adres van geadresseerde**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**
  - **Onderwerp**

  Als u op **Filters klikt,** kunt u de resultaten wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde waarden voor berichtafzet die beschikbaar zijn in de grafiek en de extra waarde **voor de doorgegeven berichten.**

- **Gegevens weergeven op: Bestand:**

  - **Datum**
  - **Adres van geadresseerde**
  - **Adres afzender**
  - **Bericht-ID**
  - **Bestand**

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Dezelfde bestandstypewaarden die zichtbaar zijn in de grafiek.

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="mail-latency-report"></a>E-maillatentierapport

In **het rapport E-maillatentie** ziet u een algemene weergave van de ervaring met de bezorging en detonatie van e-mail binnen uw organisatie. De bezorgingstijden van e-mail in de service worden door een aantal factoren beïnvloed en de absolute levertijd binnen enkele seconden is vaak geen goede indicator voor succes of een probleem. Een trage bezorging op een dag kan worden beschouwd als een gemiddelde levertijd op een andere dag, of omgekeerd. Het **rapport E-maillatentie** probeert berichtbezorging in aanmerking te komen op basis van statistische gegevens over de waargenomen bezorgingstijden van andere berichten:

- **50e percentiel:** dit is het midden voor de bezorgingstijden van berichten. U kunt deze waarde beschouwen als een gemiddelde levertijd.
- **90e percentiel:** dit geeft een hoge latentie voor berichtbezorging aan. Slechts 10% van de berichten duurde langer dan deze waarde om te bezorgen.
- **99e percentiel:** dit geeft de hoogste latentie voor berichtbezorging aan.

Clientzijde en netwerklatentie zijn niet inbegrepen.

Als u het rapport wilt bekijken, opent u het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar **het** dashboard Rapporten en selecteert u \>  **het E-maillatentierapport.** Als u rechtstreeks naar het rapport wilt gaan, opent <https://protection.office.com/mailLatencyReport?viewid=P50> u .

![Rapportwidget E-maillatentie in het dashboard Rapporten](../../media/mail-latency-report-widget.png)

### <a name="report-view-for-the-mail-latency-report"></a>Rapportweergave voor het e-maillatentierapport

Wanneer u het rapport opent, wordt standaard het **tabblad 50e percentiel** geselecteerd.

Deze weergave bevat standaard een grafiek die is geconfigureerd met de volgende filters:

- **Datum:** De laatste 7 dagen
- **Berichtweergave:**
  - Gedetoneerde berichten

In dit diagram worden berichten weergegeven die zijn ingedeeld in de volgende categorieën:

- **Latentie van e-mailbezorging**
- **Detonatielatentie**

Wanneer u de muisaanwijzer op een categorie in de grafiek beweegt, ziet u een uitsplitsing van de latentie in elke categorie.

![E-maillatentierapport](../../media/mail-latency-report.png)

Als u in **de rapportweergave** op Filteren klikt, kunt u de resultaten wijzigen met de volgende filters:

- Alle berichten
- Berichten met bijlagen of URL's

Als u op het tabblad **90e percentiel** of het **tabblad 99e percentiel** klikt, worden dezelfde standaardfilters uit de weergave **50e percentiel** gebruikt.

### <a name="details-table-view-for-the-mail-latency-report"></a>Tabelweergave Details voor het rapport E-maillatentie

De volgende informatie wordt weergegeven in de detailtabelweergave:

- **Datum**
- **Percentielen**
- **Aantal berichten**
- **Algehele latentie**

![Details van e-maillatentierapport](../../media/mail-latency-report-details.png)

Uit het bovenstaande blijkt dat op 14 november de gemiddelde latentie voor alle berichten die worden bezorgd en gedetoneerd, **108,033 seconden** was.

De detailtabel bevat dezelfde informatie op elk tabblad.

## <a name="threat-protection-status-report"></a>Statusrapport bedreigingsbeveiliging

Het **statusrapport** Risicobeveiliging is een enkele weergave waarin informatie over schadelijke inhoud en schadelijke e-mail wordt gevonden en geblokkeerd door [Exchange Online Protection](exchange-online-protection-overview.md) (EOP) en Microsoft Defender voor Office 365. Zie het statusrapport [Risicobeveiliging voor meer informatie.](view-email-security-reports.md#threat-protection-status-report)

## <a name="url-threat-protection-report"></a>Rapport URL-bedreigingsbeveiliging

Het **rapport URL-bedreigingsbeveiliging** biedt overzichts- en trendweergaven voor gedetecteerde bedreigingen en acties die worden ondernomen bij klikken op URL's als onderdeel van [veilige koppelingen.](atp-safe-links.md) In dit rapport zijn geen klikgegevens beschikbaar van gebruikers waarop voor het beleid voor veilige koppelingen de optie **Gebruikersklikken** niet bijhouden is geselecteerd.

Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** dashboard Rapporten \>  en selecteert u het **rapport URL-beveiliging.** Als u rechtstreeks naar het rapport wilt gaan, opent <https://protection.office.com/reportv2?id=URLProtectionActionReport> u .

![Rapportwidget VOOR URL-beveiliging in het dashboard Rapporten](../../media/url-protection-report-widget.png)

> [!NOTE]
> Dit is een *beveiligingstrendrapport,* wat betekent dat gegevens trends in een grotere gegevensset vertegenwoordigen. Hierdoor zijn de gegevens in de samengevoegde weergave hier niet in realtime beschikbaar, maar de gegevens in de detailtabelweergave wel, zodat u een kleine afwijking tussen de twee weergaven kunt zien.

### <a name="report-view-for-the-url-threat-protection-report"></a>Rapportweergave voor het rapport URL-bedreigingsbeveiliging

Het **rapport URL-bedreigingsbeveiliging** heeft twee samengevoegde weergaven die één keer per vier uur worden vernieuwd, met gegevens voor de afgelopen 90 dagen:

- **Actie voor het beschermen van URL's:** hier ziet u het aantal klikken op URL's door gebruikers in de organisatie en de resultaten van de klik:

  - **Geblokkeerd** (de gebruiker is geblokkeerd voor het navigeren naar de URL)
  - **Geblokkeerd en geklikt door**
  - **Er is tijdens het scannen op geklikt**

  Een klik geeft aan dat de gebruiker via de blokkeringspagina naar de schadelijke website heeft geklikt (beheerders kunnen klikken uitschakelen in beleidsregels voor veilige koppelingen).

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - De beschikbare acties voor klikbeveiliging, plus de waarde **Toegestaan** (de gebruiker mag naar de URL navigeren).

  ![De weergave Beveiligingsactie met URL-klik in het rapport URL-bedreigingsbeveiliging](../../media/url-threat-protection-report-url-click-protection-action-view.png)

- **URL klikken per toepassing:** hier ziet u het aantal klikken op URL's van toepassingen die veilige koppelingen ondersteunen:

  - **E-mailclient**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Teams**
  - **Overige**

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - De beschikbare toepassingen.

### <a name="details-table-view-for-the-url-threat-protection-report"></a>Detailtabelweergave voor het rapport URL-bedreigingsbeveiliging

Als u op de tabel **Details** weergeven klikt, biedt het rapport een bijna-realtime weergave van alle klikken die de afgelopen zeven dagen binnen de organisatie plaatsvinden, met de volgende details:

- **Klik op tijd**
- **Gebruiker**
- **URL**
- **Actie**
- **App**

Als u in **de detailtabelweergave** op Filters klikt, kunt u filteren  op dezelfde  criteria als in de rapportweergave, en ook op domeinen of geadresseerden, gescheiden door komma's.

> [!NOTE]
> Het **filter Domeinen** verwijst naar het URL-domein dat wordt weergegeven in de rapportresultaten. 

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="additional-reports-to-view"></a>Extra rapporten om te bekijken

Naast de rapporten die in dit artikel worden beschreven, zijn er nog verschillende andere rapporten beschikbaar, zoals wordt beschreven in de volgende tabel:

****

|Rapport|Onderwerp|
|---|---|
|**Verkenner** (Microsoft Defender voor Office 365-abonnement 2) of **realtime detecties** (Microsoft Defender voor Office 365-abonnement 1)|[Bedreigingsverkenner (en realtime detecties)](threat-explorer.md)|
|**Beveiligingsrapporten voor** e-mail, zoals het rapport Belangrijkste afzenders en geadresseerden, het rapport Spoof-e-mail en het rapport Spamdetectie.|[Beveiligingsrapporten voor e-mail weergeven in het & compliancecentrum](view-email-security-reports.md)|
|**E-mailstroomrapporten,** zoals het rapport Doorsturen, het statusrapport Mailflow en het rapport Belangrijkste afzenders en geadresseerden.|[E-mailstroomrapporten weergeven in het & compliancecentrum](view-mail-flow-reports.md)|
|**URL-trace voor veilige koppelingen** (alleen PowerShell). In de uitvoer van deze cmdlet ziet u de resultaten van acties voor veilige koppelingen van de afgelopen zeven dagen.|[Get-UrlTrace](https://docs.microsoft.com/powershell/module/exchange/get-urltrace)|
|**Verkeersresultaten voor EOP en Microsoft Defender voor Office 365** (alleen PowerShell). De uitvoer van deze cmdlet bevat informatie over domein, datum, evenementtype, richting, actie en aantal berichten.|[Get-MailTrafficATPReport](https://docs.microsoft.com/powershell/module/exchange/get-mailtrafficatpreport)|
|**E-maildetailrapporten voor EOP- en Defender voor Office 365-detecties** (alleen PowerShell). De uitvoer van deze cmdlet bevat details over schadelijke bestanden of URL's, phishingpogingen, imitatie en andere potentiële bedreigingen in e-mail of bestanden.|[Get-MailDetailATPReport](https://docs.microsoft.com/powershell/module/exchange/get-maildetailatpreport)|
|

## <a name="what-permissions-are-needed-to-view-the-defender-for-office-365-reports"></a>Welke machtigingen zijn nodig om de Defender voor Office 365-rapporten weer te geven?

Als u de rapporten in dit artikel wilt bekijken en gebruiken, moet u lid zijn van een van de volgende rollengroepen in het & Compliancecentrum:

- **Organisatiebeheer**
- **Beveiligingsbeheerder**
- **Beveiligingslezer**
- **Globale lezer**

Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

**Opmerking:** als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen in het beveiligings- & compliancecentrum en machtigingen voor andere functies in Microsoft 365.  Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="what-if-the-reports-arent-showing-data"></a>Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?

Als u geen gegevens ziet in uw Defender voor Office 365-rapporten, controleert u of uw beleid correct is ingesteld. Er moeten beleidsregels voor [](set-up-atp-safe-attachments-policies.md) [veilige](set-up-atp-safe-links-policies.md) koppelingen en veilige bijlagen zijn gedefinieerd om Defender voor Office 365-beveiliging te kunnen gebruiken. Zie ook [Beveiliging tegen ongewenste e-mail en malware.](anti-spam-and-anti-malware-protection.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Slimme rapporten en inzichten in het beveiligings- & compliancecentrum](reports-and-insights-in-security-and-compliance.md)

[Rolmachtigingen (Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#role-permissions)
