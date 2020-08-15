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
ms.openlocfilehash: c77898b58b58c6ae91492debd7ad66f395d80d52
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689290"
---
# <a name="view-directory-synchronization-status-in-microsoft-365"></a><span data-ttu-id="603f2-103">De status van de adreslijstsynchronisatie bekijken in Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="603f2-103">View directory synchronization status in Microsoft 365</span></span>

<span data-ttu-id="603f2-104">Als u uw on-premises Active Directory met Azure AD hebt geïntegreerd met de synchronisatie van uw on-premises omgeving met Microsoft 365, kunt u ook de status van uw synchronisatie controleren.</span><span class="sxs-lookup"><span data-stu-id="603f2-104">If you have integrated your on-premises Active Directory with Azure AD by synchronizing your on-premises environment with Microsoft 365, you can also check the status of your synchronization.</span></span>
  
## <a name="view-directory-synchronization-status"></a><span data-ttu-id="603f2-105">De status van de adreslijstsynchronisatie bekijken</span><span class="sxs-lookup"><span data-stu-id="603f2-105">View directory synchronization status</span></span>

- <span data-ttu-id="603f2-106">Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) en kies **DirSync-status** op de startpagina.</span><span class="sxs-lookup"><span data-stu-id="603f2-106">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) and choose **DirSync Status** on the home page.</span></span>
- <span data-ttu-id="603f2-107">U kunt **ook op** \> de pagina **actieve** gebruikers op de pagina actieve **gebruikers klikken**en **meer** \> **adreslijstsynchronisatie**kiezen.</span><span class="sxs-lookup"><span data-stu-id="603f2-107">Alternately, you can go to **Users** \> **Active users**, and on the **Active users** page, choose **More** \> **Directory synchronization**.</span></span> <span data-ttu-id="603f2-108">In het deelvenster **adreslijstsynchronisatie** kiest **u Ga naar DirSync-beheer**.</span><span class="sxs-lookup"><span data-stu-id="603f2-108">On the **Directory Synchronization** pane, choose **Go to DirSync management**.</span></span>

## <a name="information-on-the-manage-directory-synchronization-page"></a><span data-ttu-id="603f2-109">Gegevens op de pagina Adreslijstsynchronisatie beheren</span><span class="sxs-lookup"><span data-stu-id="603f2-109">Information on the Manage directory synchronization page</span></span>

<span data-ttu-id="603f2-110">De volgende tabel bevat een overzicht van de functies waarop u informatie kunt vinden over de pagina.</span><span class="sxs-lookup"><span data-stu-id="603f2-110">The following table lists the features you can get information about on the page.</span></span>
  
<span data-ttu-id="603f2-111">Als er een probleem is met uw adreslijstsynchronisatie, worden de fouten ook op deze pagina weergegeven.</span><span class="sxs-lookup"><span data-stu-id="603f2-111">If there is a problem with your directory synchronization, the errors are listed on this page as well.</span></span> <span data-ttu-id="603f2-112">Zie [fouten met adreslijstsynchronisatie identificeren in Microsoft 365](identify-directory-synchronization-errors.md)voor meer informatie over de verschillende fouten die kunnen optreden.</span><span class="sxs-lookup"><span data-stu-id="603f2-112">For more information about different errors you might encounter, see [Identify directory synchronization errors in Microsoft 365](identify-directory-synchronization-errors.md).</span></span>
  
