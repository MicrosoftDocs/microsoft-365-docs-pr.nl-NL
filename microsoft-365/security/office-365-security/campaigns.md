---
title: Campagne weergaven in ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Meer informatie over campagne weergaven in Office 365 Advanced Threat Protection.
ms.openlocfilehash: f0f5d2305b4f17c7018d32eebd155b4ad2d459e7
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825795"
---
# <a name="campaign-views-in-atp"></a>Campagne weergaven in ATP

Voorbeeld van een campagne is een functie in de weergave Advanced Threat Protection (ATP) in het beveiligings & nalevings centrum waarmee phishing-aanvallen in de service worden geïdentificeerd en gecategoriseerd. Met behulp van campagne weergaven kunt u:

- Onderzoek een efficiënt onderzoek en reageer op een malafide aanval.

- Beter inzicht in het reikwijdte van de aanval.

- Waarde weergeven voor beslissers.

Met campagne weergaven kunt u de grote afbeelding van een aanval sneller en helemaal compleet zien.

## <a name="what-is-a-campaign"></a>Wat is een campagne?

Een campagne is een gecoördineerde aanval van een e-mailbericht voor een of meer organisaties. E-mail aanvallen waarmee referenties en bedrijfsgegevens worden gestolen, bestaan uit een grote en lucrative-branche. Aangezien technologieën in een inspanning toenemen, wijzigen ze hun methoden in een inspanning om ervoor te zorgen dat ze succes oplopen.

Microsoft profiteert van de enorme hoeveelheid anti-phishing, anti-spam en bescherming tegen malware via de volledige service, zodat u campagnes kunt identificeren. We analyseren en classificeren de informatie over aanvallen op basis van diverse factoren. Bijvoorbeeld:

- **Schadelijke bron**: de bron-IP-adressen en de e-mail domeinen van de afzender.

- **Eigenschappen van een aanvals bericht**: de inhoud, stijl en Toon van de berichten.

- **Geadresseerden voor aanvallen**: domeinen van de ontvanger, de taakfuncties van de geadresseerde (beheerders, leidinggevenden, enzovoort), bedrijfstypen (groot, klein, openbaar, privé, enzovoort) en industrieën.

- **Nettolading**van een aanval: kwaadaardige koppelingen, bijlagen of andere nettoladingen in de berichten.

Een campagne kan korte tijd in beslag nemen of meerdere dagen, weken of maanden belopen met actieve en niet-actieve perioden. Er kan een campagne worden gestart voor uw specifieke organisatie of uw organisatie maakt deel uit van een grotere campagne in meerdere bedrijven.

## <a name="campaign-views-the-security--compliance-center"></a>Campagne weergeven & nalevings centrum voor beveiliging

