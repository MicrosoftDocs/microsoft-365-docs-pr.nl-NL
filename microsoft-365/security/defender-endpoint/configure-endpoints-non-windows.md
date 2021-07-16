---
title: Niet-Windows aan boord van de Microsoft Defender for Endpoint-service
description: Configureer niet-Windows apparaten zodat ze sensorgegevens kunnen verzenden naar de Microsoft Defender for Endpoint-service.
keywords: onboard non-Windows devices, macos, linux, device management, configure Microsoft Defender for Endpoint devices
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4aff505f9f35b6144360eed5992ac36cf0847617
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454707"
---
# <a name="onboard-non-windows-devices"></a><span data-ttu-id="2807c-104">Niet-Windows-apparaten onboarden</span><span class="sxs-lookup"><span data-stu-id="2807c-104">Onboard non-Windows devices</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2807c-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="2807c-105">**Applies to:**</span></span>
- [<span data-ttu-id="2807c-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="2807c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2807c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2807c-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="2807c-108">**Platforms**</span><span class="sxs-lookup"><span data-stu-id="2807c-108">**Platforms**</span></span>
- <span data-ttu-id="2807c-109">macOS</span><span class="sxs-lookup"><span data-stu-id="2807c-109">macOS</span></span>
- <span data-ttu-id="2807c-110">Linux</span><span class="sxs-lookup"><span data-stu-id="2807c-110">Linux</span></span>

><span data-ttu-id="2807c-111">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="2807c-111">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="2807c-112">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="2807c-112">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-nonwindows-abovefoldlink) 

<span data-ttu-id="2807c-113">Defender voor Eindpunt biedt een gecentraliseerde beveiligingsbewerkingservaring voor Windows en niet-Windows platforms.</span><span class="sxs-lookup"><span data-stu-id="2807c-113">Defender for Endpoint provides a centralized security operations experience for Windows as well as non-Windows platforms.</span></span> <span data-ttu-id="2807c-114">U kunt waarschuwingen van verschillende ondersteunde besturingssystemen (OS) zien in Microsoft 365 Defender en het netwerk van uw organisatie beter beveiligen.</span><span class="sxs-lookup"><span data-stu-id="2807c-114">You'll be able to see alerts from various supported operating systems (OS) in Microsoft 365 Defender and better protect your organization's network.</span></span> 

