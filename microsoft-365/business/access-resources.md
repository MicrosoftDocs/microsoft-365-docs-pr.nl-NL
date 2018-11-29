---
title: Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: b0f4d010-9fd1-44d0-9d20-fabad2cdbab5
description: Informatie over het verkrijgen van toegang tot bronnen voor bedrijfsruimten zoals Line Of Business apps, bestandsshares en printers uit een Azure Active Directory Windows 10-apparaat gekoppeld.
ms.openlocfilehash: 0a5d4b0828888fcb99676223000c446479f84ddc
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/28/2018
ms.locfileid: "26982252"
---
# <a name="access-on-premises-resources-from-an-azure-ad-joined-device-in-microsoft-365-business"></a><span data-ttu-id="b3747-103">Toegang op-premises resources uit een Azure AD verbonden apparaat in Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="b3747-103">Access on-premises resources from an Azure AD-joined device in Microsoft 365 Business</span></span>

<span data-ttu-id="b3747-p101">Elk Windows 10-apparaat dat is Azure Active Directory toegevoegd toegang hebben tot alle cloud-gebaseerde bronnen zoals uw apps Office 365 en kan worden beveiligd door Microsoft 365 Business. Als u ook toegang tot bronnen voor bedrijfsruimten zoals apps, bestandsshares en printers lijn van Business (LOB), moet u Active Directory op ruimten synchroniseren met Azure Active Directory met [Azure AD verbinding](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). Zie [Inleiding tot device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3747-p101">Any Windows 10 device that is Azure Active Directory joined will have access to all cloud-based resources such as your Office 365 apps and can be protected by Microsoft 365 Business. To also allow access to on-premises resources like Line Of Business (LOB) apps, file shares, and printers, you must synchronize your on-premises Active Directory with Azure Active Directory by using [Azure AD Connect](https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect). See [Introduction to device management in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/device-management-introduction) to learn more.</span></span> 
  
## <a name="run-azure-ad-connect"></a><span data-ttu-id="b3747-107">Verbinding Azure AD uitvoeren</span><span class="sxs-lookup"><span data-stu-id="b3747-107">Run Azure AD Connect</span></span>

<span data-ttu-id="b3747-108">Voer de volgende stappen voor het inschakelen van uw organisatie Azure AD verbonden apparaten toegang krijgen tot bronnen op gebouwen.</span><span class="sxs-lookup"><span data-stu-id="b3747-108">Complete the following steps to enable your organization's Azure AD joined devices to access on-premises resources.</span></span>
  
1. <span data-ttu-id="b3747-109">Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory naar Azure Active Directory, de Directory synchronisatie-wizard uitvoeren en Azure AD verbinden als beschreven in de [directory-synchronisatie voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="b3747-109">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure AD Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
2. <span data-ttu-id="b3747-p102">Nadat de adreslijstsynchronisatie is voltooid, moet u ervoor zorgen van uw organisatie Windows 10-apparaten zijn Azure advertentie toegevoegd. Deze stap gebeurt afzonderlijk op elk apparaat met Windows 10. Zie [Windows-apparaten voor Microsoft 365 zakelijke gebruikers instellen](set-up-windows-devices.md) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="b3747-p102">After the directory synchronization has completed, make sure your organization's Windows 10 devices are Azure AD joined. This step is done individually on each Windows 10 device. See [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md) for details.</span></span> 
    
3. <span data-ttu-id="b3747-p103">Nadat de Windows 10-apparaten Azure AD toegevoegd zijn, moet elke gebruiker opnieuw hun apparaten en meld u aan met de referenties van Microsoft 365 Business. Alle apparaten hebben nu toegang tot ook bronnen voor gebouwen.</span><span class="sxs-lookup"><span data-stu-id="b3747-p103">Once the Windows 10 devices are Azure AD joined, each user should reboot their devices and login with their Microsoft 365 Business credentials. All devices will now have access to on-premises resources as well.</span></span>
    
<span data-ttu-id="b3747-p104">Er zijn geen extra stappen vereist voor toegang tot lokale bronnen voor AD Azure verbonden apparaten. Dit is de ingebouwde functionaliteit die beschikbaar is in Windows 10.</span><span class="sxs-lookup"><span data-stu-id="b3747-p104">No additional steps are required to get access to on-premise resources for Azure AD joined devices. This is built-in functionality available in Windows 10.</span></span> 
  
<span data-ttu-id="b3747-117">Als uw organisatie niet implementeren in Azure AD verbonden configuratie van het apparaat beschreven, kunt u [configuratie van hybride Azure AD verbonden apparaat](manage-windows-devices.md).</span><span class="sxs-lookup"><span data-stu-id="b3747-117">If your organization is not ready to deploy in the Azure AD Joined Device Configuration described above, consider setting up [Hybrid Azure AD Joined device configuration](manage-windows-devices.md).</span></span>
  
### <a name="considerations-when-joining-your-windows-devices-to-azure-ad"></a><span data-ttu-id="b3747-118">Overwegingen wanneer u uw Windows-apparaten met Azure AD</span><span class="sxs-lookup"><span data-stu-id="b3747-118">Considerations when joining your Windows devices to Azure AD</span></span>

<span data-ttu-id="b3747-119">Als u Azure AD lid worden van een Windows-apparaat dat eerder deel uitmaakt van een domein is of een werkgroep, moet u rekening houden met de volgende beperkingen:</span><span class="sxs-lookup"><span data-stu-id="b3747-119">If you are Azure AD joining a Windows device that has previously been domain-joined or in a workgroup, you need to consider the following limitations:</span></span>
  
- <span data-ttu-id="b3747-p105">Wanneer een apparaat Azure AD lid, wordt een nieuwe gebruiker zonder te verwijzen naar een bestaand profiel gemaakt. U kunt dit oplossen moeten profielen handmatig worden gemigreerd. Een gebruikersprofiel bevat informatie zoals Favorieten, lokale bestanden, instellingen, instellingen van het menu Start, enz. Een beste benadering is een hulpprogramma van derden voor het toewijzen van bestanden en instellingen naar het nieuwe profiel vinden</span><span class="sxs-lookup"><span data-stu-id="b3747-p105">When a device Azure AD joins, it creates a new user without referencing an existing profile. To fix this, profiles need to be manually migrated. A user profile contains information like favorites, local files, browser settings, Start menu settings, etc. A best approach is to find a third-party tool to map existing files and settings to the new profile</span></span>
    
- <span data-ttu-id="b3747-p106">Als het apparaat wordt met behulp van Group Policy objecten (GPO), sommige groepsbeleidsobjecten niet mogelijk een vergelijkbare [Configuratie Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Het [hulpprogramma MMAT](https://www.microsoft.com/download/details.aspx?id=45520) om te zoeken naar vergelijkbare CSP's voor bestaande groepsbeleidsobjecten uitvoeren.</span><span class="sxs-lookup"><span data-stu-id="b3747-p106">If the device is using Group Policy Objects (GPO), some GPOs may not have a comparable [Configuration Service Provider](https://docs.microsoft.com/windows/configuration/provisioning-packages/how-it-pros-can-use-configuration-service-providers) (CSP) in Intune. Run the [MMAT tool](https://www.microsoft.com/download/details.aspx?id=45520) to find comparable CSPs for existing GPOs.</span></span> 
    
- <span data-ttu-id="b3747-p107">Gebruikers worden niet geverifieerd aan toepassingen die afhankelijk van de verificatie van Active Directory zijn. Omgaan met met behulp van een oude toepassingen evalueren en bij te werken naar een toepassing die gebruikmaakt van moderne Auth indien mogelijk.</span><span class="sxs-lookup"><span data-stu-id="b3747-p107">Users will not be able to authenticate to applications that depend on Active Directory authentication. To deal with this evaluate using a legacy app and consider updating to an app that uses modern Auth if possible.</span></span>
    
- <span data-ttu-id="b3747-p108">Detectie van Active Directory printer werkt niet. U kunt dit oplossen direct printerpaden bieden voor alle gebruikers of maak gebruik van [Hybride Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span><span class="sxs-lookup"><span data-stu-id="b3747-p108">Active Directory printer discovery will not work. To fix this, provide direct printer paths for all users or leverage [Hybrid Cloud Print](https://docs.microsoft.com/windows-server/administration/hybrid-cloud-print/hybrid-cloud-print-deploy).</span></span>
    

