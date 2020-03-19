---
title: Weergaven campagnes in Office 365 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over campagneweergaven in Office 365 Advanced Threat Protection.
ms.openlocfilehash: 40eab14dff8d0c51a35bfbc7a04365a5a025e207
ms.sourcegitcommit: 08a4ee7765f3eba42f0c037c5c564c581e45df3e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42808824"
---
# <a name="campaign-views-in-office-365-atp"></a>Campagneweergaven in Office 365 ATP

Campagneweergaven is een functie in Advanced Threat Protection (ATP) in het Office 365 Security & Compliance Center die phishing-aanvallen in de service identificeert en categoriseert. Campagneweergaven kunnen u helpen om:

- Onderzoek en reageer efficiënt op phishing-aanvallen.

- Beter begrijpen van de omvang van de aanval.

- Toon waarde aan besluitvormers.

Met campagneweergaven u het grote beeld van een aanval sneller en completer zien dan welke mens dan ook.

## <a name="what-is-a-campaign"></a>Wat is een campagne?

Een campagne is een gecoördineerde e-mailaanval op een of meer organisaties. E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote en lucratieve industrie. Naarmate technologieën toenemen in een poging om aanvallen te stoppen, aanvallers wijzigen hun methoden in een poging om verder succes te garanderen.

Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing-, anti-spam- en anti-malwaregegevens in de gehele Office 365-service om campagnes te identificeren. We analyseren en classificeren de aanvalsinformatie op basis van verschillende factoren. Bijvoorbeeld:

- **Aanvalsbron**: Bron IP-adressen en e-maildomeinen van afzenders.

- **Eigenschappen van aanvalsberichten:** de inhoud, stijl en toon van de aanvalsberichten.

- **Aanvalsontvangers**: Geadresseerde functies, functies voor geadresseerden (beheerders, leidinggevenden, enz.), bedrijfstypen (groot, klein, openbaar, privé, enz.) en bedrijfstakken.

- **Aanval payload:** Kwaadaardige links, bijlagen, of andere payloads in de aanval berichten.

Een campagne kan van korte duur zijn of meerdere dagen, weken of maanden duren met actieve en inactieve perioden. Er kan een campagne worden gestart tegen uw specifieke organisatie of uw organisatie maakt mogelijk deel uit van een grotere campagne voor meerdere bedrijven.

## <a name="campaign-views-the-office-365-security--compliance-center"></a>Campagne bekijkt het Office 365 Security & Compliance Center

Campagneweergaven zijn beschikbaar in het [Security & Compliance Center](https://protection.office.com) bij Threat **management** \> **Campaigns**.

![Campagneoverzicht in het Security & Compliance Center](../../media/campaigns-overview.png)

Je ook naar de campagneweergave gaan via:

- **Campagne voor bedreigingsbeheer** \> \> **Explorer-weergave** \> **Campaigns** **Explorer**

- **Bedreigingsbeheer** \> **Explorer** \> **Bekijk** \> **alle e-mailcampagne** \> **Campaign**

> [!TIP]
> Als u geen campagnegegevens ziet, probeert u het datumbereik te wijzigen.

Op de overzichtspagina vindt u de volgende informatie over de campagne:

- **Naam**

- **Voorbeeldonderwerp**: De onderwerpregel van een van de berichten in de campagne. Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.

- **Type**: Momenteel is deze waarde altijd **Phish**.

- **Subtype**: Waar beschikbaar, het merk dat wordt phished door deze campagne. Wanneer de detectie wordt aangedreven door ATP-technologie, wordt het voorvoegsel **ATP-** toegevoegd aan de subtypewaarde.

- **Ontvangers**: het aantal gebruikers dat het doelwit was van deze campagne.

- **Inboxed**: Het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet geleverd aan Ongewenste e-mail).

- **Klikte**: Het aantal gebruikers dat op de URL in het phishingbericht heeft geklikt.

- **Klik op Frequentie**: Het percentage zoals berekend door "**Klikte** / **in boxed**". Deze waarde is een indicator van de effectiviteit van de campagne en of de ontvangers het bericht als phishing konden identificeren en niet op de URL van de payload konden klikken.

- **Bezocht**: Hoeveel gebruikers daadwerkelijk maakte het door naar de payload website. Als er **klikwaarden** zijn, maar veilige links de toegang tot de website hebben geblokkeerd, is deze waarde nul.

Wanneer u op de naam van een campagne klikt, worden de campagnegegevens weergegeven in een flyout.

## <a name="campaign-details"></a>Campagnegegevens

In de weergave campagnedetails is veel informatie beschikbaar over de campagne:

