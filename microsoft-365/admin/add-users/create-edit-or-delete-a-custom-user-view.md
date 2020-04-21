---
title: Een aangepaste gebruikersweergave maken, bewerken of verwijderen
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
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Leer filters gebruiken om aangepaste gebruikersweergave in Microsoft 365 te maken, bewerken of verwijderen.
ms.openlocfilehash: 94a9ad7de8bc8e0692d97fda56200cf668b1e5f8
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43617258"
---
# <a name="create-edit-or-delete-a-custom-user-view-in-office-365"></a><span data-ttu-id="3470a-103">Een aangepaste gebruikersweergave maken, bewerken of verwijderen in Office 365</span><span class="sxs-lookup"><span data-stu-id="3470a-103">Create, edit, or delete a custom user view in Office 365</span></span>

<span data-ttu-id="3470a-p101">Als u een hoofdbeheerder of een beheerder voor gebruikerstoegang van Office 365 bent, kunt u aangepaste gebruikersweergaven maken waarmee een specifieke subset van gebruikers kan worden weergegeven. Deze weergaven vormen een aanvulling op de standaardweergaven van Office 365. U kunt aangepaste gebruikersweergaven maken, bewerken of verwijderen en de aangepaste weergaven die u maakt, zijn beschikbaar voor alle beheerders.</span><span class="sxs-lookup"><span data-stu-id="3470a-p101">If you're a global or user management admin of Office 365, you can create custom user views to view a specific subset of users. These views are in addition to the standard set of views that come with Office 365. You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3470a-107">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="3470a-107">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

::: moniker-end
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="3470a-108">Aangepaste gebruikersweergaven in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="3470a-108">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="3470a-109">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Filter** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="3470a-109">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="3470a-110">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="3470a-110">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="3470a-111">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Weergaven** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="3470a-111">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="3470a-112">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="3470a-112">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="3470a-113">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Weergaven** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="3470a-113">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="3470a-114">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="3470a-114">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="3470a-115">Standaard worden standaardgebruikersweergaven weergegeven in de vervolgkeuzelijst **Filters**.</span><span class="sxs-lookup"><span data-stu-id="3470a-115">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="3470a-116">De standaardfilters omvatten **alle gebruikers**, **gelicentieerde gebruikers,** **gastgebruikers**, **Aanmelden toegestaan,** **Aanmelden geblokkeerd,** **gebruikers zonder licentie**, gebruikers **met fouten,** **factureringsbeheerders,** **globale beheerders,** **helpdeskbeheerders,** **servicebeheerders**en **gebruikersbeheerbeheerders**.</span><span class="sxs-lookup"><span data-stu-id="3470a-116">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="3470a-117">U kunt standaardweergaven niet bewerken of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3470a-117">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="3470a-118">Let op het volgende in verband met standaardweergaven:</span><span class="sxs-lookup"><span data-stu-id="3470a-118">A few things to note about standard views:</span></span> 

