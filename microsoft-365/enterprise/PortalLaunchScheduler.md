---
title: De portal starten met behulp van de lanceer planner voor portal
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: In dit artikel wordt uitgelegd hoe u uw portal kunt starten met behulp van de lanceer planner voor portals
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999581"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>De portal starten met behulp van de lanceer planner voor portal

U kunt de portal starten met de start Planner van de portal door eerst de mogelijkheid van de tenantbeheerder te valideren voor het instellen van een golven voor een nieuwe portal. Vervolgens kan de beheerder een omleiding van aanvragen valideren, op basis van het bestaan van een gebruiker in de actieve golven.

Als u meer wilt weten over het starten van een succesvolle Portal, volgt u de basisprincipes, procedures en aanbevelingen die specifiek zijn voor het [maken, starten en onderhouden van een gezonde Portal](https://go.microsoft.com/fwlink/?linkid=2105838). 

## <a name="app-setup"></a>App instellen
1. Verwijder indien `Microsoft.Online.SharePoint.PowerShell` van uw computer een bestaande versie via het Configuratiescherm.
2. In PowerShell Passive `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .

## <a name="connect-to-sharepoint-online"></a>Verbinding maken met SharePoint Online
1. Open de [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.
2. Maak verbinding met de Tenant als beheerder.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  Geef uw wachtwoord op wanneer hierom wordt gevraagd.

## <a name="command-to-get-an-existing-setup"></a>Opdracht voor het weergeven van een bestaande instelling

Bestaande start configuraties van portal weergeven:

1. Doorgeven `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .
2. Geef de parameter extra `-DisplayFormat Raw` weer als u de Wave verzameling wilt weergeven die is opgemaakt als een RAW-invoer opmaak.

## <a name="commands-for-bi-directional-redirection"></a>Opdrachten voor bi-directionele omleiding

Oude sitegebruikers migreren naar de nieuwe site op een gefaseerde manier:

1. Lanceer golftjes voor de portal maken.
   - Dit is alleen van toepassing op de testfase van de eerste release.
   - Als u de invloed van de wijziging direct wilt testen, controleert u of de eerste golf `LaunchDateUtc` is ingesteld op de huidige datum. Als u deze vlag niet opgeeft, wordt er een foutbericht weergegeven. Deze fout treedt op omdat de start in de productie minimaal zeven dagen tevoren moet worden gepland.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Validatie voltooien.
  - Het duurt maximaal 5 minuten voordat u de configuratie via de service kunt voltooien, dus moet u wachten voordat u verdergaat.
  - Als u zich aanmeldt met de opgegeven gebruiker `WaveOverrideUsers` , wordt niets gewijzigd. U dient op de site te blijven staan waar u naar moet navigeren.
  - Meld u aan met een gebruiker die deel uitmaakt van *kijkers SG1*.
    - Ga naar de oude site, waarna u wordt doorgestuurd naar de nieuwe site.
    - Ga naar de nieuwe site en blijf op de nieuwe site.
    - Meld u aan met een gebruiker in de *SG2 van kijkers* en blader naar de oude site en blijf op de oude site.
    - Ga naar de nieuwe site, waarna u wordt doorgestuurd naar de oude site.

3. Start de portal start.
  - Als u de start golfs moet onderbreken, kunt u deze onderbreken voor het aantal dagen van ' x '. `Status`Als u wilt dat de vlag wordt ingesteld om te onderbreken, voorkomt u dat er nieuwe golf. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Hiermee wordt gecontroleerd of alle gebruikers worden doorgestuurd naar de oude site.

4. Start de voortgang van het starten van de portal opnieuw. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Valideren dat de omleiding nu wordt hersteld.

5. Een portal voor het openen van een Portal verwijderen.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - Controleer of er geen omleiding voor alle gebruikers gebeurt.

## <a name="commands-for-redirection-to-temporary-page"></a>Opdrachten voor omleiding naar tijdelijke pagina

Voer de volgende stappen uit als u geen eerdere site hebt en u gebruikers niet in de Golf van de aanvoer op de pagina nieuwe portal wilt laten staan.

Een tijdelijke pagina maken op een van de sites:

1. Maak een lanceer Golf voor de portal.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Validatie voltooien.

  - Wacht vijf minuten voordat u verder gaat, aangezien de actie maximaal vijf minuten kan duren.
  - Meld u aan met de gebruiker die deel uitmaakt van *kijkers SG1* en:
     - Ga naar de nieuwe site en blijf op de nieuwe site.
     - Ga naar de pagina Temp en blijf op de pagina Temp.
  - Meld u aan met de gebruiker die deel uitmaakt van *kijkers SG2* en:
     - Ga naar de nieuwe site en u wordt omgeleid naar de pagina Temp.
     - Ga naar de pagina Temp en blijf op de pagina Temp.

3. Een portal voor het openen van een Portal verwijderen.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Controleer of er geen omleiding voor alle gebruikers gebeurt.

## <a name="learn-more"></a>Meer informatie
[Rollen plan voor het lanceren van uw portal in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)