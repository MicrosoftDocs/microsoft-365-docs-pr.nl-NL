---
title: Factureringsprofielen beheren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over hoe facturerings profielen facturen ondersteunen.
keywords: facturerings profiel, facturen, kosten, beheerde kosten
ms.openlocfilehash: de6d6cd65d9e83e7211bcdc33f1774aaec3d1729
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638445"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="110ce-104">Factureringsprofielen beheren</span><span class="sxs-lookup"><span data-stu-id="110ce-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="110ce-105">Het beheercentrum wordt gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="110ce-105">The admin center is changing.</span></span> <span data-ttu-id="110ce-106">Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="110ce-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="110ce-107">Voor commerciële klanten die producten en services van Microsoft kopen, kunt u met facturerings profielen aanpassen welke items op uw factuur zijn opgenomen, en hoe u uw facturen betaalt.</span><span class="sxs-lookup"><span data-stu-id="110ce-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="110ce-108">Facturerings profielen bevatten de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="110ce-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="110ce-109">**Factureringsaccount** &ndash; Naam van de rekening waarop het profiel is betrekking</span><span class="sxs-lookup"><span data-stu-id="110ce-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="110ce-110">**Betaalwijzen** &ndash; Credit cards of betaalkaarten, bankrekeningen, cheques of overschrijving</span><span class="sxs-lookup"><span data-stu-id="110ce-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="110ce-111">**Contact gegevens** &ndash; Factuuradres en naam van een contactpersoon</span><span class="sxs-lookup"><span data-stu-id="110ce-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="110ce-112">**Factuurinstellingen** &ndash; Valuta op basis van het land van de factureringsrekening, een optioneel ko-nummer en de optie om facturen te ontvangen als e-mailbijlagen</span><span class="sxs-lookup"><span data-stu-id="110ce-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="110ce-113">**Machtigingen** &ndash; Machtigingen voor het wijzigen van het facturerings profiel, het betalen van facturen of het gebruik van de betaalmethode voor het facturerings profiel om aankopen te doen</span><span class="sxs-lookup"><span data-stu-id="110ce-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="110ce-114">Gebruik facturerings profielen om uw aankopen te regelen en uw factuur aan te passen.</span><span class="sxs-lookup"><span data-stu-id="110ce-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="110ce-115">Voor de producten die met het facturerings profiel zijn gekocht, wordt een maandelijkse factuur gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="110ce-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="110ce-116">U kunt de factuur aanpassen, zoals de voorkeuren voor de Aankooporder en de e-mail factuur.</span><span class="sxs-lookup"><span data-stu-id="110ce-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="110ce-117">Er wordt automatisch een facturerings profiel gemaakt voor uw factuur account tijdens uw eerste aankoop.</span><span class="sxs-lookup"><span data-stu-id="110ce-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="110ce-118">U kunt op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">facturerings profielen</a> facturerings profielen maken om meer facturen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="110ce-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="110ce-119">U kunt bijvoorbeeld verschillende facturerings profielen gebruiken wanneer u voor elke afdeling in uw organisatie aankopen doet.</span><span class="sxs-lookup"><span data-stu-id="110ce-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="110ce-120">Op de volgende factuurdatum ontvangt u voor elk facturerings profiel een factuur.</span><span class="sxs-lookup"><span data-stu-id="110ce-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="110ce-121">Rollen van facturerings profielen</span><span class="sxs-lookup"><span data-stu-id="110ce-121">Billing profile roles</span></span>

<span data-ttu-id="110ce-122">Rollen aan facturerings profielen beschikken over machtigingen voor het beheren van aankopen, en het weergeven en beheren van facturen.</span><span class="sxs-lookup"><span data-stu-id="110ce-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="110ce-123">Wijs deze rollen toe aan gebruikers die facturen bijhouden, organiseren en betalen, zoals leden van het aanschaffings team in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="110ce-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="110ce-124">Rol</span><span class="sxs-lookup"><span data-stu-id="110ce-124">Role</span></span>                          | <span data-ttu-id="110ce-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="110ce-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="110ce-126">Eigenaar van het facturerings profiel</span><span class="sxs-lookup"><span data-stu-id="110ce-126">Billing profile owner</span></span>         | <span data-ttu-id="110ce-127">Alles beheren voor een facturerings profiel</span><span class="sxs-lookup"><span data-stu-id="110ce-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="110ce-128">Inzender voor facturerings profielen</span><span class="sxs-lookup"><span data-stu-id="110ce-128">Billing profile contributor</span></span>   | <span data-ttu-id="110ce-129">Alles beheren behalve machtigingen in een facturerings profiel</span><span class="sxs-lookup"><span data-stu-id="110ce-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="110ce-130">Facturerings profiel lezer</span><span class="sxs-lookup"><span data-stu-id="110ce-130">Billing profile reader</span></span>        | <span data-ttu-id="110ce-131">Alleen-lezen weergave van alles in een facturerings profiel</span><span class="sxs-lookup"><span data-stu-id="110ce-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="110ce-132">Factuur Manager</span><span class="sxs-lookup"><span data-stu-id="110ce-132">Invoice manager</span></span>               | <span data-ttu-id="110ce-133">Rekeningen weergeven en betalen, en heeft een alleen-lezen weergave van alles in een facturerings profiel</span><span class="sxs-lookup"><span data-stu-id="110ce-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="110ce-134">Facturerings profielen weergeven</span><span class="sxs-lookup"><span data-stu-id="110ce-134">View billing profiles</span></span>

1. <span data-ttu-id="110ce-135">Ga in het Beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a>.</span><span class="sxs-lookup"><span data-stu-id="110ce-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="110ce-136">Kies **facturerings profielen**en kies vervolgens een factuur profiel in de lijst.</span><span class="sxs-lookup"><span data-stu-id="110ce-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="110ce-137">Op het tabblad **overzicht** kunt u details van facturerings profielen bewerken en het verzenden van een factuur per e-mail in-of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="110ce-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="110ce-138">Op het tabblad **machtigingen** kunt u rollen toewijzen aan gebruikers om facturen te betalen.</span><span class="sxs-lookup"><span data-stu-id="110ce-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="110ce-139">Op het tabblad **tegoed saldo van Azure** kan Azure-klanten de geschiedenis van het transactiesaldo zien voor de Azure-tegoeden die door dat facturerings profiel worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="110ce-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="110ce-140">Op het tabblad **Azure-tegoeden** kan Azure-klanten een lijst met Azure-tegoeden zien dat is gekoppeld aan het facturerings profiel en de vervaldatum.</span><span class="sxs-lookup"><span data-stu-id="110ce-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="110ce-141">Als u geen Azure-tegoed hebt, wordt de tabbladen **Azure tegoed saldo** en **Azure tegoed** niet weergegeven.</span><span class="sxs-lookup"><span data-stu-id="110ce-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="110ce-142">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="110ce-142">Need help?</span></span> <span data-ttu-id="110ce-143">Neem contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="110ce-143">Contact support.</span></span>

<span data-ttu-id="110ce-144">Als u vragen hebt of hulp nodig hebt bij uw Azure-kosten, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">maakt u een ondersteuningsverzoek met Azure-ondersteuning</a>.</span><span class="sxs-lookup"><span data-stu-id="110ce-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="110ce-145">[Neem contact op met de ondersteuning voor zakelijke producten](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)als u vragen hebt of hulp nodig hebt bij uw factuur profiel in microsoft 365-Beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="110ce-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
