---
title: Inzicht in factureringsprofielen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
f1_keywords:
- MACBillingBillsPaymentsBillingProfiles
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_billing
search.appverid: MET150
description: Lees hoe factureringsprofielen facturen ondersteunen.
ms.date: 04/02/2021
ms.openlocfilehash: 36d762e50627763b7856ed1fe6c109e8da2b4789
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332028"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="78d9a-103">Inzicht in factureringsprofielen</span><span class="sxs-lookup"><span data-stu-id="78d9a-103">Understand billing profiles</span></span>

<span data-ttu-id="78d9a-104">Voor commerciële klanten die producten en services bij Microsoft kopen, kunt u met factureringsprofielen aanpassen welke items op uw factuur zijn opgenomen en hoe u uw facturen betaalt.</span><span class="sxs-lookup"><span data-stu-id="78d9a-104">For commercial customers who buy products and services from Microsoft, billing profiles let you customize what items are included on your invoice, and how you pay your invoices.</span></span>

<span data-ttu-id="78d9a-105">Factureringsprofielen bevatten de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="78d9a-105">Billing profiles include the following information:</span></span>

- <span data-ttu-id="78d9a-106">**Factureringsaccount** &ndash; Naam van het factureringsaccount van het profiel</span><span class="sxs-lookup"><span data-stu-id="78d9a-106">**Billing account** &ndash; Name of the billing account the profile is related to</span></span>
- <span data-ttu-id="78d9a-107">**Betalingsmethoden** &ndash; Creditcards of betaalkaarten, bankrekeningen, cheques of overschrijving</span><span class="sxs-lookup"><span data-stu-id="78d9a-107">**Payment methods** &ndash; Credit or debit cards, bank accounts, check, or wire transfer</span></span>
- <span data-ttu-id="78d9a-108">**Contactgegevens** &ndash; Factureringsadres en een naam van een contactpersoon</span><span class="sxs-lookup"><span data-stu-id="78d9a-108">**Contact information** &ndash; Billing address and a contact name</span></span>
- <span data-ttu-id="78d9a-109">**Factuurinstellingen** &ndash; Valuta op basis van het land van het factureringsaccount, een optioneel PO-nummer en de optie om facturen als e-mailbijlagen te ontvangen</span><span class="sxs-lookup"><span data-stu-id="78d9a-109">**Invoice settings** &ndash; Currency based on the country of the billing account, an optional PO number, and the option to receive invoices as email attachments</span></span>
- <span data-ttu-id="78d9a-110">**Machtigingen** &ndash; Machtigingen waarmee u het factureringsprofiel kunt wijzigen, facturen kunt betalen of de betalingswijze in het factureringsprofiel kunt gebruiken om aankopen te doen</span><span class="sxs-lookup"><span data-stu-id="78d9a-110">**Permissions** &ndash; Permissions that allow you to change the billing profile, pay bills, or use the payment method on the billing profile to make purchases</span></span>

<span data-ttu-id="78d9a-111">Gebruik factureringsprofielen om uw aankopen te beheren en uw factuur aan te passen.</span><span class="sxs-lookup"><span data-stu-id="78d9a-111">Use billing profiles to control your purchases and customize your invoice.</span></span> <span data-ttu-id="78d9a-112">Er wordt een maandelijkse factuur gegenereerd voor de producten die met het factureringsprofiel zijn gekocht.</span><span class="sxs-lookup"><span data-stu-id="78d9a-112">A monthly invoice is generated for the products bought with the billing profile.</span></span> <span data-ttu-id="78d9a-113">U kunt de factuur aanpassen, zoals het aankoopordernummer en de voorkeur voor e-mailfactuur bijwerken.</span><span class="sxs-lookup"><span data-stu-id="78d9a-113">You can customize the invoice such as update the purchase order number and email invoice preference.</span></span>

<span data-ttu-id="78d9a-114">Er wordt automatisch een factureringsprofiel gemaakt voor uw factureringsaccount tijdens uw eerste aankoop.</span><span class="sxs-lookup"><span data-stu-id="78d9a-114">A billing profile is automatically created for your billing account during your first purchase.</span></span> <span data-ttu-id="78d9a-115">U kunt factureringsprofielen maken op de pagina <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Factureringsprofielen</a> om meer facturen in te stellen.</span><span class="sxs-lookup"><span data-stu-id="78d9a-115">You can create billing profiles on the <a href="https://go.microsoft.com/fwlink/p/?linkid=2103629" target="_blank">Billing profiles</a> page to set up more invoices.</span></span> <span data-ttu-id="78d9a-116">U kunt bijvoorbeeld verschillende factureringsprofielen gebruiken wanneer u aankopen voor elke afdeling in uw organisatie koopt.</span><span class="sxs-lookup"><span data-stu-id="78d9a-116">For example, you can use different billing profiles when you make purchases for each department in your organization.</span></span> <span data-ttu-id="78d9a-117">Op de volgende factureringsdatum ontvangt u een factuur voor elk factureringsprofiel.</span><span class="sxs-lookup"><span data-stu-id="78d9a-117">On your next billing date, you'll receive an invoice for each billing profile.</span></span>

