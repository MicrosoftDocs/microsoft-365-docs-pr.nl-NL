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
- commerce
- Adm_TOC
- SPO_Content
ms.custom:
- MAX_CampaignID
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het toevoegen en beperken van bestandsopslag in uw Microsoft 365-abonnement. Met extra bestandsopslag kunt u meer inhoud opslaan in SharePoint Online en OneDrive.
ms.date: ''
ms.openlocfilehash: fd59de31a27a1dd29800ae1d081e1f509f399124
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114905"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="6c9f8-104">Opslagruimte voor uw abonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="6c9f8-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="6c9f8-105">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-105">The admin center is changing.</span></span> <span data-ttu-id="6c9f8-106">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="6c9f8-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="6c9f8-107">Als de opslagruimte voor uw SharePoint Online-siteverzamelingen begint vol te raken, kunt u opslagruimte aan uw abonnement toevoegen als uw abonnement daarvoor in aanmerking komt. </span><span class="sxs-lookup"><span data-stu-id="6c9f8-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="6c9f8-108">Als u Office **365 Extra** Bestandsopslag niet ziet in de lijst met beschikbare invoegtoepassingen, betekent dit dat uw abonnement niet in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="6c9f8-109">Zie Is my [plan eligible voor meer informatie?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="6c9f8-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="6c9f8-110">Als u uw abonnement hebt gekocht via volumelicenties of een CSP, kunt u niet rechtstreeks bij Microsoft **Office 365 Extra** bestandsopslag voor uw organisatie kopen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="6c9f8-111">Neem contact op met uw vertegenwoordiger of partner voor hulp.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="6c9f8-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="6c9f8-112">Before you begin</span></span>

<span data-ttu-id="6c9f8-113">U moet een globale beheerder of Een SharePoint-beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="6c9f8-114">Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="6c9f8-115">Beschikbare opslag weergeven</span><span class="sxs-lookup"><span data-stu-id="6c9f8-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6c9f8-116">Ga in het SharePoint-beheercentrum naar de pagina Actieve <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">sites</a> en meld u aan met een account met beheerdersmachtigingen [voor](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="6c9f8-117">In de rechterbovenhoek van de pagina ziet u de hoeveelheid opslagruimte die voor alle sites wordt gebruikt en de totale opslagruimte voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="6c9f8-118">Als uw organisatie Multi-Geo in Office 365 heeft geconfigureerd, toont de balk ook de hoeveelheid opslagruimte die in alle geografische locaties wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Opslagbalk op de pagina Actieve sites](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="6c9f8-120">De gebruikte opslagruimte omvat geen wijzigingen die zijn aangebracht in de afgelopen 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6c9f8-121">Meld u aan als globale of SharePoint-beheerder en selecteer vervolgens de tegel Beheerder om https://portal.office.de het beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="6c9f8-122">Als u een bericht ziet dat u niet bent machtigingen voor toegang tot de pagina, betekent dit dat u niet over beheerdersmachtigingen voor Microsoft 365 in uw organisatie hebt.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="6c9f8-123">Selecteer **SharePoint** in het **linkerdeelvenster,** onder Beheercentra.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="6c9f8-124">Als het klassieke SharePoint-beheercentrum  wordt weergegeven, selecteert u Nu openen bovenaan de pagina om het nieuwe SharePoint-beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="6c9f8-125">Selecteer Actieve sites in het linkerdeelvenster van het nieuwe **SharePoint-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="6c9f8-126">In de rechterbovenhoek van de pagina ziet u de hoeveelheid opslagruimte die voor alle sites wordt gebruikt en de totale opslagruimte voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Opslagbalk op de pagina Actieve sites](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="6c9f8-128">De gebruikte opslagruimte omvat geen wijzigingen die zijn aangebracht in de afgelopen 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6c9f8-129">Meld u aan als globale of SharePoint-beheerder en selecteer vervolgens de tegel Beheerder om https://login.partner.microsoftonline.cn/ het beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="6c9f8-130">(Als u een bericht ziet dat u niet bent machtigingen voor toegang tot de pagina, betekent dit dat u niet over beheerdersmachtigingen voor Microsoft 365 in uw organisatie hebt.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="6c9f8-131">Selecteer **SharePoint** in het **linkerdeelvenster,** onder Beheercentra.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="6c9f8-132">Als het klassieke SharePoint-beheercentrum  wordt weergegeven, selecteert u Nu openen bovenaan de pagina om het nieuwe SharePoint-beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="6c9f8-133">Selecteer Actieve sites in het linkerdeelvenster van het nieuwe **SharePoint-beheercentrum.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="6c9f8-134">In de rechterbovenhoek van de pagina ziet u de hoeveelheid opslagruimte die voor alle sites wordt gebruikt en de totale opslagruimte voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Opslagbalk op de pagina Actieve sites](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="6c9f8-136">De gebruikte opslagruimte omvat geen wijzigingen die zijn aangebracht in de afgelopen 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="6c9f8-p111">Nadat u hebt vastgesteld hoeveel opslagruimte u gebruikt, kunt u opslagruimte voor uw abonnement toevoegen of verwijderen. Volg de stappen in dit artikel als u wilt weten wat het kost om opslagruimte toe te voegen, en bekijk de prijsinformatie voordat u iets koopt.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-p111">After you've determined how much storage you're using, you can add or remove storage space for your subscription. To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="6c9f8-139">Zie [Opslaglimieten voor siteverzamelingen beheren](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) voor informatie over het instellen van opslaglimieten voor siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="6c9f8-140">Opslagruimte toevoegen aan uw abonnement</span><span class="sxs-lookup"><span data-stu-id="6c9f8-140">Add storage to your subscription</span></span>

