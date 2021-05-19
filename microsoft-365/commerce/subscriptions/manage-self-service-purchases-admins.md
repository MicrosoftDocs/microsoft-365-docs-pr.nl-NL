---
title: Selfservice-aankopen beheren (beheerders)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- okr_smb
- commerce_ssp
search.appverid:
- MET150
description: Beheerders kunnen leren hoe ze selfservice-aankopen van gebruikers in hun organisatie kunnen beheren.
ms.date: 03/26/2021
ms.openlocfilehash: a4ac4b79a9a73f80fc22e6f14696e25925df9faf
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536092"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="4d177-103">Selfservice-aankopen beheren (Beheerders)</span><span class="sxs-lookup"><span data-stu-id="4d177-103">Manage self-service purchases (Admin)</span></span>

<span data-ttu-id="4d177-104">Als beheerder kunt u selfserviceaankopen zien die zijn gedaan door personen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4d177-104">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="4d177-105">U ziet de productnaam, de naam van de inkoper, de gekochte abonnementen, de vervaldatum, de aankoopprijs en de toegewezen gebruikers voor elke selfserviceaankoop.</span><span class="sxs-lookup"><span data-stu-id="4d177-105">You see the product name, purchaser name, subscriptions purchased, expiration date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="4d177-106">Indien vereist door uw organisatie, kunt u de selfservice-aankoop per product uitschakelen via PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d177-106">If required by your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="4d177-107">U hebt hetzelfde gegevensbeheer- en toegangsbeleid voor producten die zijn gekocht via selfserviceaankoop of centraal.</span><span class="sxs-lookup"><span data-stu-id="4d177-107">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="4d177-108">U kunt ook bepalen of gebruikers in uw organisatie selfserviceaankopen kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="4d177-108">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="4d177-109">Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4d177-109">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="4d177-110">Selfservice-abonnementen weergeven</span><span class="sxs-lookup"><span data-stu-id="4d177-110">View self-service subscriptions</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d177-111">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d177-112">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-112">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d177-113">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-113">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end

2. <span data-ttu-id="4d177-114">Selecteer op **het** tabblad Producten het filterpictogram en selecteer **vervolgens Selfservice.**</span><span class="sxs-lookup"><span data-stu-id="4d177-114">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="4d177-115">Als u meer informatie over een abonnement wilt bekijken, kiest u er een in de lijst.</span><span class="sxs-lookup"><span data-stu-id="4d177-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="4d177-116">Bekijken wie licenties heeft voor een selfservice-aankoopabonnement</span><span class="sxs-lookup"><span data-stu-id="4d177-116">View who has licenses for a self-service purchase subscription</span></span>

> [!NOTE]
> <span data-ttu-id="4d177-117">Als beheerder kunt u geen licenties toewijzen of verwijderen voor een self-service aankoopabonnement dat door een gebruiker in uw organisatie is gekocht.</span><span class="sxs-lookup"><span data-stu-id="4d177-117">As an admin, you can't assign or unassign licenses for a self-service purchase subscription bought by a user in your organization.</span></span> <span data-ttu-id="4d177-118">U kunt [self-service aankoopabonnementen overnemen](#take-over-a-self-service-purchase-subscription)en vervolgens licenties toewijzen of opheffen.</span><span class="sxs-lookup"><span data-stu-id="4d177-118">You can [take over a self-service purchase subscription](#take-over-a-self-service-purchase-subscription), and then assign or unassign licenses.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d177-119">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-119">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

 1. <span data-ttu-id="4d177-120">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

 1. <span data-ttu-id="4d177-121">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenties</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-121">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

2. <span data-ttu-id="4d177-122">Selecteer het filterpictogram en kies **vervolgens Selfservice.**</span><span class="sxs-lookup"><span data-stu-id="4d177-122">Select the filter icon, then choose **Self-service**.</span></span>
3. <span data-ttu-id="4d177-123">Selecteer een product om licenties te zien die aan personen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="4d177-123">Select a product to see licenses assigned to people.</span></span>
    > [!NOTE]
    > <span data-ttu-id="4d177-124">Als er meerdere aankopen voor een product zijn, wordt dat  product slechts één keer weergegeven en wordt in de kolom Beschikbare hoeveelheid het totaal weergegeven van alle abonnementen die voor dat product zijn gekocht.</span><span class="sxs-lookup"><span data-stu-id="4d177-124">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>
