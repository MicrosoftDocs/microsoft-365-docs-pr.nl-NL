---
title: Weergaven van campagnes in ATP
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
description: Meer informatie over campagneweergaven in Geavanceerde bedreigingsbeveiliging van Office 365.
ms.openlocfilehash: 69b11319ffb033b628e59abac931b6a3f30d082c
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637816"
---
# <a name="campaign-views-in-atp"></a>Campagneweergaven in ATP

Campaign Views is een functie in Advanced Threat Protection (ATP) in het Security & Compliance Center dat phishing-aanvallen in de service identificeert en categoriseert. Campagneweergaven kunnen u helpen om:

- Efficiënt onderzoek en reageren op phishing-aanvallen.

- Beter inzicht in de omvang van de aanval.

- Toon waarde aan besluitvormers.

Met campagneweergaven u het grote plaatje van een aanval sneller en completer zien dan welke mens dan ook.

## <a name="what-is-a-campaign"></a>Wat is een campagne?

Een campagne is een gecoördineerde e-mailaanval op een of meer organisaties. E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote en lucratieve industrie. Naarmate technologieën toenemen in een poging om aanvallen te stoppen, aanvallers wijzigen hun methoden in een poging om blijvend succes te garanderen.

Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing, anti-spam en anti-malware gegevens over de hele dienst om te helpen bij het identificeren van campagnes. We analyseren en classificeren de aanvalsinformatie op basis van verschillende factoren. Bijvoorbeeld:

- **Aanvalsbron:** Bron-IP-adressen en e-maildomeinen van afzenders.

- **Eigenschappen van aanvalsberichten:** de inhoud, stijl en toon van de aanvalsberichten.

- **Ontvangers van aanvallen**: geadresseerde domeinen, geadresseerde functies (beheerders, leidinggevenden, enz.), bedrijfstypen (groot, klein, openbaar, privaat, enz.) en industrieën.

- **Attack payload:** Kwaadaardige links, bijlagen, of andere payloads in de aanval berichten.

Een campagne kan van korte duur zijn of meerdere dagen, weken of maanden duren met actieve en inactieve perioden. Er kan een campagne worden gestart tegen uw specifieke organisatie of uw organisatie maakt mogelijk deel uit van een grotere campagne voor meerdere bedrijven.

## <a name="campaign-views-the-security--compliance-center"></a>Campagne bekijkt het Security & Compliance Center

Campagneweergaven zijn beschikbaar in het [Security & Compliance Center](https://protection.office.com) bij Threat **Management** \> **Campaigns**.

![Campagneoverzicht in het Security & Compliance Center](../../media/campaigns-overview.png)

U ook naar de weergave Campagnes gaan vanaf:

- Campagnes \> voor \> \> **bedreigingsbeheerverkenners** **Threat management** **View** **Campaigns**

- **Bedreigingsbeheer** \> **Explorer** \> **Alle e-mailcampagne** \> **weergeven** \> **Campaign**

> [!TIP]
> Als u geen campagnegegevens ziet, probeert u het datumbereik te wijzigen.

Op de overzichtspagina vindt u de volgende informatie over de campagne:

- **Naam**

- **Voorbeeldonderwerp**: de onderwerpregel van een van de berichten in de campagne. Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.

- **Type**: Momenteel is deze waarde altijd **Phish**.

- **Subtype**: Indien beschikbaar, het merk dat wordt phished door deze campagne. Wanneer de detectie wordt aangedreven door ATP-technologie, wordt het voorvoegsel **ATP-** toegevoegd aan de subtypewaarde.

- **Ontvangers**: het aantal gebruikers dat het doelwit was van deze campagne.

- **Inboxed:** het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet geleverd aan Junk).

- **Klik:** het aantal gebruikers dat op de URL in het phishingbericht heeft geklikt.

- **Klikpercentage:** het percentage zoals berekend door " / **Klikinboxed**".**Clicked** Deze waarde is een indicator van de effectiviteit van de campagne, en of de ontvangers in staat waren om het bericht te identificeren als phishing en te voorkomen dat te klikken op de payload URL.

- **Bezocht**: Hoeveel gebruikers daadwerkelijk maakte het door naar de payload website. Als er **klikwaarden** zijn, maar veilige links de toegang tot de website hebben geblokkeerd, is deze waarde nul.

Wanneer u op de naam van een campagne klikt, worden de campagnegegevens weergegeven in een flyout.

## <a name="campaign-details"></a>Campagnegegevens

In de weergave campagnedetails is veel informatie beschikbaar over de campagne:

