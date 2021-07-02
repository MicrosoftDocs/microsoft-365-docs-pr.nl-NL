---
title: Opslagruimte voor uw abonnement toevoegen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: drjones, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
- commerce_purchase
search.appverid: MET150
description: Voeg bestandsopslag toe aan uw Microsoft 365 abonnement. Met extra bestandsopslag kunt u meer inhoud opslaan in SharePoint Online en OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: dee7debfbd2b624f3bf82bd573c81e7e1373b31e
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256817"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="ff69e-104">Opslagruimte voor uw abonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="ff69e-104">Add storage space for your subscription</span></span>

<span data-ttu-id="ff69e-105">Als de opslagruimte voor uw SharePoint Online-siteverzamelingen begint vol te raken, kunt u opslagruimte aan uw abonnement toevoegen als uw abonnement daarvoor in aanmerking komt. </span><span class="sxs-lookup"><span data-stu-id="ff69e-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="ff69e-106">Als u de gegevens niet ziet Office 365 Extra Bestandsopslag **in** de lijst met beschikbare invoegtoepassingen, betekent dit dat uw abonnement niet in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="ff69e-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="ff69e-107">Zie Komt mijn abonnement in aanmerking voor [meer informatie?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="ff69e-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="ff69e-108">Als u uw abonnement hebt gekocht via volumelicenties  of een CSP, kunt u geen Office 365 Extra Bestandsopslag rechtstreeks bij Microsoft kopen voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ff69e-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="ff69e-109">Neem contact op met uw vertegenwoordiger of partner voor hulp.</span><span class="sxs-lookup"><span data-stu-id="ff69e-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="ff69e-110">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="ff69e-110">Before you begin</span></span>

<span data-ttu-id="ff69e-111">U moet een globale beheerder of SharePoint zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ff69e-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="ff69e-112">Zie[Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ff69e-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="ff69e-113">Beschikbare opslag weergeven</span><span class="sxs-lookup"><span data-stu-id="ff69e-113">View available storage</span></span>

1. <span data-ttu-id="ff69e-114">Ga in SharePoint beheercentrum naar de pagina Actieve <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">sites</a> en meld u aan met een account met beheerdersmachtigingen [voor](/sharepoint/sharepoint-admin-role) uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ff69e-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="ff69e-115">Zie in de rechterbovenhoek van de pagina de hoeveelheid opslagruimte die op alle sites wordt gebruikt en de totale opslagruimte voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="ff69e-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="ff69e-116">Als uw organisatie Multi-Geo heeft geconfigureerd in Office 365, geeft de balk ook de hoeveelheid opslagruimte weer die op alle geografische locaties wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ff69e-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Storage balk op de pagina Actieve sites](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="ff69e-118">De gebruikte opslagruimte bevat geen wijzigingen die zijn aangebracht in de afgelopen 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="ff69e-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="ff69e-119">Nadat u hebt bepaald hoeveel opslagruimte u gebruikt, kunt u opslagruimte voor uw abonnement toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ff69e-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="ff69e-120">Als u wilt weten hoeveel het kost om opslagruimte toe te voegen, volgt u de stappen in dit artikel en bekijkt u de prijsinformatie voordat u meer koopt.</span><span class="sxs-lookup"><span data-stu-id="ff69e-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="ff69e-121">Zie [Opslaglimieten voor siteverzamelingen beheren](/sharepoint/manage-site-collection-storage-limits) voor informatie over het instellen van opslaglimieten voor siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="ff69e-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="ff69e-122">Opslagruimte toevoegen aan uw abonnement</span><span class="sxs-lookup"><span data-stu-id="ff69e-122">Add storage to your subscription</span></span>

<span data-ttu-id="ff69e-123">Als u nog geen extra opslagruimte voor uw abonnement hebt gekocht, kunt u dat doen.</span><span class="sxs-lookup"><span data-stu-id="ff69e-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="ff69e-124">Ga in het beheercentrum naar de pagina  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Factureringsaankoopservices.</a></span><span class="sxs-lookup"><span data-stu-id="ff69e-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="ff69e-125">Zoek onder aan de pagina Services  **aanschaffen** in de sectie Invoegtoepassingen naar Office 365 Extra Bestandsopslag **en** selecteer **Details.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="ff69e-126">Selecteer volgende op de pagina **productdetails.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="ff69e-127">Kies indien nodig het basisabonnement en voer het aantal gigabytes opslagruimte in dat u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="ff69e-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="ff69e-128">Selecteer **Nu uitchecken.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="ff69e-129">Controleer op de pagina Hoe ziet dit **eruit?** het aantal gigabytes opslagruimte dat u hebt geselecteerd, bekijk de prijsinformatie en selecteer **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="ff69e-130">Controleer op **de pagina** Complete order het totaal.</span><span class="sxs-lookup"><span data-stu-id="ff69e-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="ff69e-131">Als u wijzigingen wilt aanbrengen, selecteert u **Volgorde bewerken.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="ff69e-132">Als voor de bestelling een kredietcontrole is vereist, schakelt u het selectievakje in.</span><span class="sxs-lookup"><span data-stu-id="ff69e-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="ff69e-133">Wanneer u klaar bent, selecteert u **Volgorde plaatsen** \> **Ga naar startpagina van beheerder.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="ff69e-134">Opslagruimte vergroten of verkleinen</span><span class="sxs-lookup"><span data-stu-id="ff69e-134">Increase or decrease storage</span></span>

<span data-ttu-id="ff69e-135">Als u al extra bestandsopslag  hebt gekocht via de Office 365 Extra Bestandsopslag, kunt u deze stappen gebruiken om de extra opslagruimte voor uw abonnement te vergroten of te verminderen.</span><span class="sxs-lookup"><span data-stu-id="ff69e-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="ff69e-136">U kunt de opslag beperken tot maar 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="ff69e-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="ff69e-137">Als u alle extra opslagruimte wilt verwijderen, [neemt u contact op met ondersteuning.](../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="ff69e-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="ff69e-138">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="ff69e-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ff69e-139">Selecteer op **het** tabblad Producten het abonnement dat de Office 365 Extra Bestandsopslag **bevat.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="ff69e-140">Selecteer op de pagina productdetails in **de** sectie Invoegtoepassingen de optie **Invoegtoepassingen beheren.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="ff69e-141">Kies in **het deelvenster Invoegtoepassingen beheren** in de lijst **Invoegtoepassingen** de **optie Office 365 Extra Bestandsopslag.**</span><span class="sxs-lookup"><span data-stu-id="ff69e-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="ff69e-142">Voer in **het** tekstvak Hoeveelheid het aantal GB's opslagruimte in dat u voor het abonnement wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ff69e-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="ff69e-143">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="ff69e-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="ff69e-144">Komt mijn abonnement in aanmerking voor Office 365 Extra Bestandsopslag?</span><span class="sxs-lookup"><span data-stu-id="ff69e-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="ff69e-145">Office 365 Extra Bestandsopslag is beschikbaar voor de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="ff69e-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="ff69e-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="ff69e-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="ff69e-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="ff69e-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="ff69e-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="ff69e-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="ff69e-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="ff69e-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="ff69e-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="ff69e-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="ff69e-151">Office 365 A3 (faculteit)</span><span class="sxs-lookup"><span data-stu-id="ff69e-151">Office 365 A3 (faculty)</span></span>
- <span data-ttu-id="ff69e-152">Office 365 A5 (faculteit)</span><span class="sxs-lookup"><span data-stu-id="ff69e-152">Office 365 A5 (faculty)</span></span>
- <span data-ttu-id="ff69e-153">webversie van Office met SharePoint plan 1</span><span class="sxs-lookup"><span data-stu-id="ff69e-153">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="ff69e-154">webversie van Office met SharePoint plan 2</span><span class="sxs-lookup"><span data-stu-id="ff69e-154">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="ff69e-155">SharePoint Online, abonnement 1</span><span class="sxs-lookup"><span data-stu-id="ff69e-155">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="ff69e-156">SharePoint Online, abonnement 2</span><span class="sxs-lookup"><span data-stu-id="ff69e-156">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="ff69e-157">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="ff69e-157">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="ff69e-158">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="ff69e-158">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="ff69e-159">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="ff69e-159">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="ff69e-160">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="ff69e-160">Microsoft 365 E3</span></span>
- <span data-ttu-id="ff69e-161">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="ff69e-161">Microsoft 365 E5</span></span>
- <span data-ttu-id="ff69e-162">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="ff69e-162">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="ff69e-163">Office 365 Extra Bestandsopslag is ook beschikbaar voor GCC, GCC High en DOD-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="ff69e-163">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="ff69e-164">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="ff69e-164">Related content</span></span>

<span data-ttu-id="ff69e-165">[Limieten voor siteopslag](/sharepoint/manage-site-collection-storage-limits) beheren (artikel)</span><span class="sxs-lookup"><span data-stu-id="ff69e-165">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="ff69e-166">[De standaardopslagruimte instellen voor OneDrive gebruikers](/onedrive/set-default-storage-space) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ff69e-166">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space) (article)</span></span>
