---
title: Upgrade naar Microsoft 365 Business vanaf Office 365 Business Premium
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
ms.openlocfilehash: f3a25746cf123fa471c29084a62a6fcfc1542a02
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/11/2019
ms.locfileid: "38231406"
---
# <a name="upgrade-to-microsoft-365-business-from-office-365-business-premium"></a><span data-ttu-id="21451-103">Upgrade naar Microsoft 365 Business vanaf Office 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="21451-103">Upgrade to Microsoft 365 Business from Office 365 Business Premium</span></span>

<span data-ttu-id="21451-104">Als u een [abonnement op office 365 voor bedrijven](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2)hebt, bijvoorbeeld Office 365 Business Premium, u eenvoudig upgraden naar microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="21451-104">If you have an [Office 365 for business subscription](https://products.office.com/compare-all-microsoft-office-products-4-column?activetab=tab:primaryr2), for example, Office 365 Business Premium, you can easily upgrade to Microsoft 365 Business.</span></span> <span data-ttu-id="21451-105">Upgrade naar Microsoft 365 Business als u wilt toevoegen:</span><span class="sxs-lookup"><span data-stu-id="21451-105">Upgrade to Microsoft 365 Business if you want to add:</span></span> 
- <span data-ttu-id="21451-106">Windows 10 Pro (naar Pc's met Windows 8 of hoger)</span><span class="sxs-lookup"><span data-stu-id="21451-106">Windows 10 Pro (to PCs running Windows 8 or later)</span></span>
- <span data-ttu-id="21451-107">Eenvoudige besturingselementen waarmee bedrijfsgegevens op apparaten worden beheerd</span><span class="sxs-lookup"><span data-stu-id="21451-107">Simple controls that manage business data on devices</span></span>
- <span data-ttu-id="21451-108">Geavanceerde beveiligingsmogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="21451-108">Advanced security capabilities.</span></span>
<span data-ttu-id="21451-109">Lees meer over Microsoft 365 Business op [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span><span class="sxs-lookup"><span data-stu-id="21451-109">Find out more about Microsoft 365 Business at [Microsoft.com](https://www.microsoft.com/microsoft-365/business)</span></span>

## <a name="whats-the-difference-between-office-365-business-premium-and-microsoft-365-business"></a><span data-ttu-id="21451-110">Wat is het verschil tussen Office 365 Business Premium en Microsoft 365 Business?</span><span class="sxs-lookup"><span data-stu-id="21451-110">What's the difference between Office 365 Business Premium and Microsoft 365 Business?</span></span>
<span data-ttu-id="21451-111">We hebben een side-by-side vergelijking van deze twee plannen toegevoegd aan de [Microsoft 365 Business servicebeschrijving](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span><span class="sxs-lookup"><span data-stu-id="21451-111">We've added a side-by-side comparison of these two plans to the [Microsoft 365 Business service description](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-business-service-description).</span></span> 

## <a name="before-you-get-started"></a><span data-ttu-id="21451-112">Voordat u aan de slag gaat</span><span class="sxs-lookup"><span data-stu-id="21451-112">Before you get started</span></span>

- <span data-ttu-id="21451-113">**Wanneer moet ik een upgrade kiezen?**</span><span class="sxs-lookup"><span data-stu-id="21451-113">**When should I choose upgrade?**</span></span> <span data-ttu-id="21451-114">Upgrade is de juiste keuze wanneer u wilt upgraden van **alle gebruikers** die zijn toegewezen aan een enkel abonnement.</span><span class="sxs-lookup"><span data-stu-id="21451-114">Upgrade is the right choice when you want to upgrade **all users** assigned to a single plan.</span></span> <span data-ttu-id="21451-115">Wanneer u kiest voor upgrade, worden alle gebruikers van het abonnement op hetzelfde moment overgeschakeld naar een ander abonnement.</span><span class="sxs-lookup"><span data-stu-id="21451-115">When you choose upgrade, all plan users get switched to another plan at the same time.</span></span> <span data-ttu-id="21451-116">Als u niet wilt upgraden van iedereen die is toegewezen aan een enkel abonnement, licenties voor het nieuwe abonnement kopen (in dit geval Microsoft 365 Business) en [deze licenties afzonderlijk toewijzen](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) aan elke gebruiker die u wilt upgraden.</span><span class="sxs-lookup"><span data-stu-id="21451-116">If you don't want to upgrade everyone assigned to a single plan, buy licenses for the new plan (in this case Microsoft 365 Business), and [assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users) to each user that you want to upgrade.</span></span> 
- <span data-ttu-id="21451-117">**Sommige invoegtoepassingen kunnen de upgrade verhinderen** Als u probeert een upgrade te starten en u hebt een invoeg versie die verhindert dat u doorgaat, u eerst de add-on verwijderen en deze later opnieuw toevoegen-als u deze nog nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="21451-117">**Some add-ons might prevent upgrade** If you try to start an upgrade and you have an add-on that prevents you from continuing, you can remove the add-on first, and then add it back later - if you still need it.</span></span> 
- <span data-ttu-id="21451-118">**Als u uw abonnement vooruitbetaald** Er is geen eenvoudig upgradepad voor vooruitbetaalde plannen.</span><span class="sxs-lookup"><span data-stu-id="21451-118">**If you prepaid your plan** There isn't a straightforward upgrade path for prepaid plans.</span></span> <span data-ttu-id="21451-119">U weet of u een prepaid-abonnement hebt omdat u uw abonnement hebt ingesteld met behulp van een product-ID die u mogelijk in een winkel hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="21451-119">You'll know if you have a prepaid plan because you set up your plan using a product ID that you might have purchased in a store.</span></span> <span data-ttu-id="21451-120">Neem contact op met een partner, ga naar de Microsoft Store of wacht tot uw prepaid-abonnement verloopt om over te schakelen naar een nieuw abonnement.</span><span class="sxs-lookup"><span data-stu-id="21451-120">Contact a partner, go to the Microsoft store, or wait until your prepaid plan expires to switch to a new plan.</span></span>

## <a name="upgrade-to-microsoft-365-business"></a><span data-ttu-id="21451-121">Upgrade naar Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="21451-121">Upgrade to Microsoft 365 Business</span></span>
<span data-ttu-id="21451-122">Koop uw licenties door deze stappen te volgen in het [nieuwe Admin Center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span><span class="sxs-lookup"><span data-stu-id="21451-122">Buy your licenses by following these steps in the [new admin center](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview):</span></span>
1. <span data-ttu-id="21451-123">Meld u aan bij het admin <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>Center op.</span><span class="sxs-lookup"><span data-stu-id="21451-123">Sign into the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a>.</span></span>
2. <span data-ttu-id="21451-124">Ga naar het navigatiedeelvenster en selecteer **facturerings** \> **producten & Services**.</span><span class="sxs-lookup"><span data-stu-id="21451-124">Go to the navigation pane and select **Billing** \> **Products & Services**.</span></span> <span data-ttu-id="21451-125">Zoek uw abonnement op Office 365 en selecteer het om de details weer te geven.</span><span class="sxs-lookup"><span data-stu-id="21451-125">Find your Office 365 subscription and select it to view the details.</span></span> 

    ![Een schermafbeelding laat zien hoe u uw abonnement vinden en selecteren in het Admin Center.](media/FindYourSubscription.png)

3. <span data-ttu-id="21451-127">Selecteer op de volgende pagina de optie **upgrade**.</span><span class="sxs-lookup"><span data-stu-id="21451-127">On the next page, select **Upgrade**.</span></span> 

      ![Een screenshot laat zien waar te selecteren upgrade in het Admin Center.](media/SelectUpgrade.png)

  > [!NOTE]
  > <span data-ttu-id="21451-129">Als u een bericht dat ' upgraden van uw abonnement wordt niet ondersteund met groepslicenties in azure Active Directory ' ziet, u dit veilig negeren, tenzij u een zeer grote organisatie hebt.</span><span class="sxs-lookup"><span data-stu-id="21451-129">If you see a message that says "Upgrading your subscription is not supported with group-based licensing in Azure Active Directory", you can safely ignore this unless you have a very large organization.</span></span> <span data-ttu-id="21451-130">Organisaties die deze optie hebben geselecteerd, zijn zich ervan bewust dat ze op groepen gebaseerde licenties gebruiken.</span><span class="sxs-lookup"><span data-stu-id="21451-130">Organizations who have selected this option will be aware that they're using group-based licensing.</span></span>

4. <span data-ttu-id="21451-131">Vervolgens u een lijst weergeven met Office-abonnementen waarop u een upgrade uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="21451-131">Next, you can view a list of Office plans that you can upgrade to.</span></span> <span data-ttu-id="21451-132">Zoek in dit geval het Microsoft 365 business plan.</span><span class="sxs-lookup"><span data-stu-id="21451-132">In this case, find the Microsoft 365 Business plan.</span></span> <span data-ttu-id="21451-133">U naar beneden scrollen als u wilt zien van alle Office-apps en services die zijn opgenomen in dit plan.</span><span class="sxs-lookup"><span data-stu-id="21451-133">You can scroll down if you want to see all the Office apps and services that are included with this plan.</span></span> <span data-ttu-id="21451-134">Selecteer onder **Microsoft 365 Business**de optie **upgrade** om Microsoft 365 Business aan uw winkelwagentje toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="21451-134">Under **Microsoft 365 Business**, select **Upgrade** to add Microsoft 365 Business to your cart.</span></span>
5. <span data-ttu-id="21451-135">In de winkelwagen:</span><span class="sxs-lookup"><span data-stu-id="21451-135">In the cart:</span></span>
    1. <span data-ttu-id="21451-136">We nemen automatisch licenties op voor al uw huidige gebruikers in het winkelwagentje.</span><span class="sxs-lookup"><span data-stu-id="21451-136">We'll automatically include licenses for all your current users to the cart.</span></span> <span data-ttu-id="21451-137">Als u meer of minder licenties nodig hebt, moet u [deze licenties afzonderlijk aanschaffen en toewijzen](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="21451-137">If you need more, or less licenses, you'll need to [buy and assign those licenses individually](https://docs.microsoft.com/office365/admin/manage/assign-licenses-to-users).</span></span>  
    2. <span data-ttu-id="21451-138">U aanpassen hoe u wilt betalen-maandelijks of jaarlijks.</span><span class="sxs-lookup"><span data-stu-id="21451-138">You can adjust how you'd like to pay - monthly or yearly.</span></span> <span data-ttu-id="21451-139">Selecteer het vervolgkeuzemenu om uw keuze te maken.</span><span class="sxs-lookup"><span data-stu-id="21451-139">Select the drop-down menu to make your choice.</span></span>
6. <span data-ttu-id="21451-140">Selecteer **Ga naar afhandeling** waar je een overzicht van je aankoop ziet, inclusief de betalingsmethode voor dit account.</span><span class="sxs-lookup"><span data-stu-id="21451-140">Select **Go to Checkout** where you'll see a summary of your purchase, including the payment method for this account.</span></span> <span data-ttu-id="21451-141">U hier ook een promo code toevoegen als u er een hebt.</span><span class="sxs-lookup"><span data-stu-id="21451-141">You can also add a promo code here if you have one.</span></span>
7. <span data-ttu-id="21451-142">Selecteer **bestelling plaatsen** om uw aankoop te voltooien.</span><span class="sxs-lookup"><span data-stu-id="21451-142">Select **Place order** to complete your purchase.</span></span>
<span data-ttu-id="21451-143">Het duurt enkele minuten voordat Microsoft uw nieuwe service plannen instelt.</span><span class="sxs-lookup"><span data-stu-id="21451-143">It takes Microsoft a few minutes to set up your new service plans.</span></span> <span data-ttu-id="21451-144">Als u de voortgang wilt controleren, selecteert u **Upgradestatus controleren**.</span><span class="sxs-lookup"><span data-stu-id="21451-144">To check on progress, select **Check upgrade status**.</span></span> 
1. <span data-ttu-id="21451-145">Zodra uw plan gereed is, moet u mogelijk enkele extra stappen in het Beheercentrum uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="21451-145">Once your plan is ready, you might need to complete some additional setup steps in the admin center.</span></span> <span data-ttu-id="21451-146">Selecteer in het navigatiedeelvenster **Home** om eventuele aanvullende instellingsstappen te voltooien.</span><span class="sxs-lookup"><span data-stu-id="21451-146">In the navigation pane, select **Home** to complete any additional setup steps.</span></span>

> [!NOTE]
> <span data-ttu-id="21451-147">U ontvangt een pro rata restitutie voor de Ofifce 365-licenties die u niet meer nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="21451-147">You'll receive a prorated refund for the Ofifce 365 licenses that you no longer need.</span></span> <span data-ttu-id="21451-148">Uw bankrekening of creditcard wordt ongeveer twee dagen na het instellen van het nieuwe abonnement in rekening gebracht.</span><span class="sxs-lookup"><span data-stu-id="21451-148">Your bank account or credit card will be charged about two days after you set up the new plan.</span></span>
  
## <a name="protect-user-devices-and-files"></a><span data-ttu-id="21451-149">Gebruikers apparaten en bestanden beveiligen</span><span class="sxs-lookup"><span data-stu-id="21451-149">Protect user devices and files</span></span>

<span data-ttu-id="21451-150">Nu dat Microsoft 365 Business-licenties zijn toegewezen, voltooit u de stappen om te beginnen met het beveiligen van apparaten en bestanden.</span><span class="sxs-lookup"><span data-stu-id="21451-150">Now that Microsoft 365 Business licenses have been assigned, complete steps to start protecting devices and files.</span></span> <span data-ttu-id="21451-151">U gebruikt enkele nieuwe opties die zijn opgenomen in het navigatiedeelvenster Admin Center.</span><span class="sxs-lookup"><span data-stu-id="21451-151">You'll be using some new options included in the admin center navigation pane.</span></span>
  
1. <span data-ttu-id="21451-152">In het Beheercentrum, in het navigatiedeelvenster, gaat u naar **apparaten** \> **beleid**.</span><span class="sxs-lookup"><span data-stu-id="21451-152">In the admin center, in the navigation pane, go to **Devices** \> **Policies**.</span></span>
    
2. <span data-ttu-id="21451-153">Selecteer op de pagina **apparaatbeleid** de optie **toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="21451-153">On the **Device policies** page, select **Add**.</span></span>
    
3. <span data-ttu-id="21451-154">Geef in het deelvenster **beleid toevoegen** het beleid een naam (bijvoorbeeld werkbestanden beveiligen) en kies vervolgens een **beleidstype** in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="21451-154">In the **Add policy** pane give the policy a name (for example, Protect work files), and then choose a **Policy type** from the drop-down.</span></span> 
    
    <span data-ttu-id="21451-155">U toepassingsbeleid instellen voor het beveiligen van bestanden op Android-en iPhone-apparaten, evenals Windows 10, en u apparaatconfiguratiebeleid instellen voor Windows 10-apparaten die eigendom zijn van het bedrijf.</span><span class="sxs-lookup"><span data-stu-id="21451-155">You can set up application policies for protecting files on Android and iPhone devices, as well as Windows 10, and you can set up device configuration policies for company owned Windows 10 devices.</span></span> <span data-ttu-id="21451-156">Zie de volgende koppelingen voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="21451-156">See the following links for details:</span></span>
    
  - [<span data-ttu-id="21451-157">Instellingen voor app-beveiliging instellen voor Android- of iOS-apparaten</span><span class="sxs-lookup"><span data-stu-id="21451-157">Set app protection settings for Android or iOS devices</span></span>](app-protection-settings-for-android-and-ios.md)
    
  - [<span data-ttu-id="21451-158">Instellingen voor toepassingsbeveiliging instellen voor Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="21451-158">Set application protection settings for Windows 10 devices</span></span>](protection-settings-for-windows-10-devices.md)
    
  - [<span data-ttu-id="21451-159">Instellingen voor apparaatbeveiliging instellen voor Windows 10-Pc's</span><span class="sxs-lookup"><span data-stu-id="21451-159">Set device protection settings for Windows 10 PCs</span></span>](protection-settings-for-windows-10-pcs.md)
    
  
4. <span data-ttu-id="21451-160">Nadat u beleid hebt ingesteld, kunnen u en uw werknemers apparaten instellen:</span><span class="sxs-lookup"><span data-stu-id="21451-160">After you set up policies, you and your employees can set up devices:</span></span>
    
  - <span data-ttu-id="21451-161">Als uw Windows-apparaten de Windows Pro Creator-update nog niet gebruiken, moet u [ze upgraden naar Windows Pro Creators update](upgrade-to-windows-pro-creators-update.md).</span><span class="sxs-lookup"><span data-stu-id="21451-161">If your Windows devices aren't already using the Windows Pro Creator update, you'll need to [upgrade them to Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).</span></span>
    
  - <span data-ttu-id="21451-162">Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md) voor stappen voor Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="21451-162">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for steps for Windows devices.</span></span> 
    
  - <span data-ttu-id="21451-163">Zie [mobiele apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-mobile-devices.md) voor stappen voor Android-telefoons en iPhones.</span><span class="sxs-lookup"><span data-stu-id="21451-163">See [Set up mobile devices for Microsoft 365 Business users](set-up-mobile-devices.md) for steps for Android phones and iPhones.</span></span> 



