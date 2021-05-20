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
description: Voeg bestandsopslag toe in uw Microsoft 365 abonnement. Met extra bestandsopslag kunt u meer inhoud opslaan in SharePoint Online en OneDrive.
ms.date: 04/02/2021
ms.openlocfilehash: b573205c7053aba0339d1f32deb2996ef80f8754
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572319"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="9559f-104">Opslagruimte voor uw abonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="9559f-104">Add storage space for your subscription</span></span>

<span data-ttu-id="9559f-105">Als de opslagruimte voor uw SharePoint Online-siteverzamelingen begint vol te raken, kunt u opslagruimte aan uw abonnement toevoegen als uw abonnement daarvoor in aanmerking komt. </span><span class="sxs-lookup"><span data-stu-id="9559f-105">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="9559f-106">Als u de **Office 365 Extra Bestandsopslag** niet ziet in de lijst met beschikbare add-ons, betekent dit dat uw abonnement niet in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="9559f-106">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="9559f-107">Zie [Komt mijn abonnement in aanmerking voor meer informatie?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="9559f-107">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="9559f-108">Als u uw abonnement hebt gekocht via Volume Licensing of een CSP, kunt u **Office 365 Extra Bestandsopslag** voor uw organisatie niet rechtstreeks bij Microsoft kopen.</span><span class="sxs-lookup"><span data-stu-id="9559f-108">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="9559f-109">Neem contact op met uw vertegenwoordiger of partner voor hulp.</span><span class="sxs-lookup"><span data-stu-id="9559f-109">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="9559f-110">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="9559f-110">Before you begin</span></span>

<span data-ttu-id="9559f-111">U moet een globale of SharePoint beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="9559f-111">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="9559f-112">Zie[Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="9559f-112">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="9559f-113">Beschikbare opslag weergeven</span><span class="sxs-lookup"><span data-stu-id="9559f-113">View available storage</span></span>

1. <span data-ttu-id="9559f-114">Ga in het SharePoint-beheercentrum naar de pagina <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Actieve sites</a> en meld u aan met een account met [beheerdersmachtigingen](/sharepoint/sharepoint-admin-role) voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="9559f-114">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="9559f-115">Bekijk rechtsboven op de pagina de hoeveelheid opslagruimte die op alle sites wordt gebruikt en de totale opslag voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="9559f-115">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="9559f-116">Als uw organisatie Multi-Geo in Office 365 heeft geconfigureerd, toont de balk ook de hoeveelheid opslag die wordt gebruikt op alle geolocaties.</span><span class="sxs-lookup"><span data-stu-id="9559f-116">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Storage balk op de pagina Actieve sites](/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="9559f-118">De gebruikte opslag bevat geen wijzigingen die in de afgelopen 24-48 uur zijn aangebracht.</span><span class="sxs-lookup"><span data-stu-id="9559f-118">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

<span data-ttu-id="9559f-119">Nadat u hebt bepaald hoeveel opslagruimte u gebruikt, kunt u opslagruimte voor uw abonnement toevoegen of verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9559f-119">After you determine how much storage you're using, you can add or remove storage space for your subscription.</span></span> <span data-ttu-id="9559f-120">Als u wilt weten hoeveel het kost om opslagruimte toe te voegen, volgt u de stappen in dit artikel en bekijkt u de prijsinformatie voordat u meer koopt.</span><span class="sxs-lookup"><span data-stu-id="9559f-120">To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you buy more.</span></span>
  
<span data-ttu-id="9559f-121">Zie [Opslaglimieten voor siteverzamelingen beheren](/sharepoint/manage-site-collection-storage-limits) voor informatie over het instellen van opslaglimieten voor siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="9559f-121">For information about setting site collection storage limits, see [Manage site collection storage limits](/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="9559f-122">Opslag toevoegen aan uw abonnement</span><span class="sxs-lookup"><span data-stu-id="9559f-122">Add storage to your subscription</span></span>

<span data-ttu-id="9559f-123">Als je nog geen extra opslagruimte voor je abonnement hebt gekocht, kun je dat doen.</span><span class="sxs-lookup"><span data-stu-id="9559f-123">If you haven't yet bought extra storage for your subscription, you can do that.</span></span>

1. <span data-ttu-id="9559f-124">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">inkoopservices.</a></span><span class="sxs-lookup"><span data-stu-id="9559f-124">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="9559f-125">Zoek Office 365 Extra Bestandsopslag onder aan de pagina **Inkoopservices** in de sectie **Invoegtoepassingen** en selecteer **Details**.</span><span class="sxs-lookup"><span data-stu-id="9559f-125">At the bottom of the **Purchase services** page, in the **Add-ons** section, find **Office 365 Extra File Storage**, and select **Details**.</span></span>
3. <span data-ttu-id="9559f-126">Selecteer **Volgende** op de pagina productdetails.</span><span class="sxs-lookup"><span data-stu-id="9559f-126">On the product details page, select **Next**.</span></span>
4. <span data-ttu-id="9559f-127">Kies indien nodig het basisabonnement en voer het aantal gigabytes opslagruimte in dat u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="9559f-127">If needed, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="9559f-128">Selecteer **Nu uitchecken**.</span><span class="sxs-lookup"><span data-stu-id="9559f-128">Select **Check out now**.</span></span>
6. <span data-ttu-id="9559f-129">Controleer op de pagina **Hoe ziet dit eruit?** het aantal gigabytes opslagruimte dat u hebt geselecteerd, bekijk de prijsinformatie en selecteer vervolgens **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="9559f-129">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="9559f-130">Controleer op de pagina **Bestelling voltooien** het totaal.</span><span class="sxs-lookup"><span data-stu-id="9559f-130">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="9559f-131">Als u wijzigingen wilt aanbrengen, selecteert u **Volgorde bewerken**.</span><span class="sxs-lookup"><span data-stu-id="9559f-131">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="9559f-132">Als voor de bestelling een kredietcontrole vereist is, schakelt u het selectievakje in.</span><span class="sxs-lookup"><span data-stu-id="9559f-132">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="9559f-133">Wanneer u klaar bent, selecteert u **Bestelling plaatsen** \> **Ga naar Admin Home**.</span><span class="sxs-lookup"><span data-stu-id="9559f-133">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="9559f-134">Opslagruimte vergroten of verkleinen</span><span class="sxs-lookup"><span data-stu-id="9559f-134">Increase or decrease storage</span></span>

<span data-ttu-id="9559f-135">Als u al extra bestandsopslag hebt gekocht via de **Office 365 Extra Bestandsopslag** add-on, kunt u deze stappen gebruiken om de extra opslagruimte voor uw abonnement te vergroten of te verkleinen.</span><span class="sxs-lookup"><span data-stu-id="9559f-135">If you've already bought extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="9559f-136">U kunt de opslag beperken tot slechts 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="9559f-136">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="9559f-137">Neem [contact op met](../business-video/get-help-support.md)de ondersteuning om alle extra opslagruimte te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="9559f-137">To remove all of the extra storage space, [contact support](../business-video/get-help-support.md).</span></span>

1. <span data-ttu-id="9559f-138">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="9559f-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="9559f-139">Selecteer op het tabblad **Producten** het abonnement dat de **Office 365 Extra Bestandsopslag** add-on bevat.</span><span class="sxs-lookup"><span data-stu-id="9559f-139">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="9559f-140">Selecteer op de pagina productdetails in de sectie **Add-ons** de optie **Invoegtoepassingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="9559f-140">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="9559f-141">Kies in het deelvenster **Invoegtoepassingen beheren** in de lijst **Invoegtoepassing** **Office 365 Extra Bestandsopslag**.</span><span class="sxs-lookup"><span data-stu-id="9559f-141">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="9559f-142">Voer **in** het tekstvak Aantal het gewenste aantal GB's opslagruimte in voor het abonnement.</span><span class="sxs-lookup"><span data-stu-id="9559f-142">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="9559f-143">Selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="9559f-143">Select **Save**.</span></span>

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="9559f-144">Komt mijn abonnement in aanmerking voor Office 365 Extra Bestandsopslag?</span><span class="sxs-lookup"><span data-stu-id="9559f-144">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="9559f-145">Office 365 Extra Bestandsopslag is beschikbaar voor de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="9559f-145">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="9559f-146">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="9559f-146">Office 365 Enterprise E1</span></span>
- <span data-ttu-id="9559f-147">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="9559f-147">Office 365 Enterprise E2</span></span>
- <span data-ttu-id="9559f-148">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="9559f-148">Office 365 Enterprise E3</span></span>
- <span data-ttu-id="9559f-149">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="9559f-149">Office 365 Enterprise E4</span></span>
- <span data-ttu-id="9559f-150">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="9559f-150">Office 365 Enterprise E5</span></span>
- <span data-ttu-id="9559f-151">webversie van Office met SharePoint Plan 1</span><span class="sxs-lookup"><span data-stu-id="9559f-151">Office for the web with SharePoint Plan 1</span></span>
- <span data-ttu-id="9559f-152">webversie van Office met SharePoint Plan 2</span><span class="sxs-lookup"><span data-stu-id="9559f-152">Office for the web with SharePoint Plan 2</span></span>
- <span data-ttu-id="9559f-153">SharePoint Online, abonnement 1</span><span class="sxs-lookup"><span data-stu-id="9559f-153">SharePoint Online Plan 1</span></span>
- <span data-ttu-id="9559f-154">SharePoint Online, abonnement 2</span><span class="sxs-lookup"><span data-stu-id="9559f-154">SharePoint Online Plan 2</span></span>
- <span data-ttu-id="9559f-155">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="9559f-155">Microsoft 365 Business Basic</span></span>
- <span data-ttu-id="9559f-156">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="9559f-156">Microsoft 365 Business Standard</span></span>
- <span data-ttu-id="9559f-157">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="9559f-157">Microsoft 365 Business Premium</span></span>
- <span data-ttu-id="9559f-158">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="9559f-158">Microsoft 365 E3</span></span>
- <span data-ttu-id="9559f-159">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="9559f-159">Microsoft 365 E5</span></span>
- <span data-ttu-id="9559f-160">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="9559f-160">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="9559f-161">Office 365 Extra Bestandsopslag is ook beschikbaar voor GCC-, GCC High- en DOD-plannen.</span><span class="sxs-lookup"><span data-stu-id="9559f-161">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="9559f-162">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="9559f-162">Related content</span></span>

<span data-ttu-id="9559f-163">[Siteopslaglimieten beheren](/sharepoint/manage-site-collection-storage-limits) (artikel)</span><span class="sxs-lookup"><span data-stu-id="9559f-163">[Manage site storage limits](/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="9559f-164">[De standaardopslagruimte instellen voor OneDrive gebruikers](/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="9559f-164">[Set the default storage space for OneDrive users](/onedrive/set-default-storage-space)(article)</span></span>
