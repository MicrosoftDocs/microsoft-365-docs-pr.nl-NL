---
title: Domeingebruikers synchroniseren met Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Synchronisatie van domeingebruikers met Microsoft 365 voor bedrijven.
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841354"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="90f17-103">Domeingebruikers synchroniseren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="90f17-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="90f17-104">1. voorbereiden op adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="90f17-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="90f17-105">Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, raadpleegt [u voorbereidingen voor adreslijstsynchronisatie met Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="90f17-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="90f17-106">Met name:</span><span class="sxs-lookup"><span data-stu-id="90f17-106">In particular:</span></span>

   - <span data-ttu-id="90f17-107">Zorg ervoor dat er geen dubbele waarden in de adreslijst voorkomen voor de volgende kenmerken: **mail** , **proxyAddresses** en **userPrincipalName** .</span><span class="sxs-lookup"><span data-stu-id="90f17-107">Make sure that no duplicates exist in your directory for the following attributes: **mail** , **proxyAddresses** , and **userPrincipalName** .</span></span> <span data-ttu-id="90f17-108">Deze waarden moeten uniek zijn en alle duplicaten moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="90f17-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="90f17-109">We raden u aan het kenmerk **userPrincipalName** (UPN) te configureren voor elk lokaal gebruikersaccount dat overeenkomt met het primaire e-mailadres dat overeenkomt met de gelicentieerde microsoft 365-gebruiker.</span><span class="sxs-lookup"><span data-stu-id="90f17-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="90f17-110">Bijvoorbeeld: *Mary.Shelley@contoso.com* in plaats van *Mary@contoso. lokaal*</span><span class="sxs-lookup"><span data-stu-id="90f17-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="90f17-111">Als het Active Directory-domein eindigt op een niet-routeerbaar achtervoegsel zoals *. lokaal* of *. LAN* , in plaats van een routeerbaar achtervoegsel voor Internet, zoals *. com* of *. org* , past u eerst het UPN-achtervoegsel van de lokale gebruikersaccounts aan zoals wordt beschreven in [een niet-routeerbaar domein voorbereiden op adreslijstsynchronisatie](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="90f17-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan* , instead of an internet routable suffix such as *.com* or *.org* , adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="90f17-112">Met de **IdFix run** in stap 4, hieronder, wordt ook gecontroleerd of uw on-premises Active Directory klaar is voor adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="90f17-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="90f17-113">2. Azure AD Connect installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="90f17-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="90f17-114">Als u uw gebruikers, groepen en contactpersonen wilt synchroniseren van de lokale Active Directory naar Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in.</span><span class="sxs-lookup"><span data-stu-id="90f17-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="90f17-115">Selecteer in het [Beheercentrum](https://go.microsoft.com/fwlink/p/?linkid=2024339) **instellingen** in het linkernavigatievenster.</span><span class="sxs-lookup"><span data-stu-id="90f17-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="90f17-116">Kies onder **Aanmelden en beveiliging** de optie **weergeven**  onder **gebruikers synchroniseren vanuit de adreslijst van uw organisatie** .</span><span class="sxs-lookup"><span data-stu-id="90f17-116">Under **Sign-in and security** , choose **View**  under **Sync users from your org's directory** .</span></span>

 3. <span data-ttu-id="90f17-117">Kies op de pagina **gebruikers synchroniseren vanaf de adreslijst van uw organisatie** de optie **aan de slag** .</span><span class="sxs-lookup"><span data-stu-id="90f17-117">On the **Sync users from your org's directory** page, choose **Get started** .</span></span>

 4. <span data-ttu-id="90f17-118">Voer in het IdFix-hulpprogramma First Step run voor de voorbereiding voor Directory-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="90f17-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="90f17-119">Voer de stappen van de wizard uit om Azure AD Connect te downloaden en te gebruiken voor het synchroniseren van uw door domein beheerde gebruikers voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="90f17-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="90f17-120">Zie [adreslijstsynchronisatie voor Microsoft 365 instellen](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90f17-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="90f17-121">Als u de opties voor Azure AD Connect configureert, is het raadzaam om **Wachtwoordsynchronisatie** , **naadloze eenmalige aanmelding** en de functie voor het **terugschrijven van wachtwoorden** in te schakelen die ook wordt ondersteund in Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="90f17-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization** , **Seamless Single Sign-On** , and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="90f17-122">U moet extra stappen uitvoeren voor het terugschrijven van wachtwoorden buiten het selectievakje in azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="90f17-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="90f17-123">Zie [procedure: Omschrijf van wachtwoord configureren](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="90f17-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="90f17-124">Zie [Windows 10-apparaten die aan het domein zijn toegevoegd om te worden beheerd door Microsoft 365 Business Premium](manage-windows-devices.md) voor het instellen van een hybride implementatie van Azure AD als u ook Windows 10-apparaten met een domein wilt beheren.</span><span class="sxs-lookup"><span data-stu-id="90f17-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 