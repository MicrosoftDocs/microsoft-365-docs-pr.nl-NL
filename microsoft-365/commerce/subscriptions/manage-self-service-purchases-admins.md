---
title: Selfservice-aankopen beheren (beheerders)
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
search.appverid:
- MET150
description: Beheerders kunnen leren hoe ze selfservice-aankopen kunnen beheren die door gebruikers in hun organisatie worden gedaan.
ms.openlocfilehash: 991dc87c40f41a6cbd2f1c08d4bc72bbb34d28f1
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44141148"
---
# <a name="manage-self-service-purchases-admin"></a><span data-ttu-id="c0422-103">Selfservice-aankopen beheren (Beheerders)</span><span class="sxs-lookup"><span data-stu-id="c0422-103">Manage self-service purchases (Admin)</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c0422-104">Het beheercentrum verandert.</span><span class="sxs-lookup"><span data-stu-id="c0422-104">The admin center is changing.</span></span> <span data-ttu-id="c0422-105">Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="c0422-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c0422-106">Als beheerder u selfservice-aankopen zien die door mensen in uw organisatie zijn gedaan.</span><span class="sxs-lookup"><span data-stu-id="c0422-106">As an admin, you can see self-service purchases made by people in your organization.</span></span> <span data-ttu-id="c0422-107">U het product, de naam van de koper, de gekochte abonnementen, de vervaldatum, de aankoopprijs en toegewezen gebruikers voor elke selfserviceaankoop bekijken.</span><span class="sxs-lookup"><span data-stu-id="c0422-107">You can see the product, purchaser name, subscriptions purchased, expiry date, purchase price, and assigned users for each self-service purchase.</span></span> <span data-ttu-id="c0422-108">Indien nodig voor uw organisatie, u self-service inkoop per product via PowerShell uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="c0422-108">If required for your organization, you can turn off self-service purchasing on a per product basis via PowerShell.</span></span> <span data-ttu-id="c0422-109">U hebt hetzelfde beleid voor gegevensbeheer en -toegang ten opzichte van producten die zijn gekocht via selfservice-aankoop of centraal.</span><span class="sxs-lookup"><span data-stu-id="c0422-109">You have the same data management and access policies over products bought through self-service purchase or centrally.</span></span>

