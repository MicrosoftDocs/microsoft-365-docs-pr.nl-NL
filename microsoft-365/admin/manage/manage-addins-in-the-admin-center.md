---
title: Invoegtoepassingen beheren in het beheercentrum
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: Meer informatie over het gebruik van gecentraliseerde invoegvoegingen voor het implementeren van invoegingen voor gebruikers en groepen in uw organisatie.
ms.openlocfilehash: d678755b28daea1578ce2a5d2e387492cf32d368
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636056"
---
# <a name="manage-add-ins-in-the-admin-center"></a><span data-ttu-id="a20c5-103">Invoegtoepassingen beheren in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="a20c5-103">Manage add-ins in the admin center</span></span>

<span data-ttu-id="a20c5-104">Office invoegvoegingen kunt u uw documenten aan uw persoonlijke voorkeur personaliseren en de manier waarop u toegang hebt tot informatie op internet stroomlijnen (zie Uw Office [gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="a20c5-104">Office add-ins help you personalize your documents and streamline the way you access information on the web (see [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> 

<span data-ttu-id="a20c5-105">Nadat een beheerder invoegvoegingen voor gebruikers in een organisatie heeft geïmplementeerd, kan de beheerder invoegingen in- of uitschakelen, bewerken, verwijderen en beheren.</span><span class="sxs-lookup"><span data-stu-id="a20c5-105">After an admin deploys add-ins for users in an organization, the admin can turn add-ins off or on, edit, delete, and manage access to the add-ins.</span></span>

<span data-ttu-id="a20c5-106">Zie Invoegvoegingen implementeren in het beheercentrum voor meer informatie over het installeren van invoegvoegingen vanuit het [beheercentrum.](./manage-deployment-of-add-ins.md)</span><span class="sxs-lookup"><span data-stu-id="a20c5-106">For more information about installing add-ins from the admin center, see [Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md).</span></span>
  
## <a name="add-in-states"></a><span data-ttu-id="a20c5-107">Statussen van invoegtoepassingen</span><span class="sxs-lookup"><span data-stu-id="a20c5-107">Add-in states</span></span>

<span data-ttu-id="a20c5-108">Een invoegvoegvoeging kan de status **Aan** of **Uit** hebben.</span><span class="sxs-lookup"><span data-stu-id="a20c5-108">An add-in can be in either the **On** or **Off** state.</span></span>
  
| <span data-ttu-id="a20c5-109">Status</span><span class="sxs-lookup"><span data-stu-id="a20c5-109">State</span></span> | <span data-ttu-id="a20c5-110">Hoe de status optreedt</span><span class="sxs-lookup"><span data-stu-id="a20c5-110">How the state occurs</span></span> | <span data-ttu-id="a20c5-111">Gevolg</span><span class="sxs-lookup"><span data-stu-id="a20c5-111">Impact</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="a20c5-112">**Actief**</span><span class="sxs-lookup"><span data-stu-id="a20c5-112">**Active**</span></span>  <br/> |<span data-ttu-id="a20c5-113">De beheerder heeft de invoegtoepassing geüpload en toegewezen aan gebruikers of groepen.</span><span class="sxs-lookup"><span data-stu-id="a20c5-113">Admin uploaded the add-in and assigned it to users or groups.</span></span>  <br/> |<span data-ttu-id="a20c5-114">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, zien de invoegtoepassing in de desbetreffende clients.</span><span class="sxs-lookup"><span data-stu-id="a20c5-114">Users and groups assigned to the add-in see it in the relevant clients.</span></span>  <br/> |
|<span data-ttu-id="a20c5-115">**Uitgeschakeld**</span><span class="sxs-lookup"><span data-stu-id="a20c5-115">**Turned off**</span></span>  <br/> |<span data-ttu-id="a20c5-116">De beheerder heeft de invoegtoepassing uitgeschakeld.</span><span class="sxs-lookup"><span data-stu-id="a20c5-116">Admin turned off the add-in.</span></span>  <br/> |<span data-ttu-id="a20c5-117">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a20c5-117">Users and groups assigned to the add-in no longer have access to it.</span></span>  <br/> <span data-ttu-id="a20c5-118">Als de status van de invoegtoepassing wordt gewijzigd in Actief, hebben de gebruikers en groepen opnieuw toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a20c5-118">If the add-in state is changed to Active, the users and groups will have access to it again.</span></span>  <br/> |
|<span data-ttu-id="a20c5-119">**Verwijderd**</span><span class="sxs-lookup"><span data-stu-id="a20c5-119">**Deleted**</span></span>  <br/> |<span data-ttu-id="a20c5-120">De beheerder heeft de invoegtoepassing verwijderd.</span><span class="sxs-lookup"><span data-stu-id="a20c5-120">Admin deleted the add-in.</span></span>  <br/> |<span data-ttu-id="a20c5-121">Gebruikers en groepen die zijn toegewezen aan de invoegtoepassing, hebben niet langer toegang tot de invoegtoepassing.</span><span class="sxs-lookup"><span data-stu-id="a20c5-121">Users and groups assigned the add-in no longer have access to it.</span></span>  <br/> |
   
<span data-ttu-id="a20c5-122">U kunt een invoegvoeginvoeging verwijderen als deze niet meer wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a20c5-122">Consider deleting an add-in if no one is using it anymore.</span></span> <span data-ttu-id="a20c5-123">Het uitschakelen van een invoeging kan bijvoorbeeld zinvol zijn als een invoeging alleen wordt gebruikt in bepaalde tijden van het jaar.</span><span class="sxs-lookup"><span data-stu-id="a20c5-123">For example, turning off an add-in might make sense if an add-in is used only during specific times of the year.</span></span>

## <a name="delete-an-add-in"></a><span data-ttu-id="a20c5-124">Een invoeging verwijderen</span><span class="sxs-lookup"><span data-stu-id="a20c5-124">Delete an add-in</span></span>

<span data-ttu-id="a20c5-125">U kunt ook een invoegvoeging verwijderen die is geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="a20c5-125">You can also delete an add-in that was deployed.</span></span>

1. <span data-ttu-id="a20c5-126">Ga in het beheercentrum naar de **pagina Instellingen** Services  >  **& invoegvoegingen.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-126">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a20c5-127">Het beheercentrum wordt bijgewerkt naar implementatieervaring met geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="a20c5-127">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a20c5-128">Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar Instellingen geïntegreerde apps te  >  **gaan.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-128">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a20c5-129">Kies invoegingen boven aan de pagina Geïntegreerde **apps.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-129">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="a20c5-130">Selecteer de geïmplementeerde invoegvoegvoeging.</span><span class="sxs-lookup"><span data-stu-id="a20c5-130">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a20c5-131">Klik op **Invoeg toevoegen verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-131">Click on **Delete Add-In**.</span></span> <span data-ttu-id="a20c5-132">Verwijder de knop Invoeg toevoegen in de rechteronderhoek.</span><span class="sxs-lookup"><span data-stu-id="a20c5-132">Remove the Add-in button on the bottom-right corner.</span></span>

4. <span data-ttu-id="a20c5-133">Valideer uw selecties en kies **Invoeging verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-133">Validate your selections, and choose **Remove add-in**.</span></span>

## <a name="edit-add-in-access"></a><span data-ttu-id="a20c5-134">Invoegtoegang bewerken</span><span class="sxs-lookup"><span data-stu-id="a20c5-134">Edit add-in access</span></span>

<span data-ttu-id="a20c5-135">Na de implementatie kunnen beheerders ook gebruikerstoegang tot invoegvoegingen beheren.</span><span class="sxs-lookup"><span data-stu-id="a20c5-135">Post deployment, admins can also manage user access to add-ins.</span></span>

1. <span data-ttu-id="a20c5-136">Ga in het beheercentrum naar de **pagina Instellingen** Services  >  **& invoegvoegingen.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-136">In the admin center, go to the **Settings** > **Services & add-ins** page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a20c5-137">Het beheercentrum wordt bijgewerkt naar implementatieervaring met geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="a20c5-137">The admin center is getting updated to deployment experience with Integrated Apps .</span></span> <span data-ttu-id="a20c5-138">Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar Instellingen geïntegreerde apps te  >  **gaan.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-138">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a20c5-139">Kies invoegingen boven aan de pagina Geïntegreerde **apps.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-139">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>

2. <span data-ttu-id="a20c5-140">Selecteer de geïmplementeerde invoegvoegvoeging.</span><span class="sxs-lookup"><span data-stu-id="a20c5-140">Select the deployed add-in.</span></span>

3. <span data-ttu-id="a20c5-141">Klik op **Bewerken onder** Wie **access heeft.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-141">Click on **Edit** under **Who has Access**.</span></span>

4. <span data-ttu-id="a20c5-142">Sla de wijzigingen op.</span><span class="sxs-lookup"><span data-stu-id="a20c5-142">Save the changes.</span></span>

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a><span data-ttu-id="a20c5-143">Invoegdownloads voorkomen door de Office store uit te schakelen voor alle clients (behalve Outlook)</span><span class="sxs-lookup"><span data-stu-id="a20c5-143">Prevent add-in downloads by turning off the Office Store across all clients (Except Outlook)</span></span>

> [!NOTE]
> <span data-ttu-id="a20c5-144">De installatie van Outlook-invoegtoepassingen wordt beheerd via een [ander proces](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span><span class="sxs-lookup"><span data-stu-id="a20c5-144">Outlook add-in installation is managed by a [different process](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins).</span></span>

<span data-ttu-id="a20c5-p105">Als organisatie kunt u het downloaden van nieuwe Office-invoegtoepassingen vanuit Office Store verhinderen. Dit kunt u doen in combinatie met Gecentraliseerde implementatie om ervoor te zorgen dat alleen invoegtoepassingen die door organisaties zijn goedgekeurd voor gebruikers binnen de organisatie worden geïmplementeerd.</span><span class="sxs-lookup"><span data-stu-id="a20c5-p105">As an organization you may wish to prevent the download of new Office add-ins from the Office Store. This can be used in conjunction with Centralized Deployment to ensure that only organization-approved add-ins are deployed to users within your organization.</span></span>
  
<span data-ttu-id="a20c5-147">**Invoegvoeging uitschakelen**</span><span class="sxs-lookup"><span data-stu-id="a20c5-147">**To turn off add-in acquisition**</span></span>
  
1. <span data-ttu-id="a20c5-148">Ga in het beheercentrum naar de pagina **Instellingen** \> [Services &amp; invoegtoepassingen](https://go.microsoft.com/fwlink/p/?linkid=2053743).</span><span class="sxs-lookup"><span data-stu-id="a20c5-148">In the admin center, go to the **Settings** \> [Services &amp; add-ins](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a20c5-149">Het beheercentrum wordt bijgewerkt naar implementatie-ervaring met geïntegreerde apps.</span><span class="sxs-lookup"><span data-stu-id="a20c5-149">The admin center is getting updated to deployment experience with Integrated Apps.</span></span> <span data-ttu-id="a20c5-150">Als u de bovenstaande stappen niet ziet, gaat u naar de sectie Gecentraliseerde implementatie door naar Instellingen geïntegreerde apps te  >  **gaan.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-150">If you don't see the above steps, go to Centralized Deployment section by going to **Settings** > **Integrated apps**.</span></span> <span data-ttu-id="a20c5-151">Kies invoegingen boven aan de pagina Geïntegreerde **apps.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-151">On the top of the **Integrated apps** page, choose **Add-ins**.</span></span>
    
3. <span data-ttu-id="a20c5-152">Selecteer **Apps en services die eigendom zijn van gebruikers.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-152">Select **User owned apps and services**.</span></span>
    
4. <span data-ttu-id="a20c5-153">De optie om gebruikers toegang te geven tot de Office store.</span><span class="sxs-lookup"><span data-stu-id="a20c5-153">Clear the option to let users access the Office store.</span></span>

    <span data-ttu-id="a20c5-154">Hierdoor wordt voorkomen dat alle gebruikers de volgende invoegtoepassingen via de store kunnen aanschaffen.</span><span class="sxs-lookup"><span data-stu-id="a20c5-154">This will prevent all users from acquiring the following add-ins from the store.</span></span>
      
    - <span data-ttu-id="a20c5-155">Invoegtoepassingen voor Word, Excel en PowerPoint 2016 van:</span><span class="sxs-lookup"><span data-stu-id="a20c5-155">Add-ins for Word, Excel, and PowerPoint 2016 from:</span></span>
        
      - <span data-ttu-id="a20c5-156">Windows</span><span class="sxs-lookup"><span data-stu-id="a20c5-156">Windows</span></span>
      - <span data-ttu-id="a20c5-157">Mac</span><span class="sxs-lookup"><span data-stu-id="a20c5-157">Mac</span></span>
      - <span data-ttu-id="a20c5-158">Office</span><span class="sxs-lookup"><span data-stu-id="a20c5-158">Office</span></span>
        
        
    - <span data-ttu-id="a20c5-159">Aanschaf die begint vanuit **AppSource**</span><span class="sxs-lookup"><span data-stu-id="a20c5-159">Acquisitions starting within **AppSource**</span></span>
        
    - <span data-ttu-id="a20c5-160">Invoegvoegingen binnen Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a20c5-160">Add-ins within Microsoft 365</span></span>
        
    <span data-ttu-id="a20c5-161">Een gebruiker die toegang probeert te krijgen tot de store, ziet het volgende bericht: Sorry, Microsoft 365 is zo geconfigureerd dat individuele overname van Office **Store-invoegvoegingen wordt voorkomen.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-161">A user who tries to access the store will see the following message: **Sorry, Microsoft 365 has been configured to prevent individual acquisition of Office Store add-ins.**</span></span>
  
<span data-ttu-id="a20c5-162">Ondersteuning voor het uitschakelen van Office Store is beschikbaar in de volgende versies:</span><span class="sxs-lookup"><span data-stu-id="a20c5-162">Support for turning off the Office Store is available in the following versions:</span></span>
  
- <span data-ttu-id="a20c5-163">Windows: 16.0.9001 - Momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a20c5-163">Windows: 16.0.9001 - Currently available.</span></span>
    
- <span data-ttu-id="a20c5-164">Mac: 16.10.18011401: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a20c5-164">Mac: 16.10.18011401 - Currently available.</span></span>
    
- <span data-ttu-id="a20c5-165">iOS: 2.9.18010804: momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a20c5-165">iOS: 2.9.18010804 - Currently available.</span></span>
    
- <span data-ttu-id="a20c5-166">Het web- Momenteel beschikbaar.</span><span class="sxs-lookup"><span data-stu-id="a20c5-166">The web - Currently available.</span></span>
    
<span data-ttu-id="a20c5-167">Hiermee wordt niet voorkomen dat een beheerder Gecentraliseerde implementatie gebruikt om invoegtoepassingen vanuit Office Store toe te wijzen.</span><span class="sxs-lookup"><span data-stu-id="a20c5-167">This does not prevent an administrator from using Centralized Deployment to assign an add-in from the Office Store.</span></span>
  
<span data-ttu-id="a20c5-168">Om te voorkomen dat een gebruiker zich aanmeldt met een Microsoft-account, kunt u ervoor zorgen dat er alleen kan worden aangemeld met het account van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="a20c5-168">To prevent a user from signing in with a Microsoft account, you can restrict logon to use only the organizational account.</span></span> <span data-ttu-id="a20c5-169">Zie Identiteit, verificatie en autorisatie [in Office 2016 voor meer informatie.](/DeployOffice/security/identity-authentication-and-authorization-in-office)</span><span class="sxs-lookup"><span data-stu-id="a20c5-169">For more information, see [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).</span></span>  

> [!NOTE] 
> <span data-ttu-id="a20c5-170">Als u voorkomt dat gebruikers toegang krijgen tot de Office Store, kunnen ze ook geen [Office-invoegingen](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)voor het testen van een netwerk delen.</span><span class="sxs-lookup"><span data-stu-id="a20c5-170">Preventing users from accessing the office store will also prevent them from [Sideloading Office Add-ins for testing from a network share](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins).</span></span>

## <a name="more-about-the-end-user-experience-with-add-ins"></a><span data-ttu-id="a20c5-171">Meer informatie over de ervaring van eindgebruikers met invoegvoegingen</span><span class="sxs-lookup"><span data-stu-id="a20c5-171">More about the end-user experience with add-ins</span></span>

<span data-ttu-id="a20c5-172">Nadat u een invoegtoepassingen hebt geïmplementeerd, kunnen uw eindgebruikers deze gaan gebruiken in hun Office toepassingen (zie Uw invoegtoepassingen [Office gebruiken).](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)</span><span class="sxs-lookup"><span data-stu-id="a20c5-172">After you deploy an add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)).</span></span> <span data-ttu-id="a20c5-173">De invoeging wordt weergegeven op alle platforms die door de invoeging worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="a20c5-173">The add-in appears on all platforms that the add-in supports.</span></span>
  
<span data-ttu-id="a20c5-p109">Als de invoegtoepassing opdrachten van de invoegtoepassing ondersteunt, verschijnen de opdrachten in het Office-lint. In het volgende voorbeeld wordt de opdracht **Bronvermelding zoeken** weergegeven voor de invoegtoepassing **Bronvermeldingen**.</span><span class="sxs-lookup"><span data-stu-id="a20c5-p109">If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in.</span></span> 

![Office lint met bronvermeldingen zoeken](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
<span data-ttu-id="a20c5-177">Als de geïmplementeerde invoegtoepassing geen ondersteuning biedt voor opdrachten van de invoegtoepassing of als u alle geïmplementeerde invoegtoepassingen wilt weergeven, kunt u ze weergeven via **Mijn invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="a20c5-177">If the deployed add-in doesn't support add-in commands or if you want to view all deployed add-ins, you can view them via **My Add-ins**.</span></span> 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a><span data-ttu-id="a20c5-178">In Word 2016, Excel 2016 of PowerPoint 2016</span><span class="sxs-lookup"><span data-stu-id="a20c5-178">In Word 2016, Excel 2016, or PowerPoint 2016</span></span>

1. <span data-ttu-id="a20c5-179">Selecteer **Mijn \> invoegingen invoegen.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-179">Select **Insert \> My Add-ins**.</span></span> 
    
2. <span data-ttu-id="a20c5-180">Selecteer het tabblad **Beheerd door beheerder** in het venster Office-invoegtoepassingen.</span><span class="sxs-lookup"><span data-stu-id="a20c5-180">Select the **Admin Managed** tab in the Office Add-ins window.</span></span> 
    
3. <span data-ttu-id="a20c5-181">Dubbelklik op de invoeg die u eerder hebt geïmplementeerd (in dit voorbeeld **Bronvermeldingen).**</span><span class="sxs-lookup"><span data-stu-id="a20c5-181">Double-click the add-in you deployed earlier (in this example, **Citations**).</span></span>

    ![Tabblad Beheerd door beheerder van Office pagina Invoegvoegingen](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a><span data-ttu-id="a20c5-183">In Outlook</span><span class="sxs-lookup"><span data-stu-id="a20c5-183">In Outlook</span></span>

1. <span data-ttu-id="a20c5-184">Selecteer op **het lint** Start de **optie Invoegvoegingen ophalen.**</span><span class="sxs-lookup"><span data-stu-id="a20c5-184">On the **Home** ribbon, select **Get Add-ins**.</span></span>

    ![Knop Store in Outlook](../../media/getaddinsicon.png)
  
2. <span data-ttu-id="a20c5-186">Selecteer **Beheer beheerd** in het linkernavigatienavigatienavigatiecentrum.</span><span class="sxs-lookup"><span data-stu-id="a20c5-186">Select **Admin-managed** in the left nav.</span></span> 

## <a name="related-content"></a><span data-ttu-id="a20c5-187">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="a20c5-187">Related content</span></span>

<span data-ttu-id="a20c5-188">[Invoegvoegingen implementeren in het beheercentrum](./manage-deployment-of-add-ins.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a20c5-188">[Deploy add-ins in the admin center](./manage-deployment-of-add-ins.md) (article)</span></span>\
<span data-ttu-id="a20c5-189">Meer informatie over het maken en Office [invoegvoegingen](/office/dev/add-ins/overview/office-add-ins) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a20c5-189">Learn more about creating and building [Office Add-ins](/office/dev/add-ins/overview/office-add-ins) (article)</span></span>\
<span data-ttu-id="a20c5-190">[Gecentraliseerde PowerShell-cmdlets voor](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) implementatie gebruiken om invoegvoegingen te beheren (artikel)</span><span class="sxs-lookup"><span data-stu-id="a20c5-190">[Use Centralized Deployment PowerShell cmdlets to manage add-ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (article)</span></span>\
<span data-ttu-id="a20c5-191">[Probleem oplossen: Gebruiker ziet invoegvoegingen niet](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a20c5-191">[Troubleshoot: User not seeing add-ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (article)</span></span>\
<span data-ttu-id="a20c5-192">[Minderjarigen en het verkrijgen van invoegvoegingen uit de Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="a20c5-192">[Minors and acquiring add-ins from the Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (article)</span></span>