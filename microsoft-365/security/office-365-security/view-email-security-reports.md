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
description: Lees hoe u beveiligingsrapporten voor e-mail voor uw organisatie kunt vinden en gebruiken. Beveiligingsrapporten voor e-mail zijn beschikbaar in het & Compliancecentrum.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: f6d9f149c9e1c71532018e6b43a6e9e31eb04607
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290797"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>E-mailbeveiligingsrapporten bekijken in het Beveiligings- en compliancecentrum

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

In het beveiligings- &-compliancecentrum vindt u [diverse](https://protection.office.com) rapporten om te zien hoe beveiligingsfuncties voor e-mail, zoals antispam, malware en versleutelingsfuncties in Microsoft 365 uw organisatie beschermen. Als u de [benodigde machtigingen hebt,](#what-permissions-are-needed-to-view-these-reports)kunt u deze rapporten bekijken in het beveiligings- & Compliancecentrum door naar rapportendashboard **te** \> **gaan.** Als u rechtstreeks naar het dashboard Rapporten wilt gaan, opent u <https://protection.office.com/insightdashboard> .

![Dashboard Rapporten in het beveiligings- & compliancecentrum](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Rapport Over gekromde gebruikers

> [!NOTE]
> Dit rapport is beschikbaar in Microsoft 365-organisaties met Exchange Online-postvakken. Het is niet beschikbaar in zelfstandige Exchange Online Protection (EOP)-organisaties.

In **het rapport Gecompromitteerde** gebruikers ziet  u  het aantal gebruikersaccounts dat in de afgelopen zeven dagen is gemarkeerd als Verdacht of Beperkt. Accounts in een van deze landen zijn problematisch of zelfs gecompromitteerd. Bij vaak gebruik kunt u het rapport gebruiken om pieken en zelfs trends te herkennen in verdachte of beperkte accounts. Zie Reageren op een gekromd e-mailaccount voor meer informatie over gecompromitteerd [gebruikers.](responding-to-a-compromised-email-account.md)

![Widget Over gekromde gebruikers in het dashboard Rapporten](../../media/compromised-users-report-widget.png)

In de samengevoegde weergave worden gegevens van de afgelopen 90 dagen en in de detailweergave de gegevens van de afgelopen 30 dagen weergeven.

Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** dashboard \> **Rapporten** en selecteert u **Gekromde gebruikers.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=CompromisedUsers> .

U kunt zowel de grafiek als de detailtabel filteren door te klikken op **Filters** en een of meer van de volgende waarden te selecteren:

- **Begindatum** **en einddatum**

- **Verdacht:** het gebruikersaccount heeft verdachte e-mailberichten verzonden en loopt het risico dat het niet kan worden verzonden.

- **Beperkt:** het gebruikersaccount kan geen e-mail meer verzenden vanwege zeer verdachte patronen.

![Rapportweergave in het rapport Gecompromitteerde gebruikers](../../media/compromised-users-report-activity-view.png)

Als u op **Detailtabel weergeven klikt,** ziet u de volgende details:

- **Tijd maken**
- **Gebruikers-id**
- **Actie**

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="encryption-report"></a>Versleutelingsrapport

Het **versleutelingsrapport** is beschikbaar in EOP (abonnementen met postvakken in Exchange Online of zelfstandige EOP zonder Exchange Online-postvakken). Het beveiligingsteam van uw organisatie kan informatie in dit rapport gebruiken om patronen te identificeren en beleid proactief toe te passen of aan te passen voor gevoelige e-mailberichten. Bijvoorbeeld:

- Als u veel e-mailberichten ziet die door gebruikers zijn versleuteld, kunt u een versleutelingsbeleid toevoegen om versleuteling voor bepaalde use cases te automatiseren. Zie Regels voor de [e-mailstroom definiëren om e-mailberichten te versleutelen in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md)voor meer informatie.

- Als er een aantal versleutelingssjablonen beschikbaar is, maar niemand gebruikt deze, kunt u na gaan of gebruikers functietraining nodig hebben.

In de samengevoegde weergave kunt u filteren voor de afgelopen 90 dagen, terwijl in de detailweergave 10 dagen mag worden gefilterd.

Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en **selecteert u Versleutelingsrapport.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=EncryptionReport> .

Zie E-mailversleuteling [in Microsoft 365](../../compliance/email-encryption.md)voor meer informatie over versleuteling.

### <a name="report-view-for-the-encryption-report"></a>Rapportweergave voor het versleutelingsrapport

U kunt de volgende filters in de grafiek gebruiken:

- **Gegevens weergeven op: Rapport berichtversleuteling** en **Opbreak door: Versleutelingsmethode:** De volgende versleutelingsmethoden zijn beschikbaar:

  - **Versleuteling door gebruiker**
  - **Versleuteling per beleid**

  Als u op **Filters klikt,** kunt u de grafiek wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Versleutelingsmethode.
  - Versleutelingssjabloon.

- **Gegevens weergeven op: Rapport berichtversleuteling** en **Opsbreed door:** Versleutelingssjabloon: De volgende versleutelingsmethoden zijn beschikbaar:

  - **Niet doorsturen**
  - **Alleen versleutelen**
  - **OME previous**
  - **Aangepast**

  Als u op **Filters klikt,** kunt u de grafiek wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - Versleutelingsmethode
  - Versleutelingssjabloon

- **Gegevens weergeven op: Top 5** geadresseerdendomeinen: In deze weergave ziet u een cirkeldiagram met verzonden berichttellingen voor de vijf belangrijkste geadresseerdendomeinen.

  Als u op **Filters klikt,** kunt u een **begin-** en **einddatum selecteren.**

### <a name="details-table-view-for-the-encryption-report"></a>Detailtabelweergave voor het versleutelingsrapport

Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:

- **Opbreed door: Versleutelingsmethode** of **Opbreed door:** Versleutelingssjabloon: De volgende informatie wordt weergegeven:

  - **Datum**
  - **Adres afzender**
  - **Versleutelingssjabloon**
  - **Versleutelingsmethode**
  - **Adres van geadresseerde**
  - **Onderwerp**

- **Gegevens weergeven op: De 5 belangrijkste geadresseerdendomeinen:**

  - **Datum**
  - **Domein van ontvanger**
  - **Aantal berichten**

Als u in een detailtabelweergave op **Filters** klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** **en einddatum**
- Versleutelingsmethode
- Versleutelingssjabloon

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="mailflow-status-report"></a>Mailflow status report

Het **rapport Mailflow-status** bevat informatie over geblokkeerde malware, spam, phishingberichten en geblokkeerde edge-berichten. Zie het [Mailflow-statusrapport](view-mail-flow-reports.md#mailflow-status-report)voor meer informatie.

## <a name="malware-detections-in-email-report"></a>Malwaredetectie in e-mailrapport

De **malwaredetectie in het** e-mailrapport bevat informatie over malwaredetectie in binnenkomende en uitgaande e-mailberichten (malware gedetecteerd door Exchange Online Protection of EOP). Zie Anti-malwarebeveiliging in EOP voor meer informatie over [malwarebeveiliging in EOP.](anti-malware-protection.md)

 Het filter voor de samengevoegde weergave kan 90 dagen duren, terwijl het detailtabelfilter slechts 10 dagen toestaat.

Als u het rapport wilt bekijken, opent u het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar **het** dashboard Rapporten en selecteert u \>  **Malwaredetecties in e-mail.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=MalwareDetections> .

![Malwaredetectie in e-mailwidget in het dashboard Rapporten](../../media/malware-detections-widget.png)

U kunt zowel de grafiek als de detailtabel filteren door op Filters te klikken **en** het volgende te selecteren:

- **Begindatum** **en einddatum**
- **Binnenkomende**
- **Uitgaand**

![Rapportweergave in de malwaredetectie in een e-mailrapport](../../media/malware-detections-report-view.png)

Als u op **Detailtabel weergeven klikt,** ziet u de volgende details:

- **Datum**
- **Adres afzender**
- **Adres van geadresseerde**
- **Bericht-id:** deze is beschikbaar in het **koptekstveld Bericht-id** in de berichtkop en moet uniek zijn. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).
- **Onderwerp**
- **Bestandsnaam**
- **Malwarenaam**

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="mail-latency-report"></a>E-maillatentierapport

Het **rapport E-maillatentie** bevat informatie over de ervaren e-mailbezorging en detonatielatentie binnen uw organisatie. Zie het [Mail-latentierapport](view-reports-for-atp.md#mail-latency-report)voor meer informatie.

## <a name="sent-and-received-email-report"></a>Rapport verzonden en ontvangen e-mail

Het **rapport Verzonden** en ontvangen e-mail bevat informatie over malware, spam, regels voor de e-mailstroom (ook wel transportregels genoemd) en geavanceerde malwaredetecties nadat e-mailberichten zijn verzonden naar de service. Zie Het rapport Verzonden en [ontvangen e-mail voor meer informatie.](view-mail-flow-reports.md#sent-and-received-email-report)

## <a name="spam-detections-report"></a>Rapport Over spamdetectie

Het **rapport Spamdetectie** toont spam-e-mailberichten die zijn geblokkeerd door EOP. Berichten worden afzonderlijk geteld, niet per geadresseerde. Als bijvoorbeeld hetzelfde spambericht is verzonden naar 100 geadresseerden in uw organisatie, telt dit als één bericht.

In de samengevoegde weergave kunt u 90 dagen filteren, terwijl in de detailtabel filteren binnen tien dagen is mogelijk.

Als u het rapport wilt bekijken, opent u  het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u \>  **Spamdetecties.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SpamDetections> .

![Widget spamdetectie in het dashboard Rapporten](../../media/spam-detections-report-widget.png)

Zie [Antispambeveiliging in EOP](anti-spam-protection.md)voor meer informatie over bescherming tegen spam.

### <a name="report-view-for-the-spam-detections-report"></a>Rapportweergave voor het rapport Over spamdetectie

De volgende grafieken zijn beschikbaar in de rapportweergave:

- **Op te breken met: Actie:** de volgende gebeurtenistypen worden weergegeven:

  - **Gefilterde spaminhoud**
  - **Spam-IP-blok**
  - **Blok met spam-enveloppen**
  - **Spam DBEB-filter:** randblokkering op basis van adreslijst (DBEB)

  Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, kunt u zien hoeveel items die dag zijn geblokkeerd en hoe deze items worden gecategoriseerd.

  ![Actieweergave in het rapport Spamdetectie](../../media/spam-detections-report-action-view.png)

- **In twee richtingen:** de volgende routebeschrijving wordt weergegeven:

  - **Binnenkomende**
  - **Uitgaand**

  ![Richtingsweergave in het rapport Spamdetectie](../../media/spam-detections-report-direction-view.png)

Als u in **een rapportweergave** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** **en einddatum**
- Richtingswaarden
- Waarden van gebeurtenistype

### <a name="details-table-view-for-the-spam-detections-report"></a>Tabelweergave Details voor het rapport Spamdetectie

Als u in **een rapportweergave op Detailtabel** weergeven klikt, wordt de volgende informatie weergegeven:

- **Datum**
- **Adres afzender**
- **Adres van geadresseerde**
- **Gebeurtenistype**
- **Actie**
- **Onderwerp**

Als u in **een detailtabel** op Filters klikt, kunt u de resultaten wijzigen met de volgende filters:

- **Begindatum** **en einddatum**
- Richtingswaarden
- Waarden van gebeurtenistype

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="spoof-detections-report"></a>Rapport met spoof-detecties

Het **rapport spoof-detecties** laat zien hoeveel spoof-e-mailberichten zijn gedetecteerd en welke als 'goed' werden beschouwd (spoof-e-mail die is uitgevoerd om legitieme zakelijke redenen). Zie Beveiliging tegen spoofing in EOP voor meer [informatie over spoofing.](anti-spoofing-protection.md)

In de samengevoegde weergave van het rapport kunt u 90 dagen filteren, terwijl in de detailweergave slechts tien dagen filtertijd is.

Als u het rapport wilt bekijken, opent u  het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar het dashboard Rapporten en selecteert u \>  **Spoof-detecties.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget voor spoofingsdetectie in het dashboard Rapporten](../../media/spoof-detections-widget.png)

Wanneer u de muisaanwijzer over een dag (gegevenspunt) in de grafiek beweegt, ziet u hoeveel spoof-e-mailberichten er zijn ontvangen.

U kunt zowel de grafiek als de detailtabel filteren door te klikken op **Filters** en een of meer van de volgende waarden te selecteren:

- **Begindatum** **en einddatum**

- **Goede e-mail**

- **Wordt als spam gemarkeerd**

![Rapportweergave in het rapport Spoof-detecties](../../media/spoof-detections-report-view.png)

Als u op **Detailtabel weergeven klikt,** ziet u de volgende details:

- **Datum**
- **Vervalste afzender**
- **Waar afzender**
- **AFZENDER-IP**
- **Actie**
- **Aantal berichten**

Als u terug wilt gaan naar de rapportweergave, klikt u **op Rapport weergeven.**

## <a name="threat-protection-status-report"></a>Statusrapport bedreigingsbeveiliging

Het **statusrapport Risicobeveiliging** is beschikbaar in zowel EOP als Microsoft Defender voor Office 365. De rapporten bevatten echter andere gegevens. EOP-klanten kunnen bijvoorbeeld informatie bekijken over malware die in e-mail is gedetecteerd, maar geen informatie over schadelijke bestanden gedetecteerd door veilige bijlagen voor [SharePoint, OneDrive](atp-for-spo-odb-and-teams.md)en Microsoft Teams.

Het rapport bevat het aantal e-mailberichten met schadelijke inhoud, zoals bestanden of websiteadressen (URL's) die zijn geblokkeerd door de antimalware-engine, [auto purge (ZAP,](zero-hour-auto-purge.md)nul uur) en Defender voor Office 365-functies [zoals](atp-safe-attachments.md) [veilige](atp-safe-links.md)koppelingen, veilige bijlagen en [anti-phishing.](set-up-anti-phishing-policies.md) U kunt deze informatie gebruiken om trends te identificeren of om te bepalen of het organisatiebeleid moet worden aangepast.

**Opmerking:** het is belangrijk om te weten dat als een bericht naar vijf geadresseerden wordt verzonden, het als vijf verschillende berichten wordt geteld en niet als één bericht.

Als u het rapport wilt bekijken, opent u het beveiligings- [& compliancecentrum,](https://protection.office.com)gaat u naar **het** dashboard Rapporten en selecteert u \>  Status **van bedreigingsbeveiliging.** Als u rechtstreeks naar het rapport wilt gaan, opent u een van de volgende URL's:

- Microsoft Defender voor Office 365: <https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- EOP: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Widget Status van bedreigingsbeveiliging in het dashboard Rapporten](../../media/threat-protection-status-report-widget.png)

Standaard worden in de grafiek gegevens van de afgelopen zeven dagen weergegeven. Als u op **Filters** klikt, kunt u een datumbereik van 90 dagen selecteren (proefabonnementen kunnen beperkt zijn tot 30 dagen). In de detailtabelweergave kunt u 30 dagen filteren.

### <a name="report-view-for-the-threat-protection-status-report"></a>Rapportweergave voor het statusrapport Risicobeveiliging

De volgende weergaven zijn beschikbaar:

- **Gegevens weergeven met: Overzicht:** de volgende detectiegegevens worden weergegeven:

  - **Malware via e-mail**
  - **Phish e-mailen**
  - **Malware in inhoud**

  ![Overzichtsweergave in het statusrapport Risicobeveiliging](../../media/threat-protection-status-report-overview-view.png)

- **Gegevens weergeven op: Inhoud \> Malware**<sup>1:</sup>de volgende informatie wordt weergegeven voor Microsoft Defender voor Office 365-organisaties:

  - **Anti-malware-engine:** kwaadaardige bestanden gedetecteerd in SharePoint, OneDrive en Microsoft Teams door de [ingebouwde virusdetectie in Microsoft 365.](virus-detection-in-spo.md)
  - **Bestandsdetonatie:** schadelijke bestanden gedetecteerd door veilige bijlagen voor [SharePoint, OneDrive en Microsoft Teams.](atp-for-spo-odb-and-teams.md)

  ![Weergave van malware op inhoud in het statusrapport Risicobeveiliging](../../media/threat-protection-status-report-content-malware-view.png)

- **Gegevens weergeven als: Bericht overschrijven:** de volgende reden hiervoor wordt weergegeven:

  - **On-premises overslaan**
  - **TOESTAAN MET IP**
  - **Regel voor e-mailstroom**
  - **Afzender toestaan**
  - **Toestaan van domein**
  - **ZAP niet ingeschakeld**
  - **Map Ongewenste e-mail niet ingeschakeld**
  - **Veilige afzender van gebruiker**
  - **Safe Domain van gebruiker**

  ![Weergave Bericht overschrijven in het statusrapport Risicobeveiliging](../../media/threat-protection-status-report-message-override-view.png)

- **Afbreed door: Detectietechnologie** en **Gegevens weergeven op: \> E-mail phish:** de volgende informatie wordt weergegeven:

  - **DOOR ATP gegenereerde URL-reputatie**<sup>1:</sup>Schadelijke URL-reputatie gegenereerd door Defender voor Office 365-detonaties in andere Klanten van Microsoft 365.
  - **Geavanceerd phish-filter:** Phishing-signalen op basis van machine learning.
  - **Anti-spoof - DMARC failure**: DMARC authentication failure on messages.
  - **Anti-spoof - rente-org:** afzender probeert het domein van de ontvanger te vervalsen.
  - **Anti-spoof - extern domein**: Sender probeert een ander domein te spoofen.
  - **Merk imitatie:** imitatie van bekende merken op basis van afzenders.
  - **Domein imitatie**<sup>1:</sup>Imitatie van domeinen die de klant bezit of definieert.
  - **Reputatie van EOP-URL:** schadelijke URL-reputatie.
  - **Algemeen phish-filter:** Phishing-signalen op basis van de regels van analisten.
  - **Overige**
  - **Phish ZAP**<sup>2</sup>: Automatisch nul uur verwijderen van phishing-berichten.
  - **URL-detonatie**<sup>1</sup>
  - **User impersonation**<sup>1:</sup>Impersonation of users defined by admin or learned through mailbox intelligence.

  ![Detectietechnologieweergave voor phishing-e-mail in het statusrapport Risicobeveiliging](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Op te delen met: Detectietechnologie** en **Gegevens weergeven op: E-mailmalware: \>** de volgende informatie wordt weergegeven:

  - **Door ATP gegenereerde**<sup>bestandsreputatie 1:</sup>Alle schadelijke bestandsreputatie die wordt gegenereerd door Defender voor Office 365-detonaties.
  - **Anti-malware engine**<sup>1:</sup>Detectie van anti-malware-engines.
  - **Blok van bestandstype tegen malwarebeleid:** dit zijn e-mailberichten die worden gefilterd vanwege het type schadelijk bestand dat wordt geïdentificeerd in het bericht.
  - **Bestandsdetonatie**<sup>1:</sup>Detectie door veilige bijlagen.
  - **Schadelijke bestandsreputatie**
  - **Malware ZAP**<sup>2</sup>
  - **Overige**

  ![Detectietechnologieweergave voor malware in het statusrapport Risicobeveiliging](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Op te delen met: Beleidstype** en **Gegevens weergeven op: \> E-mail phish** of Gegevens weergeven **op: E-mail \> malware:** de volgende informatie wordt weergegeven:

  - **Anti-malware**
  - **Veilige bijlagen**<sup>1</sup>
  - **Anti-phish**
  - **Antispam**
  - **E-mailstroomregel** (ook wel transportregel genoemd)
  - **Overige**

  ![Weergave beleidstype voor phishing-e-mail in het statusrapport Risicobeveiliging](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Op te delen door: Bezorgingsstatus** en Gegevens weergeven op: E-mail **\> phish** of Gegevens weergeven **door: E-mail \> malware:** de volgende informatie wordt weergegeven:

  - **Bezorging mislukt**
  - **Afgekapt**
  - **Doorgestuurd**
  - **Gehost postvak: Aangepaste map**
  - **Gehost postvak: Verwijderde items**
  - **Gehost postvak: Postvak IN**
  - **Gehost postvak: Ongewenste e-mail**
  - **On-premises server: Geleverd**
  - **Quarantaine**

  ![Weergave bezorgingsstatus voor phishing-e-mail in het statusrapport Risicobeveiliging](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>Alleen 1</sup> Defender voor Office 365

<sup>2</sup> Zero-hour Auto Purge (ZAP) is niet beschikbaar in zelfstandige EOP (het werkt alleen in Exchange Online-postvakken).

Als u op **Filters klikt,** zijn de beschikbare filters afhankelijk van de grafiek die u bekijkt:

- Voor **Gegevens weergeven op: \> Inhoudsmalware**  kunt u het rapport wijzigen op begin- en einddatum **en** de waarde van de **detectie.**

- Voor **gegevens weergeven als: Overschrijven bericht,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - **Reden overschrijven**
  - **Tag:** filter de resultaten op gebruikers of groepen op wie de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerstags voor meer informatie [over gebruikerslabels.](user-tags.md)
  - **Domein**

- Voor alle andere weergaven kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - **Detectie**
  - **Beveiligd door**: **ATP** of **EOP**
  - **Tag:** filter de resultaten op gebruikers of groepen op wie de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerstags voor meer informatie [over gebruikerslabels.](user-tags.md)
  - **Domein**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Tabelweergave Details voor het statusrapport Risicobeveiliging

Als u op **de tabel Details weergeven klikt,** is de informatie die wordt weergegeven afhankelijk van de grafiek die u bekijkt:

- **Gegevens weergeven op: Overzicht:** **Er is geen knop Detailstabel** weergeven beschikbaar.

- **Gegevens weergeven op: Inhoud \> Malware:**

  - **Datum**
  - **Locatie**
  - **Doorgestuurd door**
  - **Malwarenaam**

  Als u in **deze weergave** op Filters  klikt, kunt u het rapport wijzigen op begin- en einddatum **en** de waarde voor **detectie.**

- **Gegevens weergeven als: Bericht overschrijven:**

  - **Datum**
  - **Onderwerp**
  - **Afzender**
  - **Geadresseerden**
  - **Gedetecteerd door**
  - **Reden overschrijven**
  - **Bron van compromissen**
  - **Tags**

  Als u in deze **weergave op Filters** klikt, kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - **Reden overschrijven**
  - **Tag:** filter de resultaten op gebruikers of groepen op wie de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerstags voor meer informatie [over gebruikerslabels.](user-tags.md)
  - **Domein**
  - **Geadresseerden** (deze filterbare eigenschap is alleen beschikbaar in de detailtabelweergave)

- Alle andere grafieken:

  - **Datum**
  - **Onderwerp**
  - **Afzender**
  - **Geadresseerden**
  - **Gedetecteerd door**
  - **Bezorgingsstatus**
  - **Bron van compromissen**
  - **Tags**

  Als u op **Filters klikt,** kunt u het rapport wijzigen met de volgende filters:

  - **Begindatum** **en einddatum**
  - **Detectie**
  - **Beveiligd door**: **Defender voor Office 365** of **EOP**
  - **Tag:** filter de resultaten op gebruikers of groepen op wie de opgegeven gebruikerstag is toegepast (inclusief prioriteitsaccounts). Zie Gebruikerstags voor meer informatie [over gebruikerslabels.](user-tags.md)
  - **Domein**
  - **Geadresseerden** (deze filterbare eigenschap is alleen beschikbaar in de detailtabelweergave)

## <a name="top-malware-report"></a>Belangrijkste malwarerapport

Het **bovenste malwarerapport** bevat de verschillende soorten malware die is gedetecteerd door de beveiliging tegen [malware in EOP.](anti-malware-protection.md)

Als u het rapport wilt bekijken, opent u het [beveiligings- & compliancecentrum,](https://protection.office.com)gaat u naar **het** \> **dashboard Rapporten** en selecteert u **De belangrijkste malware.** Als u rechtstreeks naar het rapport wilt gaan, opent u <https://protection.office.com/reportv2?id=TopMalware> .

![Belangrijkste malwarewidget in het dashboard Rapporten](../../media/top-malware-report-widget.png)

Wanneer u de muisaanwijzer over een wig in het cirkeldiagram beweegt, kunt u de naam zien van een soort malware en kunt u zien hoeveel berichten malware bevatten.

![Topweergave malwarerapport](../../media/top-malware-report-view.png)

Als u op **Detailtabel weergeven klikt,** ziet u de volgende details:

- **Belangrijkste malware**
- **Aantal**

Als u klikt op **Filters** in de rapportweergave of de detailtabelweergave, kunt u een datumbereik opgeven met de **begin-** en **einddatum.**

## <a name="url-threat-protection-report"></a>Rapport URL-bedreigingsbeveiliging

Het **rapport URL-bedreigingsbeveiliging** is beschikbaar in Microsoft Defender voor Office 365. Zie het rapport [URL threat protection voor meer informatie.](view-reports-for-atp.md#url-threat-protection-report)

## <a name="user-reported-messages-report"></a>Rapport met door de gebruiker gerapporteerde berichten

In het rapport **met** door de gebruiker gerapporteerde berichten wordt informatie weergegeven over e-mailberichten die gebruikers hebben gerapporteerd als ongewenste e-mail, phishingpogingen of goede [e-mail](enable-the-report-message-add-in.md) met behulp van de invoegapp Bericht rapporteren of [Phishing melden.](enable-the-report-phish-add-in.md)

Er zijn details beschikbaar voor elk bericht, inclusief de bezorgings reden, zoals een uitzondering in het spambeleid of een regel voor de e-mailstroom die is geconfigureerd voor uw organisatie. Als u de details wilt bekijken, selecteert u een item  in de lijst met gebruikersrapporten en bekijkt u de informatie op de tabbladen Overzicht **en** Details.

![Het rapport User-Reported berichten bevat berichten die zijn aangeduid als ongewenste e-mail, geen ongewenste e-mail of phishing-pogingen.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Als u dit rapport wilt bekijken, gaat u op een van de volgende [&](https://protection.office.com)in het beveiligings- en compliancecentrum:

- Ga naar **berichten die door de** gebruiker van het \>  \> **bedreigingsbeheerdashboard zijn gerapporteerd.**

- Ga naar **Risicobeheer** \> **door de** gebruiker \> **gerapporteerde berichten.**

![Kies in het & Compliancecentrum de optie Door gebruiker voor \> \> risicobeheer gemelde berichten](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Om het rapport met door de gebruiker gerapporteerde berichten correct te laten werken, moet **auditlogregistratie zijn** ingeschakeld voor uw Office 365-omgeving. Dit wordt meestal gedaan door iemand aan wie de rol Auditlogboeken is toegewezen in Exchange Online. Zie Zoeken in [Microsoft 365-auditlogboek in- of uitschakelen voor meer informatie.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welke machtigingen zijn nodig om deze rapporten te bekijken?

Als u de rapporten in dit artikel wilt bekijken en gebruiken, moet u lid zijn van een van de volgende rollengroepen in het & Compliancecentrum:

- **Organisatiebeheer**
- **Beveiligingsbeheerder**
- **Beveiligingslezer**
- **Globale lezer**

Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

**Opmerking:** als u gebruikers toevoegt aan de bijbehorende Azure Active Directory-rol in het Microsoft 365-beheercentrum, krijgen gebruikers de vereiste machtigingen in het beveiligings- & compliancecentrum en machtigingen voor andere functies in Microsoft 365.  Raadpleeg [Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.

## <a name="what-if-the-reports-arent-showing-data"></a>Wat gebeurt er als er geen gegevens worden weergegeven in de rapporten?

Als u geen gegevens in uw rapporten ziet, controleert u nog eens of uw beleid correct is ingesteld. Zie Beveiligen tegen [bedreigingen voor meer informatie.](protect-against-threats.md)

## <a name="related-topics"></a>Verwante onderwerpen

[Bescherming tegen spam en malware in EOP](anti-spam-and-anti-malware-protection.md)

[Slimme rapporten en inzichten in het beveiligings- & compliancecentrum](reports-and-insights-in-security-and-compliance.md)

[E-mailstroomrapporten weergeven in het & compliancecentrum](view-mail-flow-reports.md)

[Rapporten voor Defender voor Office 365 weergeven](view-reports-for-atp.md)
