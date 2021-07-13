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
- AdminTemplateSet
search.appverid: MET150
description: Lees hoe factureringsprofielen facturen ondersteunen.
ms.date: 04/02/2021
ms.openlocfilehash: ecea09a9ceea12fa92b92eac3e5a7595b2510042
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394627"
---
# <a name="understand-billing-profiles"></a><span data-ttu-id="ce434-103">Inzicht in factureringsprofielen</span><span class="sxs-lookup"><span data-stu-id="ce434-103">Understand billing profiles</span></span>

<span data-ttu-id="ce434-104">Een factureringsprofiel bevat een betalingswijze, factuurgegevens en andere factuurinstellingen, zoals inkoopordernummer en factuurvoorkeur per e-mail.</span><span class="sxs-lookup"><span data-stu-id="ce434-104">A billing profile contains a payment method, Bill-to information, and other invoice settings, such as purchase order number and email invoice preference.</span></span> <span data-ttu-id="ce434-105">U gebruikt een factureringsprofiel om te betalen voor de producten die u bij Microsoft koopt.</span><span class="sxs-lookup"><span data-stu-id="ce434-105">You use a billing profile to pay for the products that you buy from Microsoft.</span></span> <span data-ttu-id="ce434-106">Er wordt automatisch een factureringsprofiel gemaakt wanneer een gebruiker een selfserviceaankoop doet.</span><span class="sxs-lookup"><span data-stu-id="ce434-106">A billing profile is automatically created when a user makes a self-service purchase.</span></span> <span data-ttu-id="ce434-107">Elk factureringsprofiel wordt afzonderlijk gefactureerd.</span><span class="sxs-lookup"><span data-stu-id="ce434-107">Each billing profile is invoiced separately.</span></span>

> [!NOTE]
>
> <span data-ttu-id="ce434-108">Factureringsprofielen zijn niet beschikbaar voor klanten die producten en services kopen Microsoft.com of op de **pagina Services** aanschaffen van de Microsoft 365-beheercentrum.</span><span class="sxs-lookup"><span data-stu-id="ce434-108">Billing profiles are not available to customers who buy products and services from Microsoft.com or on the **Purchase services** page of the Microsoft 365 admin center.</span></span>

## <a name="what-are-billing-profile-roles"></a><span data-ttu-id="ce434-109">Wat zijn factureringsprofielrollen?</span><span class="sxs-lookup"><span data-stu-id="ce434-109">What are billing profile roles?</span></span>

<span data-ttu-id="ce434-110">Rollen in factureringsprofielen hebben machtigingen voor het beheren van aankopen en het weergeven en beheren van facturen.</span><span class="sxs-lookup"><span data-stu-id="ce434-110">Roles on billing profiles have permissions to control purchases, and view and manage invoices.</span></span> <span data-ttu-id="ce434-111">Wijs deze rollen toe aan gebruikers die facturen bijhouden, organiseren en betalen.</span><span class="sxs-lookup"><span data-stu-id="ce434-111">Assign these roles to users who track, organize, and pay invoices.</span></span> <span data-ttu-id="ce434-112">Bijvoorbeeld leden van het inkoopteam in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ce434-112">For example, members of the procurement team in your organization.</span></span>

