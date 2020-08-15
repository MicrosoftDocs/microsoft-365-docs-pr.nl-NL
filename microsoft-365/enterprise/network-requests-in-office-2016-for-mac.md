---
title: Netwerkaanvragen in Office voor Mac
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
description: In dit artikel wordt beschreven welke eindpunten en Url's Office voor Mac-toepassingen willen bereiken en welke services beschikbaar zijn.
ms.openlocfilehash: b777b4ea7e03495cb6389be8fe05e96a26fd9664
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689265"
---
# <a name="network-requests-in-office-for-mac"></a>Netwerkaanvragen in Office voor Mac

Office voor Mac-toepassingen bieden een ingebouwde app-ervaring op het macOS-platform. Elke app is ontworpen voor gebruik in diverse scenario's, waaronder Staten waarbij geen netwerktoegang beschikbaar is. Wanneer een computer is verbonden met een netwerk, kunnen de toepassingen automatisch verbinding maken met een reeks webservices om uitgebreide functionaliteit te geven. In de volgende informatie wordt beschreven welke eindpunten en Url's de toepassingen willen bereiken en welke services beschikbaar zijn. Deze informatie is nuttig voor het oplossen van problemen met de netwerkconfiguratie en het instellen van beleid voor netwerkproxy servers. De informatie in dit artikel is bedoeld om het [artikel Office 365 URL en](urls-and-ip-address-ranges.md)adresbereiken aan te vullen, waaronder eindpunten voor computers met Microsoft Windows. Tenzij anders wordt vermeld, is de informatie in dit artikel ook van toepassing op Office 2019 voor Mac en Office 2016 voor Mac, dat beschikbaar is als eenmalige aankoop vanuit een winkel of via een Volume Licensing Agreement. 

  
In het meeste van dit artikel vindt u tabellen waarin de netwerk-Url's, typen en beschrijvingen van de service of functie van dit eindpunt worden beschreven. Elk van de Office-apps kan verschillen van de service en het gebruik van het eindpunt. In de volgende tabellen worden de volgende apps gedefinieerd:
  
- W: Word
- P: PowerPoint
- X: Excel
- O: Outlook
- N: OneNote
   
Het type URL wordt als volgt gedefinieerd:
  
- ST: statisch-de URL is hard gecodeerd in de clienttoepassing.
    
- SS: semi-statisch-de URL is gecodeerd als onderdeel van een webpagina of redirector.
    
- CS: config service-de URL wordt geretourneerd als onderdeel van de Office Configuration service.

    
## <a name="office-for-mac-default-configuration"></a>Standaardconfiguratie van Office voor Mac

 **Installatie en updates**
  
De volgende netwerkeindpunten worden gebruikt om het installatieprogramma voor Office voor Mac te downloaden van Microsoft CDN (Content Delivery Network).
  
|**URL**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |KT  <br/> |Microsoft 365-installatie Portal forward link-service naar de nieuwste installatiepakketten.  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |VEREFFEN  <br/> |Locatie van installatiepakketten op het Content Delivery Network.  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |VEREFFEN  <br/> |Locatie van installatiepakketten op het Content Delivery Network.  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |KT  <br/> |Beheer van het beheerpunt voor Microsoft AutoUpdate  <br/> |
   
 **Eerste keer starten van app**
  
