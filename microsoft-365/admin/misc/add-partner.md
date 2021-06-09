---
title: Een abonnementsadviseur toevoegen, wijzigen of verwijderen
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
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f86e8177-936e-491e-9024-44dea2b296ff
description: Voeg een recordpartner toe op het moment Microsoft 365, wijzig de partner of verwijder een partner uit een abonnement.
ms.openlocfilehash: 4cebbce41cbd2a500cc502b808734f6056271d12
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683341"
---
# <a name="add-change-or-delete-a-subscription-advisor-partner"></a><span data-ttu-id="d750f-103">Een abonnementsadviseur toevoegen, wijzigen of verwijderen</span><span class="sxs-lookup"><span data-stu-id="d750f-103">Add, change, or delete a subscription advisor partner</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="d750f-104">Dit artikel is van toepassing Office 365 beheerd door 21Vianet in China.</span><span class="sxs-lookup"><span data-stu-id="d750f-104">This article applies to Office 365 operated by 21Vianet in China.</span></span> <span data-ttu-id="d750f-105">Het is voor organisaties die willen toestaan dat een 21Vianet-partner hun Office 365 voor hen beheert.</span><span class="sxs-lookup"><span data-stu-id="d750f-105">It is for organizations who want to allow a 21Vianet Partner to administer their Office 365 subscription for them.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

