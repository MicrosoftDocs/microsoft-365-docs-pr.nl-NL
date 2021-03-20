---
title: On-premises resources openen vanaf een azure AD-apparaat in Microsoft 365 Business
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
description: Lees hoe u toegang krijgt tot on-premises resources, zoals zakelijke apps, bestandsaandelen en printers vanaf een Azure Active Directory-apparaat dat is aangesloten bij Windows 10.
ms.openlocfilehash: b78509d72cbd9b3c121039c4965625bf5c21c7e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913517"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business-premium"></a><span data-ttu-id="88fb4-103">On-premises resources openen vanaf een azure AD-apparaat in Microsoft 365 Business Premium</span><span class="sxs-lookup"><span data-stu-id="88fb4-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business Premium</span></span>

<span data-ttu-id="88fb4-104">Dit artikel is van toepassing op Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="88fb4-104">This article applies to Microsoft 365 Business Premium.</span></span>

<span data-ttu-id="88fb4-105">Elk Windows 10-apparaat dat is verbonden met Azure Active Directory, heeft toegang tot alle cloudbronnen, zoals uw Microsoft 365-apps, en kan worden beschermd door Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="88fb4-105">Any Windows 10 device that is Azure Active Directory joined has access to all cloud-based resources, such as your Microsoft 365 apps, and can be protected by Microsoft 365 Business Premium.</span></span> <span data-ttu-id="88fb4-106">U kunt ook toegang verlenen tot on-premises resources, zoals LOB-apps (Line of Business), bestandsaandelen en printers.</span><span class="sxs-lookup"><span data-stu-id="88fb4-106">You can also allow access to on-premises resources like line of business (LOB) apps, file shares, and printers.</span></span> <span data-ttu-id="88fb4-107">Als u toegang wilt toestaan, gebruikt [u Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) om uw on-premises Active Directory te synchroniseren met Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="88fb4-107">To allow access, use [Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect) to synchronize your on-premises Active Directory with Azure Active Directory.</span></span> 

<span data-ttu-id="88fb4-108">Zie Inleiding tot [apparaatbeheer in Azure Active Directory](/azure/active-directory/device-management-introduction)voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="88fb4-108">To learn more, see [Introduction to device management in Azure Active Directory](/azure/active-directory/device-management-introduction).</span></span>
<span data-ttu-id="88fb4-109">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="88fb4-109">The steps are also summarized in the following sections.</span></span>
 
## <a name="run-azure-ad-connect"></a><span data-ttu-id="88fb4-110">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="88fb4-110">Run Azure AD Connect</span></span>

<span data-ttu-id="88fb4-111">Volg de volgende stappen om de aan Azure AD-apparaten van uw organisatie verbonden apparaten toegang te geven tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="88fb4-111">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="88fb4-112">Als u uw gebruikers, groepen en contactpersonen van lokale Active Directory wilt synchroniseren met Azure Active Directory, kunt u de wizard Adreslijstsynchronisatie en Azure AD Connect uitvoeren, zoals beschreven in Adreslijstsynchronisatie instellen voor [Office 365.](../enterprise/set-up-directory-synchronization.md)</span><span class="sxs-lookup"><span data-stu-id="88fb4-112">To synchronize your users, groups, and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](../enterprise/set-up-directory-synchronization.md).</span></span>
    
