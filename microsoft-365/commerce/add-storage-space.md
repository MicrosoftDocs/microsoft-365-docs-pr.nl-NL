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
description: Leer hoe u bestanden kunt toevoegen en reduceren in uw abonnement op Microsoft 365. Met extra opslagruimte kunt u meer inhoud opslaan in SharePoint Online en OneDrive.
ms.date: ''
ms.openlocfilehash: 7f9973054bfe97beae36e28b73a3eb2025a13e73
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324466"
---
# <a name="add-storage-space-for-your-subscription"></a><span data-ttu-id="c74d5-104">Opslagruimte voor uw abonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="c74d5-104">Add storage space for your subscription</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c74d5-105">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="c74d5-105">The admin center is changing.</span></span> <span data-ttu-id="c74d5-106">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c74d5-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c74d5-107">Als de opslagruimte voor uw SharePoint Online-siteverzamelingen begint vol te raken, kunt u opslagruimte aan uw abonnement toevoegen als uw abonnement daarvoor in aanmerking komt. </span><span class="sxs-lookup"><span data-stu-id="c74d5-107">If you start to run out of storage for your SharePoint Online site collections, you can add storage to your subscription if your plan is eligible.</span></span> <span data-ttu-id="c74d5-108">Als u de **opslagruimte van Office 365** niet ziet in de lijst met beschikbare invoegtoepassingen, betekent dit dat uw abonnement niet in aanmerking komt.</span><span class="sxs-lookup"><span data-stu-id="c74d5-108">If you don't see the **Office 365 Extra File Storage** in the list of available add-ons, it means your plan is not eligible.</span></span> <span data-ttu-id="c74d5-109">Zie voor meer informatie: [mijn abonnement komt in aanmerking?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span><span class="sxs-lookup"><span data-stu-id="c74d5-109">For more information, see [Is my plan eligible?](#is-my-plan-eligible-for-office-365-extra-file-storage)</span></span>

> [!NOTE]
> <span data-ttu-id="c74d5-110">Als u uw abonnement hebt gekocht via Volume Licensing of een CSP, kunt u **Office 365 extra bestandsopslag** voor uw organisatie niet rechtstreeks bij Microsoft kopen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-110">If you bought your subscription through Volume Licensing or a CSP, you can't buy **Office 365 Extra File Storage** for your organization directly from Microsoft.</span></span> <span data-ttu-id="c74d5-111">Neem contact op met uw vertegenwoordiger of partner voor hulp.</span><span class="sxs-lookup"><span data-stu-id="c74d5-111">Contact your representative or partner for help.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c74d5-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="c74d5-112">Before you begin</span></span>

