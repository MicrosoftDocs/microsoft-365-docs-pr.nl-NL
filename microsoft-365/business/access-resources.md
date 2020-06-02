---
title: On-premises bronnen openen vanaf een azure ad-apparaat in Microsoft 365 Business
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Meer informatie over het openen van on-premises bronnen, zoals branche-apps, bestandsshares en printers vanaf een azure Active Directory-apparaat dat is aangesloten bij Windows 10.
ms.openlocfilehash: 9615ecc9469992d3e5a7479f4799c610db11fb41
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471246"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="44fb7-103">On-premises bronnen openen vanaf een azure ad-apparaat in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="44fb7-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="44fb7-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="44fb7-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="44fb7-105">Elk Windows 10-apparaat dat azure Active Directory is aangesloten, heeft toegang tot alle cloudbronnen, zoals uw Microsoft 365-apps, en kan worden beschermd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="44fb7-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="44fb7-106">U ook toegang verlenen tot on-premises bronnen, zoals LOB-apps, bestandsshares en printers.</span><span class="sxs-lookup"><span data-stu-id="44fb7-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="44fb7-107">Als u toegang wilt toestaan, gebruikt [u Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="44fb7-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="44fb7-108">Zie [Inleiding tot apparaatbeheer in Azure Active Directory voor](https://docs.microsoft.com/azure/active-directory/device-management-introduction)meer informatie.</span><span class="sxs-lookup"><span data-stu-id="44fb7-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="44fb7-109">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="44fb7-109">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="44fb7-110">Deze procedure is alleen van toepassing op OAuth en NTLM.</span><span class="sxs-lookup"><span data-stu-id="44fb7-110">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="44fb7-111">Kerberos wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="44fb7-111">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="44fb7-112">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="44fb7-112">Run Azure AD Connect</span></span>

<span data-ttu-id="44fb7-113">Voer de volgende stappen uit om de azure ad-apparaten van uw organisatie toegang te geven tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="44fb7-113">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="44fb7-114">Als u uw gebruikers, groepen en contactpersonen van lokale Active Directory wilt synchroniseren met Azure Active Directory, voert u de wizard Mapsynchronisatie en Azure AD Connect uit zoals beschreven in [Mapsynchronisatie instellen voor Office 365.](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)</span><span class="sxs-lookup"><span data-stu-id="44fb7-114">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="44fb7-115">Nadat de mapsynchronisatie is voltooid, controleert u of de Windows 10-apparaten van uw organisatie Azure AD zijn aangesloten.</span><span class="sxs-lookup"><span data-stu-id="44fb7-115">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="44fb7-116">Deze stap wordt individueel uitgevoerd op elk Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="44fb7-116">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="44fb7-117">Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="44fb7-117">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="44fb7-118">Zodra de Windows 10-apparaten azure ad zijn aangesloten, moet elke gebruiker zijn apparaten opnieuw opstarten en zich aanmelden met zijn Microsoft 365 Business Premium-referenties.</span><span class="sxs-lookup"><span data-stu-id="44fb7-118">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="44fb7-119">Alle apparaten hebben nu ook toegang tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="44fb7-119">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="44fb7-120">Er zijn geen extra stappen vereist om toegang te krijgen tot on-premises bronnen voor azure AD-apparaten.</span><span class="sxs-lookup"><span data-stu-id="44fb7-120">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="44fb7-121">Deze functionaliteit is ingebouwd in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="44fb7-121">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="44fb7-122">Als u van plan bent om in te loggen op het AADJ-apparaat, met uitzondering van wachtwoordmethode Zoals pin/bio-metric via het inloggen op whfb-referentiegegevens en vervolgens toegang te krijgen tot on-premise bronnen (shares,printers.. etc), volg danhttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="44fb7-122">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="44fb7-123">Als uw organisatie niet klaar is om te implementeren in de hierboven beschreven azure AD joined-apparaatconfiguratie, u overwegen de configuratie van [hybride Azure AD Joined in](manage-windows-devices.md)te stellen.</span><span class="sxs-lookup"><span data-stu-id="44fb7-123">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="44fb7-124">Overwegingen wanneer u Windows-apparaten aansluit bij Azure AD</span><span class="sxs-lookup"><span data-stu-id="44fb7-124">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="44fb7-125">Als het Windows-apparaat waarmee Azure-AD is lid geworden, eerder is aangesloten bij het domein of in een werkgroep, moet u de volgende beperkingen overwegen:</span><span class="sxs-lookup"><span data-stu-id="44fb7-125">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="44fb7-126">Wanneer een apparaat azure AD wordt samengevoegd, maakt het een nieuwe gebruiker zonder te verwijzen naar een bestaand profiel.</span><span class="sxs-lookup"><span data-stu-id="44fb7-126">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="44fb7-127">Profielen moeten handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="44fb7-127">Profiles must be manually migrated.</span></span> <span data-ttu-id="44fb7-128">Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en menu-instellingen starten.</span><span class="sxs-lookup"><span data-stu-id="44fb7-128">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="44fb7-129">Een beste aanpak is het vinden van een tool van derden om bestaande bestanden en instellingen in kaart te brengen aan het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="44fb7-129">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="44fb7-130">Als het apparaat Groepsbeleidsobjecten (GPO' s) gebruikt, hebben sommige GPO's mogelijk geen vergelijkbare [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span><span class="sxs-lookup"><span data-stu-id="44fb7-130">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="44fb7-131">Voer de [MMAT-tool](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare CSP's voor bestaande GPO's te vinden.</span><span class="sxs-lookup"><span data-stu-id="44fb7-131">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="44fb7-132">Gebruikers kunnen zich niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie.</span><span class="sxs-lookup"><span data-stu-id="44fb7-132">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="44fb7-133">Evalueer de verouderde app en overweeg om te updaten naar een app die gebruik maakt van de moderne Auth, indien mogelijk.</span><span class="sxs-lookup"><span data-stu-id="44fb7-133">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="44fb7-134">Active Directory-printerdetectie werkt niet.</span><span class="sxs-lookup"><span data-stu-id="44fb7-134">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="44fb7-135">U directe printerpaden bieden voor alle gebruikers of [Hybride cloudprint](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="44fb7-135">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
