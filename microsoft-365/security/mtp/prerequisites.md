---
title: Vereisten voor bedreigingsbeveiliging van Microsoft
description: Meer informatie over de vereisten voor licenties, hardware en software en andere configuratie-instellingen voor Microsoft Threat Protection
keywords: vereisten, vereisten, hardware, software, browser, MTP, M365, licentie, E5, A5, EMS, aankoop
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: c482e46cf51cbf11960c02663221df0c136b067c
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857177"
---
# <a name="microsoft-threat-protection-prerequisites"></a><span data-ttu-id="d759a-104">Vereisten voor bedreigingsbeveiliging van Microsoft</span><span class="sxs-lookup"><span data-stu-id="d759a-104">Microsoft Threat Protection prerequisites</span></span>

<span data-ttu-id="d759a-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="d759a-105">**Applies to:**</span></span>
- <span data-ttu-id="d759a-106">Microsoft-bedreigingsbeveiliging</span><span class="sxs-lookup"><span data-stu-id="d759a-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d759a-107">Meer informatie over de vereisten voor licenties, hardware en software en andere configuratie-instellingen voor het inrichten en gebruiken van Microsoft Threat Protection.</span><span class="sxs-lookup"><span data-stu-id="d759a-107">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft Threat Protection.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="d759a-108">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="d759a-108">Licensing requirements</span></span>
<span data-ttu-id="d759a-109">Als u Microsoft Threat Protection wilt gebruiken, hebt u één licentie of een combinatie van licenties nodig.</span><span class="sxs-lookup"><span data-stu-id="d759a-109">To use Microsoft Threat Protection, you need either a single license or a combination of licenses.</span></span>

### <a name="single-license"></a><span data-ttu-id="d759a-110">Eén licentie</span><span class="sxs-lookup"><span data-stu-id="d759a-110">Single license</span></span>
<span data-ttu-id="d759a-111">U *een* van de volgende licenties gebruiken:</span><span class="sxs-lookup"><span data-stu-id="d759a-111">You can use *one* of the following licenses:</span></span>

- <span data-ttu-id="d759a-112">Microsoft 365 E5 of A5</span><span class="sxs-lookup"><span data-stu-id="d759a-112">Microsoft 365 E5 or A5</span></span>
- <span data-ttu-id="d759a-113">Microsoft 365 E5-beveiliging of A5-beveiliging</span><span class="sxs-lookup"><span data-stu-id="d759a-113">Microsoft 365 E5 Security or A5 Security</span></span>

### <a name="combination-of-licenses"></a><span data-ttu-id="d759a-114">Combinatie van licenties</span><span class="sxs-lookup"><span data-stu-id="d759a-114">Combination of licenses</span></span>
<span data-ttu-id="d759a-115">U ook een combinatie van licenties voor E5- of A5-abonnementen gebruiken voor Office 365, *Enterprise Mobility + Security (EMS)* en Windows.</span><span class="sxs-lookup"><span data-stu-id="d759a-115">You can also use a combination of licenses for E5 or A5 subscriptions to Office 365, *Enterprise Mobility + Security (EMS)*, and Windows.</span></span> <span data-ttu-id="d759a-116">De licentiecombinatie moet *al* deze licenties bevatten:</span><span class="sxs-lookup"><span data-stu-id="d759a-116">The license combination must include *all* of these licenses:</span></span>

- <span data-ttu-id="d759a-117">Office 365 E5 of A5</span><span class="sxs-lookup"><span data-stu-id="d759a-117">Office 365 E5 or A5</span></span>
- <span data-ttu-id="d759a-118">*Enterprise Mobility + Security (EMS)* E5 of A5</span><span class="sxs-lookup"><span data-stu-id="d759a-118">*Enterprise Mobility + Security (EMS)* E5 or A5</span></span>
- <span data-ttu-id="d759a-119">Windows E5 of A5</span><span class="sxs-lookup"><span data-stu-id="d759a-119">Windows E5 or A5</span></span>

