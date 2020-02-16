---
title: Upgraden naar Microsoft 365 Business vanuit Office 365 Business Premium
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Stappen die uw bedrijf upgraden van Office 365 Business Premium naar Microsoft 365 Business.
ms.openlocfilehash: e17ac2658c7276ba4a77de371847343866815c42
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42065264"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="934df-103">Upgraden naar Microsoft 365 Business vanuit Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="934df-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="934df-104">Als u een [abonnement op Office 365 voor Bedrijven](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)hebt, bijvoorbeeld Office 365 Business Premium, u eenvoudig upgraden naar Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="934df-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="934df-105">Upgrade naar Microsoft 365 Business als u het:</span><span class="sxs-lookup"><span data-stu-id="934df-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="934df-106">Windows 10 Pro (naar pc's met Windows 8 of hoger)</span><span class="sxs-lookup"><span data-stu-id="934df-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="934df-107">Eenvoudige besturingselementen die bedrijfsgegevens op apparaten beheren</span><span class="sxs-lookup"><span data-stu-id="934df-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="934df-108">Geavanceerde beveiligingsmogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="934df-108">Advanced security capabilities.</span></span>
<span data-ttu-id="934df-109">Meer informatie over Microsoft 365 Business op [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="934df-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="934df-110">Wat is het verschil tussen Office 365 Business Premium en Microsoft 365 Business?</span><span class="sxs-lookup"><span data-stu-id="934df-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="934df-111">We hebben een vergelijking naast elkaar van deze twee abonnementen toegevoegd aan de [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span><span class="sxs-lookup"><span data-stu-id="934df-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business Service Description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="934df-112">Voordat u aan de slag gaat</span><span class="sxs-lookup"><span data-stu-id="934df-112">Before you get started</span></span>

- <span data-ttu-id="934df-113">**Wanneer moet ik ervoor kiezen om te upgraden?**</span><span class="sxs-lookup"><span data-stu-id="934df-113">**When should I choose to upgrade?**</span></span> <span data-ttu-id="934df-114">Upgraden is de juiste keuze wanneer u **alle gebruikers** wilt upgraden die aan één abonnement zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="934df-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="934df-115">Wanneer u voor een upgrade kiest, worden alle abonnementsgebruikers tegelijkertijd overgeschakeld naar een ander abonnement.</span><span class="sxs-lookup"><span data-stu-id="934df-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="934df-116">Als u niet iedereen wilt upgraden die aan één abonnement is toegewezen, koopt u licenties voor het nieuwe abonnement (in dit geval Microsoft 365 Business) en wijst u [deze licenties afzonderlijk toe](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) aan elke gebruiker die u wilt upgraden.</span><span class="sxs-lookup"><span data-stu-id="934df-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="934df-117">**Sommige add-ons kunnen de upgrade voorkomen** Als u een upgrade probeert te starten en u een add-on hebt die voorkomt dat u doorgaat, u de add-on eerst verwijderen en deze later weer toevoegen als u deze nog nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="934df-117">**Some add-ons might prevent the upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later if you still need it.</span></span> 
- <span data-ttu-id="934df-118">**Als u uw abonnement hebt betaald** Er is geen eenvoudig upgradepad voor prepaidabonnementen.</span><span class="sxs-lookup"><span data-stu-id="934df-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="934df-119">U weet of u een prepaidabonnement hebt omdat u uw abonnement hebt ingesteld met een product-id die u mogelijk in een winkel hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="934df-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="934df-120">Neem contact op met een partner, ga naar de Microsoft Store of wacht tot uw prepaidabonnement verloopt om over te schakelen naar een nieuw abonnement.</span><span class="sxs-lookup"><span data-stu-id="934df-120">Contact a partner, go to the Microsoft Store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="934df-121">Upgraden naar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="934df-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="934df-122">Koop uw licenties door deze stappen te volgen in het [nieuwe beheercentrum:](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)</span><span class="sxs-lookup"><span data-stu-id="934df-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="934df-123">Meld u aan <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>bij het beheercentrum bij .</span><span class="sxs-lookup"><span data-stu-id="934df-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="934df-124">Ga naar het navigatiedeelvenster en selecteer \> **Factureringsproducten & Services**. \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="934df-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="934df-125">Zoek uw Office 365-abonnement en selecteer het om de details te bekijken.</span><span class="sxs-lookup"><span data-stu-id="934df-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![Op een schermafbeelding is te zien hoe u uw abonnement vinden en selecteren in het beheercentrum.](../media/FindYourSubscription.png)

3. <span data-ttu-id="934df-127">Selecteer op de volgende pagina **Upgraden**.</span><span class="sxs-lookup"><span data-stu-id="934df-127">On the next page, select **Upgrade**.</span></span> 

      ![Op een schermafbeelding ziet u waar u Upgraden in het beheercentrum selecteren.](../media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="934df-129">Als u een bericht ziet waarin staat dat het upgraden van **uw abonnement niet wordt ondersteund met groepslicenties in Azure Active Directory,** u dit veilig negeren, tenzij u een zeer grote organisatie hebt.</span><span class="sxs-lookup"><span data-stu-id="934df-129">If you see a message that says **Upgrading your subscription is not supported with group-based licensing in Azure Active Directory**, you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="934df-130">Organisaties die deze optie hebben geselecteerd, zijn zich ervan bewust dat ze groepslicenties gebruiken.</span><span class="sxs-lookup"><span data-stu-id="934df-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="934df-131">Vervolgens u een lijst met Office-abonnementen weergeven waarnaar u upgraden.</span><span class="sxs-lookup"><span data-stu-id="934df-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="934df-132">Zoek in dit geval het Microsoft 365 Business-abonnement.</span><span class="sxs-lookup"><span data-stu-id="934df-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="934df-133">U omlaag scrollen als u alle Office-apps en -services wilt zien die bij dit abonnement zijn inbegrepen.</span><span class="sxs-lookup"><span data-stu-id="934df-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="934df-134">Selecteer onder **Microsoft 365 Business**de optie **Upgraden** om Microsoft 365 Business aan uw winkelwagentje toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="934df-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="934df-135">In de kar:</span><span class="sxs-lookup"><span data-stu-id="934df-135">In the cart:</span></span>
    1. <span data-ttu-id="934df-136">We nemen automatisch licenties op voor al uw huidige gebruikers.</span><span class="sxs-lookup"><span data-stu-id="934df-136">We'll automatically include licenses for all your current users.</span></span> <span data-ttu-id="934df-137">Als u meer of minder licenties nodig hebt, moet u [deze licenties afzonderlijk kopen en toewijzen.](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users)</span><span class="sxs-lookup"><span data-stu-id="934df-137">If you need more or fewer licenses, you need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="934df-138">U aanpassen hoe u wilt betalen: maandelijks of jaarlijks.</span><span class="sxs-lookup"><span data-stu-id="934df-138">You can adjust how you'd like to pay: monthly or yearly.</span></span> <span data-ttu-id="934df-139">Selecteer het vervolgkeuzemenu om uw keuze te maken.</span><span class="sxs-lookup"><span data-stu-id="934df-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="934df-140">Selecteer **Ga naar Afhandeling** waar je een overzicht van je aankoop ziet, inclusief de betalingsmethode voor dit account.</span><span class="sxs-lookup"><span data-stu-id="934df-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="934df-141">U hier ook een promocode toevoegen als u er een hebt.</span><span class="sxs-lookup"><span data-stu-id="934df-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="934df-142">Selecteer **Bestelling plaatsen** om uw aankoop te voltooien.</span><span class="sxs-lookup"><span data-stu-id="934df-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="934df-143">Het duurt Microsoft een paar minuten om uw nieuwe serviceplannen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="934df-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="934df-144">Als u de voortgang wilt controleren, selecteert u **De upgradestatus controleren**.</span><span class="sxs-lookup"><span data-stu-id="934df-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="934df-145">Zodra uw abonnement klaar is, moet u mogelijk een aantal extra installatiestappen in het beheercentrum uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="934df-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="934df-146">Selecteer In het navigatiedeelvenster de optie **Start** om eventuele extra installatiestappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="934df-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="934df-147">U ontvangt een prorata-terugbetaling voor de Office 365-licenties die u niet meer nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="934df-147">You'll receive a prorated refund for the Office 365 licenses that you no longer need.</span></span> <span data-ttu-id="934df-148">Uw bankrekening of creditcard wordt ongeveer twee dagen na het instellen van het nieuwe abonnement in rekening gebracht.</span><span class="sxs-lookup"><span data-stu-id="934df-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="934df-149">Gebruikersapparaten en bestanden beveiligen</span><span class="sxs-lookup"><span data-stu-id="934df-149">Protect user devices and files</span></span>

<span data-ttu-id="934df-150">Nu Microsoft 365 Business-licenties zijn toegewezen, voert u stappen uit om apparaten en bestanden te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="934df-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="934df-151">U gebruikt een aantal nieuwe opties in het navigatiedeelvenster van het beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="934df-151">You'll use some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="934df-152">Ga in het beheercentrum in het navigatiedeelvenster naar **Het beleid voor** **apparaten** \> .</span><span class="sxs-lookup"><span data-stu-id="934df-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="934df-153">Selecteer op de pagina **Apparaatbeleid** de optie **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="934df-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="934df-154">Geef in het **deelvenster Beleid toevoegen** het beleid een naam (bijvoorbeeld Werkbestanden beveiligen) en kies vervolgens een **beleidstype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="934df-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down list.</span></span> 
    
    <span data-ttu-id="934df-155">U toepassingsbeleid instellen voor het beveiligen van bestanden op Android- en iPhone-apparaten en Windows 10 en u apparaatconfiguratiebeleid instellen voor Windows 10-apparaten die eigendom zijn van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="934df-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="934df-156">Zie de volgende links voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="934df-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="934df-157">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="934df-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="934df-158">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="934df-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="934df-159">Apparaatbeveiligingsinstellingen instellen voor Windows 10-pc's</span><span class="sxs-lookup"><span data-stu-id="934df-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="934df-160">Nadat u beleid hebt ingesteld, kunnen u en uw medewerkers apparaten instellen:</span><span class="sxs-lookup"><span data-stu-id="934df-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="934df-161">Als uw Windows-apparaten de Windows Pro Creator-update nog niet gebruiken, moet u [deze upgraden naar Windows Pro Creators Update.](upgrade-to-windows-pro-creators-update.md)</span><span class="sxs-lookup"><span data-stu-id="934df-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="934df-162">Zie [Windows-apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="934df-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="934df-163">Zie [Mobiele apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones.</span><span class="sxs-lookup"><span data-stu-id="934df-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 