<span data-ttu-id="d750f-106">Een geautoriseerde partner van Microsoft die fungeert als uw abonnementsadviseur biedt de verkoop-, ondersteunings- en technische expertise die u nodig hebt om u te helpen een abonnement in te stellen en te onderhouden.</span><span class="sxs-lookup"><span data-stu-id="d750f-106">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription.</span></span> <span data-ttu-id="d750f-107">U kunt een partner van een abonnementsadviseur toevoegen als partner van record wanneer u een abonnement Microsoft 365 of op een ander tijdstip.</span><span class="sxs-lookup"><span data-stu-id="d750f-107">You can add a subscription advisor partner as a partner of record when you purchase Microsoft 365 or at another time.</span></span> <span data-ttu-id="d750f-108">Als u momenteel niet met een partner werkt, kunt u er ook een zoeken op de website [Microsoft Pinpoint](https://pinpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d750f-108">If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="d750f-p103">Een geautoriseerde partner van Microsoft die fungeert als uw abonnementsadviseur biedt de verkoop-, ondersteunings- en technische expertise die u nodig hebt om u te helpen een abonnement in te stellen en te onderhouden. U kunt een abonnementsadviseur toevoegen als een Partner of Record wanneer u Office 365 koopt of op elk ander gewenst moment. Als u momenteel niet met een partner werkt, kunt u er ook een zoeken op de website [Microsoft Pinpoint](https://pinpoint.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d750f-p103">An authorized partner of Microsoft who serves as your subscription advisor provides the sales, support, and technical expertise you need to help you set up and maintain your subscription. You can add a subscription advisor partner as a partner of record when you purchase Office 365 or at another time. If you're not currently working with a partner, you can also find one on the [Microsoft Pinpoint](https://pinpoint.microsoft.com) website.</span></span>

::: moniker-end

## <a name="before-you-begin"></a><span data-ttu-id="d750f-112">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="d750f-112">Before you begin</span></span>

::: moniker range="o365-worldwide"

<span data-ttu-id="d750f-113">De partner die u kiest, is afhankelijk van de Microsoft-services die u gebruikt en het land of de regio waar u deze services gaat gebruiken.</span><span class="sxs-lookup"><span data-stu-id="d750f-113">The partner you choose depends on the Microsoft services you use and the country or region where you'll use those services.</span></span> <span data-ttu-id="d750f-114">Als u een partner toevoegt, of de partner voor uw abonnement wijzigt, moet u de partner eerst vragen om diens Microsoft-partner-id.</span><span class="sxs-lookup"><span data-stu-id="d750f-114">If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-germany"

<span data-ttu-id="d750f-p105">Welke partner u kiest, hangt af van de Office 365-services die u gebruikt en het land of de regio waar u die services gebruikt. Als u een partner toevoegt, of de partner voor uw abonnement wijzigt, moet u de partner eerst vragen om diens Microsoft-partner-id.</span><span class="sxs-lookup"><span data-stu-id="d750f-p105">The partner you choose depends on the Office 365 services you use and the country or region where you'll use those services. If you are adding a partner, or changing the partner for your subscription, first you need to get the partner's Microsoft Partner ID by asking the partner for it.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="d750f-117">Als beheerder voor Office 365 kunt u gebruikers maken of bewerken, gebruikerswachtwoorden opnieuw instellen, gebruikerslicenties beheren, domeinen beheren en beheerdersmachtigingen toewijzen aan andere gebruikers in uw organisatie, onder andere.</span><span class="sxs-lookup"><span data-stu-id="d750f-117">As an admin for Office 365, you can create or edit users, reset user passwords, manage user licenses, manage domains, and assign admin permissions to other users in your organization, among other things.</span></span> <span data-ttu-id="d750f-118">Als u echter wilt dat iemand anders deze beheertaken uitvoert, kunt u deze rol delegeren aan een geautoriseerde partner van 21Vianet door een partnerrelatie te maken.</span><span class="sxs-lookup"><span data-stu-id="d750f-118">However, if you want someone else to do these administrative tasks, you can delegate this role to an authorized partner of 21Vianet by creating a partner relationship.</span></span>

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="d750f-119">Een partner toevoegen op het moment van aanschaf</span><span class="sxs-lookup"><span data-stu-id="d750f-119">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="d750f-120">Ga in het beheercentrum naar de pagina  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Factureringsaankoopservices.**</a></span><span class="sxs-lookup"><span data-stu-id="d750f-120">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**Purchase services**</a> page.</span></span>
2. <span data-ttu-id="d750f-121">Selecteer het product dat u wilt kopen en selecteer vervolgens **Kopen.**</span><span class="sxs-lookup"><span data-stu-id="d750f-121">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="d750f-122">Als u een nieuwe partner wilt toevoegen, **vouwt** u Hulp nodig bij uw bestelling uit en selecteert u Hulp krijgen van een **Microsoft-partner.**</span><span class="sxs-lookup"><span data-stu-id="d750f-122">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="d750f-123">Volg de stappen op de pagina providers om te zoeken naar of om te worden gematcht met een partner.</span><span class="sxs-lookup"><span data-stu-id="d750f-123">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="d750f-124">Als u al een partner hebt, selecteert u in de tweede stap van de wizard Uitchecken in het rechterdeelvenster onder Partnergegevens de optie **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d750f-124">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="d750f-p107">Typ de Microsoft-partner-id van de partner die u toevoegt. U kunt de partner vragen om diens Microsoft-partner-id.</span><span class="sxs-lookup"><span data-stu-id="d750f-p107">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="d750f-127">Voltooi de rest van de wizard om de aanschaf van uw abonnementen te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d750f-127">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

::: moniker range="o365-germany"

## <a name="add-a-partner-at-the-time-of-purchase"></a><span data-ttu-id="d750f-128">Een partner toevoegen op het moment van aanschaf</span><span class="sxs-lookup"><span data-stu-id="d750f-128">Add a partner at the time of purchase</span></span>

1. <span data-ttu-id="d750f-129">Ga in [het beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=848041)naar de pagina **Factureringsaankoopservices.** \> </span><span class="sxs-lookup"><span data-stu-id="d750f-129">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=848041), go to the **Billing** \> **Purchase services**  page.</span></span>
2. <span data-ttu-id="d750f-130">Selecteer het product dat u wilt kopen en selecteer vervolgens **Kopen.**</span><span class="sxs-lookup"><span data-stu-id="d750f-130">Select the product that you want to purchase, and then select **Buy**.</span></span>
3. <span data-ttu-id="d750f-131">Als u een nieuwe partner wilt toevoegen, **vouwt** u Hulp nodig bij uw bestelling uit en selecteert u Hulp krijgen van een **Microsoft-partner.**</span><span class="sxs-lookup"><span data-stu-id="d750f-131">To add a new partner, expand **Need help with your order?** and select **Get assistance from a Microsoft Partner**.</span></span><br>
<span data-ttu-id="d750f-132">Volg de stappen op de pagina providers om te zoeken naar of om te worden gematcht met een partner.</span><span class="sxs-lookup"><span data-stu-id="d750f-132">Follow the steps on the providers page to either search for, or to get matched with a partner.</span></span>
4. <span data-ttu-id="d750f-133">Als u al een partner hebt, selecteert u in de tweede stap van de wizard Uitchecken in het rechterdeelvenster onder Partnergegevens de optie **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d750f-133">If you already have a partner, in the second step of the checkout wizard, in the right pane, under Partner information, select **Add**.</span></span>
5. <span data-ttu-id="d750f-p108">Typ de Microsoft-partner-id van de partner die u toevoegt. U kunt de partner vragen om diens Microsoft-partner-id.</span><span class="sxs-lookup"><span data-stu-id="d750f-p108">Type the Microsoft Partner ID for the partner you're adding. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
6. <span data-ttu-id="d750f-136">Voltooi de rest van de wizard om de aanschaf van uw abonnementen te voltooien.</span><span class="sxs-lookup"><span data-stu-id="d750f-136">Complete the rest of the wizard to finish buying your subscriptions.</span></span>

::: moniker-end

