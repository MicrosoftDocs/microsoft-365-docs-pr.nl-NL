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
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: ce3c8f7d669f2fe5d19c48d7a1fb1f224aaec7f4
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402868"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="a5cff-103">Licenties voor apparaten beheren</span><span class="sxs-lookup"><span data-stu-id="a5cff-103">Manage licenses for devices</span></span>

<span data-ttu-id="a5cff-104">Als u Microsoft 365 Apps voor bedrijven (apparaat) of Microsoft 365 Apps for Education (apparaat) hebt, u licenties toewijzen aan apparaten met behulp van Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="a5cff-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="a5cff-105">Wanneer een apparaat een licentie heeft, kan iedereen die dat apparaat gebruikt Microsoft 365 Apps voor bedrijven gebruiken (voorheen Office 365 ProPlus genoemd).</span><span class="sxs-lookup"><span data-stu-id="a5cff-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="a5cff-106">Stel dat u 20 laptops en tablets hebt die door mensen in uw organisatie worden gebruikt.</span><span class="sxs-lookup"><span data-stu-id="a5cff-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="a5cff-107">Wanneer u een licentie aan elk apparaat toewijst, gebruikt elke persoon die zich aanmeldt bij een van de apparaten Microsoft 365 Apps voor bedrijven zonder de noodzaak van een eigen licentie.</span><span class="sxs-lookup"><span data-stu-id="a5cff-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5cff-108">Apparaatgebaseerde licenties voor Microsoft 365 Apps for Enterprise zijn alleen beschikbaar als add-on licentie voor sommige commerciële klanten en sommige klanten in het onderwijs.</span><span class="sxs-lookup"><span data-stu-id="a5cff-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="a5cff-109">Voor commerciële klanten is de licentie *Microsoft 365 Apps for Enterprise (apparaat)* en is deze alleen beschikbaar via enterprise agreement/enterprise agreement subscription.</span><span class="sxs-lookup"><span data-stu-id="a5cff-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="a5cff-110">Voor onderwijsklanten is de licentie *Microsoft 365 Apps for Education (apparaat)* en alleen beschikbaar via Inschrijving voor Onderwijsoplossingen (EES).</span><span class="sxs-lookup"><span data-stu-id="a5cff-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="a5cff-111">Voor meer informatie, lees de blogpost over [de beschikbaarheid van het onderwijs](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="a5cff-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="a5cff-112">Neem voor commerciële beschikbaarheid contact op met uw Microsoft-accountvertegenwoordiger.</span><span class="sxs-lookup"><span data-stu-id="a5cff-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="a5cff-113">Om te beginnen maakt u een groep in het Azure Active Directory-beheercentrum en wijst u apparaten toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="a5cff-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="a5cff-114">Zie [Apparaatgebaseerde licenties voor Microsoft 365 Apps voor bedrijven](https://go.microsoft.com/fwlink/p/?linkid=2094216)voor meer informatie over apparaatlicenties, waaronder apparaatvereisten, welke typen groepen u gebruiken en hoe u Microsoft 365 Apps for Enterprise configureren om apparaatlicenties te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="a5cff-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a5cff-115">U moet een globale beheerder zijn om de taken in dit artikel te voltooien.</span><span class="sxs-lookup"><span data-stu-id="a5cff-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="a5cff-116">Licenties toewijzen aan apparaten</span><span class="sxs-lookup"><span data-stu-id="a5cff-116">Assign licenses to devices</span></span>

<span data-ttu-id="a5cff-117">Wanneer u licenties aan een groep toewijst, wijst u licenties toe aan alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="a5cff-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="a5cff-118">U slechts één abonnement toewijzen aan één groep.</span><span class="sxs-lookup"><span data-stu-id="a5cff-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="a5cff-119">Ga in het Microsoft 365-beheercentrum naar de pagina **Billing**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a></span><span class="sxs-lookup"><span data-stu-id="a5cff-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a5cff-120">Kies **op** de pagina Licenties de optie **Microsoft 365 Apps for Education (apparaat)** of **Microsoft 365 Apps for Enterprise (apparaat).**</span><span class="sxs-lookup"><span data-stu-id="a5cff-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="a5cff-121">Kies op de volgende pagina een abonnement en kies **Licenties toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="a5cff-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="a5cff-122">Begin in het **groepsvenster licenties toewijzen aan een groepsvenster** met het typen van een groepsnaam en kies deze vervolgens uit de resultaten om deze aan de lijst toe te voegen.</span><span class="sxs-lookup"><span data-stu-id="a5cff-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="a5cff-123">Kies **Toewijzen**en kies **Sluiten**.</span><span class="sxs-lookup"><span data-stu-id="a5cff-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="a5cff-124">Licenties van apparaten ongedaan maken</span><span class="sxs-lookup"><span data-stu-id="a5cff-124">Unassign licenses from devices</span></span>

<span data-ttu-id="a5cff-125">Wanneer u licenties uit een groep ongedaan maakt, verwijdert u de licenties van alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="a5cff-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="a5cff-126">Alle apps en de bijbehorende gegevens zijn dan alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="a5cff-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="a5cff-127">Ga in het beheercentrum naar de pagina **Factureringslicenties.**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a></span><span class="sxs-lookup"><span data-stu-id="a5cff-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="a5cff-128">Kies **op** de pagina Licenties de optie **Microsoft 365 Apps for Education (apparaat)** of **Microsoft 365 Apps for Enterprise (apparaat).**</span><span class="sxs-lookup"><span data-stu-id="a5cff-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="a5cff-129">Kies op de volgende pagina een abonnement, kies **Meer acties**en kies **Licenties ongedaan maken**.</span><span class="sxs-lookup"><span data-stu-id="a5cff-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="a5cff-130">Kies in het dialoogvenster **Licenties zonder toewijzing** de optie **Niet-toewijzen**.</span><span class="sxs-lookup"><span data-stu-id="a5cff-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>