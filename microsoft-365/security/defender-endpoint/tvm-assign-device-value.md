---
title: Apparaatwaarde toewijzen - bedreigings- en kwetsbaarheidsbeheer
description: Meer informatie over het toewijzen van een lage, normale of hoge waarde aan een apparaat om onderscheid te maken tussen activumprioriteiten.
keywords: Microsoft Defender voor de waarde van het eindpuntapparaat, de waarde van het apparaat voor bedreigings- en kwetsbaarheidsbeheer, apparaten met een hoge waarde, blootstellingsscore voor apparaatwaarde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1f5d90190418f84795bdd899ea0e48ac25831a96
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689387"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a><span data-ttu-id="f1b60-104">Apparaatwaarde toewijzen - bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="f1b60-104">Assign device value - threat and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f1b60-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="f1b60-105">**Applies to:**</span></span>

- [<span data-ttu-id="f1b60-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="f1b60-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f1b60-107">Bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="f1b60-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f1b60-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f1b60-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f1b60-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="f1b60-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f1b60-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="f1b60-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

<span data-ttu-id="f1b60-111">Als u de waarde van een apparaat definieert, kunt u onderscheid maken tussen activumprioriteiten.</span><span class="sxs-lookup"><span data-stu-id="f1b60-111">Defining a device’s value helps you differentiate between asset priorities.</span></span> <span data-ttu-id="f1b60-112">De apparaatwaarde wordt gebruikt om de risicobereidheid van een afzonderlijk activum op te nemen in de berekening van blootstellingsscores voor bedreigings- en kwetsbaarheidsbeheer.</span><span class="sxs-lookup"><span data-stu-id="f1b60-112">The device value is used to incorporate the risk appetite of an individual asset into the threat and vulnerability management exposure score calculation.</span></span> <span data-ttu-id="f1b60-113">Apparaten die zijn toegewezen als 'hoge waarde' krijgen meer gewicht.</span><span class="sxs-lookup"><span data-stu-id="f1b60-113">Devices assigned as “high value” will receive more weight.</span></span>

<span data-ttu-id="f1b60-114">U kunt ook de [set device value API gebruiken.](set-device-value.md)</span><span class="sxs-lookup"><span data-stu-id="f1b60-114">You can also use the [set device value API](set-device-value.md).</span></span>

<span data-ttu-id="f1b60-115">Opties voor apparaatwaarde:</span><span class="sxs-lookup"><span data-stu-id="f1b60-115">Device value options:</span></span>

- <span data-ttu-id="f1b60-116">Laag</span><span class="sxs-lookup"><span data-stu-id="f1b60-116">Low</span></span>
- <span data-ttu-id="f1b60-117">Normaal (standaard)</span><span class="sxs-lookup"><span data-stu-id="f1b60-117">Normal (Default)</span></span>
- <span data-ttu-id="f1b60-118">Hoog</span><span class="sxs-lookup"><span data-stu-id="f1b60-118">High</span></span>

<span data-ttu-id="f1b60-119">Voorbeelden van apparaten die een hoge waarde moeten krijgen:</span><span class="sxs-lookup"><span data-stu-id="f1b60-119">Examples of devices that should be assigned a high value:</span></span>

- <span data-ttu-id="f1b60-120">Domeincontrollers, Active Directory</span><span class="sxs-lookup"><span data-stu-id="f1b60-120">Domain controllers, Active Directory</span></span>
- <span data-ttu-id="f1b60-121">Apparaten met internet</span><span class="sxs-lookup"><span data-stu-id="f1b60-121">Internet facing devices</span></span>
- <span data-ttu-id="f1b60-122">VIP-apparaten</span><span class="sxs-lookup"><span data-stu-id="f1b60-122">VIP devices</span></span>
- <span data-ttu-id="f1b60-123">Apparaten die interne/externe productieservices hosten</span><span class="sxs-lookup"><span data-stu-id="f1b60-123">Devices hosting internal/external production services</span></span>

## <a name="choose-device-value"></a><span data-ttu-id="f1b60-124">Apparaatwaarde kiezen</span><span class="sxs-lookup"><span data-stu-id="f1b60-124">Choose device value</span></span>

1. <span data-ttu-id="f1b60-125">Navigeer naar een apparaatpagina, de eenvoudigste plaats is uit de apparaatvoorraad.</span><span class="sxs-lookup"><span data-stu-id="f1b60-125">Navigate to any device page, the easiest place is from the device inventory.</span></span>

2. <span data-ttu-id="f1b60-126">Selecteer **Apparaatwaarde** op drie puntjes naast de actiebalk boven aan de pagina.</span><span class="sxs-lookup"><span data-stu-id="f1b60-126">Select **Device value** from three dots next to the actions bar at the top of the page.</span></span>

    ![Voorbeeld van de vervolgkeuzekeuze van de apparaatwaarde.](images/tvm-device-value-dropdown.png)

3. <span data-ttu-id="f1b60-128">Er wordt een flyout weergegeven met de huidige apparaatwaarde en wat dit betekent.</span><span class="sxs-lookup"><span data-stu-id="f1b60-128">A flyout will appear with the current device value and what it means.</span></span> <span data-ttu-id="f1b60-129">Controleer de waarde van het apparaat en kies het apparaat dat het beste bij uw apparaat past.</span><span class="sxs-lookup"><span data-stu-id="f1b60-129">Review the value of the device and choose the one that best fits your device.</span></span>
<span data-ttu-id="f1b60-130">![Voorbeeld van de flyout van de apparaatwaarde.](images/tvm-device-value-flyout.png)</span><span class="sxs-lookup"><span data-stu-id="f1b60-130">![Example of the device value flyout.](images/tvm-device-value-flyout.png)</span></span>

## <a name="how-device-value-impacts-your-exposure-score"></a><span data-ttu-id="f1b60-131">Hoe de apparaatwaarde van invloed is op uw blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="f1b60-131">How device value impacts your exposure score</span></span>

<span data-ttu-id="f1b60-132">De blootstellingsscore is een gewogen gemiddelde op alle apparaten.</span><span class="sxs-lookup"><span data-stu-id="f1b60-132">The exposure score is a weighted average across all devices.</span></span> <span data-ttu-id="f1b60-133">Als u apparaatgroepen hebt, kunt u de score ook filteren op apparaatgroep.</span><span class="sxs-lookup"><span data-stu-id="f1b60-133">If you have device groups, you can also filter the score by device group.</span></span>

- <span data-ttu-id="f1b60-134">Normale apparaten hebben een gewicht van 1</span><span class="sxs-lookup"><span data-stu-id="f1b60-134">Normal devices have a weight of 1</span></span>
- <span data-ttu-id="f1b60-135">Apparaten met een lage waarde hebben een gewicht van 0,75</span><span class="sxs-lookup"><span data-stu-id="f1b60-135">Low value devices have a weight of 0.75</span></span>
- <span data-ttu-id="f1b60-136">Apparaten met een hoge waarde hebben een gewicht van NumberOfAssets / 10.</span><span class="sxs-lookup"><span data-stu-id="f1b60-136">High value devices have a weight of NumberOfAssets / 10.</span></span>
    - <span data-ttu-id="f1b60-137">Als u 100 apparaten hebt, heeft elk apparaat met een hoge waarde een gewicht van 10 (100-10)</span><span class="sxs-lookup"><span data-stu-id="f1b60-137">If you have 100 devices, each high value device will have a weight of 10 (100/10)</span></span>

## <a name="related-topics"></a><span data-ttu-id="f1b60-138">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="f1b60-138">Related topics</span></span>

- [<span data-ttu-id="f1b60-139">Overzicht van bedreigings- en kwetsbaarheidsbeheer</span><span class="sxs-lookup"><span data-stu-id="f1b60-139">Threat and vulnerability management overview</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f1b60-140">Blootstellingsscore</span><span class="sxs-lookup"><span data-stu-id="f1b60-140">Exposure Score</span></span>](tvm-exposure-score.md)
- [<span data-ttu-id="f1b60-141">API‘s</span><span class="sxs-lookup"><span data-stu-id="f1b60-141">APIs</span></span>](next-gen-threat-and-vuln-mgt.md#apis)