De volgende netwerkeindpunten worden bij de eerste keer starten van een Office-app contact opgenomen. Deze eindpunten zorgen voor uitgebreide Office-functionaliteit voor gebruikers en de Url's worden opgenomen, ongeacht het type licentie (inclusief volume licentie-installaties).
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |KT  <br/> |' Flighting ', zodat u zich kunt uitlichten en experimenteert.  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |KT  <br/> |Test voor netwerkconfiguratie van flighting  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |KT  <br/> |Test voor netwerkconfiguratie van flighting  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |KT  <br/> |Office Configuration service: hoofdlijst met Service-eindpunten.  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |KT  <br/> |Office-regels voor telemetrie downloaden: informeert de client over welke gegevens en gebeurtenissen moeten worden geüpload naar de telemetrie-service.  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |P  <br/> |Support  <br/> |OneNote-telemetrie-service  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |KT  <br/> |Office Telemetry upload-rapporten: ' heartbeat ' en foutgebeurtenissen die optreden op de client worden geüpload naar de telemetrie-service.  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |Support  <br/> |Office-sjabloon service: biedt gebruikers met online documentsjablonen.  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |Support  <br/> |Downloads van Office-sjablonen: opslag van PNG-sjabloon afbeeldingen.  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |Support  <br/> |Store-configuratie voor Office-apps.  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |Support  <br/> |Catalogus van Office document Integration Services (lijst met Services en eindpunten) en voor thuis-realm-detectie.  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |Support  <br/> |Bronnen voor thuis-realm-detectie v2 (15,40 en hoger)  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |KT  <br/> |Microsoft AutoUpdate-manifesten: Hiermee wordt gecontroleerd of er updates beschikbaar zijn  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |VEREFFEN  <br/> |Microsoft AJAX JavaScript-bibliotheek  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |VEREFFEN  <br/> |Wikipedia-app voor Office-configuratie en-bronnen.  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |VEREFFEN  <br/> |Bing Kaarten-app voor Office-configuratie en-bronnen.  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |VEREFFEN  <br/> |De app personen Graph voor Office-configuratie en-bronnen.  <br/> |
|```https://www.onenote.com/```  <br/> |P  <br/> |KT  <br/> |Wat is de nieuwe inhoud voor OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |P  <br/> |KT  <br/> |Nieuwe inhoud voor OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |P  <br/> |VEREFFEN  <br/> |Nieuwe afbeeldingen voor OneNote  <br/> |
|```https://acompli.helpshift.com/```  <br/> |W  <br/> |KT  <br/> |In-app-ondersteunings service.  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |W  <br/> |KT  <br/> |Detectie service voor e-mailaccounts.  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |KT  <br/> |Automatisch opsporen van Outlook  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |KT  <br/> |Outlook-eindpunt voor Microsoft 365-service.  <br/> |
|```https://r1.res.office365.com/```  <br/> |W  <br/> |KT  <br/> |Pictogrammen voor Outlook-invoegtoepassingen.  <br/> |
   
> [!NOTE]
> De Office-configuratie service fungeert als een service voor automatische detectie voor alle Microsoft Office-clients, niet alleen voor Mac. De eindpunten die in het antwoord worden geretourneerd, zijn semi-statisch in die wijziging, maar wel mogelijk. 
  
 **Aanmelden**
  
Voor de volgende netwerkeindpunten wordt contact opgenomen wanneer u zich aanmeldt bij de opslag in de Cloud. Afhankelijk van uw accounttype kan u contact opnemen met andere services. Bijvoorbeeld:
  
- **MSA: Microsoft-account:** wordt meestal gebruikt voor scenario's met consumenten en detailhandel 
    
- **OrgID: organisatie account:** wordt meestal gebruikt voor commerciële scenario's 
    
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |KT  <br/> |Windows-autorisatie service  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |KT  <br/> |Microsoft 365-login service (OrgID)  <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |KT  <br/> |Inlog service voor Microsoft-accounts (MSA)  <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |Support  <br/> |Helper voor Microsoft-account login service (MSA)  <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |VEREFFEN  <br/> |Microsoft 365-huisstijl aanmelding (OrgID)  <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |Support  <br/> |Locator voor opslag van documenten en locaties  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |Support  <br/> |De MRU-documentservice (most recently used)  <br/> |
   