- Campagne-informatie:

  - **ID:** de unieke campagne-id.

  - **Gestart** en **beëindigd:** het datumbereikfilter dat u hebt geselecteerd.

  - **Impact:** de volgende gegevens voor het datumbereikfilter dat u hebt geselecteerd:
  
    - Het totale aantal ontvangers.

    - Het aantal berichten dat 'Inboxed' is (dat wil zeggen, geleverd aan de Postvak IN, niet aan Junk).

    - Hoeveel gebruikers klikten op de URL payload in het phishing-bericht.

    - Hoe veel gebruikers de URL hebben bezocht.

  - Een tijdlijn van campagneactiviteit: wanneer de campagne is gestart en beëindigd en het aantal berichten in de loop van de tijd.

### <a name="campaign-flow"></a>Campagnestroom

Belangrijke details over de campagne worden weergegeven in een horizontaal stroomdiagram (bekend als een _Sankey-diagram)_ in de sectie **Flow.** Deze gegevens helpen u inzicht te krijgen in de elementen van de campagne en de mogelijke impact in uw organisatie.

![Campagnegegevens die geen klikken op url-pagina's van gebruikers bevatten](../../media/campaign-details-no-recipient-actions.png)

Als u de plaats over een horizontale band in het diagram houdt, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaald bron-IP, berichten van het bron-IP met behulp van het opgegeven afzenderdomein, enz.).

Het diagram bevat de volgende informatie:

- **Afzender-IP's**

- **Afzenderdomeinen**

- **Filter uitspraken:** De waarden hier zijn gerelateerd aan de beschikbare phishing en spam filteren vonnissen zoals beschreven in [Anti-spam bericht headers](anti-spam-message-headers.md). De beschikbare waarden worden beschreven in de volgende tabel:

  |Value|Spam filter vonnis|Beschrijving|
  |:-----|:-----|:-----|
  | **Toegestaan**|`SFV:SKN` <br/><br/> `SFV:SKI`|Het bericht is gemarkeerd als geen spam en/of het filteren van overgeslagen voordat het wordt beoordeeld door spamfiltering (bijvoorbeeld door een regel voor e-mailstroom, ook wel een transportregel genoemd).<br/><br/>Het bericht heeft spamfilters overgeslagen om andere redenen (de afzender en ontvanger lijken zich bijvoorbeeld in dezelfde organisatie te bevindt).|
  |**Geblokkeerd**|`SFV:SKS`|Het bericht is gemarkeerd als spam voordat het werd geëvalueerd door spamfiltering (bijvoorbeeld door een regel voor e-mailstroom).|
  |**Gedetecteerd**|`SFV:SPM`|Het bericht is gemarkeerd als spam.|
  |**Niet gedetecteerd**|`SFV:NSPM`|Het bericht is gemarkeerd als geen spam door spamte filteren.|
  |**Vrijgegeven**|`SFV:SKQ`|Het bericht heeft spamfilters overgeslagen omdat het is vrijgegeven uit quarantaine.|
  |**Tenant toestaan**<sup>\*</sup>|`SFV:SKA`|Het bericht heeft spamfilters overgeslagen vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).|
  |**Tenantblok**<sup>\*\*</sup>|`SFV:SKA`|Het bericht is geblokkeerd door spamfiltering vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinlijst).|
  |**Gebruikerstoestaan**<sup>\*</sup>|`SFV:SFE`|Het bericht heeft spamfilters overgeslagen omdat de afzender zich in de lijst Veilige afzenders van een gebruiker in Outlook bevond.|
  |**Gebruikersblok**<sup>\*\*</sup>|`SFV:BLK`|Het bericht is geblokkeerd door spamfilters omdat de afzender zich in de lijst Geblokkeerde afzenders van een gebruiker in Outlook bevond.|
  |**Zap**|N/a|[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) ondernam actie op het afgeleverde bericht volgens uw anti-spam beleidsinstellingen (verplaatst naar de map Ongewenste e-mail of in quarantaine geplaatst).|

  <sup>\*</sup>Bekijk uw antispambeleid, omdat het toegestane bericht waarschijnlijk door de service is geblokkeerd.

  <sup>\*\*</sup>Bekijk uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.

- **Leveringslocaties**: U wilt waarschijnlijk berichten onderzoeken die daadwerkelijk aan ontvangers zijn geleverd (naar het Postvak IN of de map Ongewenste e-mail), zelfs als gebruikers niet op de payload-URL in het bericht hebben geklikt. U de in quarantaine geplaatste berichten ook uit quarantaine verwijderen. Zie [E-mailberichten in quarantaine in Office 365](quarantine-email-messages.md)voor meer informatie.

  - **Verwijderde map**

  - **Gedaald**

  - **Extern:** de ontvanger bevindt zich in uw on-premises e-mailorganisatie.

  - **Mislukt**

  - **Doorgestuurd**

  - **Inbox**

  - **Map ongewenste e-mail**

  - **Quarantaine**

  - **Unknown**

