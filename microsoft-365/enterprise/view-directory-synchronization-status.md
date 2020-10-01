---
title: De status van de adreslijstsynchronisatie bekijken in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
ms.assetid: 18be3b98-34ae-47be-9337-ab6c3fb372ac
description: In dit artikel leest u hoe u de status van de adreslijstsynchronisatie in Office 365 kunt controleren.
ms.openlocfilehash: 7577ed358a262d5b0ef2932bc73cf61941bec31b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326947"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="09e71-103">De status van de adreslijstsynchronisatie bekijken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="09e71-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="09e71-104">Als u uw on-premises Active Directory Domain Services (AD DS) met Azure Active Directory (Azure AD) hebt geïntegreerd met de synchronisatie van uw on-premises omgeving met Microsoft 365, kunt u ook de status van uw synchronisatie controleren.</span><span class="sxs-lookup"><span data-stu-id="09e71-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="09e71-105">De status van de adreslijstsynchronisatie bekijken</span><span class="sxs-lookup"><span data-stu-id="09e71-105">View directory synchronization status</span></span>

- <span data-ttu-id="09e71-106">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) en kies **DirSync-status** op de startpagina.</span><span class="sxs-lookup"><span data-stu-id="09e71-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="09e71-107">U kunt **ook op** \> de pagina **actieve** gebruikers op de pagina actieve **gebruikers klikken**en **meer** \> **adreslijstsynchronisatie**kiezen.</span><span class="sxs-lookup"><span data-stu-id="09e71-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="09e71-108">In het deelvenster **adreslijstsynchronisatie** kiest **u Ga naar DirSync-beheer**.</span><span class="sxs-lookup"><span data-stu-id="09e71-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="09e71-109">Gegevens op de pagina Adreslijstsynchronisatie beheren</span><span class="sxs-lookup"><span data-stu-id="09e71-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="09e71-110">De volgende tabel bevat een overzicht van de functies waarop u informatie kunt vinden over de pagina.</span><span class="sxs-lookup"><span data-stu-id="09e71-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="09e71-111">Als er een probleem is met uw adreslijstsynchronisatie, worden de fouten ook op deze pagina weergegeven.</span><span class="sxs-lookup"><span data-stu-id="09e71-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="09e71-112">Zie [fouten met adreslijstsynchronisatie identificeren in Microsoft 365](identify-directory-synchronization-errors.md)voor meer informatie over de verschillende fouten die kunnen optreden.</span><span class="sxs-lookup"><span data-stu-id="09e71-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="09e71-113">Item</span><span class="sxs-lookup"><span data-stu-id="09e71-113">Item</span></span>|<span data-ttu-id="09e71-114">Doel</span><span class="sxs-lookup"><span data-stu-id="09e71-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="09e71-115">**Geverifieerde domeinen**</span><span class="sxs-lookup"><span data-stu-id="09e71-115">**Domains verified**</span></span> | <span data-ttu-id="09e71-116">Het aantal domeinen in uw Microsoft 365-Tenant waarvoor u hebt gecontroleerd of u de eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="09e71-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="09e71-117">**Domeinen niet gecontroleerd**</span><span class="sxs-lookup"><span data-stu-id="09e71-117">**Domains not verified**</span></span> | <span data-ttu-id="09e71-118">Domeinen die u hebt toegevoegd, maar die niet zijn geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="09e71-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="09e71-119">**Directory-synchronisatie ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="09e71-119">**Directory sync enabled**</span></span> |<span data-ttu-id="09e71-120">Waar of onwaar.</span><span class="sxs-lookup"><span data-stu-id="09e71-120">True or False.</span></span> <span data-ttu-id="09e71-121">Hiermee geeft u op of u adreslijstsynchronisatie hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="09e71-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="09e71-122">**Laatste adreslijstsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="09e71-122">**Latest directory sync**</span></span> | <span data-ttu-id="09e71-123">Laatste keer dat de adreslijstsynchronisatie is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="09e71-123">Last time directory sync ran.</span></span> <span data-ttu-id="09e71-124">Geeft een waarschuwing weer en een koppeling naar het hulpprogramma voor probleemoplossing als de laatste synchronisatie langer dan drie dagen geleden was.</span><span class="sxs-lookup"><span data-stu-id="09e71-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="09e71-125">**Wachtwoordsynchronisatie ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="09e71-125">**Password sync enabled**</span></span> | <span data-ttu-id="09e71-126">Waar of onwaar.</span><span class="sxs-lookup"><span data-stu-id="09e71-126">True or False.</span></span> <span data-ttu-id="09e71-127">Hiermee geeft u op of u een hash-synchronisatie tussen onze on-premises en uw Microsoft 365-Tenant hebt.</span><span class="sxs-lookup"><span data-stu-id="09e71-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="09e71-128">**Laatste Wachtwoordsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="09e71-128">**Last Password Sync**</span></span> | <span data-ttu-id="09e71-129">Laatste keer dat de hash-synchronisatie voor het wachtwoord is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="09e71-129">Last time password hash sync ran.</span></span> <span data-ttu-id="09e71-130">Geeft een waarschuwing weer en een koppeling naar het hulpprogramma voor probleemoplossing als de laatste synchronisatie langer dan drie dagen geleden was.</span><span class="sxs-lookup"><span data-stu-id="09e71-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="09e71-131">**Versie van adreslijstsynchronisatie client**</span><span class="sxs-lookup"><span data-stu-id="09e71-131">**Directory sync client version**</span></span> | <span data-ttu-id="09e71-132">Bevat een downloadkoppeling als er een nieuwe versie van Azure AD Connect is uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="09e71-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="09e71-133">**Serviceaccount adreslijstsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="09e71-133">**Directory sync service account**</span></span> | <span data-ttu-id="09e71-134">Toont de naam van uw Microsoft 365 Directory-synchronisatieserviceaccount.</span><span class="sxs-lookup"><span data-stu-id="09e71-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="09e71-135">Synchronisatiestatus bewaken</span><span class="sxs-lookup"><span data-stu-id="09e71-135">Monitor synchronization health</span></span>

<span data-ttu-id="09e71-136">In deze sectie installeert u een Azure AD Connect Health-agent op elk van uw on-premises AD DS-domeincontrollers om uw identiteitsinfrastructuur en de synchronisatieservices van Azure AD Connect te bewaken.</span><span class="sxs-lookup"><span data-stu-id="09e71-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="09e71-137">De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="09e71-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="09e71-138">De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:</span><span class="sxs-lookup"><span data-stu-id="09e71-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="09e71-139">Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure AD Connect Health gebruiken met synchronisatie](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), om Azure AD Connect Health te begrijpen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="09e71-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="09e71-140">Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te begrijpen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="09e71-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="09e71-141">Wanneer u klaar bent, hebt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="09e71-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="09e71-142">De Azure AD Connect Health-agent die is geïnstalleerd op uw on-premises servers van de identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="09e71-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="09e71-143">De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Microsoft 365- en EMS-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="09e71-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>