> [!NOTE]
> Als u een abonnement hebt op basis van abonnementen en een licentie, meldt u zich aan bij het activeren van het product en schakelt u de toegang tot Cloud bronnen zoals OneDrive. Bij installaties van volume licenties wordt gebruikers nog steeds gevraagd zich aan te melden (standaard), maar dit is alleen vereist voor de toegang tot Cloud bronnen, aangezien het product al is geactiveerd. 
  
 **Product activering**
  
De volgende netwerkeindpunten zijn van toepassing op activeringen van Microsoft 365-abonnement en voor handels producten. Dit geldt met name niet voor installaties van volume licenties.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |Support  <br/> |Office Licensing-service  <br/> |
   
 **Inhoud van nieuwe functies**
  
De volgende netwerkeindpunten zijn alleen van toepassing op Microsoft 365-abonnementen.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |VEREFFEN  <br/> |Wat is de nieuwe inhoud van de JSON-pagina.  <br/> |
   
 **Onderzoeker**
  
De volgende netwerkeindpunten zijn alleen van toepassing op Microsoft 365-abonnementen.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |Support  <br/> |Service voor onderzoeker  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |Support  <br/> |Onderzoek statische inhoud  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |Support  <br/> |Onderzoeker-inhouds provider  <br/> |
   
 **Slim zoeken**
  
De volgende netwerkeindpunten zijn van toepassing op activeringen van zowel Microsoft 365-abonnement als voor handels-en volume licenties.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |Support  <br/> |Inzichten-webservice  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |Support  <br/> |JQuery-bibliotheek  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |Support  <br/> |Ondersteunende JavaScript-bibliotheek  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |Support  <br/> |Inzicht inhouds provider  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |Support  <br/> |Inzicht inhouds provider  <br/> |
   
 **PowerPoint Designer**
  
De volgende netwerkeindpunten zijn alleen van toepassing op Microsoft 365-abonnementen.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |Support  <br/> |PowerPoint Designer-webservice  <br/> |
   
 **PowerPoint QuickStarter**
  
De volgende netwerkeindpunten zijn alleen van toepassing op Microsoft 365-abonnementen.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |Support  <br/> |PowerPoint Quick Service-webservice  <br/> |
   
 **Glimlach/frons verzenden**
  
De volgende netwerkeindpunten zijn van toepassing op activeringen van zowel Microsoft 365-abonnement als voor handels-en volume licenties.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |Support  <br/> |Een glimlach-service verzenden  <br/> |
   
 **Contact opnemen met ondersteuning**
  
De volgende netwerkeindpunten zijn van toepassing op activeringen van zowel Microsoft 365-abonnement als voor handels-en volume licenties.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |W  <br/> |Support  <br/> |Neem contact op met ondersteunings service  <br/> |
|```https://acompli.helpshift.com/```  <br/> |W  <br/> |Support  <br/> |In-app-ondersteunings service  <br/> |
   
 **Opslaan als PDF**
  
De volgende netwerkeindpunten zijn van toepassing op activeringen van zowel Microsoft 365-abonnement als voor handels-en volume licenties.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |Support  <br/> |Word document Conversion Service (PDF)  <br/> |
   
 **Office-apps (aka invoegtoepassingen)**
  
De volgende netwerkeindpunten zijn van toepassing op activeringen van Microsoft 365-abonnement en detailhandel/volume licenties wanneer Office-app-invoegtoepassingen worden vertrouwd.
  
