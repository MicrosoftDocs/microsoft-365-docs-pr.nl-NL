---
title: Campagneweergaven in ATP
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
ms.openlocfilehash: fe443c43fa5cea8ec6e3e1c0bc5ee5307b5c28f6
ms.sourcegitcommit: 9ee1261c405f82b49c62390a25dfdea23340d644
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/06/2020
ms.locfileid: "45039451"
---
# <a name="campaign-views-in-atp"></a>Campagneweergaven in ATP

Campaign Views is een functie in Advanced Threat Protection (ATP) in het Security & Compliance Center dat phishing-aanvallen in de service identificeert en categoriseert. Campagneweergaven kunnen u helpen om:

- Onderzoek en reageer efficiënt op phishing-aanvallen.

- Beter begrijpen van de omvang van de aanval.

- Toon waarde aan besluitvormers.

Met campagneweergaven kun je het grote plaatje van een aanval sneller en completer zien dan welke mens dan ook.

## <a name="what-is-a-campaign"></a>Wat is een campagne?

Een campagne is een gecoördineerde e-mailaanval tegen een of meer organisaties. E-mailaanvallen die referenties en bedrijfsgegevens stelen, zijn een grote en lucratieve industrie. Naarmate technologieën toenemen in een poging om aanvallen te stoppen, aanvallers wijzigen hun methoden in een poging om blijvend succes te garanderen.

Microsoft maakt gebruik van de enorme hoeveelheden anti-phishing, anti-spam en anti-malware gegevens in de hele service om te helpen bij het identificeren van campagnes. We analyseren en classificeren de aanvalsinformatie op basis van verschillende factoren. Bijvoorbeeld:

- **Aanvalsbron**: De bron-IP-adressen en e-maildomeinen van afzenders.

- **Eigenschappen van het bericht aan te vallen:** de inhoud, stijl en toon van de berichten.

- **Ontvangers van aanvallen**: geadresseerdedomeinen, geadresseerde functiefuncties (beheerders, leidinggevenden, enz.), bedrijfstypen (groot, klein, openbaar, privé, enz.) en bedrijfstakken.

- **Aanval payload:** Kwaadaardige links, bijlagen, of andere payloads in de berichten.

Een campagne kan van korte duur zijn, of kan meerdere dagen, weken of maanden met actieve en inactieve perioden omvatten. Er kan een campagne worden gestart tegen uw specifieke organisatie of uw organisatie maakt mogelijk deel uit van een grotere campagne voor meerdere bedrijven.

## <a name="campaign-views-the-security--compliance-center"></a>Campagne bekijkt het Security & Compliance Center

