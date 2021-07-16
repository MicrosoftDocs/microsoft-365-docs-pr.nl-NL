---
title: Aan de slag met app-beheer
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Ga aan de slag met mogelijkheden voor app-beheer om uw apps te beheren.
ms.openlocfilehash: 58f3bab9f8c5e28ce921ab244b23c49682394795
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430706"
---
# <a name="get-started-with-app-governance-in-preview"></a><span data-ttu-id="1b7df-103">Aan de slag met app-governance (in preview)</span><span class="sxs-lookup"><span data-stu-id="1b7df-103">Get started with app governance (in preview)</span></span>

<span data-ttu-id="1b7df-104">Ga als volgt te werk om de functie voor app-governance te gebruiken voor Microsoft Cloud App Security:</span><span class="sxs-lookup"><span data-stu-id="1b7df-104">To begin using the app governance add-on to Microsoft Cloud App Security:</span></span>

1. <span data-ttu-id="1b7df-105">Controleer of uw account het juiste licentieniveau heeft.</span><span class="sxs-lookup"><span data-stu-id="1b7df-105">Verify your account has the appropriate level of licensing.</span></span> <span data-ttu-id="1b7df-106">App-beheer is een invoegtoepassingsfunctie voor Microsoft Cloud App Security (MCAS) en daarom moet MCAS aanwezig zijn in uw account als zelfstandig product of als onderdeel van de verschillende licentiepakketten die hieronder worden vermeld.</span><span class="sxs-lookup"><span data-stu-id="1b7df-106">App governance is an add-on feature for Microsoft Cloud App Security (MCAS), and thus MCAS must be present in your account as either a standalone product or as part of the various license packages listed below.</span></span>
1. <span data-ttu-id="1b7df-107">U moet een van de onderstaande beheerdersrollen hebben om toegang te krijgen tot de pagina's voor app-beheer in de portal.</span><span class="sxs-lookup"><span data-stu-id="1b7df-107">You must have one of the administrator roles listed below to access the app governance pages in the portal.</span></span>

## <a name="licensing-for-app-governance"></a><span data-ttu-id="1b7df-108">Licenties voor app-beheer</span><span class="sxs-lookup"><span data-stu-id="1b7df-108">Licensing for app governance</span></span>

<span data-ttu-id="1b7df-109">Voordat u aan de slag gaat met app-beheer, moet u uw [Microsoft 365-abonnement](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) en eventuele invoegtoepassingen bevestigen.</span><span class="sxs-lookup"><span data-stu-id="1b7df-109">Before you get started with the app governance, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="1b7df-110">Voor toegang tot en gebruik van app-beheer moet uw organisatie een van de volgende abonnementen of invoegtoepassingen hebben:</span><span class="sxs-lookup"><span data-stu-id="1b7df-110">To access and use app governance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="1b7df-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="1b7df-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="1b7df-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="1b7df-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="1b7df-113">Microsoft 365 E5 Compliance</span><span class="sxs-lookup"><span data-stu-id="1b7df-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="1b7df-114">Microsoft 365 E5 Developer (zonder Windows en Audiovergadering)</span><span class="sxs-lookup"><span data-stu-id="1b7df-114">Microsoft 365 E5 Developer (without Windows and Audio Conferencing)</span></span>
- <span data-ttu-id="1b7df-115">Microsoft 365 E5 Gegevensbeveiliging en -beheer</span><span class="sxs-lookup"><span data-stu-id="1b7df-115">Microsoft 365 E5 Information Protection and Governance</span></span>
- <span data-ttu-id="1b7df-116">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="1b7df-116">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="1b7df-117">Microsoft 365 A5 met belminuten</span><span class="sxs-lookup"><span data-stu-id="1b7df-117">Microsoft 365 E5 with Calling Minutes</span></span>
- <span data-ttu-id="1b7df-118">Microsoft 365 E5 zonder Audiovergadering</span><span class="sxs-lookup"><span data-stu-id="1b7df-118">Microsoft 365 E5 without Audio Conferencing</span></span>
- <span data-ttu-id="1b7df-119">Microsoft 365 A5 Compliance voor onderwijsmedewerkers</span><span class="sxs-lookup"><span data-stu-id="1b7df-119">Microsoft 365 A5 Compliance for faculty</span></span>
- <span data-ttu-id="1b7df-120">Microsoft 365 A5 Compliance voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-120">Microsoft 365 A5 Compliance for students</span></span>
- <span data-ttu-id="1b7df-121">Microsoft 365 A5 voor onderwijsmedewerkers</span><span class="sxs-lookup"><span data-stu-id="1b7df-121">Microsoft 365 A5 for faculty</span></span>
- <span data-ttu-id="1b7df-122">Microsoft 365 A5 voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-122">Microsoft 365 A5 for students</span></span>
- <span data-ttu-id="1b7df-123">Microsoft 365 A5 Gegevensbeveiliging en -beheer voor onderwijsmedewerkers</span><span class="sxs-lookup"><span data-stu-id="1b7df-123">Microsoft 365 A5 Information Protection and Governance for faculty</span></span>
- <span data-ttu-id="1b7df-124">Microsoft 365 A5 Gegevensbeveiliging en -beheer voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-124">Microsoft 365 A5 Information Protection and Governance for students</span></span>
- <span data-ttu-id="1b7df-125">Microsoft 365 A5-beveiliging voor onderwijsmedewerkers</span><span class="sxs-lookup"><span data-stu-id="1b7df-125">Microsoft 365 A5 Security for faculty</span></span>
- <span data-ttu-id="1b7df-126">Microsoft 365 A5-beveiliging voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-126">Microsoft 365 A5 Security for students</span></span>
- <span data-ttu-id="1b7df-127">Gebruiksvoordeel Microsoft 365 A5 voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-127">Microsoft 365 A5 student use benefits</span></span>
- <span data-ttu-id="1b7df-128">Microsoft 365 A5 met belminuten voor onderwijsmedewerkers</span><span class="sxs-lookup"><span data-stu-id="1b7df-128">Microsoft 365 A5 with Calling Minutes for Faculty</span></span>
- <span data-ttu-id="1b7df-129">Microsoft 365 A5 met belminuten voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-129">Microsoft 365 A5 with Calling Minutes for Students</span></span>
- <span data-ttu-id="1b7df-130">Microsoft 365 A5 zonder Audiovergadering voor onderwijsmedewerkers</span><span class="sxs-lookup"><span data-stu-id="1b7df-130">Microsoft 365 A5 without Audio Conferencing for faculty</span></span>
- <span data-ttu-id="1b7df-131">Microsoft 365 A5 zonder Audiovergadering voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-131">Microsoft 365 A5 without Audio Conferencing for students</span></span>
- <span data-ttu-id="1b7df-132">Gebruiksvoordeel Microsoft 365 A5 zonder Audiovergadering voor leerlingen en studenten</span><span class="sxs-lookup"><span data-stu-id="1b7df-132">Microsoft 365 A5 without Audio Conferencing for students use benefit</span></span>

