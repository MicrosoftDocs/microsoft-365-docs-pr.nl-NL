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
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="24daa-103">Uw portal starten met de Portal Launch Scheduler</span><span class="sxs-lookup"><span data-stu-id="24daa-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="24daa-104">Een portal is een SharePoint-site op uw intranet met een groot aantal sitekijkers die inhoud op de site gebruiken.</span><span class="sxs-lookup"><span data-stu-id="24daa-104">A portal is a SharePoint site on your intranet that has a large number of site viewers who consume content on the site.</span></span> <span data-ttu-id="24daa-105">Het starten van uw portal in golven is een belangrijk onderdeel om ervoor te zorgen dat gebruikers een soepele en performante ervaring hebben met het openen van een nieuwe SharePoint Online-portal.</span><span class="sxs-lookup"><span data-stu-id="24daa-105">Launching your portal in waves is an important part of ensuring users have a smooth and performant experience accessing a new SharePoint Online portal.</span></span> 

<span data-ttu-id="24daa-106">Starten in golven is een belangrijke manier om uw portal uit te rollen, zoals wordt beschreven in Het plannen van uw [portal launch roll-out plan in SharePoint Online.](./planportallaunchroll-out.md?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="24daa-106">Launching in waves is a key way to roll-out your portal, as detailed in [Planning your portal launch roll-out plan in SharePoint Online](./planportallaunchroll-out.md?view=o365-worldwide).</span></span> <span data-ttu-id="24daa-107">De Portal Launch Scheduler is ontworpen om u te helpen een wave/phased roll-out benadering te volgen door de omleidingen voor de nieuwe portal te beheren.</span><span class="sxs-lookup"><span data-stu-id="24daa-107">The Portal Launch Scheduler is designed to help you follow a wave / phased roll-out approach by managing the redirects for the new portal.</span></span> <span data-ttu-id="24daa-108">Tijdens elk van de golven kunt u feedback van gebruikers verzamelen en de prestaties tijdens elke implementatiegolf controleren.</span><span class="sxs-lookup"><span data-stu-id="24daa-108">During each of the waves, you can gather user feedback and monitor performance during each wave of deployment.</span></span> <span data-ttu-id="24daa-109">Dit heeft het voordeel dat u de portal langzaam introduceert, zodat u problemen kunt onderbreken en oplossen voordat u verdergaat met de volgende golf, en er uiteindelijk voor zorgt dat uw gebruikers een positieve ervaring hebben.</span><span class="sxs-lookup"><span data-stu-id="24daa-109">This has the advantage of slowly introducing the portal, giving you the option to pause and resolve issues before proceeding with the next wave, and ultimately ensuring a positive experience for your users.</span></span> 

<span data-ttu-id="24daa-110">Er zijn twee soorten omleiding:</span><span class="sxs-lookup"><span data-stu-id="24daa-110">There are two types of redirection:</span></span> 
- <span data-ttu-id="24daa-111">bidirectioneel: start een nieuwe moderne SharePoint Online-portal om een bestaande klassieke of moderne SharePoint-portal te vervangen</span><span class="sxs-lookup"><span data-stu-id="24daa-111">bidirectional: launch a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal</span></span> 
- <span data-ttu-id="24daa-112">tijdelijke omleiding van pagina's: start een nieuwe moderne SharePoint Online-portal zonder bestaande SharePoint-portal</span><span class="sxs-lookup"><span data-stu-id="24daa-112">temporary page redirection: launch a new modern SharePoint Online portal with no existing SharePoint portal</span></span>

<span data-ttu-id="24daa-113">De planning voor het starten van portals is alleen beschikbaar voor het starten van moderne SharePoint Online-portals (dat wil zeggen communicatiesites).</span><span class="sxs-lookup"><span data-stu-id="24daa-113">The portal launch scheduler is only available to launch modern SharePoint Online portals (i.e. communication sites).</span></span> <span data-ttu-id="24daa-114">De lanceringen moeten ten minste 7 dagen van tevoren zijn gepland.</span><span class="sxs-lookup"><span data-stu-id="24daa-114">Launches must be scheduled at least 7 days in advance.</span></span> <span data-ttu-id="24daa-115">Het aantal benodigde golven wordt bepaald door het verwachte aantal gebruikers.</span><span class="sxs-lookup"><span data-stu-id="24daa-115">The number of waves required is determined by the expected number of users.</span></span> <span data-ttu-id="24daa-116">Voordat u een portalstart wilt plannen, moet het hulpprogramma Paginadiagnose voor [SharePoint](./page-diagnostics-for-spo.md) worden uitgevoerd om te controleren of de startpagina van de portal gezond is.</span><span class="sxs-lookup"><span data-stu-id="24daa-116">Before scheduling a portal launch, the [Page Diagnostics for SharePoint tool](./page-diagnostics-for-spo.md) must be run to verify that the home page on the portal is healthy.</span></span> <span data-ttu-id="24daa-117">Aan het einde van de portallancering hebben alle gebruikers met machtigingen voor de site toegang tot de nieuwe site.</span><span class="sxs-lookup"><span data-stu-id="24daa-117">At the end of the portal launch, all users with permissions to the site will be able to access the new site.</span></span> 

<span data-ttu-id="24daa-118">Voor meer informatie over het starten van een succesvolle portal, volgt u de basisprincipes, procedures en aanbevelingen die worden beschreven in Het maken, starten en [onderhouden van een gezonde portal.](/sharepoint/portal-health)</span><span class="sxs-lookup"><span data-stu-id="24daa-118">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in [Creating, launching and maintaining a healthy portal](/sharepoint/portal-health).</span></span> 

> [!NOTE]
> <span data-ttu-id="24daa-119">Deze functie is niet beschikbaar voor Office 365 Duitsland, Office 365 beheerd door 21Vianet (China) of microsoft 365 Amerikaanse overheidsplannen.</span><span class="sxs-lookup"><span data-stu-id="24daa-119">This feature is not available for Office 365 Germany, Office 365 operated by 21Vianet (China), or Microsoft 365 US Government plans.</span></span>

## <a name="app-setup-and-connecting-to-sharepoint-online"></a><span data-ttu-id="24daa-120">App-installatie en verbinding maken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="24daa-120">App setup and connecting to SharePoint Online</span></span>
1. <span data-ttu-id="24daa-121">[Download de nieuwste SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span><span class="sxs-lookup"><span data-stu-id="24daa-121">[Download the latest SharePoint Online Management Shell](https://go.microsoft.com/fwlink/p/?LinkId=255251).</span></span>

    > [!NOTE]
    > <span data-ttu-id="24daa-122">Als u een eerdere versie van de SharePoint Online Management Shell hebt geïnstalleerd, gaat u naar Programma's toevoegen of verwijderen en verwijdert u 'SharePoint Online Management Shell'.</span><span class="sxs-lookup"><span data-stu-id="24daa-122">If you installed a previous version of the SharePoint Online Management Shell, go to Add or remove programs and uninstall "SharePoint Online Management Shell."</span></span> <br><span data-ttu-id="24daa-123">Selecteer op de pagina Downloadcentrum uw taal en klik vervolgens op de knop Downloaden.</span><span class="sxs-lookup"><span data-stu-id="24daa-123">On the Download Center page, select your language and then click the Download button.</span></span> <span data-ttu-id="24daa-124">U wordt gevraagd om te kiezen tussen het downloaden van een x64- en x86.msi-bestand.</span><span class="sxs-lookup"><span data-stu-id="24daa-124">You'll be asked to choose between downloading a x64 and x86 .msi file.</span></span> <span data-ttu-id="24daa-125">Download het x64-bestand als u de 64-bits versie van Windows of het x86-bestand gebruikt als u de 32-bits versie gebruikt.</span><span class="sxs-lookup"><span data-stu-id="24daa-125">Download the x64 file if you're running the 64-bit version of Windows or the x86 file if you're running the 32-bit version.</span></span> <span data-ttu-id="24daa-126">Zie Welke versie van windows-besturingssysteem gebruik ik? als u het [niet weet.](https://support.microsoft.com/help/13443/windows-which-operating-system)</span><span class="sxs-lookup"><span data-stu-id="24daa-126">If you don't know, see [Which version of Windows operating system am I running?](https://support.microsoft.com/help/13443/windows-which-operating-system).</span></span> <span data-ttu-id="24daa-127">Voer het bestand na het downloaden uit en volg de stappen in de wizard Instellen.</span><span class="sxs-lookup"><span data-stu-id="24daa-127">After the file downloads, run it and follow the steps in the Setup Wizard.</span></span>

2. <span data-ttu-id="24daa-128">Maak verbinding met SharePoint als [globale beheerder of SharePoint-beheerder](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="24daa-128">Connect to SharePoint as a [global admin or SharePoint admin](/sharepoint/sharepoint-admin-role) in Microsoft 365.</span></span> <span data-ttu-id="24daa-129">Zie Aan de slag [met SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="24daa-129">To learn how, see [Getting started with SharePoint Online Management Shell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).</span></span>


## <a name="view-any-existing-portal-launch-setups"></a><span data-ttu-id="24daa-130">Bestaande installatie voor het starten van portals weergeven</span><span class="sxs-lookup"><span data-stu-id="24daa-130">View any existing portal launch setups</span></span>

<span data-ttu-id="24daa-131">Als u wilt zien of er bestaande configuraties voor het starten van portals zijn:</span><span class="sxs-lookup"><span data-stu-id="24daa-131">To see if there are existing portal launch configurations:</span></span>

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a><span data-ttu-id="24daa-132">Een portallancering op de site plannen</span><span class="sxs-lookup"><span data-stu-id="24daa-132">Schedule a portal launch on the site</span></span>

<span data-ttu-id="24daa-133">Het aantal benodigde golven is afhankelijk van de verwachte startgrootte.</span><span class="sxs-lookup"><span data-stu-id="24daa-133">The number of waves required depends on your expected launch size.</span></span> 
- <span data-ttu-id="24daa-134">Minder dan 10.000 gebruikers: 1 golf</span><span class="sxs-lookup"><span data-stu-id="24daa-134">Less than 10k users: 1 wave</span></span>
- <span data-ttu-id="24daa-135">10.000 tot 30.000 gebruikers: 3 golven</span><span class="sxs-lookup"><span data-stu-id="24daa-135">10k to 30k users: 3 waves</span></span> 
- <span data-ttu-id="24daa-136">30.000 tot 100.000 gebruikers: 5 golven</span><span class="sxs-lookup"><span data-stu-id="24daa-136">30k+ to 100k users: 5 waves</span></span>
- <span data-ttu-id="24daa-137">Meer dan 100.000 gebruikers: 5 golven en neem contact op met uw Microsoft-accountteam</span><span class="sxs-lookup"><span data-stu-id="24daa-137">More than 100k users: 5 waves and contact your Microsoft account team</span></span>

### <a name="steps-for-bidirectional-redirection"></a><span data-ttu-id="24daa-138">Stappen voor bidirectionele omleiding</span><span class="sxs-lookup"><span data-stu-id="24daa-138">Steps for bidirectional redirection</span></span>

<span data-ttu-id="24daa-139">Bidirectionele omleiding omvat het starten van een nieuwe moderne SharePoint Online-portal om een bestaande klassieke of moderne SharePoint-portal te vervangen.</span><span class="sxs-lookup"><span data-stu-id="24daa-139">Bidirectional redirection involves launching a new modern SharePoint Online portal to replace an existing SharePoint classic or modern portal.</span></span> <span data-ttu-id="24daa-140">Gebruikers in actieve golven worden omgeleid naar de nieuwe site, ongeacht of ze naar de oude of nieuwe site gaan.</span><span class="sxs-lookup"><span data-stu-id="24daa-140">Users in active waves will be redirected to the new site regardless of whether they navigate to the old or new site.</span></span> <span data-ttu-id="24daa-141">Gebruikers in een niet-gestarte golf die toegang proberen te krijgen tot de nieuwe site, worden teruggeleid naar de oude site totdat hun golf wordt gestart.</span><span class="sxs-lookup"><span data-stu-id="24daa-141">Users in a non-launched wave that try to access the new site will be redirected back to the old site until their wave is launched.</span></span> 

<span data-ttu-id="24daa-142">We ondersteunen alleen omleiding tussen de standaard startpagina op de oude site en de standaard startpagina op de nieuwe site.</span><span class="sxs-lookup"><span data-stu-id="24daa-142">We only support redirection between the default home page on the old site and the default home page on the new site.</span></span> <span data-ttu-id="24daa-143">Als u beheerders of eigenaren hebt die toegang nodig hebben tot de oude en nieuwe sites zonder dat deze worden omgeleid, moet u ervoor zorgen dat deze worden weergegeven met de `WaveOverrideUsers` parameter.</span><span class="sxs-lookup"><span data-stu-id="24daa-143">Should you have administrators or owners that need access to the old and new sites without being redirected, ensure they are listed using the `WaveOverrideUsers` parameter.</span></span>

<span data-ttu-id="24daa-144">Gebruikers op een gefaseerd manier migreren van een bestaande SharePoint-site naar een nieuwe SharePoint-site:</span><span class="sxs-lookup"><span data-stu-id="24daa-144">To migrate users from an existing SharePoint site to a new SharePoint site in a staged manner:</span></span>

1. <span data-ttu-id="24daa-145">Voer de volgende opdracht uit om portallancerings golven aan te wijzen.</span><span class="sxs-lookup"><span data-stu-id="24daa-145">Run the following command to designate portal launch waves.</span></span>
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="24daa-146">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="24daa-146">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="24daa-147">Volledige validatie.</span><span class="sxs-lookup"><span data-stu-id="24daa-147">Complete validation.</span></span> <span data-ttu-id="24daa-148">Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid.</span><span class="sxs-lookup"><span data-stu-id="24daa-148">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

### <a name="steps-for-redirection-to-temporary-page"></a><span data-ttu-id="24daa-149">Stappen voor omleiding naar tijdelijke pagina</span><span class="sxs-lookup"><span data-stu-id="24daa-149">Steps for redirection to temporary page</span></span>

<span data-ttu-id="24daa-150">Tijdelijke omleiding van pagina's moet worden gebruikt wanneer er geen bestaande SharePoint-portal bestaat.</span><span class="sxs-lookup"><span data-stu-id="24daa-150">Temporary page redirection should be used when no existing SharePoint portal exists.</span></span> <span data-ttu-id="24daa-151">Gebruikers worden op een gefaseerd manier doorgestuurd naar een nieuwe moderne SharePoint Online-portal.</span><span class="sxs-lookup"><span data-stu-id="24daa-151">Users are directed to a new modern SharePoint Online portal in a staged manner.</span></span> <span data-ttu-id="24daa-152">Als een gebruiker in een golf zit die niet is gestart, wordt deze omgeleid naar een tijdelijke pagina (elke URL).</span><span class="sxs-lookup"><span data-stu-id="24daa-152">If a user is in a wave that has not been launched, they will be redirected to a temporary page (any URL).</span></span> 

1. <span data-ttu-id="24daa-153">Voer de volgende opdracht uit om portallancerings golven aan te wijzen.</span><span class="sxs-lookup"><span data-stu-id="24daa-153">Run the following command to designate portal launch waves.</span></span>
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

<span data-ttu-id="24daa-154">Voorbeeld:</span><span class="sxs-lookup"><span data-stu-id="24daa-154">Example:</span></span>
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. <span data-ttu-id="24daa-155">Volledige validatie.</span><span class="sxs-lookup"><span data-stu-id="24daa-155">Complete validation.</span></span> <span data-ttu-id="24daa-156">Het kan 5-10 minuten duren voordat de omleiding de configuratie van de service heeft voltooid.</span><span class="sxs-lookup"><span data-stu-id="24daa-156">It can take 5-10 minutes for the redirection to complete its configuration across the service.</span></span> 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a><span data-ttu-id="24daa-157">Een portal starten op de site onderbreken of opnieuw starten</span><span class="sxs-lookup"><span data-stu-id="24daa-157">Pause or restart a portal launch on the site</span></span>

1. <span data-ttu-id="24daa-158">Voer de volgende opdracht uit om de voortgang van een portal te onderbreken en tijdelijk te voorkomen dat toekomstige golfprogressie optreedt:</span><span class="sxs-lookup"><span data-stu-id="24daa-158">To pause a portal launch in progress and temporarily prevent upcoming wave progressions from occurring, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. <span data-ttu-id="24daa-159">Valideer dat alle gebruikers worden omgeleid naar de oude site.</span><span class="sxs-lookup"><span data-stu-id="24daa-159">Validate that all users are redirected to the old site.</span></span> 

3. <span data-ttu-id="24daa-160">Voer de volgende opdracht uit als u een portallancering wilt starten die is onderbroken:</span><span class="sxs-lookup"><span data-stu-id="24daa-160">To restart a portal launch that's been paused, run the following command:</span></span>

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. <span data-ttu-id="24daa-161">Controleer of de omleiding nu is hersteld.</span><span class="sxs-lookup"><span data-stu-id="24daa-161">Validate that the redirection is now restored.</span></span> 

## <a name="delete-a-portal-launch-on-the-site"></a><span data-ttu-id="24daa-162">Een portallancering op de site verwijderen</span><span class="sxs-lookup"><span data-stu-id="24daa-162">Delete a portal launch on the site</span></span>

1. <span data-ttu-id="24daa-163">Voer de volgende opdracht uit om een portalstart gepland of in uitvoering voor een site te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="24daa-163">Run the following command to delete a portal launch scheduled or in progress for a site.</span></span>

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. <span data-ttu-id="24daa-164">Valideer dat er geen omleiding voor alle gebruikers gebeurt.</span><span class="sxs-lookup"><span data-stu-id="24daa-164">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="24daa-165">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="24daa-165">Learn more</span></span>
[<span data-ttu-id="24daa-166">Het plannen van een implementatieplan voor het starten van uw portal in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="24daa-166">Planning your portal launch roll-out plan in SharePoint Online</span></span>](./planportallaunchroll-out.md)