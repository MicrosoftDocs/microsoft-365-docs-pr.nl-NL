---
title: E-mailstroomrapporten weergeven in het Security & Compliance Center
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
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over het zoeken en gebruiken van beveiligingsrapporten voor e-mailstromen voor uw organisatie. E-mailstroomrapporten zijn beschikbaar in het Security & Compliance Center.
ms.custom: ''
ms.openlocfilehash: 70c96bb4f43edb80f98fdc98aa173fed9e54e7d7
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937180"
---
# <a name="view-mail-flow-reports-in-the-security--compliance-center"></a>E-mailstroomrapporten weergeven in het Security & Compliance Center

Naast de [e-mailstroominzichten](mail-flow-insights-v2.md) die beschikbaar zijn in het Security & Compliance Center, zijn er ook verschillende e-mailstroomrapporten beschikbaar om u te helpen uw Microsoft 365-organisatie te controleren. Als u over de [benodigde machtigingen](#what-permissions-are-needed-to-view-these-reports)beschikt, u deze rapporten bekijken in het Security & Compliance Center <https://office.protection.com> door naar Dashboard **Rapporten** te gaan \> **Dashboard**. Als u rechtstreeks naar het dashboard van rapporten wilt gaan, opent <https://office.protection.office.com/insightdashboard> u .

![Dashboard Rapporten in het Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Connectorrapport

In **het rapport Connector** wordt de e-mailstroomactiviteit weergegeven op de [inkomende en uitgaande connectoren](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.

Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Rapportendashboard** \> **Dashboard** en selecteert u **Connector-rapport**. Open <https://protection.office.com/reportv2?id=ConnectorReport> .

![Object Connectorrapport in het dashboard Rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Rapportweergave voor het connector-rapport

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven op: e-mailstroom**: Deze grafiek toont het aantal binnenkomende en uitgaande berichten, georganiseerd door:

  - **Totaal**
  - **Van het internet zonder connector**
  - **Naar het internet zonder connector**
  - Een specifieke connector die u hebt geconfigureerd.
  
  Als u de gegevens in de grafiek wilt isoleren, gebruikt u de **gegevens weergeven voor** het besturingselement om een van deze opties of **Alle e-mailstroom**te selecteren.

  ![Gegevens per e-mailstroom weergeven in het connectorrapport](../../media/connector-report-view-data-by-mail-flow.png)

- **Gegevens weergeven door: TLS-gebruik**: deze grafiek toont het percentage TLS-versiegebruik (Transport Layer Security) voor e-mailstroom.

  Als u de gegevens in de grafiek wilt isoleren, gebruikt u de **gegevens weergeven voor** het besturingselement om een van de volgende opties te selecteren:

  - **Alle e-mailstroom**
  - **Van het internet zonder connector**
  - **Naar het internet zonder connector**
  - Een specifieke connector die u hebt geconfigureerd.

  ![Gegevens weergeven op TLS-gebruik in het connector-rapport](../../media/connector-report-view-data-by-tls-usage.png)

Als u op **Filters** in een rapportweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.

### <a name="details-table-view-for-the-connector-report"></a>Tabelweergave Details voor het connectorrapport

Als u op **tabel Details weergeven** klikt in een rapportweergave, wordt de volgende informatie weergegeven:

- **Datum**
- **Verbindingsrichting en -naam**
- **Connectortype**
- **Gedwongen TLS?**: De waarde **Waar** of **Onwaar**.
- **Geen TLS** (percentage)
- **TLS 1.0** (percentage)
- **TLS 1.1** (percentage)
- **TLS 1.2** (percentage)
- **Volume**: Het aantal berichten.

Als u op **Filters** in een tabelweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="exchange-transport-rule-report"></a>Rapport over de regel van exchange-transport

Het **regelrapport Exchange-transport** bevat het effect van e-mailstroomregels (ook wel transportregels genoemd) op inkomende en uitgaande berichten in uw organisatie.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center](https://protection.office.com), gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Exchange Transport-regel**. Open <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Widget Transportregel uitwisselen in het dashboard Rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Rapportweergave voor het regelrapport Exchange-transport

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens bekijken door: Transportregels** \> uitwisselen **Uitsplitsen op: Richting**: Deze grafiek toont het aantal **binnenkomende** en **uitgaande** berichten dat door transportregels is beïnvloed.

- **Gegevens bekijken door: Transportregels** \> uitwisselen **Opsplitsen door: Ernst:** Deze grafiek toont het aantal **hoge ernst** en **gemiddelde ernst,** en **lage ernst** berichten. U stelt het ernstniveau in als een actie in de regel **(Controleer deze regel met ernstniveau** of _SetAuditSeverity)._ Zie Acties van [de mailstroomregel in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)voor meer informatie.

- **Gegevens bekijken door: DLP Exchange-transportregels** \> **Uitsplitsen door: Richting**: Deze grafiek toont het aantal **binnenkomende** en **uitgaande** berichten die zijn beïnvloed door de transportregels voor gegevensverliespreventie (DLP). U de grafiek verder verfijnen door de volgende opties te selecteren:

  - **Gegevens weergeven voor: alle DLP-transportregels**
  - **Gegevens weergeven voor: gecompromitteerde gebruikers**
  - **Gegevens weergeven voor: Laag volume van de gedetecteerde inhoud us Patriot Act**

- **Gegevens bekijken door: DLP Exchange-transportregels** \> **Afbreken door: Richting**: Deze weergave toont het aantal **hoge ernst** en **gemiddelde ernst**en berichten met een lage **ernst** die zijn beïnvloed door DLP-transportregels. U de grafiek verder verfijnen door de volgende opties te selecteren:

  - **Gegevens weergeven voor: alle DLP-transportregels**
  - **Gegevens weergeven voor: gecompromitteerde gebruikers**
  - **Gegevens weergeven voor: Laag volume van de gedetecteerde inhoud us Patriot Act**

Als u op **Filters** in een rapportweergave klikt, u de resultaten wijzigen met de volgende filters::

- **Begindatum** en **einddatum**
- Richtingswaarden
- Ernstwaarden

![Rapportweergave in het regelrapport Exchange-transport](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Tabelweergave details voor het regelrapport Exchange-transport

Als u op **tabel Details weergeven**klikt, is de weergegeven informatie afhankelijk van de grafiek die u bekeet:

- **Gegevens bekijken door: Exchange Transport rules**:

  - **Datum**
  - **Transportregel**
  - **Onderwerp**
  - **Adres afzender**
  - **Adres van de geadresseerde**
  - **Ernst**
  - **Richting**

- **Gegevens bekijken door: DLP Exchange transportregels**:

  - **Datum**
  - **DLP-beleid**
  - **Transportregel**
  - **Onderwerp**
  - **Adres afzender**
  - **Adres van de geadresseerde**
  - **Ernst**
  - **Richting**

Als u op **Filters** in een tabelweergave voor details klikt, u de resultaten wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Richtingswaarden
- Ernstwaarden

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="forwarding-report"></a>Rapport doorsturen

In **het rapport Doorsturen** worden automatisch doorgestuurde berichten van uw organisatie weergegeven naar externe domeinen vanuit Exchange Online-postvakken. Doorgestuurde berichten kunnen een beveiligings- of nalevingsrisico vormen en kunnen duiden op een gecompromitteerd account.

Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** en \> **Dashboard** selecteert u **Rapport Doorsturen**. Open <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Rapportobject doorsturen in het dashboard Rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Rapportweergave voor het rapport Doorsturen

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven voor: Doorstuurmethoden**: De volgende methoden worden weergegeven:

  - **Transportregel**: Ook wel [regels voor e-mailstroom genoemd](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules).
  - **Postvakregel**: Ook wel [inboxregels genoemd](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59).

  ![Weergave Methoden doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarding-methods.png)

- **Gegevens weergeven voor: Domeinen doorsturen**: in deze weergave worden de domeinen van de ontvanger weergegeven die de bestemmingen zijn voor doorsturen.

  ![Domeinenweergave doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarding-domains.png)

- **Gegevens weergeven voor: Expediteurs**: De volgende expediteurs worden weergegeven:

  - **Transportregel**
  - Het postvak dat de regel Postvak IN bevat.

  ![Weergave Doorstuuraars in het rapport Doorsturen](../../media/forwarding-report-forwarders.png)

Als u op **Filters** in een rapportweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.

### <a name="details-table-view-for-the-forwarding-report"></a>Tabelweergave Details voor het rapport Doorsturen

Als u op **tabel Details weergeven** klikt in een rapportweergave, wordt de volgende informatie weergegeven:

- **Doorstuuraars**: de **regel waardetransport** of het postvak dat de regel Postvak IN doorstuurt.
- **Type doorsturen**: de **regel waardepostvak** of **transportregel**.
- **Naam van geadresseerde**
- **Geadresseerdendomein**
- **Details**: dit is de GUID-waarde van de e-mailstroomregel of de regelwaarde RuleIdentity van de regel Postvak IN.
- **Tellen**
- **Eerste termijn**

Als u op **Filters** in een tabelweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="mailflow-status-report"></a>Mailflow-statusrapport

Het **e-mailstatusrapport** is vergelijkbaar met het [e-mailrapport Verzonden en ontvangen,](#sent-and-received-email-report)met aanvullende informatie over e-mail die is toegestaan of geblokkeerd op de rand. Dit is het enige rapport dat randbeschermingsinformatie bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat deze wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP).

Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** en \> **Dashboard** selecteert u **het statusrapport van Mailflow**. Als u rechtstreeks naar het statusrapport Van de **e-mailstroom wilt**gaan, opent u <https://protection.office.com/mailflowStatusReport> .

![Object Mailflow-statusrapport in het dashboard Rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Tekstweergave voor het statusrapport Mailflow

Wanneer u het rapport opent, wordt het tabblad **Type** standaard geselecteerd. Standaard bevat deze weergave een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:

- **Datum**: De laatste 7 dagen.
- **Richting**:

  - **Inkomende**
  - **Uitgaande**
  - **Intra-org** (apart geteld van **Inbound** en **Outbound)**

- **Type**:

  - **Goede e-mail**
  - **Malware**
  - **Spam**
  - **Randbescherming**
  - **Regelberichten**
  - **Phishing-e-mail**

De grafiek wordt georganiseerd door de **waarden type.**

U deze filters wijzigen door op **Filter** te klikken of door op een waarde in de grafieklegenda te klikken.

De gegevenstabel bevat de volgende gegevens:

- **Richting**
- **Type**
- **24 uur**
- **3 dagen**
- **7 dagen**
- **15 dagen**
- **30 dagen**

Als u op **Een categorie kiezen voor meer details**klikt, u kiezen uit de volgende waarden:

- **Phishing-e-mail:** deze selectie neemt u mee naar het [statusrapport bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)
- **Malware in e-mail**: Deze selectie neemt u mee naar het [statusrapport bedreigingsbescherming.](view-email-security-reports.md#threat-protection-status-report)
- **Spamdetecties**: Deze selectie neemt u mee naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)
- **Edge geblokkeerde spam**: Deze selectie neemt je mee naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)

**Uitvoer**:

Voor de detailweergave u alleen gegevens voor één dag exporteren. Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.

Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen. Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.

![Tekstweergave in het statusrapport Mailflow ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Richtingsweergave voor het estroomstatusrapport

Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters in de weergave **Type** gebruikt.

De grafiek wordt georganiseerd op **richtingswaarden.**

U deze filters wijzigen door op **Filter** te klikken of door op een waarde in de grafieklegenda te klikken. Dezelfde filters uit de weergave **Type** worden gebruikt.

De gegevenstabel bevat dezelfde informatie uit de weergave **Type.**

De **categorie Een categorie kiezen voor meer details beschikbare** selecties en gedrag zijn hetzelfde als de weergave **Type.**

**Uitvoer**:

Voor de detailweergave u alleen gegevens voor één dag exporteren. Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.

Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen. Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden er meerdere CSV-bestanden gemaakt.

![Richtingsweergave in het estroomstatusrapport ](../../media/mail-flow-status-report-direction-view.png)

## <a name="sent-and-received-email-report"></a>Verzonden en ontvangen e-mailrapport

Het **verzonden en ontvangen e-mailrapport** is een slim rapport met informatie over inkomende en uitgaande e-mail, waaronder spamdetecties, malware en e-mail die als 'goed' zijn geïdentificeerd. Het verschil tussen dit rapport en het [e-mailstatusrapport](#mailflow-status-report) is: dit rapport bevat geen gegevens over berichten die zijn geblokkeerd door randbeveiliging.

De totaalweergave en de detailweergave van het rapport maken 90 dagen filteren mogelijk.

Als u het rapport wilt bekijken, opent u het [Beveiligingscentrum & Compliance Center,](https://protection.office.com)gaat u naar **Dashboard Rapporten** \> **Dashboard** en selecteert u **Verzonden en ontvangen e-mail**. Open <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Verzonden en ontvangen e-mailwidget in het dashboard Rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Rapportweergave voor het e-mailrapport Verzonden en ontvangen

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Uitsplitsen op: Tekst:** De grafiek toont alle beschikbare categorieën:

  - **Totaal**
  - **Goede e-mail**
  - **Malware (anti-malware)** (EOP)
  - **Spamdetecties**
  - **Regelberichten**
  - **Geavanceerde malware** (AtP voor Office 365)

  Wanneer u gedurende een dag (gegevenspunt) in de grafiek houdt, u details voor die dag zien.

  ![Typ weergave in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-type-view.png)

- **Uitsplitsen op: Richting**: De grafiek toont **totaal-** en **binnenkomende**en **uitgaande** gegevens. Wanneer u gedurende een dag (gegevenspunt) in de grafiek houdt, u details voor die dag zien.

  ![Richtingsweergave in het e-mailrapport Verzonden en ontvangen](../../media/sent-and-received-email-report-direction-view.png)

- **Inzoomen op** \> **Malware (anti-malware)**: Deze selectie neemt u mee naar de [malware detectie in e-mail rapport](view-email-security-reports.md#malware-detection-in-email-report).

- **Inzoomen op** \> **Spamdetecties)**: Deze selectie neemt je mee naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)

Als u op **Filters** in een rapportweergave klikt, u de resultaten wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Richtingswaarden
- Tekstwaarden

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Tabelweergave details voor het e-mailrapport Verzonden en ontvangen

Als u op **Tabel Details weergeven** klikt in de **tabel Uitsplitsen door: Richting** of **Opsplitsen door:** Richtingsweergave, wordt de volgende informatie weergegeven:

- **Datum (UTC)**
- **Type**
- **Richting**
- **Aantal berichten**

Als u op **Filters** in een tabelweergave voor details klikt, u de resultaten wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Richtingswaarden
- Tekstwaarden

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="top-senders-and-recipients-report"></a>Rapport Top afzenders en ontvangers

Het rapport **Top afzenders en geadresseerden** is een cirkeldiagram met uw beste e-mail afzenders en ontvangers.

Als u het rapport wilt bekijken, opent u het [Security & Compliance Center,](https://protection.office.com)gaat u naar **Reports** \> **Rapportendashboard** en selecteert u **Top afzenders en ontvangers**. Open <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Widget Top afzenders en geadresseerden in het dashboard Rapporten](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Rapportweergave voor het rapport Top afzenders en geadresseerden

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven voor \> topmailzenders**
- **Gegevens weergeven voor \> tope-mailontvangers**
- **Gegevens weergeven voor \> topspamontvangers**
- **Gegevens weergeven voor \> Top malware ontvangers** (EOP)
- **Gegevens weergeven voor \> Top malware ontvangers (ATP)** (Office 365 ATP)

De samenstelling van het cirkeldiagram wordt gewijzigd op basis van deze selecties.

Wanneer u over een wig in het cirkeldiagram beweegt, ziet u een aantal verzonden of ontvangen berichten.

Als u op **Filters** in een rapportweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.

![Cirkeldiagram in rapportweergave in het rapport Top afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Tabelweergave details voor het rapport Top afzenders en geadresseerden

Als u op **tabel Details weergeven**klikt, is de weergegeven informatie afhankelijk van de grafiek die u bekeet:

- **Gegevens weergeven voor \> topmailzenders**

  - **Top e-mail afzenders**
  - **Tellen**

- **Gegevens weergeven voor \> tope-mailontvangers**

  - **Topontvangers voor e-mail**
  - **Tellen**

- **Gegevens weergeven voor \> topspamontvangers**

  - **Top spam ontvangers**
  - **Tellen**

- **Gegevens weergeven voor \> Top malware ontvangers** (EOP)

  - **Top malware ontvangers**
  - **Tellen**

- **Gegevens weergeven voor \> Top malware ontvangers (ATP)** (Office 365 ATP)

  - **Top malware ontvangers (ATP)**
  - **Tellen**

Als u op **Filters** in een tabelweergave klikt, u een datumbereik opgeven met **begindatum** en **einddatum**.

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven**.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welke machtigingen zijn nodig om deze rapporten weer te geven?

Als u de rapporten wilt weergeven en gebruiken, moet u lid zijn van de opgegeven rolgroep in het Security & Compliance Center **en** in Exchange Online.

- In het Security & Compliance Center moet u lid zijn van een van de volgende rolgroepen:

  -Organisatiebeheer

  -Beveiligingsbeheerder (u dit ook doen in het [Azure Active Directory-beheercentrum](https://aad.portal.azure.com) -Security Reader

  Zie [Machtigingen in het Beveiligings- & compliancecentrum](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) voor meer informatie.

- In Exchange Online moet u lid zijn van een van de volgende rolgroepen:

  -Organisatiebeheer

  -Alleen-weergeven organisatiebeheer

  -Ontvangers alleen weergeven

  -Compliance Management

Zie [Machtigingen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) en [Rolgroepen beheren in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups)voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

[Slimme rapporten en inzichten in het Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)

[E-mailbeveiligingsrapporten weergeven in het Security & Compliance Center](view-email-security-reports.md)
