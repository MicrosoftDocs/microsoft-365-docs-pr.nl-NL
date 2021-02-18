---
title: E-mailstroomrapporten weergeven in het dashboard Rapporten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer informatie krijgen over de e-mailstroomrapporten die beschikbaar zijn in het dashboard Rapporten in het & Compliancecentrum.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286715"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>E-mailstroomrapporten weergeven in het dashboard Rapporten in & Compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Naast de e-mailstroomrapporten die beschikbaar zijn in het [dashboard](mail-flow-insights-v2.md) E-mailstroom in het beveiligings- & Compliancecentrum, vindt u diverse aanvullende e-mailstroomrapporten in het dashboard Rapporten om u te helpen uw Microsoft 365-organisatie te bewaken.

Als u de [benodigde machtigingen hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken in het beveiligings- [& compliancecentrum](https://protection.office.com) door naar het dashboard Rapporten **te** \> **gaan.** Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://protection.office.com/insightdashboard> .

![Dashboard Rapporten in het beveiligings- & compliancecentrum](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Connectorrapport

Het **rapport Connector toont** de activiteit van de e-mailstroom op de binnenkomende en uitgaande [connectors](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die zijn geconfigureerd voor uw organisatie.

Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en **selecteert u het rapport Connector.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ConnectorReport> .

![Connectorrapportwidget in het dashboard Rapporten](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Rapportweergave voor het rapport Connector

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven op: E-mailstroom:** in deze grafiek ziet u het aantal inkomende en uitgaande berichten, ingedeeld in:

  - **Totaal**
  - **Van internet zonder een connector**
  - **Naar internet zonder een connector**
  - Een specifieke connector die u hebt geconfigureerd.

  Als u de gegevens in  de grafiek wilt isoleren, gebruikt u Gegevens voor besturingselementen tonen om een van deze opties of **Alle e-mailstroom te selecteren.**

  ![Gegevens weergeven per e-mailstroom in het rapport Connector](../../media/connector-report-view-data-by-mail-flow.png)

- **Gegevens weergeven met: TLS-gebruik:** in deze grafiek ziet u het percentage versiegebruik van TLS (Transport Layer Security) voor de e-mailstroom.

  Als u de gegevens in de grafiek wilt isoleren, gebruikt u gegevens voor **besturingselementen** om een van de volgende opties te selecteren:

  - **Alle e-mailstromen**
  - **Van internet zonder een connector**
  - **Naar internet zonder een connector**
  - Een specifieke connector die u hebt geconfigureerd.

  ![Gegevens weergeven op TLS-gebruik in het rapport Connector](../../media/connector-report-view-data-by-tls-usage.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

### <a name="details-table-view-for-the-connector-report"></a>Tabelweergave Details voor het rapport Connector

Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Richting en naam van verbindingslijn**
- **Type verbindingslijn**
- **Geforceerd TLS?**: De waarde **Waar** of **Onwaar.**
- **Geen TLS** (percentage)
- **TLS 1.0** (percentage)
- **TLS 1.1** (percentage)
- **TLS 1.2** (percentage)
- **Volume:** het aantal berichten.

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="exchange-transport-rule-report"></a>Exchange-transportregelrapport

Het **Exchange-transportregelrapport** toont het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.

Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en selecteert u de **Exchange-transportregel.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Exchange-transportregelwidget in het dashboard Rapporten](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Rapportweergave voor het Exchange-transportregelrapport

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens weergeven met: Exchange-transportregels** \> **Op te breken met: Richting:** in deze  grafiek ziet u het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door transportregels.

- **Gegevens weergeven op: Exchange-transportregels** \> **Op te breken door: Ernst:** in  deze grafiek ziet u het aantal berichten met hoge ernst en gemiddelde ernst **en** berichten met een **lage ernst.** U stelt het niveau van ernst in als een actie in de regel (**Controleer** deze regel met ernstniveau of _SetAuditSeverity)._ Zie [E-mailstroomregelacties in Exchange Online voor meer informatie.](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **Gegevens weergeven met: DLP Exchange-transportregels** \> **Op te delen met: Richting:** in deze  grafiek ziet u het aantal **inkomende** en uitgaande berichten dat is beïnvloed door DLP-transportregels (Data Loss Prevention). U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:

  - **Gegevens tonen voor: Alle DLP-transportregels**
  - **Gegevens tonen voor: gecompromitteerde gebruikers**
  - **Gegevens tonen voor: laag volume van gedetecteerde V.S. Act**

- **Gegevens weergeven met: DLP Exchange-transportregels** \> **Op te breken met: Richting:** in deze weergave ziet u  het aantal berichten met hoge ernst en gemiddelde ernst en berichten met lage ernst die zijn beïnvloed door DLP-transportregels.  U kunt de grafiek verder verfijnen door een van de volgende opties te selecteren:

  - **Gegevens tonen voor: Alle DLP-transportregels**
  - **Gegevens tonen voor: gecompromitteerde gebruikers**
  - **Gegevens tonen voor: laag volume van gedetecteerde V.S. Act**

Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** **en einddatum**
- Richtingswaarden
- Ernstwaarden

![Rapportweergave in het Exchange-transportregelrapport](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Detailtabelweergave voor het Exchange-transportregelrapport

Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:

- **Gegevens weergeven op: Exchange-transportregels:**

  - **Datum**
  - **Transportregel**
  - **Onderwerp**
  - **Adres afzender**
  - **Adres van geadresseerde**
  - **Ernst**
  - **Richting**

- **Gegevens weergeven met: DLP Exchange-transportregels:**

  - **Datum**
  - **DLP-beleid**
  - **Transportregel**
  - **Onderwerp**
  - **Adres afzender**
  - **Adres van geadresseerde**
  - **Ernst**
  - **Richting**

Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** **en einddatum**
- Richtingswaarden
- Ernstwaarden

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="forwarding-report"></a>Doorsturen-rapport

In **het rapport Doorsturen** worden de automatisch doorgestuurde berichten van uw organisatie naar externe domeinen vanuit Exchange Online-postvakken doorgestuurd. Doorgestuurde berichten kunnen een beveiligings- of nalevingsrisico vormen en kunnen een gekromd account aangeven.

Als u het rapport wilt bekijken, opent u het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en **selecteert u Rapport doorsturen.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Widget Rapport doorsturen in het dashboard Rapporten](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Rapportweergave voor het doorsturende rapport

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens tonen voor: Methoden voor doorsturen:** de volgende methoden worden weergegeven:

  - **Transportregel:** ook wel [e-mailstroomregels genoemd.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **Postvakregel:** ook wel regels [voor Postvak IN genoemd.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)

  ![Weergave doorsturenmethoden in het rapport Doorsturen](../../media/forwarding-report-forwarding-methods.png)

- **Gegevens weergeven voor: Doorsturen-domeinen:** in deze weergave ziet u de geadresseerdedomeinen die de bestemmingen voor doorsturen zijn.

  ![De weergave Doorsturen van domeinen in het rapport Doorsturen](../../media/forwarding-report-forwarding-domains.png)

- **Gegevens tonen voor: Doorgestuurde gebruikers:** de volgende doorgestuurde gebruikers worden weergegeven:

  - **Transportregel**
  - Het postvak met de regel voor Postvak IN doorsturen.

  ![De weergave Doorsturen in het rapport Doorsturen](../../media/forwarding-report-forwarders.png)

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

### <a name="details-table-view-for-the-forwarding-report"></a>Detailtabelweergave voor het rapport Doorsturen

Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:

- **Forwarders:** de waarde **transportregel of** het postvak dat de regel voor Postvak IN voor doorsturen bevat.
- **Type doorsturen:** de waarde van **de regel Postvak of** **Transportregel.**
- **Naam van geadresseerde**
- **Domein van ontvanger**
- **Details:** dit is de GUID-waarde van de regel voor de e-mailstroom, of de waarde RuleIdentity van de regel voor Postvak IN.
- **Aantal**
- **First forward date**

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="mailflow-status-report"></a>Mailflow status report

Het **statusrapport Mailflow** is vergelijkbaar met het rapport Verzonden en ontvangen e-mail, [](#sent-and-received-email-report)met aanvullende informatie over e-mail die is toegestaan of geblokkeerd aan de rand. Dit is het enige rapport met informatie over randbeveiliging en laat zien hoeveel e-mail is geblokkeerd voordat deze wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP). Het is belangrijk om te weten dat als een bericht naar vijf geadresseerden wordt verzonden, het als vijf verschillende berichten wordt geteld en niet als één bericht.
Als u het rapport wilt bekijken, opent u het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar **het** dashboard Rapporten en selecteert u \>  **het Mailflow-statusrapport.** Als u rechtstreeks naar het statusrapport van de **e-mailstroom wilt gaan,** opent u <https://protection.office.com/mailflowStatusReport> .

![Widget Mailflow-statusrapport in het dashboard Rapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Typeweergave voor het Mailflow-statusrapport

Wanneer u het rapport opent, is het **tabblad Type** standaard geselecteerd. Deze weergave bevat standaard een grafiek en een gegevenstabel die zijn geconfigureerd met de volgende filters:

- **Datum:** De laatste 7 dagen.
- **Richting:**

  - **Binnenkomende**
  - **Uitgaand**
  - **Rente-organisatie:** dit aantal is voor berichten binnen een tenant, dat wil zeggen sender abc@domain.com verzendt naar ontvanger xyz@domain.com (afzonderlijk geteld van **binnenkomende** en **uitgaande**)

- **Typt** u:

  - **Goede e-mail**
  - **Malware**
  - **Spam**
  - **Randbeveiliging**
  - **Regelberichten**
  - **Phishing-e-mail**

De grafiek is ingedeeld op basis van **de typewaarden.**

U kunt deze filters wijzigen door te klikken op **Filter** of door te klikken op een waarde in de grafieklegenda.

De gegevenstabel bevat de volgende informatie:

- **Richting**
- **Type**
- **24 uur**
- **3 dagen**
- **7 dagen**
- **15 dagen**
- **30 dagen**

Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u een van de volgende waarden selecteren:

- **Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Risicobeveiliging.](view-email-security-reports.md#threat-protection-status-report)
- **Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Risicobeveiliging.](view-email-security-reports.md#threat-protection-status-report)
- **Spamdetecties:** met deze selectie gaat u naar het [rapport Spamdetectie.](view-email-security-reports.md#spam-detections-report)
- **Geblokkeerde spam in Edge:** met deze selectie gaat u naar het [rapport Spamdetectie.](view-email-security-reports.md#spam-detections-report)

**Exporteren:**

Voor de detailweergave kunt u slechts gegevens voor één dag exporteren. Dus als u gegevens zeven dagen lang wilt exporteren, moet u 7 verschillende exportacties uitvoeren.

Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen. Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.

![Typeweergave in het Mailflow-statusrapport ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Richtingsweergave voor het Mailflow-statusrapport

Als u op het **tabblad Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.

De grafiek is ingedeeld op **richtingswaarden.**

U kunt deze filters wijzigen door te klikken op **Filter** of door te klikken op een waarde in de grafieklegenda. Dezelfde filters uit de **weergave Type** worden gebruikt.

De gegevenstabel bevat dezelfde informatie uit de **weergave Type.**

De **optie Kies een categorie voor meer informatie** over beschikbare selecties en gedrag is hetzelfde als de weergave **Type.**

**Exporteren:**

Voor de detailweergave kunt u slechts gegevens voor één dag exporteren. Dus als u gegevens zeven dagen lang wilt exporteren, moet u 7 verschillende exportacties uitvoeren.

Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen. Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.

![Richtingsweergave in het statusrapport Mailflow ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Trechterweergave voor het Mailflow-statusrapport

In **de weergave** Trechter ziet u hoe met de beveiligingsfuncties voor e-mail van Microsoft binnenkomende en uitgaande e-mail in uw organisatie wordt gefilterd. Het bevat details over het totale aantal e-mails en hoe de geconfigureerde functies voor bedreigingsbeveiliging, waaronder randbeveiliging, anti-malware, anti-phishing, anti-spam en anti-spoofing van invloed zijn op dit aantal.

Als u op het **tabblad Trechter** klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die zijn geconfigureerd met de volgende filters:

- **Datum:** De laatste 7 dagen.

- **Richting:**

  - **Binnenkomende**
  - **Uitgaand**
  - **Rente-organisatie:** dit aantal geldt voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat abc@domain.com berichten naar de ontvanger xyz@domain.com (geteld afzonderlijk van binnenkomende en uitgaande).

Filteren kan in de statistische weergave en de gegevenstabelweergave 90 dagen duren.

Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.

In dit diagram ziet u het aantal e-mailberichten, georganiseerd op:

- **Totaal aantal e-mailberichten**
- **E-mail na randbeveiliging**
- **E-mail na anti-malware, bestandsreputatie, bestandstypeblokkering**
- **E-mail na anti-phish, URL-reputatie, merk imitatie, anti-spoofing**
- **E-mail na antispamfilters, bulkmailfilters**
- **E-mail na gebruikers- en domein imitatie**<sup>1</sup>
- **E-mail na bestands- en URL-detonatie**<sup>1</sup>
- **E-mail die na de bezorgingsbeveiliging is gedetecteerd (URL-kliktijdbeveiliging)**

<sup>Alleen 1</sup> Defender voor Office 365

Als u de e-mail die wordt gefilterd op EOP of Defender voor Office 365 afzonderlijk wilt bekijken, klikt u op de waarde in de grafieklegenda.

De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:

- **Datum**
- **Totaal aantal e-mailberichten**
- **Randbeveiliging**
- **Anti-malware, bestandsreputatie, bestandstypeblokkering:**
  - **Bestandsreputatie:** berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.
  - **Bestandstypeblokkering:** berichten die zijn gefilterd vanwege het type schadelijk bestand dat is geïdentificeerd in het bericht.
- **Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**
  - **URL-reputatie:** berichten gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.
  - **Merk imitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende afzenders die zich voordoen als afzenders.
  - **Anti-spoofing:** berichten die zijn gefilterd omdat het bericht een domein probeert te vervalsen waar de geadresseerde deel van uit maakt, of een domein dat niet in bezit is van de afzender van het bericht.
- **Antispamfilters, bulkmailfilters:**
  - **Bulkmailfilter:** berichten die zijn gefilterd vanwege een poging om bulkmail af te leveren bij de geadresseerden.
- **Imitatie van gebruikers en domeinen (Defender voor Office 365)**:
  - **Gebruikers imitatie:** berichten gefilterd vanwege een poging om een gebruiker (afzender van bericht) te imiteren die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.
  - **Domein imitatie:** berichten gefilterd vanwege een poging om een domein te imiteren dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.
- **Detonatie van bestanden en URL's (Defender voor Office 365)**:
  - **Bestandsdetonatie:** berichten die zijn gefilterd op een beleid voor veilige bijlagen.
  - **URL-detonatie:** bericht gefilterd op een beleid voor veilige koppelingen.
- **Beveiliging na aflevering en ZAP (ATP) of ZAP (EOP)**: ZAP geeft automatisch purge van nul uur aan.

Als u een rij in de gegevenstabel selecteert, worden de e-mailberichten in de flyout verder uitsplitsing weergegeven.

**Exporteren:**

Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: 

- **Overzicht (met gegevens van de afgelopen 90 dagen)**
- **Details (met gegevens voor de afgelopen 30 dagen)**

Kies **een** bereik onder Datum en klik op **Toepassen.** Gegevens voor de huidige filters worden geëxporteerd naar een CSV-bestand.

Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen. Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.

 ![Trechterweergave in het statusrapport Mailflow ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Technische weergave voor het Mailflow-statusrapport

De **weergave Tech** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging. In de grafiek kunt u zien hoe berichten zijn gecategoriseerd in de verschillende fasen van risicobeveiliging.

Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een gegevenstabel die is geconfigureerd met de volgende filters:

- **Datum:** De laatste 7 dagen.

- **Richting:**

  - **Binnenkomende**
  - **Uitgaand**
  - **Rente-organisatie:** dit aantal is voor berichten binnen een tenant, dat wil zeggen sender abc@domain.com verzendt naar ontvanger xyz@domain.com (afzonderlijk geteld van inkomende en uitgaande)

Filteren kan in de statistische weergave en de gegevenstabelweergave 90 dagen duren.

Als u op **Filteren klikt,** kunt u zowel de grafiek als de gegevenstabel filteren.

In dit diagram worden berichten weergegeven die zijn ingedeeld in de volgende categorieën:

- **Totaal aantal e-mailberichten**
- **Edge toestaan** en **Edge gefilterd**
- **Geen malware,** **detectie van veilige bijlagen,** <sup>\*</sup> detectie van **antimalware-engine en** **regelberichten**
- **Not phish,** **DMARC failure,** **Impersonation detection,** **Spoof detection,** and **Phish detection**
- **Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup>
- **Geen spam en**  **spam**
- **Niet-schadelijke e-mail,** **detectie van veilige koppelingen** en <sup>\*</sup> **ZAP**

<sup>\*</sup> Defender voor Office 365

Wanneer u de muisaanwijzer op een categorie in de grafiek beweegt, ziet u het aantal berichten in die categorie.

De gegevenstabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:

- **Datum**
- **Totaal aantal e-mailberichten**
- **Gefilterd op Edge**
- **Antimalware-engine, veilige bijlagen, regel gefilterd:**
  - **Regel gefilterd:** berichten die zijn gefilterd vanwege regels voor de e-mailstroom (ook wel transportregels genoemd).
- **DMARC, imitatie, spoofing, phish gefilterd:**
  - **DMARC: Berichten** gefilterd als gevolg van het bericht dat de DMARC-verificatiecontrole mislukt.
- **DETECTIE VAN URL-detonatie**
- **Antispam gefilterd**
- **ZAP is verwijderd**
- **Detectie via veilige koppelingen**

Als u een rij in de gegevenstabel selecteert, worden de e-mailberichten in de flyout verder uitsplitsing weergegeven.

**Exporteren:**

Als u op **Exporteren klikt,** kunt u onder **Opties** een van de volgende waarden selecteren:

- **Overzicht (met gegevens van de afgelopen 90 dagen)**
- **Details (met gegevens voor de afgelopen 30 dagen)**

Kies **een** bereik onder Datum en klik op **Toepassen.** Gegevens voor de huidige filters worden geëxporteerd naar een CSV-bestand.

Elk geëxporteerd CSV-bestand is beperkt tot 150.000 rijen. Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere CSV-bestanden gemaakt.

 ![Technische weergave in het Mailflow-statusrapport ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Rapport verzonden en ontvangen e-mail

Het **rapport Verzonden** en ontvangen e-mail is een slim rapport met informatie over binnenkomende en uitgaande e-mail, inclusief spamdetecties, malware en e-mail die wordt geïdentificeerd als 'goed'. Het verschil tussen dit rapport en het [Mailflow-statusrapport](#mailflow-status-report) is: dit rapport bevat geen gegevens over berichten die zijn geblokkeerd door randbeveiliging. Het is belangrijk om te weten dat als een bericht naar vijf geadresseerden wordt verzonden, dit als één bericht wordt geteld.

Filteren kan 90 dagen duren voor de statistische weergave en de detailweergave van het rapport.

Als u het rapport wilt bekijken, opent u  het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u \>  **Verzonden en ontvangen e-mail.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![De widget Verzonden en ontvangen e-mail in het dashboard Rapporten](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Rapportweergave voor het rapport Verzonden en ontvangen e-mail

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Afbreken op: Type:** De grafiek bevat alle beschikbare categorieën:

  - **Totaal**
  - **Goede e-mail**
  - **Malware (anti-malware)** (EOP)
  - **Spamdetecties**
  - **Regelberichten**
  - **Geavanceerde malware** (Microsoft Defender voor Office 365)

  Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, ziet u de details voor die dag.

  ![Weergave Typen in het rapport Verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-type-view.png)

- **Op te delen met: Richting:** in de grafiek ziet u **het totaal,** **de** binnenkomende en **uitgaande** gegevens. Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, ziet u de details voor die dag.

  ![Richtingsweergave in het rapport Verzonden en ontvangen e-mail](../../media/sent-and-received-email-report-direction-view.png)

- **Inzoomen op** \> **Malware (anti-malware)**: met deze selectie gaat u naar de [malwaredetecties in het e-mailrapport.](view-email-security-reports.md#malware-detections-in-email-report)

- **Inzoomen op** \> **Spamdetecties:** hiermee gaat u naar het [rapport Spamdetectie.](view-email-security-reports.md#spam-detections-report)

Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** **en einddatum**
- Richtingswaarden
- Typewaarden

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Tabelweergave Details voor het rapport Verzonden en ontvangen e-mail

Als u klikt **op de tabel Details weergeven** in Op delen **door:** Richting of Opbreken **door:** Richtingsweergave, wordt de volgende informatie weergegeven:

- **Datum (UTC)**
- **Type**
- **Richting**
- **Aantal berichten**

Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** **en einddatum**
- Richtingswaarden
- Typewaarden

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="top-senders-and-recipients-report"></a>Top senders and recipients report

Het **rapport met de belangrijkste afzenders en geadresseerden** is een cirkeldiagram met de belangrijkste afzenders en geadresseerden van uw e-mail.

Als u het rapport wilt bekijken, opent u  het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u de belangrijkste \>  **afzenders en geadresseerden.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![De belangrijkste widget voor afzenders en geadresseerden in het dashboard Rapporten](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Rapportweergave voor het rapport met de belangrijkste afzenders en geadresseerden

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Gegevens voor belangrijkste \> afzenders van e-mailberichten tonen**
- **Gegevens voor belangrijkste \> e-mailontvangers tonen**
- **Gegevens voor belangrijkste \> geadresseerden van ongewenste e-mail tonen**
- **Gegevens tonen voor \> Belangrijkste ontvangers van malware** (EOP)
- **Gegevens tonen voor \> belangrijkste malwareontvangers (Defender voor Office 365)**

De samenstelling van het cirkeldiagram verandert op basis van deze selecties.

Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u het aantal verzonden of ontvangen berichten.

Als u in **een rapportweergave** op Filters klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

![Cirkeldiagram in rapportweergave in het rapport Met de belangrijkste afzenders en geadresseerden](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Detailtabelweergave voor het rapport Met de belangrijkste afzenders en geadresseerden

Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:

- **Gegevens voor belangrijkste \> afzenders van e-mailberichten tonen**

  - **Belangrijkste afzenders van e-mail**
  - **Aantal**

- **Gegevens voor belangrijkste \> e-mailontvangers tonen**

  - **Belangrijkste e-mailontvangers**
  - **Aantal**

- **Gegevens voor belangrijkste \> geadresseerden van ongewenste e-mail tonen**

  - **Belangrijkste geadresseerden voor ongewenste e-mail**
  - **Aantal**

- **Gegevens tonen voor \> Belangrijkste ontvangers van malware** (EOP)

  - **Belangrijkste ontvangers van malware**
  - **Aantal**

- **Gegevens tonen voor \> belangrijkste malwareontvangers (Defender voor Office 365)**

  - **Belangrijkste ontvangers van malware (Defender voor Office 365)**
  - **Aantal**

Als u in een detailtabelweergave op **Filters** klikt, kunt u een datumbereik opgeven met **de begin-** en **einddatum.**

Als u wilt teruggaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welke machtigingen zijn nodig om deze rapporten te bekijken?

Als u de rapporten in dit artikel wilt bekijken en gebruiken, moet u lid zijn van een van de volgende rollengroepen in het beveiligings- & compliancecentrum:

- **Organisatiebeheer**
- **Beveiligingsbeheerder**
- **Beveiligingslezer**
- **Globale lezer**

Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

> [!NOTE]
> Gebruikers toevoegen aan de overeenkomstige Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de benodigde machtigingen in het Beveiligings- en compliancecentrum _en_ machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="related-topics"></a>Verwante onderwerpen

[Slimme rapporten en inzichten in het beveiligings- & compliancecentrum](reports-and-insights-in-security-and-compliance.md)

[Inzichten in e-mailstroom in het & compliancecentrum](mail-flow-insights-v2.md)

[Beveiligingsrapporten voor e-mail weergeven in het & compliancecentrum](view-email-security-reports.md)

[Rapporten voor Microsoft Defender voor Office 365 weergeven](view-reports-for-atp.md)
