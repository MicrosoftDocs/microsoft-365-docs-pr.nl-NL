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
description: Synchroniseer domeingestuurde gebruikers met Microsoft 365 voor bedrijven.
ms.openlocfilehash: af9cb7c9b2b639edc2375679a73ab41c4cf6de71
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080057"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a><span data-ttu-id="eba38-103">Domeingebruikers synchroniseren met Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="eba38-103">Synchronize domain users to Microsoft 365</span></span>

## <a name="1-prepare-for-directory-synchronization"></a><span data-ttu-id="eba38-104">1. Voorbereiden op directorysynchronisatie</span><span class="sxs-lookup"><span data-stu-id="eba38-104">1. Prepare for Directory Synchronization</span></span> 

<span data-ttu-id="eba38-105">Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert [u Voorbereiden op adreslijstsynchronisatie naar Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="eba38-105">Before you synchronize your users and computers from the local Active Directory Domain, review [Prepare for directory synchronization to Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization).</span></span> <span data-ttu-id="eba38-106">In het bijzonder:</span><span class="sxs-lookup"><span data-stu-id="eba38-106">In particular:</span></span>

   - <span data-ttu-id="eba38-107">Zorg ervoor dat er geen duplicaten in uw map bestaan voor de volgende kenmerken: **e-mail,** **proxyAdressen**en **userPrincipalName**.</span><span class="sxs-lookup"><span data-stu-id="eba38-107">Make sure that no duplicates exist in your directory for the following attributes: **mail**, **proxyAddresses**, and **userPrincipalName**.</span></span> <span data-ttu-id="eba38-108">Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.</span><span class="sxs-lookup"><span data-stu-id="eba38-108">These values must be unique and any duplicates must be removed.</span></span>
   
   - <span data-ttu-id="eba38-109">We raden u aan het kenmerk **USERPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren op basis van het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker.</span><span class="sxs-lookup"><span data-stu-id="eba38-109">We recommend that you configure the **userPrincipalName** (UPN) attribute for each local user account to match the primary email address that corresponds to the licensed Microsoft 365 user.</span></span> <span data-ttu-id="eba38-110">Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*</span><span class="sxs-lookup"><span data-stu-id="eba38-110">For example: *mary.shelley@contoso.com* rather than *mary@contoso.local*</span></span>
   
   - <span data-ttu-id="eba38-111">Als het Active Directory-domein eindigt in een niet-routeerbaar achtervoegsel zoals *.local* of *.lan*, in plaats van een internetroertable achtervoegsel zoals *.com* of *.org,* past u eerst het UPN-achtervoegsel van het lokale gebruikersaccounts aan zoals beschreven in [Een niet-routeerbaar domein voorbereiden voor adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="eba38-111">If the Active Directory domain ends in a non-routable suffix like *.local* or *.lan*, instead of an internet routable suffix such as *.com* or *.org*, adjust the UPN suffix of the local user accounts first as described in [Prepare a non-routable domain for directory synchronization](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization).</span></span> 

<span data-ttu-id="eba38-112">De **Run IdFix** in stap vier (4) hieronder, zorgt er ook voor dat uw on-premises Active Directory klaar is voor dir-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="eba38-112">The **Run IdFix** in step four (4) below, will also make sure your on-premises Active Directory is ready for dir sync.</span></span>

## <a name="2-install-and-configure-azure-ad-connect"></a><span data-ttu-id="eba38-113">2. Azure AD Connect installeren en configureren</span><span class="sxs-lookup"><span data-stu-id="eba38-113">2. Install and configure Azure AD Connect</span></span>

<span data-ttu-id="eba38-114">Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory wilt synchroniseren met Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in.</span><span class="sxs-lookup"><span data-stu-id="eba38-114">To synchronize your users, groups, and contacts from the local Active Directory into Azure Active Directory, install Azure Active Directory Connect and set up directory synchronization.</span></span> 

 1. <span data-ttu-id="eba38-115">In het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> de optie **Setup** in het linkernavigatiesysteem.</span><span class="sxs-lookup"><span data-stu-id="eba38-115">In the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> select **Setup** in the left nav.</span></span>

 2. <span data-ttu-id="eba38-116">Kies Onder **Aanmelden en beveiliging**de optie **Weergave** onder Gebruikers synchroniseren in de map van **uw organisatie.**</span><span class="sxs-lookup"><span data-stu-id="eba38-116">Under **Sign-in and security**, choose **View**  under **Sync users from your org's directory**.</span></span>

 3. <span data-ttu-id="eba38-117">Kies op de **pagina Gebruikers synchroniseren vanaf de map van uw organisatie** de optie Aan de **slag**.</span><span class="sxs-lookup"><span data-stu-id="eba38-117">On the **Sync users from your org's directory** page, choose **Get started**.</span></span>

 4. <span data-ttu-id="eba38-118">Voer in de eerste stap idfix-gereedschap uit om u voor te bereiden op Directory-synchronisatie.</span><span class="sxs-lookup"><span data-stu-id="eba38-118">In the first step  run IdFix tool to prepare for Directory sync.</span></span>

 5. <span data-ttu-id="eba38-119">Volg de wizardstappen om Azure AD Connect te downloaden en deze te gebruiken om uw domeingestuurde gebruikers te synchroniseren met Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="eba38-119">Follow the wizard steps to download Azure AD Connect and use it to synchronize your domain-controlled users to Microsoft 365.</span></span>


<span data-ttu-id="eba38-120">Zie [Mapsynchronisatie instellen voor Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="eba38-120">See [Set up directory synchronization for Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) to learn more.</span></span>

<span data-ttu-id="eba38-121">Terwijl u uw opties voor Azure AD Connect configureert, raden we u aan **wachtwoordsynchronisatie,** **naadloze aanmelding met één aanmelding**en de functie voor het **terugschrijven van wachtwoorden** in te schakelen, die ook wordt ondersteund in Microsoft 365 voor bedrijven.</span><span class="sxs-lookup"><span data-stu-id="eba38-121">As you configure your options for Azure AD Connect, we recommend that you enable **Password Synchronization**, **Seamless Single Sign-On**, and the **password writeback** feature, which is also supported in Microsoft 365 for business.</span></span>

> [!NOTE]
> <span data-ttu-id="eba38-122">Er zijn enkele extra stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="eba38-122">There are some additional steps for password writeback beyond the check box in Azure AD Connect.</span></span> <span data-ttu-id="eba38-123">Zie Hoe voor meer [informatie: wachtwoordschrijftijd configureren.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)</span><span class="sxs-lookup"><span data-stu-id="eba38-123">For more information, see [How-to: configure password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback).</span></span> 

<span data-ttu-id="eba38-124">Als u ook windows 10-apparaten met domein wilt beheren, [raadpleegt u Windows 10-apparaten inschakelen die door Microsoft 365 Business Premium moeten worden beheerd](manage-windows-devices.md) om een hybride Azure AD Join-join in te stellen.</span><span class="sxs-lookup"><span data-stu-id="eba38-124">If you want to manage domain-joined Windows 10 devices also, see [Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business Premium](manage-windows-devices.md) to set up a hybrid Azure AD Join.</span></span> 