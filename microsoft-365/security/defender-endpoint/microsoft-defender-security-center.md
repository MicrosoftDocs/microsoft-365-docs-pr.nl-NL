---
title: Microsoft Defender-beveiligingscentrum
description: Microsoft Defender Security Center is de portal waar u toegang hebt tot Microsoft Defender voor Eindpunt.
keywords: windows, defender, security, center, defender, advanced, threat, protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 521c24c24ecc46c81f74e0bab28642aaf581274d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057049"
---
# <a name="microsoft-defender-security-center"></a><span data-ttu-id="671da-104">Microsoft Defender-beveiligingscentrum</span><span class="sxs-lookup"><span data-stu-id="671da-104">Microsoft Defender Security Center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="671da-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="671da-105">**Applies to:**</span></span>
- [<span data-ttu-id="671da-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="671da-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="671da-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="671da-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="671da-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="671da-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="671da-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="671da-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="671da-110">Microsoft Defender Security Center is de portal waar u toegang hebt tot Microsoft Defender voor endpoint-mogelijkheden.</span><span class="sxs-lookup"><span data-stu-id="671da-110">Microsoft Defender Security Center is the portal where you can access Microsoft Defender for Endpoint capabilities.</span></span> <span data-ttu-id="671da-111">Het biedt teams voor bedrijfsbeveiligingsbewerkingen één glaservaring om netwerken te beveiligen.</span><span class="sxs-lookup"><span data-stu-id="671da-111">It gives enterprise security operations teams a single pane of glass experience to help secure networks.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="671da-112">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="671da-112">In this section</span></span>

<span data-ttu-id="671da-113">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="671da-113">Topic</span></span> | <span data-ttu-id="671da-114">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="671da-114">Description</span></span>
:---|:---
<span data-ttu-id="671da-115">Aan de slag</span><span class="sxs-lookup"><span data-stu-id="671da-115">Get started</span></span>  |  <span data-ttu-id="671da-116">Meer informatie over de minimumvereisten, het valideren van licenties en de volledige installatie, meer informatie over voorbeeldfuncties, informatie over gegevensopslag en privacy en hoe u gebruikerstoegang aan de portal kunt toewijzen.</span><span class="sxs-lookup"><span data-stu-id="671da-116">Learn about the minimum requirements, validate licensing and complete setup, know about preview features, understand data storage and privacy, and how to assign user access to the portal.</span></span>
[<span data-ttu-id="671da-117">Onboard-apparaten</span><span class="sxs-lookup"><span data-stu-id="671da-117">Onboard devices</span></span>](onboard-configure.md) | <span data-ttu-id="671da-118">Meer informatie over onboardingclient, server en niet-Windows-apparaten.</span><span class="sxs-lookup"><span data-stu-id="671da-118">Learn about onboarding client, server, and non-Windows devices.</span></span> <span data-ttu-id="671da-119">Meer informatie over het uitvoeren van een detectietest, het configureren van proxy- en internetverbindingsinstellingen en het oplossen van mogelijke onboarding-problemen.</span><span class="sxs-lookup"><span data-stu-id="671da-119">Learn how to run a detection test, configure proxy and Internet connectivity settings, and how to troubleshoot potential onboarding issues.</span></span>
[<span data-ttu-id="671da-120">De portal begrijpen</span><span class="sxs-lookup"><span data-stu-id="671da-120">Understand the portal</span></span>](use.md) | <span data-ttu-id="671da-121">Meer informatie over de beveiligingsbewerkingen, secure score en bedreigingsanalysedashboards en hoe u door de portal kunt navigeren.</span><span class="sxs-lookup"><span data-stu-id="671da-121">Understand the Security operations, Secure Score, and Threat analytics dashboards as well as how to navigate the portal.</span></span>
<span data-ttu-id="671da-122">Bedreigingen onderzoeken en corrigeren</span><span class="sxs-lookup"><span data-stu-id="671da-122">Investigate and remediate threats</span></span> | <span data-ttu-id="671da-123">Onderzoek waarschuwingen, apparaten en neem antwoordacties om bedreigingen te verhelpen.</span><span class="sxs-lookup"><span data-stu-id="671da-123">Investigate alerts, devices, and take response actions to remediate threats.</span></span>
<span data-ttu-id="671da-124">API- en SIEM-ondersteuning</span><span class="sxs-lookup"><span data-stu-id="671da-124">API and SIEM support</span></span> | <span data-ttu-id="671da-125">Gebruik de ondersteunde API's om aangepaste waarschuwingen op te halen en te maken of werkstromen te automatiseren.</span><span class="sxs-lookup"><span data-stu-id="671da-125">Use the supported APIs to pull and create custom alerts, or automate workflows.</span></span> <span data-ttu-id="671da-126">Gebruik de ondersteunde SIEM-hulpprogramma's om waarschuwingen op te halen bij het Microsoft Defender-beveiligingscentrum.</span><span class="sxs-lookup"><span data-stu-id="671da-126">Use the supported SIEM tools to pull alerts from Microsoft Defender Security Center.</span></span>
<span data-ttu-id="671da-127">Rapportage</span><span class="sxs-lookup"><span data-stu-id="671da-127">Reporting</span></span> | <span data-ttu-id="671da-128">Power BI-rapporten maken en maken met Microsoft Defender voor eindpuntgegevens.</span><span class="sxs-lookup"><span data-stu-id="671da-128">Create and build Power BI reports using Microsoft Defender for Endpoint data.</span></span>
<span data-ttu-id="671da-129">Status van service en sensor controleren</span><span class="sxs-lookup"><span data-stu-id="671da-129">Check service health and sensor state</span></span> | <span data-ttu-id="671da-130">Controleer of de service wordt uitgevoerd en controleer de sensortoestand op apparaten.</span><span class="sxs-lookup"><span data-stu-id="671da-130">Verify that the service is running and check the sensor state on devices.</span></span>
[<span data-ttu-id="671da-131">Instellingen van het Microsoft Defender-beveiligingscentrum configureren</span><span class="sxs-lookup"><span data-stu-id="671da-131">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="671da-132">Configureer algemene instellingen, schakel de preview-ervaring in, meldingen en schakel andere functies in.</span><span class="sxs-lookup"><span data-stu-id="671da-132">Configure general settings, turn on the preview experience, notifications, and enable other features.</span></span>
[<span data-ttu-id="671da-133">Toegang tot het Microsoft Defender for Endpoint Community Center</span><span class="sxs-lookup"><span data-stu-id="671da-133">Access the Microsoft Defender for Endpoint Community Center</span></span>](community.md) | <span data-ttu-id="671da-134">Toegang tot het Microsoft Defender for Endpoint Community Center voor meer informatie, samenwerking en het delen van ervaringen over het product.</span><span class="sxs-lookup"><span data-stu-id="671da-134">Access the Microsoft Defender for Endpoint Community Center to learn, collaborate, and share experiences about the product.</span></span>
[<span data-ttu-id="671da-135">Problemen met de service oplossen</span><span class="sxs-lookup"><span data-stu-id="671da-135">Troubleshoot service issues</span></span>](troubleshoot-mdatp.md) | <span data-ttu-id="671da-136">In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft Defender voor Eindpunt-service gebruikt.</span><span class="sxs-lookup"><span data-stu-id="671da-136">This section addresses issues that might arise as you use the Microsoft Defender for Endpoint service.</span></span>