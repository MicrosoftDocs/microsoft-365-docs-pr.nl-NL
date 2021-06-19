---
title: Beveiligingsrapporten voor e-mail weergeven
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Beheerders kunnen leren hoe ze de e-mailbeveiligingsrapporten kunnen vinden en gebruiken die beschikbaar zijn in de Microsoft 365 Defender-portal.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f3dcf533c232a89adf0dc1ff3fcc7c2ca4fc5d8f
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022911"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a>E-mailbeveiligingsrapporten weergeven in de Microsoft 365 Defender-portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Er zijn diverse rapporten beschikbaar in de Microsoft 365 Defender-portal om te zien hoe e-mailbeveiligingsfuncties, zoals antispam, anti-malware en versleutelingsfuncties in Microsoft 365 uw organisatie <https://security.microsoft.com> beschermen. Als u de benodigde machtigingen [hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken  in de Microsoft 365 Defender-portal door naar Rapporten E-mail & samenwerking e-mail \>  \> **& samenwerkingsrapporten.** Als u rechtstreeks naar de pagina **E-mail & samenwerkingsrapporten** wilt gaan, opent u <https://security.microsoft.com/emailandcollabreport> .

![Pagina & samenwerkingsrapporten in de Microsoft 365 Defender-portal](../../media/email-collaboration-reports.png)

> [!NOTE]
>
> Voor sommige rapporten op de pagina **E-& samenwerkingsrapporten** is Microsoft Defender voor Office 365 vereist. Zie Defender voor [Office 365-rapporten weergeven in de Microsoft 365 Defender-portal](view-reports-for-mdo.md)voor meer informatie over deze rapporten.
>
> Rapporten die zijn gerelateerd aan e-mailstroom, zijn nu in het Exchange-beheercentrum (EAC). Zie E-mailstroomrapporten in het [nieuwe Exchange-beheercentrum](/exchange/monitoring/mail-flow-reports/mail-flow-reports)voor meer informatie over deze rapporten.

## <a name="compromised-users-report"></a>Rapport over gecompromitteerde gebruikers

> [!NOTE]
> Dit rapport is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken. Het is niet beschikbaar in zelfstandige EOP-organisaties (Exchange Online Protection).

In **het rapport Gecompromitteerde** gebruikers ziet  u  het aantal gebruikersaccounts dat in de afgelopen 7 dagen is gemarkeerd als Verdacht of Beperkt. Accounts in een van deze staten zijn problematisch of zelfs gecompromitteerd. Met regelmatig gebruik kunt u het rapport gebruiken om pieken en zelfs trends te herkennen in verdachte of beperkte accounts. Zie Reageren op een gekromd e-mailaccount voor meer informatie over gecompromitteerde [gebruikers.](responding-to-a-compromised-email-account.md)

![Widget Voor gecompromitteerde gebruikers op de pagina E-mail & samenwerkingsrapporten](../../media/compromised-users-report-widget.png)

De statistische weergave bevat gegevens van de afgelopen 90 dagen en de detailweergave bevat gegevens van de afgelopen 30 dagen.

Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & samenwerkingsrapporten** naar Gecompromitteerde **gebruikers** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/CompromisedUsers> .

Op de pagina Gecompromitteerd gebruikers kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven: 

- **Datum (UTC)**: **Begindatum** en **einddatum**.
- **Activiteit**:
  - **Verdacht:** Het gebruikersaccount heeft verdachte e-mailberichten verzonden en loopt het risico dat het niet meer kan worden verzonden.
  - **Beperkt:** Het gebruikersaccount is beperkt tot het verzenden van e-mail vanwege zeer verdachte patronen.

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

![Rapportweergave in het rapport Gecompromitteerd gebruikers](../../media/compromised-users-report-activity-view.png)

In de detailtabel onder de grafiek ziet u de volgende details:

- **Aanmaaktijd**
- **Gebruikers-id**
- **Actie**

## <a name="exchange-transport-rule-report"></a>Rapport met exchange-transportregel

Het **rapport Exchange-transportregel** toont het effect van regels voor de e-mailstroom (ook wel transportregels genoemd) op binnenkomende en uitgaande berichten in uw organisatie.

Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina E-& samenwerkingsrapporten** **naar Exchange-transportregel** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/ETRRuleReport> .

![Exchange-transportregelwidget op de pagina E-mail & samenwerkingsrapporten](../../media/transport-rule-report-widget.png)

Op de rapportpagina van de **Exchange-transportregel** worden de beschikbare grafieken en gegevens in de volgende secties beschreven.

### <a name="chart-breakdown-by-direction"></a>Grafiek uitsplitsing op richting

![Richtingsweergave voor Exchange-transportregels in het rapport Exchange-transportregel](../../media/transport-rule-report-etr-direction-view.png)

Als u Grafiek **uitsplitsing op richting selecteert,** zijn de volgende grafieken beschikbaar:

- **Gegevens weergeven op exchange-transportregels:** het  aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door regels voor e-mailstroom.
- **Gegevens weergeven op DLP Exchange-transportregels:**  het aantal **binnenkomende** en uitgaande berichten dat is beïnvloed door DLP-regels (Data Loss Prevention).

De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:

