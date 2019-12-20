---
title: Toegang tot on-premises bronnen van een Azure AD-apparaat in Microsoft 365 Business
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
description: Informatie over hoe u toegang krijgt tot on-premises resources, zoals zakelijke apps, bestandsshares en printers, vanuit een Azure Active Directory dat is gekoppeld aan een Windows 10-apparaat.
ms.openlocfilehash: 89ac38f3da9cbdd3ff1a5eb33dc129d2e83521c7
ms.sourcegitcommit: 8c244b38c43dd00c4ef0102f8bed02ab36639a6b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/10/2019
ms.locfileid: "39967158"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="b2e34-103">Toegang tot on-premises bronnen van een Azure AD-apparaat in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b2e34-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="b2e34-104">Elk Windows 10-apparaat dat is Azure Active Directory toegevoegd heeft toegang tot alle cloud-gebaseerde resources, zoals uw Office 365-apps en kan worden beveiligd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="b2e34-104">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Office 365 apps, and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="b2e34-105">U ook toegang verlenen tot on-premises resources, zoals LOB-apps (line of Business), bestandsshares en printers.</span><span class="sxs-lookup"><span data-stu-id="b2e34-105">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="b2e34-106">Als u toegang wilt toestaan, gebruikt u [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b2e34-106">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="b2e34-107">Zie voor meer informatie, [Inleiding tot Apparaatbeheer in azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="b2e34-107">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="b2e34-108">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="b2e34-108">The steps are also summarized in the following sections.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b2e34-109">Deze procedure is alleen van toepassing op OAuth en NTLM.</span><span class="sxs-lookup"><span data-stu-id="b2e34-109">This procedure is only applicable to OAuth and NTLM.</span></span> <span data-ttu-id="b2e34-110">Kerberos wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="b2e34-110">Kerberos is not supported.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="b2e34-111">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="b2e34-111">Run Azure AD Connect</span></span>

<span data-ttu-id="b2e34-112">Voltooi de volgende stappen om in te schakelen van uw organisatie Azure AD gekoppelde apparaten voor toegang tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="b2e34-112">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="b2e34-113">Voor het synchroniseren van uw gebruikers, groepen en contactpersonen van lokale Active Directory in azure Active Directory, voert u de wizard Directory-synchronisatie en Azure AD Connect zoals beschreven in [Directory-synchronisatie voor Office 365 instellen](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="b2e34-113">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="b2e34-114">Nadat de adreslijstsynchronisatie voltooid is, zorg ervoor dat de Windows 10-apparaten van uw organisatie zijn gekoppeld aan Azure AD.</span><span class="sxs-lookup"><span data-stu-id="b2e34-114">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="b2e34-115">Deze stap wordt afzonderlijk uitgevoerd op elk apparaat met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b2e34-115">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="b2e34-116">Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b2e34-116">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="b2e34-117">Zodra de Windows 10-apparaten Azure AD zijn gekoppeld, moet elke gebruiker hun apparaten opnieuw opstarten en meld u aan met hun Microsoft 365 zakelijke referenties.</span><span class="sxs-lookup"><span data-stu-id="b2e34-117">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="b2e34-118">Alle apparaten hebben nu ook toegang tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="b2e34-118">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="b2e34-119">Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor Azure AD gekoppelde apparaten.</span><span class="sxs-lookup"><span data-stu-id="b2e34-119">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="b2e34-120">Deze functionaliteit is ingebouwd in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b2e34-120">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="b2e34-121">Als u van plan bent om in te loggen op het AADJ-apparaat anders dan de wachtwoord methode zoals PIN/bio-metric via WHFB-inloggegevens en vervolgens toegang tot on-premise bronnen (shares, printers.. etc), volg danhttps://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="b2e34-121">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="b2e34-122">Als uw organisatie niet gereed is voor implementatie in de Azure AD gekoppelde apparaatconfiguratie die hierboven wordt beschreven, u overwegen [hybride Azure AD gekoppelde apparaatconfiguratie](manage-windows-devices.md)in te stellen.</span><span class="sxs-lookup"><span data-stu-id="b2e34-122">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="b2e34-123">Overwegingen bij het toevoegen van Windows-apparaten aan Azure AD</span><span class="sxs-lookup"><span data-stu-id="b2e34-123">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="b2e34-124">Houd rekening met de volgende beperkingen als het Windows-apparaat waaraan u Azure-AD is toegevoegd, eerder lid was van een domein of in een werkgroep:</span><span class="sxs-lookup"><span data-stu-id="b2e34-124">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="b2e34-125">Wanneer een apparaat Azure AD wordt toegevoegd, wordt een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel.</span><span class="sxs-lookup"><span data-stu-id="b2e34-125">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="b2e34-126">Profielen moeten handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="b2e34-126">Profiles must be manually migrated.</span></span> <span data-ttu-id="b2e34-127">Een gebruikersprofiel bevat informatie zoals Favorieten, lokale bestanden, browserinstellingen en instellingen van het menu Start.</span><span class="sxs-lookup"><span data-stu-id="b2e34-127">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="b2e34-128">De beste manier is om een hulpprogramma van derden te vinden voor het toewijzen van bestaande bestanden en instellingen aan het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="b2e34-128">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="b2e34-129">Als het apparaat gebruikmaakt van groepsbeleidsobjecten (GPO), hebben sommige groepsbeleidobjecten mogelijk geen vergelijkbare [configuratie service provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in intune.</span><span class="sxs-lookup"><span data-stu-id="b2e34-129">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="b2e34-130">Voer het [hulpprogramma Mmat](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare csp's voor bestaande groepsbeleidobjecten te vinden.</span><span class="sxs-lookup"><span data-stu-id="b2e34-130">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="b2e34-131">Gebruikers kunnen niet worden geverifieerd bij toepassingen die afhankelijk van Active Directory-verificatie zijn.</span><span class="sxs-lookup"><span data-stu-id="b2e34-131">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="b2e34-132">Evalueer de oude app en overweeg een update naar een app die gebruikmaakt van moderne auth, indien mogelijk.</span><span class="sxs-lookup"><span data-stu-id="b2e34-132">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="b2e34-133">Detectie van Active Directory-printer werkt niet.</span><span class="sxs-lookup"><span data-stu-id="b2e34-133">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="b2e34-134">U directe printer paden bieden voor alle gebruikers of [hybride Cloud print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy)gebruiken.</span><span class="sxs-lookup"><span data-stu-id="b2e34-134">You can provide direct printer paths for all users or use [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
