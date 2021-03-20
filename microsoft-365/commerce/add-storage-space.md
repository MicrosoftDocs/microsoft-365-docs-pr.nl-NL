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
description: Informatie over het toevoegen en beperken van bestandsopslag in uw Microsoft 365-abonnement. Met extra bestandsopslag kunt u meer inhoud opslaan in SharePoint Online en OneDrive.
ms.date: ''
ms.openlocfilehash: b170924f40d517cb6bbdf8635ad3e163eadc8643
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911924"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="35233-104">Opslagruimte voor uw abonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="35233-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="35233-105">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="35233-105">The admin center is changing.</span></span> <span data-ttu-id="35233-106">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="35233-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](../admin/microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="35233-107">Als de opslagruimte voor uw SharePoint Online-siteverzamelingen begint vol te raken, kunt u opslagruimte aan uw abonnement toevoegen als uw abonnement daarvoor in aanmerking komt. </span><span class="sxs-lookup"><span data-stu-id="35233-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="35233-108">Als u de **Office 365 Extra** Bestandsopslag niet ziet in de lijst met beschikbare invoegtoepassingen, betekent dit dat uw abonnement niet in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="35233-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="35233-109">Zie Komt mijn abonnement in aanmerking voor [meer informatie?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="35233-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="35233-110">Als u uw abonnement hebt gekocht via volumelicenties of een CSP, kunt u **Office 365 Extra** bestandsopslag voor uw organisatie niet rechtstreeks bij Microsoft kopen.</span><span class="sxs-lookup"><span data-stu-id="35233-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="35233-111">Neem contact op met uw vertegenwoordiger of partner voor hulp.</span><span class="sxs-lookup"><span data-stu-id="35233-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="35233-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="35233-112">Before you begin</span></span>

<span data-ttu-id="35233-113">U moet een globale beheerder of SharePoint-beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="35233-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="35233-114">Zie[Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="35233-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="35233-115">Beschikbare opslag weergeven</span><span class="sxs-lookup"><span data-stu-id="35233-115">View available storage</span></span>

