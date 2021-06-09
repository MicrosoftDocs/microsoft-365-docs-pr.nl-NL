---
title: Gebruik Office 365 Content Delivery Network (CDN) met SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: Lees hoe u de Office 365 Content Delivery Network (CDN) kunt gebruiken om de levering van uw SharePoint Online-assets te versnellen.
ms.openlocfilehash: 6819f627d3590cd2739b36cb1bc303f197d6aaa5
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570403"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>De Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online

U kunt de ingebouwde Office 365 Content Delivery Network (CDN) gebruiken om statische assets te hosten om betere prestaties te bieden voor uw SharePoint Online-pagina's. De Office 365 CDN verbetert de prestaties door statische assets dichter bij de browsers te houden waarin ze worden gevraagd, wat helpt om downloads te versnellen en de latentie te verminderen. De Office 365 CDN gebruikt ook het [HTTP/2-protocol](https://en.wikipedia.org/wiki/HTTP/2) voor verbeterde compressie en HTTP-pipelineing. De Office 365 CDN service is opgenomen als onderdeel van uw SharePoint Online-abonnement.

> [!NOTE]
> De Office 365 CDN is alleen beschikbaar voor tenants in de **productiecloud** (wereldwijd). Tenants in de amerikaanse overheid, China en Duitsland clouds ondersteunen momenteel de Office 365 CDN.

De Office 365 CDN bestaat uit meerdere CDN's waarmee u statische assets op meerdere locaties of _origins_ kunt hosten en deze kunt gebruiken vanuit globale snelle netwerken. Afhankelijk van het type inhoud dat u wilt hosten in  de Office 365 CDN, kunt u openbare origins, **privé-origins** of beide toevoegen. Zie [Kiezen of elke origin openbaar](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) of privé moet zijn voor meer informatie over het verschil tussen openbare en private origins.