- Campagne-informatie:

  - **ID**: De unieke campagne-id.

  - **Gestart** en **beëindigd:** het datumbereikfilter dat u hebt geselecteerd.

  - **Impact**: de volgende gegevens voor het geselecteerde datumbereikfilter:
  
    - Het totale aantal ontvangers.

    - Het aantal berichten dat "Inboxed" (dat wil zeggen, geleverd aan de Inbox, niet aan Junk).

    - Hoeveel gebruikers hebben op de URL-payload in het phishingbericht geklikt.

    - Hoeveel gebruikers de URL hebben bezocht.

  - Een tijdlijn van campagneactiviteit: wanneer de campagne is gestart en beëindigd, en het aantal berichten in de loop van de tijd.

### <a name="campaign-flow"></a>Campagnestroom

Belangrijke details over de campagne worden weergegeven in een horizontaal stroomdiagram (bekend als een _Sankey-diagram)_ in de sectie **Flow.** Met deze gegevens u de elementen van de campagne en de mogelijke impact in uw organisatie begrijpen.

![Campagnegegevens die geen URL-klikken van gebruikers bevatten](../../media/campaign-details-no-recipient-actions.png)

Als u boven een horizontale band in het diagram zweeft, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaald bron-IP, berichten van het bron-IP-adres met behulp van het opgegeven afzenderdomein, enz.).

Het diagram bevat de volgende gegevens:

- **Afzender-IP's**

- **Afzenderdomeinen**

- **Filter vonnissen**: De waarden hier zijn gerelateerd aan de beschikbare phishing en spam filtering vonnissen zoals beschreven in [Anti-spam bericht headers](anti-spam-message-headers.md). De beschikbare waarden worden beschreven in de volgende tabel:

  |Value|Het oordeel van het spamfilter|Beschrijving|
  |:-----|:-----|:-----|
  | **Toegestaan**|`SFV:SKN` <br/><br/> `SFV:SKI`|Het bericht werd gemarkeerd als niet spam en/of overgeslagen filtering voordat het werd geëvalueerd door spamfiltering (bijvoorbeeld door een e-mailstroomregel, ook wel een transportregel genoemd).<br/><br/>Het bericht heeft spamfiltering om andere redenen overgeslagen (de afzender en ontvanger lijken bijvoorbeeld in dezelfde organisatie te zitten).|
  |**Geblokkeerd**|`SFV:SKS`|Het bericht werd gemarkeerd als spam voordat het werd geëvalueerd door spamfiltering (bijvoorbeeld door een e-mailstroomregel).|
  |**Gedetecteerd**|`SFV:SPM`|Het bericht werd gemarkeerd als spam door spamfiltering.|
  |**Niet gedetecteerd**|`SFV:NSPM`|Het bericht werd gemarkeerd als niet spam door spam filtering.|
  |**Vrijgegeven**|`SFV:SKQ`|Het bericht sloeg spamfiltering over omdat het uit quarantaine werd vrijgegeven.|
  |**Tenant toestaan**<sup>\*</sup>|`SFV:SKA`|Het bericht sloeg spamfiltering over vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).|
  |**Tenantblok**<sup>\*\*</sup>|`SFV:SKA`|Het bericht werd geblokkeerd door spamfiltering vanwege anti-spambeleidsinstellingen (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).|
  |**Gebruikerstoestaan**<sup>\*</sup>|`SFV:SFE`|Het bericht heeft spamfilters overgeslagen omdat de afzender zich in de lijst Veilige afzenders van een gebruiker in Outlook bevond.|
  |**Gebruikersblok**<sup>\*\*</sup>|`SFV:BLK`|Het bericht werd geblokkeerd door spamfiltering omdat de afzender zich in de lijst Geblokkeerde afzenders van een gebruiker in Outlook bevond.|
  |**Zap**|N/a|[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) heeft actie ondernomen op het afgeleverde bericht volgens uw anti-spam beleid instellingen (verplaatst naar de map Ongewenste e-mail of in quarantaine geplaatst).|

  <sup>\*</sup>Controleer uw antispambeleid, omdat het toegestane bericht waarschijnlijk door de service zou zijn geblokkeerd.

  <sup>\*\*</sup>Controleer uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.

