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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 4fe7f6ac-be8e-4b57-9e13-24ff889a4b28
description: Meer informatie over het gebruik van filters voor het maken, bewerken of verwijderen van aangepaste gebruikersweergave in Microsoft 365.
ms.openlocfilehash: 598a167b9845f763ddab57d3c5ba36e431aa751c
ms.sourcegitcommit: a3ec91423c352cd5fbf79b46ccd9c169455a03ba
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/09/2020
ms.locfileid: "44664572"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="0078e-103">Een aangepaste gebruikersweergave maken, bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="0078e-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="0078e-104">Als u een globale of gebruikersbeheerbeheerder bent van een Microsoft 365 voor bedrijven-abonnement, u aangepaste gebruikersweergaven maken om een specifieke subset van gebruikers weer te geven.</span><span class="sxs-lookup"><span data-stu-id="0078e-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="0078e-105">Deze weergaven zijn in aanvulling op de standaard set van weergaven.</span><span class="sxs-lookup"><span data-stu-id="0078e-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="0078e-106">U kunt aangepaste gebruikersweergaven maken, bewerken of verwijderen en de aangepaste weergaven die u maakt, zijn beschikbaar voor alle beheerders.</span><span class="sxs-lookup"><span data-stu-id="0078e-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="0078e-107">Aangepaste gebruikersweergaven in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="0078e-107">Custom user views in the admin center</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="0078e-108">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de **lijst Filter** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="0078e-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="0078e-109">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="0078e-109">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="0078e-110">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Weergaven** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="0078e-110">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="0078e-111">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="0078e-111">You can create up to 50 custom views.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="0078e-112">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Weergaven** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="0078e-112">When you create, edit, or delete a custom user view, the changes will be shown in the **Views** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="0078e-113">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="0078e-113">You can create up to 50 custom views.</span></span> 

::: moniker-end

> [!TIP]
>  <span data-ttu-id="0078e-114">Standaard worden standaardgebruikersweergaven weergegeven in de vervolgkeuzelijst **Filters**.</span><span class="sxs-lookup"><span data-stu-id="0078e-114">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="0078e-115">De standaardfilters omvatten **Alle gebruikers**, **Gelicentieerde gebruikers**, **Gastgebruikers**, **Aanmelding toegestaan**, **Aanmelden geblokkeerd,** Gebruikers zonder **licentie**, Gebruikers met fouten , **Facturering admins**, **Globale beheerders,** **Helpdesk admins**, **Service admins**, en **User management admins**. **Users with errors**</span><span class="sxs-lookup"><span data-stu-id="0078e-115">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="0078e-116">U kunt standaardweergaven niet bewerken of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0078e-116">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="0078e-117">Let op het volgende in verband met standaardweergaven:</span><span class="sxs-lookup"><span data-stu-id="0078e-117">A few things to note about standard views:</span></span> 

