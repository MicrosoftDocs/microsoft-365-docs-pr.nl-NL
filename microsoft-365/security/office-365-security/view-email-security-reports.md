---
title: E-mailbeveiligingsrapporten bekijken in het Beveiligings- en compliancecentrum
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
description: Meer informatie over het zoeken en gebruiken van e-mailbeveiligingsrapporten voor uw organisatie. E-mailbeveiligingsrapporten zijn beschikbaar in het & Compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 11fe6fd76d21b2dbd7a3e651d40efaa79f675a43
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52531011"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>E-mailbeveiligingsrapporten bekijken in het Beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Er zijn diverse rapporten beschikbaar in het [beveiligings- & compliancecentrum](https://protection.office.com) om te zien hoe e-mailbeveiligingsfuncties, zoals antispam, anti-malware en versleutelingsfuncties in Microsoft 365 uw organisatie beschermen. Als u de [benodigde machtigingen hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken in het Beveiligings- & compliancecentrum door naar  \> **Rapportendashboard** te gaan. Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://protection.office.com/insightdashboard> .

![Rapportendashboard in het beveiligings- & compliancecentrum](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Rapport over gecompromitteerde gebruikers

> [!NOTE]
> Dit rapport is beschikbaar in Microsoft 365 organisaties met Exchange Online postvakken. Het is niet beschikbaar in zelfstandige Exchange Online Protection (EOP) organisaties.

In **het rapport Gecompromitteerde** gebruikers ziet  u  het aantal gebruikersaccounts dat in de afgelopen 7 dagen is gemarkeerd als Verdacht of Beperkt. Accounts in een van deze staten zijn problematisch of zelfs gecompromitteerd. Met regelmatig gebruik kunt u het rapport gebruiken om pieken en zelfs trends te herkennen in verdachte of beperkte accounts. Zie Reageren op een gekromd e-mailaccount voor meer informatie over gecompromitteerde [gebruikers.](responding-to-a-compromised-email-account.md)

![Widget Voor gecompromitteerde gebruikers in het dashboard Rapporten](../../media/compromised-users-report-widget.png)

De statistische weergave bevat gegevens van de afgelopen 90 dagen en de detailweergave bevat gegevens van de afgelopen 30 dagen.

Als u het rapport wilt bekijken, opent u  het [beveiligingscentrum & compliancecentrum,](https://protection.office.com)gaat u naar Het \> **dashboard Rapporten** en selecteert u **Gecompromitteerde gebruikers.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=CompromisedUsers> .

U kunt zowel de grafiek als de detailtabel filteren door op **Filters** te klikken en een of meer van de volgende waarden te selecteren:

- **Begindatum** en **einddatum**

- **Verdacht:** Het gebruikersaccount heeft verdachte e-mailberichten verzonden en loopt het risico dat het niet meer kan worden verzonden.

- **Beperkt:** Het gebruikersaccount is beperkt tot het verzenden van e-mail vanwege zeer verdachte patronen.

![Rapportweergave in het rapport Gecompromitteerd gebruikers](../../media/compromised-users-report-activity-view.png)

Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:

- **Aanmaaktijd**
- **Gebruikers-id**
- **Actie**

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="encryption-report"></a>Versleutelingsrapport

Het **versleutelingsrapport** is beschikbaar in EOP (abonnementen met postvakken in Exchange Online zelfstandige EOP zonder Exchange Online postvakken). Het beveiligingsteam van uw organisatie kan informatie in dit rapport gebruiken om patronen te identificeren en beleidsregels proactief toe te passen of aan te passen voor gevoelige e-mailberichten. Bijvoorbeeld:

- Als er een groot aantal e-mailberichten wordt versleuteld door gebruikers, kunt u een versleutelingsbeleid toevoegen om versleuteling voor bepaalde gebruiksgevallen te automatiseren. Zie Regels voor e-mailstroom definiëren [om e-mailberichten te](../../compliance/define-mail-flow-rules-to-encrypt-email.md)versleutelen in Microsoft 365.

- Als u een aantal versleutelingssjablonen beschikbaar hebt, maar niemand deze gebruikt, kunt u onderzoeken of gebruikers functietraining nodig hebben.

Met de statistische weergave kunt u filteren voor de afgelopen 90 dagen, terwijl in de detailweergave 10 dagen kan worden gefilterd.

Als u het rapport wilt bekijken, opent u het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u **naar** \> **Rapportendashboard** en selecteert u **Versleutelingsrapport.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=EncryptionReport> .

Zie E-mailversleuteling in Microsoft 365 voor [meer informatie over versleuteling.](../../compliance/email-encryption.md)

### <a name="report-view-for-the-encryption-report"></a>Rapportweergave voor het versleutelingsrapport

U kunt de volgende filters in de grafiek gebruiken:

- **Gegevens weergeven op: Berichtversleutelingsrapport** en **Afbreed door: Versleutelingsmethode:** De volgende versleutelingsmethoden zijn beschikbaar:

  - **Versleuteling door gebruiker**
  - **Versleuteling per beleid**

  Als u op **Filters klikt,** kunt u de grafiek wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Versleutelingsmethode.
  - Versleutelingssjabloon.

- **Gegevens weergeven op: Berichtversleutelingsrapport** en **Afbreed door: Versleutelingssjabloon:** De volgende versleutelingsmethoden zijn beschikbaar:

  - **Niet doorsturen**
  - **Alleen versleutelen**
  - **OME vorige**
  - **Aangepast**

  Als u op **Filters klikt,** kunt u de grafiek wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - Versleutelingsmethode
  - Versleutelingssjabloon

- **Gegevens weergeven op: Top 5 geadresseerdedomeinen:** In deze weergave ziet u een cirkeldiagram met verzonden berichttellingen voor de bovenste 5 geadresseerdedomeinen.

  Als u op **Filters klikt,** kunt u een **begin-** en **einddatum selecteren.**

### <a name="details-table-view-for-the-encryption-report"></a>Tabelweergave Details voor het versleutelingsrapport

Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:

- **Afbreed door: Versleutelingsmethode** **of Afbreed door: Versleutelingssjabloon:** De volgende informatie wordt weergegeven:

  - **Datum**
  - **Adres afzender**
  - **Versleutelingssjabloon**
  - **Versleutelingsmethode**
  - **Adres van geadresseerde**
  - **Onderwerp**

- **Gegevens weergeven op: Top 5 adressendomeinen:**

  - **Datum**
  - **Domein geadresseerde**
  - **Aantal berichten**

Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten met de volgende filters wijzigen:

- **Begindatum** en **einddatum**
- Versleutelingsmethode
- Versleutelingssjabloon

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="mailflow-status-report"></a>E-mailflowstatusrapport

Het **rapport Mailflow-status** bevat informatie over malware, spam, phishing en edge geblokkeerde berichten. Zie [Mailflow-statusrapport](view-mail-flow-reports.md#mailflow-status-report)voor meer informatie.

## <a name="malware-detections-in-email-report"></a>Malwaredetecties in e-mailrapport

Het **malwaredetectierapport in het** e-mailrapport bevat informatie over malwaredetecties in inkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP). Zie [Anti-malwarebeveiliging in EOP](anti-malware-protection.md)voor meer informatie over malwarebeveiliging in EOP.

 Het filter voor de statistische weergave kan 90 dagen duren, terwijl het detailtabelfilter slechts 10 dagen toestaat.

Als u het rapport wilt bekijken, opent u  het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar Rapportendashboard en selecteert u \>  **Malwaredetecties in e-mail.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=MalwareDetections> .

![Malwaredetecties in e-mailwidget in het dashboard Rapporten](../../media/malware-detections-widget.png)

U kunt zowel de grafiek als de detailtabel filteren door op **Filters te klikken** en het volgende te selecteren:

- **Begindatum** en **einddatum**
- **Binnenkomende**
- **Uitgaande**

![Rapportweergave in het rapport Malwaredetectie in e-mailrapport](../../media/malware-detections-report-view.png)

Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:

- **Datum**
- **Adres afzender**
- **Adres van geadresseerde**
- **Bericht-id:** Beschikbaar in het **veld Bericht-id** in de berichtkoptekst en moet uniek zijn. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).
- **Onderwerp**
- **Bestandsnaam**
- **Malwarenaam**

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="mail-latency-report"></a>E-maillatentierapport

Het **rapport E-maillatentie** bevat informatie over de latentie van e-mailbezorging en detonatie binnen uw organisatie. Zie Mail [latentierapport](view-reports-for-mdo.md#mail-latency-report)voor meer informatie.

## <a name="sent-and-received-email-report"></a>E-mailrapport verzonden en ontvangen

Het **rapport Verzonden** en ontvangen e-mail bevat informatie over malware, spam, regels voor e-mailstromen (ook wel transportregels genoemd) en geavanceerde malwaredetecties nadat e-mail de service binnenkomt. Zie E-mailrapport [verzonden en ontvangen](view-mail-flow-reports.md#sent-and-received-email-report)voor meer informatie.

## <a name="spam-detections-report"></a>Rapport over spamdetectie

In **het rapport Spamdetecties** ziet u spam-e-mailberichten die zijn geblokkeerd door EOP. Berichten worden afzonderlijk geteld, niet per geadresseerde. Als bijvoorbeeld hetzelfde spambericht is verzonden naar 100 geadresseerden in uw organisatie, telt dit als één bericht.

In de statistische weergave kan 90 dagen worden gefilterd, terwijl in de detailtabel 10 dagen kan worden gefilterd.

Als u het rapport wilt bekijken, opent u het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar  \> **Rapportendashboard** en selecteert u **Spamdetecties.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget Spamdetecties in het dashboard Rapporten](../../media/spam-detections-report-widget.png)

Zie Bescherming tegen spam in [EOP](anti-spam-protection.md)voor meer informatie over bescherming tegen spam.

### <a name="report-view-for-the-spam-detections-report"></a>Rapportweergave voor het rapport Spamdetecties

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Afbreed door: Actie**: De volgende gebeurtenistypen worden weergegeven:

  - **Gefilterde spaminhoud**
  - **IP-blok spam**
  - **Spam envelopblok**
  - **Spam DBEB-filter:** Directory based edge blocking (DBEB)

  Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel items die dag zijn geblokkeerd en hoe deze items zijn gecategoriseerd.

  ![Actieweergave in het rapport Spamdetecties](../../media/spam-detections-report-action-view.png)

- **Afbreed door: Richting**: De volgende aanwijzingen worden weergegeven:

  - **Binnenkomende**
  - **Uitgaande**

  ![Richtingsweergave in het rapport Spamdetecties](../../media/spam-detections-report-direction-view.png)

Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten met de volgende filters wijzigen:

- **Begindatum** en **einddatum**
- Richtingswaarden
- Waarden voor gebeurtenistype

### <a name="details-table-view-for-the-spam-detections-report"></a>Tabelweergave details voor het rapport Spamdetecties

Als u in **een rapportweergave op Detailstabel** weergeven klikt, worden de volgende gegevens weergegeven:

- **Datum**
- **Adres afzender**
- **Adres van geadresseerde**
- **Gebeurtenistype**
- **Actie**
- **Onderwerp**

Als u in een **detailtabel** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** en **einddatum**
- Richtingswaarden
- Waarden voor gebeurtenistype

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

## <a name="spoof-detections-report"></a>Rapport spoofdetecties

> [!NOTE]
> Het verbeterde rapport Spoofdetecties, zoals beschreven in dit artikel, is in Preview, kan worden gewijzigd en is niet beschikbaar in alle organisaties. In de oudere versie van het rapport werden alleen **Goede e-mail en** **Als spam gesnapt.**

Het **rapport Spoofdetecties** bevat informatie over berichten die zijn geblokkeerd of toegestaan vanwege spoofing. Zie Bescherming tegen spoofing in EOP voor meer [informatie over spoofing.](anti-spoofing-protection.md)

Met de statistische weergave van het rapport kunt u 45 dagen filteren, terwijl de detailweergave slechts tien dagen <sup>\*</sup> filtert.

<sup>\*</sup> Uiteindelijk kunt u maximaal 90 dagen filteren gebruiken.

Als u het rapport wilt bekijken, opent u het [Beveiligings- & Compliancecentrum,](https://protection.office.com)gaat u naar  \> **Rapportendashboard** en selecteert u **Spoofdetecties.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget Spoofdetecties in het dashboard Rapporten](../../media/spoof-detections-widget.png)

Wanneer u de muisaanwijzer boven een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel vervalste berichten zijn gedetecteerd en waarom.

U kunt zowel de grafiek als de detailtabel filteren door op **Filters** te klikken en een of meer van de volgende waarden te selecteren:

- **Begindatum** en **einddatum**

- **Result**
  - **Pass**
  - **Mislukken**
  - **SoftPass**
  - **Geen**
  - **Overige**

- **Spooftype:** **Intern** en **Extern**

![Rapportweergave in het rapport Spoofdetecties](../../media/spoof-detections-report-view.png)

Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:

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

Als u terug wilt gaan naar de rapportweergave, klikt u op **Rapport weergeven.**

Zie Kopteksten voor spamberichten in Microsoft 365 voor [meer informatie over resultaatcodes voor samengestelde verificatie.](anti-spam-message-headers.md)

## <a name="threat-protection-status-report"></a>Statusrapport bedreigingsbeveiliging

Het **rapport Bedreigingsbeveiligingsstatus** is beschikbaar in zowel EOP als Microsoft Defender voor Office 365; De rapporten bevatten echter verschillende gegevens. EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die is gedetecteerd in e-mail, maar geen informatie over schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive](mdo-for-spo-odb-and-teams.md)en Microsoft Teams.

Het rapport bevat het aantal e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die zijn geblokkeerd door de anti-malware-engine, automatische [nul-uursre](safe-attachments.md) [purge (ZAP)](zero-hour-auto-purge.md)en Defender voor Office 365-functies, zoals [Safe Koppelingen,](safe-links.md)Safe Bijlagen en [Anti-phishing.](set-up-anti-phishing-policies.md) U kunt deze informatie gebruiken om trends te identificeren of om te bepalen of organisatiebeleid moet worden aangepast.

**Opmerking:** Het is belangrijk om te begrijpen dat als een bericht naar vijf geadresseerden wordt verzonden, we het als vijf verschillende berichten tellen en niet één bericht.

Als u het rapport wilt bekijken, opent u het [beveiligingscentrum & compliancecentrum,](https://protection.office.com)gaat u naar **Het** \> **dashboard Rapporten** en selecteert u **Status bedreigingsbeveiliging**. Open een van de volgende URL's om rechtstreeks naar het rapport te gaan:

- Microsoft Defender voor Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Statuswidget bedreigingsbeveiliging in het dashboard Rapporten](../../media/threat-protection-status-report-widget.png)

Standaard worden in de grafiek gegevens van de afgelopen 7 dagen weergegeven. Als u op **Filters** klikt, kunt u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen worden beperkt tot 30 dagen). In de tabelweergave details kunt u 30 dagen filteren.

### <a name="report-view-for-the-threat-protection-status-report"></a>Rapportweergave voor het rapport Bedreigingsbeveiliging

De volgende weergaven zijn beschikbaar:

- **Gegevens weergeven door: Overzicht:** De volgende detectiegegevens worden weergegeven:

  - **E-mailmalware**
  - **E-mail phish**
  - **Inhoudsmalware**

  ![Overzichtsweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-overview-view.png)

- **Gegevens weergeven op: Inhoud \> Malware**<sup>1:</sup>De volgende informatie wordt weergegeven voor Microsoft Defender voor Office 365 organisaties:

  - **Anti-malware-engine:** Schadelijke bestanden die zijn gedetecteerd in Sharepoint, OneDrive en Microsoft Teams door de [ingebouwde virusdetectie in Microsoft 365.](virus-detection-in-spo.md)
  - **Bestandsdetonatie:** schadelijke bestanden die zijn gedetecteerd door Safe Bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](mdo-for-spo-odb-and-teams.md)

  ![Inhoudsmalwareweergave in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

- **Gegevens weergeven op: Bericht overschrijven:** De volgende redengegevens worden weergegeven:

  - **On-premises overslaan**
  - **IP-toestaan**
  - **E-mailstroomregel**
  - **Afzender toestaan**
  - **Domein toestaan**
  - **ZAP niet ingeschakeld**
  - **Map Ongewenste e-mail niet ingeschakeld**
  - **Gebruiker Safe afzender**
  - **User Safe Domain**

  ![Weergave bericht overschrijven in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-message-override-view.png)

- **Afbreed door: Detectietechnologie en** **Gegevens weergeven door: E-mail \> phish:** De volgende informatie wordt weergegeven:

  - **ATP-gegenereerde URL-reputatie**<sup>1:</sup>Kwaadaardige URL-reputatie die is gegenereerd met Defender voor Office 365-detonaties in andere Microsoft 365 klanten.
  - **Geavanceerd phish-filter:** Phishing-signalen op basis van machine learning.
  - **Anti-spoof - DMARC-fout:** DMARC-verificatiefout op berichten.
  - **Anti-spoof - intra-org**: Afzender probeert het domein van de geadresseerde te vervalsen.
  - **Anti-spoof - extern domein:** Afzender probeert een ander domein te vervalsen.
  - **Merk imitatie:** Imitatie van bekende merken op basis van afzenders.
  - **Domein imitatie**<sup>1:</sup>Imitatie van domeinen die de klant bezit of definieert.
  - **EOP URL-reputatie:** reputatie van schadelijke URL's.
  - **Algemeen phish-filter:** Phishing-signalen op basis van analistregels.
  - **Anderen**
  - **Phish ZAP**<sup>2:</sup>Automatische nuluurse purge van phishingberichten.
  - **URL-detonatie**<sup>1</sup>
  - **Gebruikers-imitatie**<sup>1:</sup>imitatie van gebruikers die zijn gedefinieerd door beheerder of die zijn geleerd via postvakinformatie.

  ![Detectietechnologieweergave voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Afbreed door: Detectietechnologie en** **Gegevens weergeven door: E-mail \> malware:** De volgende informatie wordt weergegeven:

  - **ATP-gegenereerde**<sup>bestandsreputatie 1:</sup>Alle schadelijke bestandsreputatie die door Defender wordt gegenereerd voor Office 365 detonaties.
  - **Anti-malware engine**<sup>1:</sup>Detectie van anti-malware-engines.
  - **Bestandstype anti-malwarebeleid:** dit zijn e-mailberichten die zijn uitgefilterd vanwege het type schadelijk bestand dat in het bericht is geïdentificeerd.
  - **Bestandsdetonatie**<sup>1</sup>: Detectie door Safe bijlagen.
  - **Schadelijke bestandsreputatie**
  - **Malware ZAP**<sup>2</sup>
  - **Anderen**

  ![Detectietechnologieweergave voor malware in het rapport Status van bedreigingsbeveiliging](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Afbreed door: Type beleid** en **Gegevens weergeven op: E-mail \> Phish** of Gegevens weergeven **door: \> E-mail malware:** De volgende informatie wordt weergegeven:

  - **Anti-malware**
  - **Safe Bijlagen**<sup>1</sup>
  - **Anti-phish**
  - **Antispam**
  - **E-mailstroomregel** (ook wel transportregel genoemd)
  - **Anderen**

  ![Weergave beleidtype voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Afbreed door: Bezorgingsstatus** en **Gegevens weergeven door: E-mail \> Phish** of Gegevens weergeven **door: \> E-mail malware:** De volgende informatie wordt weergegeven:

  - **Bezorging mislukt**
  - **Laten vallen**
  - **Doorgestuurd**
  - **Gehost postvak: aangepaste map**
  - **Gehost postvak: Verwijderde items**
  - **Gehost postvak: Postvak IN**
  - **Gehost postvak: Ongewenste e-mail**
  - **On-premises server: geleverd**
  - **Quarantaine**

  ![Weergave bezorgingsstatus voor phishing-e-mail in het statusrapport Bedreigingsbeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Defender voor Office 365 alleen

<sup>2</sup> Zap (Zero Hour Auto Purge) is niet beschikbaar in zelfstandige EOP (het werkt alleen in Exchange Online postvakken).

Als u op **Filters klikt,** zijn de beschikbare filters afhankelijk van de grafiek die u bekijkt:

- Voor **Gegevens weergeven op: Content \> Malware**, kunt u het rapport wijzigen op **begindatum** en **einddatum** en de **detectiewaarde.**

- Voor **Gegevens weergeven door: Bericht overschrijven,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - **Reden overschrijven**
  - **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
  - **Domein**

- Voor alle andere weergaven kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** en **einddatum**
  - **Detectie**
  - **Beveiligd door**: **ATP** of **EOP**
  - **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
  - **Domein**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Tabelweergave details voor het rapport Status van bedreigingsbeveiliging

Als u op **Detailstabel weergeven klikt,** is de weergegeven informatie afhankelijk van de grafiek die u hebt bekeken:

- **Gegevens weergeven door: Overzicht:** **Knop Details weergeven** is niet beschikbaar.

- **Gegevens weergeven op: Inhoud \> Malware:**

  - **Datum**
  - **Locatie**
  - **Aangestuurd door**
  - **Malwarenaam**

  Als u in deze weergave op **Filters** klikt, kunt u het rapport wijzigen op **Begindatum** **en** Einddatum en de **waarde Detectie.**

- **Gegevens weergeven op: Bericht overschrijven:**

  - **Datum**
  - **Onderwerp**
  - **Afzender**
  - **Geadresseerden**
  - **Gedetecteerd door**
  - **Reden overschrijven**
  - **Bron van compromis**
  - **Tags**

  Als u in deze **weergave op Filters** klikt, kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - **Reden overschrijven**
  - **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
  - **Domein**
  - **Geadresseerden** (Houd er rekening mee dat deze filterbare eigenschap alleen beschikbaar is in de tabelweergave details)

- Alle andere grafieken:

  - **Datum**
  - **Onderwerp**
  - **Afzender**
  - **Geadresseerden**
  - **Gedetecteerd door**
  - **Bezorgingsstatus**
  - **Bron van compromis**
  - **Tags**

  Als u op **Filters klikt,** kunt u het rapport met de volgende filters wijzigen:

  - **Begindatum** en **einddatum**
  - **Detectie**
  - **Beveiligd door**: **Defender voor Office 365** of **EOP**
  - **Tag:** Filter de resultaten op gebruikers of groepen waarvan de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerslabels voor meer [informatie over gebruikerslabels.](user-tags.md)
  - **Domein**
  - **Geadresseerden** (Houd er rekening mee dat deze filterbare eigenschap alleen beschikbaar is in de tabelweergave details)

## <a name="top-malware-report"></a>Top malwarerapport

Het **rapport Top malware** toont de verschillende soorten malware die zijn gedetecteerd door [anti-malwarebeveiliging in EOP.](anti-malware-protection.md)

Als u het rapport wilt bekijken, opent u het [Beveiligingscentrum & Compliancecentrum,](https://protection.office.com)gaat u naar  \> **Rapportendashboard** en selecteert u **Top malware.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=TopMalware> .

![De belangrijkste malwarewidget in het dashboard Rapporten](../../media/top-malware-report-widget.png)

Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, ziet u de naam van een soort malware en hoeveel berichten zijn gedetecteerd als malware.

![Top malwarerapportweergave](../../media/top-malware-report-view.png)

Als u op **Detailstabel weergeven klikt,** ziet u de volgende details:

- **Top malware**
- **Aantal**

Als u in **de rapportweergave** of detailtabelweergave op Filters klikt, kunt u een datumbereik opgeven met **Begindatum** en **Einddatum.**

## <a name="url-threat-protection-report"></a>URL-bedreigingsbeveiligingsrapport

Het **rapport URL-bedreigingsbeveiliging** is beschikbaar in Microsoft Defender voor Office 365. Zie het rapport [URL-bedreigingsbeveiliging voor meer informatie.](view-reports-for-mdo.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>Rapport met door de gebruiker gerapporteerde berichten

Het rapport Door de gebruiker gerapporteerde berichten bevat informatie over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede **e-mail** met behulp van de [invoeging](enable-the-report-message-add-in.md) Rapportbericht of de invoegmap [Rapport phishing.](enable-the-report-phish-add-in.md)

Details zijn beschikbaar voor elk bericht, inclusief de bezorgingsreden, een dergelijke uitzondering voor spambeleid of e-mailstroomregel die is geconfigureerd voor uw organisatie. Als u details wilt weergeven, selecteert u een item in de  lijst met gebruikersrapporten en bekijkt u de gegevens op de tabbladen Overzicht **en** Details.

![Het User-Reported berichtenrapport bevat berichten die gebruikers als ongewenste e-mail, geen ongewenste e-mail of phishingpogingen hebben aangeduid.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Ga op een van [](https://protection.office.com)de volgende & om dit rapport weer te geven:

- Ga naar **Dashboard Bedreigingsbeheer** \>  \> **Door de gebruiker gerapporteerde berichten.**

- Ga naar **Bedreigingsbeheer** \> **Door** \> **de gebruiker gerapporteerde berichten controleren.**

![Kies in & Beveiligingscentrum de optie Meldingsberichten van gebruiker voor \> \> bedreigingsbeheer controleren](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Als u wilt dat het rapport Door de gebruiker gerapporteerde berichten correct werkt, moet **auditregistratie** zijn ingeschakeld voor uw Office 365 omgeving. Dit wordt meestal gedaan door iemand die de rol Auditlogboeken heeft toegewezen in Exchange Online. Zie Het zoeken in Microsoft 365 [auditlogboek in- of uitschakelen](../../compliance/turn-audit-log-search-on-or-off.md)voor meer informatie.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welke machtigingen zijn nodig om deze rapporten weer te geven?

Als u de rapporten wilt bekijken en gebruiken die in dit artikel worden beschreven, moet u lid zijn van een van de volgende rollengroepen in het Compliancecentrum & Beveiliging:

- **Organisatiebeheer**
- **Beveiligingsbeheerder**
- **Beveiligingslezer**
- **Globale lezer**

Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

**Opmerking:** Gebruikers toevoegen aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum geeft gebruikers de vereiste machtigingen in het Beveiligings- & _Compliancecentrum_ en machtigingen voor andere functies in Microsoft 365. Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="what-if-the-reports-arent-showing-data"></a>Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?

Als u geen gegevens in uw rapporten ziet, controleert u of uw beleid correct is ingesteld. Zie Beschermen tegen [bedreigingen voor meer informatie.](protect-against-threats.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Bescherming tegen spam en anti-malware in EOP](anti-spam-and-anti-malware-protection.md)

[Slimme rapporten en inzichten in het beveiligings- & compliancecentrum](reports-and-insights-in-security-and-compliance.md)

[E-mailstroomrapporten weergeven in het beveiligings- & compliancecentrum](view-mail-flow-reports.md)

[Rapporten weergeven voor Defender voor Office 365](view-reports-for-mdo.md)