|<span data-ttu-id="603f2-113">**Item**</span><span class="sxs-lookup"><span data-stu-id="603f2-113">**Item**</span></span>|<span data-ttu-id="603f2-114">**Doel**</span><span class="sxs-lookup"><span data-stu-id="603f2-114">**What it's for**</span></span>|
|:-----|:-----|
|<span data-ttu-id="603f2-115">**Geverifieerde domeinen**</span><span class="sxs-lookup"><span data-stu-id="603f2-115">**Domains verified**</span></span> | <span data-ttu-id="603f2-116">Het aantal domeinen in uw Microsoft 365-Tenant waarvoor u hebt gecontroleerd of u de eigenaar bent.</span><span class="sxs-lookup"><span data-stu-id="603f2-116">Number of domains in your Microsoft 365 tenant that you have verified you own.</span></span> |
|<span data-ttu-id="603f2-117">**Domeinen niet gecontroleerd**</span><span class="sxs-lookup"><span data-stu-id="603f2-117">**Domains not verified**</span></span> | <span data-ttu-id="603f2-118">Domeinen die u hebt toegevoegd, maar die niet zijn geverifieerd.</span><span class="sxs-lookup"><span data-stu-id="603f2-118">Domains you have added, but not verified.</span></span> |
|<span data-ttu-id="603f2-119">**Directory-synchronisatie ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="603f2-119">**Directory sync enabled**</span></span> |<span data-ttu-id="603f2-120">Waar of onwaar.</span><span class="sxs-lookup"><span data-stu-id="603f2-120">True or False.</span></span> <span data-ttu-id="603f2-121">Hiermee geeft u op of u adreslijstsynchronisatie hebt ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="603f2-121">Specifies whether you have enabled directory sync.</span></span> |
|<span data-ttu-id="603f2-122">**Laatste adreslijstsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="603f2-122">**Latest directory sync**</span></span> | <span data-ttu-id="603f2-123">Laatste keer dat de adreslijstsynchronisatie is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="603f2-123">Last time directory sync ran.</span></span> <span data-ttu-id="603f2-124">Geeft een waarschuwing weer en een koppeling naar het hulpprogramma voor probleemoplossing als de laatste synchronisatie langer dan drie dagen geleden was.</span><span class="sxs-lookup"><span data-stu-id="603f2-124">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="603f2-125">**Wachtwoordsynchronisatie ingeschakeld**</span><span class="sxs-lookup"><span data-stu-id="603f2-125">**Password sync enabled**</span></span> | <span data-ttu-id="603f2-126">Waar of onwaar.</span><span class="sxs-lookup"><span data-stu-id="603f2-126">True or False.</span></span> <span data-ttu-id="603f2-127">Hiermee geeft u op of u een hash-synchronisatie tussen onze on-premises en uw Microsoft 365-Tenant hebt.</span><span class="sxs-lookup"><span data-stu-id="603f2-127">Specifies whether you have password hash sync between our on-premises and your Microsoft 365 tenant.</span></span> |
|<span data-ttu-id="603f2-128">**Laatste Wachtwoordsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="603f2-128">**Last Password Sync**</span></span> | <span data-ttu-id="603f2-129">Laatste keer dat de hash-synchronisatie voor het wachtwoord is uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="603f2-129">Last time password hash sync ran.</span></span> <span data-ttu-id="603f2-130">Geeft een waarschuwing weer en een koppeling naar het hulpprogramma voor probleemoplossing als de laatste synchronisatie langer dan drie dagen geleden was.</span><span class="sxs-lookup"><span data-stu-id="603f2-130">Will display a warning and a link to a troubleshooting tool if the last sync was more than three days ago.</span></span> |
|<span data-ttu-id="603f2-131">**Versie van adreslijstsynchronisatie client**</span><span class="sxs-lookup"><span data-stu-id="603f2-131">**Directory sync client version**</span></span> | <span data-ttu-id="603f2-132">Bevat een downloadkoppeling als er een nieuwe versie van Azure AD Connect is uitgebracht.</span><span class="sxs-lookup"><span data-stu-id="603f2-132">Contains a download link if a new version of Azure AD Connect has been released.</span></span> |
|<span data-ttu-id="603f2-133">**Serviceaccount adreslijstsynchronisatie**</span><span class="sxs-lookup"><span data-stu-id="603f2-133">**Directory sync service account**</span></span> | <span data-ttu-id="603f2-134">Toont de naam van uw Microsoft 365 Directory-synchronisatieserviceaccount.</span><span class="sxs-lookup"><span data-stu-id="603f2-134">Displays the name of your Microsoft 365 directory sync service account.</span></span> |