> [!NOTE]
> In alle lagen die meer dan 10 items bevatten, worden de bovenste 10 items weergegeven, terwijl de rest wordt gebundeld in **Anderen**.

#### <a name="url-clicks"></a>URL-klikken

Wanneer een phishingbericht wordt bezorgd aan een ontvanger (naar de Inbox of de map Ongewenste e-mail), bestaat de kans dat de gebruiker op de payload-URL klikt. Niet klikken op de URL in een geleverd bericht is een kleine mate van succes, maar je moet bepalen waarom de phishing-bericht werd geleverd aan hun mailbox in de eerste plaats.

Als een gebruiker op de payload-URL in het phishingbericht heeft geklikt, worden de acties weergegeven in het **URL-klikgebied** van het diagram in de weergave campagnedetails.

- **Toegestaan**

- **BlockPage:** De ontvanger klikte op de payload-URL, maar hun toegang tot de kwaadaardige website werd geblokkeerd door het [ATP Safe Links-beleid](atp-safe-links.md) in uw organisatie.

- **BlockPageOverride:** De ontvanger klikte op de payload URL in het bericht, ATP Safe Links geprobeerd om ze te stoppen, maar ze mochten het blok overschrijven. U moet uw [beleid voor veilige koppelingen](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers het vonnis van veilige koppelingen mogen overschrijven en doorgaan naar de kwaadaardige website.

- **In afwachtingVanDetonationPage:** ATP Safe Attachments is in het proces van het openen van de payload URL in een virtuele computer omgeving, en zien wat er gebeurt.

- **In afwachting vanDetonationPageOverride:** De ontvanger mocht het payload-ontploffingsproces overschrijven en de URL openen zonder op de resultaten te wachten.

### <a name="tabs"></a>Tabbladen

Er zijn verschillende tabbladen in de weergave campagnedetails waarmee u de campagne verder onderzoeken.

- **KLIKKEN OP URL:** Als gebruikers niet op de payload-URL in het phishingbericht hebben geklikt, is deze sectie leeg. Als een gebruiker op de URL heeft kunnen klikken, worden de volgende waarden ingevuld:

  - **Gebruiker**<sup>\*</sup>

  - **Url**<sup>\*</sup>

  - **Klik op Tijd**

  - **Klik op Actie**

- **Afzender-IP's**

  - **Ip-afzender**<sup>\*</sup>

  - **Totaal aantal**

  - **Geteld invak**

  - **Geblokkeerd aantal**

  - **SPF Geslaagd**: De afzender is geverifieerd door het [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md) Een afzender die niet voldoet aan de SPF-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

- **Afzenders**

  - **Afzender:** Dit is het werkelijke afzenderadres in de opdracht SMTP MAIL FROM, wat niet noodzakelijkerwijs het Van: e-mailadres is dat gebruikers in hun e-mailclients zien.

  - **Totaal aantal**

  - **Postvak IN**

  - **Niet inboxed**

  - **DKIM Geslaagd**: De afzender is geverifieerd door [Domain Keys Identified Mail (DKIM).](support-for-validation-of-dkim-signed-messages.md) Een afzender die niet voldoet aan de DKIM-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

  - **DMARC Geslaagd**: De afzender is geverifieerd door [Domeinverificatie, rapportage en conformiteit (DMARC).](use-dmarc-to-validate-email.md) Een afzender die niet voldoet aan de DMARC-validatie geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

- **Payloads**

  - **Url**<sup>\*</sup>

  - **Totaal aantal**

<sup>\*</sup>Als u op deze waarde klikt, wordt een nieuwe flyout geopend met meer details over het opgegeven item (gebruiker, URL, enz.) boven op de weergave campagnedetails. Als u wilt terugkeren naar de weergave campagnegegevens, klikt u op **Gereed** in de nieuwe flyout.

### <a name="buttons"></a>Knoppen

Met de knoppen in de weergave campagnedetails u de kracht van Threat Explorer gebruiken om de campagne verder te onderzoeken.

- **Campagne verkennen:** hiermee opent u een nieuw zoektabblad van Threat Explorer met de waarde **Campagne-id** als zoekfilter.

- **Berichten in postvak in verkennen:** hiermee opent u een nieuw zoektabblad van Threat Explorer met de **locatie Campagne-id** en **weergave: Postvak IN** als zoekfilter.
