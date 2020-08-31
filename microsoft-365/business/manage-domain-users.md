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
description: Synchroniseer domein beheerde gebruikers met Microsoft 365 voor bedrijven.
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306444"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="d9602-103">Domeingebruikers synchroniseren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9602-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="d9602-104">1. voorbereiden op adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="d9602-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="d9602-105">Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, raadpleegt [u voorbereidingen voor adreslijstsynchronisatie met Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="d9602-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="d9602-106">Met name:</span><span class="sxs-lookup"><span data-stu-id="d9602-106">In particular:</span></span>

   - <span data-ttu-id="d9602-107">Zorg ervoor dat er geen dubbele waarden in de adreslijst voorkomen voor de volgende kenmerken: **mail**, **proxyAddresses**en **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="d9602-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="d9602-108">Deze waarden moeten uniek zijn en alle duplicaten moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="d9602-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="d9602-109">We raden u aan het kenmerk **userPrincipalName** (UPN) te configureren voor elk lokaal gebruikersaccount dat overeenkomt met het primaire e-mailadres dat overeenkomt met de gelicentieerde microsoft 365-gebruiker.</span><span class="sxs-lookup"><span data-stu-id="d9602-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="d9602-110">Bijvoorbeeld: *Mary.Shelley@contoso.com* in plaats van *Mary@contoso. lokaal*</span><span class="sxs-lookup"><span data-stu-id="d9602-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="d9602-111">Als het Active Directory-domein eindigt op een niet-routeerbaar achtervoegsel zoals *. lokaal* of *. LAN*, in plaats van een routeerbaar achtervoegsel voor Internet, zoals *. com* of *. org*, past u eerst het UPN-achtervoegsel van de lokale gebruikersaccounts aan zoals wordt beschreven in [een niet-routeerbaar domein voorbereiden op adreslijstsynchronisatie](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="d9602-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="d9602-112">Met de **IdFix run** in stap 4, eronder, wordt ook gecontroleerd of uw on-premises Active Directory gereed is voor synchronisatie van dir.</span><span class="sxs-lookup"><span data-stu-id="d9602-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="d9602-113">2. Azure AD Connect installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="d9602-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="d9602-114">Als u uw gebruikers, groepen en contactpersonen wilt synchroniseren van de lokale Active Directory naar Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in.</span><span class="sxs-lookup"><span data-stu-id="d9602-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="d9602-115">Selecteer in het Beheercentrum in <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> het linkernavigatievenster de optie **instellingen** in de navigatiebalk aan de linkerkant.</span><span class="sxs-lookup"><span data-stu-id="d9602-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="d9602-116">Kies onder **Aanmelden en beveiliging**de optie **weergeven**  onder **gebruikers synchroniseren vanuit de adreslijst van uw organisatie**.</span><span class="sxs-lookup"><span data-stu-id="d9602-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="d9602-117">Kies op de pagina **gebruikers synchroniseren vanaf de adreslijst van uw organisatie** de optie **aan de slag**.</span><span class="sxs-lookup"><span data-stu-id="d9602-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="d9602-118">Voer in het IdFix-hulpprogramma First Step run voor de voorbereiding voor Directory-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="d9602-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="d9602-119">Voer de stappen van de wizard uit om Azure AD Connect te downloaden en te gebruiken voor het synchroniseren van uw door domein beheerde gebruikers voor Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9602-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="d9602-120">Zie [adreslijstsynchronisatie voor Microsoft 365 instellen](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d9602-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="d9602-121">Als u de opties voor Azure AD Connect configureert, is het raadzaam om **Wachtwoordsynchronisatie**, **naadloze eenmalige aanmelding**en de functie voor het **terugschrijven van wachtwoorden** in te schakelen die ook wordt ondersteund in Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="d9602-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="d9602-122">U moet extra stappen uitvoeren voor het terugschrijven van wachtwoorden buiten het selectievakje in azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="d9602-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="d9602-123">Zie [procedure: Omschrijf van wachtwoord configureren](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="d9602-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="d9602-124">Als u Windows 10-apparaten die aan het domein zijn toegevoegd ook wilt beheren, raadpleegt u het artikel toevoegen [aan Windows 10-apparaten inschakelen voor beheer door Microsoft 365 Business Premium](manage-windows-devices.md) voor het instellen van een hybride functie voor Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d9602-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 