![Office 365 CDN conceptueel diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN conceptueel diagram")

Als u al bekend bent met de manier waarop CDN's werken, hoeft u slechts een paar stappen uit te voeren om de Office 365 CDN voor uw tenant in te stellen. In dit onderwerp wordt beschreven hoe. Lees verder voor informatie over hoe u aan de slag kunt met het hosten van uw statische assets.

> [!TIP]
> Er zijn andere door Microsoft gehoste CDN's die kunnen worden gebruikt met Office 365 voor gespecialiseerde gebruiksscenario's, maar worden niet besproken in dit onderwerp omdat ze buiten het bereik van de Office 365 CDN. Zie Andere [Microsoft CDN's](content-delivery-networks.md#other-microsoft-cdns)voor meer informatie.

 **Ga terug naar [Netwerkplanning en prestatieafstemming voor Office 365.](./network-planning-and-performance.md)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Overzicht van het werken met de Office 365 CDN in SharePoint Online

Als u de Office 365 CDN voor uw organisatie wilt instellen, volgt u de volgende basisstappen:

+ [Plannen voor implementatie van de Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Bepaal welke statische assets u wilt hosten op de CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bepaal waar u uw activa wilt opslaan.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Deze locatie kan een SharePoint site, bibliotheek of map zijn en wordt een _origin genoemd._
  + [Kies of elke origin openbaar of privé moet zijn.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) U kunt meerdere origins van zowel openbare als privétypen toevoegen.

+ De CDN instellen en configureren met PowerShell of SharePoint Online CLI

  + [De CDN instellen en configureren met de SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [De CDN instellen en configureren met PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [De CDN instellen en configureren met de Office 365 CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Wanneer u deze stap voltooit, hebt u het volgende:

  + De CDN voor uw organisatie ingeschakeld.
  + U hebt uw origins toegevoegd, die elke origin als openbaar of privé identificeren.

Nadat u klaar bent met instellen, kunt u [de](use-microsoft-365-cdn-with-spo.md#CDNManage) Office 365 CDN in de tijd beheren door:
  
+ Activa toevoegen, bijwerken en verwijderen
+ Origins toevoegen en verwijderen
+ Beleidsregels CDN configureren
+ Als dat nodig is, kunt u de CDN

Zie Ten slotte [Uw CDN gebruiken voor](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) meer informatie over toegang tot uw CDN activa van zowel openbare als privé-origins.

Zie [Problemen oplossen Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) voor richtlijnen voor het oplossen van veelvoorkomende problemen.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Plannen voor implementatie van de Office 365 CDN

Voordat u de Office 365 CDN voor uw Office 365 tenant implementeert, moet u rekening houden met de volgende factoren als onderdeel van uw planningsproces.

  + [Bepalen welke statische assets u wilt hosten op de CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bepalen waar u uw assets wilt opslaan](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Kies of elke origin openbaar of privé moet zijn](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Bepalen welke statische assets u wilt hosten op de CDN

CdN's zijn over het algemeen het meest effectief voor het hosten van _statische_ activa of activa die niet vaak veranderen. Een goede vuistregel is om bestanden te identificeren die voldoen aan bepaalde of al deze voorwaarden:

+ Statische bestanden die zijn ingesloten in een pagina (zoals scripts en afbeeldingen) die een aanzienlijk incrementeel effect kunnen hebben op laadtijden van pagina's
+ Grote bestanden, zoals uitvoerbare bestanden en installatiebestanden
+ Resourcebibliotheken die clientcode ondersteunen

Kleine bestanden die herhaaldelijk worden aangevraagd, zoals siteafbeeldingen en scripts, kunnen bijvoorbeeld de prestaties van siterendering aanzienlijk verbeteren en de belasting op uw SharePoint Online-sites stapsgewijs verminderen wanneer u ze toevoegt aan een CDN origin. Grotere bestanden, zoals installatieuitvoerbare bestanden, kunnen worden gedownload van de CDN, wat een positief effect heeft op de prestaties en de belasting op uw SharePoint Online-site, zelfs als ze niet zo vaak worden gebruikt.

Prestatieverbetering per bestand is afhankelijk van een groot aantal factoren, waaronder de nabijheid van de client tot het dichtstbijzijnde CDN eindpunt, tijdelijke voorwaarden op het lokale netwerk, enzovoort. Veel statische bestanden zijn vrij klein en kunnen in minder dan Office 365 worden gedownload. Een webpagina kan echter veel ingesloten bestanden bevatten met een cumulatieve downloadtijd van enkele seconden. Als u deze bestanden vanuit de CDN kunt u de totale laadtijd van de pagina aanzienlijk verminderen. Zie [Welke prestatiewinst levert een CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) voor een voorbeeld.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Bepalen waar u uw assets wilt opslaan

De CDN haalt uw activa op van een locatie die een origin _wordt genoemd._ Een origin kan een SharePoint site, documentbibliotheek of map zijn die toegankelijk is via een URL. U hebt grote flexibiliteit wanneer u origins voor uw organisatie opgeeft. U kunt bijvoorbeeld meerdere origins of één origin opgeven waar u al uw CDN wilt plaatsen. U kunt ervoor kiezen om zowel openbare als persoonlijke origins voor uw organisatie te hebben. De meeste organisaties kiezen ervoor om een combinatie van de twee te implementeren.

U kunt nieuwe containers maken voor uw origins, zoals mappen of documentbibliotheken, en bestanden toevoegen die u beschikbaar wilt maken vanaf de CDN. Dit is een goede methode als u een specifieke set activa hebt die u beschikbaar wilt hebben in de CDN en u de set CDN-assets wilt beperken tot alleen die bestanden in de container.

U kunt ook een bestaande siteverzameling, site, bibliotheek of map configureren als origin, zodat alle in aanmerking komende activa in de container beschikbaar zijn vanaf de CDN. Voordat u een bestaande container als origin toevoegt, is het belangrijk dat u op de hoogte bent van de inhoud en machtigingen, zodat u activa niet per ongeluk blootstelt aan anonieme toegang of niet-geautoriseerde gebruikers.

U kunt een _CDN definiëren om_ inhoud in uw origins uit te sluiten van de CDN. CDN beleidsregels sluiten activa in openbare of privé-origins uit op basis van kenmerken zoals bestandstype en _siteclassificatie_ en worden toegepast op alle origins van het CdnType (privé of openbaar) dat u opgeeft in het beleid.  Als u bijvoorbeeld een privé-origin toevoegt die bestaat uit een site die meerdere subsites bevat, kunt u een beleid definiëren om sites uit te sluiten die zijn gemarkeerd als Vertrouwelijk, zodat inhoud van sites met die classificatie wordt toegepast, niet wordt gebruikt vanaf de CDN.  Het beleid is van toepassing op inhoud van _alle_ persoonlijke origins die u hebt toegevoegd aan de CDN.
  
Houd er rekening mee dat hoe groter het aantal origins, hoe groter de impact op de tijd die de service CDN om aanvragen te verwerken. U wordt aangeraden het aantal origins zo veel mogelijk te beperken.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Kies of elke origin openbaar of privé moet zijn

Wanneer u een origin identificeert, geeft u aan of deze openbaar of _privé_ moet _worden gemaakt._ Toegang tot CDN activa in openbare origins is anoniem en CDN inhoud in privé-origins wordt beveiligd door dynamisch gegenereerde tokens voor meer beveiliging. Ongeacht welke optie u kiest, Microsoft doet al het zware werk voor u als het gaat om het beheer van de CDN zelf. U kunt ook later van gedachten veranderen nadat u de CDN hebt ingesteld en uw origins hebt geïdentificeerd.

Openbare en private opties bieden vergelijkbare prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen.

**Openbare** origins binnen de Office 365 CDN zijn anoniem toegankelijk en gehoste assets kunnen worden gebruikt door iedereen die de URL van het activum heeft. Omdat toegang tot inhoud in openbare origins anoniem is, moet u deze alleen gebruiken om niet-gevoelige algemene inhoud in de cache op te slaan, zoals JavaScript-bestanden, scripts, pictogrammen en afbeeldingen.

**Privé-origins** binnen de Office 365 CDN bieden persoonlijke toegang tot gebruikersinhoud, zoals SharePoint Online-documentbibliotheken, sites en eigen afbeeldingen. Toegang tot inhoud in privé-origins wordt beveiligd door dynamisch gegenereerde tokens, zodat deze alleen toegankelijk is voor gebruikers met machtigingen voor de oorspronkelijke documentbibliotheek of opslaglocatie. Privé-origins in de Office 365 CDN kunnen alleen worden gebruikt voor SharePoint Online-inhoud en u hebt alleen toegang tot activa in privé-origins via omleiding vanuit uw SharePoint Online-tenant.

U kunt meer informatie lezen over hoe CDN toegang tot activa in een persoonlijke origin werkt in [Assets gebruiken in private origins.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Kenmerken en voordelen van het hosten van activa in openbare origins
  
+ Activa die in een openbare origin worden getoond, zijn anoniem toegankelijk voor iedereen.
    > [!IMPORTANT]
    > U mag nooit resources plaatsen die gebruikersgegevens bevatten of die als gevoelig voor uw organisatie worden beschouwd in een openbare origin.

+ Als u een activum uit een openbare origin verwijdert, is het activum mogelijk nog maximaal 30 dagen beschikbaar in de cache. De koppelingen naar het activum worden binnen 15 minuten CDN ongeldig.

+ Wanneer u stijlbladen (CSS-bestanden) host in een openbare origin, kunt u relatieve paden en URL's binnen de code gebruiken. Dit betekent dat u kunt verwijzen naar de locatie van achtergrondafbeeldingen en andere objecten ten opzichte van de locatie van het activum dat de activum aanroept.

+ Hoewel u de URL van een openbare origin kunt maken, moet u voorzichtig te werk gaan en ervoor zorgen dat u de context-eigenschap pagina gebruikt en de richtlijnen volgt om dit te doen. De reden hiervoor is dat als de toegang tot de CDN niet beschikbaar wordt, de URL niet automatisch wordt opgelost voor uw organisatie in SharePoint Online en kan leiden tot verbroken koppelingen en andere fouten. De URL kan ook worden gewijzigd. Daarom moet de URL niet alleen hard worden gecodeerd naar de huidige waarde.

+ De standaardbestandstypen die zijn opgenomen voor openbare origins zijn .css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff en .woff2. U kunt extra bestandstypen opgeven.

+ U kunt een beleid configureren om activa uit te sluiten die zijn geïdentificeerd met siteclassificaties die u opgeeft. U kunt er bijvoorbeeld voor kiezen om alle activa uit te sluiten die zijn gemarkeerd als 'vertrouwelijk' of 'beperkt', zelfs als ze een toegestaan bestandstype zijn en zich in een openbare origin bevinden.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Kenmerken en voordelen van hostingactiva in privé-origins

+ Privé-origins kunnen alleen worden gebruikt voor SharePoint onlineactiva.

+ Gebruikers hebben alleen toegang tot de assets van een persoonlijke origin als ze machtigingen hebben voor toegang tot de container. Anonieme toegang tot deze activa wordt voorkomen.

+ Activa in privé-origins moeten worden verwezen vanuit de SharePoint Online-tenant. Directe toegang tot privé-CDN werkt niet.

+ Als u een activum uit de privé-origin verwijdert, is het activum mogelijk nog maximaal een uur beschikbaar in de cache. We zullen echter binnen 15 minuten na de verwijdering van het activum koppelingen naar het activum in CDN ongeldig maken.

+ De standaardbestandstypen die zijn opgenomen voor privé-origins zijn .gif, .ico, .jpeg, .jpg, .js en .png. U kunt extra bestandstypen opgeven.

+ Net als bij openbare origins kunt u een beleid configureren om activa uit te sluiten die zijn geïdentificeerd met siteclassificaties die u opgeeft, zelfs als u jokertekens gebruikt om alle activa in een map of documentbibliotheek op te nemen.

Zie Content [Delivery Networks](content-delivery-networks.md)voor meer informatie over Office 365 CDN, algemene CDN concepten en andere Microsoft CDN's die u kunt gebruiken met uw Office 365 tenant.

### <a name="default-cdn-origins"></a>Standaard CDN origins

Tenzij u anders opgeeft, Office 365 u een aantal standaard origins voor u in wanneer u de Office 365 CDN. Als u er in eerste instantie voor kiest om deze niet in te stellen, kunt u deze origins toevoegen nadat u de installatie hebt voltooid. Tenzij u de gevolgen begrijpt van het overslaan van de instelling van standaard origins en hiervoor een specifieke reden hebt, moet u toestaan dat deze worden gemaakt wanneer u de CDN.
  
Standaardinstellingen CDN privé-origins:
  
+ \*/userphoto.aspx
+ \*/siteassets

Standaard openbare CDN origins:
  
+ \*/masterpage
+ \*/stijlbibliotheek
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ is een standaard openbare origin die in december 2017 is toegevoegd aan de Office 365 CDN service. Deze origin moet aanwezig zijn om te kunnen SharePoint Framework oplossingen in de CDN werken. Als u de Office 365 CDN hebt ingeschakeld vóór december 2017 of als u de installatie van standaard origins hebt overgeslagen toen u de CDN inschakelen, kunt u deze origin handmatig toevoegen. Zie Mijn [webonderdeel aan de clientzijde of](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)SharePoint Framework oplossing werkt niet voor meer informatie.

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>De Office 365 CDN instellen en configureren met de SharePoint Online Management Shell

Voor de procedures in deze sectie moet u de SharePoint Online Management Shell gebruiken om verbinding te maken met SharePoint Online. Zie voor instructies [Verbinding maken SharePoint Online PowerShell.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

Voltooi deze stappen voor het instellen en configureren van de CDN om uw assets te hosten in SharePoint Online met behulp van SharePoint Online Management Shell.

<details>
  <summary>Klik om uit te vouwen</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Uw organisatie in staat stellen de Office 365 CDN

Voordat u wijzigingen aan de tenantinstellingen CDN, moet u de huidige status van de privé-CDN in uw Office 365 tenant. Verbinding maken naar uw tenant met behulp van SharePoint Online Management Shell:

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Gebruik nu **de cmdlet Get-SPOTenantCdnEnabled** om de CDN statusinstellingen van de tenant op te halen:

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

De status van de CDN voor het opgegeven CdnType wordt naar het scherm uitgevoerd.

Gebruik de **cmdlet Set-SPOTenantCdnEnabled** om uw organisatie in staat te stellen de Office 365 CDN. U kunt uw organisatie in staat stellen om openbare origins, privé-origins of beide tegelijk te gebruiken. U kunt de CDN ook zo configureren dat de instelling van standaard origins wordt overgeslagen wanneer u deze inschakelen. U kunt deze origins altijd later toevoegen, zoals in dit onderwerp wordt beschreven.
  
In Windows PowerShell voor SharePoint Online:

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als privé-origins kan gebruiken, typt u de volgende opdracht:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Als u wilt dat uw organisatie zowel openbare als persoonlijke origins kan gebruiken, maar het instellen van de standaard origins wilt overslaan, typt u de volgende opdracht:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Zie [Standaard CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de origins die standaard zijn ingericht wanneer u de Office 365 CDN inschakelen, en de mogelijke impact van het overslaan van de instelling van standaard origins.

Als u wilt dat uw organisatie openbare origins kan gebruiken, typt u de volgende opdracht:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Als u wilt dat uw organisatie persoonlijke origins kan gebruiken, typt u de volgende opdracht:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Zie [Set-SPOTenantCdnEnabled voor](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)meer informatie over deze cmdlet.

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>De lijst met bestandstypen wijzigen die u wilt opnemen in de Office 365 CDN (Optioneel)

> [!TIP]
> Wanneer u bestandstypen definieert met de **cmdlet Set-SPOTenantCdnPolicy,** overschrijft u de lijst die momenteel is gedefinieerd. Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om te kijken welke bestandstypen al zijn toegestaan en deze samen met de nieuwe bestandstypen in de lijst op te nemen.
  
Gebruik de **cmdlet Set-SPOTenantCdnPolicy** om statische bestandstypen te definiëren die kunnen worden gehost door openbare en private origins in de CDN. Standaard zijn veelgebruikte activatypen toegestaan, zoals .css, .gif, .jpg en .js.

In Windows PowerShell voor SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Als u bijvoorbeeld de CDN css en .png wilt hosten, voert u de opdracht in:

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Gebruik de **cmdlet Get-SPOTenantCdnPolicies** om te zien welke bestandstypen momenteel door de CDN zijn toegestaan:

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Zie Set-SPOTenantCdnPolicy and Get-SPOTenantCdnPolicies [(Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) en [Get-SPOTenantCdnPolicies)](/powershell/module/sharepoint-online/)voor meer informatie over deze cmdlets.

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>De lijst met siteclassificaties wijzigen die u wilt uitsluiten van de Office 365 CDN (Optioneel)

> [!TIP]
> Wanneer u siteclassificaties uitsluit met de **cmdlet Set-SPOTenantCdnPolicy,** overschrijft u de lijst die momenteel is gedefinieerd. Als u extra siteclassificaties wilt uitsluiten, gebruikt u de cmdlet eerst om te kijken welke classificaties al zijn uitgesloten en voegt u deze vervolgens samen met de nieuwe toe.

Gebruik de **cmdlet Set-SPOTenantCdnPolicy** om siteclassificaties uit te sluiten die u niet beschikbaar wilt maken in de CDN. Standaard worden geen siteclassificaties uitgesloten.

In Windows PowerShell voor SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Als u wilt zien welke siteclassificaties momenteel zijn beperkt, gebruikt u de **cmdlet Get-SPOTenantCdnPolicies:**

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.

De _eigenschap IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanaf de CDN.

> [!NOTE]
> De standaardbestandsextensies verschillen tussen openbaar en privé.

De _eigenschap ExcludeRestrictedSiteClassifications_ bevat de siteclassificaties die u wilt uitsluiten van de CDN. U kunt bijvoorbeeld sites uitsluiten die zijn gemarkeerd als **Vertrouwelijk,** zodat inhoud van sites met die classificatie die is toegepast, niet wordt gebruikt vanaf de CDN.

De _eigenschap ExcludeIfNoScriptDisabled_ sluit inhoud uit van de CDN op basis van de _noScript-kenmerkinstellingen_ op siteniveau. Het kenmerk _NoScript_ is standaard ingesteld op **Ingeschakeld voor** _moderne_ sites en **Uitgeschakeld** voor _klassieke_ sites. Dit is afhankelijk van uw tenantinstellingen.

Zie Set-SPOTenantCdnPolicy and Get-SPOTenantCdnPolicies [(Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) en [Get-SPOTenantCdnPolicies)](/powershell/module/sharepoint-online/)voor meer informatie over deze cmdlets.

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Een origin toevoegen voor uw activa

Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om een origin te definiëren. U kunt meerdere origins definiëren. De origin is een URL die wijst naar een SharePoint of map die de assets bevat die u wilt hosten door de CDN.
  
> [!IMPORTANT]
> U mag nooit resources plaatsen die gebruikersgegevens bevatten of die als gevoelig voor uw organisatie worden beschouwd in een openbare origin.

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

De waarde van _pad_ is het relatieve pad naar de bibliotheek of map die de assets bevat. U kunt jokertekens gebruiken naast relatieve paden. Origins ondersteunt jokertekens die zijn voorbereid op de URL. Op deze manier kunt u origins maken die meerdere sites bespannen. Als u bijvoorbeeld alle assets wilt opnemen in de map met basispagina's voor al uw sites als openbare origin in de CDN, typt u de volgende opdracht:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ De jokertekenmodule * kan alleen worden gebruikt aan het begin van het pad en komt overeen met alle URL-segmenten **/** onder de opgegeven URL.
+ Het pad kan naar een documentbibliotheek, map of site wijzen. Het pad _*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.

U kunt een origin toevoegen met een specifiek relatieve pad. U kunt geen origin toevoegen met het volledige pad.

In dit voorbeeld wordt een persoonlijke origin van de siteassetsbibliotheek op een specifieke site toegevoegd:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In dit voorbeeld wordt een persoonlijke origin van de _map1_ toegevoegd aan de siteactivabibliotheek van de siteverzameling:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Als er een spatie in het pad is, kunt u het pad omringen met dubbele aanhalingstekens of de spatie vervangen door de URL-codering %20. In de volgende voorbeelden wordt een persoonlijke origin van de _map 1_ in de siteactivabibliotheek van de siteverzameling toegevoegd:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.

> [!NOTE]
> In privé-origins moeten activa die vanaf een origin worden gedeeld, een hoofdversie hebben gepubliceerd voordat ze vanaf de CDN.
  
Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Dit kan maximaal 15 minuten duren.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Voorbeeld: Een openbare origin configureren voor uw basispagina's en voor uw stijlbibliotheek voor SharePoint Online

Normaal gesproken worden deze origins standaard voor u ingesteld wanneer u de Office 365 CDN. Als u ze echter handmatig wilt inschakelen, volgt u deze stappen.
  
+ Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de stijlbibliotheek te definiëren als een openbare origin.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de basispagina's te definiëren als een openbare origin.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.

Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Dit kan maximaal 15 minuten duren.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Voorbeeld: Een persoonlijke origin configureren voor uw siteactiva, sitepagina's en publicerende afbeeldingen voor SharePoint Online

+ Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de map met siteactiva te definiëren als een persoonlijke origin.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de map sitepagina's te definiëren als een persoonlijke origin.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om de map met publicatieafbeeldingen te definiëren als een persoonlijke origin.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.

Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Dit kan maximaal 15 minuten duren.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Voorbeeld: Een persoonlijke origin configureren voor een siteverzameling voor SharePoint Online

Gebruik de **cmdlet Add-SPOTenantCdnOrigin** om een siteverzameling te definiëren als een persoonlijke origin. Bijvoorbeeld:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Zie [Add-SPOTenantCdnOrigin (Add-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)voor meer informatie over deze opdracht en de syntaxis ervan.
  
Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Mogelijk ziet u een _bericht in_ behandeling met configuratie dat wordt verwacht wanneer de SharePoint Online-tenant verbinding maakt met de CDN service. Dit kan maximaal 15 minuten duren.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>De Office 365 CDN

Nadat u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in uw configuratie terwijl u inhoud bij werk of als uw behoeften veranderen, zoals in deze sectie wordt beschreven.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Activa toevoegen, bijwerken of verwijderen uit de Office 365 CDN

Nadat u de installatiestappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande assets bijwerken of verwijderen wanneer u maar wilt. Pas uw wijzigingen aan in de assets in de map of SharePoint bibliotheek die u hebt geïdentificeerd als een origin. Als u een nieuw activum toevoegt, is deze direct beschikbaar via CDN. Als u het activum echter bij werkt, duurt het maximaal 15 minuten voordat de nieuwe kopie wordt doorgegeven en beschikbaar komt in de CDN.
  
Als u de locatie van de origin wilt ophalen, kunt u de **cmdlet Get-SPOTenantCdnOrigins** gebruiken. Zie [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)voor meer informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Een origin verwijderen uit de Office 365 CDN

U kunt de toegang tot een map of bibliotheek SharePoint verwijderen die u hebt geïdentificeerd als een origin. Gebruik hiervoor de **cmdlet Remove-SPOTenantCdnOrigin.**

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Zie [Remove-SPOTenantCdnOrigin (Verwijderen-SPOTenantCdnOrigin)](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)voor meer informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Een origin in de Office 365 CDN

U kunt een origin die u hebt gemaakt niet wijzigen. In plaats daarvan verwijdert u de origin en voegt u een nieuwe toe. Zie Een origin verwijderen [uit de](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) Office 365 CDN en Een origin toevoegen voor uw assets voor [meer informatie.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>De Office 365 CDN

Gebruik de **cmdlet Set-SPOTenantCdnEnabled** om de CDN voor uw organisatie uit te schakelen. Als u zowel de openbare als de privé-origins hebt ingeschakeld voor de CDN, moet u de cmdlet tweemaal uitvoeren, zoals wordt weergegeven in de volgende voorbeelden.
  
Als u het gebruik van openbare origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Als u het gebruik van de privé-origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Zie [Set-SPOTenantCdnEnabled voor](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)meer informatie over deze cmdlet.

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>De Office 365 CDN instellen en configureren met PnP PowerShell

Voor de procedures in deze sectie moet u PnP PowerShell gebruiken om verbinding te maken met SharePoint Online. Zie Aan de slag [met PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started)voor instructies.

Voltooi deze stappen voor het instellen en configureren van de CDN om uw assets te hosten in SharePoint Online met PnP PowerShell.

<details>
  <summary>Klik om uit te vouwen</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Uw organisatie in staat stellen de Office 365 CDN

Voordat u wijzigingen aan de tenantinstellingen CDN, moet u de huidige status van de privé-CDN in uw Office 365 tenant. Verbinding maken met PnP PowerShell naar uw tenant:

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Gebruik nu **de cmdlet Get-PnPTenantCdnEnabled om** de statusinstellingen CDN de tenant op te halen:

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

De status van de CDN voor het opgegeven CdnType wordt naar het scherm uitgevoerd.

Gebruik de **cmdlet Set-PnPTenantCdnEnabled om** uw organisatie in staat te stellen de Office 365 CDN. U kunt uw organisatie inschakelen om tegelijk gebruik te maken van openbare origins, privé-origins of beide. U kunt de CDN ook zo configureren dat de instelling van standaard origins wordt overgeslagen wanneer u deze inschakelen. U kunt deze origins altijd later toevoegen, zoals in dit onderwerp wordt beschreven.
  
In PnP PowerShell:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als privé-origins kan gebruiken, typt u de volgende opdracht:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Als u wilt dat uw organisatie zowel openbare als persoonlijke origins kan gebruiken, maar het instellen van de standaard origins wilt overslaan, typt u de volgende opdracht:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Zie [Standaard CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de origins die standaard zijn ingericht wanneer u de Office 365 CDN inschakelen, en de mogelijke impact van het overslaan van de instelling van standaard origins.

Als u wilt dat uw organisatie openbare origins kan gebruiken, typt u de volgende opdracht:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Als u wilt dat uw organisatie persoonlijke origins kan gebruiken, typt u de volgende opdracht:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Zie [Set-PnPTenantCdnEnabled voor meer informatie over deze cmdlet.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>De lijst met bestandstypen wijzigen die u wilt opnemen in de Office 365 CDN (Optioneel)

> [!TIP]
> Wanneer u bestandstypen definieert met de **cmdlet Set-PnPTenantCdnPolicy,** overschrijft u de momenteel gedefinieerde lijst. Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om te kijken welke bestandstypen al zijn toegestaan en deze samen met de nieuwe bestandstypen in de lijst op te nemen.
  
Gebruik de **cmdlet Set-PnPTenantCdnPolicy** om statische bestandstypen te definiëren die kunnen worden gehost door openbare en private origins in de CDN. Standaard zijn veelgebruikte activatypen toegestaan, zoals .css, .gif, .jpg en .js.

In PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Als u bijvoorbeeld de CDN css en .png wilt hosten, voert u de opdracht in:

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Gebruik de **cmdlet Get-PnPTenantCdnPolicies** om te zien welke bestandstypen momenteel door de CDN zijn toegestaan:

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Zie [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies (Set-PnPTenantCdnPolicy en Get-PnPTenantCdnPolicies)](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>De lijst met siteclassificaties wijzigen die u wilt uitsluiten van de Office 365 CDN (Optioneel)

> [!TIP]
> Wanneer u siteclassificaties uitsluit met de **cmdlet Set-PnPTenantCdnPolicy,** overschrijft u de momenteel gedefinieerde lijst. Als u extra siteclassificaties wilt uitsluiten, gebruikt u de cmdlet eerst om te kijken welke classificaties al zijn uitgesloten en voegt u deze vervolgens samen met de nieuwe toe.

Gebruik de **cmdlet Set-PnPTenantCdnPolicy** om siteclassificaties uit te sluiten die u niet beschikbaar wilt maken in de CDN. Standaard worden geen siteclassificaties uitgesloten.

In PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Als u wilt zien welke siteclassificaties momenteel zijn beperkt, gebruikt u de **cmdlet Get-PnPTenantCdnPolicies:**

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.

De _eigenschap IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanaf de CDN.

> [!NOTE]
> De standaardbestandsextensies verschillen tussen openbaar en privé.

De _eigenschap ExcludeRestrictedSiteClassifications_ bevat de siteclassificaties die u wilt uitsluiten van de CDN. U kunt bijvoorbeeld sites uitsluiten die zijn gemarkeerd als **Vertrouwelijk,** zodat inhoud van sites met die classificatie die is toegepast, niet wordt gebruikt vanaf de CDN.

De _eigenschap ExcludeIfNoScriptDisabled_ sluit inhoud uit van de CDN op basis van de _noScript-kenmerkinstellingen_ op siteniveau. Het kenmerk _NoScript_ is standaard ingesteld op **Ingeschakeld voor** _moderne_ sites en **Uitgeschakeld** voor _klassieke_ sites. Dit is afhankelijk van uw tenantinstellingen.

Zie [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) and [Get-PnPTenantCdnPolicies (Set-PnPTenantCdnPolicy en Get-PnPTenantCdnPolicies)](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Een origin toevoegen voor uw activa

Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om een origin te definiëren. U kunt meerdere origins definiëren. De origin is een URL die wijst naar een SharePoint of map die de assets bevat die u wilt hosten door de CDN.
  
> [!IMPORTANT]
> U mag nooit resources plaatsen die gebruikersgegevens bevatten of die als gevoelig voor uw organisatie worden beschouwd in een openbare origin.

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

De waarde van _pad_ is het relatieve pad naar de bibliotheek of map die de assets bevat. U kunt jokertekens gebruiken naast relatieve paden. Origins ondersteunt jokertekens die zijn voorbereid op de URL. Op deze manier kunt u origins maken die meerdere sites bespannen. Als u bijvoorbeeld alle assets wilt opnemen in de map met basispagina's voor al uw sites als openbare origin in de CDN, typt u de volgende opdracht:

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ De jokertekenmodule * kan alleen worden gebruikt aan het begin van het pad en komt overeen met alle URL-segmenten **/** onder de opgegeven URL.
+ Het pad kan naar een documentbibliotheek, map of site wijzen. Het pad _*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.

U kunt een origin toevoegen met een specifiek relatieve pad. U kunt geen origin toevoegen met het volledige pad.

In dit voorbeeld wordt een persoonlijke origin van de siteactivabibliotheek op een specifieke site toegevoegd:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In dit voorbeeld wordt een persoonlijke origin van de _map1_ toegevoegd aan de siteactivabibliotheek van de siteverzameling:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Als er een spatie in het pad is, kunt u het pad omringen met dubbele aanhalingstekens of de spatie vervangen door de URL-codering %20. In de volgende voorbeelden wordt een persoonlijke origin van de _map 1_ in de siteactivabibliotheek van de siteverzameling toegevoegd:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.

> [!NOTE]
> In privé-origins moeten activa die vanaf een origin worden gedeeld, een hoofdversie hebben gepubliceerd voordat ze vanaf de CDN.
  
Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Dit kan maximaal 15 minuten duren.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Voorbeeld: Een openbare origin configureren voor uw basispagina's en voor uw stijlbibliotheek voor SharePoint Online

Normaal gesproken worden deze origins standaard voor u ingesteld wanneer u de Office 365 CDN. Als u ze echter handmatig wilt inschakelen, volgt u deze stappen.
  
+ Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de stijlbibliotheek te definiëren als een openbare origin.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de basispagina's te definiëren als een openbare origin.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.

Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Dit kan maximaal 15 minuten duren.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Voorbeeld: Een persoonlijke origin configureren voor uw siteactiva, sitepagina's en publicerende afbeeldingen voor SharePoint Online

+ Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de map met siteactiva te definiëren als een persoonlijke origin.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de map sitepagina's te definiëren als een persoonlijke origin.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om de map publicerende afbeeldingen te definiëren als een persoonlijke origin.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.

Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Dit kan maximaal 15 minuten duren.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Voorbeeld: Een persoonlijke origin configureren voor een siteverzameling voor SharePoint Online

Gebruik de **cmdlet Add-PnPTenantCdnOrigin** om een siteverzameling te definiëren als een persoonlijke origin. Bijvoorbeeld:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Zie [Add-PnPTenantCdnOrigin (Add-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis ervan.
  
Wanneer u de opdracht hebt uitgevoerd, synchroniseert het systeem de configuratie in het datacenter. Mogelijk ziet u een _bericht in_ behandeling met configuratie dat wordt verwacht wanneer de SharePoint Online-tenant verbinding maakt met de CDN service. Dit kan maximaal 15 minuten duren.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>De Office 365 CDN

Nadat u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in uw configuratie terwijl u inhoud bij werk of als uw behoeften veranderen, zoals in deze sectie wordt beschreven.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Activa toevoegen, bijwerken of verwijderen uit de Office 365 CDN

Nadat u de installatiestappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande assets bijwerken of verwijderen wanneer u maar wilt. Pas uw wijzigingen aan in de assets in de map of SharePoint bibliotheek die u hebt geïdentificeerd als een origin. Als u een nieuw activum toevoegt, is deze direct beschikbaar via CDN. Als u het activum echter bij werkt, duurt het maximaal 15 minuten voordat de nieuwe kopie wordt doorgegeven en beschikbaar komt in de CDN.
  
Als u de locatie van de origin wilt ophalen, kunt u de **cmdlet Get-PnPTenantCdnOrigin** gebruiken. Zie [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)voor meer informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Een origin verwijderen uit de Office 365 CDN

U kunt de toegang tot een map of bibliotheek SharePoint verwijderen die u hebt geïdentificeerd als een origin. Gebruik hiervoor de **cmdlet Remove-PnPTenantCdnOrigin.**

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Zie [Remove-PnPTenantCdnOrigin (Verwijderen-PnPTenantCdnOrigin)](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)voor meer informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Een origin in de Office 365 CDN

U kunt een origin die u hebt gemaakt niet wijzigen. In plaats daarvan verwijdert u de origin en voegt u een nieuwe toe. Zie Een origin verwijderen [uit de](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) Office 365 CDN en Een origin toevoegen voor uw assets voor [meer informatie.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>De Office 365 CDN

Gebruik de **cmdlet Set-PnPTenantCdnEnabled om** de CDN voor uw organisatie uit te schakelen. Als u zowel de openbare als de privé-origins hebt ingeschakeld voor de CDN, moet u de cmdlet tweemaal uitvoeren, zoals wordt weergegeven in de volgende voorbeelden.
  
Als u het gebruik van openbare origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Als u het gebruik van de privé-origins in de CDN wilt uitschakelen, voert u de volgende opdracht in:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Zie [Set-PnPTenantCdnEnabled voor meer informatie over deze cmdlet.](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>De Office 365 CDN instellen en configureren met Office 365 CLI

Voor de procedures in deze sectie moet u de Office 365 [CLI.](https://aka.ms/o365cli) Maak vervolgens verbinding met uw Office 365 tenant met de [opdracht Aanmelden.](https://pnp.github.io/office365-cli/cmd/login/)

Voltooi deze stappen voor het instellen en configureren van de CDN om uw assets te hosten in SharePoint Online met behulp van Office 365 CLI.

<details>
  <summary>Klik om uit te vouwen</summary>

### <a name="enable-the-office-365-cdn"></a>De Office 365 CDN

U kunt de status van de Office 365 CDN in uw tenant beheren met de [opdracht SPO-cdn-set.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/)

Als u de Office 365 openbare CDN in uw tenant wilt inschakelen, voert u het volgende uit:

```cli
spo cdn set --type Public --enabled true
```

Voer de volgende Office 365 SharePoint CDN uit om de Office 365 SharePoint CDN in te stellen:

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>De huidige status van de Office 365 CDN

Als u wilt controleren of het specifieke type Office 365 CDN is ingeschakeld of uitgeschakeld, gebruikt u de [opdracht spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Als u wilt controleren of Office 365 openbare CDN is ingeschakeld, voert u het volgende uit:

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>De oorspronkelijke Office 365 CDN weergeven

Als u de momenteel geconfigureerde Office 365 openbare CDN origins wilt weergeven:

```cli
spo cdn origin list --type Public
```

Zie [Standaardinstellingen CDN origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de origins die standaard zijn ingericht wanneer u de Office 365 CDN.

### <a name="add-an-office-365-cdn-origin"></a>Een oorspronkelijke Office 365 CDN toevoegen

> [!IMPORTANT]
> U mag resources die als gevoelig voor uw organisatie worden beschouwd, nooit in een SharePoint documentbibliotheek plaatsen die is geconfigureerd als een openbare origin.

Gebruik de [opdracht SPO CDN Origin Add om](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) een CDN definiëren. U kunt meerdere origins definiëren. De origin is een URL die wijst naar een SharePoint of map die de assets bevat die u wilt hosten door de CDN.

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

Waar `path` is het relatieve pad naar de map met de assets. U kunt jokertekens gebruiken naast relatieve paden.

Als u alle activa in de galerie met **basispagina's** van alle sites wilt opnemen als openbare origin, voert u het volgende uit:

```cli
spo cdn origin add --type Public --origin */masterpage
```

Als u een persoonlijke origin wilt configureren voor een specifieke siteverzameling, voert u het volgende uit:

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Nadat u een CDN hebt toegevoegd, kan het tot 15 minuten duren voordat u bestanden kunt ophalen via de CDN service. U kunt controleren of de specifieke origin al is ingeschakeld met de [opdracht SPO CDN Origin List.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/)

### <a name="remove-an-office-365-cdn-origin"></a>Een oorspronkelijke Office 365 CDN verwijderen

Gebruik de [opdracht SPO CDN Origin Remove om](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) een CDN voor het opgegeven CDN verwijderen.

Als u een openbare origin wilt verwijderen uit de CDN configuratie, voert u het volgende uit:

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Het verwijderen CDN origin heeft geen invloed op de bestanden die zijn opgeslagen in een documentbibliotheek die overeenkomt met die origin. Als naar deze assets wordt verwezen met behulp van SharePoint URL, SharePoint automatisch terug naar de oorspronkelijke URL die naar de documentbibliotheek wijst. Als er echter naar activa is verwezen met een openbare CDN URL, wordt de koppeling door het verwijderen van de origin verwijderd en moet u deze handmatig wijzigen.

### <a name="modify-an-office-365-cdn-origin"></a>Een oorspronkelijke Office 365 CDN wijzigen

Het is niet mogelijk om een bestaande CDN wijzigen. In plaats daarvan moet u de eerder gedefinieerde origin CDN de opdracht verwijderen en een nieuwe met `spo cdn origin remove` de opdracht `spo cdn origin add` toevoegen.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>De typen bestanden wijzigen die u wilt opnemen in de Office 365 CDN

Standaard worden de volgende bestandstypen opgenomen in de CDN: _.css, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff en .woff2_. Als u extra bestandstypen wilt opnemen in de CDN, kunt u de configuratie van de CDN wijzigen met de [opdracht SPO CDN-beleidset.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/)

> [!NOTE]
> Wanneer u de lijst met bestandstypen verandert, overschrijft u de lijst die momenteel is gedefinieerd. Als u extra bestandstypen wilt opnemen, gebruikt u eerst de opdracht lijst met [spo-cdn-beleid](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) om erachter te komen welke bestandstypen momenteel zijn geconfigureerd.

Als u het _JSON-bestandstype_ wilt toevoegen aan de standaardlijst met bestandstypen die zijn opgenomen in de openbare CDN voert u het volgende uit:

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>De lijst met siteclassificaties wijzigen die u wilt uitsluiten van de Office 365 CDN

Gebruik de [opdracht SPO CDN-beleidset](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) om siteclassificaties uit te sluiten die u niet beschikbaar wilt maken in de CDN. Standaard worden geen siteclassificaties uitgesloten.

> [!NOTE]
> Wanneer u de lijst met uitgesloten siteclassificaties verandert, overschrijft u de lijst die momenteel is gedefinieerd. Als u extra classificaties wilt uitsluiten, gebruikt u eerst de [opdracht SPO CDN-beleidlijst](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) om te kijken welke classificaties momenteel zijn geconfigureerd.

Als u sites die als _HBI zijn geclassificeerd,_ wilt uitsluiten van de openbare CDN, voert u

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>De Office 365 CDN

Als u de Office 365 CDN de opdracht `spo cdn set` wilt uitschakelen, bijvoorbeeld:

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Uw CDN gebruiken

Nu u de oorspronkelijke CDN en geconfigureerde origins en beleidsregels hebt ingeschakeld, kunt u uw CDN gebruiken.

In deze sectie krijgt u inzicht in het gebruik van CDN-URL's in uw SharePoint-pagina's en inhoud, zodat SharePoint aanvragen voor activa in zowel openbare als privé-origins omleiden naar de CDN.

+ [Koppelingen naar CDN bijwerken](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Activa gebruiken in openbare origins](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Activa in privé-origins gebruiken](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Zie het onderwerp Host [your client-side web part from Office 365 CDN (Hello World part 4)](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)voor informatie over het gebruik van de CDN voor het hosten van webonderdelen aan de clientzijde.

> [!NOTE]
> Als u de map _ClientSideAssets_ toevoegt aan de lijst met CDN-origins, kunnen CDN aangepaste webonderdelen niet worden weergegeven.  Bestanden die door SPFX-webonderdelen worden gebruikt, kunnen alleen gebruikmaken van de openbare CDN en de map ClientSideAssets is een standaardinstelling voor openbare CDN. 

### <a name="updating-links-to-cdn-assets"></a>Koppelingen naar CDN bijwerken

Als u activa wilt gebruiken die u aan een origin hebt toegevoegd, kunt u koppelingen naar het oorspronkelijke bestand bijwerken met het pad naar het bestand in de origin.

+ Bewerk de pagina of inhoud die koppelingen bevat naar activa die u aan een origin hebt toegevoegd. U kunt ook een van de verschillende methoden gebruiken om wereldwijd koppelingen in een enter-site of siteverzameling te zoeken en te vervangen als u de koppeling naar een bepaald activum overal wilt bijwerken waar deze wordt weergegeven.
+ Vervang voor elke koppeling naar een activum in een origin het pad door het pad naar het bestand in de CDN origin. U kunt relatieve paden gebruiken.
+ Sla de pagina of inhoud op.

Denk bijvoorbeeld aan de afbeelding _/site/SiteAssets/images/image.png_, die u hebt gekopieerd naar de map _documentbibliotheek /site/CDN_origins/public/_. Als u de CDN wilt gebruiken, vervangt u het oorspronkelijke pad naar de locatie van het afbeeldingsbestand door het pad naar de origin om de nieuwe URL _/site/CDN_origins/public/image.png._

Als u de volledige URL naar het activum wilt gebruiken in plaats van een relatief pad, maakt u de koppeling als het volgende:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> In het algemeen moet u URL's niet rechtstreeks hardcoderen naar activa in de CDN. U kunt echter indien nodig handmatig URL's maken voor activa in openbare origins. Zie [Hardcoding CDN URL's voor openbare activa voor meer informatie.](use-microsoft-365-cdn-with-spo.md)

Zie Hoe kan ik bevestigen dat activa worden beheerd door de CDN [Office 365 CDN?](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)in Problemen met de CDN voor meer informatie over het controleren of activa worden gebruikt vanuit de [CDN.](use-microsoft-365-cdn-with-spo.md#CDNConfirm)

### <a name="using-assets-in-public-origins"></a>Activa gebruiken in openbare origins

Met **de** functie Publiceren in SharePoint Online worden URL's van activa die zijn opgeslagen in openbare origins automatisch herschreven in hun CDN-equivalenten, zodat activa worden gebruikt vanuit de CDN-service in plaats van SharePoint.

Als uw origin zich op een site met de functie Publiceren heeft ingeschakeld en de activa die u wilt overschrijven naar de CDN zich in een van de volgende categorieën plaatsen, worden INL's in SharePoint automatisch herschreven voor activa in de origin, mits het activum niet is uitgesloten door een CDN-beleid.

Hieronder volgt een overzicht van de koppelingen die automatisch worden herschreven door de SharePoint Publicatiefunctie:

+ IMG/LINK/CSS-URL's in html-antwoorden voor klassieke publicatiepagina
  + Dit omvat afbeeldingen die door auteurs zijn toegevoegd aan de HTML-inhoud van een pagina
+ AfbeeldingsbibliotheekDiavoorstelling webonderdeel AFBEELDING-URL's
+ Afbeeldingsvelden in SPList REST API (RenderListDataAsStream) resultaten
  + De nieuwe eigenschap _ImageFieldsToTryRewriteToCdnUrls_ gebruiken om een door komma's gescheiden lijst met velden op te geven
  + Ondersteunt hyperlinkvelden en PublishingImage-velden
+ SharePoint afbeeldingsweergaven

In het volgende diagram wordt de werkstroom weergegeven wanneer SharePoint een aanvraag ontvangt voor een pagina met activa van een openbare origin.

![Werkstroomdiagram: ophalen Office 365 CDN activa van een openbare origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Werkstroom: het ophalen Office 365 CDN activa van een openbare origin")

> [!TIP]
> Als u automatisch herschrijven voor specifieke URL's op een pagina wilt uitschakelen, kunt u de pagina bekijken en de parameter queryreeks **toevoegen? NoAutoReWrites=true** aan het einde van elke koppeling die u wilt uitschakelen.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Url'CDN maken voor openbare activa

Als  de publicatiefunctie niet is ingeschakeld voor een openbare origin of als het activum niet een van de koppelingstypen is die worden ondersteund door de functie voor automatisch herschrijven van de CDN-service, kunt u HANDMATIG URL's maken naar de CDN-locatie van de activa en deze URL's in uw inhoud gebruiken.

> [!NOTE]
> U kunt url's niet hardcoderen of CDN maken voor activa in een persoonlijke origin, omdat het vereiste toegangs token dat de laatste sectie van de URL vormt, wordt gegenereerd op het moment dat de resource wordt aangevraagd. U kunt de URL voor openbare CDN maken en de URL mag niet moeilijk worden gecodeerd omdat deze onderhevig is aan wijziging.

Voor openbare CDN ziet de URL-indeling er als volgt uit:

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Vervang **TenantHostName** door uw tenantnaam. Voorbeeld:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> De paginacontext-eigenschap moet worden gebruikt om het voorvoegsel te maken in plaats van hardcoderen " https://publiccdn.sharepointonline.com ". De URL kan worden gewijzigd en mag niet hard worden gecodeerd. Als u weergavesjablonen gebruikt met Classic SharePoint Online, kunt u de eigenschap 'window._spPageContextInfo.publicCdnBaseUrl' gebruiken in de weergavesjabloon voor het voorvoegsel van de URL. Als u SPFx voor moderne en klassieke SharePoint kunt u de eigenschap 'this.context.pageContext.legacyPageContext.publicCdnBaseUrl' gebruiken. Dit geeft het voorvoegsel op, zodat als het wordt gewijzigd, de implementatie wordt bijgewerkt. Als voorbeeld voor SPFx kan de URL worden gemaakt met de eigenschap 'this.context.pageContext.legacyPageContext.publicCdnBaseUrl' + "/" + "host" + "/" + "relativeURL for the item". Zie [Gebruik CDN in clientcode](https://youtu.be/IH1RbQlbhIA) die deel uitmaakt van de [prestatiereeks seizoen 1](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>Activa in privé-origins gebruiken

Er is geen extra configuratie vereist voor het gebruik van activa in privé-origins. SharePoint Online herschrijft automatisch URL's voor activa in privé-origins, zodat aanvragen voor deze activa altijd vanaf de CDN. U kunt URL's niet handmatig maken voor CDN-assets in privé-origins, omdat deze URL's tokens bevatten die automatisch moeten worden gegenereerd door SharePoint Online op het moment dat het activum wordt aangevraagd.

Toegang tot activa in privé-origins wordt beveiligd door dynamisch gegenereerde tokens op basis van gebruikersmachtigingen voor de origin, met de waarschuwingen die in de volgende secties worden beschreven. Gebruikers moeten ten minste **leestoegang** hebben tot de origins voor de CDN om inhoud weer te geven.

In het volgende diagram wordt de werkstroom weergegeven wanneer SharePoint een aanvraag ontvangt voor een pagina met activa van een persoonlijke origin.

![Werkstroomdiagram: ophalen Office 365 CDN activa van een privé-origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Werkstroom: ophalen van Office 365 CDN activa van een privé-origin")

#### <a name="token-based-authorization-in-private-origins"></a>Autorisatie op basis van token in privé-origins

Toegang tot activa in privé-origins in de Office 365 CDN wordt verleend door tokens die worden gegenereerd door SharePoint Online. Gebruikers die al toegang hebben tot de map of bibliotheek die door de origin is aangewezen, krijgen automatisch tokens die de gebruiker toegang geven tot het bestand op basis van hun machtigingsniveau. Deze toegangstokens zijn geldig voor 30 tot 90 minuten nadat ze zijn gegenereerd om te voorkomen dat token opnieuw wordt afgespeeld.

Wanneer het toegangs token is gegenereerd, retourneert SharePoint Online een aangepaste URI naar de client met twee autorisatieparameters _eten_ (edge authorization token) en _haver_ (origin authorization token). De structuur van elk token is<'verlooptijd in tijdnotatie _epoch'>__<'secure signature'>._ Bijvoorbeeld:

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Iedereen die in het bezit is van het token, heeft toegang tot de resource in de CDN. URL's met deze toegangstokens worden echter alleen gedeeld via HTTPS, dus tenzij de URL expliciet wordt gedeeld door een eindgebruiker voordat het token verloopt, is het activum niet toegankelijk voor niet-geautoriseerde gebruikers.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Machtigingen op itemniveau worden niet ondersteund voor activa in privé-origins

Het is belangrijk om te weten dat SharePoint Online geen machtigingen op itemniveau ondersteunt voor activa in privé-origins. Voor een bestand dat zich bijvoorbeeld op bevindt, hebben gebruikers effectieve toegang tot het `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` bestand onder de volgende voorwaarden:

|Gebruiker  |Machtigingen  |Effectieve toegang  |
|---------|---------|---------|
|Gebruiker 1     |Heeft toegang tot map1         |Toegang tot image1.jpg de CDN         |
|Gebruiker 2     |Heeft geen toegang tot map1         |Geen toegang image1.jpg de CDN         |
|Gebruiker 3     |Heeft geen toegang tot map1, maar wordt expliciete machtigingen verleend voor toegang tot image1.jpg in SharePoint Online         |U kunt de activa image1.jpg rechtstreeks vanuit SharePoint Online openen, maar niet vanuit de CDN         |
|Gebruiker 4     |Heeft toegang tot map1, maar is expliciet toegang geweigerd tot image1.jpg in SharePoint Online         |Heeft geen toegang tot het activum vanuit SharePoint Online, maar heeft wel toegang tot het activum vanuit de CDN ondanks dat de toegang tot het bestand in SharePoint Online is geweigerd         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Problemen met de Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Hoe kan ik bevestigen dat activa worden gebruikt door de CDN?

Nadat u koppelingen naar CDN-assets aan een pagina hebt toegevoegd, kunt u bevestigen dat het activum wordt weergegeven vanaf de CDN door naar de pagina te bladeren, met de rechtermuisknop op de afbeelding te klikken nadat de afbeelding is weergegeven en de url van de afbeelding te controleren.

U kunt ook de hulpprogramma's voor ontwikkelaars van uw browser gebruiken om de URL voor elk activum op een pagina weer te geven of een hulpprogramma voor netwerk traceren van derden gebruiken.

> [!NOTE]
> Als u een netwerkhulpmiddel, zoals Fiddler, gebruikt om uw activa te testen buiten het weergeven van het activum vanaf een SharePoint-pagina, moet u handmatig de refererkop 'Referer:' toevoegen aan de GET-aanvraag waarbij de URL de hoofd-URL is van uw `https://yourdomain.sharepoint.com` SharePoint Online-tenant.

Het is niet mogelijk CDN URL's rechtstreeks in een webbrowser te testen, omdat u een referer moet hebben die afkomstig is van SharePoint Online. Als u echter de CDN-activa-URL toevoegt aan een SharePoint-pagina en vervolgens de pagina opent in een browser, ziet u de CDN-asset weergegeven op de pagina.

Zie voor meer informatie over het gebruik van de hulpprogramma's voor ontwikkelaars in Microsoft Edge browser [Microsoft Edge Ontwikkelaarshulpmiddelen.](/microsoft-edge/devtools-guide)

Als u een korte video wilt bekijken die wordt gehost in het [YouTube-kanaal van SharePoint Developer Patterns and Practices,](https://aka.ms/sppnp-videos) waarin wordt gedemonstreert hoe u kunt controleren of uw CDN werkt, raadpleegt u [Uw CDN-gebruik](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)verifiëren en een optimale netwerkverbinding garanderen.

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Waarom zijn activa van een nieuwe origin niet beschikbaar?
Activa in nieuwe origins zijn niet onmiddellijk beschikbaar voor gebruik, omdat het tijd kost om de registratie door te sturen via de CDN en om de assets te uploaden van de origin naar CDN storage. De tijd die nodig is om activa beschikbaar te maken in de CDN is afhankelijk van het aantal assets en de bestandsgrootten.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Mijn clientwebonderdeel of -SharePoint Framework werkt niet

Wanneer u de Office 365 CDN voor openbare origins inschakelen, worden CDN standaard origins automatisch gemaakt:

+ */MASTERPAGE
+ */STIJLBIBLIOTHEEK
+ */CLIENTSIDEASSETS

Als de origin */clientsideassets ontbreekt, mislukt SharePoint Framework en worden er geen waarschuwings- of foutberichten gegenereerd. Deze origin ontbreekt mogelijk omdat de CDN is ingeschakeld met de parameter _-NoDefaultOrigins_ ingesteld op **$true** of omdat de origin handmatig is verwijderd.

U kunt controleren welke origins aanwezig zijn met de volgende PowerShell-opdracht:

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

U kunt ook contact op met Office 365 CLI:

```cli
spo cdn origin list
```

De origin in PowerShell toevoegen:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

Als u de origin in de Office 365 CLI wilt toevoegen:

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Welke PowerShell-modules en CLI-shells heb ik nodig om met de Office 365 CDN?

U kunt ervoor kiezen om met de Office 365 CDN te werken met de **SharePoint Online Management Shell** PowerShell-module of de Office 365 **CLI.**

+ [Aan de slag met SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [De cli Office 365 installeren](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Zie ook

[Netwerken voor contentlevering](./content-delivery-networks.md)

[Network planning and performance tuning for Office 365](./network-planning-and-performance.md)

[SharePoint Performance Series - Office 365 CDN videoreeks](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)