1. <span data-ttu-id="35233-116">Ga in het SharePoint-beheercentrum naar de pagina Actieve <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">sites</a> en meld u aan met een account met [beheerdersmachtigingen](/sharepoint/sharepoint-admin-role) voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="35233-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="35233-117">Zie in de rechterbovenhoek van de pagina de hoeveelheid opslagruimte die op alle sites wordt gebruikt en de totale opslagruimte voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="35233-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="35233-118">Als uw organisatie Multi-Geo heeft geconfigureerd in Office 365, geeft de balk ook de hoeveelheid opslagruimte weer die wordt gebruikt op alle geografische locaties.</span><span class="sxs-lookup"><span data-stu-id="35233-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Opslagbalk op de pagina Actieve sites](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="35233-120">De gebruikte opslagruimte bevat geen wijzigingen die zijn aangebracht in de afgelopen 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="35233-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="35233-121">Nadat u hebt bepaald hoeveel opslagruimte u gebruikt, kunt u opslagruimte voor uw abonnement toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="35233-121">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="35233-122">Als u wilt weten hoeveel het kost om opslagruimte toe te voegen, volgt u de stappen in dit artikel en bekijkt u de prijsinformatie voordat u meer koopt.</span><span class="sxs-lookup"><span data-stu-id="35233-122">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="35233-123">Zie [Opslaglimieten voor siteverzamelingen beheren](/sharepoint/manage-site-collection-storage-limits) voor informatie over het instellen van opslaglimieten voor siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="35233-123">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="35233-124">Opslagruimte toevoegen aan uw abonnement</span><span class="sxs-lookup"><span data-stu-id="35233-124">Add storage to your subscription</span></span>

<span data-ttu-id="35233-125">Als u nog geen extra opslagruimte voor uw abonnement hebt gekocht, kunt u dat doen.</span><span class="sxs-lookup"><span data-stu-id="35233-125">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="35233-126">Ga in het beheercentrum naar de pagina  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Factureringsaankoopservices.</a></span><span class="sxs-lookup"><span data-stu-id="35233-126">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="35233-127">Zoek onder aan de **pagina** Services  aanschaffen in de sectie Invoegtoepassingen naar **Office 365 Extra** bestandsopslag en selecteer **Details.**</span><span class="sxs-lookup"><span data-stu-id="35233-127">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="35233-128">Selecteer volgende op de pagina **productdetails.**</span><span class="sxs-lookup"><span data-stu-id="35233-128">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="35233-129">Kies indien nodig het basisabonnement en voer het aantal gigabytes opslagruimte in dat u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="35233-129">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="35233-130">Selecteer **Nu uitchecken.**</span><span class="sxs-lookup"><span data-stu-id="35233-130">Select **Check out now**.</span></span>
6. <span data-ttu-id="35233-131">Controleer op de pagina Hoe ziet dit **eruit?** het aantal gigabytes opslagruimte dat u hebt geselecteerd, bekijk de prijsinformatie en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="35233-131">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="35233-132">Controleer op **de pagina** Complete order het totaal.</span><span class="sxs-lookup"><span data-stu-id="35233-132">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="35233-133">Als u wijzigingen wilt aanbrengen, selecteert u **Volgorde bewerken.**</span><span class="sxs-lookup"><span data-stu-id="35233-133">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="35233-134">Als voor de bestelling een kredietcontrole is vereist, schakelt u het selectievakje in.</span><span class="sxs-lookup"><span data-stu-id="35233-134">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="35233-135">Wanneer u klaar bent, selecteert u **Volgorde plaatsen** \> **Ga naar startpagina van beheerder.**</span><span class="sxs-lookup"><span data-stu-id="35233-135">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="35233-136">Opslagruimte vergroten of verkleinen</span><span class="sxs-lookup"><span data-stu-id="35233-136">Increase or decrease storage</span></span>

<span data-ttu-id="35233-137">Als u al extra bestandsopslag hebt gekocht via de **office 365 extra** bestandsopslag,kunt u deze stappen gebruiken om de extra opslagruimte voor uw abonnement te vergroten of te verminderen.</span><span class="sxs-lookup"><span data-stu-id="35233-137">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="35233-138">U kunt de opslag beperken tot maar 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="35233-138">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="35233-139">Als u alle extra opslagruimte wilt verwijderen, [neemt u contact op met ondersteuning.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="35233-139">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

1. <span data-ttu-id="35233-140">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="35233-140">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="35233-141">Selecteer op **het** tabblad Producten het abonnement dat de **office 365 extra** bestandsopslag-invoegvoeging bevat.</span><span class="sxs-lookup"><span data-stu-id="35233-141">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="35233-142">Selecteer op de pagina productdetails in **de** sectie Invoegtoepassingen de optie **Invoegtoepassingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="35233-142">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="35233-143">Kies in **het deelvenster Invoegtoepassingen beheren** in de lijst **Invoegtoepassingen** de optie **Office 365 Extra bestandsopslag.**</span><span class="sxs-lookup"><span data-stu-id="35233-143">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="35233-144">Voer in **het** tekstvak Hoeveelheid het aantal GB's opslagruimte in dat u voor het abonnement wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="35233-144">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="35233-145">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="35233-145">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="35233-146">Komt mijn abonnement in aanmerking voor Office 365 Extra Bestandsopslag?</span><span class="sxs-lookup"><span data-stu-id="35233-146">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="35233-147">Office 365 Extra Bestandsopslag is beschikbaar voor de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="35233-147">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="35233-148">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="35233-148">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="35233-149">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="35233-149">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="35233-150">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="35233-150">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="35233-151">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="35233-151">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="35233-152">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="35233-152">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="35233-153">Office voor het web met SharePoint-abonnement 1</span><span class="sxs-lookup"><span data-stu-id="35233-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="35233-154">Office voor het web met SharePoint-abonnement 2</span><span class="sxs-lookup"><span data-stu-id="35233-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="35233-155">SharePoint Online, abonnement 1</span><span class="sxs-lookup"><span data-stu-id="35233-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="35233-156">SharePoint Online, abonnement 2</span><span class="sxs-lookup"><span data-stu-id="35233-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="35233-157">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="35233-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="35233-158">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="35233-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="35233-159">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="35233-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="35233-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="35233-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="35233-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="35233-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="35233-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="35233-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="35233-163">Office 365 Extra Bestandsopslag is ook beschikbaar voor GCC-, GCC High- en DOD-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="35233-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="35233-164">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="35233-164">Related content</span></span>

<span data-ttu-id="35233-165">[Limieten voor siteopslag](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) beheren (artikel)</span><span class="sxs-lookup"><span data-stu-id="35233-165">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="35233-166">[De standaardopslagruimte instellen voor OneDrive-gebruikers](/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="35233-166">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>