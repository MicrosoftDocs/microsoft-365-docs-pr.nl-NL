---
title: Selfservice registratie abonnementen beheren
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
- commerce
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Meer informatie over het beheren van gratis selfservice registratie abonnementen voor uw organisatie.
ms.openlocfilehash: fb70d0c40d4358abc227c8f6ff4a0e0dce1a7265
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48647829"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="2b9e4-103">Selfservice registratie abonnementen beheren</span><span class="sxs-lookup"><span data-stu-id="2b9e4-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="2b9e4-104">Wat zijn Self-serviceregistratie abonnementen?</span><span class="sxs-lookup"><span data-stu-id="2b9e4-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="2b9e4-105">U kunt een beperkt aantal gratis selfservice registratie abonnementen instellen waarmee gebruikers in uw organisatie zich kunnen registreren.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="2b9e4-106">Een gebruiker kan zich alleen aanmelden voor een self-service-aanmeldings abonnement.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="2b9e4-107">Deze abonnementen worden weergegeven op de pagina **uw producten** , zijn gemarkeerd als **gratis**en hebben de tekst ' Dit is een gratis abonnement dat wordt geactiveerd door gebruikers in uw bedrijf. '</span><span class="sxs-lookup"><span data-stu-id="2b9e4-107">These subscriptions appear on the **Your products** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="2b9e4-108">U kunt Self-Serviceabonnementen voor eenmalige aanmelding beheren door gebruikers te blokkeren met een registratie, en door gratis abonnementen te verwijderen waarop gebruikers zich hebben geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="2b9e4-109">Zie [selfservice registratie gebruiken in uw organisatie](../../admin/misc/self-service-sign-up.md)voor meer informatie over selfservice registratie en de beschikbare abonnementen.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="2b9e4-110">Wat is het verschil tussen de abonnementen voor selfservice aankopen?</span><span class="sxs-lookup"><span data-stu-id="2b9e4-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="2b9e4-111">Selfservice registratie abonnementen zijn gratis en zijn beschikbaar voor een grotere lijst met producten dan selfservice Purchase-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="2b9e4-112">Wanneer een gebruiker zich registreert voor een self-service Purchase-abonnement, zijn ze verantwoordelijk voor de betaling ervan.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="2b9e4-113">Ook selfservice Purchase-abonnementen zijn alleen beschikbaar voor Power platform-producten (Power BI, Power apps en Power Automatiseer).</span><span class="sxs-lookup"><span data-stu-id="2b9e4-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="2b9e4-114">Voor meer informatie raadpleegt u [Veelgestelde vragen over self-service aankopen](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="2b9e4-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="2b9e4-115">Voorkomen dat gebruikers zich aanmelden</span><span class="sxs-lookup"><span data-stu-id="2b9e4-115">Block users from signing up</span></span>

<span data-ttu-id="2b9e4-116">Met de cmdlet [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions** kunt u aangeven of gebruikers zich kunnen registreren voor Self-serviceregistratie abonnementen.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="2b9e4-117">Voor meer informatie raadpleegt [u hoe kan ik selfservice-instellingen beheren?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="2b9e4-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="2b9e4-118">Een self-serviceregistratie abonnement verwijderen</span><span class="sxs-lookup"><span data-stu-id="2b9e4-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2b9e4-119">Wanneer u een abonnement voor selfservice registratie verwijdert, blok keert alle gebruikers de toegang tot de gegevens en e-mail en verwijder alle gegevens en e-mail.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="2b9e4-120">Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="2b9e4-121">Zoek het self-service-aanmeldings abonnement dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="2b9e4-122">Selecteer in de sectie **instellingen & acties** de optie **abonnement verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="2b9e4-123">In het deelvenster **abonnement verwijderen** schakelt u het selectievakje in en selecteert u vervolgens **abonnement verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="2b9e4-124">Ik heb een self-serviceregistratie abonnement dat de verwijdering van de map blokkeert</span><span class="sxs-lookup"><span data-stu-id="2b9e4-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="2b9e4-125">De selfservice registratie producten waarmee afzonderlijke gebruikers zich kunnen registreren voor het ook maken van een gastgebruiker voor verificatie in de Azure AD-Directory.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="2b9e4-126">Om verlies van gegevens te voorkomen, blok keert deze selfservice producten Directory verwijdering totdat ze volledig uit de adreslijst worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="2b9e4-127">Ze kunnen alleen worden verwijderd door de Azure AD-beheerder. Zie [een map verwijderen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="2b9e4-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>