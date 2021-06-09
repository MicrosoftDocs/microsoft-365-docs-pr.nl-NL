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
description: Lees hoe u filters kunt gebruiken om aangepaste gebruikersweergave te maken, te bewerken of te verwijderen in Microsoft 365.
ms.openlocfilehash: b4177a561d13d76f6d5a0a1077fe8037d469ee48
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683221"
---
# <a name="create-edit-or-delete-a-custom-user-view"></a><span data-ttu-id="b4761-103">Een aangepaste gebruikersweergave maken, bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="b4761-103">Create, edit, or delete a custom user view</span></span>

<span data-ttu-id="b4761-104">Als u een globale beheerder of beheerder van gebruikersbeheer bent van een Microsoft 365 voor bedrijven-abonnement, kunt u aangepaste gebruikersweergaven maken om een specifieke subset van gebruikers weer te geven.</span><span class="sxs-lookup"><span data-stu-id="b4761-104">If you're a global or user management admin of a Microsoft 365 for business subscription,  you can create custom user views to view a specific subset of users.</span></span> <span data-ttu-id="b4761-105">Deze weergaven komen bovenop de standaardset weergaven.</span><span class="sxs-lookup"><span data-stu-id="b4761-105">These views are in addition to the standard set of views.</span></span> <span data-ttu-id="b4761-106">U kunt aangepaste gebruikersweergaven maken, bewerken of verwijderen en de aangepaste weergaven die u maakt, zijn beschikbaar voor alle beheerders.</span><span class="sxs-lookup"><span data-stu-id="b4761-106">You can create, edit, or delete custom user views, and the custom views you create are available to all admins.</span></span>
  
## <a name="custom-user-views-in-the-admin-center"></a><span data-ttu-id="b4761-107">Aangepaste gebruikersweergaven in het beheercentrum</span><span class="sxs-lookup"><span data-stu-id="b4761-107">Custom user views in the admin center</span></span>

<span data-ttu-id="b4761-108">Wanneer u een aangepaste gebruikersweergave maakt, bewerkt of verwijdert, worden de wijzigingen weergegeven in de lijst **Filter** die alle beheerders in uw bedrijf zien wanneer ze naar de pagina **Gebruikers** gaan.</span><span class="sxs-lookup"><span data-stu-id="b4761-108">When you create, edit, or delete a custom user view, the changes will be shown in the **Filter** list that all admins in your company see when they go to the **Users** page.</span></span> <span data-ttu-id="b4761-109">U kunt maximaal vijftig aangepaste weergaven maken.</span><span class="sxs-lookup"><span data-stu-id="b4761-109">You can create up to 50 custom views.</span></span> 

> [!TIP]
>  <span data-ttu-id="b4761-110">Standaard worden standaardgebruikersweergaven weergegeven in de vervolgkeuzelijst **Filters**.</span><span class="sxs-lookup"><span data-stu-id="b4761-110">Standard user views are displayed by default in the **Filters** drop-down list.</span></span> <span data-ttu-id="b4761-111">De **standaardfilters** zijn Alle gebruikers **,** Gelicentieerde gebruikers **,** **Gastgebruikers** **,** Aanmelding toegestaan **,** Aanmelding geblokkeerd , Gebruikers zonder licentie **,** Gebruikers met fouten , **Factureringsbeheerders**, **Globale beheerders**, **Helpdeskbeheerders**, **Servicebeheerders** en Beheerders van **gebruikersbeheer**.</span><span class="sxs-lookup"><span data-stu-id="b4761-111">The standard filters include **All users**, **Licensed users**, **Guest users**,  **Sign-in allowed**, **Sign-in blocked**, **Unlicensed users**, **Users with errors**, **Billing admins**, **Global admins**, **Helpdesk admins**, **Service admins**, and **User management admins**.</span></span> <span data-ttu-id="b4761-112">U kunt standaardweergaven niet bewerken of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b4761-112">You can't edit or delete standard views.</span></span> 

<span data-ttu-id="b4761-113">Let op het volgende in verband met standaardweergaven:</span><span class="sxs-lookup"><span data-stu-id="b4761-113">A few things to note about standard views:</span></span> 

