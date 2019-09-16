---
title: Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informatie over het inschakelen van Microsoft 365 voor het beveiligen van lokale AD gekoppelde Windows 10-apparaten.
ms.openlocfilehash: 5cce4bc53f118560e31ad7e6048e4efcb49d662e
ms.sourcegitcommit: c0f769244d05ad019ea2307c38d5543d7b1e5afd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/16/2019
ms.locfileid: "36992224"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="eb5d6-103">Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd</span><span class="sxs-lookup"><span data-stu-id="eb5d6-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="eb5d6-104">Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="eb5d6-105">U dit instellen door eerst uw Active Directory synchroniseren met Azure Active Directory, gevolgd door het registreren van de Windows 10-apparaten met Azure AD en ze inschrijven voor Mobile Device Management door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
<span data-ttu-id="eb5d6-106">De volgende Videodetails de stappen voor het instellen van dit voor de meest voorkomende scenario.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-106">The following video details the steps for how to set this up for the most common scenario.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="eb5d6-107">Domein apparaten instellen die moeten worden beheerd door Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="eb5d6-107">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="eb5d6-108">Als u wilt instellen van uw organisatie domein apparaten om te profiteren van de mogelijkheden die worden geleverd door Azure Active Directory naast on-premises Active Directory, u **hybride Azure AD gekoppelde apparaten**implementeren.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-108">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="eb5d6-109">Dit zijn apparaten die zijn gekoppeld aan uw on-premises Active Directory en uw Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-109">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="eb5d6-110">Hybride Azure AD gekoppelde apparaten kunnen worden beveiligd en beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-110">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="eb5d6-111">Voltooi de onderstaande stappen om uw Windows 10-apparaten hybride Azure AD toegevoegd en beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-111">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="eb5d6-112">Voor het synchroniseren van uw gebruikers, groepen en contactpersonen van lokale Active Directory in azure Active Directory, voert u de wizard Directory-synchronisatie en Azure Active Directory Connect zoals beschreven in [Directory-synchronisatie voor Office 365 instellen](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span><span class="sxs-lookup"><span data-stu-id="eb5d6-112">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="eb5d6-113">De stappen zijn precies hetzelfde voor Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-113">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="eb5d6-114">Voordat u stap 3 om in te schakelen van Windows 10-apparaten hybride Azure AD toegevoegd, moet u om ervoor te zorgen dat u aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="eb5d6-114">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="eb5d6-115">U gebruikt de nieuwste versie van Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-115">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="eb5d6-116">Azure AD Connect is gesynchroniseerd met alle computer objecten van de apparaten die u wilt worden hybride Azure AD toegevoegd.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-116">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="eb5d6-117">Als de computer objecten deel uitmaken van specifieke organisatie-eenheden (OE), zorg ervoor dat deze organisatie-eenheid zijn ingesteld voor synchronisatie in azure AD Connect ook.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-117">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="eb5d6-118">Registreer bestaande domein Windows 10-apparaten als hybride Azure AD toegevoegd en Registreer deze voor beheer van mobiele apparaten door intune (Microsoft 365 Business):</span><span class="sxs-lookup"><span data-stu-id="eb5d6-118">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="eb5d6-119">Volg de stap voor stap instructies in het [configureren van hybride Azure Active Directory gekoppelde apparaten](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="eb5d6-119">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="eb5d6-120">Hiermee schakelt u de synchronisatie van uw on-premises Active Directory is aangesloten op Windows 10-computers en maken ze klaar voor de Cloud.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-120">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="eb5d6-121">Als u een Windows 10-apparaat wilt inschrijven voor beheer van mobiele apparaten, raadpleegt u een [Windows 10-apparaat inschrijven bij intune met behulp van een Groepsbeleid](https://go.microsoft.com/fwlink/p/?linkid=872871) voor instructies.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-121">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="eb5d6-122">U het Groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen, u deze instelling voor Groepsbeleid op de server van uw domeincontroller maken.</span><span class="sxs-lookup"><span data-stu-id="eb5d6-122">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>