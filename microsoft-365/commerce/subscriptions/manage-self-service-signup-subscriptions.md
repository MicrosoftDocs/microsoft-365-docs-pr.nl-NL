---
title: Abonnementen voor selfservice-aanmelding beheren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- commerce
- Adm_NonTOC
search.appverid:
- MET150
description: Meer informatie over het beheren van gratis selfservice-abonnementen voor uw organisatie.
ms.openlocfilehash: 46c77cb32fec4dfa1fb9c3d3f992bd842be1b969
ms.sourcegitcommit: eb3c7f473e8fe62624f52c9bb38dcd6a96fa58a3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/05/2020
ms.locfileid: "44045253"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="99f33-103">Abonnementen voor selfservice-aanmelding beheren</span><span class="sxs-lookup"><span data-stu-id="99f33-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="99f33-104">Wat zijn selfservice-abonnementen?</span><span class="sxs-lookup"><span data-stu-id="99f33-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="99f33-105">Er zijn een beperkt aantal gratis self-service aanmeldingsabonnementen waarvoor gebruikers in uw organisatie zich kunnen aanmelden.</span><span class="sxs-lookup"><span data-stu-id="99f33-105">There are a limited number of free self-service sign-up subscriptions that users in your organization can sign up for.</span></span> <span data-ttu-id="99f33-106">Een gebruiker kan zich alleen aanmelden voor en zelf een selfservice-abonnement gebruiken.</span><span class="sxs-lookup"><span data-stu-id="99f33-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="99f33-107">Deze abonnementen worden weergegeven op de pagina **Uw producten,** zijn gemarkeerd als **Gratis**en hebben een notitie met de tekst: "Dit is een gratis abonnement dat wordt geactiveerd door gebruikers in uw bedrijf."</span><span class="sxs-lookup"><span data-stu-id="99f33-107">These subscriptions appear on the **Your products** page, are marked as **Free**, and have a note that says, "This is a free subscription activated by users in your company."</span></span> <span data-ttu-id="99f33-108">U zelfservice-aanmeldingsabonnementen beheren door gebruikers te blokkeren zich aan te melden en door gratis abonnementen te verwijderen waarvoor gebruikers zich hebben aangemeld.</span><span class="sxs-lookup"><span data-stu-id="99f33-108">You can manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="99f33-109">Zie [Zelfserviceaanmelden gebruiken in uw organisatie](../../admin/misc/self-service-sign-up.md)voor meer informatie over het aanmelden voor selfservice en de beschikbare abonnementen.</span><span class="sxs-lookup"><span data-stu-id="99f33-109">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="99f33-110">Wat zijn deze abonnementen anders dan self-service aankoopabonnementen?</span><span class="sxs-lookup"><span data-stu-id="99f33-110">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="99f33-111">Self-service aanmeldingsabonnementen zijn gratis en zijn beschikbaar voor een grotere lijst met producten dan selfservice-aankoopabonnementen.</span><span class="sxs-lookup"><span data-stu-id="99f33-111">Self-service sign-up subscriptions are free, and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="99f33-112">Wanneer een gebruiker zich aanmeldt voor een selfservice-aankoopabonnement, is hij verantwoordelijk voor het betalen ervan.</span><span class="sxs-lookup"><span data-stu-id="99f33-112">When a user signs up for a self-service purchase subscription, they are responsible for paying for it.</span></span> <span data-ttu-id="99f33-113">Ook zijn abonnementen voor selfservice-aankopen alleen beschikbaar voor Power Platform-producten (Power BI, Power Apps en Power Automate).</span><span class="sxs-lookup"><span data-stu-id="99f33-113">Also, self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate).</span></span> <span data-ttu-id="99f33-114">Zie [Veelgestelde vragen over selfserviceaankopen](self-service-purchase-faq.md)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="99f33-114">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="99f33-115">Gebruikers blokkeren om zich aan te melden</span><span class="sxs-lookup"><span data-stu-id="99f33-115">Block users from signing up</span></span>

<span data-ttu-id="99f33-116">U gebruikt de cmdlet [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) met de parameter **AllowAdHocSubscriptions** om te bepalen of gebruikers zich kunnen aanmelden voor zelfbedieningsabonnementen.</span><span class="sxs-lookup"><span data-stu-id="99f33-116">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="99f33-117">Zie [Hoe beheer ik selfservice-instellingen?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="99f33-117">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="99f33-118">Een selfservice-abonnement verwijderen</span><span class="sxs-lookup"><span data-stu-id="99f33-118">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="99f33-119">Wanneer u een selfservice-abonnement verwijdert, blokkeert u dat alle gebruikers toegang krijgen tot hun gegevens en e-mail en alle gegevens en e-mail verwijderen.</span><span class="sxs-lookup"><span data-stu-id="99f33-119">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="99f33-120">Ga in het beheercentrum naar de pagina **Facturering** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten.</a></span><span class="sxs-lookup"><span data-stu-id="99f33-120">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="99f33-121">Zoek het selfservice-abonnement dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="99f33-121">Find the self-service sign-up subscription that you want to delete.</span></span> <span data-ttu-id="99f33-122">Selecteer **abonnement verwijderen**in de sectie Instellingen **& acties** .</span><span class="sxs-lookup"><span data-stu-id="99f33-122">In the **Settings & Actions** section, select **Delete subscription**.</span></span>
3. <span data-ttu-id="99f33-123">Schakel in het deelvenster **Abonnement verwijderen** het selectievakje in en schakel vervolgens **Abonnement verwijderen**in.</span><span class="sxs-lookup"><span data-stu-id="99f33-123">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="99f33-124">Ik heb een selfservice-abonnement dat het verwijderen van directory's blokkeert</span><span class="sxs-lookup"><span data-stu-id="99f33-124">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="99f33-125">De selfservice-aanmeldingsproducten waarvoor individuele gebruikers zich kunnen aanmelden, maken ook een gastgebruiker voor verificatie in uw Azure AD-map.</span><span class="sxs-lookup"><span data-stu-id="99f33-125">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="99f33-126">Om gegevensverlies te voorkomen, blokkeren deze selfserviceproducten het verwijderen van directorytotdat ze volledig uit de map zijn verwijderd.</span><span class="sxs-lookup"><span data-stu-id="99f33-126">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="99f33-127">Ze kunnen alleen worden verwijderd door de Azure AD-beheerder. Zie [Een map verwijderen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="99f33-127">They can be deleted only by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>