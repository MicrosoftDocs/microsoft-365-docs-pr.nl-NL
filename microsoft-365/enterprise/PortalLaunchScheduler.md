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
ms.openlocfilehash: 6a191cf323e180fa77614eb09bae4185228a5029
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087665"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="3580a-103">De portal starten met behulp van de lanceer planner voor portal</span><span class="sxs-lookup"><span data-stu-id="3580a-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="3580a-104">Een portal is een SharePoint-site op uw intranet met een groot aantal sitebezoekers die inhoud op de site gebruiken.</span><span class="sxs-lookup"><span data-stu-id="3580a-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="3580a-105">Het starten van de portal in golven is een belangrijk onderdeel van de zorgen dat gebruikers een eenvoudige en ervaren ervaring hebben om toegang te krijgen tot een nieuwe SharePoint Online-Portal.</span><span class="sxs-lookup"><span data-stu-id="3580a-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="3580a-106">De lancering in golven is een belangrijke manier om de portal uit te vouwen, zoals wordt uitgelegd in [het implementatieplan van uw portal lanceren in SharePoint Online](https://docs.microsoft.com/en-us/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="3580a-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](https://docs.microsoft.com/en-us/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide).</span></span> <span data-ttu-id="3580a-107">De lancerings planner voor de portal is bedoeld om u te helpen bij het volgen van een rol met Golf/gefaseerde samenvatting door de omleidingen voor de nieuwe portal te beheren.</span><span class="sxs-lookup"><span data-stu-id="3580a-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="3580a-108">U kunt tijdens elk van de golven feedback van gebruikers verzamelen en de prestaties controleren tijdens elke implementatie.</span><span class="sxs-lookup"><span data-stu-id="3580a-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="3580a-109">Dit heeft het voordeel van langzaam de portal, met de mogelijkheid om problemen te onderbreken en op te lossen voordat u verder gaat met de volgende golf, en de gebruikers uiteindelijk zorgen voor een gunstige ervaring.</span><span class="sxs-lookup"><span data-stu-id="3580a-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="3580a-110">Er zijn twee typen omleiding:</span><span class="sxs-lookup"><span data-stu-id="3580a-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="3580a-111">bidirectioneel: een nieuwe moderne SharePoint Online-Portal starten om een bestaande SharePoint-klassieke of moderne portal te vervangen</span><span class="sxs-lookup"><span data-stu-id="3580a-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="3580a-112">tijdelijke omleiding van pagina: een nieuwe moderne SharePoint Online-Portal starten zonder bestaande SharePoint-Portal</span><span class="sxs-lookup"><span data-stu-id="3580a-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="3580a-113">De lancerings planner voor de portal is alleen beschikbaar voor het openen van moderne SharePoint Online-portals, zoals Communicatiesites en moderne team sites.</span><span class="sxs-lookup"><span data-stu-id="3580a-113">The portal launch scheduler is only available to launch modern SharePoint Online portals, like communication sites and modern team sites.</span></span> <span data-ttu-id="3580a-114">Start moet ten minste 7 dagen vooraf worden gepland.</span><span class="sxs-lookup"><span data-stu-id="3580a-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="3580a-115">Het aantal vereiste golven wordt bepaald door het verwachte aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="3580a-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="3580a-116">Voordat u begint met het plannen van een portal, moet u eerst het [hulpprogramma pagina diagnose voor SharePoint](https://aka.ms/perftool) uitvoeren om te controleren of de startpagina op de portal in orde is.</span><span class="sxs-lookup"><span data-stu-id="3580a-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](https://aka.ms/perftool) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="3580a-117">Aan het einde van de start van de portal hebben alle gebruikers met machtigingen voor de site toegang tot de nieuwe site.</span><span class="sxs-lookup"><span data-stu-id="3580a-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="3580a-118">Als u meer wilt weten over het starten van een succesvolle Portal, volgt u de basisprincipes, procedures en aanbevelingen voor informatie over het [maken, starten en onderhouden van een gezonde Portal](https://docs.microsoft.com/sharepoint/portal-health).</span><span class="sxs-lookup"><span data-stu-id="3580a-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](https://docs.microsoft.com/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="3580a-119">Deze functie is niet beschikbaar voor Office 365 Duitsland, Office 365 beheerd door 21Vianet (China) of Microsoft 365 US Government-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="3580a-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="3580a-120">App instellen en verbinding maken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3580a-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="3580a-121">[Download de nieuwste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="3580a-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="3580a-122">Als u een eerdere versie van de SharePoint Online Management Shell hebt geïnstalleerd, gaat u naar Programma's installeren of verwijderen en klikt u op SharePoint Online Management Shell verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3580a-122">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="3580a-123">Selecteer uw taal op de pagina het Download centrum en klik vervolgens op de knop downloaden.</span><span class="sxs-lookup"><span data-stu-id="3580a-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="3580a-124">U wordt gevraagd te kiezen tussen het downloaden van een x64-en x86 MSI-bestand.</span><span class="sxs-lookup"><span data-stu-id="3580a-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="3580a-125">Download het x64-bestand als u werkt met de 64-bits versie van Windows of het x86-bestand als u de 32-bits versie uitvoert.</span><span class="sxs-lookup"><span data-stu-id="3580a-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="3580a-126">Als u het niet weet, raadpleegt u [welke versie van Windows-besturingssysteem gebruik ik?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span><span class="sxs-lookup"><span data-stu-id="3580a-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="3580a-127">Nadat het bestand is gedownload, voert u het uit en volgt u de stappen in de wizard Setup.</span><span class="sxs-lookup"><span data-stu-id="3580a-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="3580a-128">Maak verbinding met SharePoint als [globale beheerder of als SharePoint-beheerder](/sharepoint/sharepoint-admin-role) in microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3580a-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="3580a-129">Zie aan de slag [met SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3580a-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="3580a-130">Bestaande portal-start instellingen weergeven</span><span class="sxs-lookup"><span data-stu-id="3580a-130">View any existing portal launch setups</span></span>

<span data-ttu-id="3580a-131">Ga als volgt te werk om te controleren of er bestaande portal-lanceer configuraties zijn:</span><span class="sxs-lookup"><span data-stu-id="3580a-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="3580a-132">De lancering van een portal op de site plannen</span><span class="sxs-lookup"><span data-stu-id="3580a-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="3580a-133">Het aantal vereiste Golf punten is afhankelijk van de verwachte start grootte.</span><span class="sxs-lookup"><span data-stu-id="3580a-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="3580a-134">Minder dan 10.000 gebruikers: 1 Golf</span><span class="sxs-lookup"><span data-stu-id="3580a-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="3580a-135">10k voor 30k-gebruikers: 3 golven</span><span class="sxs-lookup"><span data-stu-id="3580a-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="3580a-136">30k + to afgesloten 100k gebruikers: 5 golven</span><span class="sxs-lookup"><span data-stu-id="3580a-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="3580a-137">Meer dan afgesloten 100k gebruikers: 5 golven en neem contact op met uw Microsoft-accountteam</span><span class="sxs-lookup"><span data-stu-id="3580a-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bi-directional-redirection"></a><span data-ttu-id="3580a-138">Stappen voor omleiding naar bi-richting</span><span class="sxs-lookup"><span data-stu-id="3580a-138">Steps for bi-directional redirection</span></span>

<span data-ttu-id="3580a-139">Bidirectionele omleiding houdt in dat u een nieuwe moderne SharePoint Online-Portal moet starten om een bestaande SharePoint-klassieke of moderne portal te vervangen.</span><span class="sxs-lookup"><span data-stu-id="3580a-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="3580a-140">Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site navigeren.</span><span class="sxs-lookup"><span data-stu-id="3580a-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="3580a-141">Gebruikers in een niet-geactiveerde golf die toegang proberen te krijgen tot de nieuwe site, worden weer naar de oude site omgeleid totdat hun Wave wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="3580a-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> <span data-ttu-id="3580a-142">Als u beheerders of eigenaren hebt die toegang moeten hebben tot de oude en nieuwe sites zonder te worden doorgestuurd, moet u ervoor zorgen dat ze worden weergegeven met behulp van de `WaveOverrideUsers` parameter.</span><span class="sxs-lookup"><span data-stu-id="3580a-142">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span> 

<span data-ttu-id="3580a-143">Gebruikers migreren van een bestaande SharePoint-site naar een nieuwe SharePoint-site op een gefaseerde manier:</span><span class="sxs-lookup"><span data-stu-id="3580a-143">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="3580a-144">Voer de volgende opdracht uit om de lanceer golven voor de portal aan te wijzen.</span><span class="sxs-lookup"><span data-stu-id="3580a-144">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="3580a-145">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3580a-145">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="3580a-146">Validatie voltooien.</span><span class="sxs-lookup"><span data-stu-id="3580a-146">Complete validation.</span></span> <span data-ttu-id="3580a-147">Het duurt 5-10 minuten voordat de omleiding is geconfigureerd via de service.</span><span class="sxs-lookup"><span data-stu-id="3580a-147">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="3580a-148">Stappen voor omleiding naar tijdelijke pagina</span><span class="sxs-lookup"><span data-stu-id="3580a-148">Steps for redirection to temporary page</span></span>

<span data-ttu-id="3580a-149">Tijdelijke omleiding voor pagina's moet worden gebruikt wanneer er geen bestaande SharePoint-Portal bestaat.</span><span class="sxs-lookup"><span data-stu-id="3580a-149">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="3580a-150">Gebruikers worden op een gefaseerde manier omgeleid naar een nieuwe moderne SharePoint Online-Portal.</span><span class="sxs-lookup"><span data-stu-id="3580a-150">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="3580a-151">Als een gebruiker een golf heeft die niet is gestart, wordt deze omgeleid naar een tijdelijke pagina (willekeurige URL).</span><span class="sxs-lookup"><span data-stu-id="3580a-151">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="3580a-152">Voer de volgende opdracht uit om de lanceer golven voor de portal aan te wijzen.</span><span class="sxs-lookup"><span data-stu-id="3580a-152">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="3580a-153">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="3580a-153">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="3580a-154">Validatie voltooien.</span><span class="sxs-lookup"><span data-stu-id="3580a-154">Complete validation.</span></span> <span data-ttu-id="3580a-155">Het duurt 5-10 minuten voordat de omleiding is geconfigureerd via de service.</span><span class="sxs-lookup"><span data-stu-id="3580a-155">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="3580a-156">De start van een portal op de site onderbreken of opnieuw starten</span><span class="sxs-lookup"><span data-stu-id="3580a-156">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="3580a-157">Voer de volgende opdracht uit om de start van een portal te onderbreken en de voortgang van een nieuwe golf versie te voorkomen.</span><span class="sxs-lookup"><span data-stu-id="3580a-157">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="3580a-158">Controleer of alle gebruikers worden omgeleid naar de oude site.</span><span class="sxs-lookup"><span data-stu-id="3580a-158">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="3580a-159">Voer de volgende opdracht uit als u een gepauzeerde Portal opnieuw wilt starten:</span><span class="sxs-lookup"><span data-stu-id="3580a-159">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="3580a-160">Valideren dat de omleiding nu wordt hersteld.</span><span class="sxs-lookup"><span data-stu-id="3580a-160">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="3580a-161">De start van een portal op de site verwijderen</span><span class="sxs-lookup"><span data-stu-id="3580a-161">Delete a portal launch on the site</span></span>
1. <span data-ttu-id="3580a-162">Maak een lanceer Golf voor de portal.</span><span class="sxs-lookup"><span data-stu-id="3580a-162">Create a Portal launch Wave.</span></span>
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="3580a-163">Voer de volgende opdracht uit als u een geplande Portal start of een uitvoering van een site wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3580a-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. <span data-ttu-id="3580a-164">Controleer of er geen omleiding voor alle gebruikers gebeurt.</span><span class="sxs-lookup"><span data-stu-id="3580a-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="3580a-165">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="3580a-165">Learn more</span></span>
[<span data-ttu-id="3580a-166">Rollen plan voor het lanceren van uw portal in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="3580a-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
