---
title: Netwerkverzoeken in Office voor Mac
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: In dit artikel wordt beschreven welke eindpunten en URL's Office voor Mac toepassingen proberen te bereiken en welke services worden geleverd.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689265"
---
# <a name="network-requests-in-office-for-mac"></a>Netwerkverzoeken in Office voor Mac

Office voor Mac-toepassingen bieden een native app-ervaring op het macOS-platform. Elke app is ontworpen om te werken in verschillende scenario's, waaronder staten waarin er geen netwerktoegang beschikbaar is. Wanneer een computer is verbonden met een netwerk, maken de toepassingen automatisch verbinding met een reeks webservices om verbeterde functionaliteit te bieden. In de volgende informatie wordt beschreven welke eindpunten en URL's de toepassingen proberen te bereiken en welke services worden geleverd. Deze informatie is handig bij het oplossen van problemen met netwerkconfiguratie en het instellen van beleid voor netwerkproxyservers. De details in dit artikel zijn bedoeld als aanvulling op [het artikel Office 365 URL](urls-and-ip-address-ranges.md)en adresbereiken, dat eindpunten bevat voor computers met Microsoft Windows. Tenzij vermeld, is de informatie in dit artikel ook van toepassing op Office 2019 voor Mac en Office 2016 voor Mac, die beschikbaar zijn als een een-time aankoop in een winkel of via een volumelicentieovereenkomst. 

  
Het grootste deel van dit artikel bestaat uit tabellen met informatie over netwerk-URL's, het type en de beschrijving van de service of functie die door dat eindpunt wordt geleverd. Elk van de Office apps kan verschillen in de service en het gebruik van eindpunten. De volgende apps worden gedefinieerd in de onderstaande tabellen:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
Het type URL wordt als volgt gedefinieerd:
  
- ST: Statisch: de URL wordt hard gecodeerd in de clienttoepassing.
    
- SS: Semi-Static - De URL wordt gecodeerd als onderdeel van een webpagina of omleiding.
    
- CS: Config-service: de URL wordt geretourneerd als onderdeel van Office Configuratieservice.

    
## <a name="office-for-mac-default-configuration"></a>Office voor Mac standaardconfiguratie

 **Installatie en updates**
  
De volgende netwerk-eindpunten worden gebruikt om het Office voor Mac te downloaden van de Microsoft-Content Delivery Network (CDN).
  
|**URL**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365 Installatieportal doorgestuurde koppelingsservice naar meest recente installatiepakketten.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |Locatie van installatiepakketten op de Content Delivery Network.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |Locatie van installatiepakketten op de Content Delivery Network.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Eindpunt beheerbeheer voor Microsoft AutoUpdate  <br/> |
   
 **Eerste app-start**
  
Er wordt contact opgenomen met de volgende netwerk-eindpunten bij de eerste start van een Office-app. Deze eindpunten bieden verbeterde Office functionaliteit voor gebruikers en er wordt contact opgenomen met de URL's, ongeacht het licentietype (inclusief installaties voor volumelicenties).
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |'Flighting'-configuratie: hiermee kunt u functies oplichten en experimenteren.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |'Flighting' Network Configuration Test  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |'Flighting' Network Configuration Test  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Configuratieservice : hoofdlijst met service-eindpunten.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Regels Telemetrie downloaden: informeert de client over welke gegevens en gebeurtenissen moeten worden geüpload naar de telemetrieservice.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |N  <br/> |CS  <br/> |OneNote Telemetrieservice  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office Telemetrie Upload Reporting - 'Heartbeart' en foutgebeurtenissen die zich voordoen op de client, worden geüpload naar de telemetrieservice.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office Sjabloonservice: biedt gebruikers online documentsjablonen.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office Sjablonen Downloads - Storage van PNG-sjabloonafbeeldingen.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Store-configuratie voor Office apps.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office Document Integration Services Catalog (lijst met services en eindpunten) en Home Realm Discovery.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Resources voor Home Realm Discovery v2 (15,40 en hoger)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft AutoUpdate-manifesten : controleert of er updates beschikbaar zijn  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft Ajax JavaScript-bibliotheek  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-app voor Office configuratie en resources.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing Kaart-app voor Office en resources.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Personen Graph app voor Office en resources.  <br/> |
|```https://www.onenote.com/```  <br/> |N  <br/> |ST  <br/> |Wat is nieuwe inhoud voor OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |ST  <br/> |Nieuwe inhoud voor OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |N  <br/> |SS  <br/> |Wat zijn nieuwe afbeeldingen voor OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |Ondersteuningsservice in de app.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |E-mailaccountdetectieservice.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook AutoDiscovery  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook eindpunt voor Microsoft 365 service.  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |Pictogrammen voor Outlook invoegvoegingen.  <br/> |
   
