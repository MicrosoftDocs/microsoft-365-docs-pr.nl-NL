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
ms.openlocfilehash: a7a007fdd95638109830a8e3689232060f2b9d8b
ms.sourcegitcommit: 2d3e85173c65a9e0ce92624a80ed7a9839f5b8bd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49123581"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>De portal starten met behulp van de lanceer planner voor portal

Een portal is een SharePoint-site op uw intranet met een groot aantal sitebezoekers die inhoud op de site gebruiken. Het starten van de portal in golven is een belangrijk onderdeel van de zorgen dat gebruikers een eenvoudige en ervaren ervaring hebben om toegang te krijgen tot een nieuwe SharePoint Online-Portal. 

De lancering in golven is een belangrijke manier om de portal uit te vouwen, zoals wordt uitgelegd in [het implementatieplan van uw portal lanceren in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide). De lancerings planner voor de portal is bedoeld om u te helpen bij het volgen van een rol met Golf/gefaseerde samenvatting door de omleidingen voor de nieuwe portal te beheren. U kunt tijdens elk van de golven feedback van gebruikers verzamelen en de prestaties controleren tijdens elke implementatie. Dit heeft het voordeel van langzaam de portal, met de mogelijkheid om problemen te onderbreken en op te lossen voordat u verder gaat met de volgende golf, en de gebruikers uiteindelijk zorgen voor een gunstige ervaring. 

Er zijn twee typen omleiding: 
- bidirectioneel: een nieuwe moderne SharePoint Online-Portal starten om een bestaande SharePoint-klassieke of moderne portal te vervangen 
- tijdelijke omleiding van pagina: een nieuwe moderne SharePoint Online-Portal starten zonder bestaande SharePoint-Portal

De lancerings planner voor de portal is alleen beschikbaar voor het openen van moderne SharePoint Online-portals, zoals Communicatiesites en moderne team sites. Start moet ten minste 7 dagen vooraf worden gepland. Het aantal vereiste golven wordt bepaald door het verwachte aantal gebruikers. Voordat u begint met het plannen van een portal, moet u eerst het [hulpprogramma pagina diagnose voor SharePoint](https://aka.ms/perftool) uitvoeren om te controleren of de startpagina op de portal in orde is. Aan het einde van de start van de portal hebben alle gebruikers met machtigingen voor de site toegang tot de nieuwe site. 

Als u meer wilt weten over het starten van een succesvolle Portal, volgt u de basisprincipes, procedures en aanbevelingen voor informatie over het [maken, starten en onderhouden van een gezonde Portal](https://docs.microsoft.com/sharepoint/portal-health). 

> [!NOTE]
> Deze functie is niet beschikbaar voor Office 365 Duitsland, Office 365 beheerd door 21Vianet (China) of Microsoft 365 US Government-abonnementen.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>App instellen en verbinding maken met SharePoint Online
1. [Download de nieuwste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Als u een eerdere versie van de SharePoint Online Management Shell hebt geïnstalleerd, gaat u naar Programma's installeren of verwijderen en klikt u op SharePoint Online Management Shell verwijderen. <br>Selecteer uw taal op de pagina het Download centrum en klik vervolgens op de knop downloaden. U wordt gevraagd te kiezen tussen het downloaden van een x64-en x86 MSI-bestand. Download het x64-bestand als u werkt met de 64-bits versie van Windows of het x86-bestand als u de 32-bits versie uitvoert. Als u het niet weet, raadpleegt u [welke versie van Windows-besturingssysteem gebruik ik?](https://support.microsoft.com/help/13443/windows-which-operating-system). Nadat het bestand is gedownload, voert u het uit en volgt u de stappen in de wizard Setup.

2. Maak verbinding met SharePoint als [globale beheerder of als SharePoint-beheerder](/sharepoint/sharepoint-admin-role) in microsoft 365. Zie aan de slag [met SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)voor meer informatie.


## <a name="view-any-existing-portal-launch-setups"></a>Bestaande portal-start instellingen weergeven

Ga als volgt te werk om te controleren of er bestaande portal-lanceer configuraties zijn:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>De lancering van een portal op de site plannen

Het aantal vereiste Golf punten is afhankelijk van de verwachte start grootte. 
- Minder dan 10.000 gebruikers: 1 Golf
- 10k voor 30k-gebruikers: 3 golven 
- 30k + to afgesloten 100k gebruikers: 5 golven
- Meer dan afgesloten 100k gebruikers: 5 golven en neem contact op met uw Microsoft-accountteam

### <a name="steps-for-bi-directional-redirection"></a>Stappen voor omleiding naar bi-richting

Bidirectionele omleiding houdt in dat u een nieuwe moderne SharePoint Online-Portal moet starten om een bestaande SharePoint-klassieke of moderne portal te vervangen. Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site navigeren. Gebruikers in een niet-geactiveerde golf die toegang proberen te krijgen tot de nieuwe site, worden weer naar de oude site omgeleid totdat hun Wave wordt gestart. Als u beheerders of eigenaren hebt die toegang moeten hebben tot de oude en nieuwe sites zonder te worden doorgestuurd, moet u ervoor zorgen dat ze worden weergegeven met behulp van de `WaveOverrideUsers` parameter. 

Gebruikers migreren van een bestaande SharePoint-site naar een nieuwe SharePoint-site op een gefaseerde manier:

1. Voer de volgende opdracht uit om de lanceer golven voor de portal aan te wijzen.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Voorbeeld:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Validatie voltooien. Het duurt 5-10 minuten voordat de omleiding is geconfigureerd via de service. 

### <a name="steps-for-redirection-to-temporary-page"></a>Stappen voor omleiding naar tijdelijke pagina

Tijdelijke omleiding voor pagina's moet worden gebruikt wanneer er geen bestaande SharePoint-Portal bestaat. Gebruikers worden op een gefaseerde manier omgeleid naar een nieuwe moderne SharePoint Online-Portal. Als een gebruiker een golf heeft die niet is gestart, wordt deze omgeleid naar een tijdelijke pagina (willekeurige URL). 

1. Voer de volgende opdracht uit om de lanceer golven voor de portal aan te wijzen.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Voorbeeld:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Validatie voltooien. Het duurt 5-10 minuten voordat de omleiding is geconfigureerd via de service. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>De start van een portal op de site onderbreken of opnieuw starten

1. Voer de volgende opdracht uit om de start van een portal te onderbreken en de voortgang van een nieuwe golf versie te voorkomen.

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Controleer of alle gebruikers worden omgeleid naar de oude site. 

3. Voer de volgende opdracht uit als u een gepauzeerde Portal opnieuw wilt starten:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Valideren dat de omleiding nu wordt hersteld. 

## <a name="delete-a-portal-launch-on-the-site"></a>De start van een portal op de site verwijderen
1. Maak een lanceer Golf voor de portal.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Voer de volgende opdracht uit als u een geplande Portal start of een uitvoering van een site wilt verwijderen.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. Controleer of er geen omleiding voor alle gebruikers gebeurt.

## <a name="learn-more"></a>Meer informatie
[Rollen plan voor het lanceren van uw portal in SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
