---
title: Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online
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
description: Meer informatie over het gebruik van het Office 365 Content Delivery Network (CDN) om de levering van uw SharePoint Online-assets te versnellen.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688971"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Het Office 365 Content Delivery Network (CDN) gebruiken met SharePoint Online

U kunt het ingebouwde Office 365 Content Delivery Network (CDN) gebruiken voor het hosten van statische activa voor betere prestaties voor de SharePoint Online-pagina's. Het CDN van Office 365 verbetert de prestaties omdat statische activa dichter bij de door u gevraagde browsers worden opgevolgd, zodat downloads sneller kunnen worden en de latentie minder kost. Daarnaast wordt in Office 365 CDN het [protocol http/2](https://en.wikipedia.org/wiki/HTTP/2) gebruikt voor verbeterde compressie en http-pipeline. De Office 365 CDN-service maakt deel uit van uw SharePoint Online-abonnement.

> [!NOTE]
> Het Office 365 CDN is alleen beschikbaar voor tenants in de **productie** -Cloud (wereldwijd). Tenants in de Verenigde Staten voor de overheid, China en Duitsland ondersteunen momenteel het Office 365 CDN.

Het CDN van Office 365 is samengesteld uit meerdere Cdn's die u in staat stellen statische activa te hosten op meerdere locaties of _herkomst_en ze van wereldwijde hogesnelheids netwerken te bezorgen. Afhankelijk van het type inhoud dat u in het Office 365 CDN wilt hosten, kunt u **openbare** oorsprong, **persoonlijke** Origins of beide toevoegen. Zie [kiezen of u elke oorsprong openbaar of privé moet zijn](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) voor meer informatie over het verschil tussen openbare en persoonlijke oorsprong.

