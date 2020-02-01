---
title: On-premises bronnen openen vanaf een Azure AD-verbonden apparaat in Microsoft 365 Business
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.collection: M365-subscription-management
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Meer informatie over het krijgen van toegang tot on-premises bronnen, zoals bedrijfsapps, bestandsshares en printers vanaf een Azure Active Directory-apparaat.
ms.openlocfilehash: 653b53d29e84bbdc91273cb78b9b8407c0f6a209
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41593228"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="358a5-103">On-premises bronnen openen vanaf een Azure AD-verbonden apparaat in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="358a5-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="358a5-104">Elk Windows 10-apparaat met Azure Active Directory is aangesloten, heeft toegang tot alle cloudbronnen, zoals uw Office 365-apps, en kan worden beschermd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="358a5-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Office 365 apps, and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="358a5-105">U ook toegang verlenen tot on-premises resources zoals LOB-apps, bestandsshares en printers van bedrijfsactiviteiten.</span><span class="sxs-lookup"><span data-stu-id="358a5-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="358a5-106">Gebruik [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory om toegang toe te staan.</span><span class="sxs-lookup"><span data-stu-id="358a5-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="358a5-107">Zie [Inleiding tot apparaatbeheer in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="358a5-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="358a5-108">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="358a5-108">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="358a5-109">Deze procedure is alleen van toepassing op OAuth en NTLM.</span><span class="sxs-lookup"><span data-stu-id="358a5-109">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="358a5-110">Kerberos wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="358a5-110">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="358a5-111">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="358a5-111">Run Azure AD Connect</span></span>

<span data-ttu-id="358a5-112">Voer de volgende stappen uit om de Azure AD-verbonden apparaten van uw organisatie toegang te geven tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="358a5-112">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="358a5-113">Voer de wizard Adreslijstsynchronisatie en Azure AD Connect uit zoals beschreven in [Adreslijstsynchronisatie voor Office 365,](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)als u uw gebruikers, groepen en contactpersonen van lokale Active Directory wilt synchroniseren in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="358a5-113">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="358a5-114">Nadat de adreslijstsynchronisatie is voltooid, moet u ervoor zorgen dat de Windows 10-apparaten van uw organisatie Azure AD zijn aangesloten.</span><span class="sxs-lookup"><span data-stu-id="358a5-114">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="358a5-115">Deze stap wordt afzonderlijk gedaan op elk Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="358a5-115">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="358a5-116">Zie [Windows-apparaten instellen voor Microsoft 365 Business-gebruikers](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="358a5-116">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="358a5-117">Zodra de Windows 10-apparaten zijn samengevoegd met Azure AD, moet elke gebruiker zijn apparaten opnieuw opstarten en zich aanmelden met zijn Microsoft 365 Business-referenties.</span><span class="sxs-lookup"><span data-stu-id="358a5-117">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="358a5-118">Alle apparaten hebben nu ook toegang tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="358a5-118">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="358a5-119">Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor azure AD-verbonden apparaten.</span><span class="sxs-lookup"><span data-stu-id="358a5-119">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="358a5-120">Deze functionaliteit is ingebouwd in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="358a5-120">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="358a5-121">Als u plannen hebt om in te loggen op het AADJ-apparaat, andere dan wachtwoordmethode Zoals PIN / Bio-metric via WHFB referentie login en vervolgens toegang on-premise bronnen (aandelen, printers.. etc), volghttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="358a5-121">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="358a5-122">Als uw organisatie nog niet klaar is om te implementeren in de hierboven beschreven Azure AD-apparaatconfiguratie, u overwegen de configuratie van [hybride Azure AD-verbonden apparaat](manage-windows-devices.md)in te stellen.</span><span class="sxs-lookup"><span data-stu-id="358a5-122">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="358a5-123">Overwegingen wanneer u lid wordt van Windows-apparaten op Azure AD</span><span class="sxs-lookup"><span data-stu-id="358a5-123">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="358a5-124">Houd rekening met de volgende beperkingen als het Windows-apparaat waarvan u lid is geworden van Azure-AD eerder is verbonden met domeinof in een werkgroep:</span><span class="sxs-lookup"><span data-stu-id="358a5-124">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="358a5-125">Wanneer een apparaat Azure AD wordt lid, maakt het een nieuwe gebruiker zonder te verwijzen naar een bestaand profiel.</span><span class="sxs-lookup"><span data-stu-id="358a5-125">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="358a5-126">Profielen moeten handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="358a5-126">Profiles must be manually migrated.</span></span> <span data-ttu-id="358a5-127">Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en menu-instellingen starten.</span><span class="sxs-lookup"><span data-stu-id="358a5-127">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="358a5-128">Een beste aanpak is het vinden van een tool van derden om bestaande bestanden en instellingen in kaart te brengen naar het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="358a5-128">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="358a5-129">Als het apparaat groepsbeleidsobjecten (GPO) gebruikt, hebben sommige GPO's mogelijk geen vergelijkbare [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span><span class="sxs-lookup"><span data-stu-id="358a5-129">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="358a5-130">Voer de [MMAT-tool](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare CSP's te vinden voor bestaande GPO's.</span><span class="sxs-lookup"><span data-stu-id="358a5-130">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="358a5-131">Gebruikers kunnen zich niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie.</span><span class="sxs-lookup"><span data-stu-id="358a5-131">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="358a5-132">Evalueer de verouderde app en overweeg om zo mogelijk te updaten naar een app die gebruik maakt van het moderne Auth.</span><span class="sxs-lookup"><span data-stu-id="358a5-132">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="358a5-133">Active Directory-printerdetectie werkt niet.</span><span class="sxs-lookup"><span data-stu-id="358a5-133">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="358a5-134">U directe printerpaden voor alle gebruikers bieden of [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="358a5-134">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
