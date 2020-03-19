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
ms.openlocfilehash: c9bd089843bcb620dc3feb8ec3e8f946cd739d17
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42812796"
---
# <a name="manage-billing-profiles"></a><span data-ttu-id="a0518-104">Factureringsprofielen beheren</span><span class="sxs-lookup"><span data-stu-id="a0518-104">Manage billing profiles</span></span>
<span data-ttu-id="a0518-105">Voor commerciële klanten die producten en services bij Microsoft kopen, u met factureringsprofielen aanpassen welke artikelen op uw factuur zijn opgenomen en hoe u uw facturen betaalt.</span><span class="sxs-lookup"><span data-stu-id="a0518-105">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="a0518-106">Factureringsprofielen bevatten de volgende gegevens:</span><span class="sxs-lookup"><span data-stu-id="a0518-106">Billing profiles include the following information:</span></span>

- <span data-ttu-id="a0518-107">**Factureringsaccount** &ndash; Naam van het factureringsaccount waaraan het profiel is gerelateerd</span><span class="sxs-lookup"><span data-stu-id="a0518-107">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="a0518-108">**Betalingsmethoden** &ndash; Creditcards of betaalpassen, bankrekeningen, cheque of overschrijving</span><span class="sxs-lookup"><span data-stu-id="a0518-108">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="a0518-109">**Contactgegevens** &ndash; Factuuradres en een naam van de contactpersoon</span><span class="sxs-lookup"><span data-stu-id="a0518-109">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="a0518-110">**Factuurinstellingen** &ndash; Valuta op basis van het land van het factureringsaccount, een optioneel PO-nummer en de optie om facturen als e-mailbijlagen te ontvangen</span><span class="sxs-lookup"><span data-stu-id="a0518-110">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="a0518-111">Machtigingen machtigingen waarmee u het factureringsprofiel wijzigen, rekeningen betalen of de betalingsmethode op het **factureringsprofiel** &ndash; gebruiken om aankopen te doen</span><span class="sxs-lookup"><span data-stu-id="a0518-111">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="a0518-112">Gebruik factureringsprofielen om uw aankopen te beheren en uw factuur aan te passen.</span><span class="sxs-lookup"><span data-stu-id="a0518-112">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="a0518-113">Er wordt een maandelijkse factuur gegenereerd voor de producten die zijn gekocht met het factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="a0518-113">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="a0518-114">U de factuur aanpassen, zoals het aankoopordernummer bijwerken en de voorkeur voor e-mailfactuur.</span><span class="sxs-lookup"><span data-stu-id="a0518-114">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="a0518-115">Tijdens uw eerste aankoop wordt automatisch een factureringsprofiel aangemaakt voor uw factureringsaccount.</span><span class="sxs-lookup"><span data-stu-id="a0518-115">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="a0518-116">U factureringsprofielen maken op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen</a> om meer facturen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="a0518-116">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="a0518-117">U bijvoorbeeld verschillende factureringsprofielen gebruiken wanneer u aankopen doet voor elke afdeling in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a0518-117">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="a0518-118">Op uw volgende factureringsdatum ontvangt u een factuur voor elk factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="a0518-118">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="a0518-119">Rollen van factureringsprofielen</span><span class="sxs-lookup"><span data-stu-id="a0518-119">Billing profile roles</span></span>

