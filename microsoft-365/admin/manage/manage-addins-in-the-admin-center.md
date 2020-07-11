---
title: Invoegtoepassingen beheren in het beheercentrum
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Meer informatie over het implementeren van invoegtoepassingen voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het beheercentrum.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103091"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="a2f24-103">Invoegtoepassingen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a2f24-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="a2f24-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="a2f24-104">The admin center is changing.</span></span> <span data-ttu-id="a2f24-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="a2f24-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="a2f24-106">Met Office-invoegtoepassingen u uw documenten personaliseren en de manier waarop u toegang krijgt tot informatie op internet te stroomlijnen (zie [Start met uw Office-invoegtoepassing).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="a2f24-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="a2f24-107">Nadat een beheerder invoegtoepassingen voor gebruikers in een organisatie heeft geïmplementeerd, kan de beheerder invoegtoepassingen uitschakelen of in- of uitschakelen, bewerken, verwijderen en de toegang tot de invoegtoepassingen beheren.</span><span class="sxs-lookup"><span data-stu-id="a2f24-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="a2f24-108">Zie Invoegtoepassingen implementeren in het beheercentrum voor meer informatie over het installeren van [invoegtoepassingen vanuit het beheercentrum.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="a2f24-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="a2f24-109">Statussen van invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="a2f24-109">Add-in states</span></span>

<span data-ttu-id="a2f24-110">Een invoegtoepassing kan in **de** aan- of **uit-status** zijn.</span><span class="sxs-lookup"><span data-stu-id="a2f24-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="a2f24-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="a2f24-111">**State**</span></span>|<span data-ttu-id="a2f24-112">**Hoe de status optreedt**</span><span class="sxs-lookup"><span data-stu-id="a2f24-112">**How the state occurs**</span></span>|<span data-ttu-id="a2f24-113">**Impact**</span><span class="sxs-lookup"><span data-stu-id="a2f24-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a2f24-114">**Actief**</span><span class="sxs-lookup"><span data-stu-id="a2f24-114">**Active**</span></span>  <br/> |<span data-ttu-id="a2f24-115">De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.</span><span class="sxs-lookup"><span data-stu-id="a2f24-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="a2f24-116">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.</span><span class="sxs-lookup"><span data-stu-id="a2f24-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="a2f24-117">**Uitgeschakeld**</span><span class="sxs-lookup"><span data-stu-id="a2f24-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="a2f24-118">De beheerder heeft de invoegtoepassing uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a2f24-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="a2f24-119">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a2f24-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="a2f24-120">Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a2f24-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="a2f24-121">**Verwijderd**</span><span class="sxs-lookup"><span data-stu-id="a2f24-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="a2f24-122">De beheerder heeft de invoegtoepassing verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a2f24-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="a2f24-123">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a2f24-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="a2f24-124">Overweeg een invoegtoepassing te verwijderen als niemand deze niet meer gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a2f24-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="a2f24-125">Het uitschakelen van een invoegtoepassing kan bijvoorbeeld zinvol zijn als een invoegtoepassing alleen wordt gebruikt op specifieke tijden van het jaar.</span><span class="sxs-lookup"><span data-stu-id="a2f24-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="a2f24-126">Een invoegtoepassing verwijderen</span><span class="sxs-lookup"><span data-stu-id="a2f24-126">Delete an add-in</span></span>

<span data-ttu-id="a2f24-127">U ook een invoegtoepassing verwijderen die is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="a2f24-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="a2f24-128">Ga in het beheercentrum **Settings**naar de  >  **pagina Instellingenservices & invoegtoepassingen.**</span><span class="sxs-lookup"><span data-stu-id="a2f24-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="a2f24-129">Selecteer de geïmplementeerde invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a2f24-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a2f24-130">Klik op **Invoegtoepassing verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="a2f24-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="a2f24-131">Verwijder de invoegknop rechtsonder.</span><span class="sxs-lookup"><span data-stu-id="a2f24-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="a2f24-132">Valideer uw selecties en kies **Invoegtoepassing verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="a2f24-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="a2f24-133">Invoegtoepassingstoegang bewerken</span><span class="sxs-lookup"><span data-stu-id="a2f24-133">Edit add-in access</span></span>

<span data-ttu-id="a2f24-134">Na de implementatie kunnen beheerders ook de toegang van gebruikers tot invoegtoepassingen beheren.</span><span class="sxs-lookup"><span data-stu-id="a2f24-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="a2f24-135">Ga in het beheercentrum **Settings**naar de  >  **pagina Instellingenservices & invoegtoepassingen.**</span><span class="sxs-lookup"><span data-stu-id="a2f24-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="a2f24-136">Selecteer de geïmplementeerde invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a2f24-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a2f24-137">Klik op **Bewerken** onder **Wie heeft Toegang**.</span><span class="sxs-lookup"><span data-stu-id="a2f24-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="a2f24-138">Sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="a2f24-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="a2f24-139">Downloads van invoegtoepassing voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)</span><span class="sxs-lookup"><span data-stu-id="a2f24-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="a2f24-140">De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="a2f24-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="a2f24-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span><span class="sxs-lookup"><span data-stu-id="a2f24-141">As an organization you may wish to prevent the download of new Office add-ins from the Office Store.</span></span> <span data-ttu-id="a2f24-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span><span class="sxs-lookup"><span data-stu-id="a2f24-142">This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="a2f24-143">**Overname van invoegtoepassing uitschakelen**</span><span class="sxs-lookup"><span data-stu-id="a2f24-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="a2f24-144">Ga in het beheercentrum naar de pagina**Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="a2f24-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="a2f24-145">Selecteer **apps en services van gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="a2f24-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="a2f24-146">Schakel de optie uit om gebruikers toegang te geven tot het Office-winkel.</span><span class="sxs-lookup"><span data-stu-id="a2f24-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="a2f24-147">Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.</span><span class="sxs-lookup"><span data-stu-id="a2f24-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="a2f24-148">Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:</span><span class="sxs-lookup"><span data-stu-id="a2f24-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="a2f24-149">Windows</span><span class="sxs-lookup"><span data-stu-id="a2f24-149">Windows</span></span>
    
  - <span data-ttu-id="a2f24-150">Mac</span><span class="sxs-lookup"><span data-stu-id="a2f24-150">Mac</span></span>
    
  - <span data-ttu-id="a2f24-151">Office</span><span class="sxs-lookup"><span data-stu-id="a2f24-151">Office</span></span>
    
    
- <span data-ttu-id="a2f24-152">Aanschaf die begint vanuit **AppSource**</span><span class="sxs-lookup"><span data-stu-id="a2f24-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="a2f24-153">Invoegtoepassingen binnen Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a2f24-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="a2f24-154">Een gebruiker die toegang probeert te krijgen tot de store, ziet het volgende bericht: **Sorry, Microsoft 365 is geconfigureerd om individuele acquisitie van Office Store-invoegtoepassingen te voorkomen.**</span><span class="sxs-lookup"><span data-stu-id="a2f24-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="a2f24-155">Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:</span><span class="sxs-lookup"><span data-stu-id="a2f24-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="a2f24-156">Windows: 16.0.9001 - Momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a2f24-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="a2f24-157">Mac: 16.10.18011401: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a2f24-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="a2f24-158">iOS: 2.9.18010804: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a2f24-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="a2f24-159">Het web - Momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a2f24-159">The web - Currently available.</span></span>
    
<span data-ttu-id="a2f24-160">Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="a2f24-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="a2f24-161">Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="a2f24-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="a2f24-162">Zie [Identiteit, verificatie en autorisatie in Office 2016 voor](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="a2f24-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="a2f24-163">Meer over de ervaring van de eindgebruiker met invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="a2f24-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="a2f24-164">Nadat u een invoegtoepassing hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office-toepassingen (zie [Start met uw Office-invoegtoepassing).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="a2f24-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="a2f24-165">De invoegtoepassing wordt weergegeven op alle platforms die de invoegtoepassing ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="a2f24-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="a2f24-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span><span class="sxs-lookup"><span data-stu-id="a2f24-166">If the add-in supports add-in commands, the commands appear on the Office ribbon.</span></span> <span data-ttu-id="a2f24-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span><span class="sxs-lookup"><span data-stu-id="a2f24-167">In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office-lint met zoekvermeldingen](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="a2f24-169">Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="a2f24-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="a2f24-170">In Word 2016, Excel 2016 of PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="a2f24-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="a2f24-171">Selecteer \*\* \> Mijn invoegtoepassingen invoegen\*\*.</span><span class="sxs-lookup"><span data-stu-id="a2f24-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="a2f24-172">Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="a2f24-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="a2f24-173">Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ).</span><span class="sxs-lookup"><span data-stu-id="a2f24-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="a2f24-174">![Tabblad Beheerde van de pagina Office-invoegtoepassingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="a2f24-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="a2f24-175">In Outlook</span><span class="sxs-lookup"><span data-stu-id="a2f24-175">In Outlook</span></span>

1. <span data-ttu-id="a2f24-176">Selecteer op **het** startlint de optie **Invoegtoepassingen ophalen**.</span><span class="sxs-lookup"><span data-stu-id="a2f24-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="a2f24-177">![Knop Store in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="a2f24-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="a2f24-178">Selecteer **Beheerd beheer** in het linkernavigatiesysteem.</span><span class="sxs-lookup"><span data-stu-id="a2f24-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="a2f24-179">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="a2f24-179">Learn more</span></span>

[<span data-ttu-id="a2f24-180">Invoegtoepassingen implementeren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a2f24-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="a2f24-181">Lees meer over het maken en bouwen van [Office-invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=846362).</span><span class="sxs-lookup"><span data-stu-id="a2f24-181">Learn more about creating and building [Office Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362).</span></span>
  
<span data-ttu-id="a2f24-182">[Gebruik Gecentraliseerde PowerShell-cmdlets voor het beheren van invoegtoepassingen.](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="a2f24-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="a2f24-183">Problemen oplossen: gebruiker ziet geen invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="a2f24-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="a2f24-184">Minderjarigen en het verwerven van invoegtoepassingen uit de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="a2f24-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)