---
title: Een SharePoint-site verplaatsen naar een andere geografische locatie
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
f1.keywords:
- NOCSH
description: Meer informatie over hoe u een SharePoint-site kunt verplaatsen naar een andere geografische locatie binnen uw omgeving met meerdere geografische gebieden en de verwachtingen van de wijzigingen aan uw gebruikers kunt communiceren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e96c422b1d2685c9fe3d4c8c45aa8437a6776621
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688931"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Een SharePoint-site verplaatsen naar een andere geografische locatie

Met de geo-verplaatsing van de SharePoint-site kunt u SharePoint-sites verplaatsen naar andere geo-locaties binnen uw omgeving met meerdere geografische locaties.

U kunt de volgende typen sites verplaatsen tussen geo-locaties:

- Met Microsoft 365 groep verbonden sites
- Moderne sites zonder een Microsoft 365-groeps koppeling
- Klassieke SharePoint-sites
- Communicatiesites

U moet een globale beheerder of SharePoint-beheerder zijn als u een site wilt verplaatsen tussen de geografische locaties.

Er is een alleen-lezen venster voor de geografische site 4-6 van een SharePoint-site, afhankelijk van de inhoud van de site.
 
## <a name="best-practices"></a>Aanbevolen procedures

- Probeer een SharePoint-site op een testsite te zetten om de procedure te leren kennen. 
- Controleer of de site kan worden verplaatst voordat u de verhuizing plant of uitvoert. 
- Wanneer mogelijke planning van cross-geografische sites gedurende buiten kantooruren verloopt, kunt u de gevolgen van de gebruikers verminderen.
- Communiceer met beïnvloede gebruikers voordat ze overstappen op de sites. 

## <a name="communicating-to-your-users"></a>Communiceren met uw gebruikers

Als u SharePoint-sites tussen geo-locaties verplaatst, is het belangrijk om te communiceren met de gebruikers van de sites (meestal iedereen met de mogelijkheid om de site te bewerken) wat u kunt verwachten. Dit kan de gebruikers verwarring en oproepen naar uw helpdesk verminderen. E-mail de gebruikers van uw site vóór de verhuizing en laat de volgende informatie weten:

- Wanneer de verplaatsing naar verwachting begint en hoe lang deze duurt
- De geografische locatie waarnaar de site wordt verplaatst, en de URL voor toegang tot de nieuwe locatie
- De persoon moet hun bestanden sluiten en geen wijzigingen aanbrengen tijdens de verhuizing.
- De bestandsmachtigingen en het delen worden niet door de verhuizing gewijzigd.
- Wat kunt u verwachten van de gebruikerservaring in een omgeving met meerdere geografische omgevingen?

Zorg ervoor dat u de gebruikers van uw sites een e-mail verzendt wanneer deze is voltooid, zodat ze hun werk op hun site kunnen voortzetten.

## <a name="scheduling-sharepoint-site-moves"></a>Verplaatsen van SharePoint-site plannen

U kunt instellen dat de SharePoint-site vooraf wordt gepland (verderop in dit artikel wordt beschreven). U kunt als volgt de agenda verplaatsen:

- U kunt maximaal 4.000 verplaatsen.
- Zoals de verhuizing begint, kunt u meer plannen, met een maximum van 4.000 in behandeling in de wachtrij en op een bepaald moment.
 
Als u een SharePoint-site wilt plannen voor een later tijdstip, moet u een van de volgende parameters toevoegen wanneer u de verhuizing begint:
- `PreferredMoveBeginDate` -De verhuizing begint waarschijnlijk op deze opgegeven tijd.
- `PreferredMoveEndDate` – De verhuizing wordt waarschijnlijk op basis van de opgegeven tijd voltooid. 

Voor beide parameters moet de tijd worden opgegeven in Coordinated Universal Time (UTC).

## <a name="moving-the-site"></a>De site verplaatsen

Voor het verplaatsen van een SharePoint-site moet de locatie van de SharePoint-beheerder verbinding maken en de overstappen van de SharePoint-beheer-URL

Als de URL van de site bijvoorbeeld is https://contosohealthcare.sharepoint.com/sites/Turbines , maakt u verbinding met de SharePoint-beheer-URL op https://contosohealthcare-admin.sharepoint.com:

`Connect-SPOService -url https://contosohealthcare-admin.sharepoint.com`

