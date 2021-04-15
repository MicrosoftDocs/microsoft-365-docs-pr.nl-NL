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
description: Lees hoe u filters gebruikt om aangepaste gebruikersweergave te maken, bewerken of verwijderen in Microsoft 365.
ms.openlocfilehash: 4bd4ea351612c2ae5175cd27fa7a689d671a8b62
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51755570"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="d84f6-103">Een aangepaste gebruikersweergave maken, bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="d84f6-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="d84f6-104">Als u een globale beheerder of beheerder van gebruikersbeheer bent van een Microsoft 365 voor Bedrijven-abonnement, kunt u aangepaste gebruikersweergaven maken om een specifieke subset van gebruikers weer te geven.</span><span class="sxs-lookup"><span data-stu-id="d84f6-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="d84f6-105">Deze weergaven komen bovenop de standaardset weergaven.</span><span class="sxs-lookup"><span data-stu-id="d84f6-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="d84f6-106">U kunt aangepaste gebruikersweergaven maken, bewerken of verwijderen en de aangepaste weergaven die u maakt, zijn beschikbaar voor alle beheerders.</span><span class="sxs-lookup"><span data-stu-id="d84f6-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="d84f6-107">Aangepaste gebruikersweergaven in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="d84f6-107">Custom user views in the admin center</span></span>