## <a name="administrator-roles"></a><span data-ttu-id="1b7df-133">Beheerdersrollen</span><span class="sxs-lookup"><span data-stu-id="1b7df-133">Administrator roles</span></span>

<span data-ttu-id="1b7df-134">Een van de volgende beheerdersrollen is vereist om app-beheerpagina's te zien of beleidsregels en -instellingen te beheren:</span><span class="sxs-lookup"><span data-stu-id="1b7df-134">One of the following administrator roles are required to see app governance pages or manage policies and settings:</span></span>

- <span data-ttu-id="1b7df-135">Toepassingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-135">Application Administrator</span></span>
- <span data-ttu-id="1b7df-136">Cloudtoepassingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-136">Cloud Application Administrator</span></span>
- <span data-ttu-id="1b7df-137">Bedrijfsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-137">Company Administrator</span></span>
- <span data-ttu-id="1b7df-138">Nalevingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-138">Compliance Administrator</span></span>
- <span data-ttu-id="1b7df-139">Beheerder van nalevingsgegevens</span><span class="sxs-lookup"><span data-stu-id="1b7df-139">Compliance Data Administrator</span></span>
- <span data-ttu-id="1b7df-140">Nalevingslezer (alleen-lezen)</span><span class="sxs-lookup"><span data-stu-id="1b7df-140">Compliance Reader (read-only)</span></span>
- <span data-ttu-id="1b7df-141">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="1b7df-141">Global Reader</span></span>
- <span data-ttu-id="1b7df-142">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-142">Security Administrator</span></span>
- <span data-ttu-id="1b7df-143">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="1b7df-143">Security Operator</span></span>
- <span data-ttu-id="1b7df-144">Beveiligingslezer (alleen-lezen)</span><span class="sxs-lookup"><span data-stu-id="1b7df-144">Security Reader (read-only)</span></span>

<span data-ttu-id="1b7df-145">Dit zijn de mogelijkheden voor elke rol.</span><span class="sxs-lookup"><span data-stu-id="1b7df-145">Here are the capabilities for each role.</span></span>

