---
title: Een domein verwijderen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Meer informatie over het verwijderen van een oud domein uit Microsoft 365 en het verplaatsen van gebruikers en groepen naar een ander domein.
ms.openlocfilehash: ef0209d6ccb7534745172585fe599f627e386cb4
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140403"
---
# <a name="remove-a-domain"></a><span data-ttu-id="3ff26-103">Een domein verwijderen</span><span class="sxs-lookup"><span data-stu-id="3ff26-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3ff26-104">Het beheercentrum verandert.</span><span class="sxs-lookup"><span data-stu-id="3ff26-104">The admin center is changing.</span></span> <span data-ttu-id="3ff26-105">Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="3ff26-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="3ff26-106">**[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt.</span><span class="sxs-lookup"><span data-stu-id="3ff26-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="3ff26-107">Verwijdert u uw domein omdat u het wilt toevoegen aan een ander Microsoft 365-abonnement?</span><span class="sxs-lookup"><span data-stu-id="3ff26-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="3ff26-108">Of wilt u uw abonnement gewoon opzeggen?</span><span class="sxs-lookup"><span data-stu-id="3ff26-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="3ff26-109">U kunt [uw abonnement wijzigen](../../commerce/subscriptions/switch-to-a-different-plan.md) of [uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="3ff26-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="3ff26-110">Stap 1: Gebruikers verplaatsen naar een ander domein</span><span class="sxs-lookup"><span data-stu-id="3ff26-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="3ff26-111">Gebruikers verplaatsen</span><span class="sxs-lookup"><span data-stu-id="3ff26-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3ff26-112">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="3ff26-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="3ff26-113">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="3ff26-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="3ff26-114">Selecteer **Gebruikers** > **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="3ff26-115">Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="3ff26-116">Selecteer **Meer opties** (**...**) boven aan de pagina en kies Domeinen **wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="3ff26-117">Selecteer **in** het deelvenster Domeinen wijzigen een ander domein.</span><span class="sxs-lookup"><span data-stu-id="3ff26-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="3ff26-p103">U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="3ff26-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3ff26-120">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="3ff26-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="3ff26-121">Selecteer **Gebruikers** > **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="3ff26-122">Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="3ff26-123">Kies boven aan de pagina **Meer** > **bewerkingsdomeinen**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="3ff26-124">Selecteer in het deelvenster **Domeinen bewerken** een ander domein.</span><span class="sxs-lookup"><span data-stu-id="3ff26-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="3ff26-p104">U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="3ff26-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3ff26-127">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="3ff26-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="3ff26-128">Selecteer **Gebruikers** > **actieve gebruikers**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="3ff26-129">Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="3ff26-130">Kies boven aan de pagina **Meer** > **bewerkingsdomeinen**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="3ff26-131">Selecteer in het deelvenster **Domeinen bewerken** een ander domein.</span><span class="sxs-lookup"><span data-stu-id="3ff26-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="3ff26-p105">U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.</span><span class="sxs-lookup"><span data-stu-id="3ff26-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="3ff26-134">Beweeg jezelf</span><span class="sxs-lookup"><span data-stu-id="3ff26-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3ff26-135">Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.</span><span class="sxs-lookup"><span data-stu-id="3ff26-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="3ff26-136">Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>.</span><span class="sxs-lookup"><span data-stu-id="3ff26-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="3ff26-137">Ga naar **Gebruikers** \> **actieve gebruikers**en selecteer uw account in de lijst.</span><span class="sxs-lookup"><span data-stu-id="3ff26-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="3ff26-138">Selecteer op het tabblad **Account** de optie **Gebruikersnaam beheren**en kies vervolgens een ander domein.</span><span class="sxs-lookup"><span data-stu-id="3ff26-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="3ff26-139">Selecteer bovenaan uw accountnaam en selecteer **Afmelden.**</span><span class="sxs-lookup"><span data-stu-id="3ff26-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="3ff26-140">Meld u aan met het nieuwe domein en hetzelfde wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="3ff26-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="3ff26-141">U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein.</span><span class="sxs-lookup"><span data-stu-id="3ff26-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="3ff26-142">Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3ff26-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="3ff26-143">Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3ff26-144">Ga naar **Gebruikers** \> **actieve gebruikers**en selecteer uw naam in de lijst.</span><span class="sxs-lookup"><span data-stu-id="3ff26-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="3ff26-145">**Selecteer**bewerken en kies vervolgens een ander domein in de sectie Gebruikersnaam **/ e-mail.**</span><span class="sxs-lookup"><span data-stu-id="3ff26-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="3ff26-146">Selecteer **Instellen als primaire** > **Afsluiting** > **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="3ff26-147">Selecteer bovenaan uw accountnaam en selecteer **Afmelden.**</span><span class="sxs-lookup"><span data-stu-id="3ff26-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="3ff26-148">Meld u aan met het nieuwe domein en hetzelfde wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="3ff26-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="3ff26-149">U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein.</span><span class="sxs-lookup"><span data-stu-id="3ff26-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="3ff26-150">Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3ff26-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="3ff26-151">Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3ff26-152">Ga naar **Gebruikers** \> **actieve gebruikers**en selecteer uw naam in de lijst.</span><span class="sxs-lookup"><span data-stu-id="3ff26-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="3ff26-153">**Selecteer**bewerken en kies vervolgens een ander domein in de sectie Gebruikersnaam **/ e-mail.**</span><span class="sxs-lookup"><span data-stu-id="3ff26-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="3ff26-154">Selecteer **Instellen als primaire** > **Afsluiting** > **opslaan**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="3ff26-155">Selecteer bovenaan uw accountnaam en selecteer **Afmelden.**</span><span class="sxs-lookup"><span data-stu-id="3ff26-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="3ff26-156">Meld u aan met het nieuwe domein en hetzelfde wachtwoord.</span><span class="sxs-lookup"><span data-stu-id="3ff26-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="3ff26-157">U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein.</span><span class="sxs-lookup"><span data-stu-id="3ff26-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="3ff26-158">Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3ff26-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="3ff26-159">Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="3ff26-160">Stap 2: Groepen naar een ander domein verplaatsen</span><span class="sxs-lookup"><span data-stu-id="3ff26-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3ff26-161">Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">groepen.</a></span><span class="sxs-lookup"><span data-stu-id="3ff26-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="3ff26-162">Selecteer de groepsnaam en selecteer vervolgens op het tabblad **Algemeen** onder **E-mailadres Primair ,** Selecteer **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="3ff26-163">Gebruik de vervolgkeuzelijst om een ander domein te kiezen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="3ff26-164">Selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="3ff26-165">Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3ff26-166">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>naar de pagina **Groepen** > **groepen.**</span><span class="sxs-lookup"><span data-stu-id="3ff26-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="3ff26-167">Selecteer de groepsnaam en selecteer **Bewerken** naast **Naam**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="3ff26-168">Gebruik de vervolgkeuzelijst om een ander domein te kiezen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="3ff26-169">Selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="3ff26-170">Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3ff26-171">Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>naar de pagina **Groepen** > **groepen.**</span><span class="sxs-lookup"><span data-stu-id="3ff26-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="3ff26-172">Selecteer de groepsnaam en selecteer **Bewerken** naast **Naam**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="3ff26-173">Gebruik de vervolgkeuzelijst om een ander domein te kiezen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="3ff26-174">Selecteer **Opslaan** en vervolgens **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="3ff26-175">Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="3ff26-176">Stap 3: Het oude domein verwijderen</span><span class="sxs-lookup"><span data-stu-id="3ff26-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="3ff26-177">Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.</span><span class="sxs-lookup"><span data-stu-id="3ff26-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="3ff26-178">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Setup-domeinen.</a> **Setup**</span><span class="sxs-lookup"><span data-stu-id="3ff26-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="3ff26-179">Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Setup-domeinen.</a> **Setup**</span><span class="sxs-lookup"><span data-stu-id="3ff26-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="3ff26-180">Selecteer **op** de pagina Domeinen het domein dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="3ff26-181">Selecteer **Verwijderen**in het rechterdeelvenster .</span><span class="sxs-lookup"><span data-stu-id="3ff26-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="3ff26-182">Volg eventuele aanvullende aanwijzingen en selecteer **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="3ff26-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="3ff26-183">Hoe lang duurt het voordat een domein is verwijderd?</span><span class="sxs-lookup"><span data-stu-id="3ff26-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="3ff26-184">Het kan slechts 5 minuten duren voordat Microsoft 365 een domein verwijdert als er niet naar wordt verwezen op veel plaatsen, zoals beveiligingsgroepen, distributielijsten, gebruikers en Microsoft 365-groepen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="3ff26-185">Als er veel verwijzingen zijn waarin het domein wordt gebruikt, kan het enkele uren (een dag) duren voordat het domein is verwijderd.</span><span class="sxs-lookup"><span data-stu-id="3ff26-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="3ff26-p113">Als u honderden of duizenden gebruikers hebt, gebruikt u PowerShell om alle gebruikers te zoeken en ze vervolgens naar een ander domein te verplaatsen. Anders is het mogelijk dat een klein aantal gebruikers in de UI over het hoofd wordt gezien. Wanneer u het domein vervolgens wilt verwijderen, lukt dit niet en weet u niet waarom. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="3ff26-190">Nog steeds hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="3ff26-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="3ff26-191">U kunt het ['.onmicrosoft.com'](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)-domein niet uit uw account verwijderen.</span><span class="sxs-lookup"><span data-stu-id="3ff26-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="3ff26-p114">Werkt het nog steeds niet? Uw domein moet mogelijk handmatig worden verwijderd. [Bel ons gerust](../contact-support-for-business-products.md). We helpen u graag.</span><span class="sxs-lookup"><span data-stu-id="3ff26-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="3ff26-195">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="3ff26-195">Related articles</span></span>

[<span data-ttu-id="3ff26-196">Veelgestelde vragen over domeinen</span><span class="sxs-lookup"><span data-stu-id="3ff26-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="3ff26-197">Hulp krijgen bij Office 365-domeinen</span><span class="sxs-lookup"><span data-stu-id="3ff26-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="3ff26-198">Overstappen op een ander Microsoft 365 voor Bedrijven-abonnement</span><span class="sxs-lookup"><span data-stu-id="3ff26-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="3ff26-199">Uw abonnement opzeggen</span><span class="sxs-lookup"><span data-stu-id="3ff26-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
