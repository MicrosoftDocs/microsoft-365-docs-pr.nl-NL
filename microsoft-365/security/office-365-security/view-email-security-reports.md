---
title: E-mailbeveiligingsrapporten bekijken in het Beveiligings- en compliancecentrum
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Meer informatie over het zoeken naar en gebruiken van e-mailbeveiligingsrapporten voor uw organisatie. E-mailbeveiligingsrapporten zijn beschikbaar in het Security & Compliance Center.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6fbaa0b57c888f5eaf90a2a30d1850a145c33a80
ms.sourcegitcommit: 8595cb9ffe0ca5556080f24224182381e1d880de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/03/2020
ms.locfileid: "45035727"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>E-mailbeveiligingsrapporten bekijken in het Beveiligings- en compliancecentrum

Er zijn verschillende rapporten beschikbaar in het [Security & Compliance Center](https://protection.office.com) om u te laten zien hoe e-mailbeveiligingsfuncties, zoals anti-spam, anti-malware en versleutelingsfuncties in Microsoft 365 uw organisatie beschermen. Als u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-these-reports)beschikt, u deze rapporten bekijken in het Security & Compliance Center door naar **Dashboard Rapporten** te gaan \> **Dashboard**. Als u rechtstreeks naar het dashboard van rapporten wilt gaan, opent <https://protection.office.com/insightdashboard> u .

![Dashboard Rapporten in het Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Gecompromitteerde gebruikers melden

> [!NOTE]
> Dit rapport is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken. Het is niet beschikbaar in zelfstandige Exchange Online Protection (EOP) organisaties zonder Exchange Online mailboxen.

In het rapport **gecompromitteerde gebruikers** wordt het aantal gebruikersaccounts weergegeven dat in de afgelopen 7 dagen als **Verdacht** of **Beperkt is** gemarkeerd. Rekeningen in een van deze staten zijn problematisch of zelfs gecompromitteerd. Bij veelvuldig gebruik u het rapport gebruiken om pieken en zelfs trends in verdachte of beperkte accounts te herkennen. Zie [Reageren op een gecompromitteerd e-mailaccount](responding-to-a-compromised-email-account.md)voor meer informatie over gecompromitteerde gebruikers.

De totaalweergave toont gegevens over de afgelopen 90 dagen en de detailweergave toont gegevens van de afgelopen 30 dagen.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Gecompromitteerde gebruikers**. Open <https://protection.office.com/reportv2?id=CompromisedUsers> .

U zowel de grafiek als de detailtabel filteren door op **Filters** te klikken en een of meer van de volgende waarden te selecteren:

- **Begindatum** en **einddatum**

- **Verdacht**: Het gebruikersaccount heeft verdachte e-mail verzonden en loopt het risico geen e-mail te verzenden.

- **Beperkt**: Het gebruikersaccount is beperkt tot het verzenden van e-mail als gevolg van zeer verdachte patronen.

![De gecompromitteerde gebruikers melden zoals het verschijnt in Microsoft 365](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

Als u op **tabel Details weergeven**klikt, ziet u de volgende details:

- **Aanmaaktijd**
- **Gebruikersnaam**
- **Actie**

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="encryption-report"></a>Versleutelingsrapport

Het **versleutelingsrapport** is beschikbaar in EOP (abonnementen met postvakken in Exchange Online of standalone EOP zonder Exchange Online-postvakken). Het beveiligingsteam van uw organisatie kan informatie in dit rapport gebruiken om patronen te identificeren en proactief beleid voor gevoelige e-mailberichten toe te passen of aan te passen. Bijvoorbeeld:

- Als u een groot aantal e-mailberichten ziet die door gebruikers zijn versleuteld, u een versleutelingsbeleid toevoegen om versleuteling voor bepaalde use cases te automatiseren. Zie [Regels voor e-mailstroom definiëren om e-mailberichten te versleutelen in Microsoft 365 voor](../../compliance/define-mail-flow-rules-to-encrypt-email.md)meer informatie.

- Als u een aantal versleutelingssjablonen beschikbaar hebt, maar niemand ze gebruikt, u onderzoeken of gebruikers functietraining nodig hebben.

De geaggregeerde weergave maakt het mogelijk om de afgelopen 90 dagen te filteren, terwijl de detailweergave het mogelijk maakt om 10 dagen te filteren.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Versleutelingsrapport**. Open <https://protection.office.com/reportv2?id=EncryptionReport> .

Zie [E-mailversleuteling in Microsoft 365](../../compliance/email-encryption.md)voor meer informatie over versleuteling.

### <a name="report-view-for-the-encryption-report"></a>Rapportweergave voor het versleutelingsrapport

U de volgende filters in de grafiek gebruiken:

- **Gegevens weergeven door: Message Encryption Report** and **Break down by: Encryption method:** The following encryption methods are available:

  - **Versleuteling door gebruiker**
  - **Versleuteling op beleid**

  Als u op **Filters**klikt, u de grafiek wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Versleutelingsmethode.
  - Versleutelingssjabloon.

- **Gegevens weergeven door: Message Encryption Report** and **Break down by: Encryption template**: The following encryption methods are available:

  - **Niet doorsturen**
  - **Alleen versleutelen**
  - **OME vorige**
  - **Aangepaste**

  Als u op **Filters**klikt, u de grafiek wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Versleutelingsmethode
  - Versleutelingssjabloon

- **Gegevens weergeven door: Top 5 geadresseerde domeinen**: in deze weergave ziet u een cirkeldiagram met verzonden berichttellingen voor de top 5 geadresseerde domeinen.

  Als u op **Filters**klikt, u een **begindatum** en **einddatum**selecteren.

### <a name="details-table-view-for-the-encryption-report"></a>Tabelweergave details voor het rapport Versleuteling

Als u op **tabel Details weergeven**klikt, is de weergegeven informatie afhankelijk van de grafiek die u bekeet:

- **Uitsplitsen door: Versleutelingsmethode** of **Opsplitsen door: Versleutelingssjabloon**: De volgende informatie wordt weergegeven:

  - **Datum**
  - **Adres afzender**
  - **Versleutelingssjabloon**
  - **Versleutelingsmethode**
  - **Adres van de geadresseerde**
  - **Onderwerp**

- **Gegevens bekijken door: Top 5 geadresseerde domeinen:**

  - **Datum**
  - **Geadresseerdendomein**
  - **Aantal berichten**
  
Als u op **Filters** in een tabelweergave voor details klikt, u de resultaten wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Versleutelingsmethode
- Versleutelingssjabloon

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="mailflow-status-report"></a>Mailflow-statusrapport

Het **Mailflow-statusrapport** bevat informatie over malware, spam, phishing en geblokkeerde berichten. Zie [Het statusrapport van Mailflow](view-mail-flow-reports.md#mailflow-status-report)voor meer informatie .

## <a name="malware-detection-in-email-report"></a>Detectie van malware in e-mailrapport

De **malware detecties in e-mail** rapport toont informatie over malware detecties in inkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP). Zie [Anti-malwarebescherming in EOP](anti-malware-protection.md)voor meer informatie over malwarebescherming in EOP.

 Het filter voor de totale weergave biedt 90 dagen, terwijl het detailtabelfilter slechts 10 dagen toestaat.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Malwaredetecties in e-mail**. Open <https://protection.office.com/reportv2?id=MalwareDetections> .

![Malwaredetecties in e-mailwidget in het dashboard Rapporten](../../media/malware-detections-widget.png)

U zowel de grafiek als de detailtabel filteren door op **Filters** te klikken en het selecteren van:

- **Begindatum** en **einddatum**
- **Inkomende**
- **Uitgaande**

![Rapportweergave in de malwaredetectie in e-mailrapport](../../media/malware-detections-report-view.png)

Als u op **tabel Details weergeven**klikt, ziet u de volgende details:

- **Datum**
- **Adres afzender**
- **Adres van de geadresseerde**
- **Bericht-ID**
- **Onderwerp**
- **Bestandsnaam**
- **Naam malware**

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="sent-and-received-email-report"></a>Verzonden en ontvangen e-mailrapport

Het **verzonden en ontvangen e-mailrapport** bevat informatie over malware, spam, regels voor e-mailstromen (ook wel transportregels genoemd) en geavanceerde malwaredetecties nadat e-mail de service is binnengekomen. Zie [Verzonden en ontvangen e-mailrapport](view-mail-flow-reports.md#sent-and-received-email-report)voor meer informatie.

## <a name="spam-detections-report"></a>Rapport spamdetecties

Het rapport **Spamdetecties** toont spam-e-mailberichten die door EOP zijn geblokkeerd. Berichten worden individueel geteld, niet per ontvanger. Als bijvoorbeeld hetzelfde spambericht naar 100 ontvangers in uw organisatie is verzonden, telt dit als één bericht.

De geaggregeerde weergave maakt het mogelijk om 90 dagen te filteren, terwijl de detailtabel het filteren van 10 dagen mogelijk maakt.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Spamdetecties**. Open <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget Spamdetecties in het dashboard Rapporten](../../media/spam-detections-report-widget.png)

Zie [Anti-spambescherming in EOP](anti-spam-protection.md)voor meer informatie over antispambeveiliging.

### <a name="report-view-for-the-spam-detections-report"></a>Rapportweergave voor het rapport Spamdetecties

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Uitsplitsen op: Actie**: De volgende gebeurtenistypen worden weergegeven:

  - **Spam-inhoud gefilterd**
  - **Spam IP-blok**
  - **Spam envelop blok**
  - **Spam DBEB filter**: Directory based edge blocking (DBEB) Spam DBEB filter : Directory based edge blocking (DBEB) Spam DBEB filter : Directory based edge blocking (DBEB) Spam DB

  Wanneer u de muisaanwijzer gedurende een dag (gegevenspunt) in de grafiek houdt, u zien hoeveel items die dag zijn geblokkeerd en hoe deze items zijn gecategoriseerd.

  ![Actieweergave in het rapport Spamdetecties](../../media/spam-detections-report-action-view.png)

- **Afsplitsen door:Richting**: De volgende richtingen worden weergegeven:

  - **Inkomende**
  - **Uitgaande**

  ![Richtingsweergave in het rapport Spamdetecties](../../media/spam-detections-report-direction-view.png)

Als u op **Filters** in een rapportweergave klikt, u de resultaten wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Richtingswaarden
- Gebeurtenistypewaarden

### <a name="details-table-view-for-the-spam-detections-report"></a>Tabelweergave details voor het rapport Spamdetecties

Als u in een rapportweergave op **tabel Details weergeven** klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Adres afzender**
- **Adres van de geadresseerde**
- **Gebeurtenistype**
- **Actie**
- **Onderwerp**

Als u op **Filters** in een tabel met details klikt, u de resultaten wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Richtingswaarden
- Gebeurtenistypewaarden

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="spoof-detections-report"></a>Rapport spoofdetecties

De **Spoof detecties** rapport laat zien hoeveel spoof e-mailberichten werden gedetecteerd, en van die, welke werden beschouwd als "goed" (spoof e-mail gedaan om legitieme zakelijke redenen). Zie [Anti-spoofing-beveiliging in EOP](anti-spoofing-protection.md)voor meer informatie over spoofing.

De totale weergave van het rapport maakt het mogelijk om 90 dagen te filteren, terwijl de detailweergave slechts tien dagen filtering mogelijk maakt.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Spoofdetecties**. Open <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget Spoofdetecties in het dashboard Rapporten](../../media/spoof-detections-widget.png)

Wanneer u de muisaanwijzer gedurende een dag (gegevenspunt) in de grafiek houdt, u zien hoeveel spoofberichten zijn verzonden.

U zowel de grafiek als de detailtabel filteren door op **Filters** te klikken en een of meer van de volgende waarden te selecteren:

- **Begindatum** en **einddatum**

- **Goede e-mail**

- **Gevangen als spam**

![Rapportweergave in het rapport Spoofdetecties](../../media/spoof-detections-report-view.png)

Als u op **tabel Details weergeven**klikt, ziet u de volgende details:

- **Datum**
- **Vervalste afzender**
- **Echte afzender**
- **IP-adres van afzender**
- **Actie**
- **Aantal berichten**

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="threat-protection-status-report"></a>Statusrapport voor bedreigingsbescherming

Het statusrapport **voor bedreigingsbescherming** is beschikbaar in zowel EOP als Office 365 ATP; de rapporten bevatten echter verschillende gegevens. EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die in e-mail is gedetecteerd, maar geen informatie over [schadelijke bestanden die zijn gedetecteerd in SharePoint Online, OneDrive of Microsoft Teams.](atp-for-spo-odb-and-teams.md) Zie Rapporten voor Geavanceerde bedreigingsbeveiliging van [Office 365 weergeven voor](view-reports-for-atp.md)meer informatie over ATP-rapporten van Office 365 .

Dit is een slim rapport met schadelijke e-mail die is gedetecteerd en geblokkeerd, en het stelt beveiligingsbeheerders in staat om trends te identificeren of te bepalen of het organisatiebeleid moet worden aangepast.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **de status van bedreigingsbeveiliging**. Open <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .

![Widget Statusstatus bedreiging in het dashboard Rapporten](../../media/threat-protection-status-report-widget.png)

Standaard worden in de grafiek gegevens van de afgelopen 7 dagen weergegeven. Als u op **Filters**klikt, u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen worden beperkt tot 30 dagen). Met de tabelweergave voor details u 30 dagen filteren.

### <a name="report-view-for-the-threat-protection-status-report"></a>Rapportweergave voor het statusrapport Bedreigingsbeveiliging

De volgende weergaven zijn beschikbaar:

- **Gegevens bekijken door: Overzicht**: De volgende detectie-informatie wordt weergegeven:

  - **E-mail malware**
  - **E-mail phish**
  - **Inhoudsmalware**

  ![Overzichtsweergave in het rapport Status bedreigingsbeveiliging](../../media/threat-protection-status-report-overview-view.png)

- **Gegevens weergeven op: Inhoud \> Malware**<sup>1</sup>: De volgende informatie wordt weergegeven voor AtP-organisaties van Office 365:

  - **Anti-malware motor**
  - **Bestandsontploffing**

  ![Weergave voor malware in inhoud in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

- **Opsplitsen door: Detectietechnologie** en **Bekijk gegevens door: E-mail \> Phish**: De volgende informatie wordt getoond:

  - **ATP-gegenereerde URL reputatie**<sup>1</sup>
  - **Geavanceerd phish-filter**
  - **Anti-spoof: DMARC-storing**
  - **Anti-spoof: Intra-org**
  - **Anti-spoof: extern domein**
  - **Merkimitatie**
  - **Domeinimitatie**<sup>1</sup>
  - **EOP URL reputatie**
  - **Algemeen phish filter**
  - **Anderen**
  - **Phish ZAP**<sup>2</sup>
  - **URL-ontploffing**<sup>1</sup>
  - **Imitatie van de gebruiker**<sup>1</sup>

  ![Detectietechnologieweergave voor phishing-e-mail in het statusrapport bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Break down door: Detectie technologie** en **Bekijk gegevens door: E-mail \> Malware:** De volgende informatie wordt getoond:

  - **ATP-gegenereerde bestandsreputatie**<sup>1</sup>
  - **Anti-malware motor**<sup>1</sup>
  - **Blok van het bestandstype van antimalwarebeleid**
  - **Bestand detonatie**<sup>1</sup>
  - **Kwaadaardige bestandsreputatie**
  - **Malware ZAP**<sup>2</sup>
  - **Anderen**

  ![Detectietechnologieweergave voor malware in het statusrapport voor bedreigingsbescherming](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Opsplitsen op: Beleidstype** en **Gegevens weergeven door: E-mail \> Phish** of **Bekijk gegevens door: E-mail \> malware:** De volgende informatie wordt weergegeven:

  - **Anti-malware**
  - **Veilige bijlage**<sup>1</sup>
  - **Anti-phish**
  - **Anti-spam**
  - **Mailstroomregel** (ook wel een transportregel genoemd)
  - **Anderen**

  ![Beleidstypeweergave voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Opsplitsen door: Leveringsstatus** en **Gegevens weergeven door: E-mail \> Phish** of **Bekijk gegevens door: E-mail \> malware:** De volgende informatie wordt weergegeven:

  - **Levering is mislukt**
  - **Gedaald**
  - **Doorgestuurd**
  - **Gehost postvak: aangepaste map**
  - **Gehost postvak: verwijderde items**
  - **Gehost postvak: Postvak IN**
  - **Gehost postvak: ongewenste e-mail**
  - **On-premises server: geleverd**
  - **Quarantaine**

  ![Weergave leveringsstatus voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Office 365 ATP alleen

<sup>2</sup> Zero-hour auto purge (ZAP) is niet beschikbaar in standalone EOP (het werkt alleen in Exchange Online mailboxen).

Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Detectiewaarde
- **Beschermd door** (alleen Office 365 ATP): **ATP** of **EOP**. Houd er rekening mee dat deze filterbare eigenschap niet beschikbaar is in **weergavegegevens door: \> ContentMalware**.

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Tabelweergave details voor het statusrapport Bedreigingsbeveiliging

Als u op **tabel Details weergeven**klikt, is de weergegeven informatie afhankelijk van de grafiek die u bekeet:

- **Gegevens weergeven op: Inhoud \> Malware:**

  - **Datum**
  - **Locatie**
  - **Geregisseerd door**
  - **Naam malware**

- **Gegevens bekijken door: Overzicht**: Er is geen tabelknop **voor weergavedetails** beschikbaar.

- Alle andere grafieken:

  - **Datum**
  - **Onderwerp**
  - **Afzender**
  - **Geadresseerden**
  - **Gedetecteerd door**
  - **Leveringsstatus**
  - **Bron van compromissen**

Als u op **Filters**klikt, u het rapport wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Detectiewaarde
- **Beschermd door** (alleen Office 365 ATP): **ATP** of **EOP**. Houd er rekening mee dat deze filterbare eigenschap niet beschikbaar is in **weergavegegevens door: \> ContentMalware**.

## <a name="top-malware-report"></a>Top malware rapport

De **Top malware** rapport toont de verschillende soorten malware die werd gedetecteerd door [anti-malware bescherming in EOP](anti-malware-protection.md).

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Topmalware**. Open <https://protection.office.com/reportv2?id=TopMalware> .

![Top malware widget in het dashboard Rapporten](../../media/top-malware-report-widget.png)

Wanneer u boven een wig in het cirkeldiagram hangt, u de naam van een soort malware zien en hoeveel berichten zijn gedetecteerd als het hebben van die malware.

![Top malware rapport weergave](../../media/top-malware-report-view.png)

Als u op **tabel Details weergeven**klikt, ziet u de volgende details:

- **Top malware**
- **Tellen**

Als u op **Filters** klikt in de rapportweergave of de tabelweergave details, u een datumbereik opgeven met **begindatum** en **einddatum**.

## <a name="url-threat-protection-report"></a>URL-melding voor bedreigingsbeveiliging

> [!NOTE]
> Dit rapport is alleen beschikbaar in Office 365 Advanced Threat Protection (ATP). Bijvoorbeeld een Microsoft 365 E5-abonnement of een ATP-abonnement 1 of ATP-abonnement 2-add-on.

Het **URL-waarschuwingsrapport voor bedreigingsbeveiliging** biedt overzichten en trendweergaven voor gedetecteerde bedreigingen en acties die zijn uitgevoerd op URL-klikken als onderdeel van [ATP Safe Links](atp-safe-links.md). In dit rapport worden geen klikgegevens van gebruikers weergegeven waarbij het toegepaste beleid Voor veilige koppelingen de optie **Klikken van gebruikers niet bijhouden** is geselecteerd.

Als u het rapport wilt bekijken, opent u het [Beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** \> **Dashboard** en selecteert u **URL-beveiliging**. Open <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

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

### <a name="details-table-view-for-the-threat-protection-report"></a>Tabelweergave details voor het rapport dreigingsbeveiliging

Als u op **tabel Details weergeven**klikt, geeft het rapport een bijna realtime weergave van alle klikken die de afgelopen zeven dagen binnen de organisatie plaatsvinden met de volgende details:

- **Kliktijd**
- **Gebruiker**
- **Url**
- **Actie**
- **App**

Als u op **Filters** klikt in de tabelweergave details, u filteren op dezelfde criteria als in de rapportweergave, en ook op **domeinen** of **geadresseerden,** gescheiden door komma's.

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="user-reported-messages-report"></a>Rapport door door gebruikers gerapporteerde berichten

In het rapport **Door gebruikers gerapporteerde berichten** wordt informatie weergegeven over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishing-pogingen of goede e-mail met behulp van de [invoegtoepassing Rapportbericht](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in).

Details zijn beschikbaar voor elk bericht, inclusief de reden van de levering, een dergelijke uitzondering van het spambeleid of de regel voor de e-mailstroom die is geconfigureerd voor uw organisatie. Als u details wilt weergeven, selecteert u een item in de lijst met gebruikersrapporten en bekijkt u de informatie op de tabbladen **Overzicht** en **Details.**

![In het rapport Door gebruikers gerapporteerde berichten worden berichten weergegeven die gebruikers hebben gelabeld als ongewenste, niet ongewenste e-mail- of phishingpogingen.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Als u dit rapport wilt bekijken, gaat u in het [Security & Compliance Center](https://protection.office.com)een van de volgende handelingen uit:

- Ga **Threat management** naar \> **Dashboard** \> **Waarschuwingsbeheer**Dashboard Door gebruikers gerapporteerde berichten .

- Ga naar **door gebruikers** \> gerapporteerde berichten voor **Review** \> **bedreigingsbeheercontrole.**

![Kies in het Security & Compliance Center de gebruiker \> gerapporteerde berichten van Threat management Review \>](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Als u wilt dat het rapport Door de gebruiker gerapporteerde berichten correct werkt, **moet controleregistratie zijn ingeschakeld** voor uw Office 365-omgeving. Dit wordt meestal gedaan door iemand die de rol Controlelogboeken heeft toegewezen in Exchange Online. Zie [Microsoft 365-controlelogboek zoeken in- of uitschakelen](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off)voor meer informatie.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welke machtigingen zijn nodig om deze rapporten weer te geven?

Als u de rapporten wilt weergeven en gebruiken, moet u lid zijn van de opgegeven rolgroep in het Security & Compliance Center **en** in Exchange Online.

- In het Security & Compliance Center moet u lid zijn van een van de volgende rolgroepen:

  -Organisatiebeheer -Beveiligingsbeheerder (u dit ook doen in het [Azure Active Directory-beheercentrum](https://aad.portal.azure.com) -Security Reader

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) voor meer informatie.

- In Exchange Online moet u lid zijn van een van de volgende rolgroepen:

  -Organisatiebeheer -Alleen-weergave organisatiebeheer -Ontvangers alleen weergeven -Compliance Management

Zie [Machtigingen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) en [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie.

## <a name="what-if-the-reports-arent-showing-data"></a>Wat als de rapporten geen gegevens weergeven?

Als u geen gegevens in uw rapporten ziet, controleert u dubbel of uw beleid correct is ingesteld. Zie [Beschermen tegen bedreigingen](protect-against-threats.md)voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

[Bescherming tegen spam en malwarebestrijding in EOP](anti-spam-and-anti-malware-protection.md)

[Slimme rapporten en inzichten in het Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)