- <span data-ttu-id="b4761-p104">In bepaalde standaardweergaven wordt een ongesorteerde lijst weergegeven als de lijst meer dan 2.000 gebruikers bevat. Via het zoekvak kunt u vervolgens zoeken naar specifieke gebruikers in deze lijst.</span><span class="sxs-lookup"><span data-stu-id="b4761-p104">Some standard views display an unsorted list if there are more than 2,000 users in the list. To locate specific users in this list, use the search box.</span></span> 
- <span data-ttu-id="b4761-116">Als u geen Microsoft 365 bij Microsoft hebt gekocht, worden **factureringsbeheerders** niet weergegeven in de lijst met standaardweergaven.</span><span class="sxs-lookup"><span data-stu-id="b4761-116">If you didn't purchase Microsoft 365 from Microsoft, **Billing admins** don't appear in the standard views list.</span></span> <span data-ttu-id="b4761-117">Zie [Beheerdersrollen toewijzen](assign-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b4761-117">For more information, see [Assigning admin roles](assign-admin-roles.md).</span></span> 
  
## <a name="choose-the-filters-for-your-custom-user-view"></a><span data-ttu-id="b4761-118">Kies de filters voor de aangepaste gebruikersweergave</span><span class="sxs-lookup"><span data-stu-id="b4761-118">Choose the filters for your custom user view</span></span>

<span data-ttu-id="b4761-119">U kunt uw aangepaste weergaven maken en bewerken in **het deelvenster Aangepast filter.**</span><span class="sxs-lookup"><span data-stu-id="b4761-119">You can create and edit your custom views in the **Custom filter** pane.</span></span> <span data-ttu-id="b4761-120">Als u meerdere filteropties selecteert, bevatten de resultaten de gebruikers die voldoen aan alle geselecteerde criteria.</span><span class="sxs-lookup"><span data-stu-id="b4761-120">If you select multiple filter options, you get results that contain users who match all the selected criteria.</span></span> <span data-ttu-id="b4761-121">In het volgende voorbeeld ziet u hoe u een aangepaste weergave met de naam 'Canadese gebruikers' maakt, waarin alle gebruikers worden weergegeven op een specifiek domein en in Canada.</span><span class="sxs-lookup"><span data-stu-id="b4761-121">The following example shows you how to create a custom view named "Canadian users" that shows all users on a specific domain who are in Canada.</span></span> 

  
 <span data-ttu-id="b4761-122">**A - Domein** Als u meerdere domeinen voor uw organisatie hebt, kunt u kiezen uit een vervolgkeuzelijst met beschikbare domeinen.</span><span class="sxs-lookup"><span data-stu-id="b4761-122">**A - Domain** If you have multiple domains for your organization, you can choose from a drop-down list of domains that are available.</span></span> 
  
 <span data-ttu-id="b4761-123">**B - Aanmeldingsstatus** Kies gebruikers die zijn toegestaan of geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="b4761-123">**B - Sign-in status** Choose users that are allowed or blocked.</span></span> 
  
 <span data-ttu-id="b4761-124">**C - Locatie** Kies een locatie in een vervolgkeuzelijst met landen.</span><span class="sxs-lookup"><span data-stu-id="b4761-124">**C - Location** Choose a location from a drop-down list of countries.</span></span> 
  
 <span data-ttu-id="b4761-125">**D - Productlicentie toegewezen** Kies uit een vervolgkeuzelijst met licenties die beschikbaar zijn in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b4761-125">**D - Assigned product license** Choose from a drop-down list of licenses that are available at your organization.</span></span> <span data-ttu-id="b4761-126">Gebruik dit filter als u gebruikers wilt weergeven waaraan de geselecteerde licentie is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b4761-126">Use this filter to show users who have the license you selected assigned to them.</span></span> <span data-ttu-id="b4761-127">Gebruikers kunnen meerdere licenties hebben.</span><span class="sxs-lookup"><span data-stu-id="b4761-127">Users may also have additional licenses.</span></span> 
  
<span data-ttu-id="b4761-128">Ook kunt u filteren op andere gegevens uit het gebruikersprofiel die worden gebruikt in uw organisatie, zoals afdeling, plaats, staat of provincie, land of regio, of functie.</span><span class="sxs-lookup"><span data-stu-id="b4761-128">You can also filter by additional user profile details used in your organization such as department, city, state or province, country or region, or job title.</span></span>
  
 <span data-ttu-id="b4761-129">**Overige voorwaarden:**</span><span class="sxs-lookup"><span data-stu-id="b4761-129">**Other conditions:**</span></span>
  
- <span data-ttu-id="b4761-130">**Alleen gesynchroniseerde gebruikers** Selecteer dit vakje als u alle gebruikers wilt weergeven die zijn gesynchroniseerd met de lokale Active Directory, ongeacht of ze zijn geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="b4761-130">**Synchronized users only** Select this box to show all users who have been synced with the local Active Directory, regardless of whether the users have been activated or not.</span></span> 
    
- <span data-ttu-id="b4761-131">**Gebruikers met fouten** Selecteer dit vakje als u gebruikers wilt weergeven waarvoor mogelijk inrichtingsfouten zijn opgetreden.</span><span class="sxs-lookup"><span data-stu-id="b4761-131">**Users with errors** Select this box to show users who may have provisioning errors.</span></span> 
    
- <span data-ttu-id="b4761-p108">**Gebruikers zonder licentie** Selecteer dit vakje als u alle gebruikers wilt weergeven waaraan geen licentie is toegewezen. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-postvak hebben maar geen licentie. Als u deze gebruikers specifiek wilt opsporen, gebruikt u het filter **Gebruikers zonder licentie met Exchange-postvakken of -archieven**. Het resultaat van deze weergave kan ook gebruikers omvatten die een Exchange-archief hebben maar geen licentie.</span><span class="sxs-lookup"><span data-stu-id="b4761-p108">**Unlicensed users** Select this box to find all the users who haven't been assigned a license. The results for this view can also include users who have an Exchange mailbox but don't have a license. To track those users specifically, use the filter **Unlicensed users with Exchange mailboxes or archives**. The results for this view can also include users who have an Exchange archive, but don't have a license.</span></span>
    
- <span data-ttu-id="b4761-136">**Gebruikers zonder vergunning met Exchange of archieven** Schakel dit vakje in om gebruikersaccounts weer te geven die zijn gemaakt in Exchange Online en een Exchange postvak hebben, maar die geen licentie Microsoft 365 toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b4761-136">**Unlicensed users with Exchange mailboxes or archives** Select this box to show user accounts that were created in Exchange Online and have an Exchange mailbox, but weren't assigned an Microsoft 365 license.</span></span> <span data-ttu-id="b4761-137">De resultaten van dit filter omvatten gebruikers met een Exchange-archief of waaraan een archief is toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b4761-137">The results of this filter include users who have or who were assigned an Exchange archive.</span></span> 

> [!NOTE]
> <span data-ttu-id="b4761-138">Het **filter Niet-gelicenseerde gebruikers Exchange postvakken** werkt als:</span><span class="sxs-lookup"><span data-stu-id="b4761-138">The **Unlicensed users with Exchange mailboxes** filter works when:</span></span>
1. <span data-ttu-id="b4761-139">Het postvak is onlangs geconverteerd van **gedeeld** naar **gebruiker** en heeft geen licentie.</span><span class="sxs-lookup"><span data-stu-id="b4761-139">The mailbox has been recently converted from **shared** to **user** and it has no license.</span></span>
2. <span data-ttu-id="b4761-140">Het postvak is onlangs gemigreerd naar Microsoft 365 maar er is geen licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b4761-140">The mailbox has been recently migrated to Microsoft 365 but a license has not been assigned.</span></span>
3. <span data-ttu-id="b4761-141">Het postvak is gemaakt met PowerShell en er is geen licentie toegewezen.</span><span class="sxs-lookup"><span data-stu-id="b4761-141">The mailbox has been created using PowerShell, and a license has not been assigned.</span></span>
4. <span data-ttu-id="b4761-142">Een nieuw postvak dat on-premises is gemaakt met een New-RemoteMailbox cmdlet is ingericht voor de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="b4761-142">A new mailbox that has been created on-premise with a New-RemoteMailbox cmdlet is provisioned for the user.</span></span>
    
> [!TIP]
> <span data-ttu-id="b4761-143">Als u een aangepaste weergave maakt die meer dan 2.000 gebruikers oplevert, is de resulterende lijst ongesorteerd.</span><span class="sxs-lookup"><span data-stu-id="b4761-143">If you create a custom view that returns more than 2,000 users, the resulting user list isn't sorted.</span></span> <span data-ttu-id="b4761-144">Gebruik in dit geval het zoekvak om gebruikers te zoeken of uw aangepaste weergave te bewerken om uw zoekopdracht te verfijnen.</span><span class="sxs-lookup"><span data-stu-id="b4761-144">In this case, use the search box to find users or edit your custom view to refine your search.</span></span> 
  
## <a name="create-a-custom-user-view"></a><span data-ttu-id="b4761-145">Een aangepaste gebruikersweergave maken</span><span class="sxs-lookup"><span data-stu-id="b4761-145">Create a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b4761-146">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="b4761-146">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>
  
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b4761-147">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="b4761-147">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b4761-148">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="b4761-148">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span>  

::: moniker-end
    
2. <span data-ttu-id="b4761-149">Selecteer op **de pagina** Actieve gebruikers de **optie Filters** en selecteer **Nieuw filter.**</span><span class="sxs-lookup"><span data-stu-id="b4761-149">On the **Active users** page, select **Filters** and select **New filter**.</span></span>
  
3. <span data-ttu-id="b4761-150">Voer op **de pagina** Aangepast filter de naam voor het filter in, kies de voorwaarden voor het aangepaste filter en selecteer **vervolgens Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="b4761-150">On the **Custom filter** page, enter the name for your filter, choose the conditions for your custom filter, and then select **Add**.</span></span> <span data-ttu-id="b4761-151">Uw aangepaste weergave wordt nu opgenomen in de vervolgkeuzelijst met filters.</span><span class="sxs-lookup"><span data-stu-id="b4761-151">Your custom view is now included in the drop-down list of filters.</span></span>

## <a name="edit-or-delete-a-custom-user-view"></a><span data-ttu-id="b4761-152">Een aangepaste gebruikersweergave bewerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="b4761-152">Edit or delete a custom user view</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="b4761-153">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="b4761-153">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a>.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="b4761-154">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="b4761-154">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Active users</a>.</span></span> 

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="b4761-155">Ga in het beheercentrum naar **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers.</a></span><span class="sxs-lookup"><span data-stu-id="b4761-155">In the admin center, go to **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Active users</a>.</span></span> 

::: moniker-end 
    
2. <span data-ttu-id="b4761-156">Selecteer op **de pagina** Actieve gebruikers de optie **Filter,** selecteer het filter dat u wilt wijzigen en selecteer **vervolgens Filter bewerken.**</span><span class="sxs-lookup"><span data-stu-id="b4761-156">On the **Active users** page, select **Filter**, select the filter you want to change, and then select **Edit filter**.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="b4761-157">U kunt alleen aangepaste weergaven bewerken.</span><span class="sxs-lookup"><span data-stu-id="b4761-157">You can edit only custom views.</span></span> 
  
3. <span data-ttu-id="b4761-158">Bewerk **de gegevens op** de pagina Aangepast filter zo nodig en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="b4761-158">On the **Custom filter** page, edit the information as needed, and then select **Save**.</span></span> <span data-ttu-id="b4761-159">Of als u het filter wilt verwijderen, selecteert u onder aan de pagina **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="b4761-159">Or, to delete the filter, at the bottom of the page select **Delete**.</span></span> 

## <a name="related-content"></a><span data-ttu-id="b4761-160">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="b4761-160">Related content</span></span>

<span data-ttu-id="b4761-161">[Overzicht van het Microsoft 365](../../business-video/admin-center-overview.md) (video)</span><span class="sxs-lookup"><span data-stu-id="b4761-161">[Overview of the Microsoft 365 admin center](../../business-video/admin-center-overview.md) (video)</span></span>\
<span data-ttu-id="b4761-162">[Over beheerdersrollen](../add-users/about-admin-roles.md) (video)</span><span class="sxs-lookup"><span data-stu-id="b4761-162">[About admin roles](../add-users/about-admin-roles.md) (video)</span></span>\
<span data-ttu-id="b4761-163">[Het thema Microsoft 365 uw organisatie aanpassen](../setup/customize-your-organization-theme.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="b4761-163">[Customize the Microsoft 365 theme for your organization](../setup/customize-your-organization-theme.md) (article)</span></span>


     