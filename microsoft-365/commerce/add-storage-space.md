---
title: Opslagruimte voor uw abonnement toevoegen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Meer informatie over het toevoegen en beperken van bestandsopslag in uw Microsoft 365-abonnement. Met extra bestandsopslag kunt u meer inhoud opslaan in SharePoint Online en OneDrive.
ms.date: ''
ms.openlocfilehash: 626cc81faea43ebdcf618a4f26c33069bae6a206
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/03/2021
ms.locfileid: "50405886"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="354db-104">Opslagruimte voor uw abonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="354db-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="354db-105">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="354db-105">The admin center is changing.</span></span> <span data-ttu-id="354db-106">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="354db-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="354db-107">Als de opslagruimte voor uw SharePoint Online-siteverzamelingen begint vol te raken, kunt u opslagruimte aan uw abonnement toevoegen als uw abonnement daarvoor in aanmerking komt. </span><span class="sxs-lookup"><span data-stu-id="354db-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="354db-108">Als u Office **365 Extra** Bestandsopslag niet ziet in de lijst met beschikbare invoegtoepassingen, betekent dit dat uw abonnement niet in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="354db-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="354db-109">Zie Is my [plan eligible voor meer informatie?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="354db-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="354db-110">Als u uw abonnement hebt gekocht via volumelicenties of een CSP, kunt u niet rechtstreeks bij Microsoft **Office 365 Extra** bestandsopslag voor uw organisatie kopen.</span><span class="sxs-lookup"><span data-stu-id="354db-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="354db-111">Neem contact op met uw vertegenwoordiger of partner voor hulp.</span><span class="sxs-lookup"><span data-stu-id="354db-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="354db-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="354db-112">Before you begin</span></span>

<span data-ttu-id="354db-113">U moet een globale beheerder of Een SharePoint-beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="354db-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="354db-114">Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="354db-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="354db-115">Beschikbare opslag weergeven</span><span class="sxs-lookup"><span data-stu-id="354db-115">View available storage</span></span>

1. <span data-ttu-id="354db-116">Ga in het SharePoint-beheercentrum naar de pagina Actieve <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">sites</a> en meld u aan met een account met beheerdersmachtigingen [voor](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="354db-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="354db-117">In de rechterbovenhoek van de pagina ziet u de hoeveelheid opslagruimte die voor alle sites wordt gebruikt en de totale opslagruimte voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="354db-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="354db-118">Als uw organisatie Multi-Geo in Office 365 heeft geconfigureerd, toont de balk ook de hoeveelheid opslagruimte die in alle geografische locaties wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="354db-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Opslagbalk op de pagina Actieve sites](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="354db-120">De gebruikte opslagruimte omvat geen wijzigingen die zijn aangebracht in de afgelopen 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="354db-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="354db-121">Nadat u hebt bepaald hoeveel opslagruimte u gebruikt, kunt u opslagruimte voor uw abonnement toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="354db-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="354db-122">Als u wilt weten hoeveel het kost om opslagruimte toe te voegen, volgt u de stappen in dit artikel en bekijkt u de prijsinformatie voordat u meer koopt.</span><span class="sxs-lookup"><span data-stu-id="354db-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="354db-123">Zie [Opslaglimieten voor siteverzamelingen beheren](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) voor informatie over het instellen van opslaglimieten voor siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="354db-123">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="354db-124">Opslagruimte toevoegen aan uw abonnement</span><span class="sxs-lookup"><span data-stu-id="354db-124">Add storage to your subscription</span></span>

<span data-ttu-id="354db-125">Als u nog geen extra opslagruimte voor uw abonnement hebt gekocht, kunt u dat doen.</span><span class="sxs-lookup"><span data-stu-id="354db-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="354db-126">Ga in het beheercentrum naar de **pagina Services voor facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">aanschaffen.</a></span><span class="sxs-lookup"><span data-stu-id="354db-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="354db-127">Zoek onderaan de **pagina Services** aanschaffen  in de sectie Invoegtoepassingen naar **Office 365 Extra** bestandsopslag en selecteer **Details.**</span><span class="sxs-lookup"><span data-stu-id="354db-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="354db-128">Selecteer Volgende op de pagina met **productdetails.**</span><span class="sxs-lookup"><span data-stu-id="354db-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="354db-129">Kies indien nodig het basisabonnement en voer vervolgens het aantal gigabytes aan opslagruimte in dat u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="354db-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="354db-130">Selecteer **Nu uitchecken.**</span><span class="sxs-lookup"><span data-stu-id="354db-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="354db-131">Controleer op de pagina Hoe ziet dit **eruit?** het aantal gigabytes aan opslagruimte dat u hebt geselecteerd, controleer de prijsinformatie en selecteer **vervolgens Volgende.**</span><span class="sxs-lookup"><span data-stu-id="354db-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="354db-132">Controleer het **totaal op de** pagina Bestelling voltooien.</span><span class="sxs-lookup"><span data-stu-id="354db-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="354db-133">Als u wijzigingen wilt aanbrengen, selecteert u **Volgorde bewerken.**</span><span class="sxs-lookup"><span data-stu-id="354db-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="354db-134">Als voor de bestelling een kredietcontrole is vereist, selecteert u het selectievakje.</span><span class="sxs-lookup"><span data-stu-id="354db-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="354db-135">Wanneer u klaar bent, selecteert u **Bestelling plaatsen** \> **naar startpagina voor beheerders.**</span><span class="sxs-lookup"><span data-stu-id="354db-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="354db-136">Opslagruimte vergroten of verkleinen</span><span class="sxs-lookup"><span data-stu-id="354db-136">Increase or decrease storage</span></span>

<span data-ttu-id="354db-137">Als u al extra bestandsopslag hebt gekocht via de invoegabonnement **Office 365 Extra** Bestandsopslag, kunt u deze stappen gebruiken om de extra opslagruimte voor uw abonnement te vergroten of te verlagen.</span><span class="sxs-lookup"><span data-stu-id="354db-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="354db-138">U kunt de opslag beperken tot maar weinig dan 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="354db-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="354db-139">Neem contact op met ondersteuning als u alle extra [opslagruimte wilt verwijderen.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="354db-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="354db-140">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="354db-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="354db-141">Selecteer op **het** tabblad Producten het abonnement met de invoegvoegsnaam **Office 365 Extra** Bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="354db-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="354db-142">Selecteer Invoegtoepassingen beheren  op de pagina met productdetails in de sectie **Invoegtoepassingen.**</span><span class="sxs-lookup"><span data-stu-id="354db-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="354db-143">Kies in **het deelvenster Invoegtoepassingen** beheren in **de** lijst Met invoegtoepassingen **Office 365 Extra Bestandsopslag.**</span><span class="sxs-lookup"><span data-stu-id="354db-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="354db-144">Voer in **het** tekstvak Hoeveelheid het aantal gb-opslagruimte in dat u voor het abonnement wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="354db-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="354db-145">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="354db-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="354db-146">Komt mijn abonnement in aanmerking voor Office 365 Extra Bestandsopslag?</span><span class="sxs-lookup"><span data-stu-id="354db-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="354db-147">Office 365 Extra Bestandsopslag is beschikbaar voor de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="354db-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="354db-148">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="354db-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="354db-149">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="354db-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="354db-150">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="354db-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="354db-151">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="354db-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="354db-152">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="354db-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="354db-153">Office voor het web met SharePoint Abonnement 1</span><span class="sxs-lookup"><span data-stu-id="354db-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="354db-154">Office voor het web met SharePoint Abonnement 2</span><span class="sxs-lookup"><span data-stu-id="354db-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="354db-155">SharePoint Online, abonnement 1</span><span class="sxs-lookup"><span data-stu-id="354db-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="354db-156">SharePoint Online, abonnement 2</span><span class="sxs-lookup"><span data-stu-id="354db-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="354db-157">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="354db-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="354db-158">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="354db-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="354db-159">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="354db-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="354db-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="354db-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="354db-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="354db-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="354db-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="354db-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="354db-163">Office 365 Extra Bestandsopslag is ook beschikbaar voor de GCC-, GCC High- en DOD-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="354db-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="354db-164">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="354db-164">Related content</span></span>

<span data-ttu-id="354db-165">[Opslaglimieten voor site beheren](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel)</span><span class="sxs-lookup"><span data-stu-id="354db-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="354db-166">[De standaardopslagruimte voor OneDrive-gebruikers instellen](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="354db-166">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>