<span data-ttu-id="d84f6-108">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Filter** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="d84f6-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="d84f6-109">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="d84f6-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="d84f6-110">Standaard worden standaardgebruikersweergaven weergegeven in de vervolgkeuzelijst **Filters**.</span><span class="sxs-lookup"><span data-stu-id="d84f6-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="d84f6-111">De **standaardfilters** zijn Alle gebruikers **,** Gelicentieerde gebruikers **,** **Gastgebruikers** **,** Aanmelding toegestaan **,** Aanmelding geblokkeerd , Gebruikers zonder licentie **,** Gebruikers met fouten , **Factureringsbeheerders**, **Globale beheerders**, **Helpdeskbeheerders**, **Servicebeheerders** en Beheerders van **gebruikersbeheer**.</span><span class="sxs-lookup"><span data-stu-id="d84f6-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="d84f6-112">U kunt standaardweergaven niet bewerken of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="d84f6-113">Let op het volgende in verband met standaardweergaven:</span><span class="sxs-lookup"><span data-stu-id="d84f6-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="d84f6-p104">In bepaalde standaardweergaven wordt een ongesorteerde lijst weergegeven als de lijst meer dan 2.000 gebruikers bevat. Via het zoekvak kunt u vervolgens zoeken naar specifieke gebruikers in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="d84f6-p104">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="d84f6-116">Als u Microsoft 365 niet bij Microsoft hebt gekocht, worden **factureringsbeheerders** niet weergegeven in de lijst met standaardweergaven.</span><span class="sxs-lookup"><span data-stu-id="d84f6-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="d84f6-117">Zie [Beheerdersrollen toewijzen](assign-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d84f6-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="d84f6-118">Kies de filters voor de aangepaste gebruikersweergave</span><span class="sxs-lookup"><span data-stu-id="d84f6-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="d84f6-119">U kunt uw aangepaste weergaven maken en bewerken in **het deelvenster Aangepast filter.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="d84f6-120">Als u meerdere filteropties selecteert, bevatten de resultaten de gebruikers die voldoen aan alle geselecteerde criteria.</span><span class="sxs-lookup"><span data-stu-id="d84f6-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="d84f6-121">In het volgende voorbeeld ziet u hoe u een aangepaste weergave met de naam 'Canadese gebruikers' maakt, waarin alle gebruikers worden weergegeven op een specifiek domein en in Canada.</span><span class="sxs-lookup"><span data-stu-id="d84f6-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="d84f6-122">**A - Domein** Als u meerdere domeinen voor uw organisatie hebt, kunt u kiezen uit een vervolgkeuzelijst met beschikbare domeinen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="d84f6-123">**B - Aanmeldingsstatus** Kies gebruikers die zijn toegestaan of geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="d84f6-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="d84f6-124">**C - Locatie** Kies een locatie in een vervolgkeuzelijst met landen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="d84f6-125">**D - Productlicentie toegewezen** Kies uit een vervolgkeuzelijst met licenties die beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d84f6-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="d84f6-126">Gebruik dit filter als u gebruikers wilt weergeven waaraan de geselecteerde licentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="d84f6-127">Gebruikers kunnen meerdere licenties hebben.</span><span class="sxs-lookup"><span data-stu-id="d84f6-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="d84f6-128">Ook kunt u filteren op andere gegevens uit het gebruikersprofiel die worden gebruikt in uw organisatie, zoals afdeling, plaats, staat of provincie, land of regio, of functie.</span><span class="sxs-lookup"><span data-stu-id="d84f6-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="d84f6-129">**Overige voorwaarden:**</span><span class="sxs-lookup"><span data-stu-id="d84f6-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="d84f6-130">**Alleen gesynchroniseerde gebruikers** Selecteer dit vakje als u alle gebruikers wilt weergeven die zijn gesynchroniseerd met de lokale Active Directory, ongeacht of ze zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="d84f6-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="d84f6-131">**Gebruikers met fouten** Selecteer dit vakje als u gebruikers wilt weergeven waarvoor mogelijk inrichtingsfouten zijn opgetreden.</span><span class="sxs-lookup"><span data-stu-id="d84f6-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="d84f6-p108">**Gebruikers zonder licentie** Selecteer dit vakje als u alle gebruikers wilt weergeven waaraan geen licentie is toegewezen. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-postvak hebben maar geen licentie. Als u deze gebruikers specifiek wilt opsporen, gebruikt u het filter **Gebruikers zonder licentie met Exchange-postvakken of -archieven**. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-archief hebben maar geen licentie.</span><span class="sxs-lookup"><span data-stu-id="d84f6-p108">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="d84f6-136">**Gebruikers zonder vergunning met Exchange-postvakken of archieven** Schakel dit vakje in om gebruikersaccounts weer te geven die zijn gemaakt in Exchange Online en een Exchange-postvak hebben, maar die geen Microsoft 365-licentie hebben gekregen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="d84f6-137">De resultaten van dit filter omvatten gebruikers met een Exchange-archief of waaraan een archief is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="d84f6-138">Het **filter Niet-gelicenseerde gebruikers met** Exchange-postvakken werkt als:</span><span class="sxs-lookup"><span data-stu-id="d84f6-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="d84f6-139">Het postvak is onlangs geconverteerd van **gedeeld** naar **gebruiker** en heeft geen licentie.</span><span class="sxs-lookup"><span data-stu-id="d84f6-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="d84f6-140">Het postvak is onlangs gemigreerd naar Microsoft 365, maar er is geen licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="d84f6-141">Het postvak is gemaakt met PowerShell en er is geen licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="d84f6-142">Een nieuw postvak dat on-premises is gemaakt met een New-RemoteMailbox cmdlet is ingericht voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d84f6-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="d84f6-143">Als u een aangepaste weergave maakt die meer dan 2.000 gebruikers oplevert, is de resulterende lijst ongesorteerd.</span><span class="sxs-lookup"><span data-stu-id="d84f6-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="d84f6-144">Gebruik in dit geval het zoekvak om gebruikers te zoeken of uw aangepaste weergave te bewerken om uw zoekopdracht te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="d84f6-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="d84f6-145">Een aangepaste gebruikersweergave maken</span><span class="sxs-lookup"><span data-stu-id="d84f6-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d84f6-146">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="d84f6-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="d84f6-147">Selecteer op **de pagina** Actieve gebruikers de **optie Filters** en selecteer **Nieuw filter.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-147">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="d84f6-148">Voer op **de pagina** Aangepast filter de naam voor het filter in, kies de voorwaarden voor het aangepaste filter en selecteer **vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-148">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="d84f6-149">Uw aangepaste weergave wordt nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="d84f6-149">Your custom view is now included in the drop-down list of filters.</span></span>
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d84f6-150">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="d84f6-150">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="d84f6-151">Selecteer op **de pagina Actieve** gebruikers **weergaven** en selecteer **Aangepaste weergave toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-151">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="d84f6-152">Voer op **de pagina** Aangepaste weergave de naam voor het filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-152">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="d84f6-153">Uw aangepaste weergave wordt nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="d84f6-153">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end


::: moniker range="o365-21vianet"

1. <span data-ttu-id="d84f6-154">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="d84f6-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="d84f6-155">Selecteer op **de pagina Actieve** gebruikers **weergaven** en selecteer **Aangepaste weergave toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-155">On the **Active users** page, select **Views** and select **Add custom view**.</span></span>
  
3. <span data-ttu-id="d84f6-156">Voer op **de pagina** Aangepaste weergave de naam voor het filter in, kies de voorwaarden voor uw aangepaste filter en selecteer **vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-156">On the **Custom view** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="d84f6-157">Uw aangepaste weergave wordt nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="d84f6-157">Your custom view is now included in the drop-down list of filters.</span></span>

::: moniker-end
    

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="d84f6-158">Een aangepaste gebruikersweergave bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="d84f6-158">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d84f6-159">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="d84f6-159">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
    
2. <span data-ttu-id="d84f6-160">Selecteer op **de pagina** Actieve gebruikers de optie **Filter,** selecteer het filter dat u wilt wijzigen en selecteer **vervolgens Filter bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-160">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d84f6-161">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="d84f6-161">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="d84f6-162">Bewerk **de gegevens op** de pagina Aangepast filter zo nodig en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-162">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="d84f6-163">Of als u het filter wilt verwijderen, selecteert u onder aan de pagina **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-163">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 
    
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d84f6-164">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="d84f6-164">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span>  

2. <span data-ttu-id="d84f6-165">Selecteer op **de pagina** Actieve gebruikers **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer vervolgens Deze **weergave bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-165">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d84f6-166">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="d84f6-166">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="d84f6-167">Bewerk **de gegevens zo** nodig op de pagina Aangepaste weergave en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-167">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="d84f6-168">Of als u het filter wilt verwijderen, selecteert u onder aan de pagina **Aangepaste weergave verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-168">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d84f6-169">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="d84f6-169">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

2. <span data-ttu-id="d84f6-170">Selecteer op **de pagina** Actieve gebruikers **weergaven,** selecteer het filter dat u wilt wijzigen en selecteer vervolgens Deze **weergave bewerken.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-170">On the **Active users** page, select **Views**, select the filter you want to change, and then select **Edit this view**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="d84f6-171">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="d84f6-171">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="d84f6-172">Bewerk **de gegevens zo** nodig op de pagina Aangepaste weergave en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-172">On the **Custom view** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="d84f6-173">Of als u het filter wilt verwijderen, selecteert u onder aan de pagina **Aangepaste weergave verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="d84f6-173">Or, to delete the filter, at the bottom of the page select **Delete custom view**.</span></span> 

::: moniker-end


     