- **Leveringslocaties**: U wilt waarschijnlijk berichten onderzoeken die daadwerkelijk aan ontvangers zijn bezorgd (of aan de map Postvak IN of de map Ongewenste e-mail), zelfs als gebruikers niet op de URL van de payload in het bericht hebben geklikt. U ook de berichten in quarantaine verwijderen uit quarantaine. Zie [E-mailberichten in quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

  - **Verwijderde map**

  - **Gedaald**

  - **Extern**: De ontvanger bevindt zich in uw on-premises e-mailorganisatie.

  - **Mislukt**

  - **Doorgestuurd**

  - **Inbox**

  - **Map Ongewenste ongewenste e-mail**

  - **Quarantaine**

  - **Unknown**

> [!NOTE]
> In alle lagen die meer dan 10 items bevatten, worden de top 10 items weergegeven, terwijl de rest is gebundeld in **anderen.**

#### <a name="url-clicks"></a>URL-klikken

Wanneer een phishingbericht wordt bezorgd aan een ontvanger (in het Postvak IN of de map Ongewenste e-mail), is er altijd een kans dat de gebruiker op de URL van de payload klikt. Niet klikken op de URL in een bezorgd bericht is een kleine mate van succes, maar je moet bepalen waarom de phishing-bericht werd geleverd aan hun mailbox in de eerste plaats.

Als een gebruiker in het phishingbericht op de URL van de payload heeft geklikt, worden de acties weergegeven in het **URL-klikgebied** van het diagram in de weergave campagnedetails.

- **Toegestaan**

- **BlockPage:** De ontvanger klikte op de URL van de payload, maar zijn toegang tot de kwaadaardige website werd geblokkeerd door het [ATP Safe Links-beleid](atp-safe-links.md) in uw organisatie.

- **BlockPageOverride**: De ontvanger klikte op de url van de payload in het bericht, ATP Safe Links probeerde ze te stoppen, maar ze mochten het blok overschrijven. U moet uw [beleid voor veilige links](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers het vonnis veilige links mogen overschrijven en doorgaan naar de schadelijke website.

- **PendingDetonationPage**: ATP Safe Attachments is in het proces van het openen van de payload URL in een virtuele computer omgeving, en zien wat er gebeurt.

- **PendingDetonationPageOverride**: De ontvanger mocht het ontnatieproces van payload's overschrijven en de URL openen zonder te wachten op de resultaten.

### <a name="tabs"></a>Tabbladen

Er zijn verschillende tabbladen in de campagnedetailsweergave waarmee u de campagne verder onderzoeken.

- **URL-klikken:** als gebruikers niet op de URL van de payload in het phishingbericht hebben geklikt, is deze sectie leeg. Als een gebruiker op de URL kon klikken, worden de volgende waarden ingevuld:

  - **Gebruiker**<sup>\*</sup>

  - **Url**<sup>\*</sup>

  - **Klik op Tijd**

  - **Klik op Actie**

- **Afzender-IP's**

  - **Afzender IP**<sup>\*</sup>

  - **Totaal aantal**

  - **Inboxed Tellen**

  - **Geblokkeerd aantal**

  - **SPF geslaagd:** De afzender is geverifieerd door het [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md) Een afzender die niet slaagt voor spf-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

- **Afzenders**

  - **Afzender**: Dit is het werkelijke afzenderadres in de opdracht SMTP MAIL FROM, wat niet noodzakelijkerwijs het Van: e-mailadres is dat gebruikers in hun e-mailclients zien.

  - **Totaal aantal**

  - **Inboxed**

  - **Niet inboxed**

  - **DKIM geslaagd:** De afzender is geverifieerd door [Domain Keys Identified Mail (DKIM).](support-for-validation-of-dkim-signed-messages.md) Een afzender die de DKIM-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

  - **DMARC geslaagd:** De afzender is geverifieerd door [domeingebaseerde berichtverificatie, rapportage en conformiteit (DMARC).](use-dmarc-to-validate-email.md) Een afzender die de DMARC-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

- **Payloads**

  - **Url**<sup>\*</sup>

  - **Totaal aantal**

<sup>\*</sup>Als u op deze waarde klikt, wordt een nieuwe flyout geopend die meer details bevat over het opgegeven item (gebruiker, URL, enz.) bovenop de weergave campagnedetails. Als u wilt terugkeren naar de weergave campagnedetails, klikt u op **Gereed** in de nieuwe flyout.

### <a name="buttons"></a>Knoppen

Met de knoppen in de weergave campagnedetails u de kracht van Threat Explorer gebruiken om de campagne verder te onderzoeken.

- **Campagne verkennen:** hiermee opent u een nieuw zoektabblad Bedreigingverkenner met de waarde **Campagne-id** als zoekfilter.

- **Inboxed-berichten verkennen:** hiermee opent u een nieuw zoektabblad Bedreigingverkenner met de **locatie Campagne-id** en **levering: Postvak IN** als zoekfilter.
