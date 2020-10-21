---
title: Licenties voor apparaten beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Meer informatie over het toewijzen van licenties aan groepen voor gebruik met apparaten.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638181"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="ad637-103">Licenties voor apparaten beheren</span><span class="sxs-lookup"><span data-stu-id="ad637-103">Manage licenses for devices</span></span>

<span data-ttu-id="ad637-104">Als u Microsoft 365-apps hebt voor Enterprise (hardware) of Microsoft 365-apps voor onderwijs (apparaat), kunt u licenties toewijzen aan apparaten via Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="ad637-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="ad637-105">Wanneer een apparaat een licentie heeft, kan iedereen die dit apparaat gebruikt, Microsoft 365-apps gebruiken voor Enterprise (eerder Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="ad637-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="ad637-106">Stel, u hebt 20 laptops en tablets die door mensen in uw organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="ad637-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="ad637-107">Wanneer u aan elk apparaat een licentie toewijst, gebruikt elke persoon die zich aanmeldt op een van de apparaten Microsoft 365-apps voor Enterprise zonder dat u een licentie nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="ad637-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad637-108">Licenties op basis van apparaten op basis van Microsoft 365-apps voor ondernemingen is alleen beschikbaar als een licentie voor de invoegtoepassing voor sommige commerciële klanten en sommige education-klanten.</span><span class="sxs-lookup"><span data-stu-id="ad637-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="ad637-109">Voor commerciële klanten is de licentie *Microsoft 365-apps voor Enterprise (apparaat)* en is alleen beschikbaar via een Enterprise Agreement/Enterprise Agreement-abonnement.</span><span class="sxs-lookup"><span data-stu-id="ad637-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="ad637-110">Voor onderwijs klanten is de licentie *Microsoft 365-apps voor onderwijs (apparaat)* en is alleen beschikbaar via inschrijving voor onderwijs oplossingen (EES).</span><span class="sxs-lookup"><span data-stu-id="ad637-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="ad637-111">Lees voor meer informatie het blogbericht over de [beschikbaarheid](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)van de opleiding.</span><span class="sxs-lookup"><span data-stu-id="ad637-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="ad637-112">Neem contact op met de vertegenwoordiger van uw Microsoft-account voor commerciële beschikbaarheid.</span><span class="sxs-lookup"><span data-stu-id="ad637-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="ad637-113">Als u wilt beginnen, maakt u een groep in het Azure Active Directory-Beheercentrum en wijst u vervolgens apparaten toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="ad637-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="ad637-114">Zie [licenties voor Microsoft 365-apps voor ondernemingen voor](https://go.microsoft.com/fwlink/p/?linkid=2094216)meer informatie over licenties voor apparaten, waaronder hardwarevereisten, welke soorten groepen u kunt gebruiken en hoe u microsoft 365-apps voor Enterprise kunt configureren voor het gebruik van licenties voor het gebruik van een apparaat.</span><span class="sxs-lookup"><span data-stu-id="ad637-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ad637-115">U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="ad637-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="ad637-116">Licenties toewijzen aan apparaten</span><span class="sxs-lookup"><span data-stu-id="ad637-116">Assign licenses to devices</span></span>

<span data-ttu-id="ad637-117">Wanneer u licenties toewijst aan een groep, kunt u een licentie toewijzen aan alle apparaten in de groep.</span><span class="sxs-lookup"><span data-stu-id="ad637-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="ad637-118">U kunt slechts één abonnement toewijzen aan een enkele groep.</span><span class="sxs-lookup"><span data-stu-id="ad637-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="ad637-119">Ga in het Microsoft 365-Beheercentrum naar de pagina **facturerings**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> .</span><span class="sxs-lookup"><span data-stu-id="ad637-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="ad637-120">Kies op de pagina **licenties** de optie **Microsoft 365 apps for education (hardware)** of **Microsoft 365-apps voor Enterprise (apparaat)**.</span><span class="sxs-lookup"><span data-stu-id="ad637-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="ad637-121">Kies een abonnement op de volgende pagina en kies vervolgens **licenties toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="ad637-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="ad637-122">In het deelvenster **licenties toewijzen aan een groep** begint u met het typen van de naam van een groep en kiest u deze van de resultaten om deze aan de lijst toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="ad637-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="ad637-123">Kies **toewijzen**en kies vervolgens **sluiten**.</span><span class="sxs-lookup"><span data-stu-id="ad637-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="ad637-124">Licenties van apparaten intrekken</span><span class="sxs-lookup"><span data-stu-id="ad637-124">Unassign licenses from devices</span></span>

<span data-ttu-id="ad637-125">Wanneer u licenties van een groep intrekken, verwijdert u de licenties van alle apparaten in de groep.</span><span class="sxs-lookup"><span data-stu-id="ad637-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="ad637-126">Alle apps en de bijbehorende gegevens zijn dan alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="ad637-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="ad637-127">Ga in het Beheercentrum naar de pagina **factuur**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">licenties</a> .</span><span class="sxs-lookup"><span data-stu-id="ad637-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="ad637-128">Kies op de pagina **licenties** de optie **Microsoft 365 apps for education (hardware)** of **Microsoft 365-apps voor Enterprise (apparaat)**.</span><span class="sxs-lookup"><span data-stu-id="ad637-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="ad637-129">Kies een abonnement op de volgende pagina, kies **meer acties**en kies vervolgens **licenties intrekken**.</span><span class="sxs-lookup"><span data-stu-id="ad637-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="ad637-130">Kies in het dialoogvenster **licenties intrekken** de optie **intrekken opheffen**.</span><span class="sxs-lookup"><span data-stu-id="ad637-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>