> [!NOTE]
> De Office Configuration Service fungeert als een automatische detectieservice voor alle Microsoft Office clients, niet alleen voor Mac. De eindpunten die in het antwoord worden geretourneerd, zijn semi-statisch, omdat de wijziging zeer zeldzaam is, maar nog steeds mogelijk is. 
  
 **Aanmelden**
  
Er wordt contact opgenomen met de volgende netwerk-eindpunten wanneer u zich aanmeldt bij cloudopslag. Afhankelijk van uw accounttype kan er contact worden opgenomen met verschillende services. Bijvoorbeeld:
  
- **MSA: Microsoft-account** - meestal gebruikt voor scenario's voor consumenten en detailhandel 
    
- **OrgID: Organisatieaccount** - meestal gebruikt voor commerciële scenario's 
    
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows Autorisatieservice  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365 Aanmeldingsservice (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft Account Login Service (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |Microsoft Account Login Service Helper (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365 Login Branding (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Document en locaties Storage Locator  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Meest recent gebruikte documentservice (MRU)  <br/> |
   
> [!NOTE]
> Voor abonnements- en detailhandelslicenties activeert u het product door u aan te melden en kunt u toegang krijgen tot cloudresources, zoals OneDrive. Voor installaties met volumelicenties worden gebruikers nog steeds gevraagd zich (standaard) aan te melden, maar dat is alleen vereist voor toegang tot cloudbronnen, omdat het product al is geactiveerd. 
  
 **Productactivering**
  
De volgende netwerk-eindpunten zijn van toepassing op Microsoft 365 activeringen van abonnementen en retaillicenties. Dit geldt met name niet voor installaties met volumelicenties.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office Licentieservice  <br/> |
   
 **Nieuwe inhoud**
  
De volgende netwerk-eindpunten zijn alleen van toepassing Microsoft 365 abonnement.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |Wat is nieuwe JSON-pagina-inhoud.  <br/> |
   
 **Onderzoeker**
  
De volgende netwerk-eindpunten zijn alleen van toepassing Microsoft 365 abonnement.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Researcher Web Service  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |Statische inhoud van onderzoeker  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |Onderzoeker-inhoudsprovider  <br/> |
   
 **Slim zoeken**
  
De volgende netwerk-eindpunten zijn van toepassing op zowel Microsoft 365 abonnementen als retail-/volumelicentieactiveringen.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights Web Service  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery-bibliotheek  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |Ondersteuning voor JavaScript-bibliotheek  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights Content Provider  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Insights Content Provider  <br/> |
   
 **PowerPoint Designer**
  
De volgende netwerk-eindpunten zijn alleen van toepassing Microsoft 365 abonnement.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint Designer webservice  <br/> |
   
 **PowerPoint QuickStarter**
  
De volgende netwerk-eindpunten zijn alleen van toepassing Microsoft 365 abonnement.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint QuickStarter-webservice  <br/> |
   
 **Een glimlach/frons verzenden**
  
De volgende netwerk-eindpunten zijn van toepassing op zowel Microsoft 365 abonnementen als retail-/volumelicentieactiveringen.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |Een glimlachservice verzenden  <br/> |
   
 **Contact opnemen met ondersteuning**
  
De volgende netwerk-eindpunten zijn van toepassing op zowel Microsoft 365 abonnementen als retail-/volumelicentieactiveringen.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |Contact opnemen met ondersteuningsservice  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |Ondersteuningsservice in de app  <br/> |
   
 **Opslaan als PDF**
  
De volgende netwerk-eindpunten zijn van toepassing op zowel Microsoft 365 abonnementen als retail-/volumelicentieactiveringen.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Word-documentconversieservice (PDF)  <br/> |
   
 **Office Apps (ook wel invoegingen)**
  
De volgende netwerk-eindpunten zijn van toepassing op zowel Microsoft 365 abonnementen als retail-/volumelicentieactiveringen wanneer Office app-invoegingen worden vertrouwd.
  
|**URL**|**Apps**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Office-app store-configuratie  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-appbronnen  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |Bing App-resources in kaart brengen  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |Personen Graph app-resources  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office Omleidingsservice  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |Office JavaScript-bibliotheken  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |Telemetrie- en rapportageservice voor Office apps  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft Ajax JavaScript-bibliotheek  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft Ajax JavaScript-bibliotheek  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Office JavaScript-bibliotheken  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Ondersteuningsbronnen  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Ondersteuningsbronnen  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |Ondersteuningsbronnen  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript-bibliotheek  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |Foutrapportage  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |Lettertypebronnen  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetrieservice  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |Telemetrierapportage  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store Activabibliotheek  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-paginabronnen  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |Wikipedia-mediabronnen  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia sandbox frame  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |Kaartsjablonen  <br/> |
   
 **Veilige koppelingen**
  
Het volgende netwerk-eindpunt is alleen van toepassing op alle Office voor Microsoft 365 abonnement.
  
|**URL**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft Safe Koppelingsservice  <br/> |
   
 **Crashrapportage**
  
Het volgende netwerk-eindpunt is van toepassing op alle Office voor zowel Microsoft 365-abonnementen als retail-/volumelicentieactiveringen. Wanneer een proces onverwacht vast loopt, wordt er een rapport gegenereerd en verzonden naar de Watson-service.
  
|**URL**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Microsoft Error Reporting Service  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office Collaborative Insights Service  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opties voor het verminderen van netwerkaanvragen en -verkeer

De standaardconfiguratie van Office voor Mac biedt de beste gebruikerservaring, zowel wat betreft functionaliteit als het up-to-date houden van de computer. In sommige scenario's wilt u mogelijk voorkomen dat toepassingen contact opnemen met netwerk-eindpunten. In deze sectie worden de opties besproken om dit te doen.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Cloud-Sign-In en Office Add-Ins
  
Klanten van volumelicenties hebben mogelijk een strikt beleid voor het opslaan van documenten in cloudopslag. De volgende voorkeur per toepassing kan worden ingesteld om MSA/OrgID-aanmelding uit te schakelen en toegang tot Office invoegtoepassing.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Als gebruikers toegang proberen te krijgen tot Sign-In, zien ze een foutmelding dat er geen netwerkverbinding aanwezig is. Omdat deze voorkeur ook online productactivering blokkeert, mag deze alleen worden gebruikt voor installaties met volumelicenties. Met deze voorkeur wordt met name voorkomen Office toepassingen toegang krijgen tot de volgende eindpunten:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Alle eindpunten in de bovenstaande sectie Aanmelden.
    
- Alle eindpunten die worden weergegeven in de sectie 'Slim zoeken' hierboven.
    
- Alle eindpunten in de bovenstaande sectie Productactivering.
    
- Alle eindpunten die worden weergegeven in de sectie 'Office Apps (aka invoegvoegingen)' hierboven.
    
Als u de volledige functionaliteit voor de gebruiker opnieuw wilt instellen, stelt u de voorkeur in op '2' of verwijdert u deze.
  
> [!NOTE]
> Voor deze voorkeur Office voor Mac build 15,25 [160726] of hoger vereist. 
  
### <a name="telemetry"></a>Telemetrie 
  
Office voor Mac verzendt regelmatig telemetriegegevens terug naar Microsoft. Gegevens worden geüpload naar het eindpunt 'Nexus'. Met de telemetriegegevens kan het technische team de status en onverwachte gedragingen van elke Office-app. Er zijn twee categorieën telemetrie:
  
- **Heartbeat** bevat versie- en licentiegegevens. Deze gegevens worden direct na het starten van de app verzonden. 
    
- **Gebruik** bevat informatie over hoe apps worden gebruikt en niet-fatale fouten. Deze gegevens worden elke 60 minuten verzonden. 
    
Microsoft neemt uw privacy zeer serieus. U kunt meer lezen over het gegevensverzamelingsbeleid van Microsoft op [https://privacy.microsoft.com](https://privacy.microsoft.com) . Als u wilt voorkomen dat toepassingen telemetrie 'Gebruik' verzenden, kan de voorkeur **SendAllTelemetryEnabled** worden aangepast. De voorkeur is per toepassing en kan worden ingesteld via macOS-configuratieprofielen of handmatig vanuit Terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

Heartbeat-telemetrie wordt altijd verzonden en kan niet worden uitgeschakeld.
  
### <a name="crash-reporting"></a>Crashrapportage
  
Wanneer er een fatale toepassingsfout optreedt, wordt de toepassing onverwacht beëindigd en wordt er een crashrapport geüpload naar de 'Watson'-service. Het crashrapport bestaat uit een call-stack, de lijst met stappen die de toepassing heeft verwerkt voorafgaand aan de crash. Met deze stappen kan het technische team de exacte functie identificeren die is mislukt en waarom.
  
In sommige gevallen loopt de toepassing vast door de inhoud van een document. Als de app het document als oorzaak identificeert, wordt de gebruiker gevraagd of het goed is om het document ook samen met de stapel met de oproep te verzenden. Gebruikers kunnen een weloverwogen keuze maken voor deze vraag. IT-beheerders hebben mogelijk strikte vereisten voor het verzenden van documenten en besluiten namens de gebruiker om nooit documenten te verzenden. De volgende voorkeur kan worden ingesteld om te voorkomen dat documenten worden verzonden en om de prompt naar de gebruiker te onderdrukken:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Als **SendAllTelemetryEnabled** is ingesteld op **ONWAAR,** is alle crashrapportage voor dat proces uitgeschakeld. Als u crashrapportage wilt inschakelen zonder telemetrie te verzenden, kunt u de volgende voorkeur instellen: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Updates
  
Microsoft brengt Office voor Mac regelmatig updates uit (meestal eenmaal per maand). We raden gebruikers en IT-beheerders ten zeerste aan om machines up-to-date te houden om ervoor te zorgen dat de meest recente beveiligingsupdates worden geïnstalleerd. In gevallen waarin IT-beheerders machine-updates nauwlettend willen controleren en beheren, kan de volgende voorkeur worden ingesteld om te voorkomen dat het AutoUpdate-proces automatisch productupdates detecteert en aanbiedt:
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Verzoeken blokkeren met een firewall/proxy
  
Als uw organisatie aanvragen voor URL's blokkeert via een firewall of proxyserver, moet u de URL's in dit document configureren als toegestaan of blokkeren met een 40X-antwoord (bijvoorbeeld 403 of 404). Met een 40X-antwoord kunnen de Office-toepassingen het onvermogen om toegang tot de resource te krijgen, accepteren en biedt het een snellere gebruikerservaring dan alleen het laten vallen van de verbinding, waardoor de client op zijn beurt opnieuw moet proberen.
  
Als voor uw proxyserver verificatie is vereist, wordt een antwoord van 407 geretourneerd naar de client. Voor de beste ervaring, zorg ervoor dat u Office voor Mac builds 15.27 of hoger gebruikt, aangezien deze specifieke oplossingen bevatten voor het werken met NTLM- en Kerberos-servers.
  
  
## <a name="see-also"></a>Zie ook

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

