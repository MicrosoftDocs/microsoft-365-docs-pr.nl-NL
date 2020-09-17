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
description: Informatie over het implementeren van invoegtoepassingen voor gebruikers en groepen in uw organisatie met behulp van gecentraliseerde implementatie in het Beheercentrum.
ms.openlocfilehash: 10bca6776173c07a28b097f44c641c3e65a0cf6c
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948698"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="af73e-103">Invoegtoepassingen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="af73e-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="af73e-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="af73e-104">The admin center is changing.</span></span> <span data-ttu-id="af73e-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="af73e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="af73e-106">Met behulp van Office-invoegtoepassingen kunt u uw documenten aan uw persoonlijke voorkeur aanpassen en de manier waarop u toegang kunt krijgen tot de webversie van Office (Zie [uw Office-invoegtoepassing gaan gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="af73e-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="af73e-107">Nadat een beheerder invoegtoepassingen voor gebruikers in een organisatie heeft geïmplementeerd, kan de beheerder invoegtoepassingen in-of uitschakelen, bewerken, verwijderen en de toegang tot de invoegtoepassingen beheren.</span><span class="sxs-lookup"><span data-stu-id="af73e-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="af73e-108">Zie [invoegtoepassingen implementeren in het Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)voor meer informatie over het installeren van invoegtoepassingen vanuit het Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="af73e-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="af73e-109">Statussen van invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="af73e-109">Add-in states</span></span>

<span data-ttu-id="af73e-110">U kunt een invoeg **toepassing in-of** **uitschakelen** .</span><span class="sxs-lookup"><span data-stu-id="af73e-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="af73e-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="af73e-111">**State**</span></span>|<span data-ttu-id="af73e-112">**Hoe de status optreedt**</span><span class="sxs-lookup"><span data-stu-id="af73e-112">**How the state occurs**</span></span>|<span data-ttu-id="af73e-113">**Impact**</span><span class="sxs-lookup"><span data-stu-id="af73e-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af73e-114">**Actief**</span><span class="sxs-lookup"><span data-stu-id="af73e-114">**Active**</span></span>  <br/> |<span data-ttu-id="af73e-115">De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.</span><span class="sxs-lookup"><span data-stu-id="af73e-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="af73e-116">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.</span><span class="sxs-lookup"><span data-stu-id="af73e-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="af73e-117">**Uitgeschakeld**</span><span class="sxs-lookup"><span data-stu-id="af73e-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="af73e-118">De beheerder heeft de invoegtoepassing uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="af73e-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="af73e-119">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="af73e-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="af73e-120">Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="af73e-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="af73e-121">**Verwijderd**</span><span class="sxs-lookup"><span data-stu-id="af73e-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="af73e-122">De beheerder heeft de invoegtoepassing verwijderd.</span><span class="sxs-lookup"><span data-stu-id="af73e-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="af73e-123">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="af73e-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="af73e-124">Als u een invoegtoepassing niet meer gebruikt, kunt u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="af73e-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="af73e-125">Als u bijvoorbeeld een invoegtoepassing uitschakelt, kan het handig zijn als een invoegtoepassing alleen wordt gebruikt in specifieke tijden van het jaar.</span><span class="sxs-lookup"><span data-stu-id="af73e-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="af73e-126">Een invoegtoepassing verwijderen</span><span class="sxs-lookup"><span data-stu-id="af73e-126">Delete an add-in</span></span>

<span data-ttu-id="af73e-127">U kunt ook een invoegtoepassing verwijderen die is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="af73e-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="af73e-128">Ga in het Beheercentrum naar de pagina **instellingen**  >  **Services & invoegtoepassingen** .</span><span class="sxs-lookup"><span data-stu-id="af73e-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="af73e-129">Selecteer de geïmplementeerde invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="af73e-129">Select the deployed add-in.</span></span>

3. <span data-ttu-id="af73e-130">Klik op **invoegtoepassing verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="af73e-130">Click on **Delete Add-In**.</span></span> <span data-ttu-id="af73e-131">De knop invoegtoepassing in de rechterbenedenhoek verwijderen.</span><span class="sxs-lookup"><span data-stu-id="af73e-131">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="af73e-132">Valideer uw selecties en kies **invoegtoepassing verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="af73e-132">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="af73e-133">Toegang tot invoegtoepassing bewerken</span><span class="sxs-lookup"><span data-stu-id="af73e-133">Edit add-in access</span></span>

<span data-ttu-id="af73e-134">Na implementatie kunnen beheerders ook gebruikers toegang tot invoegtoepassingen beheren.</span><span class="sxs-lookup"><span data-stu-id="af73e-134">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="af73e-135">Ga in het Beheercentrum naar de pagina **instellingen**  >  **Services & invoegtoepassingen** .</span><span class="sxs-lookup"><span data-stu-id="af73e-135">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

2. <span data-ttu-id="af73e-136">Selecteer de geïmplementeerde invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="af73e-136">Select the deployed add-in.</span></span>

