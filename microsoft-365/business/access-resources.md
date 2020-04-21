---
title: On-premises resources openen vanaf een apparaat dat is verbonden met Azure AD in Microsoft 365 Business
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
description: Meer informatie over hoe u toegang krijgt tot on-premises bronnen zoals bedrijfsapps, bestandsshares en printers van een Azure Active Directory dat is toegetreden tot Windows 10-apparaat.
ms.openlocfilehash: c1e04e5ca0d36c32a55a9819140356db5093e3a1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627449"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="dfcf3-103">On-premises resources openen vanaf een apparaat dat is verbonden met Azure AD in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="dfcf3-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="dfcf3-104">Elk Windows 10-apparaat dat Azure Active Directory heeft samengevoegd, heeft toegang tot alle cloudbronnen, zoals uw Microsoft 365-apps, en kan worden beschermd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="dfcf3-105">U ook toegang verlenen tot on-premises bronnen zoals LOB-apps (Line of Business), bestandsshares en printers.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="dfcf3-106">Als u toegang wilt verlenen, gebruikt u [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="dfcf3-107">Zie [Inleiding tot apparaatbeheer in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="dfcf3-108">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-108">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dfcf3-109">Deze procedure is alleen van toepassing op OAuth en NTLM.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-109">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="dfcf3-110">Kerberos wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-110">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="dfcf3-111">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="dfcf3-111">Run Azure AD Connect</span></span>

<span data-ttu-id="dfcf3-112">Voer de volgende stappen uit om de Azure AD-apparaten van uw organisatie toegang te geven tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-112">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="dfcf3-113">Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory wilt synchroniseren met Azure Active Directory, voert u de wizard Adressynchronisatie en Azure AD Connect uit zoals beschreven in [Adreslijstsynchronisatie instellen voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="dfcf3-113">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="dfcf3-114">Nadat de adreslijstsynchronisatie is voltooid, controleert u of de Windows 10-apparaten van uw organisatie zijn aangesloten bij Azure AD.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-114">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="dfcf3-115">Deze stap wordt individueel gedaan op elk Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-115">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="dfcf3-116">Zie [Windows-apparaten instellen voor Microsoft 365 Business Premium-gebruikers](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-116">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="dfcf3-117">Zodra de Windows 10-apparaten zijn aangesloten op Azure AD, moet elke gebruiker zijn apparaten opnieuw opstarten en zich aanmelden met hun Microsoft 365 Business Premium-referenties.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-117">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="dfcf3-118">Alle apparaten hebben nu ook toegang tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-118">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="dfcf3-119">Er zijn geen extra stappen vereist om toegang te krijgen tot on-premises bronnen voor Azure AD-apparaten.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-119">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="dfcf3-120">Deze functionaliteit is ingebouwd in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-120">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="dfcf3-121">Als u plannen hebt om in te loggen op het AADJ-apparaat, andere dan wachtwoordmethode Zoals PIN / Bio-metric via WHFB-inloggegevens en vervolgens toegang hebt tot on-premise bronnen (shares,printers.. etc), volghttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="dfcf3-121">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="dfcf3-122">Als uw organisatie nog niet klaar is om te worden geïmplementeerd in de hierboven beschreven Azure AD-apparaatconfiguratie, u overwegen [de configuratie van hybride Azure AD Joined-apparaat](manage-windows-devices.md)in te stellen.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-122">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="dfcf3-123">Overwegingen wanneer u Windows-apparaten aansluit bij Azure AD</span><span class="sxs-lookup"><span data-stu-id="dfcf3-123">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="dfcf3-124">Als het Windows-apparaat waarvan u Azure-AD lid van het Bureaublad bent geworden, eerder is verbonden aan het domein of in een werkgroep, moet u rekening houden met de volgende beperkingen:</span><span class="sxs-lookup"><span data-stu-id="dfcf3-124">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="dfcf3-125">Wanneer een apparaat azure AD lid wordt, wordt een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-125">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="dfcf3-126">Profielen moeten handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-126">Profiles must be manually migrated.</span></span> <span data-ttu-id="dfcf3-127">Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en menu-instellingen voor het starten.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-127">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="dfcf3-128">Een beste aanpak is het vinden van een tool van derden om bestaande bestanden en instellingen in kaart te brengen naar het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-128">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="dfcf3-129">Als het apparaat Groepsbeleidsobjecten (GPO) gebruikt, hebben sommige GPO's mogelijk geen vergelijkbare [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-129">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="dfcf3-130">Voer de [MMAT-tool](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare CSP's voor bestaande GPO's te vinden.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-130">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="dfcf3-131">Gebruikers kunnen zich niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-131">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="dfcf3-132">Evalueer de verouderde app en overweeg te updaten naar een app die gebruik maakt van moderne Auth, indien mogelijk.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-132">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="dfcf3-133">Detectie van Active Directory-printers werkt niet.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-133">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="dfcf3-134">U directe printerpaden voor alle gebruikers bieden of [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="dfcf3-134">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
