---
title: Factureringsmeldingen en bijlagen voor facturen beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: Lees hoe u kunt beheren wie e-mailberichten voor factureringsmelding en factuurbijlagen ontvangt.
ms.date: 03/17/2021
ms.openlocfilehash: a0c7de8638a227d432ff2c5a0d4839fa8f66582c
ms.sourcegitcommit: 787fb30fdae6d49347a87f4baae3cd140067e573
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52998762"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a><span data-ttu-id="63e11-103">Factureringsmeldingen en bijlagen voor facturen beheren</span><span class="sxs-lookup"><span data-stu-id="63e11-103">Manage billing notifications and invoice attachments</span></span>

<span data-ttu-id="63e11-104">Op **de pagina Factureringsmeldingen** kunt u beheren wie e-mailberichten voor factureringsmeldingen voor uw organisatie ontvangt.</span><span class="sxs-lookup"><span data-stu-id="63e11-104">The **Billing notifications** page lets you manage who receives billing notification emails for your organization.</span></span> <span data-ttu-id="63e11-105">De pagina biedt ook de optie om de facturen van uw organisatie als [e-mailbijlagen te ontvangen.](#receive-your-organizations-invoices-as-email-attachments)</span><span class="sxs-lookup"><span data-stu-id="63e11-105">The page also provides the option to [receive your organization's invoices as email attachments](#receive-your-organizations-invoices-as-email-attachments).</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="63e11-106">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="63e11-106">Before you begin</span></span>

<span data-ttu-id="63e11-107">U moet een globale beheerder zijn om de stappen uit te voeren die in dit artikel worden beschreven.</span><span class="sxs-lookup"><span data-stu-id="63e11-107">You must be a Global admin to do the steps described in this article.</span></span> <span data-ttu-id="63e11-108">Factureringsbeheerders kunnen enkele van deze wijzigingen aanbrengen, zoals wordt vermeld in de onderstaande secties.</span><span class="sxs-lookup"><span data-stu-id="63e11-108">Billing admins can make some of these changes, as noted in the sections below.</span></span> <span data-ttu-id="63e11-109">Zie[Over beheerdersrollen](../../admin/add-users/about-admin-roles.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="63e11-109">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>

## <a name="change-the-language-you-receive-email-in"></a><span data-ttu-id="63e11-110">De taal wijzigen waarin u e-mail ontvangt</span><span class="sxs-lookup"><span data-stu-id="63e11-110">Change the language you receive email in</span></span>

> [!NOTE]
> <span data-ttu-id="63e11-111">Factureringsbeheerders kunnen ook de stappen in deze sectie doen.</span><span class="sxs-lookup"><span data-stu-id="63e11-111">Billing admins can also do the steps in this section.</span></span>

<span data-ttu-id="63e11-112">E-mailberichten met factureringsmeldingen worden verzonden in de voorkeurstaal van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="63e11-112">Billing notification emails are sent in your organization’s preferred language.</span></span> <span data-ttu-id="63e11-113">Als u de voorkeurstaal wilt wijzigen, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="63e11-113">To change the preferred language, use the following steps.</span></span>

1. <span data-ttu-id="63e11-114">Ga in Microsoft 365-beheercentrum naar de pagina  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Factureringsmeldingen.</a></span><span class="sxs-lookup"><span data-stu-id="63e11-114">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="63e11-115">Selecteer in **de sectie Instellingen voor** factureringsmeldingen de optie **Meldingsinstellingen bewerken.**</span><span class="sxs-lookup"><span data-stu-id="63e11-115">In the **Billing notification settings** section, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="63e11-116">Selecteer in **het deelvenster Instellingen voor** factureringsmeldingen onder **Voorkeurstaal** de taal die u wilt gebruiken en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="63e11-116">In the **Billing notification settings** pane, under **Preferred language** select the language you want to use, then select **Save**.</span></span>

## <a name="change-who-receives-billing-notifications"></a><span data-ttu-id="63e11-117">Wijzigen wie factureringsmeldingen ontvangt</span><span class="sxs-lookup"><span data-stu-id="63e11-117">Change who receives billing notifications</span></span>

<span data-ttu-id="63e11-118">De factureringsmeldingen van uw organisatie worden verzonden naar het primaire en alternatieve e-mailadres van elke globale en factureringsbeheerder. Als u wilt wijzigen welke gebruikers de rol globale of factureringsbeheerder hebben, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="63e11-118">Your organization's billing notifications are sent to the primary and alternate email address of every Global and Billing admin. To change which users have the Global or Billing admin role, use the following steps.</span></span>

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="63e11-119">Beheerdersrollen toewijzen met behulp van de pagina Factureringsmeldingen</span><span class="sxs-lookup"><span data-stu-id="63e11-119">Assign admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="63e11-120">In het beheercentrum gaat u naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Factureringsmeldingen</a>.</span><span class="sxs-lookup"><span data-stu-id="63e11-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="63e11-121">Selecteer in de sectie Beheerders die  **factureringsmeldingen** ontvangen de koppeling Factureringsbeheerder of Globale **beheerder** in de beschrijvingstekst.</span><span class="sxs-lookup"><span data-stu-id="63e11-121">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="63e11-122">Selecteer in het rechterdeelvenster op het tabblad Toegewezen **beheerders** de optie **Toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="63e11-122">In the right pane, on the **Assigned admins** tab, select **Add**.</span></span>
4. <span data-ttu-id="63e11-123">Typ in **het deelvenster** Beheerders toevoegen de weergavenaam of gebruikersnaam van de gebruiker en selecteer de gebruiker in de lijst met suggesties.</span><span class="sxs-lookup"><span data-stu-id="63e11-123">In the **Add admins** pane, type the user’s display name or username, and then select the user from the list of suggestions.</span></span>
5. <span data-ttu-id="63e11-124">Voeg meerdere gebruikers toe totdat u klaar bent.</span><span class="sxs-lookup"><span data-stu-id="63e11-124">Add multiple users until you’re done.</span></span>
6. <span data-ttu-id="63e11-125">Kies **Opslaan**.</span><span class="sxs-lookup"><span data-stu-id="63e11-125">Select **Save**.</span></span> <span data-ttu-id="63e11-126">De gebruiker wordt toegevoegd aan de lijst met toegewezen beheerders.</span><span class="sxs-lookup"><span data-stu-id="63e11-126">The user is added to the list of assigned admins.</span></span>

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a><span data-ttu-id="63e11-127">Beheerdersrollen verwijderen met behulp van de pagina Factureringsmeldingen</span><span class="sxs-lookup"><span data-stu-id="63e11-127">Remove admin roles by using the Billing notifications page</span></span>

1. <span data-ttu-id="63e11-128">In het beheercentrum gaat u naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Factureringsmeldingen</a>.</span><span class="sxs-lookup"><span data-stu-id="63e11-128">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="63e11-129">Selecteer in de sectie Beheerders die  **factureringsmeldingen** ontvangen de koppeling Factureringsbeheerder of Globale **beheerder** in de beschrijvingstekst.</span><span class="sxs-lookup"><span data-stu-id="63e11-129">In the **Admins receiving billing notifications** section, select the **Billing administrator** or **Global administrator** link in the description text.</span></span>
3. <span data-ttu-id="63e11-130">Selecteer in het rechterdeelvenster op het tabblad Toegewezen **beheerders** de gebruikers die u uit de rol wilt verwijderen en selecteer **vervolgens Verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="63e11-130">In the right pane, on the **Assigned admins** tab, select the users to remove from the role, and then select **Remove**.</span></span>
4. <span data-ttu-id="63e11-131">Selecteer verwijderen in het **bevestigingsvak.**</span><span class="sxs-lookup"><span data-stu-id="63e11-131">In the confirmation box, select **Remove**.</span></span> <span data-ttu-id="63e11-132">De gebruiker wordt verwijderd uit de lijst met toegewezen beheerders.</span><span class="sxs-lookup"><span data-stu-id="63e11-132">The user is removed from the list of assigned admins.</span></span>

## <a name="change-the-email-addresses-for-admins"></a><span data-ttu-id="63e11-133">De e-mailadressen voor beheerders wijzigen</span><span class="sxs-lookup"><span data-stu-id="63e11-133">Change the email addresses for admins</span></span>

<span data-ttu-id="63e11-134">Als u het primaire en alternatieve e-mailadres van andere beheerders in uw organisatie wilt wijzigen, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="63e11-134">To change the primary and alternate email address of other admins in your organization, use the following steps.</span></span>

> [!NOTE]
> <span data-ttu-id="63e11-135">Factureringsbeheerders kunnen hun eigen primaire en alternatieve e-mailadressen wijzigen, maar niet voor andere beheerders.</span><span class="sxs-lookup"><span data-stu-id="63e11-135">Billing admins can change their own primary and alternate email addresses, but not for other admins.</span></span>

1. <span data-ttu-id="63e11-136">In het beheercentrum gaat u naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Factureringsmeldingen</a>.</span><span class="sxs-lookup"><span data-stu-id="63e11-136">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="63e11-137">Selecteer een naam in de sectie Beheerders die **factureringsmeldingen** ontvangen.</span><span class="sxs-lookup"><span data-stu-id="63e11-137">In the **Admins receiving billing notifications** section, select a name.</span></span>
3. <span data-ttu-id="63e11-138">Voeg in het rechterdeelvenster zo nodig het primaire en alternatieve e-mailadres toe of werk deze bij en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="63e11-138">In the right pane, add or update the primary and alternate email address as needed, then select **Save**.</span></span>

## <a name="change-your-organizations-contact-email"></a><span data-ttu-id="63e11-139">Het e-mailadres van de contactpersoon van uw organisatie wijzigen</span><span class="sxs-lookup"><span data-stu-id="63e11-139">Change your organization's contact email</span></span>

<span data-ttu-id="63e11-140">Naast uw globale en factureringsbeheerders sturen we factureringsmeldingen naar het e-mailadres van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="63e11-140">In addition to your Global and Billing admins, we send billing notifications to your organization's contact email address.</span></span> <span data-ttu-id="63e11-141">Als u het e-mailadres wilt wijzigen, gebruikt u de volgende stappen.</span><span class="sxs-lookup"><span data-stu-id="63e11-141">To change the email address, use the following steps.</span></span>

1. <span data-ttu-id="63e11-142">In het beheercentrum gaat u naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Factureringsmeldingen</a>.</span><span class="sxs-lookup"><span data-stu-id="63e11-142">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="63e11-143">Selecteer **onder Organisatiecontactcontactpunt dat factureringsmeldingen ontvangt** de contactpersoon van de organisatie.</span><span class="sxs-lookup"><span data-stu-id="63e11-143">Under **Organization contact receiving billing notifications**, select the organization contact.</span></span>
3. <span data-ttu-id="63e11-144">Typ in het rechterdeelvenster het e-mailadres dat u wilt gebruiken en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="63e11-144">In the right pane, type the email address that you want to use, then select **Save**.</span></span>

## <a name="receive-your-organizations-invoices-as-email-attachments"></a><span data-ttu-id="63e11-145">Facturen van uw organisatie ontvangen als e-mailbijlagen</span><span class="sxs-lookup"><span data-stu-id="63e11-145">Receive your organization's invoices as email attachments</span></span>

<span data-ttu-id="63e11-146">U kunt een kopie van de factuur van uw organisatie als PDF-bestand toevoegen aan e-mailberichten met factuurmeldingen wanneer een nieuwe factuur gereed is.</span><span class="sxs-lookup"><span data-stu-id="63e11-146">You can have a copy of your organization's invoice attached as a PDF file to invoice notification emails when a new invoice is ready.</span></span> <span data-ttu-id="63e11-147">Gebruik de volgende stappen om facturen als bijlagen te ontvangen.</span><span class="sxs-lookup"><span data-stu-id="63e11-147">Use the following steps to receive invoices as attachments.</span></span>

1. <span data-ttu-id="63e11-148">In het beheercentrum gaat u naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Factureringsmeldingen</a>.</span><span class="sxs-lookup"><span data-stu-id="63e11-148">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Billing notifications</a> page.</span></span>
2. <span data-ttu-id="63e11-149">Selecteer **onder Instellingen voor factureringsmeldingen** de optie **Meldingsinstellingen bewerken.**</span><span class="sxs-lookup"><span data-stu-id="63e11-149">Under **Billing notification settings**, select **Edit notification settings**.</span></span>
3. <span data-ttu-id="63e11-150">Schakel in **het deelvenster Instellingen voor** factureringsmeldingen onder Een **PDF-bestand** bij uw factuur-e-mailberichten bijmaken het selectievakje in en selecteer **opslaan.**</span><span class="sxs-lookup"><span data-stu-id="63e11-150">In the **Billing notification settings** pane, under **Attach a PDF to your invoice emails**, check the checkbox, then select **Save**.</span></span>

<span data-ttu-id="63e11-151">Als u de factuurbijlage op elk moment niet meer wilt ontvangen, volgt u de bovenstaande stappen en leegt u het selectievakje Een **PDF** bij uw factuur-e-mailberichten toevoegen in stap 3 uit.</span><span class="sxs-lookup"><span data-stu-id="63e11-151">To stop receiving the invoice attachment at any time, follow the steps above and clear the **Attach a PDF to your invoice  emails** checkbox in step 3.</span></span>

## <a name="what-if-i-have-a-billing-profile"></a><span data-ttu-id="63e11-152">Wat moet ik doen als ik een factureringsprofiel heb?</span><span class="sxs-lookup"><span data-stu-id="63e11-152">What if I have a billing profile?</span></span>

<span data-ttu-id="63e11-153">Als u een factureringsprofiel hebt, kunnen sommige stappen die in dit artikel worden beschreven, enigszins afwijken voor sommige van uw abonnementen.</span><span class="sxs-lookup"><span data-stu-id="63e11-153">If you have a billing profile, some of the steps described in this article might be slightly different for some of your subscriptions.</span></span> <span data-ttu-id="63e11-154">In deze sectie worden deze verschillen beschreven.</span><span class="sxs-lookup"><span data-stu-id="63e11-154">This section describes those differences.</span></span> [<span data-ttu-id="63e11-155">Hoe weet ik of ik een factureringsprofiel heb?</span><span class="sxs-lookup"><span data-stu-id="63e11-155">How do I know if I have a billing profile?</span></span>](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a><span data-ttu-id="63e11-156">Wie ontvangt u factureringsmeldingen?</span><span class="sxs-lookup"><span data-stu-id="63e11-156">Who receives Billing notifications?</span></span>

<span data-ttu-id="63e11-157">E-mailberichten over factureringsmeldingen worden verzonden naar de primaire en alternatieve e-mailadressen voor gebruikers die een van de volgende rollen krijgen toegewezen:</span><span class="sxs-lookup"><span data-stu-id="63e11-157">Billing notification emails are sent to the primary and alternate email addresses for users who are assigned one of the following roles:</span></span>

- <span data-ttu-id="63e11-158">Factureringsprofieleigenaar</span><span class="sxs-lookup"><span data-stu-id="63e11-158">Billing profile owner</span></span>
- <span data-ttu-id="63e11-159">Factureringsprofielbetaler</span><span class="sxs-lookup"><span data-stu-id="63e11-159">Billing profile contributor</span></span>
- <span data-ttu-id="63e11-160">Factuurbeheer</span><span class="sxs-lookup"><span data-stu-id="63e11-160">Invoice manager</span></span>

<span data-ttu-id="63e11-161">Zie Microsoft Customer Agreement administrative roles in Azure voor meer informatie over factureringsprofielrollen en hoe u deze kunt [beheren.](/azure/cost-management-billing/manage/understand-mca-roles)</span><span class="sxs-lookup"><span data-stu-id="63e11-161">To learn more about billing profile roles and how to manage them, see [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).</span></span>

<span data-ttu-id="63e11-162">Als u wilt wijzigen wie de factureringsmeldingen van uw organisatie ontvangt, gebruikt u de volgende stappen om de rollen te wijzigen die aan gebruikers zijn toegewezen.</span><span class="sxs-lookup"><span data-stu-id="63e11-162">To change who receives your organization’s billing notifications, use the following steps to change the roles assigned to users.</span></span>

1. <span data-ttu-id="63e11-163">Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Factureringsfacturen & betalingen.</a></span><span class="sxs-lookup"><span data-stu-id="63e11-163">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="63e11-164">Selecteer op **het tabblad** Factureringsprofiel een factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="63e11-164">On the **Billing profile** tab, select a billing profile.</span></span>
3. <span data-ttu-id="63e11-165">Wijs in **de sectie Factureringsprofielrollen** rollen toe aan of verwijder rollen voor de eigenaar van het factureringsprofiel,  **factureringsprofielbetaler** of **Factuurmanager.**</span><span class="sxs-lookup"><span data-stu-id="63e11-165">In the **Billing profile roles** section, assign or remove roles for **Billing profile owner**, **Billing profile contributor**, or **Invoice manager**.</span></span>

### <a name="receive-invoices-as-email-attachments"></a><span data-ttu-id="63e11-166">Facturen als e-mailbijlagen ontvangen</span><span class="sxs-lookup"><span data-stu-id="63e11-166">Receive invoices as email attachments</span></span>

<span data-ttu-id="63e11-167">Als u uw facturen wilt ontvangen als bijlagen bij uw factuurmeldingen, gebruikt u de volgende stappen om deze instelling in te stellen voor een specifiek factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="63e11-167">To receive your invoices as attachments to your invoice notifications, use the following steps to turn on this setting for a specific billing profile.</span></span>

1. <span data-ttu-id="63e11-168">Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Factureringsfacturen & betalingen.</a></span><span class="sxs-lookup"><span data-stu-id="63e11-168">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="63e11-169">Selecteer het **tabblad Factureringsprofielen** en selecteer vervolgens een factureringsprofiel in de lijst.</span><span class="sxs-lookup"><span data-stu-id="63e11-169">Select the **Billing profiles** tab, then select a billing profile from the list.</span></span>
3. <span data-ttu-id="63e11-170">Schakel op de pagina met **factureringsprofielgegevens** onder Facturen in e-mailbijlagen downloaden de wisselknop over op **Aan.**</span><span class="sxs-lookup"><span data-stu-id="63e11-170">On the billing profile details page, under **Get invoices in email attachments**, switch the toggle to **On**.</span></span>

## <a name="related-content"></a><span data-ttu-id="63e11-171">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="63e11-171">Related content</span></span>

<span data-ttu-id="63e11-172">[Uw rekening of factuur bekijken](view-your-bill-or-invoice.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="63e11-172">[View your bill or invoice](view-your-bill-or-invoice.md) (article)</span></span>\
<span data-ttu-id="63e11-173">[Factureringsgegevens voor Microsoft 365 voor bedrijven in Mexico](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (artikel) </span><span class="sxs-lookup"><span data-stu-id="63e11-173">[Billing information for Microsoft 365 for business in Mexico](/microsoft-365/commerce/billing-and-payments/mexico-billing-info) (article) </span></span>\
<span data-ttu-id="63e11-174">[Uw factuur of factuur voor Microsoft 365 voor bedrijven](understand-your-invoice2.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="63e11-174">[Understand your bill or invoice for Microsoft 365 for business](understand-your-invoice2.md) (article)</span></span>\
<span data-ttu-id="63e11-175">[Gebruikers toevoegen en tegelijkertijd licenties](../../admin/add-users/add-users.md) toewijzen (artikel)</span><span class="sxs-lookup"><span data-stu-id="63e11-175">[Add users and assign licenses at the same time](../../admin/add-users/add-users.md) (article)</span></span>
