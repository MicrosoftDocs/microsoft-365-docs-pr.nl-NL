---
title: Campagneweergaven in Microsoft Defender voor Office 365-abonnement
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Meer informatie over campagneweergaven in Microsoft Defender voor Office 365.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e7742b26eb901bc9dfe79d01a9f3414adf524dd9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286895"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Campagneweergaven in Microsoft Defender voor Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)

Campagneweergaven is een functie in Microsoft Defender voor Office 365 Abonnement 2 (bijvoorbeeld Microsoft 365 E5 of organisaties met een invoegfunctie voor Defender voor Office 365 Abonnement 2). Campagneweergaven in het & compliancecentrum identificeren en categoriseren phishing-aanvallen in de service. Campagneweergaven kunnen u helpen met het volgende:

- Onderzoek efficiënt en reageer op phishing-aanvallen.
- Beter inzicht in de omvang van de aanval.
- Waarde tonen aan besluitvormers.

Met campagneweergaven kunt u sneller en completer het geheel van een aanval zien dan een menselijke aanval.

## <a name="what-is-a-campaign"></a>Wat is een campagne?

Een campagne is een gecoördineerde e-mail-aanval tegen een of meer organisaties. E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote industrie. Naarmate technologieën meer tijd in het werk nemen om aanvallen te stoppen, veranderen aanvallers hun methoden in een poging om het succes te waarborgen.

Microsoft maakt gebruik van de grote hoeveelheden gegevens tegen phishing, antispam en malware in de hele service om campagnes te identificeren. We analyseren en classificeren de gegevens van de aanval op basis van verschillende factoren. Bijvoorbeeld:

- **Aanvalsbron:** de IP-adressen van de bron en de e-maildomeinen van de afzender.
- **Berichteigenschappen:** de inhoud, stijl en toon van de berichten.
- **Geadresseerden van het bericht:** de relatie van geadresseerden. Dit zijn bijvoorbeeld adresdomeinen, functies voor geadresseerden (beheerders, leidinggevenden, enzovoort), bedrijfstypen (grote, kleine, openbare, persoonlijke enzovoort) en bedrijfstakken.
- **Nettolading voor** aanvallen: kwaadaardige koppelingen, bijlagen of andere nettoladingen in de berichten.

Een campagne kan van korte duur zijn of meerdere dagen, weken of maanden duren met actieve en inactieve perioden. Er kan een campagne worden gestart voor uw specifieke organisatie of uw organisatie maakt deel uit van een grotere campagne voor meerdere bedrijven.

## <a name="campaign-views-in-the-security--compliance-center"></a>Campagneweergaven in het & compliancecentrum

