---
title: Selfservice-abonnementen beheren
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
description: Meer informatie over het beheren van gratis selfservice-abonnementen voor uw organisatie.
ms.openlocfilehash: 5910ed5d65f93a4dab15c681610d4d59d0427fb0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920166"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="ad45c-103">Selfservice-abonnementen beheren</span><span class="sxs-lookup"><span data-stu-id="ad45c-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="ad45c-104">Wat zijn selfservice-abonnementen?</span><span class="sxs-lookup"><span data-stu-id="ad45c-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="ad45c-105">Er is een beperkt aantal gratis selfservice-abonnementen beschikbaar voor gebruikers in uw organisatie om zich voor aan te melden.</span><span class="sxs-lookup"><span data-stu-id="ad45c-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="ad45c-106">Een gebruiker kan zich alleen registreren voor en een selfservice-abonnement voor zichzelf gebruiken.</span><span class="sxs-lookup"><span data-stu-id="ad45c-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="ad45c-107">U beheert selfservice-abonnementen door te blokkeren dat gebruikers zich kunnen registreren en door gratis abonnementen te verwijderen waar gebruikers zich voor hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="ad45c-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="ad45c-108">Zie Selfservice registreren in uw organisatie voor meer informatie over [selfservice-aanmelding](../../admin/misc/self-service-sign-up.md)en de beschikbare abonnementen.</span><span class="sxs-lookup"><span data-stu-id="ad45c-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="ad45c-109">Een lijst met selfservice-abonnementen weergeven</span><span class="sxs-lookup"><span data-stu-id="ad45c-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="ad45c-110">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="ad45c-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ad45c-111">Selecteer op **het** tabblad Producten het filterpictogram en selecteer vervolgens **Gratis.**</span><span class="sxs-lookup"><span data-stu-id="ad45c-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="ad45c-112">Er wordt een lijst met alle selfservice-abonnementen weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ad45c-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="ad45c-113">Hoe verschillen deze abonnementen van abonnementen voor selfserviceaankoop?</span><span class="sxs-lookup"><span data-stu-id="ad45c-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="ad45c-114">Selfservice-abonnementen zijn gratis en zijn beschikbaar voor een grotere lijst met producten dan abonnementen voor selfserviceaankoop.</span><span class="sxs-lookup"><span data-stu-id="ad45c-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="ad45c-115">Wanneer een gebruiker zich meldt voor een selfservice-aankoopabonnement, is hij of zij verantwoordelijk voor het betalen ervan.</span><span class="sxs-lookup"><span data-stu-id="ad45c-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="ad45c-116">Selfservice-abonnementen zijn alleen beschikbaar voor Power Platform-producten (Power BI, Power Apps en Power Automate), Project en Visio.</span><span class="sxs-lookup"><span data-stu-id="ad45c-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="ad45c-117">Zie Veelgestelde vragen over [selfservice-aankopen voor meer informatie.](self-service-purchase-faq.md)</span><span class="sxs-lookup"><span data-stu-id="ad45c-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="ad45c-118">Gebruikers blokkeren om zich aan te melden</span><span class="sxs-lookup"><span data-stu-id="ad45c-118">Block users from signing up</span></span>

<span data-ttu-id="ad45c-119">U gebruikt de cmdlet [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions** om te bepalen of gebruikers zich kunnen registreren voor selfservice-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="ad45c-119">You use the [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="ad45c-120">Zie Hoe beheer ik [selfservice-instellingen?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="ad45c-120">For more information, see [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="ad45c-121">Een selfservice-abonnement verwijderen</span><span class="sxs-lookup"><span data-stu-id="ad45c-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad45c-122">Wanneer u een selfservice-abonnement verwijdert, blokkeert u dat alle gebruikers toegang hebben tot hun gegevens en e-mail en verwijdert u alle gegevens en e-mail.</span><span class="sxs-lookup"><span data-stu-id="ad45c-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="ad45c-123">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Mijn producten</a>.</span><span class="sxs-lookup"><span data-stu-id="ad45c-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="ad45c-124">Selecteer op **het** tabblad Producten het filterpictogram en selecteer vervolgens **Gratis.**</span><span class="sxs-lookup"><span data-stu-id="ad45c-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="ad45c-125">Selecteer het selfservice-abonnement dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="ad45c-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="ad45c-126">Selecteer op de pagina **Abonnementsgegevens** in de sectie Abonnementen en betalingsinstellingen de optie **Abonnement verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ad45c-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="ad45c-127">Schakel in **het deelvenster** Abonnement verwijderen het selectievakje in en selecteer vervolgens **Abonnement verwijderen.**</span><span class="sxs-lookup"><span data-stu-id="ad45c-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="ad45c-128">Ik heb een selfservice-abonnement dat adreslijstverhaling blokkeert</span><span class="sxs-lookup"><span data-stu-id="ad45c-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="ad45c-129">De selfservice-aanmeldingsproducten waar afzonderlijke gebruikers zich voor kunnen registreren, maken ook een gastgebruiker voor verificatie in uw Azure AD-adreslijst.</span><span class="sxs-lookup"><span data-stu-id="ad45c-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="ad45c-130">Om gegevensverlies te voorkomen, blokkeren deze selfserviceproducten adreslijstverhalingen totdat ze volledig uit de adreslijst zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="ad45c-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="ad45c-131">Ze kunnen alleen worden verwijderd door de Azure AD-beheerder. Zie Een adreslijst verwijderen in Azure Active Directory voor [meer informatie.](/azure/active-directory/users-groups-roles/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="ad45c-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>