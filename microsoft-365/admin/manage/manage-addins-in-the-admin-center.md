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
description: Meer informatie over het gebruik van Gecentraliseerde invoegvoegingen voor het implementeren van invoegingen voor gebruikers en groepen in uw organisatie.
ms.openlocfilehash: b888c0f329e3f1f36f5aa566df7efbab07cd1f5f
ms.sourcegitcommit: a6b998fef5bdb35ec6726c743a24fea721535fcd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/05/2021
ms.locfileid: "50509132"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="aea2a-103">Invoegtoepassingen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="aea2a-103">Manage add-ins in the admin center</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="aea2a-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="aea2a-104">The admin center is changing.</span></span> <span data-ttu-id="aea2a-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="aea2a-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="aea2a-106">Met Office-invoegvoegingen kunt u uw documenten aan uw persoonlijke voorkeur personaliseren en de manier waarop u toegang krijgt tot informatie op internet stroomlijnen (zie [Uw Office-invoegonderdeel gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="aea2a-106">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="aea2a-107">Nadat een beheerder invoegingen voor gebruikers in een organisatie heeft geïmplementeerd, kan de beheerder invoegingen in- of uitschakelen, bewerken, verwijderen en de toegang tot de invoegingen beheren.</span><span class="sxs-lookup"><span data-stu-id="aea2a-107">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="aea2a-108">Zie Invoegingen implementeren in het beheercentrum voor meer informatie over het installeren van invoeg graag vanuit [het beheercentrum.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)</span><span class="sxs-lookup"><span data-stu-id="aea2a-108">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="aea2a-109">Statussen van invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="aea2a-109">Add-in states</span></span>

<span data-ttu-id="aea2a-110">Een invoeg mag de status **Aan** of **Uit** hebben.</span><span class="sxs-lookup"><span data-stu-id="aea2a-110">An add-in can be in either the **On** or **Off** state.</span></span>
  
|<span data-ttu-id="aea2a-111">**Status**</span><span class="sxs-lookup"><span data-stu-id="aea2a-111">**State**</span></span>|<span data-ttu-id="aea2a-112">**Hoe de status optreedt**</span><span class="sxs-lookup"><span data-stu-id="aea2a-112">**How the state occurs**</span></span>|<span data-ttu-id="aea2a-113">**Impact**</span><span class="sxs-lookup"><span data-stu-id="aea2a-113">**Impact**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="aea2a-114">**Actief**</span><span class="sxs-lookup"><span data-stu-id="aea2a-114">**Active**</span></span>  <br/> |<span data-ttu-id="aea2a-115">De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.</span><span class="sxs-lookup"><span data-stu-id="aea2a-115">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="aea2a-116">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.</span><span class="sxs-lookup"><span data-stu-id="aea2a-116">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="aea2a-117">**Uitgeschakeld**</span><span class="sxs-lookup"><span data-stu-id="aea2a-117">**Turned off**</span></span>  <br/> |<span data-ttu-id="aea2a-118">De beheerder heeft de invoegtoepassing uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="aea2a-118">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="aea2a-119">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="aea2a-119">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="aea2a-120">Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="aea2a-120">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="aea2a-121">**Verwijderd**</span><span class="sxs-lookup"><span data-stu-id="aea2a-121">**Deleted**</span></span>  <br/> |<span data-ttu-id="aea2a-122">De beheerder heeft de invoegtoepassing verwijderd.</span><span class="sxs-lookup"><span data-stu-id="aea2a-122">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="aea2a-123">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="aea2a-123">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="aea2a-124">U kunt een invoeginvoeging verwijderen als deze door niemand meer wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="aea2a-124">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="aea2a-125">Het uitschakelen van een invoeg mag bijvoorbeeld zinvol zijn als een invoeg mag worden gebruikt in bepaalde tijden van het jaar.</span><span class="sxs-lookup"><span data-stu-id="aea2a-125">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="aea2a-126">Een invoeg toevoegen verwijderen</span><span class="sxs-lookup"><span data-stu-id="aea2a-126">Delete an add-in</span></span>

<span data-ttu-id="aea2a-127">U kunt ook een geïmplementeerde invoeg procenten verwijderen.</span><span class="sxs-lookup"><span data-stu-id="aea2a-127">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="aea2a-128">Ga in het beheercentrum naar de **pagina**  >  **Instellingenservices &-invoegingen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-128">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="aea2a-129">Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="aea2a-129">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="aea2a-130">Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie via **Geïntegreerde**  >  **apps instellingen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-130">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="aea2a-131">Kies invoegingen boven aan de pagina Geïntegreerde **apps.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-131">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="aea2a-132">Selecteer de geïmplementeerde invoegsoper.</span><span class="sxs-lookup"><span data-stu-id="aea2a-132">Select the deployed add-in.</span></span>