<span data-ttu-id="2807c-115">U moet de exacte Linux-distributies en macOS-versies kennen die compatibel zijn met Defender voor Eindpunt om de integratie te laten werken.</span><span class="sxs-lookup"><span data-stu-id="2807c-115">You'll need to know the exact Linux distros and macOS versions that are compatible with Defender for Endpoint for the integration to work.</span></span> <span data-ttu-id="2807c-116">Zie voor meer informatie:</span><span class="sxs-lookup"><span data-stu-id="2807c-116">For more information, see:</span></span>
- [<span data-ttu-id="2807c-117">Microsoft Defender for Endpoint on Linux system requirements</span><span class="sxs-lookup"><span data-stu-id="2807c-117">Microsoft Defender for Endpoint on Linux system requirements</span></span>](microsoft-defender-endpoint-linux.md#system-requirements)  
- <span data-ttu-id="2807c-118">[Microsoft Defender voor Eindpunt voor systeemvereisten voor macOS](microsoft-defender-endpoint-mac.md#system-requirements).</span><span class="sxs-lookup"><span data-stu-id="2807c-118">[Microsoft Defender for Endpoint on macOS system requirements](microsoft-defender-endpoint-mac.md#system-requirements).</span></span>

## <a name="onboarding-non-windows-devices"></a><span data-ttu-id="2807c-119">Onboarding van niet-Windows apparaten</span><span class="sxs-lookup"><span data-stu-id="2807c-119">Onboarding non-Windows devices</span></span>
<span data-ttu-id="2807c-120">U moet de volgende stappen ondernemen om niet-Windows in te stappen:</span><span class="sxs-lookup"><span data-stu-id="2807c-120">You'll need to take the following steps to onboard non-Windows devices:</span></span>
1. <span data-ttu-id="2807c-121">Selecteer uw voorkeursmethode voor onboarding:</span><span class="sxs-lookup"><span data-stu-id="2807c-121">Select your preferred method of onboarding:</span></span>

   - <span data-ttu-id="2807c-122">Voor macOS-apparaten kunt u ervoor kiezen om aan boord te gaan via Microsoft Defender voor Eindpunt of via een oplossing van derden.</span><span class="sxs-lookup"><span data-stu-id="2807c-122">For macOS devices, you can choose to onboard through Microsoft Defender for Endpoint or through a third-party solution.</span></span> <span data-ttu-id="2807c-123">Zie Microsoft Defender voor Eindpunt op Mac voor [meer informatie.](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac)</span><span class="sxs-lookup"><span data-stu-id="2807c-123">For more information, see [Microsoft Defender for Endpoint on Mac](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint-mac).</span></span>

   - <span data-ttu-id="2807c-124">Voor andere niet-Windows-apparaten kiest u **Onboard niet-Windows** apparaten via integratie van derden.</span><span class="sxs-lookup"><span data-stu-id="2807c-124">For other non-Windows devices, choose **Onboard non-Windows devices through third-party integration**.</span></span>   
    1. <span data-ttu-id="2807c-125">Selecteer in het navigatiedeelvenster **Interoperabiliteitspartners.**  >  </span><span class="sxs-lookup"><span data-stu-id="2807c-125">In the navigation pane, select **Interoperability** > **Partners**.</span></span> <span data-ttu-id="2807c-126">Zorg ervoor dat de oplossing van derden wordt vermeld.</span><span class="sxs-lookup"><span data-stu-id="2807c-126">Make sure the third-party solution is listed.</span></span>
    2. <span data-ttu-id="2807c-127">Selecteer op **het tabblad Partnertoepassingen** de partner die uw niet-Windows ondersteunt.</span><span class="sxs-lookup"><span data-stu-id="2807c-127">In the **Partner Applications** tab, select the partner that supports your non-Windows devices.</span></span>
    3. <span data-ttu-id="2807c-128">Selecteer **Partnerpagina openen om** de pagina van de partner te openen.</span><span class="sxs-lookup"><span data-stu-id="2807c-128">Select **Open partner page** to open the partner's page.</span></span> <span data-ttu-id="2807c-129">Volg de instructies op de pagina.</span><span class="sxs-lookup"><span data-stu-id="2807c-129">Follow the instructions provided on the page.</span></span>
    4. <span data-ttu-id="2807c-130">Nadat u een account hebt gemaakt of een abonnement hebt genomen op de partneroplossing, moet u naar een fase gaan waarin een globale tenantbeheerder in uw organisatie wordt gevraagd een machtigingsaanvraag van de partnertoepassing te accepteren.</span><span class="sxs-lookup"><span data-stu-id="2807c-130">After creating an account or subscribing to the partner solution, you should get to a stage where a tenant Global Admin in your organization is asked to accept a permission request from the partner application.</span></span> <span data-ttu-id="2807c-131">Lees de machtigingsaanvraag zorgvuldig door om ervoor te zorgen dat het is uitgelijnd met de service die u nodig hebt.</span><span class="sxs-lookup"><span data-stu-id="2807c-131">Read the permission request carefully to make sure that it is aligned with the service that you require.</span></span> 

        
2. <span data-ttu-id="2807c-132">Voer een detectietest uit door de instructies van de oplossing van derden te volgen.</span><span class="sxs-lookup"><span data-stu-id="2807c-132">Run a detection test by following the instructions of the third-party solution.</span></span>

## <a name="offboard-non-windows-devices"></a><span data-ttu-id="2807c-133">Niet-offboard-Windows apparaten</span><span class="sxs-lookup"><span data-stu-id="2807c-133">Offboard non-Windows devices</span></span>

1. <span data-ttu-id="2807c-134">Volg de documentatie van derden om de externe oplossing los te koppelen van Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="2807c-134">Follow the third-party's documentation to disconnect the third-party solution from Microsoft Defender for Endpoint.</span></span>

2. <span data-ttu-id="2807c-135">Verwijder machtigingen voor de oplossing van derden in uw Azure AD-tenant.</span><span class="sxs-lookup"><span data-stu-id="2807c-135">Remove permissions for the third-party solution in your Azure AD tenant.</span></span>
   1. <span data-ttu-id="2807c-136">Meld u aan bij [Azure Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="2807c-136">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
   2. <span data-ttu-id="2807c-137">Selecteer **Azure Active Directory > Enterprise Applications**.</span><span class="sxs-lookup"><span data-stu-id="2807c-137">Select **Azure Active Directory > Enterprise Applications**.</span></span>
   3. <span data-ttu-id="2807c-138">Selecteer de toepassing die u wilt offboarden.</span><span class="sxs-lookup"><span data-stu-id="2807c-138">Select the application you'd like to offboard.</span></span>
   4. <span data-ttu-id="2807c-139">Selecteer de **knop** Verwijderen.</span><span class="sxs-lookup"><span data-stu-id="2807c-139">Select the **Delete** button.</span></span>


## <a name="related-topics"></a><span data-ttu-id="2807c-140">Gerelateerde onderwerpen</span><span class="sxs-lookup"><span data-stu-id="2807c-140">Related topics</span></span>
- [<span data-ttu-id="2807c-141">Onboarden Windows 10-apparaten</span><span class="sxs-lookup"><span data-stu-id="2807c-141">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="2807c-142">Onboard-servers</span><span class="sxs-lookup"><span data-stu-id="2807c-142">Onboard servers</span></span>](configure-server-endpoints.md)
- [<span data-ttu-id="2807c-143">Proxy- en internetconnectiviteitsinstellingen configureren</span><span class="sxs-lookup"><span data-stu-id="2807c-143">Configure proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="2807c-144">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="2807c-144">Troubleshooting Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