<span data-ttu-id="c74d5-113">U moet een globale beheerder of SharePoint-beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="c74d5-113">You must be a Global or SharePoint admin to do the tasks in this article.</span></span> <span data-ttu-id="c74d5-114">Raadpleeg [Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c74d5-114">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="view-available-storage"></a><span data-ttu-id="c74d5-115">Beschikbare opslag weergeven</span><span class="sxs-lookup"><span data-stu-id="c74d5-115">View available storage</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c74d5-116">Ga in het SharePoint-Beheercentrum naar de pagina <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">actieve sites</a> en meld u aan met een account met [beheerdersmachtigingen](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c74d5-116">In the SharePoint admin center, go to the <a href="https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true" target="_blank">Active sites</a> page, and sign in with an account that has [admin permissions](https://docs.microsoft.com/sharepoint/sharepoint-admin-role) for your organization.</span></span>

2. <span data-ttu-id="c74d5-117">In de rechterbovenhoek van de pagina ziet u de hoeveelheid gebruikte opslagruimte voor alle sites en de totale opslag voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c74d5-117">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span> <span data-ttu-id="c74d5-118">Als uw organisatie meerdere geografische locaties heeft geconfigureerd in Office 365, wordt in de balk ook de hoeveelheid opslagruimte weergegeven die wordt gebruikt voor alle geo-locaties.</span><span class="sxs-lookup"><span data-stu-id="c74d5-118">If your organization has configured Multi-Geo in Office 365, the bar also shows the amount of storage used across all geo locations.</span></span>

   ![Opslag balk op de pagina actieve sites](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c74d5-120">De gebruikte opslagruimte bevat geen wijzigingen die zijn aangebracht in de laatste 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="c74d5-120">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c74d5-121">Meld u aan https://portal.office.de als globale beheerder of SharePoint-beheerder en selecteer vervolgens de tegel beheerder om het Beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-121">Sign in to https://portal.office.de as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c74d5-122">Als u een bericht ziet dat u geen machtiging hebt voor toegang tot de pagina, betekent dit dat u geen Microsoft 365-beheerdersmachtigingen hebt in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c74d5-122">If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="c74d5-123">Selecteer in het linkerdeelvenster onder **beheer centra**de optie **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-123">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c74d5-124">Als het klassieke SharePoint-Beheercentrum wordt weergegeven, selecteert u **Open dit nu** boven aan de pagina om het nieuwe SharePoint-Beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-124">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="c74d5-125">Selecteer in het linkerdeelvenster van het nieuwe SharePoint-Beheercentrum de optie **actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-125">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c74d5-126">In de rechterbovenhoek van de pagina ziet u de hoeveelheid gebruikte opslagruimte voor alle sites en de totale opslag voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c74d5-126">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>

   ![Opslag balk op de pagina actieve sites](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c74d5-128">De gebruikte opslagruimte bevat geen wijzigingen die zijn aangebracht in de laatste 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="c74d5-128">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c74d5-129">Meld u aan https://login.partner.microsoftonline.cn/ als globale beheerder of SharePoint-beheerder en selecteer vervolgens de tegel beheerder om het Beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-129">Sign in to https://login.partner.microsoftonline.cn/ as a global or SharePoint admin, and then select the Admin tile to open the admin center.</span></span> <span data-ttu-id="c74d5-130">(Als u een bericht ziet dat u geen machtiging hebt voor toegang tot de pagina, betekent dit dat u geen Microsoft 365-beheerdersmachtigingen hebt in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="c74d5-130">(If you see a message that you don't have permission to access the page, it means that you don't have Microsoft 365 administrator permissions in your organization.</span></span>

2. <span data-ttu-id="c74d5-131">Selecteer in het linkerdeelvenster onder **beheer centra**de optie **SharePoint**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-131">In the left pane, under **Admin centers**, select **SharePoint**.</span></span> <span data-ttu-id="c74d5-132">Als het klassieke SharePoint-Beheercentrum wordt weergegeven, selecteert u **Open dit nu** boven aan de pagina om het nieuwe SharePoint-Beheercentrum te openen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-132">If the classic SharePoint admin center appears, select **Open it now** at the top of the page to open the new SharePoint admin center.</span></span>

3. <span data-ttu-id="c74d5-133">Selecteer in het linkerdeelvenster van het nieuwe SharePoint-Beheercentrum de optie **actieve sites**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-133">In the left pane of the new SharePoint admin center, select **Active sites**.</span></span>

4. <span data-ttu-id="c74d5-134">In de rechterbovenhoek van de pagina ziet u de hoeveelheid gebruikte opslagruimte voor alle sites en de totale opslag voor uw abonnement.</span><span class="sxs-lookup"><span data-stu-id="c74d5-134">In the upper right of the page, see the amount of storage used across all sites, and the total storage for your subscription.</span></span>  

   ![Opslag balk op de pagina actieve sites](https://docs.microsoft.com/sharepoint/sharepointonline/media/active-sites-storage-bar.png)

   > [!NOTE]
   > <span data-ttu-id="c74d5-136">De gebruikte opslagruimte bevat geen wijzigingen die zijn aangebracht in de laatste 24-48 uur.</span><span class="sxs-lookup"><span data-stu-id="c74d5-136">The storage used doesn't include changes made within the last 24-48 hours.</span></span>

::: moniker-end

<span data-ttu-id="c74d5-p111">Nadat u hebt vastgesteld hoeveel opslagruimte u gebruikt, kunt u opslagruimte voor uw abonnement toevoegen of verwijderen. Volg de stappen in dit artikel als u wilt weten wat het kost om opslagruimte toe te voegen, en bekijk de prijsinformatie voordat u iets koopt.</span><span class="sxs-lookup"><span data-stu-id="c74d5-p111">After you've determined how much storage you're using, you can add or remove storage space for your subscription. To find out how much it will cost to add storage space, follow the steps in this article, and review the pricing information before you purchase.</span></span>
  
<span data-ttu-id="c74d5-139">Zie [Opslaglimieten voor siteverzamelingen beheren](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) voor informatie over het instellen van opslaglimieten voor siteverzamelingen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-139">For information about setting site collection storage limits, see [Manage site collection storage limits](https://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits).</span></span>
  
## <a name="add-storage-to-your-subscription"></a><span data-ttu-id="c74d5-140">Opslagruimte aan uw abonnement toevoegen</span><span class="sxs-lookup"><span data-stu-id="c74d5-140">Add storage to your subscription</span></span>

<span data-ttu-id="c74d5-141">Als u nog geen extra opslagruimte voor uw abonnement hebt gekocht, kunt u dat doen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-141">If you haven't yet purchased extra storage for your subscription, you can do that.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c74d5-142">Ga in het Beheercentrum naar de pagina Services voor het kopen van **facturen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> .</span><span class="sxs-lookup"><span data-stu-id="c74d5-142">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>
2. <span data-ttu-id="c74d5-143">Selecteer **invoegtoepassingen**onder aan de pagina **Services aanschaffen** .</span><span class="sxs-lookup"><span data-stu-id="c74d5-143">At the bottom of the **Purchase services** page, select **Add-ons**.</span></span>
3. <span data-ttu-id="c74d5-144">Selecteer **Office 365 extra bestandsopslag**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-144">Select **Office 365 Extra File Storage**.</span></span>
4. <span data-ttu-id="c74d5-145">Kies op de pagina **Office 365 extra bestandsopslag** , indien weergegeven, het basisabonnement en voer vervolgens het aantal GB opslagruimte in dat u wilt toevoegen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-145">On the **Office 365 Extra File Storage** page, if shown, choose the base subscription, then enter the number of gigabytes of storage you want to add.</span></span>
5. <span data-ttu-id="c74d5-146">Selecteer **nu uitchecken**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-146">Select **Check out now**.</span></span>
6. <span data-ttu-id="c74d5-147">Controleer op de pagina **Hoe ziet dit eruit?** hoeveel GB opslagruimte u hebt geselecteerd, Controleer de prijsgegevens en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-147">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>
7. <span data-ttu-id="c74d5-148">Controleer het totaal op de pagina **bestelling voltooien** .</span><span class="sxs-lookup"><span data-stu-id="c74d5-148">On the **Complete order** page, verify the total.</span></span> <span data-ttu-id="c74d5-149">Als u wijzigingen wilt aanbrengen, selecteert u **bestelling bewerken**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-149">If you need to make any changes, select **Edit order**.</span></span> <span data-ttu-id="c74d5-150">Als voor de bestelling een kredietcontrole is vereist, schakelt u het selectievakje in.</span><span class="sxs-lookup"><span data-stu-id="c74d5-150">If the order requires a credit check, select the check box.</span></span> <span data-ttu-id="c74d5-151">Wanneer u klaar bent, selecteert u **bestelling plaatsen** \> **Ga naar startpagina voor beheerders**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-151">When you're finished, select **Place order** \> **Go to Admin Home**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c74d5-152">Ga in het Beheercentrum naar de pagina **facturerings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">abonnementen</a> .  </span><span class="sxs-lookup"><span data-stu-id="c74d5-152">In the admin center, go to the **Billing** \>  <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c74d5-153">Kies op de pagina **abonnementen** het abonnement waaraan u opslagruimte wilt toevoegen en selecteer vervolgens **invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-153">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c74d5-155">Als u **invoegtoepassingen**niet ziet en uw abonnement is aangeschaft via een partner, selecteert u **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-155">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c74d5-156">Selecteer **invoegtoepassingen kopen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-156">Select **Buy add-ons**.</span></span>

    ![Koppeling invoegtoepassingen aanschaffen op de pagina Abonnementen van het Beheercentrum.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c74d5-158">Ga naar de pagina **Services aanschaffen** of tik op **Office 365 extra bestandsopslag**en selecteer vervolgens **Nu kopen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-158">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c74d5-159">Voer het aantal benodigde gebruikerslicenties in dat u nodig hebt en kies een basisabonnement, indien weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c74d5-159">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c74d5-160">Selecteer **nu uitchecken**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-160">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c74d5-161">Controleer op de pagina **Hoe ziet dit eruit?** hoeveel GB opslagruimte u hebt geselecteerd, Controleer de prijsgegevens en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-161">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c74d5-162">Selecteer **bestelling plaatsen**op de pagina **bestelling voltooien** .</span><span class="sxs-lookup"><span data-stu-id="c74d5-162">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c74d5-163">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="c74d5-163">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c74d5-164">Kies op de pagina **abonnementen** het abonnement waaraan u opslagruimte wilt toevoegen en selecteer vervolgens **invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-164">On the **Subscriptions** page, choose the subscription to which  you want to add storage space, then select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c74d5-166">Als u **invoegtoepassingen**niet ziet en uw abonnement is aangeschaft via een partner, selecteert u **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-166">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c74d5-167">Selecteer **invoegtoepassingen kopen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-167">Select **Buy add-ons**.</span></span>

    ![Koppeling invoegtoepassingen aanschaffen op de pagina Abonnementen van het Beheercentrum.](../media/f5cbc3fa-90f7-4299-976d-2482f2c69755.png)
  
4. <span data-ttu-id="c74d5-169">Ga naar de pagina **Services aanschaffen** of tik op **Office 365 extra bestandsopslag**en selecteer vervolgens **Nu kopen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-169">On the **Purchase services** page, mouse over or tap **Office 365 Extra File Storage**, then select **Buy now**.</span></span>
  
5. <span data-ttu-id="c74d5-170">Voer het aantal benodigde gebruikerslicenties in dat u nodig hebt en kies een basisabonnement, indien weergegeven.</span><span class="sxs-lookup"><span data-stu-id="c74d5-170">Enter the number of user licenses that you need and, if shown, choose a base subscription.</span></span> <span data-ttu-id="c74d5-171">Selecteer **nu uitchecken**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-171">Select **Check out now**.</span></span>
  
6. <span data-ttu-id="c74d5-172">Controleer op de pagina **Hoe ziet dit eruit?** hoeveel GB opslagruimte u hebt geselecteerd, Controleer de prijsgegevens en selecteer **volgende**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-172">On the **How does this look?** page, verify the number of gigabytes of storage you selected, review the pricing information, and then select **Next**.</span></span>

7. <span data-ttu-id="c74d5-173">Selecteer **bestelling plaatsen**op de pagina **bestelling voltooien** .</span><span class="sxs-lookup"><span data-stu-id="c74d5-173">On the **Complete order** page, select **Place order**.</span></span>

::: moniker-end

## <a name="increase-or-decrease-storage"></a><span data-ttu-id="c74d5-174">Opslagruimte vergroten of verkleinen</span><span class="sxs-lookup"><span data-stu-id="c74d5-174">Increase or decrease storage</span></span>

<span data-ttu-id="c74d5-175">Als u al extra opslagruimte hebt aangeschaft via de invoegtoepassing **Office 365 extra bestandsopslag** , kunt u deze stappen gebruiken om de opslagruimte voor uw abonnement groter of kleiner te maken.</span><span class="sxs-lookup"><span data-stu-id="c74d5-175">If you have already purchased extra file storage via the **Office 365 Extra File Storage** add-on, you can use these steps to increase or decrease the extra storage space for your subscription.</span></span> <span data-ttu-id="c74d5-176">U kunt de opslag tot slechts 1 GB verminderen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-176">You can reduce the storage to as low as 1 gigabyte.</span></span> <span data-ttu-id="c74d5-177">[Neem contact op met de ondersteuning](../admin/contact-support-for-business-products.md)om alle extra opslagruimte te verwijderen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-177">To remove all of the extra storage space, [contact support](../admin/contact-support-for-business-products.md).</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c74d5-178">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="c74d5-178">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="c74d5-179">Selecteer op het tabblad **Products** het abonnement dat de invoegtoepassing **Office 365 extra bestandsopslag** bevat.</span><span class="sxs-lookup"><span data-stu-id="c74d5-179">On the **Products** tab, select the subscription that contains the **Office 365 Extra File Storage** add-on.</span></span>
3. <span data-ttu-id="c74d5-180">Selecteer op de pagina productdetails, in de sectie **invoegtoepassingen** , **Invoegtoepassingen beheren**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-180">On the product details page, in the **Add-ons** section, select **Manage add-ons**.</span></span>
4. <span data-ttu-id="c74d5-181">In het deelvenster **Invoegtoepassingen beheren** kiest u in de lijst met **invoeg** toepassingen de optie **Office 365 extra bestandsopslag**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-181">In the **Manage add-ons** pane, from the **Add-on** list, choose **Office 365 Extra File Storage**.</span></span>
5. <span data-ttu-id="c74d5-182">Voer in het tekstvak **hoeveelheid** het gewenste aantal opslagruimte voor het abonnement in.</span><span class="sxs-lookup"><span data-stu-id="c74d5-182">In the **Quantity** text box, enter the number of GBs of storage space that you want for the subscription.</span></span>
6. <span data-ttu-id="c74d5-183">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-183">Select **Save**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c74d5-184">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="c74d5-184">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c74d5-185">Selecteer op de pagina **abonnementen** de optie **invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-185">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c74d5-187">Als u **invoegtoepassingen**niet ziet en uw abonnement is aangeschaft via een partner, selecteert u **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-187">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c74d5-188">Selecteer onder **Office 365 extra bestandsopslag**de optie **aantal wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-188">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Koppeling voor Aantal wijzigen.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c74d5-190">Voer in het rechterdeelvenster het totale aantal gigabytes in dat u nodig hebt, en selecteer vervolgens **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-190">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c74d5-191">Als u bijvoorbeeld momenteel 200 GB extra opslagruimte hebt, maar slechts 100 gigabyte nodig hebt, typt u **100** in het vak.</span><span class="sxs-lookup"><span data-stu-id="c74d5-191">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c74d5-192">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-192">Select **Close**.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c74d5-193">Ga in het beheercentrum naar de pagina **Facturering**\><a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="c74d5-193">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Subscriptions</a> page.</span></span>

2. <span data-ttu-id="c74d5-194">Selecteer op de pagina **abonnementen** de optie **invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-194">On the **Subscriptions** page, select **Add-ons**.</span></span>

    ![Add-ons button used to purchase add-ons.](../media/b4d2beb4-4f6d-435a-b127-01ceebd6eebf.png)
  
    > [!NOTE]
    > <span data-ttu-id="c74d5-196">Als u **invoegtoepassingen**niet ziet en uw abonnement is aangeschaft via een partner, selecteert u **Volume Licensing Service Center (VLSC)**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-196">If you don't see **Add-ons**, and your subscription was purchased through a partner, select **Volume Licensing Service Center (VLSC)**.</span></span>
  
3. <span data-ttu-id="c74d5-197">Selecteer onder **Office 365 extra bestandsopslag**de optie **aantal wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-197">Under **Office 365 Extra File Storage**, select **Change quantity**.</span></span>

    ![Koppeling voor Aantal wijzigen.](../media/96473f2b-6ff6-45ec-b1a3-d7b204ac1f6e.png)
  
4. <span data-ttu-id="c74d5-199">Voer in het rechterdeelvenster het totale aantal gigabytes in dat u nodig hebt, en selecteer vervolgens **verzenden**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-199">In the right pane, enter the total number of gigabytes that you need, then select **Submit**.</span></span>

    <span data-ttu-id="c74d5-200">Als u bijvoorbeeld momenteel 200 GB extra opslagruimte hebt, maar slechts 100 gigabyte nodig hebt, typt u **100** in het vak.</span><span class="sxs-lookup"><span data-stu-id="c74d5-200">For example, if you currently have 200 gigabytes of extra file storage but you only need 100 gigabytes, then you would enter **100** in the box.</span></span>

5. <span data-ttu-id="c74d5-201">Selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="c74d5-201">Select **Close**.</span></span>

::: moniker-end

## <a name="is-my-plan-eligible-for-office-365-extra-file-storage"></a><span data-ttu-id="c74d5-202">Komt mijn abonnement in aanmerking voor Office 365 Extra Bestandsopslag?</span><span class="sxs-lookup"><span data-stu-id="c74d5-202">Is my plan eligible for Office 365 Extra File Storage?</span></span>

<span data-ttu-id="c74d5-203">Office 365 Extra Bestandsopslag is beschikbaar voor de volgende abonnementen:</span><span class="sxs-lookup"><span data-stu-id="c74d5-203">Office 365 Extra File Storage is available for the following subscriptions:</span></span>
  
- <span data-ttu-id="c74d5-204">Office 365 Enterprise E1</span><span class="sxs-lookup"><span data-stu-id="c74d5-204">Office 365 Enterprise E1</span></span>

- <span data-ttu-id="c74d5-205">Office 365 Enterprise E2</span><span class="sxs-lookup"><span data-stu-id="c74d5-205">Office 365 Enterprise E2</span></span>

- <span data-ttu-id="c74d5-206">Office 365 Enterprise E3</span><span class="sxs-lookup"><span data-stu-id="c74d5-206">Office 365 Enterprise E3</span></span>

- <span data-ttu-id="c74d5-207">Office 365 Enterprise E4</span><span class="sxs-lookup"><span data-stu-id="c74d5-207">Office 365 Enterprise E4</span></span>

- <span data-ttu-id="c74d5-208">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="c74d5-208">Office 365 Enterprise E5</span></span>

- <span data-ttu-id="c74d5-209">Office voor het web met SharePoint-abonnement 1</span><span class="sxs-lookup"><span data-stu-id="c74d5-209">Office for the web with SharePoint Plan 1</span></span>

- <span data-ttu-id="c74d5-210">Office voor het web met SharePoint-abonnement 2</span><span class="sxs-lookup"><span data-stu-id="c74d5-210">Office for the web with SharePoint Plan 2</span></span>

- <span data-ttu-id="c74d5-211">SharePoint Online, abonnement 1</span><span class="sxs-lookup"><span data-stu-id="c74d5-211">SharePoint Online Plan 1</span></span>

- <span data-ttu-id="c74d5-212">SharePoint Online, abonnement 2</span><span class="sxs-lookup"><span data-stu-id="c74d5-212">SharePoint Online Plan 2</span></span>

- <span data-ttu-id="c74d5-213">Microsoft 365 Business Basic</span><span class="sxs-lookup"><span data-stu-id="c74d5-213">Microsoft 365 Business Basic</span></span>

- <span data-ttu-id="c74d5-214">Microsoft 365 Business Standard</span><span class="sxs-lookup"><span data-stu-id="c74d5-214">Microsoft 365 Business Standard</span></span>

- <span data-ttu-id="c74d5-215">Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="c74d5-215">Microsoft 365 Business Premium</span></span>

- <span data-ttu-id="c74d5-216">Microsoft 365 E3</span><span class="sxs-lookup"><span data-stu-id="c74d5-216">Microsoft 365 E3</span></span>

- <span data-ttu-id="c74d5-217">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="c74d5-217">Microsoft 365 E5</span></span>

- <span data-ttu-id="c74d5-218">Microsoft 365 F1</span><span class="sxs-lookup"><span data-stu-id="c74d5-218">Microsoft 365 F1</span></span>

> [!NOTE]
> <span data-ttu-id="c74d5-219">Office 365 extra bestandsopslag is ook beschikbaar voor GCC-, GCC High-en DOD-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="c74d5-219">Office 365 Extra File Storage is also available for GCC, GCC High, and DOD plans.</span></span>

## <a name="related-content"></a><span data-ttu-id="c74d5-220">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="c74d5-220">Related content</span></span>

<span data-ttu-id="c74d5-221">[Limieten voor site-opslag beheren](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (artikel) </span><span class="sxs-lookup"><span data-stu-id="c74d5-221">[Manage site storage limits](ttps://docs.microsoft.com/sharepoint/manage-site-collection-storage-limits) (article)</span></span>\
<span data-ttu-id="c74d5-222">[De standaardopslagruimte voor OneDrive-gebruikers instellen](https://docs.microsoft.com/onedrive/set-default-storage-space)(artikel)</span><span class="sxs-lookup"><span data-stu-id="c74d5-222">[Set the default storage space for OneDrive users](https://docs.microsoft.com/onedrive/set-default-storage-space)(article)</span></span>
