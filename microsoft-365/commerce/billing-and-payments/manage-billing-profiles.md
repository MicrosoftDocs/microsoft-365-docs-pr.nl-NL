---
title: Factureringsprofielen beheren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- commerce
ms.custom: ''
search.appverid:
- MET150
description: Meer informatie over hoe factureringsprofielen facturen ondersteunen.
keywords: factureringsprofiel, facturen, kosten, beheerde kosten
ms.openlocfilehash: f93ca5af11ba416fecd13fcceffe75055a776553
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140888"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="80d1f-104">Factureringsprofielen beheren</span><span class="sxs-lookup"><span data-stu-id="80d1f-104">Manage billing profiles</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="80d1f-105">Het beheercentrum verandert.</span><span class="sxs-lookup"><span data-stu-id="80d1f-105">The admin center is changing.</span></span> <span data-ttu-id="80d1f-106">Als uw ervaring niet overeenkomt met de hier gepresenteerde details, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="80d1f-106">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="80d1f-107">Voor commerciële klanten die producten en services van Microsoft kopen, u met factureringsprofielen aanpassen welke artikelen op uw factuur zijn opgenomen en hoe u uw facturen betaalt.</span><span class="sxs-lookup"><span data-stu-id="80d1f-107">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="80d1f-108">Factureringsprofielen bevatten de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="80d1f-108">Billing profiles include the following information:</span></span>

- <span data-ttu-id="80d1f-109">**Factuurrekening** &ndash; Naam van het factureringsaccount waaraan het profiel is gerelateerd</span><span class="sxs-lookup"><span data-stu-id="80d1f-109">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="80d1f-110">**Betalingsmethoden** &ndash; Creditcards of betaalpassen, bankrekeningen, cheque of overschrijving</span><span class="sxs-lookup"><span data-stu-id="80d1f-110">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="80d1f-111">**Contactgegevens** &ndash; Factuuradres en een naam van contactpersonen</span><span class="sxs-lookup"><span data-stu-id="80d1f-111">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="80d1f-112">**Factuurinstellingen** &ndash; Valuta op basis van het land van de factureringsaccount, een optioneel PO-nummer en de optie om facturen als e-mailbijlagen te ontvangen</span><span class="sxs-lookup"><span data-stu-id="80d1f-112">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="80d1f-113">**Machtigingen** &ndash; waarmee u het factureringsprofiel wijzigen, rekeningen betalen of de betalingsmethode in het factureringsprofiel gebruiken om aankopen te doen</span><span class="sxs-lookup"><span data-stu-id="80d1f-113">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="80d1f-114">Gebruik factureringsprofielen om uw aankopen te beheren en uw factuur aan te passen.</span><span class="sxs-lookup"><span data-stu-id="80d1f-114">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="80d1f-115">Er wordt een maandelijkse factuur gegenereerd voor de producten die zijn gekocht met het factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="80d1f-115">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="80d1f-116">U de factuur aanpassen, zoals het aankoopordernummer bijwerken en de voorkeur voor e-mailfactuur.</span><span class="sxs-lookup"><span data-stu-id="80d1f-116">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="80d1f-117">Er wordt automatisch een factureringsprofiel gemaakt voor uw factureringsaccount tijdens uw eerste aankoop.</span><span class="sxs-lookup"><span data-stu-id="80d1f-117">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="80d1f-118">U factureringsprofielen maken op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen</a> om meer facturen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="80d1f-118">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="80d1f-119">U bijvoorbeeld verschillende factureringsprofielen gebruiken wanneer u aankopen doet voor elke afdeling in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="80d1f-119">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="80d1f-120">Op uw volgende factureringsdatum ontvangt u een factuur voor elk factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="80d1f-120">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="80d1f-121">Rollen voor factureringsprofielen</span><span class="sxs-lookup"><span data-stu-id="80d1f-121">Billing profile roles</span></span>

<span data-ttu-id="80d1f-122">Rollen in factureringsprofielen hebben machtigingen om aankopen te beheren en facturen te bekijken en te beheren.</span><span class="sxs-lookup"><span data-stu-id="80d1f-122">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="80d1f-123">Wijs deze rollen toe aan gebruikers die facturen bijhouden, ordenen en betalen, zoals leden van het inkoopteam in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="80d1f-123">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="80d1f-124">Rol</span><span class="sxs-lookup"><span data-stu-id="80d1f-124">Role</span></span>                          | <span data-ttu-id="80d1f-125">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="80d1f-125">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="80d1f-126">Eigenaar van het factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="80d1f-126">Billing profile owner</span></span>         | <span data-ttu-id="80d1f-127">Alles beheren voor een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="80d1f-127">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="80d1f-128">Bijdrager factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="80d1f-128">Billing profile contributor</span></span>   | <span data-ttu-id="80d1f-129">Alles beheren behalve machtigingen in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="80d1f-129">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="80d1f-130">Factureringsprofiellezer</span><span class="sxs-lookup"><span data-stu-id="80d1f-130">Billing profile reader</span></span>        | <span data-ttu-id="80d1f-131">Alleen-lezen weergave van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="80d1f-131">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="80d1f-132">Factuurbeheer</span><span class="sxs-lookup"><span data-stu-id="80d1f-132">Invoice manager</span></span>               | <span data-ttu-id="80d1f-133">Rekeningen bekijken en betalen en heeft een alleen-lezen weergave van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="80d1f-133">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="80d1f-134">Factureringsprofielen weergeven</span><span class="sxs-lookup"><span data-stu-id="80d1f-134">View billing profiles</span></span>

1. <span data-ttu-id="80d1f-135">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Facturen en betalingen</a>.</span><span class="sxs-lookup"><span data-stu-id="80d1f-135">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="80d1f-136">Kies **Factureringsprofielen**en kies vervolgens een factureringsprofiel in de lijst.</span><span class="sxs-lookup"><span data-stu-id="80d1f-136">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="80d1f-137">Op het tabblad **Overzicht** u de details van het factureringsprofiel bewerken en het verzenden van een factuur per e-mail in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="80d1f-137">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="80d1f-138">Op het tabblad **Machtigingen** u rollen toewijzen aan gebruikers om facturen te betalen.</span><span class="sxs-lookup"><span data-stu-id="80d1f-138">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="80d1f-139">Op het tabblad **Azure-tegoed kunnen** Azure-klanten de transactiebalansgeschiedenis zien voor de Azure-tegoeden die door dat factureringsprofiel worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="80d1f-139">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="80d1f-140">Op het tabblad **Azure-credits** kunnen Azure-klanten een lijst met Azure-tegoeden zien die zijn gekoppeld aan dat factureringsprofiel en hun vervaldatums.</span><span class="sxs-lookup"><span data-stu-id="80d1f-140">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="80d1f-141">Als u geen Azure-tegoedhebt, ziet u de tabbladen **Azure-tegoed** of **Azure-tegoed** niet.</span><span class="sxs-lookup"><span data-stu-id="80d1f-141">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="80d1f-142">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="80d1f-142">Need help?</span></span> <span data-ttu-id="80d1f-143">Neem contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="80d1f-143">Contact support.</span></span>

<span data-ttu-id="80d1f-144">Als u vragen hebt of hulp nodig hebt bij uw Azure-kosten, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">maakt u een ondersteuningsaanvraag met Azure-ondersteuning.</a></span><span class="sxs-lookup"><span data-stu-id="80d1f-144">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="80d1f-145">Als u vragen hebt of hulp nodig hebt bij uw factureringsprofiel in het Microsoft 365-beheercentrum, neemt u [contact op met de ondersteuning voor zakelijke producten.](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="80d1f-145">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