- <span data-ttu-id="0078e-p106">In bepaalde standaardweergaven wordt een ongesorteerde lijst weergegeven als de lijst meer dan 2.000 gebruikers bevat. Via het zoekvak kunt u vervolgens zoeken naar specifieke gebruikers in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="0078e-p106">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="0078e-120">Als u Microsoft 365 niet van Microsoft hebt gekocht, worden **factureringsbeheerders** niet weergegeven in de lijst met standaardweergaven.</span><span class="sxs-lookup"><span data-stu-id="0078e-120">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="0078e-121">Zie [Beheerdersrollen toewijzen](assign-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="0078e-121">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="0078e-122">Kies de filters voor de aangepaste gebruikersweergave</span><span class="sxs-lookup"><span data-stu-id="0078e-122">Choose the filters for your custom user view</span></span>

<span data-ttu-id="0078e-123">U uw aangepaste weergaven maken en bewerken in het **filtervenster Aangepast.**</span><span class="sxs-lookup"><span data-stu-id="0078e-123">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="0078e-124">Als u meerdere filteropties selecteert, bevatten de resultaten de gebruikers die voldoen aan alle geselecteerde criteria.</span><span class="sxs-lookup"><span data-stu-id="0078e-124">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="0078e-125">In het volgende voorbeeld ziet u hoe u een aangepaste weergave met de naam 'Canadese gebruikers' maakt, waarin alle gebruikers worden weergegeven op een specifiek domein en in Canada.</span><span class="sxs-lookup"><span data-stu-id="0078e-125">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="0078e-126">**A - Domein** Als u meerdere domeinen voor uw organisatie hebt, u kiezen uit een vervolgkeuzelijst met beschikbare domeinen.</span><span class="sxs-lookup"><span data-stu-id="0078e-126">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="0078e-127">**B - Aanmeldingsstatus** Kies gebruikers die zijn toegestaan of geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="0078e-127">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="0078e-128">**C - Locatie** Kies een locatie uit een vervolgkeuzelijst met landen.</span><span class="sxs-lookup"><span data-stu-id="0078e-128">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="0078e-129">**D - Toegewezen productlicentie** Kies uit een vervolgkeuzelijst met licenties die beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="0078e-129">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="0078e-130">Gebruik dit filter als u gebruikers wilt weergeven waaraan de geselecteerde licentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0078e-130">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="0078e-131">Gebruikers kunnen meerdere licenties hebben.</span><span class="sxs-lookup"><span data-stu-id="0078e-131">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="0078e-132">Ook kunt u filteren op andere gegevens uit het gebruikersprofiel die worden gebruikt in uw organisatie, zoals afdeling, plaats, staat of provincie, land of regio, of functie.</span><span class="sxs-lookup"><span data-stu-id="0078e-132">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="0078e-133">**Overige voorwaarden:**</span><span class="sxs-lookup"><span data-stu-id="0078e-133">**Other conditions:**</span></span>
  
- <span data-ttu-id="0078e-134">**Alleen gesynchroniseerde gebruikers** Selecteer dit vakje als u alle gebruikers wilt weergeven die zijn gesynchroniseerd met de lokale Active Directory, ongeacht of ze zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="0078e-134">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="0078e-135">**Gebruikers met fouten** Selecteer dit vakje als u gebruikers wilt weergeven waarvoor mogelijk inrichtingsfouten zijn opgetreden.</span><span class="sxs-lookup"><span data-stu-id="0078e-135">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="0078e-p110">**Gebruikers zonder licentie** Selecteer dit vakje als u alle gebruikers wilt weergeven waaraan geen licentie is toegewezen. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-postvak hebben maar geen licentie. Als u deze gebruikers specifiek wilt opsporen, gebruikt u het filter **Gebruikers zonder licentie met Exchange-postvakken of -archieven**. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-archief hebben maar geen licentie.</span><span class="sxs-lookup"><span data-stu-id="0078e-p110">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="0078e-140">**Gebruikers zonder licentie met Exchange-postvakken of archieven** Selecteer dit vak om gebruikersaccounts weer te geven die zijn gemaakt in Exchange Online en een Exchange-postvak te hebben, maar waaraan geen Microsoft 365-licentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0078e-140">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="0078e-141">De resultaten van dit filter omvatten gebruikers met een Exchange-archief of waaraan een archief is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0078e-141">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="0078e-142">Het **filter Gebruikers zonder licentie met exchange-postvakken** werkt wanneer:</span><span class="sxs-lookup"><span data-stu-id="0078e-142">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="0078e-143">Het postvak is onlangs geconverteerd van **gedeeld** naar **gebruiker** en het heeft geen licentie.</span><span class="sxs-lookup"><span data-stu-id="0078e-143">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="0078e-144">Het postvak is onlangs gemigreerd naar Microsoft 365, maar een licentie is niet toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0078e-144">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="0078e-145">Het postvak is gemaakt met PowerShell en er is geen licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="0078e-145">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="0078e-146">Een nieuw postvak dat on-premise is gemaakt met een cmdlet new-remotemailbox is ingericht voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="0078e-146">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="0078e-147">Als u een aangepaste weergave maakt die meer dan 2.000 gebruikers oplevert, is de resulterende lijst ongesorteerd.</span><span class="sxs-lookup"><span data-stu-id="0078e-147">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="0078e-148">Gebruik in dit geval het zoekvak om gebruikers te zoeken of uw aangepaste weergave te bewerken om uw zoekopdracht te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="0078e-148">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="0078e-149">Een aangepaste gebruikersweergave maken</span><span class="sxs-lookup"><span data-stu-id="0078e-149">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0078e-150">Ga in het beheercentrum naar **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Gebruikers actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0078e-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="0078e-151">Selecteer op de pagina **Actieve gebruikers** de optie **Filters** en selecteer **Nieuw filter**.</span><span class="sxs-lookup"><span data-stu-id="0078e-151">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="0078e-152">Voer op de pagina **Aangepast filter** de naam voor het filter in, kies de voorwaarden voor het aangepaste filter en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0078e-152">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0078e-153">Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="0078e-153">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0078e-154">Ga in het beheercentrum naar **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Gebruikers actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0078e-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="0078e-155">Selecteer **weergaven op** de pagina **Actieve gebruikers** en selecteer Aangepaste **weergave toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0078e-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="0078e-156">Voer op de pagina **Aangepaste weergave** de naam voor het filter in, kies de voorwaarden voor het aangepaste filter en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0078e-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0078e-157">Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="0078e-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="0078e-158">Ga in het beheercentrum naar **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Gebruikers actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0078e-158">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="0078e-159">Selecteer **weergaven op** de pagina **Actieve gebruikers** en selecteer Aangepaste **weergave toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0078e-159">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="0078e-160">Voer op de pagina **Aangepaste weergave** de naam voor het filter in, kies de voorwaarden voor het aangepaste filter en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="0078e-160">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="0078e-161">Uw aangepaste weergave is nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="0078e-161">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="0078e-162">Een aangepaste gebruikersweergave bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="0078e-162">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="0078e-163">Ga in het beheercentrum naar **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Gebruikers actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0078e-163">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="0078e-164">Selecteer op de pagina **Actieve gebruikers** **Filter,** selecteer het filter dat u wilt wijzigen en selecteer **vervolgens Filter bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0078e-164">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0078e-165">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="0078e-165">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0078e-166">Bewerk de informatie op de pagina **Aangepast filter** des nodige informatie en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0078e-166">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0078e-167">Of selecteer onder aan de pagina verwijderen als u het filter **wilt**verwijderen.</span><span class="sxs-lookup"><span data-stu-id="0078e-167">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="0078e-168">Ga in het beheercentrum naar **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Gebruikers actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0078e-168">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="0078e-169">Selecteer op de pagina **Actieve gebruikers** **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer **Deze weergave bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0078e-169">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0078e-170">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="0078e-170">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0078e-171">Bewerk de informatie op de pagina **Aangepaste weergave** indien nodig en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0078e-171">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0078e-172">Als u het filter wilt verwijderen, selecteert u onder aan de pagina **aangepaste weergave verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="0078e-172">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="0078e-173">Ga in het beheercentrum naar **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Gebruikers actieve gebruikers</a>.</span><span class="sxs-lookup"><span data-stu-id="0078e-173">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="0078e-174">Selecteer op de pagina **Actieve gebruikers** **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer **Deze weergave bewerken**.</span><span class="sxs-lookup"><span data-stu-id="0078e-174">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="0078e-175">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="0078e-175">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="0078e-176">Bewerk de informatie op de pagina **Aangepaste weergave** indien nodig en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="0078e-176">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="0078e-177">Als u het filter wilt verwijderen, selecteert u onder aan de pagina **aangepaste weergave verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="0078e-177">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     