De weergave campagne is beschikbaar in het [beveiligings & compliance](https://protection.office.com) van een **Threat Management** \> **Campaigns**-campagne, of direct op <https://protection.office.com/campaigns> .

![Overzicht van campagnes in het nalevings centrum voor beveiligings &](../../media/campaigns-overview.png)

U kunt ook weergave van de campagne bekijken:

- **Threat Management** \> **Verkenner** \> **Weergave** \> Een **campagne**

- **Threat Management** \> **Verkenner** \> **Weergave** \> **Alle e-mailberichten** \> Tabblad **campagne**

- **Threat Management** \> **Verkenner** \> **Weergave** \> **Phishing** \> Tabblad **campagne**

- **Threat Management** \> **Verkenner** \> **Weergave** \> **Malware** \> Tabblad **campagne**

Voor de weergave van een campagne moet u lid zijn van de rollen groepen **Organisatiebeheer**, **beveiliging beheerder**of **beveiligings lezer** in het beveiligings & nalevings centrum. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="campaigns-overview"></a>Overzicht van campagnes

Op de pagina overzicht vindt u informatie over alle campagnes.

Op het tabblad standaard **campagne** wordt in het gebied **type campagne** een staafdiagram weergegeven met het aantal geadresseerden per dag. In de grafiek worden standaard zowel de gegevens **phishing** als de **malware** weergegeven.

> [!TIP]
> Als u geen gegevens van een campagne ziet, probeer dan het datumbereik of de [filters](#filters-and-settings)te wijzigen.

De rest van de pagina overzicht bevat de volgende informatie op het tabblad **campagne** :

- **Naam**

- Voor **beeld van onderwerp**: het onderwerp van een van de berichten in de campagne. Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.

- **Targeted**: het percentage zoals berekend door: (het aantal geadresseerden van de campagne in uw organisatie)/(het totale aantal geadresseerden in de campagne voor alle organisaties in de service). Met deze waarde wordt de mate aangegeven waarin de campagne specifiek wordt aangegeven voor uw organisatie (een hogere waarde), en die wordt doorgestuurd naar andere organisaties in de service (een lagere waarde).

- **Type**: deze waarde is een **phishing** of **malware**.

- **Subtype**: deze waarde bevat meer details over de campagne. Bijvoorbeeld:

  - **Phishing**: indien beschikbaar, het merk dat wordt door deze campagne verphishd. Bijvoorbeeld,, `Microsoft` , `365` `Unknown` `Outlook` of `DocuSign` .

  - **Malware**: bijvoorbeeld `HTML/PHISH` of `HTML/<MalwareFamilyName>` .

Indien beschikbaar, het merk dat door deze campagne wordt verphishd. Wanneer de detectie wordt gestuurd met de ATP-technologie, wordt de **ATP-** voorvoegsel toegevoegd aan de waarde van het subtype.

- **Geadresseerden**: het aantal gebruikers dat is gericht op deze campagne.

- **Postvak in met postvak**in: het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun postvak in (niet bezorgd in de map Ongewenste e-mail).

- **Geklikt**op: het aantal gebruikers dat op de URL heeft geklikt of de bijlage in het malafide bericht heeft geopend.

- **Klik op rente**: het percentage zoals berekend door te**klikken**op  /  **Postvak in**. Deze waarde is een indicator van de effectiviteit van de campagne, en of de geadresseerden het bericht als phishing konden identificeren en niet op de URL van de nettolading hoeven te klikken.

  Houd er rekening mee dat deze waarde niet wordt gebruikt in malware van malware.

- **Bezocht**: hoeveel gebruikers hebben dit via de website van uw nettolading gemaakt. Als er op waarden werd **geklikt** , maar veilige koppelingen naar de website zijn geblokkeerd, is deze waarde nul.

Het tabblad **campagne oorsprong** bevat de berichten bronnen op een kaart van de wereld.

### <a name="filters-and-settings"></a>Filters en instellingen

Boven aan de pagina met campagne weergaven vindt u diverse filter-en queryinstellingen waarmee u specifieke campagnes kunt zoeken en isoleren.

![Campagne filters](../../media/campaign-filters-and-settings.png)

De meest basisfilters die u kunt uitvoeren, zijn de begindatum/-tijd en de einddatum en-tijd.

Als u de weergave verder wilt filteren, kunt u één eigenschap met meerdere waarden filteren door te klikken op de knop **campagnetype** , uw selectie te maken en vervolgens op **vernieuwen**te klikken.

In de volgende lijst vindt u een beschrijving van de beschikbare campagne-eigenschappen:

- Basis

  - **Type campagne**: Selecteer **malware** of **phishing**. Wanneer u de selecties uitschakelt, heeft dit hetzelfde resultaat als met beide.
  - **Naam van campagne**
  - **Subtype campagne**
  - **Afzender**
  - **Allen**
  - **Afzenderdomein**
  - **Onderwerp**
  - **Bestandsnaam van bijlage**
  - **Familie van malware**
  - **Bezorgings actie**
  - **Detectietechnologie**
  - **Tags**
  - **Systeem overschrijvingen**

- Geavanceerd

  - **Internet bericht-id**: beschikbaar in het veld **bericht-id-** koptekst in de kop van het bericht. Een Voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Let op de punthaken).
  
  - **Netwerkbericht-id**: een GUID-waarde die beschikbaar is in het veld **X-MS-Exchange-Organization-Network-Message-ID** in de kop van het bericht.
  
  - **IP van afzender**
  
  - **Bijlage sha256**: als u de sha256-hashwaarde van een bestand wilt zoeken in Windows, voert u de volgende opdracht uit op een opdrachtregel: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  
  - **Cluster-ID**
  
  - **ID van waarschuwings beleid**

- URLs

  - **URL-domein**
  - **URL Domain en Path**
  - **URL**
  - **URL-pad**
  - **Klik op Verdict**

Voor uitgebreid filteren, waaronder filteren via meerdere eigenschappen, kunt u op de knop **Geavanceerd filter** klikken om een query te maken. De eigenschappen van dezelfde campagne zijn beschikbaar, maar met de volgende verbeteringen:

- U kunt op **een voorwaarde toevoegen** klikken om meerdere voorwaarden te selecteren.
- U kunt de operator **and** of **or** kiezen tussen voorwaarden.
- U kunt het item **voor de voorwaarde-groep** onder aan de lijst met voorwaarden selecteren om complexe samengestelde voorwaarden te vormen.

Wanneer u klaar bent, klikt u op de knop **query** .

Nadat u een basis-of Geavanceerd filter hebt gemaakt, kunt u dit opslaan met behulp van **query opslaan** of **query opslaan als**. Wanneer u later terugkeert naar de weergave campagne, kunt u een opgeslagen filter laden door te klikken op **opgeslagen queryinstellingen**.

Als u de grafiek of de lijst met campagnes wilt exporteren, klikt u op **exporteren** en selecteert u **grafiekgegevens exporteren** of **campagnelijst exporteren**.

Als u een abonnement op Microsoft Defender ATP hebt, kunt u op **WDATP** klikken om verbinding te maken met de gegevens van de campagnes of de gegevens ervan te verbreken met Microsoft Defender ATP. Zie voor meer informatie [Office 365-ATP integreren met Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp).

## <a name="campaign-details"></a>Campagne Details

Wanneer u op de naam van een campagne klikt, worden de gegevens van de campagne in een flyout weergegeven.

### <a name="campaign-information"></a>Campagne-informatie

Boven in de weergave met campagnegegevens zijn de volgende gegevens van de campagne beschikbaar:

- **Id**: de unieke campagne-id.

- **Begonnen** en **beëindigd**: de begindatum en einddatum van de campagne. Houd er rekening mee dat deze datums mogelijk verder lopen dan de filter datums die u hebt geselecteerd op de pagina overzicht.

- **Impact**: deze sectie bevat de volgende gegevens voor het datumbereik dat u hebt geselecteerd (of die u in de tijdlijn selecteert):
  
  - Het totale aantal geadresseerden.
  - Het aantal berichten dat is verzonden naar het postvak in (dat wordt bezorgd in het postvak in, niet op de map Ongewenste E-mail).
  - Hoeveel gebruikers klikken op de URL-nettolading in het malafide bericht.
  - Howe veel gebruikers hebben de URL bezocht.

- **Targeted**: het percentage zoals berekend door: (het aantal geadresseerden van de campagne in uw organisatie)/(het totale aantal geadresseerden in de campagne voor alle organisaties in de service). Houd er rekening mee dat deze waarde wordt berekend gedurende de hele levensduur van de campagne, en geen invloed heeft op de filter datums.

- Een interactieve tijdlijn van een campagneactiviteit: de tijdlijn toont de activiteiten gedurende de hele levensduur van de campagne. Het gearceerd gebied bevat standaard het datumbereik filter dat u hebt geselecteerd in het overzicht. U kunt klikken en slepen om een specifiek beginpunt en eindpunt te selecteren, <u>waardoor de gegevens die worden weergegeven in het gebied met **impact** en op de rest van de pagina, zoals beschreven in de volgende secties, worden gewijzigd</u>.

U kunt op de titelbalk op de knop **campagne-afschrijven downloaden** ![ campagne klikken ](../../media/download-campaign-write-up-button.png) om de campagne details te downloaden naar een Word-document (standaard met de naam CampaignReport.docx). Dit document bevat details over de volledige levensduur van de campagne (niet alleen de filter datums die u hebt geselecteerd).

![Campagne-informatie](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Campagne stroom

In het midden van de weergave met campagne Details worden belangrijke informatie over de campagne weergegeven in de sectie **stroom** in een horizontaal-stroomdiagram (genaamd een _Sankey_ -diagram). Met deze informatie kunt u inzicht krijgen in de elementen van de campagne en de potentiële impact van uw organisatie.

> [!TIP]
> De informatie die in het **stroom** diagram wordt weergegeven, wordt bepaald door het gearceerde datumbereik in de tijdlijn zoals beschreven in de vorige sectie.

![Campagne details die geen gebruikers-URL klikken](../../media/campaign-details-no-recipient-actions.png)

Als u de muisaanwijzer over een horizontale band in het diagram houdt, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaalde bron-IP, berichten van het bron-IP-adres met het opgegeven afzender domein, enzovoort).

Het diagram bevat de volgende informatie:

- **Ip's van afzender**

- **Zender domeinen**

- **Filter Verdicts**: deze waarden zijn gerelateerd aan de beschikbare Verdicts voor phishing en spam filteren, zoals wordt beschreven in [anti spambericht koppen](anti-spam-message-headers.md). In de volgende tabel vindt u een beschrijving van de beschikbare waarden:

  ****

  |Value|Spam filter verdict|Beschrijving|
  |---|---|---|
  |**Ingesteld**|`SFV:SKN` <br/><br/> `SFV:SKI`|Het bericht is gemarkeerd als niet-spam en/of overgeslagen filters voordat het wordt geëvalueerd door spam te filteren (bijvoorbeeld met een e-mail stroom regel, ook wel een transportregel genoemd).<br/><br/>Het bericht heeft geen spam gefilterd op andere redenen (de afzender en de geadresseerde lijken in dezelfde organisatie).|
  |**Blokkeert**|`SFV:SKS`|Het bericht is gemarkeerd als spam voordat ze worden geëvalueerd via spamfilters (bijvoorbeeld via een e-mail stroom regel).|
  |**Aangetoond**|`SFV:SPM`|Het bericht is gemarkeerd als spam.|
  |**Niet gedetecteerd**|`SFV:NSPM`|Het bericht is gemarkeerd als geen spam via spamfilters.|
  |**Uitgebracht**|`SFV:SKQ`|Het bericht heeft het filteren van spam genegeerd, omdat het is vrijgegeven uit Quarantine.|
  |**Tenant toestaan**<sup>\*</sup>|`SFV:SKA`|Het bericht is overgeslagen op spam filteren vanwege antispam beleidsinstellingen (de afzender bevonden zich bijvoorbeeld in de lijst met toegestane afzenders of toegestane domeinen).|
  |**Tenant blok**<sup>\*\*</sup>|`SFV:SKA`|Het bericht is geblokkeerd door spam te filteren vanwege antispam beleidsinstellingen (de afzender stond in de lijst met toegestane afzenders of toegestane domeinen).|
  |**Gebruiker toestaan**<sup>\*</sup>|`SFV:SFE`|Het bericht is overgeslagen op spam filteren omdat de afzender in de lijst met veilige afzenders van een gebruiker in Outlook.|
  |**Gebruikers blok**<sup>\*\*</sup>|`SFV:BLK`|Het bericht is geblokkeerd door spam te filteren omdat de afzender in de lijst met geblokkeerde afzenders van een gebruiker in Outlook was.|
  |**ZAP**|n/b|[Zero-Hour auto leegmaak actie (ZAP)](zero-hour-auto-purge.md) heeft de actie uitgevoerd op het bezorgde bericht overeenkomstig de instellingen van uw Antispambeleid (verplaatst naar de map Ongewenste e-mail of in quarantaine).|
  |

  <sup>\*</sup> Controleer uw Antispambeleid, omdat het toegestane bericht waarschijnlijk door de dienst werd geblokkeerd.

  <sup>\*\*</sup> Controleer uw Antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst.

- **Bezorgingslocaties**: u wilt waarschijnlijk berichten onderzoeken die daadwerkelijk voor geadresseerden zijn afgeleverd (naar het postvak in of de map Ongewenste e-mail), zelfs als gebruikers niet op de URL van de nettolading in het bericht klikken. U kunt ook de in quarantaine geplaatste berichten verwijderen uit quarantaine. Zie voor meer informatie [Gequarantinee e-mailberichten in EOP](quarantine-email-messages.md).

  - **Map verwijderd**
  - **Drop**
  - **Extern**: de geadresseerde bevindt zich in de on-premises e-mail organisatie in hybride omgevingen.
  - **Mislukt**
  - **Ter**
  - **Postvak in**
  - **Map Ongewenste e-mail**
  - **Quarantaine**
  - **Unknown**

- **URL-klikken**: deze worden beschreven in het volgende gedeelte.

> [!NOTE]
> Op alle lagen met meer dan 10 items worden de bovenste 10 items weergegeven, terwijl de rest in de **andere**lagen bijeen.

#### <a name="url-clicks"></a>URL'S klikken

Wanneer een malafide bericht wordt afgeleverd bij een geadresseerde (het postvak in of de map Ongewenste E-mail), is er altijd een kans dat de gebruiker op de URL van de nettolading klikt. U kunt niet op de URL in een geleverd bericht klikken, maar u moet op de eerste plaats bepalen waarom het malafide bericht is bezorgd bij hun postvak.

Als een gebruiker in het malafide e-mailbericht op de URL van de nettolading heeft geklikt, worden de acties weergegeven in het gebied voor de **URL-klikken** van het diagram in de weergave campagne Details.

- **Ingesteld**

- **BlockPage**: de geadresseerde heeft op de URL van de nettolading geklikt, maar de toegang tot de schadelijke website werd geblokkeerd door het beleid voor [veilige koppelingen](atp-safe-links.md) in de organisatie.

- **BlockPageOverride**: de geadresseerde die in het bericht op de URL van de nettolading hebt geklikt, heeft getrachte ATP-koppelingen geprobeerd ze te stoppen, maar ze kunnen het blok negeren. U moet uw beleid voor [veilige koppelingen](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers de verdict voor veilige koppelingen mogen negeren en doorgaan naar de schadelijke website.

- **PendingDetonationPage**: veilige bijlagen voor ATP wordt geopend met het openen van de URL van de nettolading in een virtuele computeromgeving, zodat u kunt zien wat er gebeurt.

- **PendingDetonationPageOverride**: de geadresseerde mag de detonatie procedure overschrijven en de URL openen zonder te hoeven wachten tot de resultaten.

### <a name="tabs"></a>Tabvolgorde

Op de tabbladen in de weergave campagne Details kunt u de campagne verder onderzoeken.

> [!TIP]
> De informatie die wordt weergegeven op de tabbladen, wordt bepaald door het gearceerde datumbereik op de tijdlijn, zoals beschreven in de sectie [campagnegegevens](#campaign-information) .

- **URL-klikken**: als gebruikers niet op de URL van de nettolading in het phishingberichten klikken, is dit gedeelte leeg. Als een gebruiker op de URL kon klikken, worden de volgende waarden ingevuld:

  - **Aanmeldings**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Klik op tijd**
  - **Klik op Verdict**

- **Ip's van afzender**

  - **IP van afzender**<sup>\*</sup>
  - **Totaal aantal**
  - **Postvak in**
  - **Niet in Postvak in**
  - **SPF doorgegeven**: de afzender is geauthenticeerd door het [beleidsraamwerk voor verzenders (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md). Een afzender die SPF valideert, geeft aan dat de afzender niet is geverifieerd, of dat het bericht een vervalste afzender is.

- **Afzenders**

  - **Afzender**: dit is het werkelijke adres van de afzender in de SMTP-e-mail van de opdracht, wat niet het is: een e-mailadres dat gebruikers zien in hun e-mailclients.
  - **Totaal aantal**
  - **Postvak in**
  - **Niet in Postvak in**
  - **Dkim doorgegeven**: de afzender is geverifieerd door de [domein sleutels, die e-mail (dkim) heeft geïdentificeerd](support-for-validation-of-dkim-signed-messages.md). Een afzender die geen DKIM-validatie geeft, geeft aan dat de afzender niet is geverifieerd, of dat het bericht een vervalste afzender is.
  - **DMARC doorgegeven**: de afzender is geverifieerd door [verificatie op basis van een domein op basis van een berichtverificatie, rapportering en conformiteit (DMARC)](use-dmarc-to-validate-email.md). Een afzender die geen DMARC-validatie geeft, geeft aan dat de afzender niet is geverifieerd, of dat het bericht een vervalste afzender is.

- **Stukken**

  - **Namen**
  - **SHA256**
  - **Familie van malware**
  - **Totaal aantal**

- **URL**

  - **URL**<sup>\*</sup>
  - **Totaal aantal**

<sup>\*</sup> Als u op deze waarde klikt, wordt een nieuwe flyout geopend met meer informatie over het opgegeven item (gebruiker, URL, etc.) boven aan de weergave campagne Details. Als u wilt teruggaan naar de weergave met campagnegegevens, klikt u op **gereed** in de vervolgmenu nieuw.

### <a name="buttons"></a>Hardwareknoppen

Met de knoppen in de weergave campagne Details kunt u de kracht van de bedreigings Verkenner gebruiken om de campagne verder te onderzoeken.

- **Campagne verkennen**: Hiermee opent u een nieuw tabblad Zoeken in de bedreiging van een nieuwe bedreiging met de waarde van de **campagne-id** als het zoekfilter.

- **Berichten in Postvak in verkennen**: Hiermee opent u een nieuw Zoek tabblad van de bedreigings Verkenner met behulp van de **campagne-id** en locatie van de **geadresseerde: Postvak in** als zoekfilter.
