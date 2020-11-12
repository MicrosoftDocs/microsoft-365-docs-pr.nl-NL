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
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a><span data-ttu-id="81fb3-103">De portal starten met behulp van de lanceer planner voor portal</span><span class="sxs-lookup"><span data-stu-id="81fb3-103">Launch your portal using the Portal Launch Scheduler</span></span>

<span data-ttu-id="81fb3-104">U kunt de portal starten met de start Planner van de portal door eerst de mogelijkheid van de tenantbeheerder te valideren voor het instellen van een golven voor een nieuwe portal.</span><span class="sxs-lookup"><span data-stu-id="81fb3-104">You can launch your portal using the Portal Launch Scheduler by first validating the tenant admin's ability to setup a waves for a new portal.</span></span> <span data-ttu-id="81fb3-105">Vervolgens kan de beheerder een omleiding van aanvragen valideren, op basis van het bestaan van een gebruiker in de actieve golven.</span><span class="sxs-lookup"><span data-stu-id="81fb3-105">Then the admin can validate a redirection of requests, based on the existence of a user in the active waves.</span></span>

<span data-ttu-id="81fb3-106">Als u meer wilt weten over het starten van een succesvolle Portal, volgt u de basisprincipes, procedures en aanbevelingen die specifiek zijn voor het [maken, starten en onderhouden van een gezonde Portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span><span class="sxs-lookup"><span data-stu-id="81fb3-106">For more information about launching a successful portal, follow the basic principles, practices, and recommendations detailed in the [Creating, launching and maintaining a healthy portal](https://go.microsoft.com/fwlink/?linkid=2105838).</span></span> 

## <a name="app-setup"></a><span data-ttu-id="81fb3-107">App instellen</span><span class="sxs-lookup"><span data-stu-id="81fb3-107">App setup</span></span>
1. <span data-ttu-id="81fb3-108">Verwijder indien `Microsoft.Online.SharePoint.PowerShell` van uw computer een bestaande versie via het Configuratiescherm.</span><span class="sxs-lookup"><span data-stu-id="81fb3-108">Uninstall if there an existing `Microsoft.Online.SharePoint.PowerShell` from your machine through the control panel.</span></span>
2. <span data-ttu-id="81fb3-109">In PowerShell Passive `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .</span><span class="sxs-lookup"><span data-stu-id="81fb3-109">On PowerShell pass `Install-Module -Name Microsoft.Online.SharePoint.PowerShell`.</span></span>

## <a name="connect-to-sharepoint-online"></a><span data-ttu-id="81fb3-110">Verbinding maken met SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="81fb3-110">Connect to SharePoint Online</span></span>
1. <span data-ttu-id="81fb3-111">Open de [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span><span class="sxs-lookup"><span data-stu-id="81fb3-111">Open the [SharePoint Online Management Shell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) in Windows.</span></span>
2. <span data-ttu-id="81fb3-112">Maak verbinding met de Tenant als beheerder.</span><span class="sxs-lookup"><span data-stu-id="81fb3-112">Connect to your tenant as an admin.</span></span>
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  <span data-ttu-id="81fb3-113">Geef uw wachtwoord op wanneer hierom wordt gevraagd.</span><span class="sxs-lookup"><span data-stu-id="81fb3-113">Supply your password when prompted.</span></span>

## <a name="command-to-get-an-existing-setup"></a><span data-ttu-id="81fb3-114">Opdracht voor het weergeven van een bestaande instelling</span><span class="sxs-lookup"><span data-stu-id="81fb3-114">Command to get an existing setup</span></span>

<span data-ttu-id="81fb3-115">Bestaande start configuraties van portal weergeven:</span><span class="sxs-lookup"><span data-stu-id="81fb3-115">To view existing portal launch configurations:</span></span>

1. <span data-ttu-id="81fb3-116">Doorgeven `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .</span><span class="sxs-lookup"><span data-stu-id="81fb3-116">Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite`.</span></span>
2. <span data-ttu-id="81fb3-117">Geef de parameter extra `-DisplayFormat Raw` weer als u de Wave verzameling wilt weergeven die is opgemaakt als een RAW-invoer opmaak.</span><span class="sxs-lookup"><span data-stu-id="81fb3-117">Pass the additional parameter `-DisplayFormat Raw` if you wish to see the wave collection formatted as a raw input format.</span></span>

## <a name="commands-for-bi-directional-redirection"></a><span data-ttu-id="81fb3-118">Opdrachten voor bi-directionele omleiding</span><span class="sxs-lookup"><span data-stu-id="81fb3-118">Commands for bi-directional redirection</span></span>

<span data-ttu-id="81fb3-119">Oude sitegebruikers migreren naar de nieuwe site op een gefaseerde manier:</span><span class="sxs-lookup"><span data-stu-id="81fb3-119">To migrate old site users to the new site in a staged manner:</span></span>

1. <span data-ttu-id="81fb3-120">Lanceer golftjes voor de portal maken.</span><span class="sxs-lookup"><span data-stu-id="81fb3-120">Create Portal launch waves.</span></span>
   - <span data-ttu-id="81fb3-121">Dit is alleen van toepassing op de testfase van de eerste release.</span><span class="sxs-lookup"><span data-stu-id="81fb3-121">This is only applicable in the early release test phase.</span></span>
   - <span data-ttu-id="81fb3-122">Als u de invloed van de wijziging direct wilt testen, controleert u of de eerste golf `LaunchDateUtc` is ingesteld op de huidige datum.</span><span class="sxs-lookup"><span data-stu-id="81fb3-122">To test the impact of the change immediately, make sure the first wave `LaunchDateUtc` is set to the current date.</span></span> <span data-ttu-id="81fb3-123">Als u deze vlag niet opgeeft, wordt er een foutbericht weergegeven.</span><span class="sxs-lookup"><span data-stu-id="81fb3-123">If you do not supply this flag, you get an error message.</span></span> <span data-ttu-id="81fb3-124">Deze fout treedt op omdat de start in de productie minimaal zeven dagen tevoren moet worden gepland.</span><span class="sxs-lookup"><span data-stu-id="81fb3-124">This error happens because launches in production must be scheduled at least 7 days in advance.</span></span>

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="81fb3-125">Validatie voltooien.</span><span class="sxs-lookup"><span data-stu-id="81fb3-125">Complete validation.</span></span>
  - <span data-ttu-id="81fb3-126">Het duurt maximaal 5 minuten voordat u de configuratie via de service kunt voltooien, dus moet u wachten voordat u verdergaat.</span><span class="sxs-lookup"><span data-stu-id="81fb3-126">It can take up to 5 minutes for the redirection to complete its configuration across the service, so please wait before continuing.</span></span>
  - <span data-ttu-id="81fb3-127">Als u zich aanmeldt met de opgegeven gebruiker `WaveOverrideUsers` , wordt niets gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="81fb3-127">If you login with the user specified as `WaveOverrideUsers`, then nothing changes.</span></span> <span data-ttu-id="81fb3-128">U dient op de site te blijven staan waar u naar moet navigeren.</span><span class="sxs-lookup"><span data-stu-id="81fb3-128">You should be staying at the site you navigated to.</span></span>
  - <span data-ttu-id="81fb3-129">Meld u aan met een gebruiker die deel uitmaakt van *kijkers SG1*.</span><span class="sxs-lookup"><span data-stu-id="81fb3-129">Login with a user who is part of *Viewers SG1*.</span></span>
    - <span data-ttu-id="81fb3-130">Ga naar de oude site, waarna u wordt doorgestuurd naar de nieuwe site.</span><span class="sxs-lookup"><span data-stu-id="81fb3-130">Navigate to the old site and you should be redirected to the new site.</span></span>
    - <span data-ttu-id="81fb3-131">Ga naar de nieuwe site en blijf op de nieuwe site.</span><span class="sxs-lookup"><span data-stu-id="81fb3-131">Navigate to the new site and you should be stay on the new site.</span></span>
    - <span data-ttu-id="81fb3-132">Meld u aan met een gebruiker in de *SG2 van kijkers* en blader naar de oude site en blijf op de oude site.</span><span class="sxs-lookup"><span data-stu-id="81fb3-132">Log with user in *Viewers SG2* and navigate to the old site and stay on the old site.</span></span>
    - <span data-ttu-id="81fb3-133">Ga naar de nieuwe site, waarna u wordt doorgestuurd naar de oude site.</span><span class="sxs-lookup"><span data-stu-id="81fb3-133">Navigate to the new site and you should be redirected to the old site.</span></span>

3. <span data-ttu-id="81fb3-134">Start de portal start.</span><span class="sxs-lookup"><span data-stu-id="81fb3-134">Pause Portal launch.</span></span>
  - <span data-ttu-id="81fb3-135">Als u de start golfs moet onderbreken, kunt u deze onderbreken voor het aantal dagen van ' x '.</span><span class="sxs-lookup"><span data-stu-id="81fb3-135">If you need to pause the launch waves, you can pause them for "x" number of days.</span></span> <span data-ttu-id="81fb3-136">`Status`Als u wilt dat de vlag wordt ingesteld om te onderbreken, voorkomt u dat er nieuwe golf.</span><span class="sxs-lookup"><span data-stu-id="81fb3-136">Setting the `Status` flag to pause prevents all upcoming wave progressions.</span></span> 
  - <span data-ttu-id="81fb3-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="81fb3-137">`Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="81fb3-138">Hiermee wordt gecontroleerd of alle gebruikers worden doorgestuurd naar de oude site.</span><span class="sxs-lookup"><span data-stu-id="81fb3-138">This validates that all users are redirected to the old site.</span></span>

4. <span data-ttu-id="81fb3-139">Start de voortgang van het starten van de portal opnieuw.</span><span class="sxs-lookup"><span data-stu-id="81fb3-139">Restart the portal launch progression.</span></span> 
  - <span data-ttu-id="81fb3-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="81fb3-140">`Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="81fb3-141">Valideren dat de omleiding nu wordt hersteld.</span><span class="sxs-lookup"><span data-stu-id="81fb3-141">Validate that the redirection is now restored.</span></span>

5. <span data-ttu-id="81fb3-142">Een portal voor het openen van een Portal verwijderen.</span><span class="sxs-lookup"><span data-stu-id="81fb3-142">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="81fb3-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="81fb3-143">`Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="81fb3-144">Controleer of er geen omleiding voor alle gebruikers gebeurt.</span><span class="sxs-lookup"><span data-stu-id="81fb3-144">Validate that no redirection happens for all users.</span></span>

## <a name="commands-for-redirection-to-temporary-page"></a><span data-ttu-id="81fb3-145">Opdrachten voor omleiding naar tijdelijke pagina</span><span class="sxs-lookup"><span data-stu-id="81fb3-145">Commands for redirection to temporary page</span></span>

<span data-ttu-id="81fb3-146">Voer de volgende stappen uit als u geen eerdere site hebt en u gebruikers niet in de Golf van de aanvoer op de pagina nieuwe portal wilt laten staan.</span><span class="sxs-lookup"><span data-stu-id="81fb3-146">Follow these steps if you have no previous site and you want to omit users not in the wave from landing on the new portal page.</span></span>

<span data-ttu-id="81fb3-147">Een tijdelijke pagina maken op een van de sites:</span><span class="sxs-lookup"><span data-stu-id="81fb3-147">To create a temporary page in any of the sites:</span></span>

1. <span data-ttu-id="81fb3-148">Maak een lanceer Golf voor de portal.</span><span class="sxs-lookup"><span data-stu-id="81fb3-148">Create a Portal launch Wave.</span></span>
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. <span data-ttu-id="81fb3-149">Validatie voltooien.</span><span class="sxs-lookup"><span data-stu-id="81fb3-149">Complete validation.</span></span>

  - <span data-ttu-id="81fb3-150">Wacht vijf minuten voordat u verder gaat, aangezien de actie maximaal vijf minuten kan duren.</span><span class="sxs-lookup"><span data-stu-id="81fb3-150">Wait five minutes before continuing, as the action can take up to five minutes to complete.</span></span>
  - <span data-ttu-id="81fb3-151">Meld u aan met de gebruiker die deel uitmaakt van *kijkers SG1* en:</span><span class="sxs-lookup"><span data-stu-id="81fb3-151">Log with the user who is part of *Viewers SG1* and:</span></span>
     - <span data-ttu-id="81fb3-152">Ga naar de nieuwe site en blijf op de nieuwe site.</span><span class="sxs-lookup"><span data-stu-id="81fb3-152">Navigate to the new site, and you should be stay on the new site.</span></span>
     - <span data-ttu-id="81fb3-153">Ga naar de pagina Temp en blijf op de pagina Temp.</span><span class="sxs-lookup"><span data-stu-id="81fb3-153">Navigate to the temp page, and you should be stay on the temp page.</span></span>
  - <span data-ttu-id="81fb3-154">Meld u aan met de gebruiker die deel uitmaakt van *kijkers SG2* en:</span><span class="sxs-lookup"><span data-stu-id="81fb3-154">Log with the user who is part of *Viewers SG2* and:</span></span>
     - <span data-ttu-id="81fb3-155">Ga naar de nieuwe site en u wordt omgeleid naar de pagina Temp.</span><span class="sxs-lookup"><span data-stu-id="81fb3-155">Navigate to the new site, and you should be redirected to the temp page.</span></span>
     - <span data-ttu-id="81fb3-156">Ga naar de pagina Temp en blijf op de pagina Temp.</span><span class="sxs-lookup"><span data-stu-id="81fb3-156">Navigate to the temp page, and you should stay on the temp page.</span></span>

3. <span data-ttu-id="81fb3-157">Een portal voor het openen van een Portal verwijderen.</span><span class="sxs-lookup"><span data-stu-id="81fb3-157">Delete a portal launch setup.</span></span>
  - <span data-ttu-id="81fb3-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span><span class="sxs-lookup"><span data-stu-id="81fb3-158">`Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.</span></span>
  - <span data-ttu-id="81fb3-159">Controleer of er geen omleiding voor alle gebruikers gebeurt.</span><span class="sxs-lookup"><span data-stu-id="81fb3-159">Validate that no redirection happens for all users.</span></span>

## <a name="learn-more"></a><span data-ttu-id="81fb3-160">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="81fb3-160">Learn more</span></span>
[<span data-ttu-id="81fb3-161">Rollen plan voor het lanceren van uw portal in SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="81fb3-161">Planning your portal launch roll-out plan in SharePoint Online</span></span>](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)