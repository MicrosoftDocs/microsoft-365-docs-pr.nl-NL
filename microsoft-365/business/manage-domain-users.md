---
title: Domeingebruikers synchroniseren met Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Domeingestuurde gebruikers synchroniseren met Microsoft 365 voor Bedrijven.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578402"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="51647-103">Domeingebruikers synchroniseren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="51647-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="51647-104">1. Voorbereidingen treffen voor adreslijstsynchronisatie</span><span class="sxs-lookup"><span data-stu-id="51647-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="51647-105">Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, bekijkt u Voorbereiden op [adreslijstsynchronisatie met Microsoft 365.](../enterprise/prepare-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="51647-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](../enterprise/prepare-for-directory-synchronization.md).</span></span> <span data-ttu-id="51647-106">In het bijzonder:</span><span class="sxs-lookup"><span data-stu-id="51647-106">In particular:</span></span>

   - <span data-ttu-id="51647-107">Zorg ervoor dat er geen duplicaten aanwezig zijn in uw adreslijst voor de volgende kenmerken: **e-mail,** **proxyAddresses** en **userPrincipalName.**</span><span class="sxs-lookup"><span data-stu-id="51647-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="51647-108">Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="51647-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="51647-109">U wordt aangeraden het **kenmerk userPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren op basis van het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker.</span><span class="sxs-lookup"><span data-stu-id="51647-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="51647-110">Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="51647-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="51647-111">Als het Active Directory-domein eindigt op een niet-routable achtervoegsel zoals *.local* of *.lan*, in plaats van een internet routable suffix zoals *.com* of *.org*, past u eerst het UPN-achtervoegsel van de lokale gebruikersaccounts aan, zoals beschreven in Een niet-routable domain voorbereiden voor [adreslijstsynchronisatie.](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="51647-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md).</span></span> 

<span data-ttu-id="51647-112">Met **IdFix** uitvoeren in stap vier (4) hieronder, wordt er ook voor zorgen dat uw on-premises Active Directory gereed is voor adreslijstsynchronisatie.</span><span class="sxs-lookup"><span data-stu-id="51647-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for directory synchronization.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="51647-113">2. Azure AD Connect installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="51647-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="51647-114">Als u uw gebruikers, groepen en contactpersonen vanuit de lokale Active Directory wilt synchroniseren met Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in.</span><span class="sxs-lookup"><span data-stu-id="51647-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="51647-115">Selecteer instellen in het linkernavigatienavigatiecentrum **in** het [beheercentrum.](https://go.microsoft.com/fwlink/p/?linkid=2024339)</span><span class="sxs-lookup"><span data-stu-id="51647-115">In the [admin center](https://go.microsoft.com/fwlink/p/?linkid=2024339), select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="51647-116">Kies **onder Aanmelden en beveiliging** de optie **Weergeven** onder Gebruikers synchroniseren vanuit **de adreslijst van uw organisatie.**</span><span class="sxs-lookup"><span data-stu-id="51647-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="51647-117">Kies op de pagina Gebruikers synchroniseren op de **adreslijstpagina** van uw organisatie de optie **Aan de slag.**</span><span class="sxs-lookup"><span data-stu-id="51647-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="51647-118">Voer in de eerste stap Het hulpprogramma IdFix uit om de synchronisatie van adreslijst voor te bereiden.</span><span class="sxs-lookup"><span data-stu-id="51647-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="51647-119">Volg de wizardstappen om Azure AD Connect te downloaden en deze te gebruiken om uw domeingestuurde gebruikers te synchroniseren met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="51647-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="51647-120">Zie [Adreslijstsynchronisatie instellen voor Microsoft 365](../enterprise/set-up-directory-synchronization.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51647-120">See [Set up directory synchronization for Microsoft 365](../enterprise/set-up-directory-synchronization.md) to learn more.</span></span>

<span data-ttu-id="51647-121">Wanneer u uw opties configureert voor Azure AD Connect, raden we u aan  wachtwoordsynchronisatie, naadloze een-aan-/uit-tekenfunctie en de functie voor het terugschrijven van wachtwoorden in te stellen, die ook wordt ondersteund in Microsoft 365 voor Bedrijven. </span><span class="sxs-lookup"><span data-stu-id="51647-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="51647-122">Er zijn enkele extra stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="51647-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="51647-123">Zie [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="51647-123">For more information, see [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="51647-124">Als u ook windows 10-apparaten met een domein wilt beheren, zie Windows [10-apparaten](manage-windows-devices.md) die zijn verbonden met een domein, door Microsoft 365 Business Premium worden beheerd om een hybride Azure AD Join in te stellen.</span><span class="sxs-lookup"><span data-stu-id="51647-124">If you also want to manage domain-joined Windows 10 devices, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span>