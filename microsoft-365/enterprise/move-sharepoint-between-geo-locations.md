---
title: Een site SharePoint naar een andere geografische locatie verplaatsen
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
description: Meer informatie over het verplaatsen van een SharePoint naar een andere geografische locatie in uw multi-geo-omgeving en de verwachtingen van de wijzigingen aan uw gebruikers communiceren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: eed323b2e2b8f68a4a603052657e17495bb17690
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910928"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>Een site SharePoint naar een andere geografische locatie verplaatsen

Met SharePoint site geoverplaatsing kunt u SharePoint sites verplaatsen naar andere geografische locaties in uw multi-geo-omgeving.

De volgende typen site kunnen worden verplaatst tussen geografische locaties:

- Microsoft 365 Sites met groepsconnectie
- Moderne sites zonder een Microsoft 365 groep
- Klassieke SharePoint sites
- Communicatiesites

U moet een globale beheerder of beheerder SharePoint om een site tussen geografische locaties te verplaatsen.

Er is een venster alleen-lezen tijdens de SharePoint site geoverplaatsing van ongeveer 4-6 uur, afhankelijk van de site-inhoud.

## <a name="best-practices"></a>Aanbevolen procedures

- Probeer een SharePoint site verplaatsen op een testsite om vertrouwd te raken met de procedure.
- Controleer of de site kan worden verplaatst vóór het plannen of uitvoeren van de verhuizing.
- Indien mogelijk worden cross-geosites verplaatst voor buiten de werkuren om de impact van de gebruiker te beperken.
- Communiceer met beïnvloede gebruikers voordat de sites worden verplaatst.

## <a name="communicating-to-your-users"></a>Communiceren met uw gebruikers

Wanneer u SharePoint sites verplaatst tussen geografische locaties, is het belangrijk om te communiceren met de gebruikers van de sites (meestal iedereen met de mogelijkheid om de site te bewerken) wat u kunt verwachten. Dit kan gebruikersverwarring en oproepen naar uw helpdesk helpen verminderen. E-mail de gebruikers van uw sites vóór de verhuizing en laat ze de volgende informatie weten:

- Wanneer de overstap wordt verwacht en hoe lang deze naar verwachting zal duren
- Naar welke geografische locatie de site wordt verplaatst en de URL voor toegang tot de nieuwe locatie
- Ze moeten hun bestanden sluiten en geen wijzigingen maken tijdens het verplaatsen.
- Bestandsmachtigingen en delen worden niet gewijzigd vanwege de verhuizing.
- Wat u kunt verwachten van de gebruikerservaring in een multi-geo-omgeving

Zorg ervoor dat u de gebruikers van uw sites een e-mail stuurt wanneer de overstap is voltooid, zodat ze kunnen hervatten met werken op hun sites.

## <a name="scheduling-sharepoint-site-moves"></a>Site-SharePoint plannen

U kunt de SharePoint van tevoren plannen (verder in dit artikel beschreven). U kunt bewegingen als volgt plannen:

- U kunt maximaal 4.000 bewegingen tegelijk plannen.
- Wanneer de bewegingen beginnen, kunt u meer plannen, met een maximum van 4.000 in behandeling zijnde bewegingen in de wachtrij en een bepaalde tijd.

Als u een SharePoint site geo-move voor een later tijdstip wilt plannen, moet u een van de volgende parameters opnemen wanneer u de move start:

- `PreferredMoveBeginDate` – De verhuizing begint waarschijnlijk op dit opgegeven tijdstip.
- `PreferredMoveEndDate` – De verhuizing wordt waarschijnlijk voltooid op deze opgegeven tijd, op basis van de beste inspanning.

Tijd moet worden opgegeven in UTC (Coordinated Universal Time) voor beide parameters.

## <a name="moving-the-site"></a>De site verplaatsen

SharePoint site geo-move vereist dat u verbinding maakt en de overstap maakt van de url van de beheerder SharePoint de geografische locatie waar de site zich bevindt.