3. <span data-ttu-id="af73e-137">Klik op **bewerken** onder **wie toegang heeft**.</span><span class="sxs-lookup"><span data-stu-id="af73e-137">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="af73e-138">Sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="af73e-138">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="af73e-139">Downloads van invoegtoepassingen voorkomen door Office Store op alle clients uit te schakelen (met uitzondering van Outlook)</span><span class="sxs-lookup"><span data-stu-id="af73e-139">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="af73e-140">De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="af73e-140">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="af73e-p104">Als organisatie kunt u het downloaden van nieuwe Office-invoegtoepassingen vanuit Office Store verhinderen. Dit kunt u doen in combinatie met Gecentraliseerde implementatie om ervoor te zorgen dat alleen invoegtoepassingen die door organisaties zijn goedgekeurd voor gebruikers binnen de organisatie worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="af73e-p104">As an organization you may wish to prevent the download of new Office add-ins from the Office Store. This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="af73e-143">**Verwerving van invoegtoepassing uitschakelen**</span><span class="sxs-lookup"><span data-stu-id="af73e-143">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="af73e-144">Ga in het beheercentrum naar de pagina**Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="af73e-144">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>
    
3. <span data-ttu-id="af73e-145">Selecteer **apps en services van gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="af73e-145">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="af73e-146">Wis de optie om gebruikers toegang te bieden tot de Office Store.</span><span class="sxs-lookup"><span data-stu-id="af73e-146">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="af73e-147">Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.</span><span class="sxs-lookup"><span data-stu-id="af73e-147">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="af73e-148">Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:</span><span class="sxs-lookup"><span data-stu-id="af73e-148">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="af73e-149">Windows</span><span class="sxs-lookup"><span data-stu-id="af73e-149">Windows</span></span>
    
  - <span data-ttu-id="af73e-150">Mac</span><span class="sxs-lookup"><span data-stu-id="af73e-150">Mac</span></span>
    
  - <span data-ttu-id="af73e-151">Office</span><span class="sxs-lookup"><span data-stu-id="af73e-151">Office</span></span>
    
    
- <span data-ttu-id="af73e-152">Aanschaf die begint vanuit **AppSource**</span><span class="sxs-lookup"><span data-stu-id="af73e-152">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="af73e-153">Invoegtoepassingen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="af73e-153">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="af73e-154">Een gebruiker die toegang tot de Store wil hebben, ziet het volgende bericht: **Sorry, Microsoft 365 is zodanig geconfigureerd om individuele aanschaf van invoegtoepassingen van Office Store te voorkomen.**</span><span class="sxs-lookup"><span data-stu-id="af73e-154">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="af73e-155">Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:</span><span class="sxs-lookup"><span data-stu-id="af73e-155">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="af73e-156">Windows: 16.0.9001-momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="af73e-156">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="af73e-157">Mac: 16.10.18011401: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="af73e-157">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="af73e-158">iOS: 2.9.18010804: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="af73e-158">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="af73e-159">De webversie die op dat moment beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="af73e-159">The web - Currently available.</span></span>
    
<span data-ttu-id="af73e-160">Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="af73e-160">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="af73e-161">Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="af73e-161">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="af73e-162">Zie voor meer informatie [identiteit, authenticatie en autorisatie in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="af73e-162">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="af73e-163">Meer informatie over de eindgebruikers ervaring met invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="af73e-163">More about the end user experience with add-ins</span></span>

<span data-ttu-id="af73e-164">Wanneer u een invoegtoepassing hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office-toepassingen (Zie [uw Office-invoegtoepassing gaan gebruiken](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span><span class="sxs-lookup"><span data-stu-id="af73e-164">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="af73e-165">De invoegtoepassing wordt weergegeven op alle platforms die de invoegtoepassing ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="af73e-165">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="af73e-p107">Als de invoegtoepassing opdrachten van de invoegtoepassing ondersteunt, verschijnen de opdrachten in het Office-lint. In het volgende voorbeeld wordt de opdracht **Bronvermelding zoeken** weergegeven voor de invoegtoepassing **Bronvermeldingen**.</span><span class="sxs-lookup"><span data-stu-id="af73e-p107">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office-lint met zoek bronvermeldingen](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="af73e-169">Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="af73e-169">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="af73e-170">In Word 2016, Excel 2016 of PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="af73e-170">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="af73e-171">Selecteer \*\* \> mijn invoegtoepassingen invoegen\*\*.</span><span class="sxs-lookup"><span data-stu-id="af73e-171">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="af73e-172">Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="af73e-172">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="af73e-173">Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ).</span><span class="sxs-lookup"><span data-stu-id="af73e-173">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="af73e-174">![Tabblad beheerd door beheerder op de pagina Office-invoegtoepassingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="af73e-174">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="af73e-175">In Outlook</span><span class="sxs-lookup"><span data-stu-id="af73e-175">In Outlook</span></span>

1. <span data-ttu-id="af73e-176">Selecteer **invoegtoepassing downloaden**op het lint **Start** .</span><span class="sxs-lookup"><span data-stu-id="af73e-176">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="af73e-177">![Knop Store in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="af73e-177">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="af73e-178">Selecteer **beheerder beheerd** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="af73e-178">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="af73e-179">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="af73e-179">Learn more</span></span>

[<span data-ttu-id="af73e-180">Invoegtoepassingen implementeren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="af73e-180">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="af73e-181">Lees meer over het maken en bouwen van [Office-invoegtoepassingen](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="af73e-181">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="af73e-182">[PowerShell-cmdlets voor gecentraliseerde implementatie gebruiken om invoegtoepassingen te beheren](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span><span class="sxs-lookup"><span data-stu-id="af73e-182">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="af73e-183">Problemen oplossen: gebruikers kunnen geen invoegtoepassingen zien</span><span class="sxs-lookup"><span data-stu-id="af73e-183">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="af73e-184">Minderjarigen en het verkrijgen van invoegtoepassingen uit de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="af73e-184">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)