- <span data-ttu-id="3470a-p106">In bepaalde standaardweergaven wordt een ongesorteerde lijst weergegeven als de lijst meer dan 2.000 gebruikers bevat. Via het zoekvak kunt u vervolgens zoeken naar specifieke gebruikers in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="3470a-p106">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="3470a-121">Als u Microsoft 365 niet bij Microsoft hebt gekocht, worden **factureringsbeheerders** niet weergegeven in de lijst met standaardweergaven.</span><span class="sxs-lookup"><span data-stu-id="3470a-121">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="3470a-122">Zie [Beheerdersrollen toewijzen](assign-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3470a-122">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="3470a-123">Kies de filters voor de aangepaste gebruikersweergave</span><span class="sxs-lookup"><span data-stu-id="3470a-123">Choose the filters for your custom user view</span></span>

<span data-ttu-id="3470a-124">U uw aangepaste weergaven maken en bewerken in het **deelvenster Aangepast filter.**</span><span class="sxs-lookup"><span data-stu-id="3470a-124">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="3470a-125">Als u meerdere filteropties selecteert, bevatten de resultaten de gebruikers die voldoen aan alle geselecteerde criteria.</span><span class="sxs-lookup"><span data-stu-id="3470a-125">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="3470a-126">In het volgende voorbeeld ziet u hoe u een aangepaste weergave met de naam 'Canadese gebruikers' maakt, waarin alle gebruikers worden weergegeven op een specifiek domein en in Canada.</span><span class="sxs-lookup"><span data-stu-id="3470a-126">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="3470a-127">**A - Domein** Als u meerdere domeinen voor uw organisatie hebt, u kiezen uit een vervolgkeuzelijst met domeinen die beschikbaar zijn.</span><span class="sxs-lookup"><span data-stu-id="3470a-127">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="3470a-128">**B - Aanmeldingsstatus** Kies gebruikers die zijn toegestaan of geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="3470a-128">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="3470a-129">**C - Locatie** Kies een locatie uit een vervolgkeuzelijst met landen.</span><span class="sxs-lookup"><span data-stu-id="3470a-129">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="3470a-130">**D - Toegewezen productlicentie** Kies uit een vervolgkeuzelijst met licenties die beschikbaar zijn bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3470a-130">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="3470a-131">Gebruik dit filter als u gebruikers wilt weergeven waaraan de geselecteerde licentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3470a-131">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="3470a-132">Gebruikers kunnen meerdere licenties hebben.</span><span class="sxs-lookup"><span data-stu-id="3470a-132">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="3470a-133">Ook kunt u filteren op andere gegevens uit het gebruikersprofiel die worden gebruikt in uw organisatie, zoals afdeling, plaats, staat of provincie, land of regio, of functie.</span><span class="sxs-lookup"><span data-stu-id="3470a-133">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="3470a-134">**Overige voorwaarden:**</span><span class="sxs-lookup"><span data-stu-id="3470a-134">**Other conditions:**</span></span>
  
- <span data-ttu-id="3470a-135">**Alleen gesynchroniseerde gebruikers** Selecteer dit vakje als u alle gebruikers wilt weergeven die zijn gesynchroniseerd met de lokale Active Directory, ongeacht of ze zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="3470a-135">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="3470a-136">**Gebruikers met fouten** Selecteer dit vakje als u gebruikers wilt weergeven waarvoor mogelijk inrichtingsfouten zijn opgetreden.</span><span class="sxs-lookup"><span data-stu-id="3470a-136">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="3470a-p110">**Gebruikers zonder licentie** Selecteer dit vakje als u alle gebruikers wilt weergeven waaraan geen licentie is toegewezen. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-postvak hebben maar geen licentie. Als u deze gebruikers specifiek wilt opsporen, gebruikt u het filter **Gebruikers zonder licentie met Exchange-postvakken of -archieven**. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-archief hebben maar geen licentie.</span><span class="sxs-lookup"><span data-stu-id="3470a-p110">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="3470a-141">**Gebruikers zonder licentie met Exchange-postvakken of -archieven** Selecteer dit vak om gebruikersaccounts weer te geven die zijn gemaakt in Exchange Online en een Exchange-postvak hebben, maar die geen Microsoft 365-licentie hebben gekregen.</span><span class="sxs-lookup"><span data-stu-id="3470a-141">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="3470a-142">De resultaten van dit filter omvatten gebruikers met een Exchange-archief of waaraan een archief is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3470a-142">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="3470a-143">Het filter **Zonder licentie voor gebruikers met Exchange-postvakken** werkt wanneer:</span><span class="sxs-lookup"><span data-stu-id="3470a-143">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="3470a-144">Het postvak is onlangs geconverteerd van **gedeeld** naar **gebruiker** en heeft geen licentie.</span><span class="sxs-lookup"><span data-stu-id="3470a-144">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="3470a-145">Het postvak is onlangs gemigreerd naar Microsoft 365, maar er is geen licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3470a-145">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="3470a-146">Het postvak is gemaakt met PowerShell en er is geen licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="3470a-146">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="3470a-147">Een nieuwe mailbox die on-premise is gemaakt met een Nieuw-RemoteMailbox-cmdlet is ingericht voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="3470a-147">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="3470a-148">Als u een aangepaste weergave maakt die meer dan 2.000 gebruikers oplevert, is de resulterende lijst ongesorteerd.</span><span class="sxs-lookup"><span data-stu-id="3470a-148">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="3470a-149">Gebruik in dit geval het zoekvak om gebruikers te vinden of uw aangepaste weergave te bewerken om uw zoekopdracht te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="3470a-149">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="3470a-150">Een aangepaste gebruikersweergave maken</span><span class="sxs-lookup"><span data-stu-id="3470a-150">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3470a-151">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3470a-151">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="3470a-152">Selecteer op de pagina **Actieve gebruikers** de optie **Filters** en selecteer **Nieuw filter**.</span><span class="sxs-lookup"><span data-stu-id="3470a-152">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="3470a-153">Voer **op** de pagina Aangepast filter de naam voor uw filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-153">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="3470a-154">Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="3470a-154">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3470a-155">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3470a-155">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="3470a-156">Selecteer **weergaven** op de pagina **Actieve gebruikers** en selecteer Aangepaste **weergave toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-156">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="3470a-157">Voer op de pagina **Aangepaste weergave** de naam voor uw filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-157">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="3470a-158">Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="3470a-158">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="3470a-159">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3470a-159">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="3470a-160">Selecteer **weergaven** op de pagina **Actieve gebruikers** en selecteer Aangepaste **weergave toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-160">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="3470a-161">Voer op de pagina **Aangepaste weergave** de naam voor uw filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-161">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="3470a-162">Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="3470a-162">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="3470a-163">Een aangepaste gebruikersweergave bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="3470a-163">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3470a-164">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3470a-164">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
    
2. <span data-ttu-id="3470a-165">Selecteer op de pagina **Actieve gebruikers** De optie **Filter,** selecteer het filter dat u wilt wijzigen en selecteer **vervolgens Filter bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3470a-165">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3470a-166">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="3470a-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="3470a-167">Bewerk de gegevens op de pagina **Aangepast filter** indien nodig en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3470a-167">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="3470a-168">Of, als u het filter wilt verwijderen, selecteert u onder aan de pagina **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-168">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3470a-169">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3470a-169">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a> page.</span></span>  

2. <span data-ttu-id="3470a-170">Selecteer op de pagina **Actieve gebruikers** **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer **deze weergave bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3470a-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3470a-171">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="3470a-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="3470a-172">Bewerk de gegevens indien nodig op de pagina **Aangepaste weergave** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3470a-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="3470a-173">Als u het filter wilt verwijderen, selecteert u onder aan de pagina **Aangepaste weergave verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3470a-174">Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="3470a-174">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a> page.</span></span> 

2. <span data-ttu-id="3470a-175">Selecteer op de pagina **Actieve gebruikers** **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer **deze weergave bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3470a-175">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="3470a-176">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="3470a-176">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="3470a-177">Bewerk de gegevens indien nodig op de pagina **Aangepaste weergave** en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3470a-177">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="3470a-178">Als u het filter wilt verwijderen, selecteert u onder aan de pagina **Aangepaste weergave verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="3470a-178">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     