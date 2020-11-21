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
ms.openlocfilehash: 589466908dcda1461011f046b99be21788c1a018
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376303"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="b138c-103">Selfservice registratie abonnementen beheren</span><span class="sxs-lookup"><span data-stu-id="b138c-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="b138c-104">Wat zijn Self-serviceregistratie abonnementen?</span><span class="sxs-lookup"><span data-stu-id="b138c-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="b138c-105">U kunt zich een beperkt aantal gratis selfservice registraties bevinden zodat gebruikers in uw organisatie zich kunnen registreren.</span><span class="sxs-lookup"><span data-stu-id="b138c-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="b138c-106">Een gebruiker kan zich alleen aanmelden voor een self-service-aanmeldings abonnement.</span><span class="sxs-lookup"><span data-stu-id="b138c-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="b138c-107">U beheert selfservice abonnementen voor eenmalige aanmelding door gebruikers te blokkeren met de registratie, en door gratis abonnementen te verwijderen waarop gebruikers zich hebben geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="b138c-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="b138c-108">Zie [selfservice registratie gebruiken in uw organisatie](../../admin/misc/self-service-sign-up.md)voor meer informatie over selfservice registratie en de beschikbare abonnementen.</span><span class="sxs-lookup"><span data-stu-id="b138c-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="b138c-109">Een lijst met selfservice abonnementen weergeven</span><span class="sxs-lookup"><span data-stu-id="b138c-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="b138c-110">Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.</span><span class="sxs-lookup"><span data-stu-id="b138c-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b138c-111">Selecteer op het tabblad **Products** het pictogram filter en selecteer vervolgens **gratis**.</span><span class="sxs-lookup"><span data-stu-id="b138c-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="b138c-112">Er verschijnt een lijst met alle selfservice registratie abonnementen.</span><span class="sxs-lookup"><span data-stu-id="b138c-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="b138c-113">Wat is het verschil tussen de abonnementen voor selfservice aankopen?</span><span class="sxs-lookup"><span data-stu-id="b138c-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="b138c-114">Selfservice registratie abonnementen zijn gratis en zijn beschikbaar voor een grotere lijst met producten dan selfservice Purchase-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="b138c-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="b138c-115">Wanneer een gebruiker zich registreert voor een self-service Purchase-abonnement, zijn ze verantwoordelijk voor de betaling ervan.</span><span class="sxs-lookup"><span data-stu-id="b138c-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="b138c-116">Abonnementen voor selfservice aankopen zijn alleen beschikbaar voor Power platform-producten (Power BI, Power-apps en Power Automatiseer), project en Visio.</span><span class="sxs-lookup"><span data-stu-id="b138c-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="b138c-117">Voor meer informatie raadpleegt u [Veelgestelde vragen over self-service aankopen](self-service-purchase-faq.md).</span><span class="sxs-lookup"><span data-stu-id="b138c-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="b138c-118">Voorkomen dat gebruikers zich aanmelden</span><span class="sxs-lookup"><span data-stu-id="b138c-118">Block users from signing up</span></span>

<span data-ttu-id="b138c-119">Met de cmdlet [**set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) met de parameter **AllowAdHocSubscriptions** kunt u aangeven of gebruikers zich kunnen registreren voor Self-serviceregistratie abonnementen.</span><span class="sxs-lookup"><span data-stu-id="b138c-119">You use the [**Set-MsolCompanySettings**](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0&preserve-view=true) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="b138c-120">Voor meer informatie raadpleegt [u hoe kan ik selfservice-instellingen beheren?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="b138c-120">For more information, see [How do I control self-service settings?](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="b138c-121">Een self-serviceregistratie abonnement verwijderen</span><span class="sxs-lookup"><span data-stu-id="b138c-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b138c-122">Wanneer u een abonnement voor selfservice registratie verwijdert, blok keert alle gebruikers de toegang tot de gegevens en e-mail en verwijder alle gegevens en e-mail.</span><span class="sxs-lookup"><span data-stu-id="b138c-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="b138c-123">Ga in het Beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">uw producten</a> factureren.</span><span class="sxs-lookup"><span data-stu-id="b138c-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="b138c-124">Selecteer op het tabblad **Products** het pictogram filter en selecteer vervolgens **gratis**.</span><span class="sxs-lookup"><span data-stu-id="b138c-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="b138c-125">Selecteer het selfservice registratie abonnement dat u wilt verwijderen.</span><span class="sxs-lookup"><span data-stu-id="b138c-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="b138c-126">Selecteer op de pagina Details van abonnement in de sectie **Abonnementen en betalings instellingen** de optie **abonnement verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="b138c-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="b138c-127">In het deelvenster **abonnement verwijderen** schakelt u het selectievakje in en selecteert u vervolgens **abonnement verwijderen**.</span><span class="sxs-lookup"><span data-stu-id="b138c-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="b138c-128">Ik heb een self-serviceregistratie abonnement dat de verwijdering van de map blokkeert</span><span class="sxs-lookup"><span data-stu-id="b138c-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="b138c-129">De selfservice registratie producten waarmee afzonderlijke gebruikers zich kunnen registreren voor het ook maken van een gastgebruiker voor verificatie in de Azure AD-Directory.</span><span class="sxs-lookup"><span data-stu-id="b138c-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="b138c-130">Om verlies van gegevens te voorkomen, blok keert deze selfservice producten Directory verwijdering totdat ze volledig uit de adreslijst worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="b138c-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="b138c-131">Ze kunnen alleen worden verwijderd door de Azure AD-beheerder. Zie [een map verwijderen in azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b138c-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>