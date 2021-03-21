---
title: Uw portal starten met de Portal Launch Scheduler
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
description: In dit artikel wordt beschreven hoe u uw portal kunt starten met de Portal Launch Scheduler
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926140"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Uw portal starten met de Portal Launch Scheduler

Een portal is een SharePoint-site op uw intranet met een groot aantal sitekijkers die inhoud op de site gebruiken. Het starten van uw portal in golven is een belangrijk onderdeel om ervoor te zorgen dat gebruikers een soepele en performante ervaring hebben met het openen van een nieuwe SharePoint Online-portal. 

Starten in golven is een belangrijke manier om uw portal uit te rollen, zoals wordt beschreven in Het plannen van uw [portal launch roll-out plan in SharePoint Online.](./planportallaunchroll-out.md?view=o365-worldwide) De Portal Launch Scheduler is ontworpen om u te helpen een wave/phased roll-out benadering te volgen door de omleidingen voor de nieuwe portal te beheren. Tijdens elk van de golven kunt u feedback van gebruikers verzamelen en de prestaties tijdens elke implementatiegolf controleren. Dit heeft het voordeel dat u de portal langzaam introduceert, zodat u problemen kunt onderbreken en oplossen voordat u verdergaat met de volgende golf, en er uiteindelijk voor zorgt dat uw gebruikers een positieve ervaring hebben. 

Er zijn twee soorten omleiding: 
- bidirectioneel: start een nieuwe moderne SharePoint Online-portal om een bestaande klassieke of moderne SharePoint-portal te vervangen 
- tijdelijke omleiding van pagina's: start een nieuwe moderne SharePoint Online-portal zonder bestaande SharePoint-portal

De planning voor het starten van portals is alleen beschikbaar voor het starten van moderne SharePoint Online-portals (dat wil zeggen communicatiesites). De lanceringen moeten ten minste 7 dagen van tevoren zijn gepland. Het aantal benodigde golven wordt bepaald door het verwachte aantal gebruikers. Voordat u een portalstart wilt plannen, moet het hulpprogramma Paginadiagnose voor [SharePoint](./page-diagnostics-for-spo.md) worden uitgevoerd om te controleren of de startpagina van de portal gezond is. Aan het einde van de portallancering hebben alle gebruikers met machtigingen voor de site toegang tot de nieuwe site. 

Voor meer informatie over het starten van een succesvolle portal, volgt u de basisprincipes, procedures en aanbevelingen die worden beschreven in Het maken, starten en [onderhouden van een gezonde portal.](/sharepoint/portal-health) 

> [!NOTE]
> Deze functie is niet beschikbaar voor Office 365 Duitsland, Office 365 beheerd door 21Vianet (China) of microsoft 365 Amerikaanse overheidsplannen.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>App-installatie en verbinding maken met SharePoint Online
1. [Download de nieuwste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Als u een eerdere versie van de SharePoint Online Management Shell hebt geïnstalleerd, gaat u naar Programma's toevoegen of verwijderen en verwijdert u 'SharePoint Online Management Shell'. <br>Selecteer op de pagina Downloadcentrum uw taal en klik vervolgens op de knop Downloaden. U wordt gevraagd om te kiezen tussen het downloaden van een x64- en x86.msi-bestand. Download het x64-bestand als u de 64-bits versie van Windows of het x86-bestand gebruikt als u de 32-bits versie gebruikt. Zie Welke versie van windows-besturingssysteem gebruik ik? als u het [niet weet.](https://support.microsoft.com/help/13443/windows-which-operating-system) Voer het bestand na het downloaden uit en volg de stappen in de wizard Instellen.

2. Maak verbinding met SharePoint als [globale beheerder of SharePoint-beheerder](/sharepoint/sharepoint-admin-role) in Microsoft 365. Zie Aan de slag [met SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)voor meer informatie.


## <a name="view-any-existing-portal-launch-setups"></a>Bestaande installatie voor het starten van portals weergeven

Als u wilt zien of er bestaande configuraties voor het starten van portals zijn:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Een portallancering op de site plannen

Het aantal benodigde golven is afhankelijk van de verwachte startgrootte. 
- Minder dan 10.000 gebruikers: 1 golf
- 10.000 tot 30.000 gebruikers: 3 golven 
- 30.000 tot 100.000 gebruikers: 5 golven
- Meer dan 100.000 gebruikers: 5 golven en neem contact op met uw Microsoft-accountteam

### <a name="steps-for-bidirectional-redirection"></a>Stappen voor bidirectionele omleiding

Bidirectionele omleiding omvat het starten van een nieuwe moderne SharePoint Online-portal om een bestaande klassieke of moderne SharePoint-portal te vervangen. Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site gaan. Gebruikers in een niet-gestarte golf die toegang proberen te krijgen tot de nieuwe site, worden teruggeleid naar de oude site totdat hun golf wordt gestart. 

We ondersteunen alleen omleiding tussen de standaard startpagina op de oude site en de standaard startpagina op de nieuwe site. Als u beheerders of eigenaren hebt die toegang nodig hebben tot de oude en nieuwe sites zonder dat deze worden omgeleid, moet u ervoor zorgen dat deze worden weergegeven met de `WaveOverrideUsers` parameter.

Gebruikers op een gefaseerd manier migreren van een bestaande SharePoint-site naar een nieuwe SharePoint-site:

1. Voer de volgende opdracht uit om portallancerings golven aan te wijzen.
   
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

2. Volledige validatie. Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid. 

### <a name="steps-for-redirection-to-temporary-page"></a>Stappen voor omleiding naar tijdelijke pagina

Tijdelijke omleiding van pagina's moet worden gebruikt wanneer er geen bestaande SharePoint-portal bestaat. Gebruikers worden op een gefaseerd manier doorgestuurd naar een nieuwe moderne SharePoint Online-portal. Als een gebruiker in een golf zit die niet is gestart, wordt deze omgeleid naar een tijdelijke pagina (elke URL). 

1. Voer de volgende opdracht uit om portallancerings golven aan te wijzen.
   
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

2. Volledige validatie. Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Een portal starten op de site onderbreken of opnieuw starten

1. Voer de volgende opdracht uit om de voortgang van een portal te onderbreken en tijdelijk te voorkomen dat toekomstige golfprogressie optreedt:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Valideer dat alle gebruikers worden omgeleid naar de oude site. 

3. Voer de volgende opdracht uit als u een portallancering wilt starten die is onderbroken:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Controleer of de omleiding nu is hersteld. 

## <a name="delete-a-portal-launch-on-the-site"></a>Een portallancering op de site verwijderen

1. Voer de volgende opdracht uit om een portalstart gepland of in uitvoering voor een site te verwijderen.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Valideer dat er geen omleiding voor alle gebruikers gebeurt.

## <a name="learn-more"></a>Meer informatie
[Het plannen van een implementatieplan voor het starten van uw portal in SharePoint Online](./planportallaunchroll-out.md)