---
title: Uw evaluatieomgeving Microsoft 365 Defender naar productie, Microsoft 365 Defender evaluatie, een evaluatie proberen, een evaluatie houden, productie-evaluatie houden
description: Gebruik dit artikel om uw evals van MDI, MDO, MDE en MCAS te promoten in uw live omgeving in Microsoft 365 Defender of M365D.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: b67f0f493c97b900fa08b10e3eb7a5967560dcfd
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457907"
---
# <a name="promote-your-microsoft-365-defender-evaluation-environment-to-production"></a><span data-ttu-id="84769-103">Uw evaluatieomgeving Microsoft 365 Defender naar de productie</span><span class="sxs-lookup"><span data-stu-id="84769-103">Promote your Microsoft 365 Defender evaluation environment to production</span></span>

<span data-ttu-id="84769-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="84769-104">**Applies to:**</span></span>
- <span data-ttu-id="84769-105">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="84769-105">Microsoft 365 Defender</span></span>

<span data-ttu-id="84769-106">Koop eerst de benodigde licentie om Microsoft 365 Defender evaluatieomgeving te promoten naar de productie.</span><span class="sxs-lookup"><span data-stu-id="84769-106">To promote your Microsoft 365 Defender evaluation environment to production, first purchase the necessary license.</span></span> <span data-ttu-id="84769-107">Volg de stappen in [De eval-omgeving maken](eval-create-eval-environment.md) en koop de Office 365 E5 licentie (in plaats van gratis proefversie starten te selecteren).</span><span class="sxs-lookup"><span data-stu-id="84769-107">Follow the steps in [Create the eval environment](eval-create-eval-environment.md) and purchase the Office 365 E5 license (instead of selecting Start free trial).</span></span>

<span data-ttu-id="84769-108">Voltooi vervolgens een extra configuratie en vouw uw testgroepen uit totdat deze volledige productie hebben bereikt.</span><span class="sxs-lookup"><span data-stu-id="84769-108">Next, complete any additional configuration and expand your pilot groups until these have reached full production.</span></span> 

## <a name="microsoft-defender-for-identity"></a><span data-ttu-id="84769-109">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="84769-109">Microsoft Defender for Identity</span></span>
<span data-ttu-id="84769-110">Voor Defender voor identiteit is geen extra configuratie vereist.</span><span class="sxs-lookup"><span data-stu-id="84769-110">Defender for Identity doesn't require any additional configuration.</span></span> <span data-ttu-id="84769-111">Zorg ervoor dat u de benodigde licenties hebt gekocht en de sensor hebt geïnstalleerd op al uw Active Directory-domeincontrollers en AD FS-servers (Active Directory Federation Services).</span><span class="sxs-lookup"><span data-stu-id="84769-111">Just make sure you've purchased the necessary licenses and installed the sensor on all of your Active Directory domain controllers and Active Directory Federation Services (AD FS) servers.</span></span> 

## <a name="microsoft-defender-for-office-365"></a><span data-ttu-id="84769-112">Microsoft Defender voor Office 365</span><span class="sxs-lookup"><span data-stu-id="84769-112">Microsoft Defender for Office 365</span></span>
<span data-ttu-id="84769-113">Na het evalueren of piloten van MDO, kan deze worden gepromoveerd naar uw hele productieomgeving.</span><span class="sxs-lookup"><span data-stu-id="84769-113">After successfully evaluating or piloting MDO, it can be promoted to your entire production environment.</span></span>
1. <span data-ttu-id="84769-114">Koop en inrichten van de benodigde licenties en wijs deze toe aan uw productiegebruikers.</span><span class="sxs-lookup"><span data-stu-id="84769-114">Purchase and provision the necessary licenses and assign them to your production users.</span></span>
2. <span data-ttu-id="84769-115">Voer aanbevolen basislijnbeleidsconfiguraties (Standaard of Strikt) opnieuw uit op uw productie-e-maildomein of specifieke groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="84769-115">Re-run recommended baseline policy configurations (either Standard or Strict) against your production email domain or specific groups of users.</span></span>
3. <span data-ttu-id="84769-116">U kunt desgewenst aangepaste MDO-beleidsregels maken en configureren voor uw productie-e-maildomein of groepen gebruikers.</span><span class="sxs-lookup"><span data-stu-id="84769-116">Optionally create and configure any custom MDO policies against your production email domain or groups of users.</span></span>  <span data-ttu-id="84769-117">Houd er echter rekening mee dat toegewezen basislijnbeleid altijd voorrang heeft op aangepast beleid.</span><span class="sxs-lookup"><span data-stu-id="84769-117">However, remember that any assigned baseline policies will always take precedence over custom policies.</span></span>
4. <span data-ttu-id="84769-118">Werk de openbare MX-record voor uw productie-e-maildomein bij om rechtstreeks naar EOP op te lossen.</span><span class="sxs-lookup"><span data-stu-id="84769-118">Update the public MX record for your production email domain to resolve directly to EOP.</span></span>
5. <span data-ttu-id="84769-119">Schakel SMTP-gateways van derden uit en schakel ALLE EXO-connectors die aan dit relais zijn gekoppeld uit of verwijder deze uit.</span><span class="sxs-lookup"><span data-stu-id="84769-119">Decommission any third-party SMTP gateways and disable or delete any EXO connectors associated with this relay.</span></span>

