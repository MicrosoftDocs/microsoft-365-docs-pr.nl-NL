---
title: On-premises resources openen vanuit een Azure AD-apparaat in Microsoft 365 Business
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
description: Meer informatie over hoe u toegang krijgt tot on-premises bronnen, zoals line-of-Business-Apps, bestandsshares en printers van een Azure Active Directory-apparaat met Windows 10.
ms.openlocfilehash: 22edf0c23d6318e1f70bcb21b2cd697ea0a75da4
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688228"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="3c261-103">On-premises resources openen vanuit een Azure AD-domein dat is gekoppeld aan Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="3c261-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="3c261-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3c261-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="3c261-105">Een Windows 10-apparaat dat Azure Active Directory is aangemeld, heeft toegang tot alle bronnen op basis van de Cloud, zoals uw Microsoft 365-apps, en kan worden beveiligd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3c261-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="3c261-106">U kunt ook toegang verlenen tot on-premises bronnen, zoals LOB-apps (line of Business), bestandsshares en printers.</span><span class="sxs-lookup"><span data-stu-id="3c261-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="3c261-107">Als u toegang wilt toestaan, gebruikt u [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3c261-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="3c261-108">Zie [Inleiding tot Apparaatbeheer in azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c261-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="3c261-109">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="3c261-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="3c261-110">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="3c261-110">Run Azure AD Connect</span></span>

<span data-ttu-id="3c261-111">Voer de volgende stappen uit om in te stellen dat de Azure Active Directory-apparaten van uw organisatie toegang hebben tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="3c261-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="3c261-112">Als u uw gebruikers, groepen en contactpersonen wilt synchroniseren van lokale Active Directory naar Azure Active Directory, voert u de wizard adreslijstsynchronisatie en Azure AD Connect uit, zoals wordt beschreven in [adreslijstsynchronisatie instellen voor Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span><span class="sxs-lookup"><span data-stu-id="3c261-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="3c261-113">Wanneer de adreslijstsynchronisatie is voltooid, controleert u of de Windows 10-apparaten van uw organisatie aan Azure AD zijn toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="3c261-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="3c261-114">Deze stap gaat afzonderlijk op elk Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="3c261-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="3c261-115">Zie [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3c261-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="3c261-116">Wanneer de Windows 10-apparaten Azure AD zijn toegevoegd, moet elke gebruiker zijn of haar apparaten opnieuw opstarten en zich aanmelden met de referenties van Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="3c261-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="3c261-117">Alle apparaten hebben nu ook toegang tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="3c261-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="3c261-118">Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor gekoppelde apparaten in azure AD.</span><span class="sxs-lookup"><span data-stu-id="3c261-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="3c261-119">Deze functionaliteit is ingebouwd in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="3c261-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="3c261-120">Als u een abonnement hebt om u aan te melden bij het AADJ-apparaat, zoals pincode/bio-metric via WHFB Credential login en vervolgens toegang tot on-premises resources (shares, printers. etc), kunt u het volgende doen https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="3c261-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="3c261-121">Als uw organisatie niet klaar is om te implementeren in de hierboven beschreven configuratie van Azure AD, kunt u overwegen om de configuratie van de [hybride Azure AD-apparaat](manage-windows-devices.md)in te stellen.</span><span class="sxs-lookup"><span data-stu-id="3c261-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="3c261-122">Aandachtspunten wanneer u deelneemt aan Windows-apparaten aan Azure AD</span><span class="sxs-lookup"><span data-stu-id="3c261-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="3c261-123">Als het Windows-apparaat waarvan u Azure-AD lid bent geworden, eerder domein of een werkgroep is, kunt u de volgende beperkingen overwegen:</span><span class="sxs-lookup"><span data-stu-id="3c261-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="3c261-124">Wanneer een apparaat van Azure AD wordt samengevoegd, wordt er een nieuwe gebruiker gemaakt zonder op een bestaand profiel te verwijzen.</span><span class="sxs-lookup"><span data-stu-id="3c261-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="3c261-125">Profielen moeten handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="3c261-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="3c261-126">Een gebruikersprofiel bevat informatie, zoals Favorieten, lokale bestanden, browserinstellingen en menu Start-menu instellingen.</span><span class="sxs-lookup"><span data-stu-id="3c261-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="3c261-127">Een beste manier is om een hulpmiddel van een derde partij te zoeken waarmee u bestaande bestanden en instellingen kunt toewijzen aan het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="3c261-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="3c261-128">Als het apparaat gebruikmaakt van groepsbeleidsobjecten (groepsbeleidsobjecten), hebben sommige Gpo's mogelijk geen vergelijkbaar [Configuration service provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in intune.</span><span class="sxs-lookup"><span data-stu-id="3c261-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="3c261-129">Voer het [hulpprogramma MMAT](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare csp's voor bestaande gpo's te zoeken.</span><span class="sxs-lookup"><span data-stu-id="3c261-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="3c261-130">Gebruikers kunnen zich niet verifiëren met toepassingen die afhankelijk zijn van Active Directory-verificatie.</span><span class="sxs-lookup"><span data-stu-id="3c261-130">Users won't be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="3c261-131">Evalueer de oudere app en overweeg, indien mogelijk, bij te werken naar een app die gebruikmaakt van moderne auth.</span><span class="sxs-lookup"><span data-stu-id="3c261-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="3c261-132">Active Directory-Printer detectie werkt niet.</span><span class="sxs-lookup"><span data-stu-id="3c261-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="3c261-133">U kunt direct printer paden voor alle gebruikers geven of [universeel afdrukken](https://aka.ms/UPDocs).</span><span class="sxs-lookup"><span data-stu-id="3c261-133">You can provide direct printer paths for all users or use [Universal Print](https://aka.ms/UPDocs).</span></span>
