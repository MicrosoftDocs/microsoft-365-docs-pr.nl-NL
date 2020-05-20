---
title: Betalingswijzen beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- okr_SMB
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
description: Meer informatie over het beheren van uw betalingsmethoden in het Microsoft 365-beheercentrum.
ms.openlocfilehash: d31da19c10eb61719ba813d271dbdcf573a5aff3
ms.sourcegitcommit: 5c43e89ed94ad9fd1db049446383c65e548189b7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2020
ms.locfileid: "44322157"
---
# <a name="manage-payment-methods"></a><span data-ttu-id="49819-103">Betalingswijzen beheren</span><span class="sxs-lookup"><span data-stu-id="49819-103">Manage payment methods</span></span>

::: moniker range="o365-21vianet"
> [!NOTE]
> <span data-ttu-id="49819-104">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="49819-104">The admin center is changing.</span></span> <span data-ttu-id="49819-105">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="49819-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>
::: moniker-end

<span data-ttu-id="49819-106">Wanneer u zakelijke producten of services van Microsoft koopt, u een bestaande betalingsmethode gebruiken of een nieuwe methode toevoegen.</span><span class="sxs-lookup"><span data-stu-id="49819-106">When you buy business products or services from Microsoft, you can use an existing payment method, or add a new one.</span></span> <span data-ttu-id="49819-107">U een creditcard of bankpas of bankrekening gebruiken om te betalen voor de dingen die u koopt.</span><span class="sxs-lookup"><span data-stu-id="49819-107">You can use a credit or debit card, or bank account to pay for the things you buy.</span></span>

<span data-ttu-id="49819-108">Als uw zakelijke account een factureringsprofiel heeft en u een eigenaar van het factureringsprofiel of een bijdrager voor factureringsprofielen bent, u het factureringsprofiel dat wordt ondersteund door een creditcard of factuurbetaling gebruiken om aankopen te doen of rekeningen te betalen.</span><span class="sxs-lookup"><span data-stu-id="49819-108">If your business account has a billing profile, and you are a billing profile owner or billing profile contributor, you can use the billing profile that's backed by a credit card or invoice payment to make purchases or pay bills.</span></span> <span data-ttu-id="49819-109">Als u een factuurbeheerder bent, u alleen een factureringsprofiel gebruiken om facturen te betalen.</span><span class="sxs-lookup"><span data-stu-id="49819-109">If you're a billing invoice manager, you can only use a billing profile to pay bills.</span></span> <span data-ttu-id="49819-110">Zie [Factureringsprofielen beheren](manage-billing-profiles.md)voor meer informatie over factureringsprofielen en -rollen .</span><span class="sxs-lookup"><span data-stu-id="49819-110">To learn more about billing profiles and roles, see [Manage billing profiles](manage-billing-profiles.md).</span></span>

<span data-ttu-id="49819-111">Als uw zakelijke account geen factureringsprofiel heeft, kan elke globale of factureringsbeheerder een bankrekening beheren en gebruiken die aan het zakelijke account is toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="49819-111">If your business account doesn't have a billing profile, any Global or Billing admin can manage and use any bank account that is added to the business account.</span></span> <span data-ttu-id="49819-112">U echter alleen creditcards beheren of gebruiken die u toevoegt.</span><span class="sxs-lookup"><span data-stu-id="49819-112">However, you can only manage or use credit cards that you add.</span></span>

> [!NOTE]
> <span data-ttu-id="49819-113">De optie om te betalen met een bankrekening is niet beschikbaar in sommige landen of regio's.</span><span class="sxs-lookup"><span data-stu-id="49819-113">The option to pay with a bank account is not available in some countries or regions.</span></span>
>
> <span data-ttu-id="49819-114">U moet een betalingsmethode gebruiken die is uitgegeven vanuit hetzelfde land als uw huurder.</span><span class="sxs-lookup"><span data-stu-id="49819-114">You must use a payment method issued from the same country as your tenant.</span></span>

