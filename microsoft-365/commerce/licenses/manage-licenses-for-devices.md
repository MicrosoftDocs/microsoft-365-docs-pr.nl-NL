---
title: Licenties voor apparaten beheren
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: a29465e9425694f8913cc09d1b8a0c761c79803c
ms.sourcegitcommit: 2859c82b30ae9cbd3a3e4bcdebd65f18444f1a9e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/18/2020
ms.locfileid: "42826277"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="868cb-103">Licenties voor apparaten beheren</span><span class="sxs-lookup"><span data-stu-id="868cb-103">Manage licenses for devices</span></span>

<span data-ttu-id="868cb-104">Als u Office 365 ProPlus (apparaat) of Office 365 ProPlus voor Onderwijs (apparaat) hebt, u licenties toewijzen aan apparaten met Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="868cb-104">If you have Office 365 ProPlus (device) or Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="868cb-105">Wanneer een apparaat een licentie heeft, kan iedereen die dat apparaat gebruikt Office 365 gebruiken.</span><span class="sxs-lookup"><span data-stu-id="868cb-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="868cb-106">Stel dat u 20 laptops en tablets hebt die worden gebruikt door mensen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="868cb-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="868cb-107">Wanneer u een licentie aan elk apparaat toewijst, gebruikt elke persoon die zich aanmeldt bij een van de apparaten Office 365 zonder dat zijn eigen licentie nodig is.</span><span class="sxs-lookup"><span data-stu-id="868cb-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="868cb-108">Apparaatgebaseerde licenties voor Office 365 ProPlus zijn alleen beschikbaar als invoeglicentie voor sommige klanten en sommige klanten in het onderwijs.</span><span class="sxs-lookup"><span data-stu-id="868cb-108">Device-based licensing for Office 365 ProPlus is available only as an add-on license for some commerical customers and some education customers.</span></span> <span data-ttu-id="868cb-109">Voor commerciële klanten is de licentie *Office 365 ProPlus (apparaat)* en is deze alleen beschikbaar via Enterprise Agreement/Enterprise Agreement Subscription.</span><span class="sxs-lookup"><span data-stu-id="868cb-109">For commercial customers, the license is *Office 365 ProPlus (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="868cb-110">Voor klanten in het onderwijs is de licentie *Office 365 ProPlus for Education (apparaat)* en is deze alleen beschikbaar via Enrollment for Education Solutions (EES).</span><span class="sxs-lookup"><span data-stu-id="868cb-110">For education customers, the license is *Office 365 ProPlus for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="868cb-111">Voor meer informatie, lees de blogpost over [beschikbaarheid van het onderwijs](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="868cb-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="868cb-112">Neem voor commerciële beschikbaarheid contact op met uw Microsoft-accountvertegenwoordiger.</span><span class="sxs-lookup"><span data-stu-id="868cb-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="868cb-113">Om te beginnen maakt u een groep in het Azure Active Directory-beheercentrum en wijst u apparaten toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="868cb-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="868cb-114">Zie [Apparaatgebaseerde licenties voor Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216)voor meer informatie over apparaatlicenties, waaronder apparaatvereisten, welke typen groepen u gebruiken en hoe u Office 365 ProPlus configureren om apparaatlicenties te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="868cb-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device-based licensing for Office 365 ProPlus](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="868cb-115">U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="868cb-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="868cb-116">Licenties toewijzen aan apparaten</span><span class="sxs-lookup"><span data-stu-id="868cb-116">Assign licenses to devices</span></span>

<span data-ttu-id="868cb-117">Wanneer u licenties aan een groep toewijst, wijst u licenties toe aan alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="868cb-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="868cb-118">U slechts één abonnement toewijzen aan één groep.</span><span class="sxs-lookup"><span data-stu-id="868cb-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="868cb-119">Ga in het Microsoft 365-beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a> **Billing**</span><span class="sxs-lookup"><span data-stu-id="868cb-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="868cb-120">Kies op de pagina **Licenties** de optie **Office 365 ProPlus voor Onderwijs (apparaat)** of **Office ProPlus (apparaat).**</span><span class="sxs-lookup"><span data-stu-id="868cb-120">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="868cb-121">Kies op de volgende pagina een abonnement en kies **Licenties toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="868cb-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="868cb-122">Begin in het deelvenster **Licenties toewijzen aan een groepsvenster** met het typen van een groepsnaam en kies deze vervolgens uit de resultaten om deze aan de lijst toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="868cb-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="868cb-123">Kies **Toewijzen**en kies **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="868cb-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="868cb-124">Licenties van apparaten ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="868cb-124">Unassign licenses from devices</span></span>

<span data-ttu-id="868cb-125">Wanneer u licenties uit een groep ongedaan maakt, verwijdert u de licenties van alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="868cb-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="868cb-126">Alle apps en de bijbehorende gegevens worden vervolgens alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="868cb-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="868cb-127">Ga in het beheercentrum naar de pagina > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a> **Billing**</span><span class="sxs-lookup"><span data-stu-id="868cb-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="868cb-128">Kies op de pagina **Licenties** de optie **Office 365 ProPlus voor Onderwijs (apparaat)** of **Office ProPlus (apparaat).**</span><span class="sxs-lookup"><span data-stu-id="868cb-128">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)** or **Office ProPlus (device)**.</span></span>
3. <span data-ttu-id="868cb-129">Kies op de volgende pagina een abonnement en kies **Meer acties**en kies **Licenties ongedaan maken.**</span><span class="sxs-lookup"><span data-stu-id="868cb-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="868cb-130">Kies in het dialoogvenster **Licenties ontoegewezen** maken de optie **Toewijzen .**</span><span class="sxs-lookup"><span data-stu-id="868cb-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>