<span data-ttu-id="d759a-120">Bekijk voor meer informatie [de Microsoft 365 Enterprise-serviceplannen](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span><span class="sxs-lookup"><span data-stu-id="d759a-120">For more information, [view the Microsoft 365 Enterprise service plans](https://www.microsoft.com/licensing/product-licensing/microsoft-365-enterprise).</span></span>

> <span data-ttu-id="d759a-121">Heb je nog geen rijbewijs?</span><span class="sxs-lookup"><span data-stu-id="d759a-121">Don't have license yet?</span></span> [<span data-ttu-id="d759a-122">Een Microsoft 365-abonnement proberen of kopen</span><span class="sxs-lookup"><span data-stu-id="d759a-122">Try or buy a Microsoft 365 subscription</span></span>](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide)

### <a name="check-your-existing--licenses"></a><span data-ttu-id="d759a-123">Uw bestaande licenties controleren</span><span class="sxs-lookup"><span data-stu-id="d759a-123">Check your existing  licenses</span></span>
<span data-ttu-id="d759a-124">Ga naar microsoft 365-beheercentrum[(admin.microsoft.com)](https://admin.microsoft.com/)om uw bestaande licenties te bekijken.</span><span class="sxs-lookup"><span data-stu-id="d759a-124">Go to Microsoft 365 admin center ([admin.microsoft.com](https://admin.microsoft.com/)) to view your existing licenses.</span></span> <span data-ttu-id="d759a-125">Ga in het beheercentrum naar **Factureringslicenties** > **Licenses**.</span><span class="sxs-lookup"><span data-stu-id="d759a-125">In the admin center, go to **Billing** > **Licenses**.</span></span>

>[!NOTE]
> <span data-ttu-id="d759a-126">U moet de **factureringsbeheerder** of de rol **globale lezer** [in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) toegewezen hebben om licentiegegevens te kunnen zien.</span><span class="sxs-lookup"><span data-stu-id="d759a-126">You need to be assigned either the **Billing admin** or **Global reader** [role in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#available-roles) to be able to see license information.</span></span> <span data-ttu-id="d759a-127">Als u toegangsproblemen ondervindt, neemt u contact op met een globale beheerder.</span><span class="sxs-lookup"><span data-stu-id="d759a-127">If you encounter access problems, contact a global admin.</span></span>

## <a name="browser-requirements"></a><span data-ttu-id="d759a-128">Browservereisten</span><span class="sxs-lookup"><span data-stu-id="d759a-128">Browser requirements</span></span>
<span data-ttu-id="d759a-129">Toegang tot Microsoft Threat Protection in het Microsoft 365-beveiligingscentrum met Microsoft Edge, Internet Explorer 11 of een HTML 5-compatibele webbrowser.</span><span class="sxs-lookup"><span data-stu-id="d759a-129">Access Microsoft Threat Protection in the Microsoft 365 security center using Microsoft Edge, Internet Explorer 11, or any HTML 5 compliant web browser.</span></span>

## <a name="microsoft-threat-protection-for-us-government-community-cloud-and-us-government-community-cloud-high-gcc-high-customers"></a><span data-ttu-id="d759a-130">Microsoft Threat Protection voor klanten van de Amerikaanse overheid Community Cloud en de Amerikaanse overheid Community Cloud High (GCC High)</span><span class="sxs-lookup"><span data-stu-id="d759a-130">Microsoft Threat Protection for US Government Community Cloud and US Government Community Cloud High (GCC High) customers</span></span>
<span data-ttu-id="d759a-131">Momenteel is Microsoft Threat Protection niet beschikbaar voor Amerikaanse GCC- en GCC High-klanten.</span><span class="sxs-lookup"><span data-stu-id="d759a-131">Currently, Microsoft Threat Protection is not available to US GCC and GCC High customers.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="d759a-132">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="d759a-132">Related topics</span></span>
- [<span data-ttu-id="d759a-133">Overzicht van Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d759a-133">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="d759a-134">Microsoft-bedreigingsbeveiliging inschakelen</span><span class="sxs-lookup"><span data-stu-id="d759a-134">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
