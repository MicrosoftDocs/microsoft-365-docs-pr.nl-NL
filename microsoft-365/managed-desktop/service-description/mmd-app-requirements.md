---
title: Microsoft Managed Desktop app-vereisten
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: 322a46ce48cce4d080e51f482178462934d5c8f2
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659712"
---
# <a name="microsoft-managed-desktop-app-requirements"></a><span data-ttu-id="4b42e-103">Microsoft Managed Desktop app-vereisten</span><span class="sxs-lookup"><span data-stu-id="4b42e-103">Microsoft Managed Desktop app requirements</span></span>

<!--This topic is the target for aka.ms/app-req. This is aka link is used from EA agreement for MMD. do not delete.-->

<!--Application addendum -->
 
<span data-ttu-id="4b42e-104">Microsoft Managed Desktop vereist dat we apparaten beheren met een specifieke benadering om de prestaties, betrouwbaarheid en servicebaarheid van apparaten te garanderen.</span><span class="sxs-lookup"><span data-stu-id="4b42e-104">Microsoft Managed Desktop requires that we manage devices using a specific approach to guarantee the performance, reliability, and serviceability of devices.</span></span>


|<span data-ttu-id="4b42e-105">Beheergebied</span><span class="sxs-lookup"><span data-stu-id="4b42e-105">Management area</span></span>  |<span data-ttu-id="4b42e-106">Microsoft Managed Desktop benadering</span><span class="sxs-lookup"><span data-stu-id="4b42e-106">Microsoft Managed Desktop approach</span></span>  |
|---------|---------|
|<span data-ttu-id="4b42e-107">Apparaatconfiguratie of beleidsbeleid</span><span class="sxs-lookup"><span data-stu-id="4b42e-107">Device configuration or policy management</span></span>     |  <span data-ttu-id="4b42e-108">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4b42e-108">Microsoft Intune</span></span>       |
|<span data-ttu-id="4b42e-109">Toepassingsbeheer</span><span class="sxs-lookup"><span data-stu-id="4b42e-109">Application management</span></span>     | <span data-ttu-id="4b42e-110">Microsoft Intune en Bedrijfsportal</span><span class="sxs-lookup"><span data-stu-id="4b42e-110">Microsoft Intune and Company Portal</span></span>        |
|<span data-ttu-id="4b42e-111">Stuurprogramma-implementatie</span><span class="sxs-lookup"><span data-stu-id="4b42e-111">Driver deployment</span></span>     |  <span data-ttu-id="4b42e-112">Stuurprogramma's die zijn inbegrepen bij het apparaat, Windows Update of Intune</span><span class="sxs-lookup"><span data-stu-id="4b42e-112">Drivers included with the device, Windows Update, or Intune</span></span>       |
|<span data-ttu-id="4b42e-113">Apparaatbeveiliging</span><span class="sxs-lookup"><span data-stu-id="4b42e-113">Device security</span></span>     | <span data-ttu-id="4b42e-114">Zie [Apparaatbeveiliging](security.md#device-security)</span><span class="sxs-lookup"><span data-stu-id="4b42e-114">See [Device security](security.md#device-security)</span></span>      |
|<span data-ttu-id="4b42e-115">Identiteits- en toegangsbeheer</span><span class="sxs-lookup"><span data-stu-id="4b42e-115">Identity and access management</span></span>     | <span data-ttu-id="4b42e-116">Zie [Identiteits- en toegangsbeheer](security.md#identity-and-access-management)</span><span class="sxs-lookup"><span data-stu-id="4b42e-116">See [Identity and access management](security.md#identity-and-access-management)</span></span>        |
|<span data-ttu-id="4b42e-117">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="4b42e-117">Network security</span></span>     | <span data-ttu-id="4b42e-118">Zie [Netwerkbeveiliging](security.md#network-security)</span><span class="sxs-lookup"><span data-stu-id="4b42e-118">See [Network security](security.md#network-security)</span></span>        |
|<span data-ttu-id="4b42e-119">Informatiebeveiliging</span><span class="sxs-lookup"><span data-stu-id="4b42e-119">Information security</span></span>     |  <span data-ttu-id="4b42e-120">Zie [Informatiebeveiliging](security.md#information-security)</span><span class="sxs-lookup"><span data-stu-id="4b42e-120">See [Information security](security.md#information-security)</span></span>       |
|<span data-ttu-id="4b42e-121">Gegevensherstel</span><span class="sxs-lookup"><span data-stu-id="4b42e-121">Data recovery</span></span>     | <span data-ttu-id="4b42e-122">OneDrive voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="4b42e-122">OneDrive for Business</span></span>        |
|<span data-ttu-id="4b42e-123">Kernproductiviteit</span><span class="sxs-lookup"><span data-stu-id="4b42e-123">Core productivity</span></span>     | <span data-ttu-id="4b42e-124">Microsoft 365-apps voor ondernemingen</span><span class="sxs-lookup"><span data-stu-id="4b42e-124">Microsoft 365 Apps for enterprise</span></span>    |
|<span data-ttu-id="4b42e-125">Browser</span><span class="sxs-lookup"><span data-stu-id="4b42e-125">Browser</span></span>     | <span data-ttu-id="4b42e-126">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="4b42e-126">Microsoft Edge</span></span>        |




<span data-ttu-id="4b42e-127">Microsoft Managed Desktop kan andere software controleren die wordt uitgevoerd op beheerde apparaten.</span><span class="sxs-lookup"><span data-stu-id="4b42e-127">Microsoft Managed Desktop might monitor other software running on managed devices.</span></span> <span data-ttu-id="4b42e-128">Als dit een negatieve invloed heeft op apparaatbeheer, apparaatbeveiliging, prestaties of betrouwbaarheid, moet u mogelijk een uitzondering op het [serviceplan aanvragen.](customizing.md)</span><span class="sxs-lookup"><span data-stu-id="4b42e-128">If it negatively impacts device management, device security, performance, or reliability, you might be required to request an [exception to the service plan](customizing.md).</span></span>