- **Datum**
- **DLP-beleid** (**Alleen gegevens weergeven op DLP Exchange-transportregels)**
- **Transportregel**
- **Onderwerp**
- **Adres afzender**
- **Adres van geadresseerde**
- **Ernst**
- **Richting**

U kunt zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Richting:** **Uitgaande en Inkomende** 
- **Ernst:** **hoge ernst,** **gemiddelde ernst** en **lage ernst**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

### <a name="chart-breakdown-by-severity"></a>Uitsplitsing van grafieken op ernst

![Ernstweergave voor Exchange-transportregels in het rapport Exchange-transportregel](../../media/transport-rule-report-etr-severity-view.png)

Als u Grafiek **uitsplitsing op ernst selecteert,** zijn de volgende grafieken beschikbaar:

- **Gegevens weergeven op exchange-transportregels:** het aantal berichten met hoge **ernst,** gemiddelde **ernst** en **berichten met lage ernst.** U stelt het ernstniveau in als een actie in de regel ( Controleer deze regel met **ernstniveau** of _SetAuditSeverity_). Zie Acties voor [e-mailstroomregelen in Exchange Online voor meer informatie.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **Gegevens weergeven op DLP Exchange-transportregels:** het aantal berichten  met hoge **ernst,** gemiddelde ernst en lage ernst die zijn beïnvloed door DLP-regels voor e-mailstroom.

De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:

- **Datum**
- **DLP-beleid** (**Alleen gegevens weergeven op DLP Exchange-transportregels)**
- **Transportregel**
- **Onderwerp**
- **Adres afzender**
- **Adres van geadresseerde**
- **Ernst**
- **Richting**

U kunt zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Richting:** **Uitgaande en Inkomende** 
- **Ernst:** **hoge ernst,** **gemiddelde ernst** en **lage ernst**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

## <a name="forwarding-report"></a>Doorsturen van rapport

> [!NOTE]
> Het **rapport Doorsturen** is nu beschikbaar in het EAC. Zie Rapport Automatisch doorgestuurde berichten in het nieuwe EAC voor [meer informatie.](/exchange/monitoring/mail-flow-reports/mfr-auto-forwarded-messages-report)

## <a name="mailflow-status-report"></a>E-mailflowstatusrapport

Het **mailflowstatusrapport** is een slim rapport met informatie over inkomende en uitgaande e-mail, spamdetecties, malware, e-mail die als 'goed' is geïdentificeerd en informatie over e-mail die is toegestaan of geblokkeerd op de rand. Dit is het enige rapport dat informatie over randbeveiliging bevat en laat zien hoeveel e-mail wordt geblokkeerd voordat e-mail wordt toegestaan in de service voor evaluatie door Exchange Online Protection (EOP). Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.

Als u het rapport wilt bekijken in de  Microsoft 365 Defender-portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de & e-mail met samenwerkingsrapporten** de **statusoverzicht van Mailflow** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/mailflowStatusReport> .

![Overzichtswidget Mailflow-status op de pagina E-mail & samenwerkingsrapporten](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Typweergave voor het rapport Mailflow-status

Wanneer u het rapport opent, is **het tabblad Type** standaard geselecteerd. Deze weergave bevat standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:

- **Datum (UTC)** De afgelopen 7 dagen.
- **E-mailrichting**:
  - **Binnenkomende**
  - **Uitgaande**
  - **Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen afzender abc@domain.com verzendt naar geadresseerde xyz@domain.com (afzonderlijk geteld van **Binnenkomende** en **Uitgaande**)
- **Typ**:
  - **Goede e-mail**
  - **Malware**
  - **Spam**
  - **Randbeveiliging**
  - **Regelberichten**
  - **Phishing-e-mail**
- **Domein:** **Alles**

De grafiek wordt ingedeeld op basis van **de waarden Type.**

U kunt deze filters wijzigen door op **Filter te klikken of** door te klikken op een waarde in de grafieklegenda.

De volgende informatie wordt weergegeven in de detailtabel onder de grafiek:

- **Richting**
- **Type**
- **24 uur**
- **3 dagen**
- **7 dagen**
- **15 dagen**
- **30 dagen**

Als u op **Een categorie kiezen klikt voor meer informatie,** kunt u kiezen uit de volgende waarden:

- **Phishing-e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)
- **Malware in e-mail:** met deze selectie gaat u naar het [statusrapport Bedreigingsbeveiliging.](view-email-security-reports.md#threat-protection-status-report)
- **Spamdetecties:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)
- **Edge geblokkeerde spam:** Met deze selectie gaat u naar het [rapport Spamdetecties.](view-email-security-reports.md#spam-detections-report)

#### <a name="export-from-type-view"></a>Exporteren vanuit de weergave Type

Voor de detailweergave kunt u slechts één dag gegevens exporteren. Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.

Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen. Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.

![Weergave typen in het rapport Mailflow-status](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Richtingsweergave voor het rapport Mailflow-status

Als u op het tabblad **Richting** klikt, worden dezelfde standaardfilters uit de **weergave Type** gebruikt.

De grafiek is ingedeeld op **richtingswaarden.**

U kunt deze filters wijzigen door op Filter te **klikken.** Dezelfde filters uit de **weergave Type** worden gebruikt.

De detailtabel bevat dezelfde informatie uit de **weergave Type.**

De **categorie Kies een categorie voor meer informatie** beschikbare selecties en gedrag zijn hetzelfde als de **weergave** Type.

#### <a name="export-from-direction-view"></a>Exporteren vanuit de richtingsweergave

Voor de detailweergave kunt u slechts één dag gegevens exporteren. Dus als u gegevens 7 dagen wilt exporteren, moet u 7 verschillende exportacties uitvoeren.

Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen. Als de gegevens voor die dag meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.

![Richtingsweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Trechterweergave voor het rapport Mailflow-status

In **de trechterweergave** ziet u hoe de beveiligingsfuncties voor e-mail van Microsoft inkomende en uitgaande e-mail in uw organisatie filteren. Het bevat informatie over het totale aantal e-mailberichten en hoe de geconfigureerde beveiligingsfuncties voor bedreigingen, zoals randbeveiliging, anti-malware, anti-phishing, antispam en anti-spoofing van invloed zijn op dit aantal.

Als u op **het** tabblad Trechter klikt, bevat deze weergave standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:

- **Datum:** De laatste 7 dagen.

- **Richting**:
  - **Binnenkomende**
  - **Uitgaande**
  - **Intra-org:** Dit aantal is voor berichten die binnen een tenant worden verzonden; Dat wil zeggen dat afzenders abc@domain.com naar geadresseerden xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande).

De tabelweergave voor statistische weergave en details kan 90 dagen worden gefilterd.

U kunt deze filters wijzigen door op Filter te **klikken.** Dezelfde filters uit de **weergave Type** worden gebruikt.

In deze grafiek ziet u het aantal e-mailberichten dat is ingedeeld op:

- **Totaal aantal e-mail**
- **E-mail na randbeveiliging**
- **Regel E-mail na transport** (regel voor e-mailstroom)
- **E-mail na anti-malware, bestandsreputatie, bestandstypeblok**
- **E-mail na anti-phish, URL-reputatie, merkremitatie, anti-spoofing**
- **E-mail na antispam, bulkmailfilters**
- **E-mail na gebruikers- en domein-imitatie**<sup>\*</sup>
- **E-mail na bestand en URL-detonatie**<sup>\*</sup>
- **E-mail die is gedetecteerd als goedaardig na de beveiliging na de bezorging (URL klik op tijdbeveiliging)**

<sup>\*</sup>Defender voor Office 365 alleen

Als u het e-mailbericht wilt weergeven dat is gefilterd op EOP of Defender Office 365 afzonderlijk, klikt u op de waarde in de grafieklegenda.

De detailtabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:

- **Datum**
- **Totaal aantal e-mail**
- **Randbeveiliging**
- **Anti-malware, bestandsreputatie, bestandstypeblok:**
  - **Bestandsreputatie:** Berichten die zijn gefilterd vanwege de identificatie van een bijgevoegd bestand door andere Microsoft-klanten.
  - **Bestandstypeblok:** Berichten die zijn gefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.
- **Anti-phish, URL-reputatie, merk imitatie, anti-spoof:**
  - **URL-reputatie:** Berichten die zijn gefilterd vanwege de identificatie van de URL door andere Microsoft-klanten.
  - **Merkremitatie:** berichten die zijn gefilterd vanwege het bericht dat afkomstig is van bekende merkremiterende afzenders.
  - **Anti-spoof:** Berichten die zijn gefilterd vanwege het bericht waarin wordt geprobeerd een domein te vervalsen dat de geadresseerde behoort, of een domein dat de afzender van het bericht niet bezit.
- **Antispam, bulkmailfilters:**
  - **Bulkmailfilters:** Berichten gefilterd op basis van de drempel voor bulksgewijs klagen (BCL) in een antispambeleid.
- **Gebruikers- en domein-imitatie (Defender voor Office 365)**:
  - **Gebruikers-imitatie:** berichten die zijn gefilterd vanwege een poging om zich voor te doen als een gebruiker (afzender van een bericht) die is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.
  - **Domein imitatie:** Berichten gefilterd vanwege een poging om een domein na te bootsen dat is gedefinieerd in de instellingen voor imitatiebeveiliging van een anti-phishingbeleid.
- **Bestands- en URL-detonatie (Defender voor Office 365)**:
  - **Bestandsdetonatie:** Berichten gefilterd op een Safe bijlagenbeleid.
  - **URL-detonatie:** bericht gefilterd door een Safe koppelingenbeleid.
- **Bescherming na bezorging en ZAP (ATP) of ZAP (EOP)**: Automatische purge (ZAP) van nul uur voor malware, spam en phishing.

Als u een rij in de detailtabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.

#### <a name="export-from-funnel-view"></a>Exporteren vanuit de trechterweergave

Nadat u onder **Opties op Exporteren** hebt geklikt, kunt u een van de volgende waarden selecteren: 

- **Overzicht (met gegevens van de afgelopen 90 dagen)**
- **Details (met gegevens van de afgelopen 30 dagen ten hoogst)**

Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.** Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.

Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen. Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.

![Trechterweergave in het rapport Mailflow-status](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Technische weergave voor het mailflowstatusrapport

De **techweergave** is vergelijkbaar met de **trechterweergave,** met meer gedetailleerde details voor de geconfigureerde functies voor bedreigingsbeveiliging. In de grafiek kunt u zien hoe berichten worden gecategoriseerd in de verschillende stadia van bedreigingsbeveiliging.

Als u op het **tabblad Technische** weergave klikt, bevat deze weergave standaard een grafiek en een detailtabel die is geconfigureerd met de volgende filters:

- **Datum:** De laatste 7 dagen.

- **Richting**:
  - **Binnenkomende**
  - **Uitgaande**
  - **Intra-org:** dit aantal is voor berichten binnen een tenant, dat wil zeggen afzender abc@domain.com verzenden naar geadresseerde xyz@domain.com (afzonderlijk geteld van Binnenkomende en Uitgaande)

De tabelweergave voor statistische weergave en details kan 90 dagen worden gefilterd.

U kunt deze filters wijzigen door op Filter te **klikken.** Dezelfde filters uit de **weergave Type** worden gebruikt.

In deze grafiek ziet u berichten die zijn ingedeeld in de volgende categorieën:

- **Totaal aantal e-mail**
- **Rand toestaan** en **Edge gefilterd**
- **Transportregel toestaan** en **Transportregel gefilterd** (regels voor e-mailstroom)
- **Geen malware,** **Safe detectie van** bijlagen en detectie van <sup>\*</sup> **anti-malware-engine**
- **Geen phish,** **DMARC-fout,** **imitatiedetectie,** <sup>\*</sup> **spoofdetectie** en **Phish-detectie**
- **Geen detectie met URL-detonatie en** **URL-detonatiedetectie**<sup>\*</sup>
- **Geen spam en**  **spam**
- **Niet-schadelijke e-mail,** **Safe koppelingendetectie** <sup>\*</sup> en **ZAP**

<sup>\*</sup>Defender voor Office 365

Wanneer u de muisaanwijzer boven een categorie in de grafiek beweegt, kunt u het aantal berichten in die categorie zien.

De detailtabel bevat de volgende gegevens, weergegeven in aflopende datumvolgorde:

- **Datum (UTC)**
- **Totaal aantal e-mail**
- **Gefilterde rand**
- **Regelberichten:** Berichten die zijn gefilterd vanwege regels voor e-mailstroom (ook wel transportregels genoemd).
- **Anti-malware engine**, **Safe Bijlagen:** <sup>\*</sup>
- **DMARC, imitatie** <sup>\*</sup> , **spoof**, **phish gefilterd**:
  - **DMARC:** Berichten gefilterd vanwege het bericht dat de DMARC-verificatiecontrole mislukt.
- **DETECTIE VAN URL-detonatie**<sup>\*</sup>
- **Gefilterde antispam**
- **ZAP verwijderd**
- **Detectie door Safe koppelingen**<sup>\*</sup>

<sup>\*</sup>Defender voor Office 365

Als u een rij in de detailtabel selecteert, wordt een verdere uitsplitsing van de e-mailtellingen weergegeven in de flyout.

#### <a name="export-from-tech-view"></a>Exporteren vanuit de techweergave

Als u op **Exporteren** klikt, kunt u onder **Opties** een van de volgende waarden selecteren:

- **Overzicht (met gegevens van de afgelopen 90 dagen)**
- **Details (met gegevens van de afgelopen 30 dagen ten hoogst)**

Kies **onder Datum** een bereik en klik vervolgens op **Toepassen.** Gegevens voor de huidige filters worden geëxporteerd naar een .csv bestand.

Elk geëxporteerd .csv bestand is beperkt tot 150.000 rijen. Als de gegevens meer dan 150.000 rijen bevatten, worden meerdere .csv gemaakt.

![Technische weergave in het rapport Mailflow-status](../../media/mail-flow-status-report-tech-view.png)

## <a name="malware-detections-report"></a>Rapport malwaredetecties

Het **rapport Malwaredetecties bevat** informatie over malwaredetecties in inkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP). Zie [Anti-malwarebeveiliging in EOP](anti-malware-protection.md)voor meer informatie over malwarebeveiliging in EOP.

Het filter voor de statistische weergave kan 90 dagen duren, terwijl het detailtabelfilter slechts 10 dagen toestaat.

Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & samenwerkingsrapporten** malware die **is gedetecteerd in e-mail** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/MalwareDetections> .

![Malwaredetecties in e-mailwidget op de pagina E-mail & samenwerkingsrapporten](../../media/malware-detections-widget.png)

Op de **rapportpagina Malwaredetecties** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een van de volgende waarden te selecteren:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Richting:** **Binnenkomende** en **uitgaande**

![Rapportweergave in het rapport Malwaredetectie in e-mailrapport](../../media/malware-detections-report-view.png)

In de detailtabel onder de grafiek ziet u de volgende details:

- **Datum**
- **Adres afzender**
- **Adres van geadresseerde**
- **Bericht-id:** Beschikbaar in het **veld Bericht-id** in de berichtkoptekst en moet uniek zijn. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).
- **Onderwerp**
- **Bestandsnaam**
- **Malwarenaam**

## <a name="mail-latency-report"></a>E-maillatentierapport

Het **rapport E-maillatentie** in Defender voor Office 365 bevat informatie over de latentie van e-mailbezorging en detonatie binnen uw organisatie. Zie Mail [latentierapport](view-reports-for-mdo.md#mail-latency-report)voor meer informatie.

## <a name="spam-detections-report"></a>Rapport over spamdetectie

> [!NOTE]
> Het **rapport Spamdetecties** gaat uiteindelijk weg. Dezelfde informatie is beschikbaar in het rapport [Bedreigingsbeveiligingsstatus.](#threat-protection-status-report)

## <a name="spoof-detections-report"></a>Rapport spoofdetecties

> [!NOTE]
> Het verbeterde rapport Spoofdetecties, zoals beschreven in dit artikel, is in Preview, kan worden gewijzigd en is niet beschikbaar in alle organisaties. In de oudere versie van het rapport ziet u alleen **Goede e-mail** en **Gevangen als spam.**

Het **rapport Spoofdetecties** bevat informatie over berichten die zijn geblokkeerd of toegestaan vanwege spoofing. Zie Bescherming tegen spoofing in EOP voor meer [informatie over spoofing.](anti-spoofing-protection.md)

Met de statistische weergave van het rapport kunt u 45 dagen filteren, terwijl de detailweergave slechts tien dagen <sup>\*</sup> filtert.

<sup>\*</sup> Uiteindelijk kunt u maximaal 90 dagen filteren gebruiken.

Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & samenwerkingsrapporten** naar **Spoofdetecties** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/SpoofMailReportV2> .

![Widget Spoofdetecties op de pagina E-mail & samenwerkingsrapporten](../../media/spoof-detections-widget.png)

In de grafiek ziet u de volgende informatie:

- **Pass**
- **Mislukken**
- **SoftPass**
- **Geen**
- **Overige**

Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel vervalste berichten zijn gedetecteerd en waarom.

Op de **pagina Spoof-e-mailrapport** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Resultaat**:
  - **Pass**
  - **Mislukken**
  - **SoftPass**
  - **Geen**
  - **Overige**
- **Spooftype:** **Intern** en **Extern**

![Pagina spoof-e-mailrapport in de Microsoft 365 Defender portal](../../media/spoof-detections-report-page.png)

In de detailtabel onder de grafiek ziet u de volgende details:

- **Datum**
- **Vervalste gebruiker**
- **Verzendende infrastructuur**
- **Spooftype**
- **Result**
- **Resultaatcode**
- **SPF**
- **DKIM**
- **DMARC**
- **Aantal berichten**

Zie Kopteksten voor spamberichten in Microsoft 365 voor [meer informatie over resultaatcodes voor samengestelde verificatie.](anti-spam-message-headers.md)

## <a name="submissions-report"></a>Rapport Inzendingen

Het **rapport Inzendingen** bevat informatie over items die beheerders hebben gerapporteerd bij Microsoft voor analyse. Zie Beheerdersinzending gebruiken om [verdachte spam, phish, URL's en](admin-submission.md)bestanden in te dienen bij Microsoft voor meer informatie.

Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & samenwerkingsrapporten** naar **Inzendingen** en klik vervolgens op Details **weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/adminSubmissionReport> . Als u wilt gaan [naar beheerdersinzendingen in de Microsoft 365 Defender portal,](admin-submission.md)klikt u **op Ga naar Inzendingen.**

![Widget Inzendingen op de pagina E-& samenwerkingsrapporten](../../media/submissions-report-widget.png)

In de grafiek ziet u de volgende informatie:

- **In behandeling**
- **Voltooid**

Op de **pagina Inzendingen** kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren:

- **Datum gerapporteerd:** **Begintijd** en **eindtijd**
- **Inzendingstype:** **E-mail,** **URL** of **Bestand**
- **Inzending-id**
- **Netwerkbericht-id**
- **Afzender**
- **Naam**
- **Ingediend door**
- **Reden voor het indienen** van : **Geen ongewenste** e-mail, **Phish,** **Malware** of **Spam**
- **Status opnieuw scannen:** **In behandeling** of **voltooid**

De detailtabel onder de grafiek bevat dezelfde  informatie en heeft  dezelfde opties voor groepen of kolommen aanpassen als op het tabblad Ingediend voor analyse op  **E-mail &** \> **samenwerkingsinzendingen.** Zie Beheerdersinzendingen [weergeven bij Microsoft voor meer informatie.](admin-submission.md#view-admin-submissions-to-microsoft)

![Rapportpagina Inzendingen in de Microsoft 365 Defender portal](../../media/submissions-report-page.png)

## <a name="threat-protection-status-report"></a>Statusrapport bedreigingsbeveiliging

Het **rapport Bedreigingsbeveiligingsstatus** is beschikbaar in zowel EOP als Defender voor Office 365; De rapporten bevatten echter verschillende gegevens. EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die is gedetecteerd in e-mail, maar geen informatie over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)en Microsoft Teams.

Het rapport bevat het aantal e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die zijn geblokkeerd door de anti-malware-engine, automatische nul-uursre [purge (ZAP)](zero-hour-auto-purge.md)en Defender voor Office 365-functies, zoals [Safe Koppelingen,](safe-links.md) [Safe](safe-attachments.md)Bijlagen en functies voor imitatiebeveiliging [in anti-phishingbeleid.](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) U kunt deze informatie gebruiken om trends te identificeren of om te bepalen of organisatiebeleid moet worden aangepast.

**Opmerking:** Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.

Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & samenwerkingsrapporten** naar Status van **bedreigingsbeveiliging** en klik vervolgens op **Details weergeven.** Open een van de volgende URL's om rechtstreeks naar het rapport te gaan:

- Defender voor Office 365:<https://security.microsoft.com/reports/TPSAggregateReportATP>
- EOP: <https://security.microsoft.com/reports/TPSAggregateReport>

![Statuswidget Bedreigingsbeveiliging op de pagina E-mail & samenwerkingsrapporten](../../media/threat-protection-status-report-widget.png)

Standaard worden in de grafiek gegevens van de afgelopen 7 dagen weergegeven. Als u op  **Filter klikt** op de rapportpagina bedreigingsstatus, kunt u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen beperkt zijn tot 30 dagen). Met de detailtabel kunt u 30 dagen filteren.

De beschikbare weergaven worden in de volgende secties beschreven.

### <a name="view-data-by-overview"></a>Gegevens weergeven op overzicht

![Overzichtsweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-overview-view.png)

In de **weergave Gegevens weergeven op** overzicht worden de volgende detectiegegevens weergegeven in de grafiek:

- **E-mailmalware**
- **E-mail phish**
- **Inhoudsmalware**

Er is geen detailtabel beschikbaar onder de grafiek.

Als u op **Filter klikt,** zijn de volgende filters beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Detectie:** **E-mail malware,** **E-mail phish** of **Inhoudsmalware**
- **Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**
- **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
- **Richting**
- **Domein**
- **Beleidstype**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

### <a name="view-data-by-email--phish-and-chart-breakdown-by-detection-technology"></a>Gegevens weergeven op \> e-mail phish en grafiek met detectietechnologie

![Detectietechnologieweergave voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

In de **weergave Gegevens weergeven per \> e-mail phish** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:

- **URL-schadelijke reputatie**: Kwaadaardige URL-reputatie die is gegenereerd door Defender voor Office 365 <sup>\*</sup> detonaties in andere Microsoft 365 klanten.
- **Geavanceerd filter:** Phishing-signalen op basis van machine learning.
- **Algemeen filter:** Phishing-signalen op basis van analistregels.
- **Spoof intra-org:** Afzender probeert het domein van de geadresseerde te vervalsen.
- **Extern domein vervalsen:** afzender probeert een ander domein te vervalsen.
- **Spoof DMARC:** DMARC-verificatiefout op berichten.
- **Imitatiemerk:** Imitatie van bekende merken op basis van afzenders.
- **Detectie van gemengde analyse**
- **Bestandsreputatie**
- **Vingerafdrukmatching**
- **URL-detonatiereputatie**<sup>\*</sup>
- **URL-detonatie**<sup>\*</sup>
- **Imitatiegebruiker**<sup>\*</sup>
- **Imitatiedomein:** imitatie van domeinen die de klant bezit <sup>\*</sup> of definieert.
- **Postvakintelligentie** <sup>\*</sup> imiteren: Imitatie van gebruikers die zijn gedefinieerd door beheerder of die zijn geleerd via postvakinformatie.
- **Bestandsdetonatie**<sup>\*</sup>
- **Campagne**<sup>\*</sup>

In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:

- **Datum**
- **Onderwerp**
- **Afzender**
- **Geadresseerden**
- **Gedetecteerd door**
- **Bezorgingsstatus**
- **Bron van compromis**
- **Tags**

Als u op **Filter klikt,** zijn de volgende filters beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Detectie**
- **Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**
- **Richting**
- **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
- **Domein**
- **Beleidstype**
- **Naam van beleid** (alleen detailstabel)
- **Geadresseerden**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

### <a name="view-data-by-email--malware-and-chart-breakdown-by-detection-technology"></a>Gegevens weergeven op \> e-mailmalware en grafiek met detectietechnologie

![Detectietechnologieweergave voor malware in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-malware-detection-tech-view.png)

In de **weergave Gegevens weergeven per e-mail \> malware** en grafiek op **detectietechnologie** worden de volgende gegevens weergegeven in de grafiek:

- **Bestandsdetonatie** <sup>\*</sup> : Detectie door Safe bijlagen.
- **Reputatie van bestandsdetonatie:** alle schadelijke bestandsreputatie die door Defender wordt gegenereerd <sup>\*</sup> Office 365 detonaties.
- **Bestandsreputatie**
- **Anti-malware-engine:** <sup>\*</sup> Detectie van anti-malwareprogramma's.
- **Bestandstype anti-malwarebeleid:** dit zijn e-mailberichten die zijn uitgefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.
- **URL schadelijke reputatie**
- **URL-detonatie**
- **URL-detonatiereputatie**
- **Campagne**

In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:

- **Datum**
- **Onderwerp**
- **Afzender**
- **Geadresseerden**
- **Gedetecteerd door**
- **Bezorgingsstatus**
- **Bron van compromis**
- **Tags**

Als u op **Filter klikt,** zijn de volgende filters beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Detectie**
- **Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**
- **Richting**
- **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
- **Domein**
- **Beleidstype**
- **Naam van beleid** (alleen detailstabel)
- **Geadresseerden**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

### <a name="chart-breakdown-by-policy-type-and-view-data-by-email--phish-or-view-data-by-email--malware"></a>Grafiekinsplitsing per type beleid en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per e-mail \> malware

![Weergave beleidtype voor phishing-e-mail of malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

In de **uitsplitsing Grafiek op type beleid** en Gegevens weergeven per e-mail **\> Phish** of Weergave van gegevens per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:

- **Anti-malware**
- **Safe Bijlagen**<sup>\*</sup>
- **Anti-phish**
- **Antispam**
- **E-mailstroomregel** (ook wel transportregel genoemd)
- **Anderen**

In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:

- **Datum**
- **Onderwerp**
- **Afzender**
- **Geadresseerden**
- **Gedetecteerd door**
- **Bezorgingsstatus**
- **Bron van compromis**
- **Tags**

Als u op **Filter klikt,** zijn de volgende filters beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Detectie**
- **Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**
- **Richting**
- **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
- **Domein**
- **Beleidstype**
- **Naam van beleid** (alleen detailstabel)
- **Geadresseerden**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

### <a name="chart-breakdown-by-delivery-status-and-view-data-by-email--phish-or-view-data-by-email--malware"></a>Grafiekinsplitsing op bezorgingsstatus en Gegevens weergeven per \> e-mail phish of Gegevens weergeven per \> e-mail malware

![Weergave bezorgingsstatus voor phishing-e-mail en malware-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

In de **uitsplitsing Grafiek per bezorgingsstatus** en **Gegevens weergeven per e-mail \> phish** of Gegevens weergeven per e-mail **\> malwareweergaven,** worden de volgende gegevens weergegeven in de grafieken:

- **Gehost postvak: Postvak IN**
- **Gehost postvak: Ongewenste e-mail**
- **Gehost postvak: aangepaste map**
- **Gehost postvak: Verwijderde items**
- **Doorgestuurd**
- **On-premises server: geleverd**
- **Quarantaine**
- **Bezorging mislukt**
- **Laten vallen**

In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:

- **Datum**
- **Onderwerp**
- **Afzender**
- **Geadresseerden**
- **Gedetecteerd door**
- **Bezorgingsstatus**
- **Bron van compromis**
- **Tags**

Als u op **Filter klikt,** zijn de volgende filters beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Detectie**
- **Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**
- **Richting**
- **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
- **Domein**
- **Beleidstype**
- **Naam van beleid** (alleen detailstabel)
- **Geadresseerden**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

### <a name="view-data-by-content--malware"></a>Gegevens weergeven op \> inhoudsmalware

![Inhoudsmalwareweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

In de **weergave Gegevens weergeven op \> inhoudsmalware** worden de volgende gegevens weergegeven in de grafiek voor Microsoft Defender voor Office 365 organisaties:

- **Anti-malware-engine:** Schadelijke bestanden die zijn gedetecteerd in Sharepoint, OneDrive en Microsoft Teams door de [ingebouwde virusdetectie in Microsoft 365.](virus-detection-in-spo.md)
- **Bestandsdetonatie:** schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Locatie**
- **Gedetecteerd door**
- **Malwarenaam**

Als u op **Filter klikt,** zijn de volgende filters beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Detectie:** **Anti-malware-engine** of **Bestandsdetonatie**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

### <a name="view-data-by-system-override"></a>Gegevens weergeven op systeem overschrijven

![Weergave bericht overschrijven in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-message-override-view.png)

In de **weergave Gegevens weergeven op systeem overschrijven** worden de volgende redengegevens overschrijven weergegeven in de grafiek:

- **On-premises overslaan**
- **IP-toestaan**
- **Exchange regel voor e-mailtransport** (regel e-mailstroom)
- **Organisatie toegestaan afzenders**
- **Toegestane domeinen van de organisatie**
- **ZAP niet ingeschakeld**
- **Map Ongewenste e-mail niet ingeschakeld**
- **Gebruiker Safe afzender**
- **User Safe Domain**

In de detailtabel onder de grafiek zijn de volgende gegevens beschikbaar:

- **Datum**
- **Onderwerp**
- **Afzender**
- **Geadresseerden**
- **Gedetecteerd door**
- **Bezorgingsstatus**
- **Bron van compromis**
- **Tags**

Als u op **Filter klikt,** zijn de volgende filters beschikbaar:

- **Datum (UTC)** **Begindatum** en **einddatum**
- **Detectie**
- **Beveiligd door**: **MDO** (Defender voor Office 365) of **EOP**
- **Richting**
- **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
- **Domein**
- **Beleidstype**
- **Naam van beleid** (alleen detailstabel)
- **Geadresseerden**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

<sup>\*</sup>Defender voor Office 365 alleen

## <a name="top-malware-report"></a>Top malwarerapport

Het **rapport Top malware** toont de verschillende soorten malware die zijn gedetecteerd door [anti-malwarebeveiliging in EOP.](anti-malware-protection.md)

Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina & samenwerkingsrapporten** naar **Top malware** en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/TopMalware> .

![Top malware widget on the Email & collaboration reports page](../../media/top-malware-report-widget.png)

Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u de naam van een soort malware en hoeveel berichten zijn gedetecteerd als malware.

Op de **pagina Top malwarerapport** wordt een grotere versie van het cirkeldiagram weergegeven op de rapportpagina. In de detailtabel onder de grafiek ziet u de volgende informatie:

- **Top malware**
- **Aantal**

Als u op **Filter klikt,** kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

![Top malwarerapportweergave](../../media/top-malware-report-view.png)

## <a name="url-threat-protection-report"></a>URL-bedreigingsbeveiligingsrapport

Het **rapport URL-bedreigingsbeveiliging** is beschikbaar in Microsoft Defender voor Office 365. Zie het rapport [URL-bedreigingsbeveiliging voor meer informatie.](view-reports-for-mdo.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>Rapport met gerapporteerde berichten van gebruiker

> [!IMPORTANT]
> Als het rapport **Gerapporteerde** berichten van de gebruiker correct werkt, moet **auditregistratie** zijn ingeschakeld voor uw Microsoft 365 omgeving. Dit wordt meestal gedaan door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online. Zie Het zoeken in Microsoft 365 [auditlogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

Het **rapport Gerapporteerde** berichten van gebruiker bevat informatie over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede [e-mail](enable-the-report-message-add-in.md) met behulp van de invoeging Rapportbericht of de invoeging [Phishing melden.](enable-the-report-phish-add-in.md)

Als u het rapport wilt weergeven in  de Microsoft 365 Defender portal, gaat u naar Rapporten e-mail & \> **samenwerking** \> **e-mail & samenwerkingsrapporten**. Zoek op **de pagina E-& samenwerkingsrapporten** naar **Gerapporteerde** berichten van de gebruiker en klik vervolgens op **Details weergeven.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://security.microsoft.com/reports/userSubmissionReport> . Als u wilt gaan [naar beheerdersinzendingen in de Microsoft 365 Defender portal,](admin-submission.md)klikt u **op Ga naar Inzendingen.**

![Widget met gerapporteerde berichten van gebruiker op de pagina E-mail & samenwerkingsrapporten](../../media/user-reported-messages-widget.png)

Op de **pagina Gerapporteerde** berichten van gebruiker kunt u zowel de grafiek als de detailtabel filteren door op **Filter** te klikken en een of meer van de volgende waarden te selecteren in het flyout dat wordt weergegeven:

- **Datum gerapporteerd:** **Begintijd** en **eindtijd**
- **Gerapporteerd door**
- **E-mail onderwerp**
- **Bericht gerapporteerde id**
- **Netwerkbericht-id**
- **Afzender**
- **Gerapporteerde reden**
  - **Geen ongewenste e-mail**
  - **Phishing**
  - **Spam**
- **Phish-simulatie:** **Ja** of **Nee**

Wanneer u klaar bent met het configureren van de filters, klikt u **op Toepassen,** **Annuleren** of **Filters wissen.**

Als u de items wilt groepeert, klikt u **op Groep** en selecteert u een van de volgende waarden in de vervolgkeuzelijst:

- **Geen**
- **Reden**
- **Afzender**
- **Gerapporteerd door**
- **Resultaat opnieuw scannen**
- **Phish-simulatie**

![Rapport met gerapporteerde berichten van gebruiker](../../media/user-reported-messages-report.png)

In de detailtabel onder de grafiek ziet u de volgende details:

- **E-mail onderwerp**
- **Gerapporteerd door**
- **Datum gerapporteerd**
- **Afzender**
- **Gerapporteerde reden**
- **Resultaat opnieuw scannen**
- **Tags**

Als u een bericht wilt verzenden naar Microsoft voor analyse, selecteert u de berichtinvoer in de tabel, klikt u op Verzenden bij **Microsoft** voor analyse en selecteert u een van de volgende waarden in de vervolgkeuzelijst:

- **Rapport opschoon**
- **Phishing melden**
- **Malware rapporteren**
- **Spam melden**'
- **Onderzoek starten** (Defender voor Office 365)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welke machtigingen zijn nodig om deze rapporten weer te geven?

Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in de Microsoft 365 Defender portal:

- **Organisatiebeheer**
- **Beveiligingsbeheerder**
- **Beveiligingslezer**
- **Globale lezer**

Zie Machtigingen in de Microsoft 365 Defender [portal voor meer informatie.](permissions-in-the-security-and-compliance-center.md)

**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory rol in de Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in de _Microsoft 365 Defender-portal_ en machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="what-if-the-reports-arent-showing-data"></a>Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?

Als u geen gegevens in uw rapporten ziet, controleert u of uw beleid correct is ingesteld. Zie Beschermen tegen [bedreigingen voor meer informatie.](protect-against-threats.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Bescherming tegen spam en anti-malware in EOP](anti-spam-and-anti-malware-protection.md)

[Slimme rapporten en inzichten in de Microsoft 365 Defender portal](reports-and-insights-in-security-and-compliance.md)

[E-mailstroomrapporten weergeven in de Microsoft 365 Defender portal](view-mail-flow-reports.md)

[Rapporten weergeven voor Defender voor Office 365](view-reports-for-mdo.md)