![Office 365 CDN-conceptueel diagram](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-conceptueel diagram")

Als u al bekend bent met de manier waarop Cdn's werken, hoeft u slechts enkele stappen uit te voeren om het Office 365 CDN voor uw Tenant in te schakelen. In dit onderwerp wordt uitgelegd hoe u dit kunt doen. Lees verder voor informatie over hoe u aan de slag kunt gaan met het hosten van uw statische activa.

> [!TIP]
> Er zijn andere Microsoft-gehoste Cdn's die kunnen worden gebruikt met Office 365 voor gespecialiseerde gebruiksscenario's, maar worden niet in dit onderwerp besproken omdat ze buiten het bereik van het Office 365-CDN vallen. Zie voor meer informatie [andere Microsoft-cdn's](content-delivery-networks.md#other-microsoft-cdns).

 **Ga terug naar [netwerk planning en prestaties optimaliseren voor Office 365](https://aka.ms/tune).**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Overzicht van het werken met het Office 365-CDN in SharePoint Online

Als u het Office 365 CDN voor uw organisatie wilt instellen, volgt u deze basisstappen:

+ [Implementatie van Office 365 CDN voorbereiden](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Bepaal welke statische activa u wilt hosten op de CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets).
  + [Bepalen waar u de assets wilt opslaan](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets). Deze locatie kan een SharePoint-site,-bibliotheek of-map worden en wordt een _oorsprong_genoemd.
  + [Kies of u de oorsprong openbaar of privé wilt maken](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate). U kunt meerdere herkomst van zowel openbare als persoonlijke typen toevoegen.

+ Het CDN instellen en configureren met behulp van PowerShell of de SharePoint Online CLI

  + [Het CDN instellen en configureren met behulp van de SharePoint Online Management Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Het CDN instellen en configureren met behulp van PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Het CDN instellen en configureren met behulp van Office 365 CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Wanneer u deze stap uitvoert, hebt u de volgende opties:

  + De CDN voor uw organisatie is ingeschakeld.
  + U hebt uw oorsprong toegevoegd en identificeren elke Origin als openbaar of privé.

Wanneer u klaar bent met de configuratie, kunt u [het Office 365-CDN in de](use-microsoft-365-cdn-with-spo.md#CDNManage) loop van de tijd beheren door het volgende te doen:
  
+ Assets toevoegen, bijwerken en verwijderen
+ Oorsprong toevoegen en verwijderen
+ CDN-beleidsregels configureren
+ Het CDN zo nodig uitschakelen

Zie tot slot [uw CDN-assets gebruiken](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) voor meer informatie over het openen van uw CDN-assets via openbare en persoonlijke oorsprong.

Zie [problemen oplossen met het Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) voor informatie over het oplossen van veelvoorkomende problemen.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Implementatie van Office 365 CDN voorbereiden

Voordat u het Office 365 CDN voor uw Office 365-Tenant implementeert, moet u de volgende factoren overwegen als onderdeel van de plannings procedure.

  + [Bepalen welke statische activa u wilt hosten op het CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bepalen waar u de assets wilt opslaan](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Kies of u de oorsprong openbaar of privé wilt maken.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Bepalen welke statische activa u wilt hosten op het CDN

In het algemeen is Cdn's het meest geschikt voor het hosten van _statische activa_, of activa die niet vaak veranderen. Een goede vuistregel is om bestanden te identificeren die voldoen aan een of meer van de volgende voorwaarden:

+ Statische bestanden die zijn ingesloten in een pagina (zoals scripts en afbeeldingen) die mogelijk een belangrijke invloed hebben op de laadtijden van pagina's
+ Grote bestanden, zoals uitvoerbare bestanden en installatiebestanden
+ Bronnen bibliotheken die de programmacode voor de client ondersteunen

Wanneer u een site toevoegt aan een CDN-oorsprong, kunnen de prestaties van sites in SharePoint Online op een andere manier worden weergegeven, bijvoorbeeld wanneer u deze hebt toegevoegd aan een CDN-oorsprong. Grotere bestanden, zoals uitvoerbare bestanden, kunnen worden gedownload van de CDN, met een positieve invloed op de prestaties en het verminderen van de belasting van de SharePoint Online-site, zelfs als ze niet zo vaak worden geopend.

De prestaties zijn afhankelijk van een groot aantal factoren, waaronder de buurt van de client en het dichtstbijzijnde CDN-eindpunt, tijdelijke voorwaarden voor het lokale netwerk, enzovoort. Veel statische bestanden zijn zeer klein en kunnen worden gedownload van Office 365 in minder dan een seconde. Een webpagina kan echter veel ingesloten bestanden bevatten met een cumulatieve downloadtijd van enkele seconden. Bij deze bestanden van de CDN kan de totale laadtijd van de pagina aanzienlijk worden verkleind. Bekijk [welke prestatiewinst een CDN](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) biedt voor een voorbeeld.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Bepalen waar u de assets wilt opslaan

De CDN haalt de assets op van de locatie die een _oorsprong_wordt genoemd. Een oorsprong kan een SharePoint-site, documentbibliotheek of map zijn die toegankelijk is voor een URL. U hebt een fantastische flexibiliteit wanneer u oorsprong opgeeft voor uw organisatie. U kunt bijvoorbeeld meerdere Origins of één herkomst opgeven waar u al uw CDN-activa wilt plaatsen. U kunt ervoor kiezen om zowel openbare als persoonlijke oorsprong te hebben voor uw organisatie. De meeste organisaties kiezen om een combinatie van beide te implementeren.

U kunt een nieuwe container maken voor uw herkomst, zoals mappen of documentbibliotheken, en bestanden toevoegen die u beschikbaar wilt maken in het CDN. Dit is een goede manier om te bepalen of u beschikt over een specifieke groep activa die u in het CDN wilt weergegeven, en dat u de set CDN-assets wilt beperken tot alleen de bestanden in de container.

U kunt ook een bestaande siteverzameling, site, bibliotheek of map configureren als een oorsprong, zodat alle in aanmerking komende assets worden gemaakt in de container die beschikbaar is in het CDN. Voordat u een bestaande container als een oorsprong toevoegt, moet u ervoor zorgen dat u zich bewust bent van de inhoud en machtigingen van de container, zodat u niet per ongeluk middelen uitgeeft aan anonieme toegang of niet-geautoriseerde gebruikers.

U kunt _CDN-beleidsregels_ definiëren als u de inhoud van uw oorsprong wilt uitsluiten van het CDN. CDN-beleidsregels uitsluiten activa in openbare of persoonlijke oorsprong op basis van kenmerken zoals _bestandstype_ en _siteclassificatie_, en worden toegepast op alle oorsprong van de CdnType (privé of openbaar) die u in het beleid opgeeft. Als u bijvoorbeeld een persoonlijke oorsprong opneemt van een site die meerdere subsites bevat, kunt u een beleid definiëren om websites uit te sluiten die als **vertrouwelijk** zijn gemarkeerd, zodat de inhoud van sites met deze classificatie niet wordt verzonden vanuit de CDN. Het beleid is van toepassing op inhoud van _alle_ persoonlijke oorsprong die u hebt toegevoegd aan het CDN.
  
Houd er rekening mee dat u het volgende moet doen, hoe hoger de invloed van de CDN-service op het verwerken van aanvragen. We raden u aan het aantal oorsprong zo veel mogelijk te beperken.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Kies of u de oorsprong openbaar of privé wilt maken.

Wanneer u een oorsprong identificeert, geeft u op of deze _openbaar_ of _privé_moet worden gemaakt. Toegang tot CDN-assets in openbare Origins is anoniem, en CDN-inhoud in persoonlijke Origins wordt beveiligd door dynamische gegenereerde tokens voor een betere beveiliging. Ongeacht de optie die u kiest, heeft Microsoft het zware recht voor u bij het beheer van de CDN zelf. Daarnaast kunt u later ook wijzigen na het instellen van de CDN en het identificeren van uw oorsprong.

Zowel de openbare als de persoonlijke opties bieden soortgelijke prestatieverbeteringen, maar elk heeft unieke kenmerken en voordelen.

**Openbare** Origins in Office 365 CDN zijn anoniem toegankelijk en gehoste assets zijn toegankelijk voor iedereen die de URL van het activum bevat. Aangezien toegang tot inhoud in openbare Origin anoniem is, moet u deze alleen gebruiken voor het opslaan van niet-gevoelige algemene inhoud, zoals JavaScript-bestanden, scripts, pictogrammen en afbeeldingen.

**Persoonlijke** Origins in Office 365 CDN bieden persoonlijke toegang tot gebruikers inhoud, zoals documentbibliotheken van SharePoint Online, sites en eigen afbeeldingen. De toegang tot inhoud in persoonlijke Origins wordt door dynamische gegenereerde tokens beveiligd, zodat deze alleen kan worden geopend door gebruikers met machtigingen voor de oorspronkelijke documentbibliotheek of opslaglocatie. Persoonlijke Origins in het Office 365-CDN kunnen alleen worden gebruikt voor SharePoint Online-inhoud en u kunt geen toegang krijgen tot assets van persoonlijke oorsprong via omleiding van de SharePoint Online-Tenant.

U vindt meer informatie over de manier waarop u met behulp van de toegang tot activa in een privé-oorsprong kunt werken [met assets in persoonlijke oorsprong](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Kenmerken en voordelen van het hosten van assets in openbare oorsprong
  
+ Activa die zijn opgenomen in een openbare Origin zijn door iedereen anoniem toegankelijk.
    > [!IMPORTANT]
    > U dient nooit bronnen te plaatsen die gebruikersgegevens bevatten of die in een openbare Origin als vertrouwelijk worden beschouwd.
+ Als u een activum verwijdert uit een openbare Origin, is het mogelijk dat het activum tot 30 dagen langer beschikbaar is in de cache. We zullen de koppelingen naar het activum binnen 15 minuten ongeldig maken.
+ Wanneer u stijlbladen (CSS-bestanden) in een openbare Origin host, kunt u relatieve paden en Uri's binnen de code gebruiken. Dit betekent dat u kunt verwijzen naar de locatie van achtergrondafbeeldingen en andere objecten ten opzichte van de locatie van het activum dat wordt gebeld.
+ U kunt de URL van een openbare oorsprong ook op een andere manier vastleggen. De reden hiervoor is dat de toegang tot de CDN niet langer beschikbaar is, dat de URL automatisch wordt omgezet in uw organisatie in SharePoint Online en kan leiden tot verbroken koppelingen en andere fouten.
+ De standaardbestandstypen die zijn opgenomen voor openbare oorsprong zijn. CSS,. EOT,. GIF,. ICO,. JPEG,. jpg,. js,. map,. png,. svg,. U kunt extra bestandstypen opgeven.
+ U kunt een beleid configureren voor de uitsluiting van activa die zijn aangeduid door de site classificaties die u opgeeft. U kunt bijvoorbeeld alle assets uitsluiten die zijn gemarkeerd als ' vertrouwelijk ' of ' beperkt ', zelfs als ze een toegestaan bestandstype zijn en zich bevinden in een openbare Origin.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Kenmerken en voordelen van het hosten van assets in persoonlijke oorsprong

+ Persoonlijke Origins kunnen alleen worden gebruikt voor SharePoint Online-assets.
+ Gebruikers hebben alleen toegang tot de assets van een privé-oorsprong als ze toegang hebben tot de container. Anonieme toegang tot deze assets wordt voorkomen.
+ De activa in de privé-oorsprong moeten worden genoemd in de SharePoint Online-Tenant. Directe toegang tot private CDN-assets werkt niet.
+ Als u een activum verwijdert uit de persoonlijke oorsprong, kan het activum langer beschikbaar zijn voor een uur van de cache. We zullen echter de koppelingen naar het activum binnen 15 minuten na verwijdering van het activum ongeldig maken in het CDN.
+ De standaardbestandstypen die zijn opgenomen voor persoonlijke oorsprong zijn. GIF,. ICO,. JPEG,. jpg,. js en. png. U kunt extra bestandstypen opgeven.
+ Net als bij openbare Origin, kunt u een beleid configureren om activa uit te sluiten die zijn geïdentificeerd door site classificaties die u opgeeft, ook als u jokertekens gebruikt om alle elementen in een map of een documentbibliotheek op te nemen.

Zie [netwerken die inhoud leveren](content-delivery-networks.md)voor meer informatie over het gebruik van Office 365 CDN, algemene CDN-concepten en andere Microsoft-cdn's die u kunt gebruiken met uw Office 365-Tenant.

### <a name="default-cdn-origins"></a>Standaard CDN-oorsprong

Tenzij u anders opgeeft, worden in Office 365 sommige standaardoorsprong voor u ingesteld wanneer u Office 365 CDN inschakelt. Als u ervoor kiest deze oorsprong niet in te richten, kunt u deze oorsprong toevoegen nadat u de installatie hebt voltooid. Tenzij u weet wat de gevolgen zijn voor het overlopen van de instelling van standaardoorsprong en een specifieke reden om dit te doen, moet u ze laten maken wanneer u het CDN inschakelt.
  
Standaard persoonlijke CDN-oorsprong:
  
+ \*/userphoto.aspx
+ \*/siteassets

Standaard openbare CDN-oorsprong:
  
+ \*/masterpage
+ \*/Style-bibliotheek
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ is een standaard-openbare oorsprong die is toegevoegd aan de Office 365 CDN-service in december 2017. Deze Origin moet bestaan in de volgorde waarin oplossingen van SharePoint Framework in de CDN werken. Als u het Office 365-CDN vóór december 2017 hebt ingeschakeld, of als u de installatie van standaardoorsprong hebt overgeslagen wanneer u het CDN inschakelt, kunt u deze oorsprong handmatig toevoegen. Zie [het webonderdeel van de client of de SharePoint Framework-oplossing werkt niet](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)voor meer informatie.

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Het Office 365-CDN instellen en configureren met behulp van de SharePoint Online Management Shell

Voor de procedures in deze sectie moet u de SharePoint Online Management Shell gebruiken om verbinding te maken met SharePoint Online. Zie [verbinding maken met SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)voor instructies.

Voer de volgende stappen uit om de CDN in te stellen en te configureren voor het hosten van uw assets in SharePoint Online met behulp van SharePoint Online Management Shell.

<details>
  <summary>Klik om uit te vouwen</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Toestaan dat uw organisatie Office 365 CDN gebruikt

Voordat u wijzigingen aanbrengt in de CDN-instellingen van de Tenant, moet u de huidige status van de persoonlijke CDN-configuratie in de Office 365-Tenant ophalen. Maak verbinding met de Tenant met behulp van SharePoint Online Management Shell:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Gebruik nu de cmdlet **Get-SPOTenantCdnEnabled** om de CDN-statusinstellingen van de Tenant op te halen:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

De status van de CDN voor het opgegeven CdnType wordt uitgevoerd naar het scherm.

Gebruik de cmdlet **set-SPOTenantCdnEnabled** om uw organisatie de mogelijkheid Office 365 CDN te gebruiken. U kunt ervoor zorgen dat uw organisatie openbare Origins, persoonlijke oorsprong of beide tegelijk kan gebruiken. U kunt de CDN ook configureren om de instelling van standaardoorsprong te negeren wanneer u deze inschakelt. U kunt deze oorsprong altijd later toevoegen, zoals beschreven in dit onderwerp.
  
In Windows PowerShell voor SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als persoonlijke oorsprong kan gebruiken, typt u de volgende opdracht:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Als u wilt dat uw organisatie zowel openbare als persoonlijke Origins kan gebruiken, maar de instelling van de standaardoorsprong gaat negeren, typt u de volgende opdracht:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Zie [standaard CDN-oorsprong](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de oorsprong die standaard wordt ingericht wanneer u Office 365 CDN inschakelt en de mogelijkheid om de instelling van standaardoorsprong over te slaan.

Als u wilt dat uw organisatie gebruik kan maken van openbare oorsprong, typt u de volgende opdracht:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Als u wilt dat uw organisatie gebruik kan maken van persoonlijke oorsprong, typt u de volgende opdracht:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Zie [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx)voor meer informatie over deze cmdlet.

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>De lijst met bestandstypen wijzigen die moeten worden opgenomen in het Office 365 CDN (optioneel)

> [!TIP]
> Wanneer u bestandstypen definieert met behulp van de cmdlet **set-SPOTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven. Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om erachter te komen welke bestandstypen al zijn toegestaan en voegt u ze toe aan de lijst samen met uw nieuwe.
  
Met de cmdlet **set-SPOTenantCdnPolicy** kunt u statische bestandstypen definiëren die worden gehost door openbare en persoonlijke Origins in het CDN. Veelgebruikte activatypen zijn standaard toegestaan, bijvoorbeeld. CSS,. GIF,. jpg en. js.

In Windows PowerShell voor SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Als u bijvoorbeeld de CDN wilt inschakelen voor host. CSS-en PNG-bestanden, typt u de volgende opdracht:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Gebruik de cmdlet **Get-Get spotenantcdnpolicies** om te zien welke bestandstypen momenteel zijn toegestaan in het CDN.

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Zie [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) en [Get-Get spotenantcdnpolicies](https://technet.microsoft.com/library/mt800838.aspx)voor meer informatie over deze cmdlets.

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>De lijst met site classificaties wijzigen die u wilt uitsluiten van Office 365 CDN (optioneel)

> [!TIP]
> Wanneer u site classificaties uitsluit met behulp van de cmdlet **set-SPOTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven. Als u extra site classificaties wilt uitsluiten, gebruikt u de cmdlet eerst om erachter te komen welke classificaties al zijn uitgesloten en voegt u ze vervolgens samen met uw nieuwe.

Met de cmdlet **set-SPOTenantCdnPolicy** kunt u de site classificaties uitsluiten die u niet beschikbaar wilt maken via het CDN. Standaard zijn geen site classificaties uitgesloten.

In Windows PowerShell voor SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Gebruik de cmdlet **Get-Get spotenantcdnpolicies** om te zien welke site classificaties momenteel zijn toegestaan.

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.

De eigenschap _IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanuit het CDN worden bediend.

> [!NOTE]
> De standaardbestandsextensies verschillen tussen openbare en persoonlijke bestanden.

De eigenschap _ExcludeRestrictedSiteClassifications_ bevat de site classificaties die u wilt uitsluiten van het CDN. U kunt bijvoorbeeld sites die als **vertrouwelijk** zijn gemarkeerd, uitsluiten, zodat de inhoud van sites met die classificatie niet via het CDN wordt verzonden.

De eigenschap _ExcludeIfNoScriptDisabled_ uitsluiten de inhoud van de CDN op basis van de instellingen van het _NoScript_ op siteniveau. Het kenmerk _NoScript_ is standaard ingesteld op **beschikbaar** voor _moderne_ sites en **uitgeschakeld** voor _klassieke_ sites. Dit hangt af van uw tenantinstellingen.

Zie [set-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) en [Get-Get spotenantcdnpolicies](https://technet.microsoft.com/library/mt800838.aspx)voor meer informatie over deze cmdlets.

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Een oorsprong voor uw activa toevoegen

Met de cmdlet **add-add spotenantcdnorigin** kunt u een oorsprong definiëren. U kunt meerdere oorsprong definiëren. De origin is een URL die verwijst naar een SharePoint-bibliotheek of-map die de assets bevat die u wilt hosten door de CDN.
  
> [!IMPORTANT]
> U dient nooit bronnen te plaatsen die gebruikersgegevens bevatten of die in een openbare Origin als vertrouwelijk worden beschouwd.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

De waarde van _pad_ is het relatieve pad naar de bibliotheek of map met de assets. U kunt jokertekens gebruiken in aanvulling op relatieve paden. Voor de URL worden jokertekens ondersteund. Hiermee kunt u oorsprong maken die meerdere sites beslaat. Als u bijvoorbeeld alle activa in de map # # # # # # # # # # # # # # # # wilt opnemen in het CDN, typt u de volgende opdracht:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ De wijziging van het jokerteken * **/** kan alleen aan het begin van het pad worden gebruikt en komt overeen met alle URL-segmenten onder de opgegeven URL.
+ Het pad kan verwijzen naar een documentbibliotheek, map of site. Het pad _*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.

U kunt een oorsprong met een specifiek relatief pad toevoegen. U kunt geen origin toevoegen met het volledige pad.

In dit voorbeeld wordt een persoonlijke oorsprong van de siteassets-bibliotheek op een specifieke site toegevoegd:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In dit voorbeeld wordt een persoonlijke oorsprong van de map _Map1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Als het pad een spatie bevat, kunt u het pad tussen dubbele aanhalingstekens plaatsen of de ruimte vervangen door de URL-codering %20. In het volgende voorbeeld wordt een persoonlijke oorsprong van de map _map 1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.

> [!NOTE]
> Bij particuliere Origin moet de activa die vanaf een oorsprong worden gedeeld, een primaire versie hebben gepubliceerd voordat ze toegankelijk zijn vanuit het CDN.
  
Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. Dit kan 15 minuten duren.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Voorbeeld: een openbare Origin configureren voor uw basispagina's en voor de stijlbibliotheek voor SharePoint Online

Normaalgesproken zijn deze oorsprong voor u standaard ingesteld wanneer u Office 365 CDN inschakelt. Voer de volgende stappen uit als u deze handmatig wilt inschakelen.
  
+ Met de cmdlet **add-add spotenantcdnorigin** kunt u de stijlbibliotheek definiëren als een openbare Origin.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Met de cmdlet **add-add spotenantcdnorigin** kunt u de basispagina's definiëren als een openbare Origin.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.

Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. Dit kan 15 minuten duren.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Voorbeeld: een persoonlijke Origin configureren voor uw site-assets, sitepagina's en publicatie afbeeldingen voor SharePoint Online

+ Met de cmdlet **add-add spotenantcdnorigin** kunt u de map siteactiva definiëren als persoonlijke Origin.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Met de cmdlet **add-add spotenantcdnorigin** kunt u de map sitepagina's definiëren als persoonlijke Origin.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Met de cmdlet **add-add spotenantcdnorigin** kunt u de map met publicatie-afbeeldingen definiëren als persoonlijke Origin.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.

Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. Dit kan 15 minuten duren.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Voorbeeld: een persoonlijke Origin configureren voor een siteverzameling voor SharePoint Online

Met de cmdlet **add-add spotenantcdnorigin** kunt u een siteverzameling als persoonlijke Origin definiëren. Bijvoorbeeld:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Zie [add-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790772.aspx)voor meer informatie over deze opdracht en de syntaxis.
  
Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. U ziet mogelijk een bericht _in behandeling_ waarvan de status van de SharePoint Online-Tenant wordt verwacht, zodat deze verbinding maakt met de CDN-service. Dit kan 15 minuten duren.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Het Office 365-CDN beheren

Wanneer u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in de configuratie wanneer u inhoud bijwerkt of de gewenste wijziging aanbrengt, zoals in deze sectie wordt beschreven.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Bronnen toevoegen, bijwerken of verwijderen uit het Office 365 CDN

Wanneer u de instellingsstappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande activa bijwerken of verwijderen wanneer u maar wilt. Breng de gewenste wijzigingen aan in de activa in de map of in de SharePoint-bibliotheek die u als een oorsprong hebt aangewezen. Als u een nieuw activum toevoegt, is het direct beschikbaar via het CDN. Als u echter het activum bijwerkt, duurt het maximaal vijftien minuten voordat de nieuwe versie beschikbaar is in het CDN.
  
Als u de locatie van de origin moet ophalen, kunt u de cmdlet **Get-SPOTenantCdnOrigins** gebruiken. Zie [Get-SPOTenantCdnOrigins](https://technet.microsoft.com/library/mt790770.aspx)voor informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Een oorsprong uit Office 365 CDN verwijderen

U kunt de toegang tot een map of een SharePoint-bibliotheek die u als een oorsprong hebt opgegeven, verwijderen. U kunt dit doen met behulp van de **Remove-add spotenantcdnorigin-** cmdlet.

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Zie [Remove-add spotenantcdnorigin](https://technet.microsoft.com/library/mt790761.aspx)voor informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Een origin in het Office 365-CDN wijzigen

U kunt geen Origin wijzigen die u hebt gemaakt. In plaats daarvan verwijdert u de oorsprong en voegt u een nieuwe toe. Zie voor meer informatie [een origin verwijderen uit het Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) en [een origin voor uw assets toevoegen](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Het Office 365-CDN uitschakelen

Gebruik de cmdlet **set-SPOTenantCdnEnabled** om de CDN uit te schakelen voor uw organisatie. Als u zowel openbare als persoonlijke Origins voor het CDN hebt ingeschakeld, moet u de cmdlet twee keer uitvoeren, zoals in de volgende voorbeelden wordt weergegeven.
  
Als u het gebruik van openbare Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Als u het gebruik van de persoonlijke Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Zie [set-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx)voor meer informatie over deze cmdlet.

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Het Office 365-CDN instellen en configureren met behulp van PnP PowerShell

Voor de procedures in dit gedeelte moet u gebruikmaken van PnP PowerShell om verbinding te maken met SharePoint Online. Zie [aan de slag met PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started)voor instructies.

Voer de volgende stappen uit om de CDN in te stellen en te configureren voor het hosten van uw assets in SharePoint Online met behulp van PnP PowerShell.

<details>
  <summary>Klik om uit te vouwen</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Toestaan dat uw organisatie Office 365 CDN gebruikt

Voordat u wijzigingen aanbrengt in de CDN-instellingen van de Tenant, moet u de huidige status van de persoonlijke CDN-configuratie in de Office 365-Tenant ophalen. Maak verbinding met de Tenant met behulp van PnP PowerShell:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Gebruik nu de cmdlet **Get-PnPTenantCdnEnabled** om de CDN-statusinstellingen van de Tenant op te halen:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

De status van de CDN voor het opgegeven CdnType wordt uitgevoerd naar het scherm.

Gebruik de cmdlet **set-PnPTenantCdnEnabled** om uw organisatie de mogelijkheid Office 365 CDN te gebruiken. U kunt instellen dat uw organisatie openbare Origins, persoonlijke oorsprong of beide tegelijkertijd kan gebruiken. U kunt de CDN ook configureren om de instelling van standaardoorsprong te negeren wanneer u deze inschakelt. U kunt deze oorsprong altijd later toevoegen, zoals beschreven in dit onderwerp.
  
In PnP PowerShell:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Als u bijvoorbeeld wilt dat uw organisatie zowel openbare als persoonlijke oorsprong kan gebruiken, typt u de volgende opdracht:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Als u wilt dat uw organisatie zowel openbare als persoonlijke Origins kan gebruiken, maar de instelling van de standaardoorsprong gaat negeren, typt u de volgende opdracht:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Zie [standaard CDN-oorsprong](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de oorsprong die standaard wordt ingericht wanneer u Office 365 CDN inschakelt en de mogelijkheid om de instelling van standaardoorsprong over te slaan.

Als u wilt dat uw organisatie gebruik kan maken van openbare oorsprong, typt u de volgende opdracht:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Als u wilt dat uw organisatie gebruik kan maken van persoonlijke oorsprong, typt u de volgende opdracht:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Zie [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)voor meer informatie over deze cmdlet.

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>De lijst met bestandstypen wijzigen die moeten worden opgenomen in het Office 365 CDN (optioneel)

> [!TIP]
> Wanneer u bestandstypen definieert met behulp van de cmdlet **set-PnPTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven. Als u extra bestandstypen aan de lijst wilt toevoegen, gebruikt u de cmdlet eerst om erachter te komen welke bestandstypen al zijn toegestaan en voegt u ze toe aan de lijst samen met uw nieuwe.
  
Met de cmdlet **set-PnPTenantCdnPolicy** kunt u statische bestandstypen definiëren die worden gehost door openbare en persoonlijke Origins in het CDN. Veelgebruikte activatypen zijn standaard toegestaan, bijvoorbeeld. CSS,. GIF,. jpg en. js.

In PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Als u bijvoorbeeld de CDN wilt inschakelen voor host. CSS-en PNG-bestanden, typt u de volgende opdracht:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Gebruik de cmdlet **Get-PnPTenantCdnPolicies** om te zien welke bestandstypen momenteel zijn toegestaan in het CDN.

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Zie [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) en [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>De lijst met site classificaties wijzigen die u wilt uitsluiten van Office 365 CDN (optioneel)

> [!TIP]
> Wanneer u site classificaties uitsluit met behulp van de cmdlet **set-PnPTenantCdnPolicy** , wordt de momenteel gedefinieerde lijst overschreven. Als u extra site classificaties wilt uitsluiten, gebruikt u de cmdlet eerst om erachter te komen welke classificaties al zijn uitgesloten en voegt u ze vervolgens samen met uw nieuwe.

Met de cmdlet **set-PnPTenantCdnPolicy** kunt u de site classificaties uitsluiten die u niet beschikbaar wilt maken via het CDN. Standaard zijn geen site classificaties uitgesloten.

In PnP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Gebruik de cmdlet **Get-PnPTenantCdnPolicies** om te zien welke site classificaties momenteel zijn toegestaan.

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

De eigenschappen die worden geretourneerd, zijn _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ en _ExcludeIfNoScriptDisabled_.

De eigenschap _IncludeFileExtensions_ bevat de lijst met bestandsextensies die vanuit het CDN worden bediend.

> [!NOTE]
> De standaardbestandsextensies verschillen tussen openbare en persoonlijke bestanden.

De eigenschap _ExcludeRestrictedSiteClassifications_ bevat de site classificaties die u wilt uitsluiten van het CDN. U kunt bijvoorbeeld sites die als **vertrouwelijk** zijn gemarkeerd, uitsluiten, zodat de inhoud van sites met die classificatie niet via het CDN wordt verzonden.

De eigenschap _ExcludeIfNoScriptDisabled_ uitsluiten de inhoud van de CDN op basis van de instellingen van het _NoScript_ op siteniveau. Het kenmerk _NoScript_ is standaard ingesteld op **beschikbaar** voor _moderne_ sites en **uitgeschakeld** voor _klassieke_ sites. Dit hangt af van uw tenantinstellingen.

Zie [set-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) en [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)voor meer informatie over deze cmdlets.

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Een oorsprong voor uw activa toevoegen

Met de cmdlet **add-PnPTenantCdnOrigin** kunt u een oorsprong definiëren. U kunt meerdere oorsprong definiëren. De origin is een URL die verwijst naar een SharePoint-bibliotheek of-map die de assets bevat die u wilt hosten door de CDN.
  
> [!IMPORTANT]
> U dient nooit bronnen te plaatsen die gebruikersgegevens bevatten of die in een openbare Origin als vertrouwelijk worden beschouwd.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

De waarde van _pad_ is het relatieve pad naar de bibliotheek of map met de assets. U kunt jokertekens gebruiken in aanvulling op relatieve paden. Voor de URL worden jokertekens ondersteund. Hiermee kunt u oorsprong maken die meerdere sites beslaat. Als u bijvoorbeeld alle activa in de map # # # # # # # # # # # # # # # # wilt opnemen in het CDN, typt u de volgende opdracht:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ De wijziging van het jokerteken * **/** kan alleen aan het begin van het pad worden gebruikt en komt overeen met alle URL-segmenten onder de opgegeven URL.
+ Het pad kan verwijzen naar een documentbibliotheek, map of site. Het pad _*/site1_ komt bijvoorbeeld overeen met alle documentbibliotheken onder de site.

U kunt een oorsprong met een specifiek relatief pad toevoegen. U kunt geen origin toevoegen met het volledige pad.

In dit voorbeeld wordt de persoonlijke oorsprong van de bibliotheek siteactiva op een specifieke site toegevoegd:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In dit voorbeeld wordt een persoonlijke oorsprong van de map _Map1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Als het pad een spatie bevat, kunt u het pad tussen dubbele aanhalingstekens plaatsen of de ruimte vervangen door de URL-codering %20. In het volgende voorbeeld wordt een persoonlijke oorsprong van de map _map 1_ toegevoegd aan de bibliotheek siteactiva van de siteverzameling:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.

> [!NOTE]
> Bij particuliere Origin moet de activa die vanaf een oorsprong worden gedeeld, een primaire versie hebben gepubliceerd voordat ze toegankelijk zijn vanuit het CDN.
  
Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. Dit kan 15 minuten duren.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Voorbeeld: een openbare Origin configureren voor uw basispagina's en voor de stijlbibliotheek voor SharePoint Online

Normaalgesproken zijn deze oorsprong voor u standaard ingesteld wanneer u Office 365 CDN inschakelt. Voer de volgende stappen uit als u deze handmatig wilt inschakelen.
  
+ Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de stijlbibliotheek definiëren als een openbare Origin.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de basispagina's definiëren als een openbare Origin.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.

Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. Dit kan 15 minuten duren.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Voorbeeld: een persoonlijke Origin configureren voor uw site-assets, sitepagina's en publicatie afbeeldingen voor SharePoint Online

+ Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de map siteactiva definiëren als persoonlijke Origin.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de map sitepagina's definiëren als persoonlijke Origin.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Met de cmdlet **add-PnPTenantCdnOrigin** kunt u de map met publicatie-afbeeldingen definiëren als persoonlijke Origin.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.

Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. Dit kan 15 minuten duren.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Voorbeeld: een persoonlijke Origin configureren voor een siteverzameling voor SharePoint Online

Met de cmdlet **add-PnPTenantCdnOrigin** kunt u een siteverzameling als persoonlijke Origin definiëren. Bijvoorbeeld:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Zie [add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)voor meer informatie over deze opdracht en de syntaxis.
  
Wanneer u de opdracht hebt uitgevoerd, wordt de configuratie door het systeem gesynchroniseerd via het datacenter. U ziet mogelijk een bericht _in behandeling_ waarvan de status van de SharePoint Online-Tenant wordt verwacht, zodat deze verbinding maakt met de CDN-service. Dit kan 15 minuten duren.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Het Office 365-CDN beheren

Wanneer u de CDN hebt ingesteld, kunt u wijzigingen aanbrengen in de configuratie wanneer u inhoud bijwerkt of de gewenste wijziging aanbrengt, zoals in deze sectie wordt beschreven.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Bronnen toevoegen, bijwerken of verwijderen uit het Office 365 CDN

Wanneer u de instellingsstappen hebt voltooid, kunt u nieuwe activa toevoegen en bestaande activa bijwerken of verwijderen wanneer u maar wilt. Breng de gewenste wijzigingen aan in de activa in de map of in de SharePoint-bibliotheek die u als een oorsprong hebt aangewezen. Als u een nieuw activum toevoegt, is het direct beschikbaar via het CDN. Als u echter het activum bijwerkt, duurt het maximaal vijftien minuten voordat de nieuwe versie beschikbaar is in het CDN.
  
Als u de locatie van de origin moet ophalen, kunt u de cmdlet **Get-PnPTenantCdnOrigin** gebruiken. Zie [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)voor informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Een oorsprong uit Office 365 CDN verwijderen

U kunt de toegang tot een map of een SharePoint-bibliotheek die u als een oorsprong hebt opgegeven, verwijderen. U kunt dit doen met behulp van de **Remove-PnPTenantCdnOrigin-** cmdlet.

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Zie [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)voor informatie over het gebruik van deze cmdlet.

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Een origin in het Office 365-CDN wijzigen

U kunt geen Origin wijzigen die u hebt gemaakt. In plaats daarvan verwijdert u de oorsprong en voegt u een nieuwe toe. Zie voor meer informatie [een origin verwijderen uit het Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) en [een origin voor uw assets toevoegen](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Het Office 365-CDN uitschakelen

Gebruik de cmdlet **set-PnPTenantCdnEnabled** om de CDN uit te schakelen voor uw organisatie. Als u zowel openbare als persoonlijke Origins voor het CDN hebt ingeschakeld, moet u de cmdlet twee keer uitvoeren, zoals in de volgende voorbeelden wordt weergegeven.
  
Als u het gebruik van openbare Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Als u het gebruik van de persoonlijke Origins in het CDN wilt uitschakelen, voert u de volgende opdracht in:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Zie [set-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)voor meer informatie over deze cmdlet.

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Het Office 365 CDN instellen en configureren met behulp van Office 365 CLI

Voor de procedures in deze sectie moet u [Office 365 cli](https://aka.ms/o365cli)hebben geïnstalleerd. Maak vervolgens verbinding met de Office 365-Tenant met behulp van de opdracht [login](https://pnp.github.io/office365-cli/cmd/login/) .

Voer de volgende stappen uit om de CDN in te stellen en te configureren voor het hosten van uw assets in SharePoint Online met behulp van Office 365 CLI.

<details>
  <summary>Klik om uit te vouwen</summary>

### <a name="enable-the-office-365-cdn"></a>Het Office 365 CDN inschakelen

U kunt de status van het Office 365 CDN in uw Tenant beheren met behulp van de CDN-opdracht [SPO](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) .

Als u het openbare CDN van Office 365 in uw Tenant wilt inschakelen, voert u het volgende uit:

```sh
spo cdn set --type Public --enabled true
```

Voer het volgende uit om het Office 365-CDN in te schakelen:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>De huidige status van het Office 365 CDN weergeven

Als u wilt controleren of het specifieke type van Office 365 CDN is ingeschakeld of uitgeschakeld, gebruikt u de opdracht [SPO CDN Get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) .

Voer het volgende uit om te controleren of het Office 365 openbare CDN is ingeschakeld:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>De Office 365 CDN-oorsprong weergeven

U kunt als volgt het momenteel geconfigureerde Office 365 openbare CDN-oorsprong uitvoeren:

```sh
spo cdn origin list --type Public
```

Zie [standaard CDN-oorsprong](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) voor informatie over de oorsprong die standaard wordt ingericht wanneer u Office 365 CDN inschakelt.

### <a name="add-an-office-365-cdn-origin"></a>Een Office 365 CDN-oorsprong toevoegen

> [!IMPORTANT]
> U dient nooit bronnen te plaatsen die in een SharePoint-documentbibliotheek zijn geconfigureerd als een openbare Origin.

Gebruik de opdracht [toevoegen van SPO CDN Origin](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) voor het definiëren van een CDN-oorsprong. U kunt meerdere oorsprong definiëren. De origin is een URL die verwijst naar een SharePoint-bibliotheek of-map die de assets bevat die u wilt hosten door de CDN.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Waar `path` is het relatieve pad naar de map die de elementen bevat. U kunt jokertekens gebruiken in aanvulling op relatieve paden.

Als u alle activa in de **Galerie met basispagina's** van alle sites als een openbare Origin wilt opnemen, voert u het volgende uit:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Voer het volgende uit om een persoonlijke Origin te configureren voor een bepaalde siteverzameling:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Na het toevoegen van een CDN-oorsprong kan het tot 15 minuten duren voordat u bestanden kunt ophalen via de CDN-service. U kunt controleren of de bepaalde oorsprong al is ingeschakeld met de opdracht [SPO CDN Origin List](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) .

### <a name="remove-an-office-365-cdn-origin"></a>Een Office 365 CDN-oorsprong verwijderen

Met de opdracht [verwijderen van SPO CDN Origin Origin](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) verwijdert u een CDN-oorsprong voor het opgegeven CDN-type.

Voer het volgende uit om een openbare Origin te verwijderen uit de CDN-configuratie:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Het verwijderen van een CDN-oorsprong heeft geen invloed op de bestanden die zijn opgeslagen in een documentbibliotheek die overeenkomen met die waarvan de oorsprong Als ernaar werd verwezen met de SharePoint-URL, wordt in SharePoint automatisch de oorspronkelijke URL weergegeven die verwijst naar de documentbibliotheek. Als ernaar verwijste verwijzingen via een openbare CDN-URL, wordt de koppeling verbroken en moet u deze handmatig wijzigen.

### <a name="modify-an-office-365-cdn-origin"></a>Een Office 365 CDN Origin wijzigen

Het is niet mogelijk om een bestaande CDN-oorsprong te wijzigen. In plaats daarvan dient u de eerder opgegeven CDN-oorsprong te verwijderen met de `spo cdn origin remove` opdracht en een nieuwe naam toe te voegen met de `spo cdn origin add` opdracht.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>De bestandstypen wijzigen die u wilt opnemen in het Office 365 CDN

Standaard zijn de volgende bestandstypen opgenomen in de CDN: _. CSS,. EOT,. GIF,. ICO,. JPEG,. jpg,. js,. folder,. png,. js_,. Als u extra bestandstypen in het CDN wilt opnemen, kunt u de CDN-configuratie wijzigen met de opdracht [SPO CDN-beleidsset](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) .

> [!NOTE]
> Wanneer u de lijst met bestandstypen wijzigt, overschrijft u de momenteel gedefinieerde lijst. Als u extra bestandstypen wilt opnemen, gebruikt u eerst de opdracht [SPO CDN-beleidslijst](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) om erachter te komen welke bestandstypen momenteel zijn geconfigureerd.

Voer de volgende stappen uit om het type _JSON_ -bestand toe te voegen aan de standaardlijst met bestandstypen die in het openbare CDN zijn opgenomen:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>De lijst met site classificaties wijzigen die u wilt uitsluiten van Office 365 CDN

Met de opdracht [SPO CDN-beleidsinstelling](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) kunt u de site classificaties uitsluiten die u niet beschikbaar wilt maken in het CDN. Standaard zijn geen site classificaties uitgesloten.

> [!NOTE]
> Wanneer u de lijst met uitgesloten site classificaties wijzigt, overschrijft u de momenteel gedefinieerde lijst. Als u extra classificaties wilt uitsluiten, gebruikt u eerst de opdracht [SPO CDN-beleidslijst](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) om erachter te komen welke indelingen zijn geconfigureerd.

Als u sites wilt uitsluiten die zijn geclassificeerd als _HBI_ uit het openbare CDN, voert u

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Het Office 365-CDN uitschakelen

Als u het Office 365-CDN wilt uitschakelen, gebruikt u de volgende `spo cdn set` opdracht:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Uw CDN-bronnen gebruiken

Nu u de CDN en de geconfigureerde oorsprong en beleidsregels hebt ingeschakeld, kunt u uw CDN-activa gaan gebruiken.

In deze sectie vindt u meer informatie over het gebruik van CDN-Url's op uw SharePoint-pagina's en inhoud, zodat aanvragen voor assets in openbare en persoonlijke Origins worden doorgestuurd naar het CDN.

+ [Koppelingen naar CDN-assets bijwerken](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Activa gebruiken in openbare oorsprong](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Werken met assets in persoonlijke oorsprong](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Voor informatie over het gebruik van het CDN voor het hosten van webonderdelen aan de clientzijde, raadpleegt u het onderwerp [uw webonderdeel op de client Toep kelen vanuit Office 365 CDN (Hallo wereld Part 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).

> [!NOTE]
> Als u de map _ClientSideAssets_ toevoegt aan de lijst met **persoonlijke** CDN-oorsprong, kunnen aangepaste webonderdelen met CDN-host niet worden weergegeven. Bestanden die worden gebruikt door webonderdelen van SPFX kunnen alleen gebruikmaken van het openbare CDN en de map ClientSideAssets is een standaardoorsprong voor openbare CDN. 

### <a name="updating-links-to-cdn-assets"></a>Koppelingen naar CDN-assets bijwerken

Als u assets wilt gebruiken die u hebt toegevoegd aan een oorsprong, moet u een koppeling naar het oorspronkelijke bestand bijwerken met het pad naar het bestand in de oorsprong.

+ Bewerk de pagina of inhoud die koppelingen bevat naar activa die u hebt toegevoegd aan een oorsprong. U kunt ook een van de volgende methoden gebruiken om koppelingen te zoeken en te vervangen op een Enter-site of siteverzameling als u de koppeling naar een bepaald activum overal wilt bijwerken.
+ Voor elke koppeling naar een activum in een oorsprong, vervangt u het pad door het pad naar het bestand in de CDN-oorsprong. U kunt relatieve paden gebruiken.
+ Sla de pagina of de inhoud op.

Kijk bijvoorbeeld naar de afbeelding _/site/SiteAssets/images/image.png_die u hebt gekopieerd naar de map documentbibliotheek _/site/CDN_origins/Public/_. Als u het CDN-activum wilt gebruiken, vervangt u het oorspronkelijke pad naar de locatie van het afbeeldingsbestand met het pad naar de oorsprong zodat u de nieuwe URL _/site/CDN_origins/public/image.png_.

Als u de volledige URL naar het activum wilt gebruiken in plaats van een relatief pad, maakt u de koppeling als volgt:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> In het algemeen is het niet mogelijk om de Url's rechtstreeks in het CDN te hardcode. U kunt echter handmatig Url's maken voor assets in openbare oorsprong. Zie voor meer informatie [HARDCODING CDN url's voor openbare assets](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).

Als u wilt weten hoe u kunt controleren of de activa worden bediend via de CDN, raadpleegt u [Hoe kan ik controleren of de activa worden geleverd door de CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in de sectie [problemen met Office 365 CDN oplossen](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .

### <a name="using-assets-in-public-origins"></a>Activa gebruiken in openbare oorsprong

Met de **functie publiceren** in SharePoint Online worden de url's van activa die in openbare Origin-Origins zijn opgeslagen, automatisch herschreven naar hun CDN-equivalenten, zodat assets van de CDN-service in plaats van SharePoint worden bediend.

Als uw oorsprong zich op een site bevindt waarop de publicatiefunctie is ingeschakeld en de activa die u wilt overzetten naar de CDN, in een van de volgende categorieën staan, worden Url's automatisch herschreven voor activa in de oorsprong, mits het activum niet is uitgesloten door een CDN-beleid.

Hieronder ziet u een overzicht van de koppelingen die automatisch worden herschreven met de SharePoint-publicatiefunctie:

+ Url's van Hyper LINK/LINK/CSS in de klassieke publicatiepagina-antwoorden
  + Dit omvat afbeeldingen die zijn toegevoegd door auteurs binnen de HTML-inhoud van een pagina.
+ Afbeeldingen van afbeeldingen in de webonderdelen afbeeldingsbibliotheek
+ Afbeeldingsvelden in de REST-API van de SPList (RenderListDataAsStream)
  + Het nieuwe eigenschappen _ImageFieldsToTryRewriteToCdnUrls_ gebruiken om een door komma's gescheiden lijst met velden te maken
  + Ondersteuning voor hyperlink velden en PublishingImage velden
+ SharePoint-afbeeldingsweergaven

In het volgende diagram ziet u de werkstroom wanneer SharePoint een aanvraag ontvangt voor een pagina die activa van een openbare oorsprong bevat.

![Werkstroom diagram: Office 365 CDN-activa ophalen uit een openbare Origin](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Werkstroom: Office 365 CDN-activa ophalen uit een openbare Origin")

> [!TIP]
> Als u automatisch herschrijven voor specifieke Url's wilt uitschakelen op een pagina, kunt u de pagina uitchecken en de queryreeksparameter toevoegen **? NoAutoReWrites = True** naar het einde van elke koppeling die u wilt uitschakelen.

#### <a name="hardcoding-cdn-urls-for-public-assets"></a>CDN-Url's voor hardcoding voor openbare assets

Als de _publicatie_ functie niet is ingeschakeld voor een openbare Origin of als het activum niet een van de koppelingstypen is die worden ondersteund door de functie automatisch herschrijven van de CDN-service, kunt u handmatig url's maken op de CDN-locatie van de assets en deze url's gebruiken in uw inhoud.

> [!NOTE]
> U kunt geen CDN-Url's hardcode naar assets in een persoonlijke Origin omdat het vereiste toegangstoken dat de laatste sectie van de URL vormt, wordt gegenereerd op het moment dat de resource wordt opgevraagd.

Voor openbare CDN-assets ziet de URL-indeling er als volgt uit:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Vervang **TenantHostName** door de naam van de Tenant. Voorbeeld:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a>Werken met assets in persoonlijke oorsprong

Er is geen extra configuratie vereist voor het gebruik van assets in persoonlijke oorsprong. Url's worden in SharePoint Online automatisch herschreven voor activa in persoonlijke oorsprong, zodat aanvragen voor deze activa altijd vanuit het CDN worden verzonden. U kunt geen Url's handmatig maken voor CDN-assets in persoonlijke Origins omdat deze Url's tokens bevatten die automatisch moeten worden gegenereerd door SharePoint Online op het moment dat het activum wordt opgevraagd.

De toegang tot assets in persoonlijke Origins wordt beschermd door dynamische tokens die op basis van gebruikersmachtigingen voor de oorsprong worden vastgelegd, met de voorbehoud van de namen in de volgende secties. Gebruikers moeten minimaal **Lees** toegang hebben tot de oorsprong van de CDN om inhoud weer te geven.

In het volgende diagram ziet u de werkstroom wanneer SharePoint een aanvraag ontvangt voor een pagina die activa van een persoonlijke oorsprong bevat.

![Werkstroom diagram: bij het ophalen van Office 365 CDN-assets van een persoonlijke Origin](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Werkstroom: Office 365 CDN-activa ophalen van een persoonlijke oorsprong")

#### <a name="token-based-authorization-in-private-origins"></a>Autorisatie op basis van tokens in persoonlijke oorsprong

Toegang tot assets in persoonlijke Origins in het Office 365 CDN wordt verleend door tokens die worden gegenereerd door SharePoint Online. Gebruikers die al machtigingen hebben voor toegang tot de map of bibliotheek die door de origin zijn aangewezen, krijgen automatisch tokens te ontvangen waarmee de gebruiker toegang kan krijgen tot het bestand op basis van hun machtigingsniveau. De toegangstokens zijn geldig gedurende 30 tot 90 minuten na het genereren ervan om token herhalings aanvallen te helpen voorkomen.

Nadat het toegangstoken is gegenereerd, retourneert SharePoint Online een aangepaste URI naar de client met twee autorisatie parameters _eten_ (Edge Authorization token) en _Oat_ (origin Authorization token). De structuur van elk token wordt _< ' verlooptijd in de epoche-tijdnotatie ' >__< ' veilige handtekening ' >_. Bijvoorbeeld:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Iedereen in het bezit van het token kan toegang krijgen tot de resource in het CDN. Url's met deze toegangstokens worden echter alleen via HTTPS gedeeld, dus tenzij de URL expliciet wordt gedeeld door een eindgebruiker voordat het token verloopt, is het activum niet toegankelijk voor niet-geautoriseerde gebruikers.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Machtigingen op item niveau worden niet ondersteund voor assets in persoonlijke Origin.

Houd er rekening mee dat SharePoint Online geen machtigingen op itemniveau biedt voor assets in persoonlijke oorsprong. Wanneer een bestand zich bevindt `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` , hebben gebruikers voor het openen van het bestand de volgende voorwaarden:

|Gebruiker  |Machtigingen  |Effectieve toegang  |
|---------|---------|---------|
|Gebruiker 1     |Toegang heeft tot Map1         |Toegang tot image1.jpg vanuit het CDN         |
|Gebruiker 2     |Heeft geen toegang tot Map1         |Geen toegang tot image1.jpg vanuit het CDN         |
|Gebruiker 3     |Heeft geen toegang tot Map1, maar krijgt expliciet toestemming voor toegang tot image1.jpg in SharePoint Online         |Toegang tot het activum image1.jpg rechtstreeks vanuit SharePoint Online, maar niet in het CDN         |
|Gebruiker 4     |Toegang tot Map1, maar de toegang tot image1.jpg in SharePoint Online is expliciet geweigerd         |Kan geen toegang krijgen tot het activum via SharePoint Online, maar het is niet mogelijk om toegang te krijgen tot het bestand in SharePoint Online         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Problemen oplossen met het Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Hoe controleer ik of de assets worden bediend door de CDN?

Wanneer u koppelingen naar CDN-assets aan een pagina hebt toegevoegd, kunt u bevestigen dat het activum wordt bediend door te browsen door op de pagina te klikken, met de rechtermuisknop op de afbeelding te klikken en de afbeeldings-URL te reviseren.

U kunt ook de ontwikkelhulpprogramma's van de browser gebruiken om de URL voor elk activum op een pagina weer te geven of een hulpprogramma voor netwerktracering van derden te gebruiken.

> [!NOTE]
> Als u een netwerkprogramma gebruikt, zoals Fiddler, om uw activa te testen buiten het activum van een SharePoint-pagina, moet u handmatig de koptekst voor de linker-header toevoegen `https://yourdomain.sharepoint.com` aan de aanvraag voor het opvragen van de URL van uw SharePoint Online-Tenant.

U kunt CDN-Url's niet rechtstreeks in een webbrowser testen, omdat u een verwijzing moet hebben van SharePoint Online. Als u echter de URL van de CDN-activum toevoegt aan een SharePoint-pagina en vervolgens de pagina in een browser opent, ziet u het CDN-activum dat op de pagina wordt weergegeven.

Zie [Microsoft Edge-ontwikkelaars Programma's](https://docs.microsoft.com/microsoft-edge/devtools-guide)voor meer informatie over het gebruik van de hulpmiddelen voor ontwikkelaars in de Microsoft Edge-browser.

Als u een korte video in het [YouTube-kanaal van de SharePoint-ontwikkel patronen en-procedures](https://aka.ms/sppnp-videos) wilt bekijken waarin wordt uitgelegd hoe u kunt controleren of uw CDN werkt, raadpleegt u [uw CDN-gebruik verifiëren en zorgen voor optimale netwerkconnectiviteit](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Waarom zijn activa van een nieuwe Origin niet beschikbaar?
Activa in nieuwe oorsprong zijn niet onmiddellijk beschikbaar voor gebruik, omdat het tijd is voor het doorgeven van de registratie via de CDN en voor de activa die van de origin worden geüpload naar de CDN-opslag. De tijd die nodig is voor het maken van activa in de CDN, is afhankelijk van het aantal activa en de grootte van de bestanden.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Het webonderdeel van de client of de SharePoint Framework-oplossing werkt niet

Wanneer u Office 365 CDN voor openbare oorsprong inschakelt, worden deze standaard Origins automatisch gemaakt met de CDN-service:

+ */MASTERPAGE
+ */STYLE BIBLIOTHEEK
+ */CLIENTSIDEASSETS

Als de/clientsideassets-oorsprong ontbreekt, mislukt SharePoint Framework-oplossingen en worden er geen waarschuwings-of foutberichten gegenereerd. Deze oorsprong kan ontbreken omdat de CDN is ingeschakeld en de parameter _NoDefaultOrigins_ is ingesteld op **$True**, of omdat de oorsprong handmatig is verwijderd.

U kunt nagaan welke oorsprong aanwezig zijn met de volgende PowerShell-opdracht:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

U kunt ook het volgende controleren met Office 365 CLI:

``` powershell
spo cdn origin list
```

De origin toevoegen in PowerShell:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

De origin toevoegen in Office 365 CLI:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Welke PowerShell-modules en CLI-shells moet ik gebruiken met Office 365 CDN?

U kunt ervoor kiezen om te werken met Office 365 CDN met behulp van de PowerShell-module van **SharePoint Online Management Shell** of **Office 365 cli**.

+ [Aan de slag met SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Office 365 CLI installeren](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Zie ook

[Netwerken voor content levering](https://aka.ms/o365cdns)

[Network planning and performance tuning for Office 365](https://aka.ms/tune)

[SharePoint-prestatie serie-Office 365 CDN-VideoReeks](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