3. <span data-ttu-id="aea2a-133">Klik op **Invoeg toevoegen verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-133">Click on **Delete Add-In**.</span></span> <span data-ttu-id="aea2a-134">Verwijder de knop in de rechteronderhoek.</span><span class="sxs-lookup"><span data-stu-id="aea2a-134">Remove the Add-in button on the bottom right corner.</span></span>

4. <span data-ttu-id="aea2a-135">Valideer uw selecties en kies **Invoeg toevoegen verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-135">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="aea2a-136">Invoegtoegang bewerken</span><span class="sxs-lookup"><span data-stu-id="aea2a-136">Edit add-in access</span></span>

<span data-ttu-id="aea2a-137">Na de implementatie kunnen beheerders ook de gebruikerstoegang tot invoegingen beheren.</span><span class="sxs-lookup"><span data-stu-id="aea2a-137">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="aea2a-138">Ga in het beheercentrum naar de **pagina**  >  **Instellingenservices &-invoegingen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-138">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="aea2a-139">Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="aea2a-139">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="aea2a-140">Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie via **Geïntegreerde**  >  **apps instellingen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-140">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="aea2a-141">Kies invoegingen boven aan de pagina Geïntegreerde **apps.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-141">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="aea2a-142">Selecteer de geïmplementeerde invoegsoper.</span><span class="sxs-lookup"><span data-stu-id="aea2a-142">Select the deployed add-in.</span></span>

3. <span data-ttu-id="aea2a-143">Klik op **Bewerken** onder **Wie heeft Access.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-143">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="aea2a-144">Sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="aea2a-144">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="aea2a-145">Downloads van invoeg apps voorkomen door de Office Store voor alle clients uit te schakelen (behalve Outlook)</span><span class="sxs-lookup"><span data-stu-id="aea2a-145">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="aea2a-146">De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="aea2a-146">Outlook add-in installation is managed by a [different process](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx).</span></span>

<span data-ttu-id="aea2a-p106">Als organisatie kunt u het downloaden van nieuwe Office-invoegtoepassingen vanuit Office Store verhinderen. Dit kunt u doen in combinatie met Gecentraliseerde implementatie om ervoor te zorgen dat alleen invoegtoepassingen die door organisaties zijn goedgekeurd voor gebruikers binnen de organisatie worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="aea2a-p106">As an organization you may wish to prevent the download of new Office add-ins from the Office Store. This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="aea2a-149">**Aanschaf van invoeg graag uitschakelen**</span><span class="sxs-lookup"><span data-stu-id="aea2a-149">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="aea2a-150">Ga in het beheercentrum naar de pagina **Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="aea2a-150">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

     > [!NOTE]
    > <span data-ttu-id="aea2a-151">Het beheercentrum wordt bijgewerkt naar de implementatie-ervaring met Geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="aea2a-151">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="aea2a-152">Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie via **Geïntegreerde**  >  **apps instellingen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-152">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="aea2a-153">Kies invoegingen boven aan de pagina Geïntegreerde **apps.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-153">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="aea2a-154">Selecteer Apps en services die eigendom zijn **van gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-154">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="aea2a-155">De optie voor gebruikers toegang geven tot de Office Store, is uit.</span><span class="sxs-lookup"><span data-stu-id="aea2a-155">Clear the option to let users access the Office store.</span></span>

<span data-ttu-id="aea2a-156">Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.</span><span class="sxs-lookup"><span data-stu-id="aea2a-156">This will prevent all users from acquiring the following add-ins from the store.</span></span>
  
- <span data-ttu-id="aea2a-157">Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:</span><span class="sxs-lookup"><span data-stu-id="aea2a-157">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
    
  - <span data-ttu-id="aea2a-158">Windows</span><span class="sxs-lookup"><span data-stu-id="aea2a-158">Windows</span></span>
    
  - <span data-ttu-id="aea2a-159">Mac</span><span class="sxs-lookup"><span data-stu-id="aea2a-159">Mac</span></span>
    
  - <span data-ttu-id="aea2a-160">Office</span><span class="sxs-lookup"><span data-stu-id="aea2a-160">Office</span></span>
    
    
- <span data-ttu-id="aea2a-161">Aanschaf die begint vanuit **AppSource**</span><span class="sxs-lookup"><span data-stu-id="aea2a-161">Acquisitions starting within **AppSource**</span></span>
    
- <span data-ttu-id="aea2a-162">Invoegingen in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="aea2a-162">Add-ins within Microsoft 365</span></span>
    
<span data-ttu-id="aea2a-163">Een gebruiker die toegang probeert te krijgen tot de Store ziet het volgende bericht: Microsoft 365 is geconfigureerd om individuele aanschaf van **Office Store-invoegingen te voorkomen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-163">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="aea2a-164">Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:</span><span class="sxs-lookup"><span data-stu-id="aea2a-164">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="aea2a-165">Windows: 16.0.9001 - Momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="aea2a-165">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="aea2a-166">Mac: 16.10.18011401: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="aea2a-166">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="aea2a-167">iOS: 2.9.18010804: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="aea2a-167">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="aea2a-168">Het web: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="aea2a-168">The web - Currently available.</span></span>
    