<span data-ttu-id="c0422-110">U ook bepalen of gebruikers in uw organisatie zelfservice-aankopen kunnen doen.</span><span class="sxs-lookup"><span data-stu-id="c0422-110">You can also control whether users in your organization can make self-service purchases.</span></span> <span data-ttu-id="c0422-111">Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module voor](allowselfservicepurchase-powershell.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c0422-111">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="view-self-service-subscriptions"></a><span data-ttu-id="c0422-112">Selfservice-abonnementen weergeven</span><span class="sxs-lookup"><span data-stu-id="c0422-112">View self-service subscriptions</span></span>

1. <span data-ttu-id="c0422-113">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a></span><span class="sxs-lookup"><span data-stu-id="c0422-113">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>

2. <span data-ttu-id="c0422-114">Kies naast **Resultaten verfijnen**in de vervolgkeuzelijst **Accounttype** de optie **Selfservice**.</span><span class="sxs-lookup"><span data-stu-id="c0422-114">Next to **Refine results**, from the **Account type** drop-down, choose **Self-service**.</span></span>

3. <span data-ttu-id="c0422-115">Als u meer details over een abonnement wilt bekijken, kiest u er een in de lijst.</span><span class="sxs-lookup"><span data-stu-id="c0422-115">To view more details about a subscription, choose one from the list.</span></span>

## <a name="view-who-has-licenses-for-a-self-service-purchase-subscription"></a><span data-ttu-id="c0422-116">Zien wie licenties heeft voor een abonnement op selfservice-aankoop</span><span class="sxs-lookup"><span data-stu-id="c0422-116">View who has licenses for a self-service purchase subscription</span></span>

1. <span data-ttu-id="c0422-117">Ga in het beheercentrum naar de pagina **Factureringslicenties.** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a></span><span class="sxs-lookup"><span data-stu-id="c0422-117">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

2. <span data-ttu-id="c0422-118">Kies het filterpictogram en kies **Self-service**.</span><span class="sxs-lookup"><span data-stu-id="c0422-118">Choose the filter icon, then choose **Self-service**.</span></span>

3. <span data-ttu-id="c0422-119">Selecteer een product om licenties te zien die aan mensen zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="c0422-119">Select a product to see licenses assigned to people.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0422-120">Als er meerdere aankopen voor een product zijn, wordt dat product slechts één keer vermeld en wordt in de kolom **Beschikbare hoeveelheid** het totaal van alle abonnementen weergegeven die voor dat product zijn gekocht.</span><span class="sxs-lookup"><span data-stu-id="c0422-120">If there are multiple purchases for a product, that product is only listed once, and the **Available quantity** column shows the total of all subscriptions bought for that product.</span></span>

4. <span data-ttu-id="c0422-121">De lijst **Gebruikers** wordt gegroepeerd op de namen van mensen die selfservice-aankopen hebben gedaan.</span><span class="sxs-lookup"><span data-stu-id="c0422-121">The **Users** list is grouped by the names of people who made self-service purchases.</span></span>

5. <span data-ttu-id="c0422-122">Als u een lijst met gebruikers met licenties voor deze abonnementen wilt exporteren, kiest u de abonnementen die u wilt exporteren en kiest u **Gebruikers exporteren**.</span><span class="sxs-lookup"><span data-stu-id="c0422-122">To export a list of users with licenses for these subscriptions, choose the subscriptions that you want to export, then choose **Export users**.</span></span>

## <a name="disable-or-enable-self-service-purchases"></a><span data-ttu-id="c0422-123">Selfservice-aankopen uitschakelen of inschakelen</span><span class="sxs-lookup"><span data-stu-id="c0422-123">Disable or enable self-service purchases</span></span>

<span data-ttu-id="c0422-124">U selfservice-aankopen voor gebruikers in uw organisatie uitschakelen of inschakelen.</span><span class="sxs-lookup"><span data-stu-id="c0422-124">You can disable or enable self-service purchases for users in your organization.</span></span> <span data-ttu-id="c0422-125">De **MSCommerce** PowerShell-module bevat een **PolicyID-parameterwaarde** voor **AllowSelfServicePurchase** waarmee u bepalen of gebruikers in uw organisatie selfservice-aankopen kunnen doen en voor welke producten.</span><span class="sxs-lookup"><span data-stu-id="c0422-125">The **MSCommerce** PowerShell module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases, and for which products.</span></span>

<span data-ttu-id="c0422-126">U de **MSCommerce** PowerShell-module gebruiken om:</span><span class="sxs-lookup"><span data-stu-id="c0422-126">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="c0422-127">De standaardstatus van de parameter **AllowSelfServicePurchase** &mdash; weergeven, ongeacht of deze is ingeschakeld of uitgeschakeld per product</span><span class="sxs-lookup"><span data-stu-id="c0422-127">View the default state of the **AllowSelfServicePurchase** parameter value &mdash; whether it's enabled or disabled by product</span></span>
- <span data-ttu-id="c0422-128">Bekijk een lijst met toepasselijke producten en of selfservice-aankoop is ingeschakeld of uitgeschakeld</span><span class="sxs-lookup"><span data-stu-id="c0422-128">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="c0422-129">De huidige instelling voor een specifiek product weergeven of wijzigen om het in te schakelen of uit te schakelen</span><span class="sxs-lookup"><span data-stu-id="c0422-129">View or modify the current setting for a specific product to either enable or disable it</span></span>

<span data-ttu-id="c0422-130">Zie [AllowSelfServicePurchase gebruiken voor de MSCommerce PowerShell-module voor](allowselfservicepurchase-powershell.md)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="c0422-130">For more information, see [Use AllowSelfServicePurchase for the MSCommerce PowerShell module](allowselfservicepurchase-powershell.md).</span></span>

## <a name="centralize-licenses-under-a-single-subscription"></a><span data-ttu-id="c0422-131">Licenties centraliseren onder één abonnement</span><span class="sxs-lookup"><span data-stu-id="c0422-131">Centralize licenses under a single subscription</span></span>

<span data-ttu-id="c0422-132">U bestaande licenties toewijzen of aanvullende abonnementen aanschaffen via bestaande overeenkomsten voor gebruikers die zijn toegewezen aan selfservice-aankopen.</span><span class="sxs-lookup"><span data-stu-id="c0422-132">You can assign existing licenses or purchase additional subscriptions through existing agreements for users assigned to self-service purchases.</span></span> <span data-ttu-id="c0422-133">Nadat u deze centraal aangeschafte licenties hebt toegewezen, u kopers vragen hun bestaande abonnementen op te zeggen.</span><span class="sxs-lookup"><span data-stu-id="c0422-133">After you assign these centrally purchased licenses, you can request that purchasers cancel their existing subscriptions.</span></span>

1. <span data-ttu-id="c0422-134">Meld u aan bij het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum</a> met uw globale beheerder- of factureringsbeheeraccount.</span><span class="sxs-lookup"><span data-stu-id="c0422-134">Sign in to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a> with your Global admin or Billing admin account.</span></span>

2. <span data-ttu-id="c0422-135">Ga naar de pagina<a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Services voor factureringsaankopen.</a> **Billing** > </span><span class="sxs-lookup"><span data-stu-id="c0422-135">Go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">Purchase services</a> page.</span></span>

3. <span data-ttu-id="c0422-136">Zoek en kies het product dat u wilt kopen en kies **kopen**.</span><span class="sxs-lookup"><span data-stu-id="c0422-136">Find and choose the product that you want to buy, then choose **Buy**.</span></span>

4. <span data-ttu-id="c0422-137">Voer de resterende stappen uit om uw aankoop te voltooien.</span><span class="sxs-lookup"><span data-stu-id="c0422-137">Complete the remaining steps to complete your purchase.</span></span>

5. <span data-ttu-id="c0422-138">Volg de stappen in [Weergave met licenties voor een selfservicegekocht abonnement](#view-who-has-licenses-for-a-self-service-purchase-subscription) om een lijst met gebruikers te exporteren om te verwijzen in stap 6.</span><span class="sxs-lookup"><span data-stu-id="c0422-138">Follow the steps in [View who has licenses for a self-service purchased subscription](#view-who-has-licenses-for-a-self-service-purchase-subscription) to export a list of users to reference in step 6.</span></span>

6. <span data-ttu-id="c0422-139">Licenties toewijzen aan iedereen die een licentie heeft in het andere abonnement.</span><span class="sxs-lookup"><span data-stu-id="c0422-139">Assign licenses to everyone who has a license in the other subscription.</span></span> <span data-ttu-id="c0422-140">Zie [Licenties toewijzen aan gebruikers voor](../../admin/manage/assign-licenses-to-users.md)volledige stappen.</span><span class="sxs-lookup"><span data-stu-id="c0422-140">For full steps, see [Assign licenses to users](../../admin/manage/assign-licenses-to-users.md).</span></span>

7. <span data-ttu-id="c0422-141">Neem contact op met de persoon die het abonnement voor selfservice-aankopen heeft gekocht en vraag hem of zij het abonnement op te zeggen.</span><span class="sxs-lookup"><span data-stu-id="c0422-141">Contact the person who bought the self-service purchase subscription and ask them to cancel it.</span></span>

## <a name="need-help-contact-us"></a><span data-ttu-id="c0422-142">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="c0422-142">Need help?</span></span> <span data-ttu-id="c0422-143">Neem contact met ons op.</span><span class="sxs-lookup"><span data-stu-id="c0422-143">Contact us.</span></span>

<span data-ttu-id="c0422-144">Zie Veelgestelde vragen over [selfservice-aankopen](self-service-purchase-faq.md)voor veelgestelde vragen over selfservice-aankopen.</span><span class="sxs-lookup"><span data-stu-id="c0422-144">For common questions about self-service purchases, see [Self-service purchases FAQ](self-service-purchase-faq.md).</span></span>

<span data-ttu-id="c0422-145">Als u vragen hebt of hulp nodig hebt bij selfservice-aankopen, neemt u [contact op met de ondersteuning.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="c0422-145">If you have questions or need help with self-service purchases, [contact support](../../admin/contact-support-for-business-products.md).</span></span>