2. <span data-ttu-id="88fb4-113">Nadat de adreslijstsynchronisatie is voltooid, moet u ervoor zorgen dat de Windows 10-apparaten van uw organisatie zijn verbonden met Azure AD.</span><span class="sxs-lookup"><span data-stu-id="88fb4-113">After the directory synchronization is complete, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="88fb4-114">Deze stap wordt afzonderlijk uitgevoerd op elk Windows 10-apparaat.</span><span class="sxs-lookup"><span data-stu-id="88fb4-114">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="88fb4-115">Zie [Windows-apparaten instellen voor Gebruikers van Microsoft 365 Business Premium](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="88fb4-115">See [Set up Windows devices for Microsoft 365 Business Premium users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="88fb4-116">Wanneer de Windows 10-apparaten zijn samengevoegd met Azure AD, moet elke gebruiker zijn of haar apparaten opnieuw opstarten en zich aanmelden met de referenties van Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="88fb4-116">Once the Windows 10 devices are Azure AD joined, each user must reboot their devices and sign in with their Microsoft 365 Business Premium credentials.</span></span> <span data-ttu-id="88fb4-117">Alle apparaten hebben nu ook toegang tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="88fb4-117">All devices now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="88fb4-118">Er zijn geen extra stappen vereist om toegang te krijgen tot on-premises resources voor aan Azure AD verbonden apparaten.</span><span class="sxs-lookup"><span data-stu-id="88fb4-118">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="88fb4-119">Deze functionaliteit is ingebouwd in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="88fb4-119">This functionality is built into Windows 10.</span></span> 

<span data-ttu-id="88fb4-120">Als u plannen hebt om u aan te melden bij het AADJ-apparaat anders dan wachtwoordmethode Like PIN/Bio-metrische via WHFB credential login en vervolgens toegang te krijgen tot on-premises resources (shares,printers.). etc), volgt u https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span><span class="sxs-lookup"><span data-stu-id="88fb4-120">If you have plans to login to the AADJ device other than password method Like PIN/Bio-metric via WHFB credential login and then access on-premise resources (shares,printers..etc), please follow https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-aadj-sso-base</span></span>
  
<span data-ttu-id="88fb4-121">Als uw organisatie nog niet klaar is om te implementeren in de configuratie van azure AD-apparaten die hierboven zijn samengevoegd, kunt u de configuratie van hybride [Azure AD-apparaten instellen.](manage-windows-devices.md)</span><span class="sxs-lookup"><span data-stu-id="88fb4-121">If your organization isn't ready to deploy in the Azure AD joined device configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-you-join-windows-devices-to-azure-ad"></a><span data-ttu-id="88fb4-122">Aandachtspunten bij het deelnemen van Windows-apparaten aan Azure AD</span><span class="sxs-lookup"><span data-stu-id="88fb4-122">Considerations when you join Windows devices to Azure AD</span></span>

<span data-ttu-id="88fb4-123">Als het Windows-apparaat waar u Azure-AD deel van hebt gemaakt eerder is verbonden aan een domein of in een werkgroep, moet u rekening houden met de volgende beperkingen:</span><span class="sxs-lookup"><span data-stu-id="88fb4-123">If the Windows device that you Azure-AD joined was previously domain-joined or in a workgroup, consider the following limitations:</span></span>
  
- <span data-ttu-id="88fb4-124">Wanneer een apparaat azure AD wordt joins, wordt er een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel.</span><span class="sxs-lookup"><span data-stu-id="88fb4-124">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="88fb4-125">Profielen moeten handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="88fb4-125">Profiles must be manually migrated.</span></span> <span data-ttu-id="88fb4-126">Een gebruikersprofiel bevat informatie zoals favorieten, lokale bestanden, browserinstellingen en Menu-instellingen starten.</span><span class="sxs-lookup"><span data-stu-id="88fb4-126">A user profile contains information like favorites, local files, browser settings, and Start menu settings.</span></span> <span data-ttu-id="88fb4-127">U kunt het beste een hulpprogramma van derden vinden om bestaande bestanden en instellingen toe te passen op het nieuwe profiel.</span><span class="sxs-lookup"><span data-stu-id="88fb4-127">A best approach is to find a third-party tool to map existing files and settings to the new profile.</span></span>

- <span data-ttu-id="88fb4-128">Als het apparaat groepsbeleidsobjecten (GPO) gebruikt, hebben sommige GPOs mogelijk geen vergelijkbare [Configuratieserviceprovider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span><span class="sxs-lookup"><span data-stu-id="88fb4-128">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="88fb4-129">Voer het [hulpprogramma MMAT uit om](https://www.microsoft.com/download/details.aspx?id=45520) vergelijkbare CSP's voor bestaande GPOs te zoeken.</span><span class="sxs-lookup"><span data-stu-id="88fb4-129">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="88fb4-130">Gebruikers kunnen zich mogelijk niet verifiëren voor toepassingen die afhankelijk zijn van Active Directory-verificatie.</span><span class="sxs-lookup"><span data-stu-id="88fb4-130">Users might not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="88fb4-131">Evalueer de oudere app en overweeg indien mogelijk bij te werken naar een app die gebruikmaakt van het moderne Auth.</span><span class="sxs-lookup"><span data-stu-id="88fb4-131">Evaluate the legacy app and consider updating to an app that uses modern Auth, if possible.</span></span>

- <span data-ttu-id="88fb4-132">Active Directory-printerdetectie werkt niet.</span><span class="sxs-lookup"><span data-stu-id="88fb4-132">Active Directory printer discovery won't work.</span></span> <span data-ttu-id="88fb4-133">U kunt directe printerpaden voor alle gebruikers bieden of Universeel [afdrukken gebruiken.](/universal-print/)</span><span class="sxs-lookup"><span data-stu-id="88fb4-133">You can provide direct printer paths for all users or use [Universal Print](/universal-print/).</span></span>