| <span data-ttu-id="1b7df-146">Rol</span><span class="sxs-lookup"><span data-stu-id="1b7df-146">Role</span></span> | <span data-ttu-id="1b7df-147">Het dashboard lezen</span><span class="sxs-lookup"><span data-stu-id="1b7df-147">Read the dashboard</span></span> | <span data-ttu-id="1b7df-148">Alle apps lezen</span><span class="sxs-lookup"><span data-stu-id="1b7df-148">Read all apps</span></span> |<span data-ttu-id="1b7df-149">Beleid lezen</span><span class="sxs-lookup"><span data-stu-id="1b7df-149">Read policies</span></span> | <span data-ttu-id="1b7df-150">Beleid maken, bijwerken of verwijderen</span><span class="sxs-lookup"><span data-stu-id="1b7df-150">Create, update, or delete policies</span></span> | <span data-ttu-id="1b7df-151">Waarschuwingen lezen</span><span class="sxs-lookup"><span data-stu-id="1b7df-151">Read alerts</span></span> | <span data-ttu-id="1b7df-152">Waarschuwingen bijwerken</span><span class="sxs-lookup"><span data-stu-id="1b7df-152">Update alerts</span></span> | <span data-ttu-id="1b7df-153">Instellingen lezen</span><span class="sxs-lookup"><span data-stu-id="1b7df-153">Read settings</span></span> | <span data-ttu-id="1b7df-154">Instellingen bijwerken</span><span class="sxs-lookup"><span data-stu-id="1b7df-154">Update settings</span></span> | <span data-ttu-id="1b7df-155">Herstel lezen</span><span class="sxs-lookup"><span data-stu-id="1b7df-155">Read Remediation</span></span> | <span data-ttu-id="1b7df-156">Herstel bijwerken</span><span class="sxs-lookup"><span data-stu-id="1b7df-156">Update Remediation</span></span> |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1b7df-157">Toepassingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-157">Application Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| <span data-ttu-id="1b7df-168">Cloudtoepassingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-168">Cloud Application Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | | | | | | | | | |
| <span data-ttu-id="1b7df-170">Bedrijfsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-170">Company Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |
| <span data-ttu-id="1b7df-181">Nalevingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-181">Compliance Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| <span data-ttu-id="1b7df-190">Beheerder van nalevingsgegevens</span><span class="sxs-lookup"><span data-stu-id="1b7df-190">Compliance Data Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| <span data-ttu-id="1b7df-199">Nalevingslezer</span><span class="sxs-lookup"><span data-stu-id="1b7df-199">Compliance Reader</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | | |
| <span data-ttu-id="1b7df-205">Algemene lezer</span><span class="sxs-lookup"><span data-stu-id="1b7df-205">Global Reader</span></span>  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | | |
| <span data-ttu-id="1b7df-211">Beveiligingsbeheerder</span><span class="sxs-lookup"><span data-stu-id="1b7df-211">Security Administrator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| <span data-ttu-id="1b7df-220">Beveiligingsoperator</span><span class="sxs-lookup"><span data-stu-id="1b7df-220">Security Operator</span></span> | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | |
| <span data-ttu-id="1b7df-230">Beveiligingslezer</span><span class="sxs-lookup"><span data-stu-id="1b7df-230">Security Reader</span></span>  | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) |  | ![Vinkje](..\media\checkmark.png) | |
|||||||||| | |

<span data-ttu-id="1b7df-237">Zie [Machtigingen voor beheerdersrollen](/azure/active-directory/roles/permissions-reference)voor meer informatie over elke rol.</span><span class="sxs-lookup"><span data-stu-id="1b7df-237">For additional information about each role, see [Administrator role permissions](/azure/active-directory/roles/permissions-reference).</span></span>

## <a name="add-app-governance-to-your-microsoft-365-account"></a><span data-ttu-id="1b7df-238">App-beheer toevoegen aan uw Microsoft 365-account</span><span class="sxs-lookup"><span data-stu-id="1b7df-238">Add app governance to your Microsoft 365 account</span></span>

<span data-ttu-id="1b7df-239">Voor bestaande Microsoft 365-klanten:</span><span class="sxs-lookup"><span data-stu-id="1b7df-239">For existing Microsoft 365 customers:</span></span>