## <a name="billing-profile-roles"></a><span data-ttu-id="78d9a-118">Factureringsprofielrollen</span><span class="sxs-lookup"><span data-stu-id="78d9a-118">Billing profile roles</span></span>

<span data-ttu-id="78d9a-119">Rollen in factureringsprofielen hebben machtigingen voor het beheren van aankopen en het weergeven en beheren van facturen.</span><span class="sxs-lookup"><span data-stu-id="78d9a-119">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="78d9a-120">Wijs deze rollen toe aan gebruikers die facturen bijhouden, organiseren en betalen, zoals leden van het inkoopteam in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="78d9a-120">Assign these roles to users who track, organize, and pay invoices, like members of the procurement team in your organization.</span></span>

| <span data-ttu-id="78d9a-121">Rol</span><span class="sxs-lookup"><span data-stu-id="78d9a-121">Role</span></span>                         | <span data-ttu-id="78d9a-122">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="78d9a-122">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="78d9a-123">Factureringsprofieleigenaar</span><span class="sxs-lookup"><span data-stu-id="78d9a-123">Billing profile owner</span></span>        | <span data-ttu-id="78d9a-124">Alles beheren voor een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="78d9a-124">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="78d9a-125">Factureringsprofielbetaler</span><span class="sxs-lookup"><span data-stu-id="78d9a-125">Billing profile contributor</span></span>  | <span data-ttu-id="78d9a-126">Alles beheren, behalve machtigingen in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="78d9a-126">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="78d9a-127">Factureringsprofiellezer</span><span class="sxs-lookup"><span data-stu-id="78d9a-127">Billing profile reader</span></span>       | <span data-ttu-id="78d9a-128">Alleen-lezen weergave van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="78d9a-128">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="78d9a-129">Factuurbeheer</span><span class="sxs-lookup"><span data-stu-id="78d9a-129">Invoice manager</span></span>              | <span data-ttu-id="78d9a-130">Facturen weergeven en betalen en heeft een alleen-lezen weergave van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="78d9a-130">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-billing-profiles"></a><span data-ttu-id="78d9a-131">Factureringsprofielen weergeven</span><span class="sxs-lookup"><span data-stu-id="78d9a-131">View billing profiles</span></span>

1. <span data-ttu-id="78d9a-132">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a>.</span><span class="sxs-lookup"><span data-stu-id="78d9a-132">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="78d9a-133">Kies **Factureringsprofielen** en kies vervolgens een factureringsprofiel in de lijst.</span><span class="sxs-lookup"><span data-stu-id="78d9a-133">Choose **Billing profiles**, and then choose a billing profile from the list.</span></span>

    - <span data-ttu-id="78d9a-134">Op het **tabblad** Overzicht kunt u factureringsprofielgegevens bewerken en het verzenden van een factuur per e-mail in- of uitschakelen.</span><span class="sxs-lookup"><span data-stu-id="78d9a-134">On the **Overview** tab, you can edit billing profile details, and turn on or off sending an invoice by email.</span></span>
    - <span data-ttu-id="78d9a-135">Op het **tabblad Machtigingen** kunt u rollen toewijzen aan gebruikers om facturen te betalen.</span><span class="sxs-lookup"><span data-stu-id="78d9a-135">On the **Permissions** tab, you can assign roles to users to pay invoices.</span></span>
    - <span data-ttu-id="78d9a-136">Op het **tabblad Azure-tegoedsaldo** kunnen Azure-klanten de transactiebalansgeschiedenis zien voor de Azure-tegoeden die door dat factureringsprofiel worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="78d9a-136">On the **Azure credit balance** tab, Azure customers can see transaction balance history for the Azure credits used by that billing profile.</span></span>
    - <span data-ttu-id="78d9a-137">Op het **tabblad Azure-tegoed** kunnen Azure-klanten een lijst zien met Azure-tegoeden die zijn gekoppeld aan dat factureringsprofiel en hun vervaldatums.</span><span class="sxs-lookup"><span data-stu-id="78d9a-137">On the **Azure credits** tab, Azure customers can see a list of Azure credits associated with that billing profile, and their expiration dates.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78d9a-138">Als u geen Azure-tegoed hebt, ziet u de **tabbladen Azure-tegoed** of **Azure-tegoed** niet.</span><span class="sxs-lookup"><span data-stu-id="78d9a-138">If you don't have any Azure credits, you won't see the **Azure credit balance** or **Azure credits** tabs.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="78d9a-139">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="78d9a-139">Need help?</span></span> <span data-ttu-id="78d9a-140">Contact opnemen met de ondersteuning</span><span class="sxs-lookup"><span data-stu-id="78d9a-140">Contact support</span></span>

<span data-ttu-id="78d9a-141">Als u vragen hebt of hulp nodig hebt bij uw Azure-kosten, maakt <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">u een ondersteuningsaanvraag met Azure-ondersteuning.</a></span><span class="sxs-lookup"><span data-stu-id="78d9a-141">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="78d9a-142">Als u vragen hebt of hulp nodig hebt bij uw factureringsprofiel in Microsoft 365 beheercentrum, neem dan contact op met [ondersteuning voor zakelijke producten.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="78d9a-142">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support for business products](../../business-video/get-help-support.md).</span></span>