![](../media/move-onedrive-between-geo-locations-image1.png)
 
### <a name="validating-the-environment"></a>De omgeving valideren

We raden u aan om te controleren of de site kan worden verplaatst voordat u de verhuizing van een site plant.

We bieden geen ondersteuning voor het verplaatsen van sites met:
-    Business Connectivity Services
-    InfoPath-formulieren 
- IRM-sjablonen (Information Rights Management)

Voer de opdracht uit om ervoor te zorgen dat alle geo-locaties compatibel zijn `Get-SPOGeoMoveCrossCompatibilityStatus` . Hiermee worden al uw geografische locaties weergegeven en wordt aangegeven of de omgeving compatibel is met de geografische locatie van de doellocatie.

Als u op uw site een validatie wilt uitvoeren, moet u `Start-SPOSiteContentMove` de `-ValidationOnly` parameter gebruiken om te controleren of de site kan worden verplaatst. Bijvoorbeeld:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Hierdoor wordt het *resultaat als* de site klaar is om te worden verplaatst of *mislukt* indien een van de geblokkeerde voorwaarden beschikbaar is.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Een geografische site van een SharePoint-site starten voor een site zonder een gekoppelde Microsoft 365-groep

De aanvankelijke URL voor de site wordt standaard gewijzigd in de URL van de geografische locatie van de bestemming. Bijvoorbeeld:

https://Contoso.sharepoint.com/sites/projectx Aan https://ContosoEUR.sharepoint.com/sites/projectx

Voor sites zonder de groeps koppeling van Microsoft 365 kunt u ook de naam van de site wijzigen met behulp van de `-DestinationUrl` parameter. Bijvoorbeeld:

https://Contoso.sharepoint.com/sites/projectx Aan https://ContosoEUR.sharepoint.com/sites/projecty

Voer het volgende uit om de site te verplaatsen:

`Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>`