|**URL**|**Cloud**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |Support  <br/> |Configuratie van Office App Store  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |VEREFFEN  <br/> |Bronnen voor Wikipedia-app  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |VEREFFEN  <br/> |Bronnen Bing Kaarten-app  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |VEREFFEN  <br/> |Bronnen voor app personen grafiek  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |VEREFFEN  <br/> |Office-omleidings service  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |VEREFFEN  <br/> |Office JavaScript-bibliotheken  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |VEREFFEN  <br/> |Telemetry and Reporting service voor Office-apps  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |VEREFFEN  <br/> |Microsoft AJAX JavaScript-bibliotheek  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |VEREFFEN  <br/> |Microsoft AJAX JavaScript-bibliotheek  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Office JavaScript-bibliotheken  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Bronnen voor ondersteuning  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Bronnen voor ondersteuning  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Bronnen voor ondersteuning  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |JavaScript-bibliotheek  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |VEREFFEN  <br/> |Foutrapportage  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Bronnen voor lettertypen  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Telemetrie-service  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Telemetrie-rapportage  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |VEREFFEN  <br/> |Microsoft Store-Activabibliotheek  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |VEREFFEN  <br/> |Bronnen voor een Wikipedia-pagina  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |VEREFFEN  <br/> |Wikipedia-mediabronnen  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |VEREFFEN  <br/> |Wikipedia-sandbox-frame  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |VEREFFEN  <br/> |Kaart Sjablonen  <br/> |
   
 **Veilige koppelingen**
  
Het volgende netwerkeindpunt is alleen van toepassing op alle Office-toepassingen voor Microsoft 365-abonnementen.
  
|**URL**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |Support  <br/> |Microsoft-service voor veilige koppelingen  <br/> |
   
 **Vastlopen van rapporten**
  
Het volgende netwerkeindpunt is van toepassing op alle Office-toepassingen voor activeringen van zowel Microsoft 365-abonnement als voor handels-en volume licenties. Wanneer een proces plotseling vastloopt, wordt een rapport gegenereerd en naar de Watson-service verzonden.
  
|**URL**|**Type**|**Beschrijving**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |KT  <br/> |Service voor foutrapportage van Microsoft  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |KT  <br/> |Service voor samenwerking van Office  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>Opties voor het beperken van netwerkaanvragen en verkeer

De standaardconfiguratie van Office voor Mac biedt de beste gebruikerservaring, zowel de functionaliteit als de computer up-to-date houden. In sommige gevallen wilt u mogelijk voorkomen dat toepassingen contact opnemen met netwerkeindpunten. In deze sectie worden opties besproken.
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>Aanmelding bij de Cloud en Office-invoegtoepassingen uitschakelen
  
Volume licentie klanten kunnen strikte beleidsregels bevatten voor het opslaan van documenten in opslag in de Cloud. U kunt de volgende voorkeuren per toepassing instellen voor het uitschakelen van MSA/OrgID-aanmelding en toegang tot Office-invoegtoepassingen.
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

Als gebruikers toegang proberen te krijgen tot de aanmeld functie, wordt een foutmelding weergegeven dat er geen netwerkverbinding is. Aangezien u met deze voorkeur ook online productactivering blokkeert, moet u dit alleen gebruiken voor installaties van volume licenties. Met deze voorkeur wordt niet voorkomen dat Office-toepassingen toegang krijgen tot de volgende eindpunten:
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- Alle eindpunten die worden vermeld in het gedeelte ' Aanmelden ' hierboven.
    
- Alle eindpunten die worden weergegeven in de sectie ' Slim zoeken ' hierboven.
    
- Alle eindpunten die worden vermeld in het gedeelte ' Product Activation ' hierboven.
    
- Alle eindpunten die worden vermeld in de sectie ' Office-apps (aka invoegtoepassingen) ' hierboven.
    
Als u de volledige functionaliteit voor de gebruiker opnieuw wilt instellen, stelt u de voorkeur in op 2 of verwijdert u deze.
  
> [!NOTE]
> Voor deze voorkeur is Office voor Mac build 15,25 [160726] of later vereist. 
  
### <a name="telemetry"></a>Telemetrie 
  
In Office voor Mac worden telemetrie-gegevensregel matig naar Microsoft verzonden. Gegevens worden geüpload naar het eindpunt ' Nexus '. Met de telemetrie-gegevens kan het engineering team de gezondheid en eventuele onverwachte gedrag van elke Office-app beoordelen. Er zijn twee categorieën telemetrie:
  