4. <span data-ttu-id="4d177-125">De **lijst** Gebruikers wordt gegroepeerd op de namen van personen die selfserviceaankopen hebben gedaan.</span><span class="sxs-lookup"><span data-stu-id="4d177-125">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>
5. <span data-ttu-id="4d177-126">Als u een lijst met gebruikers met licenties voor deze abonnementen wilt exporteren, kiest u de abonnementen die u wilt exporteren en kiest u **Vervolgens Gebruikers exporteren.**</span><span class="sxs-lookup"><span data-stu-id="4d177-126">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="4d177-127">Selfservice-aankopen uitschakelen of inschakelen</span><span class="sxs-lookup"><span data-stu-id="4d177-127">Disable or enable self-service purchases</span></span>

<span data-ttu-id="4d177-128">U kunt selfservice-aankopen uitschakelen of inschakelen voor gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4d177-128">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="4d177-129">De **MSCommerce** PowerShell-module bevat een **Beleids-id-parameterwaarde** voor **AllowSelfServicePurchase** waarmee u kunt bepalen of gebruikers in uw organisatie selfserviceaankopen kunnen doen en voor welke producten.</span><span class="sxs-lookup"><span data-stu-id="4d177-129">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="4d177-130">U kunt de **MSCommerce** PowerShell-module gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="4d177-130">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="4d177-131">De standaardtoestand van de **parameterwaarde AllowSelfServicePurchase** weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld per product</span><span class="sxs-lookup"><span data-stu-id="4d177-131">View the default state of the **AllowSelfServicePurchase** parameter value—whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="4d177-132">Een lijst met toepasselijke producten weergeven en controleren of selfserviceaankoop is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="4d177-132">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="4d177-133">De huidige instelling voor een specifiek product weergeven of wijzigen om het in of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="4d177-133">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="4d177-134">Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module](allowselfservicepurchase-powershell.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="4d177-134">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="4d177-135">Licenties centraliseren onder één abonnement</span><span class="sxs-lookup"><span data-stu-id="4d177-135">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="4d177-136">U kunt bestaande licenties toewijzen of extra abonnementen kopen via bestaande overeenkomsten voor gebruikers die zijn toegewezen aan selfserviceaankopen.</span><span class="sxs-lookup"><span data-stu-id="4d177-136">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="4d177-137">Nadat u deze centraal aangeschafte licenties hebt toegewezen, kunt u inkopers verzoeken hun bestaande abonnementen op te zeggen.</span><span class="sxs-lookup"><span data-stu-id="4d177-137">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d177-138">Ga in het beheercentrum naar de pagina  > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Factureringsaankoopservices.</a></span><span class="sxs-lookup"><span data-stu-id="4d177-138">In the admin center go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d177-139">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">het beheercentrum</a>naar de pagina **Factureringsaankoopservices.** > </span><span class="sxs-lookup"><span data-stu-id="4d177-139">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d177-140">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">het beheercentrum</a>naar de pagina **Factureringsaankoopservices.** > </span><span class="sxs-lookup"><span data-stu-id="4d177-140">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Purchase services** page.</span></span>

::: moniker-end