## <a name="add-a-payment-method"></a><span data-ttu-id="49819-115">Een betalingsmethode toevoegen</span><span class="sxs-lookup"><span data-stu-id="49819-115">Add a payment method</span></span>

<span data-ttu-id="49819-116">Als u een betalingsmethode toevoegt, worden er geen abonnementen aan gekoppeld.</span><span class="sxs-lookup"><span data-stu-id="49819-116">Adding a payment method doesn't associate any subscriptions with it.</span></span> <span data-ttu-id="49819-117">Zie [Een betalingsmethode voor één abonnement wijzigen](#change-a-payment-method-for-a-single-subscription)als u één abonnement aan de betalingsmethode wilt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="49819-117">To assign a single subscription to the payment method, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span> <span data-ttu-id="49819-118">Zie Een betalingsmethode vervangen als u alle abonnementen wilt vervangen die een andere betalingsmethode gebruiken met de nieuwe [betalingsmethode.](#replace-a-payment-method)</span><span class="sxs-lookup"><span data-stu-id="49819-118">To replace all subscriptions that use another payment method with the new one, see [Replace a payment method](#replace-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="49819-119">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-119">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="49819-120">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-120">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="49819-121">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-121">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="49819-122">Selecteer **Betaalmethode toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="49819-122">Select **Add a payment method**.</span></span>

3. <span data-ttu-id="49819-123">Kies op de pagina **Betalingsmethoden** een betalingsmethode uit het vervolgkeuzemenu.</span><span class="sxs-lookup"><span data-stu-id="49819-123">On the **Payment methods** page, pick a payment method from the drop-down menu.</span></span>

4. <span data-ttu-id="49819-124">Voer de gegevens voor de nieuwe kaart of bankrekening in en selecteer **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="49819-124">Enter the information for the new card or bank account, then select **Add**.</span></span>

## <a name="update-payment-method-details"></a><span data-ttu-id="49819-125">Gegevens over betalingsmethode bijwerken</span><span class="sxs-lookup"><span data-stu-id="49819-125">Update payment method details</span></span>

<span data-ttu-id="49819-126">U de naam wijzigen op de creditcard of betaalkaart, het factuuradres of de vervaldatum van een bestaande betalingsmethode.</span><span class="sxs-lookup"><span data-stu-id="49819-126">You can change the name on the credit or debit card, billing address, or expiration date for an existing payment method.</span></span> <span data-ttu-id="49819-127">U de kaart of het rekeningnummer echter niet wijzigen.</span><span class="sxs-lookup"><span data-stu-id="49819-127">However, you can't change the card or account number.</span></span> <span data-ttu-id="49819-128">Als het rekeningnummer is gewijzigd, [vervangt u het door een andere betalingsmethode](#replace-a-payment-method)en verwijdert u het [oude](#delete-a-payment-method)nummer .</span><span class="sxs-lookup"><span data-stu-id="49819-128">If the account number has changed, [replace it with a different payment method](#replace-a-payment-method), and then [delete the old one](#delete-a-payment-method).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="49819-129">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-129">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="49819-130">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-130">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="49819-131">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-131">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="49819-132">Selecteer de rij van de betalingsmethode die u wilt bijwerken.</span><span class="sxs-lookup"><span data-stu-id="49819-132">Select the row of the payment method to update.</span></span> <span data-ttu-id="49819-133">Selecteer **bewerken**in het rechterdeelvenster .</span><span class="sxs-lookup"><span data-stu-id="49819-133">In the right pane, select **Edit**.</span></span>

3. <span data-ttu-id="49819-134">Werk uw betalingsmethodegegevens bij, inclusief de naam op de creditcard of betaalkaart, het factuuradres of de vervaldatum, en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="49819-134">Update your payment method information, including the name on the credit or debit card, billing address, or expiration date, and then select **Save**.</span></span>

## <a name="replace-a-payment-method"></a><span data-ttu-id="49819-135">Een betalingsmethode vervangen</span><span class="sxs-lookup"><span data-stu-id="49819-135">Replace a payment method</span></span>