| <span data-ttu-id="ce434-113">Rol</span><span class="sxs-lookup"><span data-stu-id="ce434-113">Role</span></span>                         | <span data-ttu-id="ce434-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="ce434-114">Description</span></span>                                                                      |
|----------------------------- |--------------------------------------------------------------------------------- |
| <span data-ttu-id="ce434-115">Factureringsprofieleigenaar</span><span class="sxs-lookup"><span data-stu-id="ce434-115">Billing profile owner</span></span>        | <span data-ttu-id="ce434-116">Alles beheren voor een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="ce434-116">Manage everything for a billing profile</span></span>                                          |
| <span data-ttu-id="ce434-117">Factureringsprofielbetaler</span><span class="sxs-lookup"><span data-stu-id="ce434-117">Billing profile contributor</span></span>  | <span data-ttu-id="ce434-118">Alles beheren, behalve machtigingen in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="ce434-118">Manage everything except permissions in a billing profile</span></span>                        |
| <span data-ttu-id="ce434-119">Factureringsprofiellezer</span><span class="sxs-lookup"><span data-stu-id="ce434-119">Billing profile reader</span></span>       | <span data-ttu-id="ce434-120">Alleen-lezen weergave van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="ce434-120">Read-only view of everything in a billing profile</span></span>                                |
| <span data-ttu-id="ce434-121">Factuurbeheer</span><span class="sxs-lookup"><span data-stu-id="ce434-121">Invoice manager</span></span>              | <span data-ttu-id="ce434-122">Facturen weergeven en betalen en heeft een alleen-lezen weergave van alles in een factureringsprofiel</span><span class="sxs-lookup"><span data-stu-id="ce434-122">View and pay bills, and has a read-only view of everything in a billing profile</span></span>  |

## <a name="view-my-billing-profiles"></a><span data-ttu-id="ce434-123">Mijn factureringsprofielen weergeven</span><span class="sxs-lookup"><span data-stu-id="ce434-123">View my billing profiles</span></span>

> [!NOTE]
>
> <span data-ttu-id="ce434-124">Als u deze stappen volgt en de lijst met factureringsprofielen leeg is, betekent dit dat u geen factureringsprofiel hebt en deze functie niet kunt gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ce434-124">If you follow these steps and the billing profiles list is empty, it means that you don’t have a billing profile, and can’t use this feature.</span></span>

1. <span data-ttu-id="ce434-125">Ga in het beheercentrum naar de pagina **Facturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Facturen en betalingen</a>.</span><span class="sxs-lookup"><span data-stu-id="ce434-125">In the admin center, go to the **Billing** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Bills & payments</a> page.</span></span>
2. <span data-ttu-id="ce434-126">Selecteer het **tabblad Factureringsprofiel** en selecteer vervolgens een factureringsprofiel in de lijst.</span><span class="sxs-lookup"><span data-stu-id="ce434-126">Select the **Billing profile** tab, then select a billing profile from the list.</span></span>

<span data-ttu-id="ce434-127">Elk factureringsprofiel bevat de volgende informatie:</span><span class="sxs-lookup"><span data-stu-id="ce434-127">Each billing profile includes the following information:</span></span>

