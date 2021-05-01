---
title: Partnerrelaties beheren
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
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: tugu
search.appverid:
- MET150
description: Lees hoe u met microsoft-gecertificeerde oplossingsproviders (partners) producten en services voor uw organisatie of school kunt kopen en beheren.
ms.date: 04/13/2021
ms.openlocfilehash: e225fa0c525d484e8c5a3887b82277a1da5861b0
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107566"
---
# <a name="manage-partner-relationships"></a><span data-ttu-id="37eee-103">Partnerrelaties beheren</span><span class="sxs-lookup"><span data-stu-id="37eee-103">Manage partner relationships</span></span>

<span data-ttu-id="37eee-104">U kunt samenwerken met microsoft-gecertificeerde oplossingsproviders (partners) om producten en services voor uw organisatie of school te kopen en te beheren.</span><span class="sxs-lookup"><span data-stu-id="37eee-104">You can work with Microsoft-certified solution providers (partners) to purchase and manage products and services for your organization or school.</span></span> <span data-ttu-id="37eee-105">Er zijn een paar stappen betrokken bij het instellen van dingen.</span><span class="sxs-lookup"><span data-stu-id="37eee-105">There are a few steps involved in getting things set up.</span></span>

1. <span data-ttu-id="37eee-106">Beheerders zoeken en nemen contact op met een partner via het formulier op <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a> .</span><span class="sxs-lookup"><span data-stu-id="37eee-106">Admins find and contact a partner using the form at <a href="https://www.microsoft.com/solution-providers/home" target="_blank">https://www.microsoft.com/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="37eee-107">Partners sturen een e-mailverzoek naar klanten om een partnerrelatie tot stand te brengen.</span><span class="sxs-lookup"><span data-stu-id="37eee-107">Partners send an email request to customers to establish a partner relationship.</span></span>
3. <span data-ttu-id="37eee-108">Klanten accepteren de uitnodiging in Microsoft 365 beheercentrum en gaan met de partner werken.</span><span class="sxs-lookup"><span data-stu-id="37eee-108">Customers accept the invitation in Microsoft 365 admin center and start working with the partner.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="37eee-109">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="37eee-109">Before you begin</span></span>

