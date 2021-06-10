---
title: Adreslijstsynchronisatiestatus weergeven in Microsoft 365
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
description: In dit artikel leert u hoe u de status van uw adreslijstsynchronisatie kunt controleren in Office 365.
ms.openlocfilehash: cbaae8bbd31f6124c2b0f4984b9a625ffbde538f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924658"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="ee886-103">Adreslijstsynchronisatiestatus weergeven in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ee886-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="ee886-104">Als u uw on-premises Active Directory Domain Services (AD DS) hebt geïntegreerd met Azure Active Directory (Azure AD) door uw on-premises omgeving te synchroniseren met Microsoft 365, kunt u ook de status van uw synchronisatie controleren.</span><span class="sxs-lookup"><span data-stu-id="ee886-104">If you have integrated your on-premises Active Directory Domain Services (AD DS) with Azure Active Directory (Azure AD) by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="ee886-105">De status van de adreslijstsynchronisatie bekijken</span><span class="sxs-lookup"><span data-stu-id="ee886-105">View directory synchronization status</span></span>

- <span data-ttu-id="ee886-106">Meld u aan bij [het Microsoft 365 beheercentrum](https://admin.microsoft.com) en kies **DirSync-status** op de startpagina.</span><span class="sxs-lookup"><span data-stu-id="ee886-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="ee886-107">U kunt ook naar  Gebruikers Actieve gebruikers gaan en op de pagina Actieve gebruikers de optie \>  **Meer**  \> **adreslijstsynchronisatie kiezen.**</span><span class="sxs-lookup"><span data-stu-id="ee886-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="ee886-108">Kies in **het deelvenster Adreslijstsynchronisatie** **de optie Ga naar DirSync-beheer.**</span><span class="sxs-lookup"><span data-stu-id="ee886-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="ee886-109">Informatie op de pagina Adreslijstsynchronisatie beheren</span><span class="sxs-lookup"><span data-stu-id="ee886-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="ee886-110">De volgende tabel bevat de functies waar u informatie over kunt krijgen op de pagina.</span><span class="sxs-lookup"><span data-stu-id="ee886-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="ee886-111">Als er een probleem is met de adreslijstsynchronisatie, worden de fouten ook op deze pagina weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee886-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="ee886-112">Zie Adreslijstsynchronisatiefouten identificeren [in](identify-directory-synchronization-errors.md)Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ee886-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="ee886-113">Item</span><span class="sxs-lookup"><span data-stu-id="ee886-113">Item</span></span>|<span data-ttu-id="ee886-114">Doel</span><span class="sxs-lookup"><span data-stu-id="ee886-114">What it's for</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee886-115">**Geverifieerde domeinen**</span><span class="sxs-lookup"><span data-stu-id="ee886-115">**Domains verified**</span></span> | <span data-ttu-id="ee886-116">Het aantal domeinen in uw Microsoft 365 tenant dat u hebt geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="ee886-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="ee886-117">**Domeinen die niet zijn geverifieerd**</span><span class="sxs-lookup"><span data-stu-id="ee886-117">**Domains not verified**</span></span> | <span data-ttu-id="ee886-118">Domeinen die u hebt toegevoegd, maar die niet zijn geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="ee886-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="ee886-119">**Adreslijstsynchronisatie ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="ee886-119">**Directory sync enabled**</span></span> |<span data-ttu-id="ee886-120">Waar of Onwaar.</span><span class="sxs-lookup"><span data-stu-id="ee886-120">True or False.</span></span> <span data-ttu-id="ee886-121">Hiermee geeft u aan of u adreslijstsynchronisatie hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="ee886-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="ee886-122">**Meest recente adreslijstsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="ee886-122">**Latest directory sync**</span></span> | <span data-ttu-id="ee886-123">De laatste keer dat adreslijstsynchronisatie is afgelopen.</span><span class="sxs-lookup"><span data-stu-id="ee886-123">Last time directory sync ran.</span></span> <span data-ttu-id="ee886-124">Er wordt een waarschuwing en een koppeling naar een hulpprogramma voor probleemoplossing weergegeven als de laatste synchronisatie meer dan drie dagen geleden was.</span><span class="sxs-lookup"><span data-stu-id="ee886-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="ee886-125">**Wachtwoordsynchronisatie ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="ee886-125">**Password sync enabled**</span></span> | <span data-ttu-id="ee886-126">Waar of Onwaar.</span><span class="sxs-lookup"><span data-stu-id="ee886-126">True or False.</span></span> <span data-ttu-id="ee886-127">Hiermee geeft u aan of u een wachtwoordhashsynchronisatie hebt tussen onze on-premises en uw Microsoft 365 tenant.</span><span class="sxs-lookup"><span data-stu-id="ee886-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="ee886-128">**Laatste wachtwoordsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="ee886-128">**Last Password Sync**</span></span> | <span data-ttu-id="ee886-129">De laatste keer dat wachtwoordhashsynchronisatie werd gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ee886-129">Last time password hash sync ran.</span></span> <span data-ttu-id="ee886-130">Er wordt een waarschuwing en een koppeling naar een hulpprogramma voor probleemoplossing weergegeven als de laatste synchronisatie meer dan drie dagen geleden was.</span><span class="sxs-lookup"><span data-stu-id="ee886-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="ee886-131">**Clientversie adreslijstsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="ee886-131">**Directory sync client version**</span></span> | <span data-ttu-id="ee886-132">Bevat een downloadkoppeling als er een nieuwe versie van Azure AD Verbinding maken is uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="ee886-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="ee886-133">**Adreslijstsynchronisatieserviceaccount**</span><span class="sxs-lookup"><span data-stu-id="ee886-133">**Directory sync service account**</span></span> | <span data-ttu-id="ee886-134">Hiermee wordt de naam van uw Microsoft 365 adreslijstsynchronisatieserviceaccount weergegeven.</span><span class="sxs-lookup"><span data-stu-id="ee886-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |
|||

## <a name="monitor-synchronization-health"></a><span data-ttu-id="ee886-135">Synchronisatiestatus bewaken</span><span class="sxs-lookup"><span data-stu-id="ee886-135">Monitor synchronization health</span></span>

<span data-ttu-id="ee886-136">In deze sectie installeert u een Azure AD Connect Health-agent op elk van uw on-premises AD DS-domeincontrollers om uw identiteitsinfrastructuur en de synchronisatieservices van Azure AD Connect te bewaken.</span><span class="sxs-lookup"><span data-stu-id="ee886-136">In this section, you'll install an Azure AD Connect Health agent on each of your on-premises AD DS domain controllers to monitor your identity infrastructure and the synchronization services provided by Azure AD Connect.</span></span> <span data-ttu-id="ee886-137">De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.</span><span class="sxs-lookup"><span data-stu-id="ee886-137">The monitoring information is made available in an Azure AD Connect Health portal, where you can view alerts, performance monitoring, usage analytics, and other information.</span></span>

<span data-ttu-id="ee886-138">De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:</span><span class="sxs-lookup"><span data-stu-id="ee886-138">The key design decision of how to use Azure AD Connect Health is based on how you are using Azure AD Connect:</span></span>

- <span data-ttu-id="ee886-139">Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure AD Connect Health gebruiken met synchronisatie](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync), om Azure AD Connect Health te begrijpen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="ee886-139">If you’re using the **managed authentication** option, start with [Using Azure AD Connect Health with sync](/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) to understand and configure Azure AD Connect Health.</span></span>
- <span data-ttu-id="ee886-140">Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te begrijpen en te configureren.</span><span class="sxs-lookup"><span data-stu-id="ee886-140">If you're synchronizing just the names of the accounts and groups using **federated authentication** with Active Directory Federation Services (AD FS), start with [Using Azure AD Connect Health with AD FS](/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) to understand and configure Azure AD Connect Health.</span></span>

<span data-ttu-id="ee886-141">Wanneer u klaar bent, hebt u het volgende:</span><span class="sxs-lookup"><span data-stu-id="ee886-141">When complete, you’ll have:</span></span>

- <span data-ttu-id="ee886-142">De Azure AD Connect Health-agent die is geïnstalleerd op uw on-premises servers van de identiteitsprovider.</span><span class="sxs-lookup"><span data-stu-id="ee886-142">The Azure AD Connect Health agent installed on your on-premises identity provider servers.</span></span>
- <span data-ttu-id="ee886-143">De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Microsoft 365- en EMS-abonnementen.</span><span class="sxs-lookup"><span data-stu-id="ee886-143">The Azure AD Connect Health portal displaying the current state of your on-premises infrastructure and synchronization activities with the Azure AD tenant for your Microsoft 365 subscription.</span></span>