Campagneweergaven zijn beschikbaar in het [Security & Compliance Center](https://protection.office.com) bij Threat **management** \> **Campaigns**, of rechtstreeks op <https://protection.office.com/campaigns> .

![Overzicht van campagnes in het Security & Compliance Center](../../media/campaigns-overview.png)

Je ook campagneweergaven bekijken via:

- **Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Campagnes**

- **Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Alle e-mail** \> **Tabblad Campagne**

- **Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Phish Phish** \> **Tabblad Campagne**

- **Bedreigingsbeheer** \> **Explorer** \> **Bekijken** \> **Malware** \> **Tabblad Campagne**

Als u toegang wilt krijgen tot campagneweergaven, moet u lid zijn van de rolgroepen **Organisatiebeheer,** **Beveiligingsbeheerder**of **Beveiligingslezer** in het Security & Compliance Center. Zie [Machtigingen in het Beveiligings- & compliancecentrum](permissions-in-the-security-and-compliance-center.md) voor meer informatie.

## <a name="campaigns-overview"></a>Overzicht van campagnes

Op de overzichtspagina vindt u informatie over alle campagnes.

Op het **tabblad** Campagne toont het gebied **Campagnetype** een staafgrafiek met het aantal geadresseerden per dag. Standaard toont de grafiek zowel **Phish-** als **malwaregegevens.**

> [!TIP]
> Als u geen campagnegegevens ziet, probeert u het datumbereik of de [filters](#filters-and-settings)te wijzigen.

De rest van de overzichtspagina bevat de volgende informatie op het tabblad **Campagne:**

- **Naam**

- **Voorbeeldonderwerp**: De onderwerpregel van een van de berichten in de campagne. Houd er rekening mee dat alle berichten in de campagne niet noodzakelijkerwijs hetzelfde onderwerp hebben.

- **Doel:** het percentage zoals berekend door: (het aantal campagneontvangers in uw organisatie) / (het totale aantal ontvangers in de campagne voor alle organisaties in de service). Deze waarde geeft de mate aan waarin de campagne specifiek is gericht op uw organisatie (een hogere waarde) versus gericht op andere organisaties in de service (een lagere waarde).

- **Type**: Deze waarde is **Phish** of **Malware**.

- **Subtype**: Deze waarde bevat meer details over de campagne. Bijvoorbeeld:

  - **Phish**: Waar beschikbaar, het merk dat wordt geprofraakt door deze campagne. Bijvoorbeeld `Microsoft` , `365` , , , `Unknown` of `Outlook` `DocuSign` .

  - **Malware**: Bijvoorbeeld, `HTML/PHISH` of `HTML/<MalwareFamilyName>` .

Waar beschikbaar, het merk dat wordt geprofraseerd door deze campagne. Wanneer de detectie wordt aangedreven door ATP-technologie, wordt het voorvoegsel **ATP-** toegevoegd aan de subtypewaarde.

- **Ontvangers**: het aantal gebruikers dat het doelwit was van deze campagne.

- **Inbox:** het aantal gebruikers dat berichten van deze campagne heeft ontvangen in hun Postvak IN (niet geleverd aan hun map Ongewenste e-mail).

- **Geklikt**: het aantal gebruikers dat op de URL heeft geklikt of de bijlage in het phishingbericht heeft geopend.

- **Klikfrequentie**: Het percentage zoals berekend door "**Geklikt**  /  **Postvak IN**". Deze waarde is een indicator van de effectiviteit van de campagne en of de ontvangers het bericht als phishing hebben kunnen identificeren en te voorkomen dat ze op de URL van de payload klikken.

  Houd er rekening mee dat deze waarde niet wordt gebruikt in malwarecampagnes.

- **Bezocht :** Hoeveel gebruikers eigenlijk maakte het door naar de payload website. Als er **geklikte** waarden zijn, maar veilige links de toegang tot de website hebben geblokkeerd, is deze waarde nul.

Het tabblad **Campagneoorsprong** toont de berichtbronnen op een kaart van de wereld.

### <a name="filters-and-settings"></a>Filters en instellingen

Boven aan de pagina Campagneweergaven staan verschillende filter- en query-instellingen om u te helpen specifieke campagnes te vinden en te isoleren.

![Campagnefilters](../../media/campaign-filters-and-settings.png)

De meest elementaire filtering die u doen is de begindatum/tijd en de einddatum/tijd.

Als u de weergave verder wilt filteren, u één eigenschap met meerdere waarden filteren door op de knop **Campagnetype** te klikken, uw selectie te maken en vervolgens op **Vernieuwen**te klikken.

De beschikbare campagne-eigenschappen worden beschreven in de volgende lijst:

- Basic

  - **Campagnetype**: Selecteer **malware** of **Phish**. Het wissen van de selecties heeft hetzelfde resultaat als het selecteren van beide.
  - **Campagnenaam**
  - **Campagne subtype**
  - **Afzender**
  - **Geadresseerden**
  - **Afzenderdomein**
  - **Onderwerp**
  - **Bestandsnaam voor bijlagen**
  - **Malware familie**
  - **Leveringsactie**
  - **Detectietechnologie**
  - **Tags**
  - **Systeemoverschrijvingen**

- Geavanceerde

  - **Internetbericht-id**: beschikbaar in het kopveld **Bericht-ID** in de berichtkop. Een voorbeeldwaarde is `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (let op de hoekhaakjes).
  
  - **Netwerkbericht-ID:** een GUID-waarde die beschikbaar is in het kopveld **X-MS-Exchange-Organization-Network-Message-Id** in de berichtkop.
  
  - **IP-adres van afzender**
  
  - **Bijlage SHA256**: Als u de SHA256-hashwaarde van een bestand in Windows wilt zoeken, voert u de volgende opdracht uit in een opdrachtprompt: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  
  - **Cluster-id**
  
  - **Waarschuwingsbeleids-id**

- Urls

  - **URL-domein**
  - **URL-domein en -pad**
  - **Url**
  - **URL-pad**
  - **Klik op vonnis**

Voor meer geavanceerde filtering, inclusief filtering op meerdere eigenschappen, u op de **knop Geavanceerd filter** klikken om een query te maken. Dezelfde campagne-eigenschappen zijn beschikbaar, maar met de volgende verbeteringen:

- U op **Een voorwaarde toevoegen** klikken om meerdere voorwaarden te selecteren.
- U de **operator And** or **Or** kiezen tussen de voorwaarden.
- U het item **Voorwaardegroep** onder aan de lijst met voorwaarden selecteren om complexe samengestelde voorwaarden te vormen.

Als u klaar bent, klikt u op de knop **Query.**

Nadat u een basis- of geavanceerd filter hebt gemaakt, u het opslaan door **query opslaan** of Query **opslaan als**. Wanneer u later terugkeert naar campagneweergaven, u een opgeslagen filter laden door op **opgeslagen query-instellingen**te klikken.

Als u de grafiek of de lijst met campagnes wilt exporteren, klikt u op **Exporteren** en selecteert u **Grafiekgegevens exporteren** of **campagnelijst exporteren**.

Als u een Microsoft Defender ATP-abonnement hebt, u op **WDATP** klikken om de campagnegegevens te koppelen of los te koppelen met Microsoft Defender ATP. Zie [Office 365 ATP integreren met Microsoft Defender ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/integrate-office-365-ti-with-wdatp)voor meer informatie.

## <a name="campaign-details"></a>Campagnegegevens

Wanneer u op de naam van een campagne klikt, worden de campagnegegevens weergegeven in een flyout.

### <a name="campaign-information"></a>Campagne-informatie

Boven aan de campagnedetailsweergave is de volgende campagne-informatie beschikbaar:

- **ID**: De unieke campagne-id.

- **Gestart** en **beëindigd:** de begin- en einddatum van de campagne. Houd er rekening mee dat deze datums verder kunnen reiken dan uw filterdatums die u hebt geselecteerd op de overzichtspagina.

- **Impact**: deze sectie bevat de volgende gegevens voor het datumbereikfilter dat u hebt geselecteerd (of dat u selecteert in de tijdlijn):
  
  - Het totale aantal ontvangers.
  - Het aantal berichten dat inbox was (dat wil zeggen, geleverd aan het Postvak IN, niet naar de map Ongewenste e-mail).
  - Hoeveel gebruikers klikten op de URL payload in het phishing-bericht.
  - Hoeveel gebruikers hebben de URL bezocht.

- **Doel:** het percentage zoals berekend door: (het aantal campagneontvangers in uw organisatie) / (het totale aantal ontvangers in de campagne voor alle organisaties in de service). Houd er rekening mee dat deze waarde wordt berekend over de gehele levensduur van de campagne en dat de filterdatums niet worden gewijzigd.

- Een interactieve tijdlijn van campagneactiviteit: de tijdlijn toont activiteit gedurende de gehele levensduur van de campagne. Standaard bevat het gearceerde gebied het datumbereikfilter dat u in het overzicht hebt geselecteerd. U klikken en slepen om een specifiek begin- en eindpunt te selecteren, <u>waarin de gegevens worden gewijzigd die worden weergegeven in het gebied **Impact** en op de rest van de pagina zoals beschreven in de volgende secties</u>.

Klik op de titelbalk op het **schrijfpictogram campagne downloaden** ![ downloaden om de ](../../media/download-campaign-write-up-button.png) campagnedetails te downloaden naar een Word-document (standaard met de naam CampaignReport.docx). Houd er rekening mee dat dit document details bevat over de gehele levensduur van de campagne (niet alleen de filterdatums die u hebt geselecteerd).

![Campagne-informatie](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Campagnestroom

In het midden van de weergave Campagnedetails worden belangrijke details over de campagne weergegeven in de sectie **Stroom** in een horizontaal stroomdiagram (bekend als een _Sankey-diagram)._ Deze details helpen u om de elementen van de campagne en de mogelijke impact in uw organisatie te begrijpen.

> [!TIP]
> De informatie die wordt weergegeven in het **diagram Stroom** wordt beheerd door het gearceerde datumbereik in de tijdlijn zoals beschreven in de vorige sectie.

![Campagnegegevens die geen URL-klikken van gebruikers bevatten](../../media/campaign-details-no-recipient-actions.png)

Als u over een horizontale band in het diagram beweegt, ziet u het aantal gerelateerde berichten (bijvoorbeeld berichten van een bepaalde bron-IP, berichten van het bron-IP-adres met het opgegeven afzenderdomein, enz.).

Het diagram bevat de volgende informatie:

- **Ip's van afzenders**

- **Afzenderdomeinen**

- **Filter vonnissen:** Deze waarden zijn gerelateerd aan de beschikbare phishing en spam filteren vonnissen zoals beschreven in [Anti-spam bericht headers](anti-spam-message-headers.md). De beschikbare waarden worden beschreven in de volgende tabel:

  ||||
  |---|---|---|
  |**Value**|**Het oordeel van spamfilter**|**Beschrijving**|
  |**Toegestaan**|`SFV:SKN` <br/><br/> `SFV:SKI`|Het bericht is gemarkeerd als geen spam en/of overgeslagen filtering voordat het werd geëvalueerd door spamfilter (bijvoorbeeld door een mailflowregel, ook wel een transportregel genoemd).<br/><br/>Het bericht heeft spamfilters overgeslagen om andere redenen (bijvoorbeeld de afzender en ontvanger lijken zich in dezelfde organisatie te bevindt).|
  |**Geblokkeerd**|`SFV:SKS`|Het bericht is gemarkeerd als spam voordat het werd geëvalueerd door spamfilter (bijvoorbeeld door een mailflowregel).|
  |**Gedetecteerd**|`SFV:SPM`|Het bericht is gemarkeerd als spam.|
  |**Niet gedetecteerd**|`SFV:NSPM`|Het bericht is gemarkeerd als geen spam door spamfiltering.|
  |**Vrijgegeven**|`SFV:SKQ`|Het bericht sloeg spamfiltering over omdat het uit quarantaine is vrijgekomen.|
  |**Tenant toestaan**<sup>\*</sup>|`SFV:SKA`|Het bericht heeft spamfilters overgeslagen vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of de toegestane domeinlijst).|
  |**Tenantblok**<sup>\*\*</sup>|`SFV:SKA`|Het bericht is geblokkeerd door spamfilters vanwege instellingen voor antispambeleid (de afzender stond bijvoorbeeld in de lijst met toegestane afzenders of de toegestane domeinlijst).|
  |**Gebruiker toestaan**<sup>\*</sup>|`SFV:SFE`|Het bericht heeft spamfilters overgeslagen omdat de afzender zich in de lijst Veilige afzenders van een gebruiker in Outlook bevond.|
  |**Gebruikersblok**<sup>\*\*</sup>|`SFV:BLK`|Het bericht is geblokkeerd door spamfilters omdat de afzender zich in de lijst Geblokkeerde afzenders van een gebruiker in Outlook bevond.|
  |**Zap**|N/a|[Zero-hour auto purge (ZAP)](zero-hour-auto-purge.md) heeft actie ondernomen op het geleverde bericht volgens uw antispambeleidsinstellingen (verplaatst naar de map Ongewenste e-mail of in quarantaine geplaatst).|
  |

  <sup>\*</sup>Bekijk uw antispambeleid, omdat het toegestane bericht waarschijnlijk door de service zou zijn geblokkeerd.

  <sup>\*\*</sup>Bekijk uw antispambeleid, omdat deze berichten in quarantaine moeten worden geplaatst en niet moeten worden bezorgd.

- **Leveringslocaties**: U wilt waarschijnlijk berichten onderzoeken die daadwerkelijk aan ontvangers zijn bezorgd (naar de map Postvak IN of de map Ongewenste e-mail), zelfs als gebruikers niet op de URL van de payload in het bericht hebben geklikt. U de in quarantaine geplaatste berichten ook uit quarantaine verwijderen. Zie [EOP in quarantaine geplaatst](quarantine-email-messages.md)voor meer informatie.

  - **Verwijderde map**
  - **Gedaald**
  - **Extern**: De ontvanger bevindt zich in uw on-premises e-mailorganisatie in hybride omgevingen.
  - **Mislukt**
  - **Doorgestuurd**
  - **Inbox**
  - **Ongewenste map**
  - **Quarantaine**
  - **Unknown**

- **URL-klikken**: Deze worden beschreven in de volgende sectie.

> [!NOTE]
> In alle lagen die meer dan 10 items bevatten, worden de top 10 items weergegeven, terwijl de rest is gebundeld in **anderen.**

#### <a name="url-clicks"></a>URL-klikken

Wanneer een phishingbericht wordt bezorgd bij een ontvanger (naar de postvak IN of de map Ongewenste e-mail), is er altijd een kans dat de gebruiker op de URL van de payload klikt. Niet te klikken op de URL in een geleverd bericht is een kleine mate van succes, maar je moet bepalen waarom de phishing-bericht werd geleverd aan hun mailbox in de eerste plaats.

Als een gebruiker op de URL van de payload in het phishingbericht heeft geklikt, worden de acties weergegeven in het gebied met **URL-klikken** van het diagram in de weergave campagnegegevens.

- **Toegestaan**

- **BlockPage**: De ontvanger klikte op de payload-URL, maar de toegang tot de schadelijke website is geblokkeerd door het [ATP Safe Links-beleid](atp-safe-links.md) in uw organisatie.

- **BlockPageOverride**: De ontvanger klikte op de payload-URL in het bericht, ATP Safe Links probeerde ze te stoppen, maar ze mochten het blok overschrijven. U moet uw [beleid voor veilige links](set-up-atp-safe-links-policies.md) onderzoeken om te zien waarom gebruikers het vonnis Veilige links mogen negeren en doorgaan naar de kwaadaardige website.

- **In afwachtingdetonationPage:** ATP Safe Attachments is in het proces van het openen van de payload URL in een virtuele computer omgeving, en zien wat er gebeurt.

- **PendingDetonationPageOverride**: De ontvanger mocht het payload detonatieproces overschrijven en de URL openen zonder te wachten op de resultaten.

### <a name="tabs"></a>Tabbladen

Met de tabbladen in de campagnedetailsweergave u de campagne verder onderzoeken.

> [!TIP]
> De informatie die op de tabbladen wordt weergegeven, wordt beheerd door het gearceerde datumbereik in de tijdlijn zoals beschreven in de sectie [Campagnegegevens.](#campaign-information)

- **URL-klikken**: Als gebruikers niet op de URL van de payload in het phishingbericht hebben geklikt, is deze sectie leeg. Als een gebruiker op de URL heeft kunnen klikken, worden de volgende waarden ingevuld:

  - **Gebruiker**<sup>\*</sup>
  - **Url**<sup>\*</sup>
  - **Kliktijd**
  - **Klik op vonnis**

- **Ip's van afzenders**

  - **IP-adres van afzender**<sup>\*</sup>
  - **Totaal aantal**
  - **Inboxed**
  - **Niet inbox**
  - **SPF geslaagd**: De afzender is geverifieerd door het [Sender Policy Framework (SPF).](how-office-365-uses-spf-to-prevent-spoofing.md) Een afzender die de SPF-validatie niet doorgeeft, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

- **Afzenders**

  - **Afzender**: Dit is het werkelijke afzenderadres in de opdracht SMTP MAIL FROM, dat niet noodzakelijkerwijs het E-mailadres van: e-mailadres is dat gebruikers in hun e-mailclients zien.
  - **Totaal aantal**
  - **Inboxed**
  - **Niet inbox**
  - **DKIM geslaagd**: De afzender is geverifieerd door [Domain Keys Identified Mail (DKIM)](support-for-validation-of-dkim-signed-messages.md). Een afzender die de DKIM-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.
  - **DMARC geslaagd**: De afzender is geverifieerd door [domeinverificatie, rapportage en conformiteit (DMARC).](use-dmarc-to-validate-email.md) Een afzender die de DMARC-validatie niet doorstaat, geeft aan dat de afzender niet is geverifieerd of dat het bericht een legitieme afzender vervalst.

- **Bijlagen**

  - **Bestandsnaam**
  - **SHA256 SHA256**
  - **Malware familie**
  - **Totaal aantal**

- **Url**

  - **Url**<sup>\*</sup>
  - **Totaal aantal**

<sup>\*</sup>Als u op deze waarde klikt, opent u een nieuwe flyout met meer details over het opgegeven item (gebruiker, URL, enz.) boven in de weergave campagnedetails. Als u wilt terugkeren naar de weergave Campagnedetails, klikt u op **Gereed** in de nieuwe flyout.

### <a name="buttons"></a>Knoppen

Met de knoppen in de campagnedetailsweergave u de kracht van Threat Explorer gebruiken om de campagne verder te onderzoeken.

- **Campagne verkennen:** hiermee opent u een nieuw tabblad Bedreigingsverkenner met de waarde **campagne-id** als zoekfilter.

- **Inboxberichten verkennen:** opent een nieuw zoektabblad bedreigingsverkenner met behulp van de **campagne-id** en **de locatie Levering: Postvak IN** als zoekfilter.