1. <span data-ttu-id="1b7df-240">Navigeer in uw [Microsoft 365-beheercentrum](https://admin.microsoft.com)naar **Facturering - Services kopen** en klik op **Invoegtoepassingen**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-240">In your [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Billing - Purchase services** and click **Add-ons**.</span></span>
1. <span data-ttu-id="1b7df-241">Klik in de kaart voor app-beheer op **Details**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-241">In the app governance card, click **Details**.</span></span>
1. <span data-ttu-id="1b7df-242">Klik op **Gratis proefversie starten**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-242">Click **Start free trial**.</span></span>
1. <span data-ttu-id="1b7df-243">Voltooi de gevraagde informatie om app-beheer toe te voegen aan de geselecteerde tenant.</span><span class="sxs-lookup"><span data-stu-id="1b7df-243">Complete the requested information to add app governance to your selected tenant.</span></span> <span data-ttu-id="1b7df-244">Als u een nieuwe klant bent, moet u eerst informatie verstrekken om een account aan te maken en een tenant aan te maken voor uw proefperiode.</span><span class="sxs-lookup"><span data-stu-id="1b7df-244">I you are a new customer, you must first provide information to establish an account and create a tenant for your trial period.</span></span> <span data-ttu-id="1b7df-245">Zodra dit is gebeurd, kunt u app-beheer toevoegen aan de proefversie.</span><span class="sxs-lookup"><span data-stu-id="1b7df-245">Once this is done you can add app governance to the trial.</span></span>

<span data-ttu-id="1b7df-246">Voor nieuwe Microsoft 365-klanten:</span><span class="sxs-lookup"><span data-stu-id="1b7df-246">For new Microsoft 365 customers:</span></span>

1. <span data-ttu-id="1b7df-247">Klik boven aan deze pagina op de knop **Gratis account**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-247">At the top of this page, click the **Free Account** button.</span></span>
1. <span data-ttu-id="1b7df-248">Klik onder **Probeer Microsoft 365 voor Bedrijven** op **Probeer 1 maand gratis**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-248">Under **Try Microsoft 365 for business** click **Try 1 month free**.</span></span>

<span data-ttu-id="1b7df-249">Voor beide:</span><span class="sxs-lookup"><span data-stu-id="1b7df-249">For both:</span></span>

1. <span data-ttu-id="1b7df-250">Geef in de aanmeldingsportal uw e-mailadres op dat u voor de proefversie wilt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="1b7df-250">In the sign-up portal, provide your email address to use for the trial.</span></span> <span data-ttu-id="1b7df-251">Als u een bestaande klant bent, gebruikt u het e-mailadres dat is gekoppeld aan uw account.</span><span class="sxs-lookup"><span data-stu-id="1b7df-251">If you are an existing customer, use the email associated with your account.</span></span> <span data-ttu-id="1b7df-252">Klik op **Volgende**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-252">Click **Next**</span></span>
1. <span data-ttu-id="1b7df-253">Nadat u zich hebt aangemeld, klikt u op **Probeer nu** om de gratis proefversie te downloaden.</span><span class="sxs-lookup"><span data-stu-id="1b7df-253">Once you have signed in, click **Try now** to get the free trial.</span></span>
1. <span data-ttu-id="1b7df-254">Klik op **Doorgaan** om de pagina te sluiten en de installatie van de proefversie te starten.</span><span class="sxs-lookup"><span data-stu-id="1b7df-254">Click **Continue** to close page and begin trial setup.</span></span> <span data-ttu-id="1b7df-255">Voor nieuwe app-beheerklanten duurt het tot twee uur voordat uw app-beheerexemplaar beschikbaar is.</span><span class="sxs-lookup"><span data-stu-id="1b7df-255">For new app governance customers, it will take up to two hours for your app governance instance to become available.</span></span> <span data-ttu-id="1b7df-256">Voor bestaande klanten is er geen onderbreking van bestaande services.</span><span class="sxs-lookup"><span data-stu-id="1b7df-256">For existing customers, there will be no interruption of existing services.</span></span>
  > [!NOTE]
<span data-ttu-id="1b7df-257">Als u nog geen account hebt, wordt u gevraagd een nieuw account in te stellen voordat u kunt doorgaan met de proefversie.</span><span class="sxs-lookup"><span data-stu-id="1b7df-257">If you do not already have an account you will be prompted to set up a new account before you can proceed with the trial.</span></span>

1. <span data-ttu-id="1b7df-258">Voer een beschikbare domeinnaam in voor uw AAD-tenant en klik op **Beschikbaarheid controleren**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-258">Enter in an available domain name for your AAD tenant and click **Check availability**.</span></span> <span data-ttu-id="1b7df-259">Er wordt automatisch een beheerdersrol toegewezen (als u geen bestaande rol voor app-beheer hebt) en u kunt later de domeinnaam altijd wijzigen en/of meer tenants aanschaffen via het Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="1b7df-259">You will automatically be assigned an Admin role (if you don’t have an existing role for app governance) and can always change the domain name and/or purchase more tenants later through the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="1b7df-260">Voer de gebruikersnaam en het wachtwoord in die u wilt gebruiken om u aan te melden bij uw account.</span><span class="sxs-lookup"><span data-stu-id="1b7df-260">Enter the username and password you would like to use to login to your account.</span></span> <span data-ttu-id="1b7df-261">Klik op **Registeren**.</span><span class="sxs-lookup"><span data-stu-id="1b7df-261">Click **Sign up**.</span></span>
1. <span data-ttu-id="1b7df-262">Klik op **Aan de slag** om naar de portal voor app-beheer te gaan of op **Uw abonnement beheren** om naar het Microsoft 365-beheercentrum te gaan.</span><span class="sxs-lookup"><span data-stu-id="1b7df-262">Click **Get started** to go to the app governance portal or **Manage your subscription** to go to the Microsoft 365 admin center.</span></span>