<span data-ttu-id="6c9f8-141">Als u nog geen extra opslagruimte voor uw abonnement hebt gekocht, kunt u dat doen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6c9f8-142">Ga in het beheercentrum naar de **pagina Services voor facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">aanschaffen.</a></span><span class="sxs-lookup"><span data-stu-id="6c9f8-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="6c9f8-143">Selecteer invoegtoepassingen onder aan de pagina **Services** **aanschaffen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="6c9f8-144">Selecteer **Office 365 Extra bestandsopslag.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="6c9f8-145">Kies, indien weergegeven, op de pagina **Office 365 Extra** Bestandsopslag het basisabonnement en voer vervolgens het aantal gigabytes aan opslagruimte in dat u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="6c9f8-146">Selecteer **Nu uitchecken.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="6c9f8-147">Controleer op de pagina Hoe ziet dit **eruit?** het aantal gigabytes aan opslagruimte dat u hebt geselecteerd, controleer de prijsinformatie en selecteer **vervolgens Volgende.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="6c9f8-148">Controleer het **totaal op de** pagina Bestelling voltooien.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="6c9f8-149">Als u wijzigingen wilt aanbrengen, selecteert u **Volgorde bewerken.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="6c9f8-150">Als voor de bestelling een kredietcontrole is vereist, selecteert u het selectievakje.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="6c9f8-151">Wanneer u klaar bent, selecteert u **Bestelling plaatsen** \> **naar startpagina voor beheerders.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6c9f8-152">Ga in het beheercentrum naar de **pagina** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Factureringsabonnementen.</a>  </span><span class="sxs-lookup"><span data-stu-id="6c9f8-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="6c9f8-153">Kies op **de pagina** Abonnementen het abonnement waaraan u opslagruimte wilt toevoegen en selecteer **invoegtoepassingen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="6c9f8-155">Als u geen **uitbreidingen** ziet en uw abonnement is gekocht via een partner, selecteert u **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="6c9f8-156">Selecteer **Invoegtoepassingen kopen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-156">Select **Buy add-ons**.</span></span>

    ![Koppeling Invoegtoepassingen kopen op de pagina Abonnementen van het beheercentrum.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="6c9f8-158">Wijs **op de pagina Services** aanschaffen met de **muisaanwijzer Office 365 Extra bestandsopslag** aan of tik op Opslaan en selecteer Nu **kopen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="6c9f8-159">Voer het aantal gebruikerslicenties in dat u nodig hebt en kies, indien weergegeven, een basisabonnement.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="6c9f8-160">Selecteer **Nu uitchecken.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="6c9f8-161">Controleer op de pagina Hoe ziet dit **eruit?** het aantal gigabytes aan opslagruimte dat u hebt geselecteerd, controleer de prijsinformatie en selecteer **vervolgens Volgende.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="6c9f8-162">Selecteer Bestelling **plaatsen op** de pagina **Bestelling voltooien.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6c9f8-163">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="6c9f8-164">Kies op **de pagina** Abonnementen het abonnement waaraan u opslagruimte wilt toevoegen en selecteer **invoegtoepassingen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="6c9f8-166">Als u geen **uitbreidingen** ziet en uw abonnement is gekocht via een partner, selecteert u **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="6c9f8-167">Selecteer **Invoegtoepassingen kopen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-167">Select **Buy add-ons**.</span></span>

    ![Koppeling Invoegtoepassingen kopen op de pagina Abonnementen van het beheercentrum.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="6c9f8-169">Wijs **op de pagina Services** aanschaffen met de **muisaanwijzer Office 365 Extra bestandsopslag** aan of tik op Opslaan en selecteer Nu **kopen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="6c9f8-170">Voer het aantal gebruikerslicenties in dat u nodig hebt en kies, indien weergegeven, een basisabonnement.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="6c9f8-171">Selecteer **Nu uitchecken.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="6c9f8-172">Controleer op de pagina Hoe ziet dit **eruit?** het aantal gigabytes aan opslagruimte dat u hebt geselecteerd, controleer de prijsinformatie en selecteer **vervolgens Volgende.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="6c9f8-173">Selecteer Bestelling **plaatsen op** de pagina **Bestelling voltooien.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="6c9f8-174">Opslagruimte vergroten of verkleinen</span><span class="sxs-lookup"><span data-stu-id="6c9f8-174">Increase or decrease storage</span></span>

<span data-ttu-id="6c9f8-175">Als u al extra bestandsopslag hebt gekocht via de invoegabonnement **Office 365 Extra** Bestandsopslag, kunt u deze stappen gebruiken om de extra opslagruimte voor uw abonnement te vergroten of te verlagen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="6c9f8-176">U kunt de opslag beperken tot maar weinig dan 1 gigabyte.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="6c9f8-177">Neem contact op met ondersteuning als u alle extra [opslagruimte wilt verwijderen.](../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="6c9f8-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="6c9f8-178">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="6c9f8-179">Selecteer op **het** tabblad Producten het abonnement met de invoegvoegsnaam **Office 365 Extra** Bestandsopslag.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="6c9f8-180">Selecteer Invoegtoepassingen beheren  op de pagina met productdetails in de sectie **Invoegtoepassingen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="6c9f8-181">Kies in **het deelvenster Invoegtoepassingen** beheren in **de** lijst Met invoegtoepassingen **Office 365 Extra Bestandsopslag.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="6c9f8-182">Voer in **het** tekstvak Hoeveelheid het aantal gb-opslagruimte in dat u voor het abonnement wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="6c9f8-183">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="6c9f8-184">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="6c9f8-185">Selecteer **invoegtoepassingen op de** pagina **Abonnementen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="6c9f8-187">Als u geen **uitbreidingen** ziet en uw abonnement is gekocht via een partner, selecteert u **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="6c9f8-188">Selecteer aantal wijzigen onder **Office 365 Extra** **Bestandsopslag.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Koppeling voor Aantal wijzigen.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="6c9f8-190">Voer in het rechterdeelvenster het totale aantal gigabytes in dat u nodig hebt en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="6c9f8-191">Als u bijvoorbeeld momenteel 200 GB extra opslagruimte hebt, maar slechts 100 gigabyte nodig hebt, typt u **100** in het vak.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="6c9f8-192">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="6c9f8-193">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="6c9f8-194">Selecteer **invoegtoepassingen op de** pagina **Abonnementen.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="6c9f8-196">Als u geen **uitbreidingen** ziet en uw abonnement is gekocht via een partner, selecteert u **Volume Licensing Service Center (VLSC).**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="6c9f8-197">Selecteer aantal wijzigen onder **Office 365 Extra** **Bestandsopslag.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Koppeling voor Aantal wijzigen.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="6c9f8-199">Voer in het rechterdeelvenster het totale aantal gigabytes in dat u nodig hebt en selecteer **Verzenden.**</span><span class="sxs-lookup"><span data-stu-id="6c9f8-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="6c9f8-200">Als u bijvoorbeeld momenteel 200 GB extra opslagruimte hebt, maar slechts 100 gigabyte nodig hebt, typt u **100** in het vak.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="6c9f8-201">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="6c9f8-202">Komt mijn abonnement in aanmerking voor Office 365 Extra Bestandsopslag?</span><span class="sxs-lookup"><span data-stu-id="6c9f8-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="6c9f8-203">Office 365 Extra Bestandsopslag is beschikbaar voor de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="6c9f8-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="6c9f8-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="6c9f8-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="6c9f8-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="6c9f8-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="6c9f8-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="6c9f8-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="6c9f8-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="6c9f8-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="6c9f8-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="6c9f8-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="6c9f8-209">Office voor het web met SharePoint Abonnement 1</span><span class="sxs-lookup"><span data-stu-id="6c9f8-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="6c9f8-210">Office voor het web met SharePoint Abonnement 2</span><span class="sxs-lookup"><span data-stu-id="6c9f8-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="6c9f8-211">SharePoint Online, abonnement 1</span><span class="sxs-lookup"><span data-stu-id="6c9f8-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="6c9f8-212">SharePoint Online, abonnement 2</span><span class="sxs-lookup"><span data-stu-id="6c9f8-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="6c9f8-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="6c9f8-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="6c9f8-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="6c9f8-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="6c9f8-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="6c9f8-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="6c9f8-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="6c9f8-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="6c9f8-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="6c9f8-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="6c9f8-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="6c9f8-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="6c9f8-219">Office 365 Extra Bestandsopslag is ook beschikbaar voor de GCC-, GCC High- en DOD-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="6c9f8-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="6c9f8-220">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="6c9f8-220">Related content</span></span>

<span data-ttu-id="6c9f8-221">[Opslaglimieten voor site beheren](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel)</span><span class="sxs-lookup"><span data-stu-id="6c9f8-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="6c9f8-222">[De standaardopslagruimte voor OneDrive-gebruikers instellen](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="6c9f8-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