Als de url van de site bijvoorbeeld de URL van de site is, maakt u verbinding met <https://contosohealthcare.sharepoint.com/sites/Turbines> de url SharePoint beheerder op <https://contosohealthcare-admin.sharepoint.com> :

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint Venster Onlinebeheershell met de Connect-SPOService opdracht](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>De omgeving valideren

Het is raadzaam om voordat u een site verplaatsen te plannen, een validatie uit te voeren om ervoor te zorgen dat de site kan worden verplaatst.

We bieden geen ondersteuning voor het verplaatsen van sites met:

- Business Connectivity Services
- InfoPath-formulieren
- IRM-sjablonen (Information Rights Management) toegepast

Als u ervoor wilt zorgen dat alle geografische locaties compatibel zijn, moet u `Get-SPOGeoMoveCrossCompatibilityStatus` uitvoeren. Hiermee worden al uw geografische locaties weergegeven en wordt bepaald of de omgeving compatibel is met de doellocatie.

Als u een validatiecontrole op uw site wilt uitvoeren, gebruikt u de parameter om te valideren of de `Start-SPOSiteContentMove` `-ValidationOnly` site kan worden verplaatst. Bijvoorbeeld:

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

Dit geeft succes *als* de site klaar is om te worden verplaatst of *Mislukken* als er een van de geblokkeerde voorwaarden aanwezig is.

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>Een geografische SharePoint site starten voor een site zonder gekoppelde Microsoft 365 Groep

Standaard wordt de oorspronkelijke URL voor de site gewijzigd in de URL van de doellocatie. Bijvoorbeeld:

<https://Contoso.sharepoint.com/sites/projectx> Aan <https://ContosoEUR.sharepoint.com/sites/projectx>

Voor sites zonder Microsoft 365 groep kunt u de naam van de site ook wijzigen met de `-DestinationUrl` parameter. Bijvoorbeeld:

<https://Contoso.sharepoint.com/sites/projectx> Aan <https://ContosoEUR.sharepoint.com/sites/projecty>

Als u de site wilt verplaatsen, gaat u als volgende te werk:

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![Schermafbeelding van PowerShell-venster met Start-SPOSiteContentMove cmdlet](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>Een geoverplaatsing SharePoint site starten voor een Microsoft 365 met groep verbonden site

Als u een Office 365 groep verbonden site wilt verplaatsen, moet de globale beheerder of SharePoint-beheerder eerst het kenmerk Voorkeursgegevenslocatie (PDL) voor de groep Office 365 wijzigen.

De PDL voor een groep Microsoft 365 instellen:

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

Nadat u het PDF-bericht hebt bijgewerkt, kunt u de site verplaatsen:

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>Een geo-SharePoint site annuleren

U kunt een SharePoint site geoverplaatsing stoppen, mits de beweging niet wordt uitgevoerd of voltooid met behulp van de `Stop-SPOSiteContentMove` cmdlet.

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>De status van een geo-SharePoint van een site bepalen

Met de volgende cmdlets kunt u de status van een site verplaatsen in de geo waar u mee verbonden bent bepalen:

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate) (sites die niet met groepen zijn verbonden)
- [Get-SPOUnifiedGroupMoveState](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) (sites met groepsconnectie)

Gebruik de `-SourceSiteUrl` parameter om de site op te geven waarvoor u de status verplaatsen wilt zien.

De statussen voor verplaatsen worden in de volgende tabel beschreven.

****

|Status|Beschrijving|
|---|---|
|Klaar om te activeren|De move is nog niet gestart.|
|Gepland|De move staat in de wachtrij, maar is nog niet gestart.|
|InProgress (n/4)|De move wordt uitgevoerd in een van de volgende staten: Validatie (1/4), Back-up (2/4), Herstellen (3/4), Opschoning (4-4).|
|Succes|De verhuizing is voltooid.|
|Mislukt|De beweging is mislukt.|
|

U kunt de optie ook `-Verbose` toepassen om aanvullende informatie over de verhuizing te bekijken.

## <a name="user-experience"></a>Gebruikerservaring

Sitegebruikers moeten minimale onderbrekingen zien wanneer hun site naar een andere geografische locatie wordt verplaatst. Afgezien van een korte status alleen-lezen tijdens het verplaatsen, blijven bestaande koppelingen en machtigingen werken zoals verwacht wanneer de verhuizing is voltooid.

### <a name="site"></a>Site

Terwijl de move wordt uitgevoerd, is de site ingesteld op alleen-lezen. Wanneer de overstap is voltooid, wordt de gebruiker doorgestuurd naar de nieuwe site op de nieuwe geografische locatie wanneer deze op bladwijzers of andere koppelingen naar de site klikt.

### <a name="permissions"></a>Machtigingen

Gebruikers met een sitemachtiging blijven toegang tot de site hebben tijdens de verhuizing en nadat de site is voltooid.

### <a name="sync-client"></a>Synchronisatieclient

De synchronisatieclient detecteert automatisch en schakelt naadloos synchronisatie over naar de nieuwe sitelocatie zodra de siteverplaatsing is voltooid. De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie uit te voeren. (Versie 17.3.6943.0625 of hoger van de synchronisatieclient vereist.)

Als een gebruiker een bestand bij werkt terwijl de overstap wordt uitgevoerd, ontvangt de synchronisatieclient een melding dat er een bestand wordt geüpload terwijl de overstap wordt uitgevoerd.

### <a name="sharing-links"></a>Koppelingen voor delen

Wanneer de SharePoint site geoverplaatsing is voltooid, worden de bestaande gedeelde koppelingen voor de bestanden die zijn verplaatst, automatisch omgeleid naar de nieuwe geografische locatie.

### <a name="most-recently-used-files-in-office-mru"></a>Meest recent gebruikte bestanden in Office (MRU)

De MRU-service wordt bijgewerkt met de url van de site en de inhouds-URL's van de site zodra de overstap is voltooid. Dit geldt voor Word, Excel en PowerPoint.

### <a name="onenote-experience"></a>OneNote ervaring

OneNote win32-client en uwp-app (Universal) worden notitieblokken automatisch gedetecteerd en naadloos gesynchroniseerd met de nieuwe sitelocatie zodra de site is verplaatst. De gebruiker hoeft zich niet opnieuw aan te melden of een andere actie uit te voeren. De enige zichtbare indicator voor de gebruiker is dat de synchronisatie van notitieblokken mislukt wanneer de site wordt verplaatst. Deze ervaring is beschikbaar in de volgende OneNote clientversies:

- OneNote win32 – Versie 16.0.8326.2096 (en hoger)
- OneNote UWP – Versie 16.0.8431.1006 (en hoger)
- OneNote Mobiele app : versie 16.0.8431.1011 (en hoger)

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (van toepassing op verbonden Microsoft 365 groep)

Wanneer de SharePoint site geo move is voltooid, hebben gebruikers toegang tot hun Microsoft 365 Groepssitebestanden in de Teams app. Bovendien blijven bestanden die worden gedeeld via Teams chat vanaf hun site vóór geo-move, werken nadat de move is voltooid.

### <a name="sharepoint-mobile-app-iosandroid"></a>SharePoint Mobiele app (iOS/Android)

De SharePoint mobiele app is compatibel met cross geo en kan de nieuwe geografische locatie van de site detecteren.

### <a name="sharepoint-workflows"></a>SharePoint werkstromen

SharePoint 2013-werkstromen moeten opnieuw worden gepubliceerd nadat de site is verplaatst. SharePoint 2010-werkstromen moeten normaal blijven werken.

### <a name="apps"></a>Apps

Als u een site met apps verplaatst, moet u de app opnieuw instantieren op de nieuwe geografische locatie van de site, omdat de app en de verbindingen mogelijk niet beschikbaar zijn op de geografische locatie van de bestemming.

### <a name="flow"></a>Flow

In de meeste gevallen blijven stromen werken na een SharePoint site geo-move. U wordt aangeraden ze te testen zodra de verhuizing is voltooid.

### <a name="powerapps"></a>PowerApps

PowerApps moeten opnieuw worden gemaakt op de doellocatie.

### <a name="data-movement-between-geo-locations"></a>Gegevensbewegingen tussen geografische locaties

SharePoint gebruikt Azure Blob-opslag voor de inhoud ervan, terwijl de metagegevens die zijn gekoppeld aan sites en de bijbehorende bestanden, worden opgeslagen in SharePoint. Nadat de site is verplaatst van de bronlocatie naar de geografische locatie van de bestemming, wordt ook de bijbehorende Blob-locatie Storage. Blob Storage wordt in ongeveer 40 dagen voltooid verplaatst.