## <a name="add-a-partner-to-an-existing-subscription"></a><span data-ttu-id="d750f-137">Een partner toevoegen aan een bestaand abonnement</span><span class="sxs-lookup"><span data-stu-id="d750f-137">Add a partner to an existing subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d750f-138">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-138">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="d750f-139">Selecteer op **het** tabblad Producten het abonnement dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="d750f-139">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="d750f-140">Typ op de pagina abonnementsgegevens onder **Partnergegevens** de **partnernetwerk-id.**</span><span class="sxs-lookup"><span data-stu-id="d750f-140">On the subscription details page, under **Partner information**, type the **Partner Network ID**.</span></span> <span data-ttu-id="d750f-141">U kunt de Microsoft Partner Network-id van de partner krijgen door de partner om deze te vragen.</span><span class="sxs-lookup"><span data-stu-id="d750f-141">You can get the partner's Microsoft Partner Network ID by asking the partner for it.</span></span>
4. <span data-ttu-id="d750f-142">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d750f-142">Select **Add**.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d750f-143">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnementen</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-143">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Subscriptions</a> page.</span></span>
2. <span data-ttu-id="d750f-144">Als u meerdere abonnementen hebt, selecteert u het abonnement dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="d750f-144">If you have more than one subscription, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="d750f-145">Selecteer rechts onder de abonnementskosten de drie puntjes (meer acties) > **Partner van record toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="d750f-145">On the right, under the subscription cost, select the three dots (more actions) > **Add partner of record**.</span></span>
4. <span data-ttu-id="d750f-p110">Typ de Microsoft-partner-id van de partner die u toevoegt, selecteer **Id controleren** en vervolgens **Verzenden**. U kunt de partner vragen om diens Microsoft-partner-id.</span><span class="sxs-lookup"><span data-stu-id="d750f-p110">Type the Microsoft Partner ID for the partner you're adding, select **Check ID**, and then **Submit**. You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
5. <span data-ttu-id="d750f-148">De partner-id wordt weergegeven op de pagina **Abonnementen**.</span><span class="sxs-lookup"><span data-stu-id="d750f-148">The partner ID displays on the **Subscriptions** page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

<span data-ttu-id="d750f-149">Dit proces wordt gestart door uw geautoriseerde partner.</span><span class="sxs-lookup"><span data-stu-id="d750f-149">This process is initiated by your authorized partner.</span></span> <span data-ttu-id="d750f-150">De partner stuurt u een e-mail om u te vragen of u hen toestemming wilt geven om op te treden als een recordpartner.</span><span class="sxs-lookup"><span data-stu-id="d750f-150">The partner sends you an email to ask you if you want to give them permission to act as a partner of record.</span></span>
  
<span data-ttu-id="d750f-151">Deze aanbieding accepteren</span><span class="sxs-lookup"><span data-stu-id="d750f-151">To accept this offer</span></span>
  
1. <span data-ttu-id="d750f-152">Lees de voorwaarden van de partner in het e-mailbericht.</span><span class="sxs-lookup"><span data-stu-id="d750f-152">Read the partner's terms in the email.</span></span>
2. <span data-ttu-id="d750f-153">Als u de overeenkomst wilt machtigen, selecteert u de koppeling, die naar een autorisatiepagina in Office 365.</span><span class="sxs-lookup"><span data-stu-id="d750f-153">To authorize the agreement, select the link, which goes to an authorization page in Office 365.</span></span>
3. <span data-ttu-id="d750f-154">Selecteer **onder Partnerrelaties** de optie **Ja** om de partner te machtigen uw gedelegeerde beheerder te worden en selecteer vervolgens **Volgende.**</span><span class="sxs-lookup"><span data-stu-id="d750f-154">Under **Partner Relationships**, select **Yes** to authorize the partner to be your delegated admin, and then select **Next**.</span></span>
4. <span data-ttu-id="d750f-155">Als de aanbieding voor partnerrelatie is aangeboden met een proefabonnement of een aankoopaanbieding, maakt u uw proef- of abonnementsaccount.</span><span class="sxs-lookup"><span data-stu-id="d750f-155">If the offer for partner relationship came with a trial subscription or a purchase offer, create your trial or subscription account.</span></span>

::: moniker-end

## <a name="change-the-partner-for-a-subscription"></a><span data-ttu-id="d750f-156">De partner voor een abonnement wijzigen</span><span class="sxs-lookup"><span data-stu-id="d750f-156">Change the partner for a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d750f-157">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-157">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d750f-158">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-158">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d750f-159">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-159">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="d750f-160">Selecteer op de pagina abonnementendetails onder **Partnergegevens** de optie **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="d750f-160">On the subscriptions details page, under **Partner information**, select **Remove**.</span></span>
3. <span data-ttu-id="d750f-161">Typ de **Microsoft Partner Network-id** voor de nieuwe partner.</span><span class="sxs-lookup"><span data-stu-id="d750f-161">Type the **Microsoft Partner Network ID** for the new partner.</span></span> <span data-ttu-id="d750f-162">U kunt de Microsoft Partner-id van de partner opvragen door de partner hiernaar te vragen.</span><span class="sxs-lookup"><span data-stu-id="d750f-162">You can get the partner's Microsoft Partner ID by asking the partner for it.</span></span>
4. <span data-ttu-id="d750f-163">Kies **Toevoegen**.</span><span class="sxs-lookup"><span data-stu-id="d750f-163">Select **Add**.</span></span>
  