2. <span data-ttu-id="4d177-141">Zoek en kies het product dat u wilt kopen en kies vervolgens **Kopen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-141">Find and choose the product that you want to buy, then choose **Buy**.</span></span>
3. <span data-ttu-id="4d177-142">Voltooi de resterende stappen om uw aankoop te voltooien.</span><span class="sxs-lookup"><span data-stu-id="4d177-142">Complete the remaining steps to complete your purchase.</span></span>
4. <span data-ttu-id="4d177-143">Volg de stappen in Bekijk wie [er licenties](#view-who-has-licenses-for-a-self-service-purchase-subscription) heeft voor een zelf aangeschaft abonnement om een lijst met gebruikers te exporteren waarnaar wordt verwezen in de volgende stap.</span><span class="sxs-lookup"><span data-stu-id="4d177-143">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in the next step.</span></span>
5. <span data-ttu-id="4d177-144">Wijs licenties toe aan iedereen met een licentie in het andere abonnement.</span><span class="sxs-lookup"><span data-stu-id="4d177-144">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="4d177-145">Zie Licenties toewijzen aan gebruikers voor volledige [stappen.](../../admin/manage/assign-licenses-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="4d177-145">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>
6. <span data-ttu-id="4d177-146">Neem contact op met de persoon die het selfservice-aankoopabonnement heeft gekocht en vraag hem of haar om [het abonnement op te zeggen.](manage-self-service-purchases-users.md#cancel-a-subscription)</span><span class="sxs-lookup"><span data-stu-id="4d177-146">Contact the person who bought the self-service purchase subscription and ask them to [cancel it](manage-self-service-purchases-users.md#cancel-a-subscription).</span></span>

## <a name="take-over-a-self-service-purchase-subscription"></a><span data-ttu-id="4d177-147">Een selfservice-aankoopabonnement overnemen</span><span class="sxs-lookup"><span data-stu-id="4d177-147">Take over a self-service purchase subscription</span></span>

<span data-ttu-id="4d177-148">U kunt een selfservice-aankoopabonnement overnemen dat is gemaakt door een gebruiker in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="4d177-148">You can take over a self-service purchase subscription made by a user in your organization.</span></span> <span data-ttu-id="4d177-149">Wanneer u een selfservice-aankoopabonnement over neemt, hebt u twee opties:</span><span class="sxs-lookup"><span data-stu-id="4d177-149">When you take over a self-service purchase subscription, you have two options:</span></span>

1. <span data-ttu-id="4d177-150">Verplaats de gebruikers naar een ander abonnement en annuleer het oorspronkelijke abonnement.</span><span class="sxs-lookup"><span data-stu-id="4d177-150">Move the users to a different subscription and cancel the original subscription.</span></span>
2. <span data-ttu-id="4d177-151">Annuleer het selfservice-aankoopabonnement en verwijder licenties van toegewezen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="4d177-151">Cancel the self-service purchase subscription and remove licenses from assigned users.</span></span>

### <a name="move-users-to-a-different-subscription"></a><span data-ttu-id="4d177-152">Gebruikers naar een ander abonnement overzetten</span><span class="sxs-lookup"><span data-stu-id="4d177-152">Move users to a different subscription</span></span>

<span data-ttu-id="4d177-153">Wanneer u gebruikers naar een ander abonnement verplaatst, wordt het oude abonnement automatisch geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="4d177-153">When you move users to a different subscription, the old subscription is automatically canceled.</span></span> <span data-ttu-id="4d177-154">De gebruiker die het selfservice-aankoopabonnement oorspronkelijk heeft gekocht, ontvangt een e-mail met de informatie dat het abonnement is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="4d177-154">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

> [!NOTE]
> <span data-ttu-id="4d177-155">U moet een beschikbare licentie hebben voor elke gebruiker die u verplaatst in het abonnement waar u gebruikers naar verplaatst.</span><span class="sxs-lookup"><span data-stu-id="4d177-155">You must have an available license for each user you’re moving in the subscription that you’re moving users to.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d177-156">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d177-157">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">het beheercentrum</a>naar de **pagina Facturering** van > **uw producten.**</span><span class="sxs-lookup"><span data-stu-id="4d177-157">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d177-158">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">het beheercentrum</a>naar de **pagina Facturering** van > **uw producten.**</span><span class="sxs-lookup"><span data-stu-id="4d177-158">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="4d177-159">Selecteer op **het** tabblad Producten het filterpictogram en selecteer **vervolgens Selfservice.**</span><span class="sxs-lookup"><span data-stu-id="4d177-159">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="4d177-160">Selecteer het abonnement dat u wilt overnemen.</span><span class="sxs-lookup"><span data-stu-id="4d177-160">Select the subscription that you want to take over.</span></span>
4. <span data-ttu-id="4d177-161">Selecteer op de pagina **abonnementsgegevens** in de sectie Abonnementen en instellingen de optie **Beheer van dit abonnement nemen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-161">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="4d177-162">Selecteer in het rechterdeelvenster **Gebruikers verplaatsen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-162">In the right pane, select **Move users**.</span></span>
6. <span data-ttu-id="4d177-163">Selecteer het product waar u de gebruikers naar wilt verplaatsen en selecteer **vervolgens Gebruikers verplaatsen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-163">Select the product that you want to move the users to, then select **Move users**.</span></span>
7. <span data-ttu-id="4d177-164">Selecteer in **het vak Gebruikers verplaatsen** naar de optie Gebruikers **verplaatsen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-164">In the **Move users to** box, select **Move users**.</span></span> <span data-ttu-id="4d177-165">Het verplaatsen kan enkele minuten duren.</span><span class="sxs-lookup"><span data-stu-id="4d177-165">The move process might take several minutes.</span></span> <span data-ttu-id="4d177-166">Sluit uw browser niet terwijl het proces wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="4d177-166">Don’t close your browser while the process runs.</span></span>
8. <span data-ttu-id="4d177-167">Wanneer het verhuisproces is voltooid, sluit u het **deelvenster Voltooid verplaatsen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-167">When the move process is finished, close the **Move completed pane**.</span></span>
9. <span data-ttu-id="4d177-168">Op de pagina Met abonnementsgegevens wordt de **abonnementsstatus** voor het zelf aangeschafte abonnement weergegeven als **Verwijderd.**</span><span class="sxs-lookup"><span data-stu-id="4d177-168">On the subscription details page, the **Subscription status** for the self-service purchased subscription shows as **Deleted**.</span></span>

### <a name="cancel-a-self-service-purchase-subscription"></a><span data-ttu-id="4d177-169">Een selfservice-aankoopabonnement opzeggen</span><span class="sxs-lookup"><span data-stu-id="4d177-169">Cancel a self-service purchase subscription</span></span>

<span data-ttu-id="4d177-170">Wanneer u ervoor kiest om een selfservice-aankoopabonnement op te zeggen, hebben gebruikers met licenties geen toegang meer tot het product.</span><span class="sxs-lookup"><span data-stu-id="4d177-170">When you choose to cancel a self-service purchase subscription, users with licenses lose access to the product.</span></span> <span data-ttu-id="4d177-171">De gebruiker die het selfservice-aankoopabonnement oorspronkelijk heeft gekocht, ontvangt een e-mail met de informatie dat het abonnement is geannuleerd.</span><span class="sxs-lookup"><span data-stu-id="4d177-171">The user who originally bought the self-service purchase subscription receives an email that says the subscription was canceled.</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="4d177-172">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="4d177-172">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="4d177-173">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">het beheercentrum</a>naar de **pagina Facturering** van > **uw producten.**</span><span class="sxs-lookup"><span data-stu-id="4d177-173">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="4d177-174">Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">het beheercentrum</a>naar de **pagina Facturering** van > **uw producten.**</span><span class="sxs-lookup"><span data-stu-id="4d177-174">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>, go to the **Billing** > **Your products** page.</span></span>

::: moniker-end

2. <span data-ttu-id="4d177-175">Selecteer op **het** tabblad Producten het filterpictogram en selecteer **vervolgens Selfservice.**</span><span class="sxs-lookup"><span data-stu-id="4d177-175">On the **Products** tab, select the filter icon, then select **Self-service**.</span></span>
3. <span data-ttu-id="4d177-176">Selecteer het abonnement dat u wilt opzeggen.</span><span class="sxs-lookup"><span data-stu-id="4d177-176">Select the subscription that you want to cancel.</span></span>
4. <span data-ttu-id="4d177-177">Selecteer op de pagina **abonnementsgegevens** in de sectie Abonnementen en instellingen de optie **Beheer van dit abonnement nemen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-177">On the subscription details page, in the **Subscriptions and settings** section, select **Take control of this subscription**.</span></span>
5. <span data-ttu-id="4d177-178">Selecteer in het rechterdeelvenster **Abonnement opzeggen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-178">In the right pane, select **Cancel subscription**.</span></span>
6. <span data-ttu-id="4d177-179">Selecteer een reden voor uw annulering in de vervolgkeuzelijst en selecteer vervolgens **Abonnement annuleren.**</span><span class="sxs-lookup"><span data-stu-id="4d177-179">Select a reason for your cancellation from the drop-down list, then select **Cancel subscription**.</span></span>
7. <span data-ttu-id="4d177-180">Selecteer in **het vak Weet u zeker dat u wilt opzeggen?** de optie Abonnement **opzeggen.**</span><span class="sxs-lookup"><span data-stu-id="4d177-180">In the **Are you sure you want to cancel?** box, select **Cancel subscription**.</span></span>
8. <span data-ttu-id="4d177-181">Sluit het rechterdeelvenster.</span><span class="sxs-lookup"><span data-stu-id="4d177-181">Close the right pane.</span></span>
9. <span data-ttu-id="4d177-182">Op de pagina abonnementsgegevens wordt de **abonnementsstatus** weergegeven **als Verwijderd.**</span><span class="sxs-lookup"><span data-stu-id="4d177-182">On the subscription details page, the **Subscription status** shows as **Deleted**.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="4d177-183">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="4d177-183">Need help?</span></span> <span data-ttu-id="4d177-184">Neem contact met ons op.</span><span class="sxs-lookup"><span data-stu-id="4d177-184">Contact us.</span></span>

<span data-ttu-id="4d177-185">Zie Veelgestelde vragen over selfservice-aankopen voor veelgestelde vragen over [selfserviceaankopen.](self-service-purchase-faq.yml)</span><span class="sxs-lookup"><span data-stu-id="4d177-185">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.yml).</span></span>

<span data-ttu-id="4d177-186">Als u vragen hebt of hulp nodig hebt bij selfserviceaankopen, [neem dan contact op met ondersteuning.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="4d177-186">If you have questions or need help with self-service purchases, [contact support](../../business-video/get-help-support.md).</span></span>