<span data-ttu-id="a0518-120">Rollen op factureringsprofielen hebben machtigingen om aankopen te beheren en facturen weer te geven en te beheren.</span><span class="sxs-lookup"><span data-stu-id="a0518-120">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="a0518-121">Wijs deze rollen toe aan gebruikers die facturen bijhouden, organiseren en betalen, zoals leden van het inkoopteam in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a0518-121">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="a0518-122">Rol</span><span class="sxs-lookup"><span data-stu-id="a0518-122">Role</span></span>                          | <span data-ttu-id="a0518-123">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="a0518-123">Description</span></span>                                                                       |
|-----------------------------  |---------------------------------------------------------------------------------  |
| <span data-ttu-id="a0518-124">Eigenaar van factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="a0518-124">Billing profile owner</span></span>         | <span data-ttu-id="a0518-125">Alles beheren voor een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="a0518-125">Manage everything for a billing profile</span></span>                                           |
| <span data-ttu-id="a0518-126">Bijdragevan het factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="a0518-126">Billing profile contributor</span></span>   | <span data-ttu-id="a0518-127">Alles beheren behalve machtigingen in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="a0518-127">Manage everything except permissions in a billing profile</span></span>                         |
| <span data-ttu-id="a0518-128">Factureringprofiellezer</span><span class="sxs-lookup"><span data-stu-id="a0518-128">Billing profile reader</span></span>        | <span data-ttu-id="a0518-129">Alleen-lezen van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="a0518-129">Read-only view of everything in a billing profile</span></span>                                 |
| <span data-ttu-id="a0518-130">Factuurmanager</span><span class="sxs-lookup"><span data-stu-id="a0518-130">Invoice manager</span></span>               | <span data-ttu-id="a0518-131">Rekeningen bekijken en betalen en heeft een alleen-lezen weergave van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="a0518-131">View and pay bills, and has a read-only view of everything in a billing profile</span></span>   |

## <a name="view-billing-profiles"></a><span data-ttu-id="a0518-132">Factureringsprofielen weergeven</span><span class="sxs-lookup"><span data-stu-id="a0518-132">View billing profiles</span></span>

1. <span data-ttu-id="a0518-133">Ga in het Beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Facturen en betalingen</a>.</span><span class="sxs-lookup"><span data-stu-id="a0518-133">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=848039" target="_blank">Bills & payments</a> page.</span></span>

2. <span data-ttu-id="a0518-134">Kies **Factureringsprofielen**en kies vervolgens een factureringsprofiel in de lijst.</span><span class="sxs-lookup"><span data-stu-id="a0518-134">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="a0518-135">Op het tabblad **Overzicht** u de gegevens van het factureringsprofiel bewerken en een factuur per e-mail in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="a0518-135">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>

    - <span data-ttu-id="a0518-136">Op het tabblad **Machtigingen** u rollen toewijzen aan gebruikers om facturen te betalen.</span><span class="sxs-lookup"><span data-stu-id="a0518-136">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>

    - <span data-ttu-id="a0518-137">Op het tabblad **Azure-kredietsaldo** kunnen Azure-klanten de transactiebalansgeschiedenis zien voor de Azure-tegoeden die door dat factureringsprofiel worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a0518-137">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>

    - <span data-ttu-id="a0518-138">Op het tabblad **Azure-tegoeden** kunnen Azure-klanten een lijst met Azure-tegoeden zien die zijn gekoppeld aan dat factureringsprofiel en hun vervaldatums.</span><span class="sxs-lookup"><span data-stu-id="a0518-138">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="a0518-139">Als u geen Azure-tegoeden hebt, ziet u de tabbladen **Azure-tegoeden** of **Azure-tegoedpunten** niet.</span><span class="sxs-lookup"><span data-stu-id="a0518-139">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="a0518-140">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="a0518-140">Need help?</span></span> <span data-ttu-id="a0518-141">Neem contact op met ondersteuning.</span><span class="sxs-lookup"><span data-stu-id="a0518-141">Contact support.</span></span>

<span data-ttu-id="a0518-142">Als u vragen hebt of hulp nodig hebt bij uw Azure-kosten, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">maakt u een ondersteuningsverzoek met Azure-ondersteuning.</a></span><span class="sxs-lookup"><span data-stu-id="a0518-142">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="a0518-143">Als u vragen hebt of hulp nodig hebt bij uw factureringsprofiel in het Microsoft 365-beheercentrum, neemt u contact op [met ondersteuning voor zakelijke producten.](https://docs.microsoft.com/office365/admin/contact-support-for-business-products)</span><span class="sxs-lookup"><span data-stu-id="a0518-143">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](https://docs.microsoft.com/office365/admin/contact-support-for-business-products).</span></span>