![Schermafbeelding van het PowerShell-venster met de cmdlet start-SPOSiteContentMove](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Een geografische site van een SharePoint-site starten voor een site met een Microsoft 365-groep

Als u een site met een Office 365-groep wilt verplaatsen, moet de globale beheerder of SharePoint-beheerder eerst het kenmerk van de gewenste gegevenslocatie (PDL) voor de Office 365-groep wijzigen.

De PDL voor een Microsoft 365-groep instellen:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```
Wanneer u de PDL-update hebt bijgewerkt, kunt u de verhuizing van de site starten: 

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Een SharePoint-site verplaatsen naar geo

U kunt een geografische verplaatsing van een SharePoint-site stoppen, mits de overstap niet wordt uitgevoerd of voltooid met behulp van de `Stop-SPOSiteContentMove` cmdlet.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>De status van de geografische verhuizing van een SharePoint-site bepalen

Met behulp van de volgende cmdlets kunt u de status van een site bepalen in ons van de geo waarmee u bent verbonden.

- [Get-SPOSiteContentMoveState](https://docs.microsoft.com/powershell/module/sharepoint-online/get-spositecontentmovestate) (niet met een groep verbonden sites)
- Get-SPOUnifiedGroupMoveState (met een groep verbonden sites)

Met behulp `-SourceSiteUrl` van de parameter kunt u de site opgeven waarvoor u de status van verplaatsen wilt weergeven.

De verplaatsings status wordt beschreven in de volgende tabel.

|Status|Beschrijving|
|:-----|:----------|
|Klaar om te activeren|De verhuizing is niet gestart.|
|Geplande|De verhuizing bevindt zich in de wachtrij maar is nog niet gestart.|
|Invoortgang (n/4)|De verplaatsing wordt uitgevoerd in een van de volgende staten: validering (1/4), back-up (2/4), herstellen (3/4), opruimen (4/4).|
|Bevestiging|De verhuizing is voltooid.|
|Mislukt|Verplaatsen mislukt.|

U kunt ook de `-Verbose` optie gebruiken om aanvullende informatie over de verhuizing te zien.

## <a name="user-experience"></a>Gebruikerservaring

Sitegebruikers dienen de minimale overlast te zien wanneer hun site naar een andere geografische locatie wordt verplaatst. Als u tijdens de verhuizing een kortere alleen-lezen status wilt hebben, blijven bestaande koppelingen en machtigingen op de verwachte manier werken als de verplaatsing is voltooid.

### <a name="site"></a>Site

Tijdens de uitvoering wordt de site ingesteld op alleen-lezen. Wanneer de overstap is voltooid, wordt de gebruiker doorgestuurd naar de nieuwe site op de nieuwe geo-locatie wanneer ze op bladwijzers of andere koppelingen naar de site klikken.

### <a name="permissions"></a>Machtigingen

Gebruikers met machtigingen voor de site hebben nog steeds toegang tot de site tijdens de verhuizing en nadat deze is voltooid.

### <a name="sync-client"></a>Synchronisatieclient

De synchronisatieclient detecteert automatisch de synchronisatie naar de nieuwe sitelocatie en verstuurt automatisch de synchronisatie naar de nieuwe sitelocatie zodra de site is verplaatst. De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen. (Versie 17.3.6943.0625 of hoger van de synchronisatieclient vereist.)

Als een gebruiker een bestand bijwerkt terwijl de overstap wordt uitgevoerd, wordt door de synchronisatieclient aangegeven dat het uploaden van bestanden in behandeling is terwijl de verhuizing plaatsvindt.

### <a name="sharing-links"></a>Koppelingen voordelen

Wanneer de geografische site van de SharePoint-site is verplaatst, worden de bestaande gedeelde koppelingen voor de bestanden die zijn verplaatst automatisch omgeleid naar de nieuwe geografische locatie.

### <a name="most-recently-used-files-in-office-mru"></a>Meest recent gebruikte bestanden in Office (MRU)

De MRU-service wordt bijgewerkt met de URL van de site en de inhoud van de inhoud nadat de verplaatsing is voltooid. Dit geldt voor Word, Excel en PowerPoint.

### <a name="onenote-experience"></a>OneNote-ervaring

Met de apps van OneNote Win32 client en UWP (Universal) wordt automatisch notitieblokken automatisch herkend en gesynchroniseerd met de nieuwe sitelocatie zodra de verhuizing van de site is voltooid. De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie te ondernemen. De enige zichtbare indicator voor de gebruiker is het synchroniseren van notitieblokken mislukt wanneer de site wordt verplaatst. Deze ervaring is beschikbaar in de volgende versies van OneNote-clients:

- OneNote Win32-versie 16.0.8326.2096 (en later)
- OneNote UWP: versie 16.0.8431.1006 (en later)
- App OneNote Mobile: versie 16.0.8431.1011 (en later)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (van toepassing op Microsoft 365-groep verbonden sites)

Wanneer de geografische site van de SharePoint-site is verplaatst, hebben gebruikers toegang tot hun Microsoft 365-groepssite bestanden in de teams-app. Daarnaast werken bestanden die zijn gedeeld via teams-chat van de site voordat de geo-overstap is voltooid, verder.

### <a name="sharepoint-mobile-app-iosandroid"></a>Mobiele SharePoint-app (iOS/Android)

De mobiele SharePoint-app is door Geo compatibel en kan de nieuwe geografische locatie van de site detecteren.

### <a name="sharepoint-workflows"></a>SharePoint-werkstromen

SharePoint 2013-werkstromen moeten opnieuw worden gepubliceerd na de site verhuizing. SharePoint 2010-werkstromen moeten normaal blijven functioneren.

### <a name="apps"></a>Cloud

Als u een site verplaatst met apps, moet u de app opnieuw instantiëren op de nieuwe geo-locatie van de site als de app en zijn de verbindingen mogelijk niet beschikbaar op de geografische locatie van de doellocatie.

### <a name="flow"></a>Besturing

In de meeste gevallen blijven de kasstromen werken nadat u de geografische site van een SharePoint-site hebt verplaatst. We raden u aan ze te testen wanneer de overstap is voltooid.

### <a name="powerapps"></a>PowerApps

PowerApps moet opnieuw worden gemaakt op de doellocatie.

### <a name="data-movement-between-geo-locations"></a>Gegevensverplaatsing tussen geo-locaties

SharePoint gebruikt Azure Blob Storage voor de inhoud, terwijl de metagegevens van sites en de bijbehorende bestanden in SharePoint zijn opgeslagen. Wanneer de site van de geografische locatie van de site naar de geografische locatie van de doellocatie wordt verplaatst, wordt de bijbehorende Blobopslag ook verplaatst met de service. Blobopslag wordt met een gehele 40 dagen afgerond. 