- **Heartbeat** bevat versie-en licentiegegevens. Deze gegevens worden direct verzonden na de start van de app. 
    
- **Gebruik** bevat informatie over de manier waarop apps worden gebruikt en niet-kritieke fouten. Deze gegevens worden elke 60 minuten verzonden. 
    
Microsoft houdt uw privacy zeer serieus. U kunt op de site van het Microsoft-gegevens verzamelings beleid lezen [https://privacy.microsoft.com](https://privacy.microsoft.com) . Om te voorkomen dat toepassingen ' gebruik ' telemetrie verzenden, kan de **SendAllTelemetryEnabled** -voorkeur worden aangepast. De voorkeur is een optie voor de toepassing en kan worden ingesteld via macOS Configuration-profielen, of handmatig van Terminal: 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

Heartbeat-telemetrie wordt altijd verzonden en kan niet worden uitgeschakeld.
  
### <a name="crash-reporting"></a>Vastlopen van rapporten
  
Wanneer een onherstelbare toepassingsfout optreedt, stopt de toepassing en uploadt de toepassing een crash rapport naar de Watson-service. Het rapport over vastlopen bestaat uit een oproep stapel, de lijst met stappen die door de toepassing naar de crash zijn verwerkt. Met deze stappen wordt het engineering-team geholpen met de exacte functie die mislukt en waarom.
  
In sommige gevallen zorgt de inhoud van een document dat de toepassing vastloopt. Als de app het document als oorzaak identificeert, wordt de gebruiker gevraagd of u het document ook samen met de oproep stapel wilt verzenden. Gebruikers kunnen een gefundeerde optie voor deze vraag maken. IT-beheerders kunnen strikte vereisten treffen voor de verzending van documenten en de beslissing namens de gebruiker doen om nooit documenten te verzenden. U kunt de volgende voorkeur instellen om te voorkomen dat documenten worden verzonden, en om de prompt voor de gebruiker te onderdrukken:
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> Als **SendAllTelemetryEnabled** is ingesteld op **False**, zijn alle crash rapporten voor dat proces uitgeschakeld. Als u vastlopen wilt rapporteren zonder gebruik van telemetrie te verzenden, kunt u de volgende voorkeuren instellen: ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>Updates
  
Microsoft brengt regelmatig updates voor Office voor Mac uit (meestal één keer per maand). U wordt aangeraden gebruikers en IT-beheerders op de hoogte te houden om ervoor te zorgen dat de nieuwste beveiligingsfixes worden geïnstalleerd. In situaties waarin IT-beheerders hun computer updates nauwkeurig willen beheren en beheren, kan de volgende voorkeur worden ingesteld om te voorkomen dat het automatisch bijwerken van producten automatisch wordt gedetecteerd en aangeboden.
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>Aanvragen blokkeren met een firewall/proxy
  
Als uw organisatie aanvragen van Url's blokkeert via een firewall of proxyserver, moet u ervoor zorgen dat de Url's die in dit document worden vermeld, worden geconfigureerd als toegestaan of worden weergegeven in een 40X-antwoord (zoals 403 of 404). Met een 40X-antwoord kunnen de Office-toepassingen de onbepaalde gebruikerservaring op een juiste manier accepteren en een snellere gebruikerservaring bieden, ongeacht de verbinding, waardoor de client weer opnieuw kan worden uitgevoerd.
  
Als authenticatie van de proxyserver is vereist, wordt een 407-antwoord teruggegeven aan de client. Voor de beste ervaring moet u ervoor zorgen dat u Office voor Mac-versies 15,27 of hoger gebruikt, aangezien deze specifieke oplossingen bevatten voor het werken met NTLM-en Kerberos-servers.
  
  
## <a name="see-also"></a>Zie ook

[URL's en IP-adresbereiken voor Office 365](urls-and-ip-address-ranges.md)