Campagneweergaven zijn beschikbaar in het & [compliancecentrum van](https://protection.office.com) **Bedreigingsbeheercampagnes** \> of rechtstreeks op <https://protection.office.com/campaigns> .

![Overzicht van campagnes in het beveiligings- & compliancecentrum](../../media/campaigns-overview.png)

U kunt ook naar campagneweergaven gaan vanuit:

- **Bedreigingsbeheer** \> **Verkenner** \> **Weergeven** \> **Campagnes**
- **Bedreigingsbeheer** \> **Verkenner** \> **Weergeven** \> **Alle e-mailberichten** \> **Tabblad Campagne**
- **Bedreigingsbeheer** \> **Verkenner** \> **Weergeven** \> **Phish** \> **Tabblad Campagne**
- **Bedreigingsbeheer** \> **Verkenner** \> **Weergeven** \> **Malware** \> **Tabblad Campagne**

Voor toegang tot campagneweergaven moet u lid zijn van  de rollengroepen Organisatiebeheer, Beveiligingsbeheerder of Beveiligingslezer in het beveiligings- & compliancecentrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="campaigns-overview"></a>Overzicht campagnes

Op de overzichtspagina wordt informatie weergegeven over alle campagnes.

Op het **standaardtabblad** Campagne wordt in **het gebied Campagnetype** een staafdiagram weergegeven met het aantal geadresseerden per dag. Standaard worden in de grafiek zowel **Phish-** als **Malware-gegevens** weergegeven.

> [!TIP]
> Als u geen campagnegegevens ziet, kunt u het datumbereik of de [filters wijzigen.](#filters-and-settings)

Op de rest van de overzichtspagina ziet u de volgende informatie op het **tabblad** Campagne:

- **Naam**

- **Voorbeeldonderwerp:** het onderwerp van een van de berichten in de campagne. Houd er rekening mee dat alle berichten in de campagne niet per se hetzelfde onderwerp hebben.

- **Gericht:** het percentage zoals berekend door: (het aantal geadresseerden voor campagne in uw organisatie) / (het totale aantal geadresseerden in de campagne in alle organisaties in de service). Deze waarde geeft aan in welke mate de campagne alleen is gericht op uw organisatie (een hogere waarde) versus ook op andere organisaties in de service (een lagere waarde).

- **Type:** deze waarde is **Phish** of **Malware.**

- **Subtype:** deze waarde bevat meer details over de campagne. Bijvoorbeeld:
  - **Phish:** waar beschikbaar, het merk dat wordt gepromoveerd door deze campagne. Bijvoorbeeld, `Microsoft` `365` , `Unknown` of `Outlook` `DocuSign` .
  - **Malware:** `HTML/PHISH` bijvoorbeeld, of `HTML/<MalwareFamilyName>` .

  Waar beschikbaar is het merk dat wordt ge phished door deze campagne. Wanneer de detectie wordt aangestuurd door Defender voor Office 365-technologie, wordt het voorvoegsel **ATP toegevoegd** aan de waarde van het subtype.

- **Geadresseerden:** het aantal gebruikers dat is gericht door deze campagne.

- **Postvak IN:** het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet bezorgd in de map Ongewenste e-mail).

- **Geklikt:** het aantal gebruikers dat op de URL heeft geklikt of de bijlage in het phishing-bericht heeft geopend.

- **Kliktarief:** het percentage zoals berekend door "**Geklikt**  /  **in Postvak** IN". Deze waarde geeft de effectiviteit van de campagne aan. Met andere woorden, als de ontvangers het bericht als phishing kunnen identificeren en als ze niet op de nettolading-URL hebben geklikt.

  Het **klikpercentage wordt** niet gebruikt in malwarecampagnes.

- **Bezocht:** het aantal gebruikers dat de nettoladingwebsite heeft bezocht. Als er waarden **zijn waar** op wordt geklikt, maar veilige koppelingen de toegang tot de website geblokkeerd, is deze waarde nul.

Op **het origintabblad** Campagne worden de berichtbronnen op een wereldkaart weergegeven.

### <a name="filters-and-settings"></a>Filters en instellingen

Boven aan de pagina Campagneweergaven vindt u verschillende filter- en query-instellingen om specifieke campagnes te zoeken en te isoleren.

![Campagnefilters](../../media/campaign-filters-and-settings.png)

De meest eenvoudige filteropties die u kunt gebruiken, zijn de begindatum/-tijd en de einddatum/-tijd.

Als u de weergave verder wilt filteren, kunt u één eigenschap met meerdere waarden filteren door op de knop **Campagnetype** te klikken, uw selectie te maken en vervolgens op Vernieuwen **te klikken.**

De filterbare campagne-eigenschappen die beschikbaar zijn in de knop **Campagnetype** worden in de volgende lijst beschreven:

- **Basis:**
  - **Campagnetype:** Selecteer **Malware** **of Phish.** Het wissen van de selecties heeft hetzelfde resultaat als het selecteren van beide.
  - **Campagnenaam**
  - **Subtype Campagne**
  - **Afzender**
  - **Geadresseerden**
  - **Afzenderdomein**
  - **Onderwerp**
  - **Bestandsnaam bijlage**
  - **Malwarefamilie**
  - **Tags:** gebruikers of groepen die de opgegeven gebruikerstag hebben toegepast (inclusief prioriteitsaccounts). Zie Gebruikerstags voor meer informatie [over gebruikerslabels.](user-tags.md)
  - **Systeem overschrijven**
  - **Leveringsactie**
  - **Aanvullende actie**
  - **Directionality**
  - **Detectietechnologie**
  - **Oorspronkelijke bezorgingslocatie**
  - **Meest recente bezorgingslocatie**
  - **Systeem overschrijven**

- **Geavanceerd:**
  - **Internetbericht-id:** beschikbaar in het **koptekstveld Bericht-id** in de berichtkop. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaken).
  - **Netwerkbericht-id:** een GUID-waarde die beschikbaar is in het koptekstveld **X-MS-Exchange-Organization-Network-Message-Id** in de berichtkop.
  - **AFZENDER-IP**
  - **Bijlage SHA256:** als u de hashwaarde SHA256 van een bestand in Windows wilt zoeken, moet u de volgende opdracht uitvoeren in een opdrachtprompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256`
  - **Cluster-id**
  - **Id van waarschuwingsbeleid**
  - **ZAP URL-signaal**

- **URL's:**
  - **URL-domein**
  - **URL-domein en -pad**
  - **URL**
  - **URL-pad**
  - **Klik op een klik**

Voor geavanceerdere filters, waaronder filteren op meerdere eigenschappen, kunt u klikken op de knop Geavanceerd **filter** om een query te maken. Dezelfde campagne-eigenschappen zijn beschikbaar, maar met de volgende verbeteringen:

- U kunt op **Een voorwaarde toevoegen klikken om** meerdere voorwaarden te selecteren.
- U kunt de operator **And** of **Or** kiezen tussen voorwaarden.
- U kunt het **groepsitem Voorwaarde** onder aan de lijst met voorwaarden selecteren om complexe samengestelde voorwaarden te vormen.

Klik op de knop **Query** wanneer u klaar bent.

Nadat u een eenvoudig of geavanceerd filter hebt gemaakt, kunt u het opslaan met behulp van **query** Opslaan of **Query opslaan als.** Wanneer u later terug gaat naar de campagneweergaven, kunt u een opgeslagen filter laden door op Opgeslagen **query-instellingen te klikken.**

Als u de grafiek of de lijst met campagnes wilt exporteren, klikt u op **Exporteren** en **selecteert** u Grafiekgegevens exporteren of **Campagnelijst exporteren.**

Als u een abonnement hebt op Microsoft Defender for Endpoint, kunt u op **MDE-instellingen** klikken om verbinding te maken met de gegevens van de campagnes met Microsoft Defender for Endpoint of de verbinding verbreken. Zie Microsoft Defender voor [Office 365](integrate-office-365-ti-with-wdatp.md)integreren met Microsoft Defender voor eindpunt voor meer informatie.

## <a name="campaign-details"></a>Campagnedetails

Wanneer u op de naam van een campagne klikt, worden de campagnedetails weergegeven in een flyout.

### <a name="campaign-information"></a>Campagnegegevens

Boven aan de weergave met campagnedetails zijn de volgende campagnegegevens beschikbaar:

- **Id:** de unieke campagne-id.

- **Gestart** en **Beëindigd:** de begin- en einddatum van de campagne. Houd er rekening mee dat deze datums mogelijk verder gaan dan de filterdatums die u op de overzichtspagina hebt geselecteerd.

- **Impact:** deze sectie bevat de volgende gegevens voor het datumbereikfilter dat u hebt geselecteerd (of dat u selecteert in de tijdlijn):
  - Het totale aantal geadresseerden.
  - Het aantal berichten dat 'Postvak IN' is (dat wil zeggen, bezorgd in het Postvak IN, niet in de map Ongewenste e-mail).
  - Het aantal gebruikers dat heeft geklikt op de URL-nettolading in het phishingbericht.
  - Het aantal gebruikers dat de URL heeft bezocht.

- **Gericht:** het percentage zoals berekend door: (het aantal geadresseerden voor campagne in uw organisatie) / (het totale aantal geadresseerden in de campagne in alle organisaties in de service). Houd er rekening mee dat deze waarde gedurende de hele levensduur van de campagne wordt berekend en niet verandert op basis van datumfilters.

- Een interactieve tijdlijn van campagneactiviteit: Op de tijdlijn ziet u de activiteit gedurende de gehele levensduur van de campagne. Het gearceerde gebied bevat standaard het datumbereikfilter dat u in het overzicht hebt geselecteerd. U kunt klikken en slepen om een specifiek begin- en eindpunt te selecteren, waardoor de gegevens worden gewijzigd die worden weergegeven in het <u> **impactgebied** en</u>op de rest van de pagina, zoals wordt beschreven in de volgende secties.

Op de titelbalk kunt  u klikken op de op schrijfknop Campagne downloaden (opschrijven) om de campagnedetails te downloaden naar een ![ Word-document (standaard met de naam ](../../media/download-campaign-write-up-button.png) CampaignReport.docx). Houd er rekening mee dat de download details bevat voor de hele levensduur van de campagne (niet alleen de filterdatums die u hebt geselecteerd).

![Campagnegegevens](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Campagnestroom

In het midden van de weergave met campagnedetails  worden belangrijke details van de campagne weergegeven in de sectie Stroom in een horizontaal stroomdiagram (ook wel een _Sankey-diagram_ genoemd). Aan de hand van deze details krijgt u inzicht in de elementen van de campagne en de mogelijke impact op uw organisatie.

> [!TIP]
> De informatie die wordt weergegeven in het **stroomdiagram** wordt bepaald door het gearceerde datumbereik op de tijdlijn, zoals beschreven in de vorige sectie.

![Campagnedetails die geen klikken op gebruikers-URL's bevatten](../../media/campaign-details-no-recipient-actions.png)

Als u de muisaanwijzer op een horizontale band in het diagram houdt, ziet u het aantal verwante berichten (bijvoorbeeld berichten van een bepaalde bron-IP, berichten van het bron-IP-adres met het opgegeven afzenderdomein, enzovoort).

Het diagram bevat de volgende informatie:

- **Afzender-IP's**
- **Afzenderdomeinen**
- **Filterfilters:** Waarden voor filteren zijn gerelateerd aan de beschikbare phishing- en spamfilters zoals beschreven in berichtkoppen [tegen ongewenste e-mail.](anti-spam-message-headers.md) De beschikbare waarden worden in de volgende tabel beschreven:

  ****

  |Value|Filter voor ongewenste e-mail|Beschrijving|
  |---|---|---|
  |**Toegestaan**|`SFV:SKN` <p> `SFV:SKI`|Het bericht is gemarkeerd als geen spam en/of is overgeslagen filteren voordat het wordt geëvalueerd door spamfilters. Het bericht is bijvoorbeeld gemarkeerd als geen spam door een regel voor de e-mailstroom (ook wel transportregel genoemd). <p> Het bericht heeft het spamfilter om een andere reden overgeslagen. De afzender en geadresseerde lijken zich bijvoorbeeld in dezelfde organisatie te maken.|
  |**Geblokkeerd**|`SFV:SKS`|Het bericht is gemarkeerd als spam voordat het werd geëvalueerd door spamfilters. Bijvoorbeeld door een regel voor de e-mailstroom.|
  |**Gedetecteerd**|`SFV:SPM`|Het bericht is gemarkeerd als spam door het spamfilter.|
  |**Niet gedetecteerd**|`SFV:NSPM`|Het bericht is gemarkeerd als geen spam door spamfilters.|
  |**Uitgebracht**|`SFV:SKQ`|Het bericht is overgeslagen naar spamfilters omdat het uit quarantaine is vrijgegeven.|
  |**Tenant toestaan**<sup>\*</sup>|`SFV:SKA`|Het bericht is overgeslagen in spamfilters vanwege de instellingen in een antispambeleid. De afzender staat bijvoorbeeld in de lijst met toegestane afzenders of in de lijst met toegestane domeinen.|
  |**Tenantblok**<sup>\*\*</sup>|`SFV:SKA`|Het bericht is geblokkeerd door spamfilters vanwege de instellingen in een antispambeleid. De afzender staat bijvoorbeeld in de lijst met toegestane afzenders of in de lijst met toegestane domeinen.|
  |**Toestaan door gebruiker**<sup>\*</sup>|`SFV:SFE`|Het bericht is overgeslagen naar spamfilters omdat de afzender in de lijst met veilige afzenders van een gebruiker stond.|
  |**Gebruikersblok**<sup>\*\*</sup>|`SFV:BLK`|Het bericht is geblokkeerd door spamfilters omdat de afzender in de lijst met geblokkeerde afzenders van een gebruiker staat.|
  |**ZAP**|n.t.t.|[Met Zero-hour Auto Purge (ZAP)](zero-hour-auto-purge.md) wordt het bezorgde bericht verplaatst naar de map Ongewenste e-mail of quarantaine. U configureert de actie in uw antispambeleid.|
  |

  <sup>\*</sup> Controleer uw antispambeleid, omdat het toegestane bericht waarschijnlijk door de service is geblokkeerd.

  <sup>\*\*</sup> Controleer uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.

- Bezorgingslocaties: Waarschijnlijk wilt u berichten onderzoeken die zijn bezorgd bij geadresseerden (in het Postvak IN of de map Ongewenste e-mail), zelfs als gebruikers niet op de nettolading-URL in het bericht hebben geklikt. U kunt ook de in quarantaine geplaatste berichten uit quarantaine verwijderen. Zie In quarantaine [geplaatste e-mailberichten in EOP voor meer informatie.](quarantine-email-messages.md)
  - **Map verwijderd**
  - **Afgekapt**
  - **Extern:** de geadresseerde bevindt zich in uw on-premises e-mailorganisatie in hybride omgevingen.
  - **Mislukt**
  - **Doorgestuurd**
  - **Postvak IN**
  - **Map Ongewenste e-mail**
  - **Quarantaine**
  - **Unknown**

- **Klikken op** URL's: deze waarden worden in de volgende sectie beschreven.

> [!NOTE]
> In alle lagen die meer dan tien items bevatten, worden de bovenste 10 items weergegeven, terwijl de rest in Andere lagen is **gebundeld.**

#### <a name="url-clicks"></a>KLIKKEN op URL's

Wanneer een phishingbericht wordt bezorgd in het Postvak IN of de map Ongewenste e-mail van een geadresseerde, bestaat de kans dat de gebruiker op de nettolading-URL klikt. Het niet klikken op de URL is een klein succes, maar u moet bepalen waarom het phishing-bericht zelfs in het postvak is afgeleverd.

Als een gebruiker op de nettoladings-URL heeft geklikt in het phishingbericht, worden de acties weergegeven in het **gebied voor URL-klikken** van het diagram in de weergave met campagnedetails.

- **Toegestaan**
- **BlockPage:** De ontvanger heeft op de nettoladings-URL geklikt, maar zijn of haar toegang tot de schadelijke website is geblokkeerd door een beleid voor [veilige](atp-safe-links.md) koppelingen in uw organisatie.
- **BlockPageOverride:** de ontvanger heeft op de nettolading-URL in het bericht geklikt, Veilige koppelingen hebben geprobeerd ze te stoppen, maar ze konden de blokkering overschrijven. Controleer het [beleid voor veilige](set-up-atp-safe-links-policies.md) koppelingen om te zien waarom het gebruikers is toegestaan om het beleid voor veilige koppelingen te overschrijven en door te gaan naar de schadelijke website.
- **PendingDetonationPage:** Veilige bijlagen in Microsoft Defender voor Office 365 zijn bezig met het openen en onderzoeken van de nettolading-URL in een virtuele computeromgeving.
- **PendingDetonationPageOverride:** de ontvanger kon het nettoladingsdetonatieproces overschrijven en de URL openen zonder te wachten op de resultaten.

### <a name="tabs"></a>Tabbladen

Met de tabbladen in de weergave Campagnedetails kunt u de campagne verder onderzoeken.

> [!TIP]
> De informatie die op de tabbladen wordt weergegeven, wordt bepaald door het gearceerde datumbereik in de tijdlijn, zoals is beschreven in de sectie [Campagnegegevens.](#campaign-information)

- KLIKKEN OP DE **URL:** als gebruikers niet op de nettoladings-URL in het bericht hebben geklikt, is deze sectie leeg. Als een gebruiker op de URL kan klikken, worden de volgende waarden ingevuld:
  - **Gebruiker**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Klik op tijd**
  - **Klik op een klik**

- **Afzender-IP's**
  - **AFZENDER-IP**<sup>\*</sup>
  - **Totaal aantal**
  - **Postvak IN**
  - **Niet postvak IN**
  - **SPF doorgegeven:** de afzender is geverifieerd door [SPF (Sender Policy Framework).](how-office-365-uses-spf-to-prevent-spoofing.md) Een afzender die niet door SPF-validatie komt, geeft een niet-geauteerde afzender aan of het bericht vervalst een legitieme afzender.

- **Afzenders**
  - **Afzender:** dit is het adres van de werkelijke afzender in de opdracht SMTP MAIL FROM, wat niet noodzakelijkerwijs het Van-e-mailadres is dat gebruikers zien in hun e-mail clients.
  - **Totaal aantal**
  - **Postvak IN**
  - **Niet postvak IN**
  - **DKIM doorgegeven:** de afzender is geverifieerd door [DKIM (Domain Keys Identified Mail).](support-for-validation-of-dkim-signed-messages.md) Een afzender die niet door DKIM-validatie komt, geeft een niet-geauteerde afzender aan of het bericht vervalst een legitieme afzender.
  - **DMARC passed:** The sender was authenticated by [Domain-based Message Authentication, Reporting, and Conformance (DMARC)](use-dmarc-to-validate-email.md). Een afzender die niet door DMARC-validatie komt, geeft een niet-geauteerde afzender aan of het bericht vervalst een legitieme afzender.

- **Bijlagen**
  - **Bestandsnaam**
  - **SHA256**
  - **Malwarefamilie**
  - **Totaal aantal**

- **URL**
  - **URL**<sup>\*</sup>
  - **Total Count**

<sup>\*</sup> Als u op deze waarde klikt, wordt een nieuwe flyout geopend met meer informatie over het opgegeven item (gebruiker, URL, enzovoort) boven aan de weergave met campagnegegevens. Als u wilt terugkeren naar de weergave met campagnedetails, klikt u op **Klaar** in de nieuwe flyout.

### <a name="buttons"></a>Knoppen

Met de knoppen in de weergave Campagnedetails kunt u de kracht van Bedreigingsverkenner gebruiken om de campagne verder te onderzoeken.

- **Campagne verkennen:** hiermee opent u een nieuw zoektabblad Bedreigingsverkenner met de **waarde** voor campagne-id als zoekfilter.
- **Berichten in Postvak IN verkennen:** hiermee opent  u een nieuw zoektabblad van Bedreigingsverkenner met behulp van de campagne-id en bezorgingslocatie: **Postvak IN** als zoekfilter.