- <span data-ttu-id="ce434-128">**Naam en status van factureringsprofiel** &ndash; De unieke naam van het factureringsprofiel en of het factureringsprofiel actief of uitgeschakeld is voor aankoop.</span><span class="sxs-lookup"><span data-stu-id="ce434-128">**Billing profile name and status** &ndash; The unique name of the billing profile, and whether the billing profile is active or disabled for purchasing.</span></span>
- <span data-ttu-id="ce434-129">**Factuurinstellingen** &ndash; Valuta op basis van het land van het factureringsaccount, informatie over de factuurfrequentie en -datum, de optie om facturen als e-mailbijlagen te ontvangen en een optioneel veld PO-nummer</span><span class="sxs-lookup"><span data-stu-id="ce434-129">**Invoice settings** &ndash; Currency based on the country of the billing account, information about invoice frequency and date, the option to receive invoices as email attachments, and an optional PO number field</span></span>
- <span data-ttu-id="ce434-130">**Betalingsmethoden** &ndash; Toont de primaire betalingswijze en eventuele back-up voor het profiel</span><span class="sxs-lookup"><span data-stu-id="ce434-130">**Payment methods** &ndash; Shows the primary and backup payment method, if any, for the profile</span></span>
- <span data-ttu-id="ce434-131">**Factureringsaccount** &ndash; De naam van het factureringsaccount waar het profiel aan is gerelateerd.</span><span class="sxs-lookup"><span data-stu-id="ce434-131">**Billing account** &ndash; Name of the billing account the profile is related to.</span></span> <span data-ttu-id="ce434-132">Zie Factureringsaccounts begrijpen voor [meer informatie over factureringsaccounts.](../manage-billing-accounts.md)</span><span class="sxs-lookup"><span data-stu-id="ce434-132">For more information about billing accounts, see [Understand billing accounts](../manage-billing-accounts.md).</span></span>
- <span data-ttu-id="ce434-133">**Contactgegevens** &ndash; Factureringsadres en naam van contactpersoon en e-mailadres</span><span class="sxs-lookup"><span data-stu-id="ce434-133">**Contact information** &ndash; Billing address and contact name and email address</span></span>
- <span data-ttu-id="ce434-134">**Factureringsprofielrollen** &ndash; Een lijst met personen aan wie een van de factureringsprofielrollen is toegewezen om dingen voor dat profiel te doen.</span><span class="sxs-lookup"><span data-stu-id="ce434-134">**Billing profile roles** &ndash; A list of people who are assigned one of the billing profile roles to do things for that profile.</span></span> <span data-ttu-id="ce434-135">Bijvoorbeeld: betaalrekeningen, voeg een PO-nummer toe of vervang de betalingswijze die wordt gebruikt om aankopen te doen.</span><span class="sxs-lookup"><span data-stu-id="ce434-135">For example, pay bills, add a PO number, or replace the payment method that is used to make purchases.</span></span>

> [!NOTE]
>
> <span data-ttu-id="ce434-136">U kunt alleen factureringsprofielrollen toewijzen aan gebruikers in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ce434-136">You can only assign billing profile roles to users in your organization.</span></span>

## <a name="need-help-contact-support"></a><span data-ttu-id="ce434-137">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="ce434-137">Need help?</span></span> <span data-ttu-id="ce434-138">Contact opnemen met de ondersteuning</span><span class="sxs-lookup"><span data-stu-id="ce434-138">Contact support</span></span>

<span data-ttu-id="ce434-139">Als u vragen hebt of hulp nodig hebt bij uw Azure-kosten, maakt <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">u een ondersteuningsaanvraag met Azure-ondersteuning.</a></span><span class="sxs-lookup"><span data-stu-id="ce434-139">If you have questions or need help with your Azure charges, <a href="https://portal.azure.com/#blade/Microsoft_Azure_Support/HelpAndSupportBlade/newsupportrequest" target="_blank">create a support request with Azure support</a>.</span></span>

<span data-ttu-id="ce434-140">Als u vragen hebt of hulp nodig hebt bij uw factureringsprofiel in Microsoft 365-beheercentrum, [neem dan contact op met de ondersteuning.](../../business-video/get-help-support.md)</span><span class="sxs-lookup"><span data-stu-id="ce434-140">If you have questions or need help with your billing profile in Microsoft 365 admin center, [contact support](../../business-video/get-help-support.md).</span></span>

## <a name="related-content"></a><span data-ttu-id="ce434-141">Verwante inhoud</span><span class="sxs-lookup"><span data-stu-id="ce434-141">Related content</span></span>

<span data-ttu-id="ce434-142">[Betalen voor uw abonnement met een factureringsprofiel](pay-for-subscription-billing-profile.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ce434-142">[How to pay for your subscription with a billing profile](pay-for-subscription-billing-profile.md) (article)</span></span>\
<span data-ttu-id="ce434-143">[Inzicht in factureringsaccounts](../manage-billing-accounts.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ce434-143">[Understand billing accounts](../manage-billing-accounts.md) (article)</span></span>\
<span data-ttu-id="ce434-144">[Betalingsmethoden beheren](manage-payment-methods.md) (artikel)</span><span class="sxs-lookup"><span data-stu-id="ce434-144">[Manage payment methods](manage-payment-methods.md) (article)</span></span>
