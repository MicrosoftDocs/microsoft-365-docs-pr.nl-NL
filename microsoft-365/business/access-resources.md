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
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informatie over hoe u toegang krijgt tot on-premises resources, zoals zakelijke apps, bestandsshares en printers, vanuit een Azure Active Directory dat is gekoppeld aan een Windows 10-apparaat.
ms.openlocfilehash: ab9049e78617372463b8446dc8f8bc0089d8c117
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981656"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="260ca-103">Toegang tot on-premises bronnen van een Azure AD-apparaat in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="260ca-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="260ca-104">Elk Windows 10-apparaat dat is gekoppeld aan Azure Active Directory, heeft toegang tot alle cloudgebaseerde bronnen, zoals uw Office 365-apps en kan worden beveiligd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="260ca-104">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business.</span></span> <span data-ttu-id="260ca-105">Om ook toegang tot on-premises resources zoals LOB-apps (line of Business), bestandsshares en printers toe te staan, moet u uw on-premises Active Directory synchroniseren met Azure Active Directory met behulp van [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span><span class="sxs-lookup"><span data-stu-id="260ca-105">To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect).</span></span> <span data-ttu-id="260ca-106">De volgende Videodetails de stappen voor het instellen van dit voor de meest voorkomende scenario.</span><span class="sxs-lookup"><span data-stu-id="260ca-106">The following video details the steps for how to set this up for the most common scenario.</span></span>
 
> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]

<span data-ttu-id="260ca-107">Zie [Inleiding tot Apparaatbeheer in azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="260ca-107">See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span>
<span data-ttu-id="260ca-108">De stappen worden ook samengevat in de volgende secties.</span><span class="sxs-lookup"><span data-stu-id="260ca-108">The steps are also summarized in the following sections.</span></span>

## <a name="run-azure-ad-connect"></a><span data-ttu-id="260ca-109">Azure AD Connect uitvoeren</span><span class="sxs-lookup"><span data-stu-id="260ca-109">Run Azure AD Connect</span></span>

<span data-ttu-id="260ca-110">Voltooi de volgende stappen om in te schakelen van uw organisatie Azure AD gekoppelde apparaten voor toegang tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="260ca-110">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="260ca-111">Voor het synchroniseren van uw gebruikers, groepen en contactpersonen van lokale Active Directory in azure Active Directory, voert u de wizard Directory-synchronisatie en Azure AD Connect zoals beschreven in [Directory-synchronisatie voor Office 365 instellen](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="260ca-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="260ca-112">Nadat de adreslijstsynchronisatie is voltooid, zorg ervoor dat de Windows 10-apparaten van uw organisatie zijn gekoppeld aan Azure AD.</span><span class="sxs-lookup"><span data-stu-id="260ca-112">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined.</span></span> <span data-ttu-id="260ca-113">Deze stap wordt afzonderlijk uitgevoerd op elk apparaat met Windows 10.</span><span class="sxs-lookup"><span data-stu-id="260ca-113">This step is done individually on each Windows 10 device.</span></span> <span data-ttu-id="260ca-114">Zie [Windows-apparaten instellen voor Microsoft 365 zakelijke gebruikers](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="260ca-114">See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="260ca-115">Zodra de Windows 10-apparaten zijn gekoppeld aan Azure AD, moet elke gebruiker hun apparaten opnieuw opstarten en aanmelden met hun Microsoft 365 zakelijke referenties.</span><span class="sxs-lookup"><span data-stu-id="260ca-115">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials.</span></span> <span data-ttu-id="260ca-116">Alle apparaten hebben nu ook toegang tot on-premises resources.</span><span class="sxs-lookup"><span data-stu-id="260ca-116">All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="260ca-117">Er zijn geen extra stappen nodig om toegang te krijgen tot on-premises bronnen voor Azure AD gekoppelde apparaten.</span><span class="sxs-lookup"><span data-stu-id="260ca-117">No additional steps are required to get access to on-premises resources for Azure AD joined devices.</span></span> <span data-ttu-id="260ca-118">Dit is ingebouwde functionaliteit beschikbaar in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="260ca-118">This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="260ca-119">Als uw organisatie is niet gereed voor implementatie in de Azure AD gekoppelde apparaatconfiguratie hierboven beschreven, overweeg het instellen van [hybride Azure AD gekoppelde apparaatconfiguratie](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="260ca-119">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="260ca-120">Overwegingen bij het verbinden van uw Windows-apparaten met Azure AD</span><span class="sxs-lookup"><span data-stu-id="260ca-120">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="260ca-121">Als u Azure AD lid worden van een Windows-apparaat dat eerder lid van een domein of in een werkgroep is, moet u rekening houden met de volgende beperkingen:</span><span class="sxs-lookup"><span data-stu-id="260ca-121">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="260ca-122">Wanneer een apparaat Azure AD wordt toegevoegd, wordt een nieuwe gebruiker gemaakt zonder te verwijzen naar een bestaand profiel.</span><span class="sxs-lookup"><span data-stu-id="260ca-122">When a device Azure AD joins, it creates a new user without referencing an existing profile.</span></span> <span data-ttu-id="260ca-123">Om dit op te lossen, moeten profielen handmatig worden gemigreerd.</span><span class="sxs-lookup"><span data-stu-id="260ca-123">To fix this, profiles need to be manually migrated.</span></span> <span data-ttu-id="260ca-124">Een gebruikersprofiel bevat informatie zoals Favorieten, lokale bestanden, browserinstellingen, instellingen in het menu Start, enz. De beste manier is om een hulpprogramma van derden te vinden voor het toewijzen van bestaande bestanden en instellingen aan het nieuwe profiel</span><span class="sxs-lookup"><span data-stu-id="260ca-124">A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>

- <span data-ttu-id="260ca-125">Als het apparaat gebruikmaakt van groepsbeleidsobjecten (GPO), hebben sommige groepsbeleidobjecten mogelijk geen vergelijkbare [configuratie service provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in intune.</span><span class="sxs-lookup"><span data-stu-id="260ca-125">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune.</span></span> <span data-ttu-id="260ca-126">Voer het [hulpprogramma Mmat](https://www.microsoft.com/download/details.aspx?id=45520) uit om vergelijkbare csp's voor bestaande groepsbeleidobjecten te vinden.</span><span class="sxs-lookup"><span data-stu-id="260ca-126">Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span>

- <span data-ttu-id="260ca-127">Gebruikers kunnen niet worden geverifieerd bij toepassingen die afhankelijk van Active Directory-verificatie zijn.</span><span class="sxs-lookup"><span data-stu-id="260ca-127">Users will not be able to authenticate to applications that depend on Active Directory authentication.</span></span> <span data-ttu-id="260ca-128">Om te gaan met deze evaluatie met behulp van een verouderde app en overweeg het bijwerken naar een app die gebruikmaakt van moderne auth indien mogelijk.</span><span class="sxs-lookup"><span data-stu-id="260ca-128">To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>

- <span data-ttu-id="260ca-129">Detectie van Active Directory-printers werkt niet.</span><span class="sxs-lookup"><span data-stu-id="260ca-129">Active Directory printer discovery will not work.</span></span> <span data-ttu-id="260ca-130">U dit oplossen door directe printer paden voor alle gebruikers te bieden of gebruik te maken van [Hybrid Cloud print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="260ca-130">To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