<span data-ttu-id="aea2a-169">Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="aea2a-169">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="aea2a-170">Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="aea2a-170">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="aea2a-171">Zie Identiteit, verificatie en autorisatie [in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="aea2a-171">For more information, see [Identity, authentication, and authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).</span></span>  

> [!NOTE]
> <span data-ttu-id="aea2a-172">Als u voorkomt dat gebruikers toegang krijgen tot de Office Store, kunnen ze [ook Geen Office-invoegvoegingen sideloaden voor tests.](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)</span><span class="sxs-lookup"><span data-stu-id="aea2a-172">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="aea2a-173">Meer informatie over de ervaring van eindgebruikers met invoegingen</span><span class="sxs-lookup"><span data-stu-id="aea2a-173">More about the end user experience with add-ins</span></span>

<span data-ttu-id="aea2a-174">Nadat u een invoegtoepassingen hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office-toepassingen (zie [Uw Office-invoegtoepassingen gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="aea2a-174">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="aea2a-175">De invoeg feit wordt weergegeven op alle platforms die door de invoegvoeg toevoeg worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="aea2a-175">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="aea2a-p110">Als de invoegtoepassing opdrachten van de invoegtoepassing ondersteunt, verschijnen de opdrachten in het Office-lint. In het volgende voorbeeld wordt de opdracht **Bronvermelding zoeken** weergegeven voor de invoegtoepassing **Bronvermeldingen**.</span><span class="sxs-lookup"><span data-stu-id="aea2a-p110">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office-lint met bronvermeldingen zoeken](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="aea2a-179">Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="aea2a-179">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="aea2a-180">In Word 2016, Excel 2016 of PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="aea2a-180">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="aea2a-181">Selecteer **\> Mijn invoegvoegingen invoegen.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-181">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="aea2a-182">Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="aea2a-182">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="aea2a-183">Dubbelklik op de invoegtoepassing die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen** ).</span><span class="sxs-lookup"><span data-stu-id="aea2a-183">Double-click the add-in you deployed earlier (in this example, **Citations** ).</span></span> <br/><span data-ttu-id="aea2a-184">![Tabblad Beheerd door beheerder van de pagina Office-invoegvoegingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span><span class="sxs-lookup"><span data-stu-id="aea2a-184">![Admin Managed tab of the Office Add-ins page](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)</span></span>
  
### <a name="in-outlook"></a><span data-ttu-id="aea2a-185">In Outlook</span><span class="sxs-lookup"><span data-stu-id="aea2a-185">In Outlook</span></span>

1. <span data-ttu-id="aea2a-186">Selecteer **Invoegingen** ophalen op het lint **Start.**</span><span class="sxs-lookup"><span data-stu-id="aea2a-186">On the **Home** ribbon, select **Get Add-ins**.</span></span><br/><span data-ttu-id="aea2a-187">![Knop Store in Outlook](../../media/getaddinsicon.png)</span><span class="sxs-lookup"><span data-stu-id="aea2a-187">![Store button in Outlook](../../media/getaddinsicon.png)</span></span>
  
2. <span data-ttu-id="aea2a-188">Selecteer **beheerde beheerder** in de linkernavigatiebalk.</span><span class="sxs-lookup"><span data-stu-id="aea2a-188">Select **Admin-managed** in the left nav.</span></span> 

## <a name="learn-more"></a><span data-ttu-id="aea2a-189">Meer informatie</span><span class="sxs-lookup"><span data-stu-id="aea2a-189">Learn more</span></span>

[<span data-ttu-id="aea2a-190">Invoegtoepassingen implementeren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="aea2a-190">Deploy add-ins in the admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

<span data-ttu-id="aea2a-191">Lees meer over het maken en bouwen van [Office-invoegtoepassingen](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span><span class="sxs-lookup"><span data-stu-id="aea2a-191">Learn more about creating and building [Office Add-ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins).</span></span>
  
<span data-ttu-id="aea2a-192">[Gebruik PowerShell-cmdlets voor Gecentraliseerde implementatie om invoegingen te beheren.](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)</span><span class="sxs-lookup"><span data-stu-id="aea2a-192">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).</span></span>
  
[<span data-ttu-id="aea2a-193">Problemen oplossen: Gebruiker ziet geen invoegingen</span><span class="sxs-lookup"><span data-stu-id="aea2a-193">Troubleshoot: User not seeing add-ins</span></span>](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[<span data-ttu-id="aea2a-194">Minderjarigen en het verkrijgen van invoegingen uit de Microsoft Store</span><span class="sxs-lookup"><span data-stu-id="aea2a-194">Minors and acquiring add-ins from the Microsoft Store</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
