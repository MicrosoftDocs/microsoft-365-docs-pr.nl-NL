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
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911480"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="d8000-103">Licenties voor apparaten beheren</span><span class="sxs-lookup"><span data-stu-id="d8000-103">Manage licenses for devices</span></span>

<span data-ttu-id="d8000-104">Als u Microsoft 365 Apps voor ondernemingen (apparaat) of Microsoft 365 Apps voor Onderwijs (apparaat) hebt, kunt u licenties toewijzen aan apparaten met Azure AD-groepen.</span><span class="sxs-lookup"><span data-stu-id="d8000-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="d8000-105">Wanneer een apparaat een licentie heeft, kan iedereen die dat apparaat gebruikt Microsoft 365 Apps voor ondernemingen gebruiken (eerder Office 365 ProPlus genoemd).</span><span class="sxs-lookup"><span data-stu-id="d8000-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="d8000-106">Stel dat u 20 laptops en tablets hebt die worden gebruikt door personen in uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="d8000-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="d8000-107">Wanneer u een licentie toewijst aan elk apparaat, gebruikt elke persoon die zich aanmeldt bij een van de apparaten Microsoft 365 Apps voor bedrijven zonder dat er een eigen licentie voor nodig is.</span><span class="sxs-lookup"><span data-stu-id="d8000-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8000-108">Apparaatlicenties voor Microsoft 365 Apps voor ondernemingen zijn alleen beschikbaar als een invoeglicentie voor sommige commerciële klanten en sommige klanten in het onderwijs.</span><span class="sxs-lookup"><span data-stu-id="d8000-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="d8000-109">Voor commerciële klanten is de licentie *Microsoft 365 Apps voor ondernemingen (apparaat)* en is deze alleen beschikbaar via Enterprise Agreement/Enterprise Agreement Subscription.</span><span class="sxs-lookup"><span data-stu-id="d8000-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="d8000-110">Voor onderwijsklanten is de licentie *Microsoft 365 Apps voor onderwijs (apparaat)* en is deze alleen beschikbaar via Inschrijving voor Education Solutions (EES).</span><span class="sxs-lookup"><span data-stu-id="d8000-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="d8000-111">Lees het blogbericht over beschikbaarheid [van onderwijs voor meer informatie.](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/)</span><span class="sxs-lookup"><span data-stu-id="d8000-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="d8000-112">Neem voor commerciële beschikbaarheid contact op met de vertegenwoordiger van uw Microsoft-account.</span><span class="sxs-lookup"><span data-stu-id="d8000-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="d8000-113">Om te beginnen maakt u een groep in het Azure Active Directory-beheercentrum en wijst u vervolgens apparaten toe aan de groep.</span><span class="sxs-lookup"><span data-stu-id="d8000-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="d8000-114">Zie Apparaatlicenties voor [Microsoft 365 Apps](/deployoffice/device-based-licensing)voor bedrijven voor meer informatie over apparaatlicenties, inclusief apparaatvereisten, welke typen groepen u kunt gebruiken en hoe u Microsoft 365 Apps voor ondernemingen kunt configureren voor het gebruik van apparaatlicenties.</span><span class="sxs-lookup"><span data-stu-id="d8000-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d8000-115">U moet een globale beheerder zijn om de taken in dit artikel uit te voeren.</span><span class="sxs-lookup"><span data-stu-id="d8000-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="d8000-116">Licenties toewijzen aan apparaten</span><span class="sxs-lookup"><span data-stu-id="d8000-116">Assign licenses to devices</span></span>

<span data-ttu-id="d8000-117">Wanneer u licenties aan een groep toewijst, wijst u licenties toe aan alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="d8000-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="d8000-118">U kunt slechts één abonnement toewijzen aan één groep.</span><span class="sxs-lookup"><span data-stu-id="d8000-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="d8000-119">Ga in het Microsoft 365-beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a></span><span class="sxs-lookup"><span data-stu-id="d8000-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d8000-120">Kies op **de pagina** Licenties de optie **Microsoft 365 Apps voor onderwijs (apparaat)** of **Microsoft 365 Apps voor ondernemingen (apparaat).**</span><span class="sxs-lookup"><span data-stu-id="d8000-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="d8000-121">Kies op de volgende pagina een abonnement en kies **vervolgens Licenties toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="d8000-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="d8000-122">Typ een **groepsnaam** in het deelvenster Licenties toewijzen aan een groep en kies deze in de resultaten om deze toe te voegen aan de lijst.</span><span class="sxs-lookup"><span data-stu-id="d8000-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="d8000-123">Kies **Toewijzen** en kies **vervolgens Sluiten.**</span><span class="sxs-lookup"><span data-stu-id="d8000-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="d8000-124">Licenties van apparaten niet toewijzen</span><span class="sxs-lookup"><span data-stu-id="d8000-124">Unassign licenses from devices</span></span>

<span data-ttu-id="d8000-125">Wanneer u licenties uit een groep opwijst, verwijdert u de licenties van alle apparaten binnen de groep.</span><span class="sxs-lookup"><span data-stu-id="d8000-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="d8000-126">Alle apps en bijbehorende gegevens worden vervolgens alleen-lezen.</span><span class="sxs-lookup"><span data-stu-id="d8000-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="d8000-127">Ga in het beheercentrum naar de pagina   >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Factureringslicenties.</a></span><span class="sxs-lookup"><span data-stu-id="d8000-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="d8000-128">Kies op **de pagina** Licenties de optie **Microsoft 365 Apps voor onderwijs (apparaat)** of **Microsoft 365 Apps voor ondernemingen (apparaat).**</span><span class="sxs-lookup"><span data-stu-id="d8000-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="d8000-129">Kies op de volgende pagina een abonnement, kies **Meer acties** en kies vervolgens Licenties **niet toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="d8000-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="d8000-130">Kies in **het dialoogvenster** Licenties niet toewijzen de optie **Niet toewijzen.**</span><span class="sxs-lookup"><span data-stu-id="d8000-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>