<span data-ttu-id="37eee-110">U moet een globale beheerder of factureringsbeheerder zijn om deze stappen uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="37eee-110">You must be either a Global or Billing admin to do these steps.</span></span> <span data-ttu-id="37eee-111">Zie[Over beheerdersrollen](../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="37eee-111">For more information, see [About admin roles](../admin/add-users/about-admin-roles.md).</span></span>

## <a name="what-can-a-partner-do-for-my-organization-or-school"></a><span data-ttu-id="37eee-112">Wat kan een partner doen voor mijn organisatie of school?</span><span class="sxs-lookup"><span data-stu-id="37eee-112">What can a partner do for my organization or school?</span></span>

<span data-ttu-id="37eee-113">Er zijn verschillende manieren waarop een partner met u kan werken.</span><span class="sxs-lookup"><span data-stu-id="37eee-113">There are several ways that a partner can work with you.</span></span> <span data-ttu-id="37eee-114">Op basis van uw opgegeven zakelijke behoeften, kiezen ze een van deze typen wanneer ze hun verzoek verzenden om met u samen te werken.</span><span class="sxs-lookup"><span data-stu-id="37eee-114">Based on your stated business needs, they choose one of these types when they send their request to work with you.</span></span>

| <span data-ttu-id="37eee-115">Partnertype</span><span class="sxs-lookup"><span data-stu-id="37eee-115">Partner type</span></span> | <span data-ttu-id="37eee-116">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="37eee-116">Description</span></span> |
| ------ | ------------------- |
| <span data-ttu-id="37eee-117">Wederverkoper</span><span class="sxs-lookup"><span data-stu-id="37eee-117">Reseller</span></span> | <span data-ttu-id="37eee-118">Partners die Microsoft-producten verkopen aan uw organisatie of school.</span><span class="sxs-lookup"><span data-stu-id="37eee-118">Partners that sell Microsoft products to your organization or school.</span></span> |
| <span data-ttu-id="37eee-119">Gedelegeerde beheerder</span><span class="sxs-lookup"><span data-stu-id="37eee-119">Delegated administrator</span></span> | <span data-ttu-id="37eee-120">Partners die producten en services voor uw organisatie of school beheren.</span><span class="sxs-lookup"><span data-stu-id="37eee-120">Partners that manage products and services for your organization or school.</span></span> <span data-ttu-id="37eee-121">In Azure Active Directory (AD) is de partner een globale beheerder voor uw tenant.</span><span class="sxs-lookup"><span data-stu-id="37eee-121">In Azure Active Directory (AD), the partner is a Global Administrator for your tenant.</span></span> <span data-ttu-id="37eee-122">Met deze rol kunnen ze services beheren, zoals het maken van gebruikersaccounts, het toewijzen en beheren van licenties en het opnieuw instellen van wachtwoorden.</span><span class="sxs-lookup"><span data-stu-id="37eee-122">This role lets them manage services like creating user accounts, assigning and managing licenses, and password resets.</span></span> |
| <span data-ttu-id="37eee-123">Reseller & gedelegeerde beheerder</span><span class="sxs-lookup"><span data-stu-id="37eee-123">Reseller & delegated administrator</span></span> | <span data-ttu-id="37eee-124">Partners die Microsoft-producten en -services verkopen en beheren aan uw organisatie of school.</span><span class="sxs-lookup"><span data-stu-id="37eee-124">Partners that sell and manage Microsoft products and services to your organization or school.</span></span> |
| <span data-ttu-id="37eee-125">Partner</span><span class="sxs-lookup"><span data-stu-id="37eee-125">Partner</span></span> | <span data-ttu-id="37eee-126">U geeft uw partner een gebruikersaccount in uw tenant en ze werken met andere Microsoft-services namens u.</span><span class="sxs-lookup"><span data-stu-id="37eee-126">You give your partner a user account in your tenant, and they work with other Microsoft services on your behalf.</span></span> |
| <span data-ttu-id="37eee-127">Adviseur</span><span class="sxs-lookup"><span data-stu-id="37eee-127">Advisor</span></span> | <span data-ttu-id="37eee-128">Partners kunnen wachtwoorden opnieuw instellen en ondersteuningsincidenten voor u afhandelen.</span><span class="sxs-lookup"><span data-stu-id="37eee-128">Partners can reset passwords and handle support incidents for you.</span></span> |
| <span data-ttu-id="37eee-129">Microsoft Products & Services Agreement (MPSA) partner</span><span class="sxs-lookup"><span data-stu-id="37eee-129">Microsoft Products & Services Agreement (MPSA) partner</span></span> | <span data-ttu-id="37eee-130">Als u met meerdere partners hebt gewerkt via het MPSA-programma, kunt u toestaan dat ze aankopen van elkaar kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="37eee-130">If you've worked with multiple partners through the MPSA program, you can allow them to see purchases made by each other.</span></span> |
| <span data-ttu-id="37eee-131">Lob-partner (Line-of-Business)</span><span class="sxs-lookup"><span data-stu-id="37eee-131">Line-of-business (LOB) partner</span></span> | <span data-ttu-id="37eee-132">Partners kunnen LOB-apps ontwikkelen, indienen en beheren die specifiek zijn voor uw organisatie of school.</span><span class="sxs-lookup"><span data-stu-id="37eee-132">Partners can develop, submit, and manage LOB apps specific for your organization or school.</span></span> |

## <a name="find-a-partner"></a><span data-ttu-id="37eee-133">Een partner zoeken</span><span class="sxs-lookup"><span data-stu-id="37eee-133">Find a partner</span></span>

1. <span data-ttu-id="37eee-134">Ga naar <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span><span class="sxs-lookup"><span data-stu-id="37eee-134">Go to <a href="https://www.microsoft.com/en-us/solution-providers/home" target="_blank">https://www.microsoft.com/en-us/solution-providers/home</a>.</span></span>
2. <span data-ttu-id="37eee-135">Voer uw locatie in, kies de grootte van uw organisatie, voeg trefwoorden toe voor het type services dat u nodig hebt en selecteer **Vervolgens Ga**.</span><span class="sxs-lookup"><span data-stu-id="37eee-135">Enter your location, choose your organization size, add keywords for the type of services you need, then select **Go**.</span></span>
3. <span data-ttu-id="37eee-136">Kies een of meer partners en selecteer **vervolgens Geselecteerde providers contact opnemen.**</span><span class="sxs-lookup"><span data-stu-id="37eee-136">Choose one or more partners, then select **Contact selected providers**.</span></span>
4. <span data-ttu-id="37eee-137">Vul het formulier in om uw zakelijke behoeften te beschrijven en selecteer **verzenden.**</span><span class="sxs-lookup"><span data-stu-id="37eee-137">Complete the form to describe your business needs, then select **Send**.</span></span>

<span data-ttu-id="37eee-138">De partner neemt contact met u op en geeft u de mogelijkheid om meer over hen te weten te komen.</span><span class="sxs-lookup"><span data-stu-id="37eee-138">The partner contacts you and gives you a chance to learn more about them.</span></span> <span data-ttu-id="37eee-139">Als u besluit om met hen te werken, sturen ze u een e-mailuitnodiging om een partnerrelatie tot stand te komen.</span><span class="sxs-lookup"><span data-stu-id="37eee-139">If you decide to work with them, they send you an email invitation to establish a partner relationship.</span></span>

## <a name="review-and-accept-a-partner-relationship-and-microsoft-customer-agreement"></a><span data-ttu-id="37eee-140">Een partnerrelatie en microsoft-klantovereenkomst controleren en accepteren</span><span class="sxs-lookup"><span data-stu-id="37eee-140">Review and accept a partner relationship and Microsoft Customer Agreement</span></span>

<span data-ttu-id="37eee-141">Nadat u een partner hebt gevonden en met hen hebt gewerkt, sturen ze u een e-mailuitnodiging.</span><span class="sxs-lookup"><span data-stu-id="37eee-141">After you find a partner and decide to work with them, they send you an email invitation.</span></span>

1. <span data-ttu-id="37eee-142">Selecteer in het e-mailbericht de koppeling om naar het Microsoft 365 te gaan.</span><span class="sxs-lookup"><span data-stu-id="37eee-142">In the email, select the link to go to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="37eee-143">Selecteer op **de pagina Overeenkomst accepteren & partner** machtigen de koppeling voor de **Microsoft-klantovereenkomst** en lees het document.</span><span class="sxs-lookup"><span data-stu-id="37eee-143">On the **Accept agreement & authorize partner** page, select the link for the **Microsoft Customer Agreement**, and read the document.</span></span>
3. <span data-ttu-id="37eee-144">Vink het selectievakje aan om te bevestigen dat u de overeenkomst hebt gelezen.</span><span class="sxs-lookup"><span data-stu-id="37eee-144">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="37eee-145">Selecteer **Accepteren & Autor.**</span><span class="sxs-lookup"><span data-stu-id="37eee-145">Select **Accept & Authorize**.</span></span>
5. <span data-ttu-id="37eee-146">De lijst met partners met wie u werkt, wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="37eee-146">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="37eee-147">Selecteer een partner om details te zien.</span><span class="sxs-lookup"><span data-stu-id="37eee-147">Select any partner to see details.</span></span>

## <a name="review-and-accept-a-microsoft-customer-agreement"></a><span data-ttu-id="37eee-148">Een Microsoft-klantovereenkomst controleren en accepteren</span><span class="sxs-lookup"><span data-stu-id="37eee-148">Review and accept a Microsoft Customer Agreement</span></span>

<span data-ttu-id="37eee-149">Als u al een partner hebt, maar nog geen Microsoft-klantovereenkomst hebt ondertekend, moet u de overeenkomst accepteren voordat deze namens u aankopen kan doen of uw abonnementen kan beheren.</span><span class="sxs-lookup"><span data-stu-id="37eee-149">If you already have a partner but haven’t yet signed a Microsoft Customer Agreement, you must accept the agreement before they can make purchases or manage your subscriptions on your behalf.</span></span>

1. <span data-ttu-id="37eee-150">Als u een e-mailbericht van uw partner ontvangt, selecteert u de koppeling om naar het Microsoft 365 beheercentrum te gaan of gaat u naar de pagina <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Overeenkomst accepteren.</a></span><span class="sxs-lookup"><span data-stu-id="37eee-150">If you receive an email from your partner, select the link to go to the Microsoft 365 admin center, or go to the <a href="https://go.microsoft.com/fwlink/?linkid=2116573" target="_blank">Accept agreement</a> page.</span></span>
2. <span data-ttu-id="37eee-151">Selecteer de koppeling voor de **Microsoft-klantovereenkomst en** lees het document.</span><span class="sxs-lookup"><span data-stu-id="37eee-151">Select the link for the **Microsoft Customer Agreement** and read the document.</span></span>
3. <span data-ttu-id="37eee-152">Vink het selectievakje aan om te bevestigen dat u de overeenkomst hebt gelezen.</span><span class="sxs-lookup"><span data-stu-id="37eee-152">Check the box to acknowledge that you read the agreement.</span></span>
4. <span data-ttu-id="37eee-153">Selecteer **Accepteren.**</span><span class="sxs-lookup"><span data-stu-id="37eee-153">Select **Accept**.</span></span>
5. <span data-ttu-id="37eee-154">De lijst met partners met wie u werkt, wordt weergegeven.</span><span class="sxs-lookup"><span data-stu-id="37eee-154">The list of partners that you’re working with is displayed.</span></span> <span data-ttu-id="37eee-155">Selecteer een partner om details te zien.</span><span class="sxs-lookup"><span data-stu-id="37eee-155">Select any partner to see details.</span></span>

## <a name="remove-partner-admin-roles"></a><span data-ttu-id="37eee-156">Rollen van partnerbeheerders verwijderen</span><span class="sxs-lookup"><span data-stu-id="37eee-156">Remove partner admin roles</span></span>

<span data-ttu-id="37eee-157">Afhankelijk van de aanvraag van de partner, gaat u ermee akkoord dat u de partner globale en helpdeskbeheerdersrollen geeft wanneer u de uitnodiging accepteert.</span><span class="sxs-lookup"><span data-stu-id="37eee-157">Depending on the request made by the partner, when you accept the invitation, you agree to give them Global and Helpdesk admin roles.</span></span> <span data-ttu-id="37eee-158">Wanneer u deze beheerdersrollen aan een partner geeft, verleent u deze automatisch gedelegeerde beheerdersbevoegdheden in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="37eee-158">When you give these admin roles to a partner, you automatically grant them delegated admin privileges in Azure AD.</span></span> <span data-ttu-id="37eee-159">Zie Gedelegeerde beheerdersbevoegdheden in Azure AD voor [meer informatie.](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad)</span><span class="sxs-lookup"><span data-stu-id="37eee-159">To learn more, see [Delegated admin privileges in Azure AD](/partner-center/customers_revoke_admin_privileges#delegated-admin-privileges-in-azure-ad).</span></span>

<span data-ttu-id="37eee-160">Als u de beheerdersrollen niet aan de partner wilt geven, annuleert u de uitnodiging in plaats van deze te accepteren.</span><span class="sxs-lookup"><span data-stu-id="37eee-160">If you don't want to give the admin roles to the partner, cancel the invitation instead of accepting it.</span></span>

<span data-ttu-id="37eee-161">U kunt beheerdersrollen op elk moment van een partner verwijderen.</span><span class="sxs-lookup"><span data-stu-id="37eee-161">You can remove admin roles from a partner at any time.</span></span> <span data-ttu-id="37eee-162">Als u de beheerdersrollen verwijdert, wordt de partnerrelatie niet verwijderd.</span><span class="sxs-lookup"><span data-stu-id="37eee-162">Removing the admin roles doesn’t remove the partner relationship.</span></span> <span data-ttu-id="37eee-163">Ze kunnen nog steeds met u werken in een andere capaciteit, zoals een wederverkoper.</span><span class="sxs-lookup"><span data-stu-id="37eee-163">They can still work with you in a different capacity, such as a Reseller.</span></span> <span data-ttu-id="37eee-164">Als u besluit dat u niet meer met een partner wilt werken, neemt u contact op met uw partner om de relatie te beëindigen.</span><span class="sxs-lookup"><span data-stu-id="37eee-164">If you decide that you don’t want to work with a partner anymore, contact your partner to end the relationship.</span></span>

1. <span data-ttu-id="37eee-165">Ga in het beheercentrum naar de **pagina Instellingen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">partnerrelaties.</a></span><span class="sxs-lookup"><span data-stu-id="37eee-165">In the admin center, go to the **Settings** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2074649" target="_blank">Partner relationships</a> page.</span></span>
2. <span data-ttu-id="37eee-166">Selecteer op **de pagina** Partnerrelaties de rij met de naam van de partner die u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="37eee-166">On the **Partner relationships** page, select the row that contains the name of the partner that you want to remove.</span></span>
3. <span data-ttu-id="37eee-167">Selecteer de rij met de naam van de partner.</span><span class="sxs-lookup"><span data-stu-id="37eee-167">Select the row that contains the name of the partner.</span></span>
4. <span data-ttu-id="37eee-168">Selecteer rollen verwijderen op de **partnerpagina.**</span><span class="sxs-lookup"><span data-stu-id="37eee-168">On the partner page, select **Remove roles**.</span></span>
5. <span data-ttu-id="37eee-169">Selecteer ja in het dialoogvenster Rollen **verwijderen?** **.**</span><span class="sxs-lookup"><span data-stu-id="37eee-169">In the **Remove roles?** dialog box, select **Yes**.</span></span>
