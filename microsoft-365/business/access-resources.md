---
title: On-premises bronnen openen vanaf een apparaat dat lid is van Azure AD in Microsoft 365 Business
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
description: Lees hoe u toegang krijgt tot on-premises bronnen, zoals line-of-business-apps, bestands shares en printers vanaf een Windows 10-apparaat dat is aangesloten op Azure Active Directory.
ms.openlocfilehash: fc02fd30f41f25f52e653e750a6bdfd1bd7f800e
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233835"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="49278-103">On-premises bronnen openen vanaf een azure AD-apparaat in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="49278-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="49278-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="49278-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="49278-105">Elk Windows 10-apparaat dat is aangesloten op Azure Active Directory, heeft toegang tot alle cloudresources, zoals uw Microsoft 365-apps, en kan worden beveiligd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="49278-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="49278-106">U kunt ook toegang verlenen tot on-premises resources, zoals LOB-apps (Line Of Business), bestands shares en printers.</span><span class="sxs-lookup"><span data-stu-id="49278-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="49278-107">Gebruik Azure [AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory om toegang toe te staan.</span><span class="sxs-lookup"><span data-stu-id="49278-107">To allow access, use [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="49278-108">Zie Inleiding tot apparaatbeheer [in Azure Active Directory voor meer informatie.](https://docs.microsoft.com/azure/active-directory/device-management-introduction)</span><span class="sxs-lookup"><span data-stu-id="49278-108">To learn more, see [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="49278-109">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="49278-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="49278-110">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="49278-110">Run Azure AD Connect</span></span>

<span data-ttu-id="49278-111">Volg de volgende stappen om de apparaten die lid zijn van Azure AD van uw organisatie toegang te geven tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="49278-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="49278-112">Als u uw gebruikers, groepen en contactpersonen vanuit de lokale Active Directory wilt synchroniseren met Azure Active Directory, moet u de wizard Adreslijstsynchronisatie en Azure AD Connect uitvoeren, zoals is beschreven in Adreslijstsynchronisatie voor [Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)instellen.</span><span class="sxs-lookup"><span data-stu-id="49278-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization).</span></span>
    
2. <span data-ttu-id="49278-113">Nadat de adreslijstsynchronisatie is voltooid, zorgt u ervoor dat de Windows 10-apparaten van uw organisatie zijn samengevoegd met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="49278-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="49278-114">Deze stap wordt afzonderlijk uitgevoerd op elk Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="49278-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="49278-115">Zie [Windows-apparaten instellen voor gebruikers van Microsoft 365 Business Premium](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="49278-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="49278-116">Wanneer de Windows 10-apparaten zijn samengevoegd met Azure AD, moet elke gebruiker zijn of haar apparaten opnieuw opstarten en zich aanmelden met de Microsoft 365 Business Premium-referenties.</span><span class="sxs-lookup"><span data-stu-id="49278-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="49278-117">Alle apparaten hebben nu ook toegang tot on-premises bronnen.</span><span class="sxs-lookup"><span data-stu-id="49278-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="49278-118">Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor apparaten die lid zijn van Azure AD.</span><span class="sxs-lookup"><span data-stu-id="49278-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="49278-119">Deze functionaliteit is ingebouwd in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="49278-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="49278-120">Als u zich wilt aanmelden bij het AADJ-apparaat met een andere wachtwoordmethode dan bijvoorbeeld pincode/bio-meetwaarde via aanmelding bij WHFB-referenties en vervolgens toegang wilt krijgen tot lokale bronnen (shares,printers.). enzovoort) volgt u https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="49278-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="49278-121">Als uw organisatie nog niet gereed is om te implementeren in de apparaatconfiguratie die is lid van Azure AD, zoals hierboven is beschreven, kunt u overwegen om een hybride configuratie van een [Azure AD-apparaat](manage-windows-devices.md)in te stellen.</span><span class="sxs-lookup"><span data-stu-id="49278-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="49278-122">Overwegingen bij het deelnemen van Windows-apparaten aan Azure AD</span><span class="sxs-lookup"><span data-stu-id="49278-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="49278-123">Als het Windows-apparaat waar u azure-AD eerder lid van was, lid was van een domein of een werkgroep, moet u rekening houden met de volgende beperkingen:</span><span class="sxs-lookup"><span data-stu-id="49278-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="49278-124">Wanneer een apparaat wordt lid van Azure AD, wordt er een nieuwe gebruiker gemaakt zonder dat wordt verwezen naar een bestaand profiel.</span><span class="sxs-lookup"><span data-stu-id="49278-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="49278-125">Profielen moeten handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="49278-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="49278-126">Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en instellingen van het Startmenu.</span><span class="sxs-lookup"><span data-stu-id="49278-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="49278-127">U kunt het beste een hulpprogramma van derden zoeken om bestaande bestanden en instellingen toe te passen op het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="49278-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="49278-128">Als het apparaat groepsbeleidsobjecten gebruikt, hebben sommige GPOs mogelijk niet een vergelijkbaar [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span><span class="sxs-lookup"><span data-stu-id="49278-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="49278-129">Voer het [hulpprogramma MMAT uit om](https://www.microsoft.com/download/details.aspx?id=45520) vergelijkbare CSP's te zoeken voor bestaande GPOs's.</span><span class="sxs-lookup"><span data-stu-id="49278-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="49278-130">Gebruikers kunnen zich mogelijk niet verifiëren bij toepassingen die afhankelijk zijn van Active Directory-verificatie.</span><span class="sxs-lookup"><span data-stu-id="49278-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="49278-131">Evalueer de oudere app en overweeg indien mogelijk een update uit te brengen naar een app die gebruikmaakt van de moderne auth.</span><span class="sxs-lookup"><span data-stu-id="49278-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="49278-132">Active Directory Printer Discovery werkt niet.</span><span class="sxs-lookup"><span data-stu-id="49278-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="49278-133">U kunt directe printerpaden bieden voor alle gebruikers of universeel [afdrukken gebruiken.](https://aka.ms/UPDocs)</span><span class="sxs-lookup"><span data-stu-id="49278-133">You can provide direct printer paths for all users or use [Universal Print](https://aka.ms/UPDocs).</span></span>