## <a name="view-your-partner-relationships"></a><span data-ttu-id="d750f-164">Uw partnerrelaties bekijken</span><span class="sxs-lookup"><span data-stu-id="d750f-164">View your partner relationships</span></span>

- <span data-ttu-id="d750f-165">Ga in het beheercentrum naar de **pagina Instellingen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">partnerrelaties.</a></span><span class="sxs-lookup"><span data-stu-id="d750f-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span> <span data-ttu-id="d750f-166">Uw partners worden vermeld op deze pagina.</span><span class="sxs-lookup"><span data-stu-id="d750f-166">Your partners are listed on this page.</span></span>

  <span data-ttu-id="d750f-167">Als u geen partner hebt, ziet u een bericht met de tekst 'Er is hier niets'.</span><span class="sxs-lookup"><span data-stu-id="d750f-167">If you don't have a partner, you'll see a message that says "There's nothing here."</span></span>
  
## <a name="delete-a-partner-from-a-subscription"></a><span data-ttu-id="d750f-168">Een partner uit een abonnement verwijderen</span><span class="sxs-lookup"><span data-stu-id="d750f-168">Delete a partner from a subscription</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="d750f-169">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-169">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="d750f-170">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-170">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Your products</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="d750f-171">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="d750f-171">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Your products</a> page.</span></span>
::: moniker-end
2. <span data-ttu-id="d750f-172">Selecteer op **het** tabblad Producten het abonnement dat u wilt bewerken.</span><span class="sxs-lookup"><span data-stu-id="d750f-172">On the **Products** tab, select the subscription that you want to edit.</span></span>
3. <span data-ttu-id="d750f-173">Selecteer op de pagina Abonnementsgegevens onder **Partnergegevens** de optie **Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="d750f-173">On the subscription details page, under **Partner information**, select **Remove**.</span></span>

## <a name="remove-a-reseller-relationship"></a><span data-ttu-id="d750f-174">Een resellerrelatie verwijderen</span><span class="sxs-lookup"><span data-stu-id="d750f-174">Remove a reseller relationship</span></span>

<span data-ttu-id="d750f-175">Een resellerrelatie kunt u zelf niet verwijderen.</span><span class="sxs-lookup"><span data-stu-id="d750f-175">You can't remove a reseller relationship yourself.</span></span>

::: moniker range="o365-worldwide"
  
<span data-ttu-id="d750f-176">Als u een resellerrelatie wilt verwijderen is de optie **Verwijderen** niet beschikbaar. U moet uw reseller-partner vragen deze instructies te volgen: [Een resellerrelatie met een partner verwijderen](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="d750f-176">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>

::: moniker-end

::: moniker range="o365-germany"
  
<span data-ttu-id="d750f-177">Als u een resellerrelatie wilt verwijderen is de optie **Verwijderen** niet beschikbaar. U moet uw reseller-partner vragen deze instructies te volgen: [Een resellerrelatie met een partner verwijderen](/partner-center/remove-a-relationship).</span><span class="sxs-lookup"><span data-stu-id="d750f-177">If you are removing a reseller relationship the **Delete** option is grayed out, and you will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

::: moniker range="o365-21vianet"
  
<span data-ttu-id="d750f-178">U moet uw wederverkoper-partner vragen om deze instructies te volgen: [Een resellerrelatie met partner verwijderen.](/partner-center/remove-a-relationship)</span><span class="sxs-lookup"><span data-stu-id="d750f-178">You will have to ask your reseller partner to follow these instructions: [Remove a reseller relationship with partner](/partner-center/remove-a-relationship).</span></span>
  
::: moniker-end

## <a name="related-content"></a><span data-ttu-id="d750f-179">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d750f-179">Related content</span></span>

<span data-ttu-id="d750f-180">[Zoek uw Microsoft 365 partner of wederverkoper](../manage/find-your-partner-or-reseller.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="d750f-180">[Find your Microsoft 365 partner or reseller](../manage/find-your-partner-or-reseller.md) (article)</span></span>\
<span data-ttu-id="d750f-181">[Uw installatie van Microsoft 365 voor bedrijven](../setup/plan-your-setup.md) plannen (artikel)</span><span class="sxs-lookup"><span data-stu-id="d750f-181">[Plan your setup of Microsoft 365 for business](../setup/plan-your-setup.md) (article)</span></span>