## <a name="microsoft-defender-for-endpoint"></a><span data-ttu-id="84769-120">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="84769-120">Microsoft Defender for Endpoint</span></span>
<span data-ttu-id="84769-121">Als u de evaluatieomgeving van Microsoft Defender voor eindpunt wilt bevorderen van een pilot naar de productie, hoeft u alleen maar meer eindpunten aan te nemen bij de service met behulp van een van de ondersteunde [hulpprogramma's en methoden.](/defender-endpoint/onboard-configure)</span><span class="sxs-lookup"><span data-stu-id="84769-121">To promote Microsoft Defender for Endpoint evaluation environment from a pilot to production, simply onboard more endpoints to the service using any of the [supported tools and methods](/defender-endpoint/onboard-configure).</span></span>

<span data-ttu-id="84769-122">Gebruik de volgende algemene richtlijnen om meer apparaten aan te nemen bij Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="84769-122">Use the following general guidelines to onboard more devices to Microsoft Defender for Endpoint.</span></span> 

1. <span data-ttu-id="84769-123">Controleer of het apparaat aan de [minimumvereisten voldoet.](/defender-endpoint/minimum-requirements)</span><span class="sxs-lookup"><span data-stu-id="84769-123">Verify that the device fulfills the [minimum requirements](/defender-endpoint/minimum-requirements).</span></span>
2. <span data-ttu-id="84769-124">Volg, afhankelijk van het apparaat, de configuratiestappen in de onboarding-sectie van de Defender for Endpoint-portal.</span><span class="sxs-lookup"><span data-stu-id="84769-124">Depending on the device, follow the configuration steps provided in the onboarding section of the Defender for Endpoint portal.</span></span>
3. <span data-ttu-id="84769-125">Gebruik het juiste beheerprogramma en de implementatiemethode voor uw apparaten.</span><span class="sxs-lookup"><span data-stu-id="84769-125">Use the appropriate management tool and deployment method for your devices.</span></span>
4.  <span data-ttu-id="84769-126">Voer een detectietest uit om te controleren of de apparaten correct zijn onboarded en rapporteren aan de service.</span><span class="sxs-lookup"><span data-stu-id="84769-126">Run a detection test to verify that the devices are properly onboarded and reporting to the service.</span></span>

## <a name="microsoft-cloud-app-security"></a><span data-ttu-id="84769-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="84769-127">Microsoft Cloud App Security</span></span>
<span data-ttu-id="84769-128">Microsoft Cloud App Security vereist geen extra configuratie.</span><span class="sxs-lookup"><span data-stu-id="84769-128">Microsoft Cloud App Security doesn't require any additional configuration.</span></span> <span data-ttu-id="84769-129">Zorg ervoor dat u de benodigde licenties hebt gekocht.</span><span class="sxs-lookup"><span data-stu-id="84769-129">Just make sure you've purchased the necessary licenses.</span></span> <span data-ttu-id="84769-130">Als u de implementatie hebt gebereikt naar bepaalde gebruikersgroepen, vergroot u het bereik van deze groepen totdat u de productieschaal hebt bereikt.</span><span class="sxs-lookup"><span data-stu-id="84769-130">If you've scoped the deployment to certain user groups, increase the scope of these groups until you reach production scale.</span></span> 