<span data-ttu-id="49819-136">Wanneer u een betalingsmethode vervangt, vervangt u deze voor alle abonnementen en factureringsprofielen die dezelfde betalingsmethode gebruiken.</span><span class="sxs-lookup"><span data-stu-id="49819-136">When you replace a payment method, you replace it for all subscriptions and billing profiles that use the same payment method.</span></span> <span data-ttu-id="49819-137">Als u een betalingsmethode vervangt, wordt de bestaande betalingsmethode niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="49819-137">Replacing a payment method doesn't delete the existing payment method.</span></span> <span data-ttu-id="49819-138">Het is nog steeds beschikbaar voor u om te selecteren en te gebruiken voor andere abonnementen en factureringsprofielen.</span><span class="sxs-lookup"><span data-stu-id="49819-138">It's still available for you to select and use for other subscriptions and billing profiles.</span></span>

<span data-ttu-id="49819-139">Zie [Een betalingsmethode voor één abonnement wijzigen](#change-a-payment-method-for-a-single-subscription)als u de betalingsmethode voor één abonnement wilt wijzigen.</span><span class="sxs-lookup"><span data-stu-id="49819-139">To change the payment method for a single subscription, see [Change a payment method for a single subscription](#change-a-payment-method-for-a-single-subscription).</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="49819-140">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-140">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="49819-141">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-141">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="49819-142">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-142">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="49819-143">Selecteer de rij van de te vervangen betalingsmethode.</span><span class="sxs-lookup"><span data-stu-id="49819-143">Select the row of the payment method to replace.</span></span> <span data-ttu-id="49819-144">In het rechterdeelvenster worden alle factureringsprofielen en afzonderlijke abonnementen weergegeven die de geselecteerde betalingsmethode gebruiken.</span><span class="sxs-lookup"><span data-stu-id="49819-144">The right pane lists all billing profiles and individual subscriptions that use the selected payment method.</span></span>

3. <span data-ttu-id="49819-145">Selecteer in het rechterdeelvenster de optie **Betalingsmethode vervangen voor alle objecten**.</span><span class="sxs-lookup"><span data-stu-id="49819-145">In the right pane, select **Replace payment method for all items**.</span></span>

4. <span data-ttu-id="49819-146">Als u een bestaande betalingsmethode wilt gebruiken, kiest u er een in de vervolgkeuzelijst en selecteert u **Vervangen**.</span><span class="sxs-lookup"><span data-stu-id="49819-146">To use an existing payment method, choose one from the drop-down list, then select **Replace**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="49819-147">Als u abonnementen hebt die zijn gekoppeld aan een factureringsprofiel, u alleen een creditcard of betaalkaart gebruiken om ervoor te betalen.</span><span class="sxs-lookup"><span data-stu-id="49819-147">If you have subscriptions associated with a billing profile, you can only use a credit or debit card to pay for them.</span></span> <span data-ttu-id="49819-148">Als u bankrekeningen op de pagina **Betalingsmethoden** hebt vermeld, zijn deze niet beschikbaar om te selecteren in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="49819-148">If you have bank accounts listed on the **Payment methods** page, they aren't available to select in the drop-down list.</span></span>

5. <span data-ttu-id="49819-149">Als u een nieuwe betalingsmethode wilt toevoegen, selecteert u **Betalingsmethode toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="49819-149">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="49819-150">Voer **in** het deelvenster Een betalingsmethode toevoegen de accountgegevens in en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="49819-150">In the **Add a payment method** pane, enter the account information, then select **Save**.</span></span> <span data-ttu-id="49819-151">U moet een betalingsmethode uit hetzelfde land gebruiken als uw huurder.</span><span class="sxs-lookup"><span data-stu-id="49819-151">You must use a payment method from the same country as your tenant.</span></span>

7. <span data-ttu-id="49819-152">De nieuwe betalingsmethode is al geselecteerd in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="49819-152">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="49819-153">Selecteer **Vervangen**.</span><span class="sxs-lookup"><span data-stu-id="49819-153">Select **Replace**.</span></span>

## <a name="change-a-payment-method-for-a-single-subscription"></a><span data-ttu-id="49819-154">Een betalingsmethode voor één abonnement wijzigen</span><span class="sxs-lookup"><span data-stu-id="49819-154">Change a payment method for a single subscription</span></span>

<span data-ttu-id="49819-155">U de betalingsmethode wijzigen die wordt gebruikt om voor één abonnement te betalen.</span><span class="sxs-lookup"><span data-stu-id="49819-155">You can change the payment method used to pay for a single subscription.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="49819-156">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="49819-156">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="49819-157">Ga in het beheercentrum naar de pagina **Facturering** > **Mijn producten**.</span><span class="sxs-lookup"><span data-stu-id="49819-157">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="49819-158">Ga in het beheercentrum naar de pagina **Facturering** > **Mijn producten**.</span><span class="sxs-lookup"><span data-stu-id="49819-158">In the admin center, go to the **Billing** > **Your products** page.</span></span>
::: moniker-end

2. <span data-ttu-id="49819-159">Selecteer op het tabblad **Abonnementen** het abonnement waarvoor u wilt betalen met de alternatieve betalingsmethode.</span><span class="sxs-lookup"><span data-stu-id="49819-159">On the **Subscriptions** tab, select the subscription that you want to pay for with the alternate payment method.</span></span>

3. <span data-ttu-id="49819-160">Selecteer **onder Facturering**naast de betalingsmethode de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="49819-160">Under **Billing**, next to the payment method, select **Edit**.</span></span>

4. <span data-ttu-id="49819-161">Selecteer naast uw bestaande betalingsmethode **wijzigen**.</span><span class="sxs-lookup"><span data-stu-id="49819-161">Next to your existing payment method, select **Change**.</span></span>

5. <span data-ttu-id="49819-162">Kies in de vervolgkeuzelijst een alternatieve betalingsmethode of kies ervoor om een betalingsmethode toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="49819-162">From the drop-down list, choose an alternate payment method, or choose to add a payment method.</span></span>

6. <span data-ttu-id="49819-163">Als u een betalingsmethode toevoegt, voert u de kaart- of accountgegevens in en selecteert u **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="49819-163">If you add a payment method, enter the card or account details, then select **Save**.</span></span>

7. <span data-ttu-id="49819-164">Controleer of de geselecteerde betalingsmethode juist is en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="49819-164">Verify that the selected payment method is correct, then select **Save**.</span></span>

## <a name="delete-a-payment-method"></a><span data-ttu-id="49819-165">Een betalingsmethode verwijderen</span><span class="sxs-lookup"><span data-stu-id="49819-165">Delete a payment method</span></span>

<span data-ttu-id="49819-166">U alleen een betalingsmethode verwijderen die niet is gekoppeld aan een abonnement of factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="49819-166">You can only delete a payment method that isn't attached to a subscription or billing profile.</span></span> <span data-ttu-id="49819-167">Dit geldt voor alle abonnementen, ongeacht hun status.</span><span class="sxs-lookup"><span data-stu-id="49819-167">This applies to all subscriptions, whatever their status.</span></span>

### <a name="delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="49819-168">Een betalingsmethode verwijderen zonder abonnementen of factureringsprofielen</span><span class="sxs-lookup"><span data-stu-id="49819-168">Delete a payment method with no subscriptions or billing profiles attached</span></span>

<span data-ttu-id="49819-169">Als een betalingsmethode niet is gekoppeld aan abonnementen of factureringsprofielen, u deze onmiddellijk verwijderen.</span><span class="sxs-lookup"><span data-stu-id="49819-169">If a payment method isn't associated with any subscriptions or billing profiles, you can immediately delete it.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="49819-170">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-170">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="49819-171">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-171">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="49819-172">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-172">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="49819-173">Zoek de betalingsmethode die u wilt verwijderen, selecteer de drie puntjes en selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="49819-173">Find the payment method to delete, select the three dots, then select **Delete**.</span></span>

3. <span data-ttu-id="49819-174">Selecteer Onder aan het rechterdeelvenster **delete**.</span><span class="sxs-lookup"><span data-stu-id="49819-174">At the bottom of the right pane, select **Delete**.</span></span>

### <a name="delete-a-payment-method-with-subscriptions-or-billing-profiles-attached"></a><span data-ttu-id="49819-175">Een betalingsmethode verwijderen met abonnementen of factureringsprofielen eraan gekoppeld</span><span class="sxs-lookup"><span data-stu-id="49819-175">Delete a payment method with subscriptions or billing profiles attached</span></span>

<span data-ttu-id="49819-176">Als een betalingsmethode is gekoppeld aan abonnementen of factureringsprofielen, vervangt u deze eerst door een bestaande betalingsmethode of voegt u een nieuwe methode toe en verwijdert u vervolgens de oude betalingsmethode.</span><span class="sxs-lookup"><span data-stu-id="49819-176">If a payment method is attached to any subscriptions or billing profiles, first replace it with an existing payment method, or add a new one, then delete the old payment method.</span></span>

::: moniker range="o365-worldwide"
1. <span data-ttu-id="49819-177">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-177">In the admin center, go to the **Billing** > **Bills & payments** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2018806" target="_blank">Payment methods</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"
1. <span data-ttu-id="49819-178">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-178">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

::: moniker range="o365-21vianet"
1. <span data-ttu-id="49819-179">Ga in het beheercentrum naar de pagina **Betalingsmethoden** > **voor factureringsfacturen &** > **Payment methods** betalingen.</span><span class="sxs-lookup"><span data-stu-id="49819-179">In the admin center, go to the **Billing** > **Bills & payments** > **Payment methods** page.</span></span>
::: moniker-end

2. <span data-ttu-id="49819-180">Selecteer de rij voor de betalingsmethode die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="49819-180">Select the row for the payment method to delete.</span></span> <span data-ttu-id="49819-181">In het rechterdeelvenster worden bestaande abonnementen weergegeven die deze betalingsmethode gebruiken.</span><span class="sxs-lookup"><span data-stu-id="49819-181">The right pane lists existing subscriptions that use that payment method.</span></span>

3. <span data-ttu-id="49819-182">Selecteer **Verwijderen**in het rechterdeelvenster .</span><span class="sxs-lookup"><span data-stu-id="49819-182">In the right pane, select **Delete**.</span></span>

4. <span data-ttu-id="49819-183">Als u een bestaande betalingsmethode wilt gebruiken, kiest u er een in de vervolgkeuzelijst, selecteert u **Volgende**en selecteert u **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="49819-183">To use an existing payment method, choose one from the drop-down list, select **Next**, and then select **Delete**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="49819-184">Als u abonnementen hebt die zijn gekoppeld aan een factureringsprofiel, u alleen een creditcard gebruiken om ervoor te betalen.</span><span class="sxs-lookup"><span data-stu-id="49819-184">If you have subscriptions associated with a billing profile, you can only use a credit card to pay for them.</span></span> <span data-ttu-id="49819-185">Als u bankrekeningen op de pagina **Betalingsmethoden** hebt vermeld, zijn deze niet beschikbaar om te kiezen in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="49819-185">If you have bank accounts listed on the **Payment methods** page, they aren't available to choose in the drop-down list.</span></span>

5. <span data-ttu-id="49819-186">Als u een nieuwe betalingsmethode wilt toevoegen, selecteert u **Betalingsmethode toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="49819-186">To add a new payment method, select **Add payment method**.</span></span>

6. <span data-ttu-id="49819-187">Kies het type betalingsmethode dat u wilt toevoegen, voer de accountgegevens in en selecteer **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="49819-187">Choose the type of payment method that you want to add, enter the account information, and then select **Save**.</span></span>

7. <span data-ttu-id="49819-188">De nieuwe betalingsmethode is al geselecteerd in de vervolgkeuzelijst.</span><span class="sxs-lookup"><span data-stu-id="49819-188">The new payment method is already selected in the drop-down list.</span></span> <span data-ttu-id="49819-189">Selecteer **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="49819-189">Select **Next**.</span></span>

8. <span data-ttu-id="49819-190">Selecteer **Verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="49819-190">Select **Delete**.</span></span>

## <a name="troubleshoot-payment-methods"></a><span data-ttu-id="49819-191">Problemen met betalingsmethoden oplossen</span><span class="sxs-lookup"><span data-stu-id="49819-191">Troubleshoot payment methods</span></span>

|<span data-ttu-id="49819-192">**Probleem**</span><span class="sxs-lookup"><span data-stu-id="49819-192">**Issue**</span></span>|<span data-ttu-id="49819-193">**Stappen voor probleemoplossing**</span><span class="sxs-lookup"><span data-stu-id="49819-193">**Troubleshooting steps**</span></span>|
|:----------|:-----|
|<span data-ttu-id="49819-194">**Ik krijg een foutmelding met de tekst: "De browser is momenteel ingesteld om cookies te blokkeren."**</span><span class="sxs-lookup"><span data-stu-id="49819-194">**I get an error message that says, "The browser is currently set to block cookies."**</span></span> |<span data-ttu-id="49819-195">Laat uw browser cookies van derden toestaan en probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="49819-195">Set your browser to allow third-party cookies and try again.</span></span> |
|<span data-ttu-id="49819-196">**Mijn creditcard of betaalkaart is geweigerd.**</span><span class="sxs-lookup"><span data-stu-id="49819-196">**My credit or debit card was declined.**</span></span> |<span data-ttu-id="49819-197">Als u met een creditcard of betaalkaart betaalt en uw kaart wordt geweigerd, ontvangt u een e-mail met de tekst dat Microsoft de betaling niet heeft kunnen verwerken.</span><span class="sxs-lookup"><span data-stu-id="49819-197">If you pay by credit or debit card, and your card is declined, you receive an email that says Microsoft was unable to process the payment.</span></span> <span data-ttu-id="49819-198">Controleer of het &mdash; kaartnummer, de vervaldatum, de naam op de kaart en het adres, inclusief plaats, staat en postcode, &mdash; precies worden weergegeven zoals ze op de kaart en uw afschrift staan.</span><span class="sxs-lookup"><span data-stu-id="49819-198">Double-check that the card details&mdash;card number, expiration date, name on the card, and address, including city, state, and ZIP code&mdash;appear exactly as they do on the card and your statement.</span></span> <span data-ttu-id="49819-199">U uw kaartgegevens bijwerken en de betaling onmiddellijk indienen via de koppeling **Saldo vereffenen** in het gedeelte **Facturering** van de pagina met abonnementsgegevens.</span><span class="sxs-lookup"><span data-stu-id="49819-199">You can update your card information and immediately submit the payment by using the **Settle balance** link in the **Billing** section of the subscription details page.</span></span> <span data-ttu-id="49819-200">Zie [Wat als mijn creditcard is geweigerd en mijn betaling achterstallig is voor](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due) meer informatie.</span><span class="sxs-lookup"><span data-stu-id="49819-200">For more information, see [What if my credit card was declined and my payment is past due?](pay-for-your-subscription.md#what-if-my-credit-card-was-declined-and-my-payment-is-past-due)</span></span>  <br/><br/>  <span data-ttu-id="49819-201">Neem contact op met uw bank als u het bericht 'geweigerd' blijft zien.</span><span class="sxs-lookup"><span data-stu-id="49819-201">If you continue to see the "declined" message, contact your bank.</span></span> <span data-ttu-id="49819-202">Het is mogelijk dat uw kaart niet actief is.</span><span class="sxs-lookup"><span data-stu-id="49819-202">It's possible that your card isn't active.</span></span> <span data-ttu-id="49819-203">Als u de kaart onlangs in de e-mail hebt ontvangen met een bijgewerkte vervaldatum, controleert u of deze is geactiveerd.</span><span class="sxs-lookup"><span data-stu-id="49819-203">If you recently received the card in the mail with an updated expiration date, make sure it's activated.</span></span> <span data-ttu-id="49819-204">Uw bank kan u ook vertellen of uw kaart niet is goedgekeurd voor online, internationale of terugkerende transacties.</span><span class="sxs-lookup"><span data-stu-id="49819-204">Your bank can also tell you whether your card isn't approved for online, international, or recurring transactions.</span></span> |
|<span data-ttu-id="49819-205">**Ik wil een kaart of bankrekeningnummer bijwerken.**</span><span class="sxs-lookup"><span data-stu-id="49819-205">**I want to update a card or bank account number.**</span></span> |<span data-ttu-id="49819-206">U de kaart of het rekeningnummer niet wijzigen op een bestaande betalingsmethode.</span><span class="sxs-lookup"><span data-stu-id="49819-206">You can't change the card or account number on an existing payment method.</span></span> <span data-ttu-id="49819-207">Als uw kaart of rekeningnummer is gewijzigd, [vervangt u deze door een andere betalingsmethode,](#replace-a-payment-method)waarbij alle actieve abonnementen van de betalingsmethode naar de nieuwe worden verplaatst en vervolgens de oude betalingsmethode wordt [verwijderd.](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached)</span><span class="sxs-lookup"><span data-stu-id="49819-207">If your card or account number has changed, [replace it with a different payment method](#replace-a-payment-method), which moves all active subscriptions from the payment method to the new one, then [delete the old payment method](#delete-a-payment-method-with-no-subscriptions-or-billing-profiles-attached).</span></span> |
|<span data-ttu-id="49819-208">**Ik heb slechts één kaart of bankrekening op mijn rekening en ik wil deze verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="49819-208">**I only have one card or bank account on my account and I want to remove it.**</span></span> |<span data-ttu-id="49819-209">Als u slechts één betalingsmethode hebt, moet u [deze vervangen door een nieuwe betalingsmethode](#replace-a-payment-method) voordat u deze verwijderen.</span><span class="sxs-lookup"><span data-stu-id="49819-209">If you only have one payment method, you must [replace it with a new payment method](#replace-a-payment-method) before you can delete it.</span></span> |
|<span data-ttu-id="49819-210">**Ik kan mijn kaart of bankrekening niet toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="49819-210">**I can't add my card or bank account.**</span></span>  |<span data-ttu-id="49819-211">U moet een betalingsmethode gebruiken die is uitgegeven vanuit hetzelfde land als uw huurder.</span><span class="sxs-lookup"><span data-stu-id="49819-211">You must use a payment method issued from the same country as your tenant.</span></span> <span data-ttu-id="49819-212">Als u problemen ondervindt bij het invoeren van uw kaart- of bankrekeninggegevens, u [contact opnemen met de ondersteuning.](../../admin/contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="49819-212">If you have trouble entering your card or bank account information, you can [contact support](../../admin/contact-support-for-business-products.md).</span></span> |

## <a name="related-articles"></a><span data-ttu-id="49819-213">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="49819-213">Related articles</span></span>

[<span data-ttu-id="49819-214">Betalen voor uw zakelijke abonnement</span><span class="sxs-lookup"><span data-stu-id="49819-214">Pay for your business subscription</span></span>](pay-for-your-subscription.md)

[<span data-ttu-id="49819-215">Factureringsprofielen beheren</span><span class="sxs-lookup"><span data-stu-id="49819-215">Manage billing profiles</span></span>](manage-billing-profiles.md)

[<span data-ttu-id="49819-216">Uw betalingsfrequentie wijzigen</span><span class="sxs-lookup"><span data-stu-id="49819-216">Change your payment frequency</span></span>](change-payment-frequency.md)