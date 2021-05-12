---
title: Licenties voor apparaten beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: shegu, nicholak
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
description: Meer informatie over het toewijzen van licenties aan groepen voor gebruik met apparaten.
ms.custom:
- AdminSurgePortfolio
- okr_SMB
- commerce_licensing
search.appverid: MET150
ms.date: 03/17/2021
ms.openlocfilehash: 67bd0734953c64f51390aac949a7da477914c7b4
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2021
ms.locfileid: "52331656"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="73cf7-103">Licenties voor apparaten beheren</span><span class="sxs-lookup"><span data-stu-id="73cf7-103">Manage licenses for devices</span></span>

<span data-ttu-id="73cf7-104">Als u een Microsoft 365-apps voor ondernemingen (apparaat) of Microsoft 365-apps voor Onderwijs (apparaat) hebt, kunt u licenties toewijzen aan apparaten met Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="73cf7-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="73cf7-105">Wanneer een apparaat een licentie heeft, kan iedereen die dat apparaat gebruikt, Microsoft 365-apps voor ondernemingen gebruiken (eerder benoemd Office 365 ProPlus).</span><span class="sxs-lookup"><span data-stu-id="73cf7-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="73cf7-106">Stel dat u 20 laptops en tablets hebt die worden gebruikt door personen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="73cf7-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="73cf7-107">Wanneer u een licentie toewijst aan elk apparaat, gebruikt elke persoon die zich aanmeldt bij een van de apparaten Microsoft 365-apps voor ondernemingen zonder dat er een eigen licentie nodig is.</span><span class="sxs-lookup"><span data-stu-id="73cf7-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73cf7-108">Apparaatlicenties voor Microsoft 365-apps voor ondernemingen is alleen beschikbaar als invoeglicentie voor sommige commerciële klanten en sommige klanten van het onderwijs.</span><span class="sxs-lookup"><span data-stu-id="73cf7-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="73cf7-109">Voor commerciële klanten is de licentie Microsoft 365-apps voor ondernemingen *(apparaat)* en is deze alleen beschikbaar via Enterprise Agreement/Enterprise Agreement-abonnement.</span><span class="sxs-lookup"><span data-stu-id="73cf7-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="73cf7-110">Voor onderwijsklanten is de licentie Microsoft 365-apps voor onderwijs *(apparaat)* en is deze alleen beschikbaar via Inschrijving voor Education Solutions (EES).</span><span class="sxs-lookup"><span data-stu-id="73cf7-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="73cf7-111">Lees het blogbericht over beschikbaarheid [van onderwijs voor meer informatie.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education)</span><span class="sxs-lookup"><span data-stu-id="73cf7-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-office-365-proplus-device-based-subscription-for-education).</span></span> <span data-ttu-id="73cf7-112">Neem voor commerciële beschikbaarheid contact op met de vertegenwoordiger van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="73cf7-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="73cf7-113">Om te beginnen maakt u een groep in het Azure Active Directory beheercentrum en wijst u vervolgens apparaten toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="73cf7-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="73cf7-114">Zie Apparaatlicenties voor Microsoft 365-apps voor ondernemingen voor meer informatie over apparaatlicenties, inclusief apparaatvereisten, welke typen groepen u kunt gebruiken en hoe u Microsoft 365-apps voor ondernemingen [Microsoft 365-apps voor ondernemingen](/deployoffice/device-based-licensing)configureert voor het gebruik van apparaatlicenties.</span><span class="sxs-lookup"><span data-stu-id="73cf7-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73cf7-115">U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="73cf7-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="73cf7-116">Licenties toewijzen aan apparaten</span><span class="sxs-lookup"><span data-stu-id="73cf7-116">Assign licenses to devices</span></span>

<span data-ttu-id="73cf7-117">Wanneer u licenties aan een groep toewijst, wijst u licenties toe aan alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="73cf7-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="73cf7-118">U kunt slechts één abonnement toewijzen aan één groep.</span><span class="sxs-lookup"><span data-stu-id="73cf7-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="73cf7-119">Ga in Microsoft 365 beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a></span><span class="sxs-lookup"><span data-stu-id="73cf7-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="73cf7-120">Kies op **de pagina** Licenties de Microsoft 365-apps voor **onderwijs (apparaat)** of **Microsoft 365-apps voor ondernemingen (apparaat)**.</span><span class="sxs-lookup"><span data-stu-id="73cf7-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="73cf7-121">Kies op de volgende pagina een abonnement en kies **vervolgens Licenties toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="73cf7-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="73cf7-122">Typ een **groepsnaam** in het deelvenster Licenties toewijzen aan een groep en kies deze in de resultaten om deze toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="73cf7-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="73cf7-123">Kies **Toewijzen** en kies **vervolgens Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="73cf7-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="73cf7-124">Licenties van apparaten niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="73cf7-124">Unassign licenses from devices</span></span>

<span data-ttu-id="73cf7-125">Wanneer u licenties uit een groep opwijst, verwijdert u de licenties van alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="73cf7-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="73cf7-126">Alle apps en bijbehorende gegevens worden vervolgens alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="73cf7-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="73cf7-127">Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a></span><span class="sxs-lookup"><span data-stu-id="73cf7-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="73cf7-128">Kies op **de pagina** Licenties de Microsoft 365-apps voor **onderwijs (apparaat)** of **Microsoft 365-apps voor ondernemingen (apparaat)**.</span><span class="sxs-lookup"><span data-stu-id="73cf7-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="73cf7-129">Kies op de volgende pagina een abonnement, kies **Meer acties** en kies vervolgens Licenties **niet toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="73cf7-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="73cf7-130">Kies in **het dialoogvenster** Licenties niet toewijzen de optie **Niet toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="73cf7-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>
