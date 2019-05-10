---
title: Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
description: Informatie over het inschakelen van Microsoft 365 te beschermen lokale AD verbonden apparaten met Windows 10.
ms.openlocfilehash: 661e5bf8205a661eb4382b4bdd8fcf3a54ecc12f
ms.sourcegitcommit: db1dfb2df2c2f7beced3b57bc772d106c189e88a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2019
ms.locfileid: "33660304"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="3209d-103">Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd</span><span class="sxs-lookup"><span data-stu-id="3209d-103">Enable domain-joined Windows 10 devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="3209d-104">Als uw organisatie gebruikmaakt van Windows Server Active Directory op lokalen, kunt u Microsoft 365 Business instellen ter bescherming van uw Windows 10-apparaten, terwijl zij toch toegang tot bronnen voor ruimten die lokale verificatie vereisen.</span><span class="sxs-lookup"><span data-stu-id="3209d-104">If your organization uses Windows Server Active Directory on-premises, you can set up Microsoft 365 Business to protect your Windows 10 devices, while still maintaining access to on-premises resources that require local authentication.</span></span> <span data-ttu-id="3209d-105">U kunt dit instellen door de eerste synchronisatie van Active Directory met Azure Active Directory, gevolgd door de Windows 10-apparaten met Azure Active Directory registreren en deze inschrijven voor mobiel Apparaatbeheer door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3209d-105">You can set this up by first synchronizing your Active Directory with Azure Active Directory, followed by registering the Windows 10 devices with Azure AD and enrolling them for mobile device management by Microsoft 365 Business.</span></span>
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a><span data-ttu-id="3209d-106">Apparaten die deel uitmaakt van een domein wordt beheerd door Microsoft 365 Business instellen</span><span class="sxs-lookup"><span data-stu-id="3209d-106">Set up domain-joined devices to be managed by Microsoft 365 Business</span></span>

<span data-ttu-id="3209d-107">Om in te stellen van uw organisatie deel uitmaakt van een domein apparaten om te profiteren van de mogelijkheden die Azure Active Directory ondersteunt naast Active Directory voor het bedrijf, kunt u de **hybride Azure AD verbonden apparaten**implementeren.</span><span class="sxs-lookup"><span data-stu-id="3209d-107">To set up your organization's domain-joined devices to benefit from the capabilities provided by Azure Active Directory in addition to on-premises Active Directory, you can implement **Hybrid Azure AD joined devices**.</span></span> <span data-ttu-id="3209d-108">Dit zijn apparaten die deel van zowel op ruimten Active Directory en Azure Active Directory uitmaken.</span><span class="sxs-lookup"><span data-stu-id="3209d-108">These are devices that are joined both to your on-premises Active Directory and your Azure Active Directory.</span></span> <span data-ttu-id="3209d-109">Hybride Azure AD verbonden apparaten kunnen worden beveiligd en beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3209d-109">Hybrid Azure AD joined devices can be protected and managed by Microsoft 365 Business.</span></span> 
  
<span data-ttu-id="3209d-110">De stappen hieronder om uw Windows 10-apparaten hybride Azure AD toegevoegd en beheerd door Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3209d-110">Complete the steps below to make your Windows 10 devices Hybrid Azure AD joined and managed by Microsoft 365 Business.</span></span>
  
1. <span data-ttu-id="3209d-111">Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory naar Azure Active Directory, de Directory synchronisatie wizard en Azure Active Directory verbinding zoals beschreven in de [directory-synchronisatie voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="3209d-111">To synchronize your users, groups and contacts from local Active Directory into Azure Active Directory, run the Directory synchronization wizard and Azure Active Directory Connect as described in [Set up directory synchronization for Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3209d-112">De stappen zijn precies hetzelfde voor Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3209d-112">The steps are exactly the same for Microsoft 365 Business.</span></span> 
  
2. <span data-ttu-id="3209d-113">Voordat u stap 3 waarmee Windows 10-apparaten hybride Azure AD lid worden voltooid, moet u om ervoor te zorgen dat u aan de volgende vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="3209d-113">Before you complete step 3 to enable Windows 10 devices to be Hybrid Azure AD joined, you need to make sure that you meet the following prerequisites:</span></span>

   - <span data-ttu-id="3209d-114">U gebruikt de meest recente versie van Azure AD verbinding.</span><span class="sxs-lookup"><span data-stu-id="3209d-114">You are running the latest version of Azure AD connect.</span></span>

   - <span data-ttu-id="3209d-115">Verbinding Azure AD is de computerobjecten van de gewenste hybride Azure AD verbonden apparaten gesynchroniseerd.</span><span class="sxs-lookup"><span data-stu-id="3209d-115">Azure AD connect has synchronized all the computer objects of the devices you want to be hybrid Azure AD joined.</span></span> <span data-ttu-id="3209d-116">Als u de computerobjecten behoren tot de specifieke organisatie-eenheden (OU), moeten u ervoor zorgen dat deze organisatie-eenheden zijn ingesteld voor synchronisatie in Azure AD ook verbinden.</span><span class="sxs-lookup"><span data-stu-id="3209d-116">If the computer objects belong to specific organizational units (OU), then make sure these OUs are set for synchronization in Azure AD connect as well.</span></span>
    
3. <span data-ttu-id="3209d-117">Registreren bestaande domein behoren Windows 10-apparaten worden verbonden met Azure AD hybride en ze inschrijven voor mobiel Apparaatbeheer door Intune (Business Microsoft 365):</span><span class="sxs-lookup"><span data-stu-id="3209d-117">Register existing domain-joined Windows 10 devices to be hybrid Azure AD Joined and enroll them for mobile device management by Intune (Microsoft 365 Business):</span></span>
    
4. <span data-ttu-id="3209d-118">Volg de instructies stap voor stap in [hybride Azure Active Directory verbonden apparaten configureren](https://go.microsoft.com/fwlink/p/?linkid=872870).</span><span class="sxs-lookup"><span data-stu-id="3209d-118">Follow the step by step instructions in [How to configure hybrid Azure Active Directory joined devices](https://go.microsoft.com/fwlink/p/?linkid=872870).</span></span> <span data-ttu-id="3209d-119">Hiermee schakelt u de synchronisatie van Active Directory op ruimten verbonden computers met Windows 10 en deze cloud klaar te maken.</span><span class="sxs-lookup"><span data-stu-id="3209d-119">This will enable the synchronization of your on-premises Active Directory joined Windows 10 computers and make them cloud ready.</span></span>
    
5. <span data-ttu-id="3209d-120">Om te kunnen inschrijven voor een apparaat met Windows 10 voor mobile device management, Zie [inschrijven voor een Windows 10-apparaat met Intune met behulp van een Groepsbeleid](https://go.microsoft.com/fwlink/p/?linkid=872871) voor meer informatie.</span><span class="sxs-lookup"><span data-stu-id="3209d-120">In order to enroll a Windows 10 device for mobile device management, see [Enroll a Windows 10 device with Intune by using a Group Policy](https://go.microsoft.com/fwlink/p/?linkid=872871) for instructions.</span></span> <span data-ttu-id="3209d-121">U kunt het groepsbeleid op een lokale computer niveau of voor bulkbewerkingen, kunt u deze instelling voor Groepsbeleid op uw server domain controller.</span><span class="sxs-lookup"><span data-stu-id="3209d-121">You can set the Group Policy at a local computer level or for bulk operations, you can create this group policy setting on your domain controller server.</span></span>