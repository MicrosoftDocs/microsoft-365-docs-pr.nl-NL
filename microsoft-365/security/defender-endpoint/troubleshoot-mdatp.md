---
title: Problemen met de Microsoft Defender-service oplossen
description: Zoek oplossingen en werk rond voor bekende problemen, zoals serverfouten wanneer u toegang probeert te krijgen tot de service.
keywords: problemen met Microsoft Defender voor eindpunt oplossen, problemen met Windows ATP oplossen, serverfout, toegang geweigerd, ongeldige referenties, geen gegevens, dashboardportal, toestaan, gebeurtenisviewer
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: bd211a56ee9ed6aa871c8d55149247a4755bc863
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51058694"
---
# <a name="troubleshoot-service-issues"></a><span data-ttu-id="7f97b-104">Problemen met de service oplossen</span><span class="sxs-lookup"><span data-stu-id="7f97b-104">Troubleshoot service issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="7f97b-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7f97b-105">**Applies to:**</span></span>
- [<span data-ttu-id="7f97b-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="7f97b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7f97b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7f97b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7f97b-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7f97b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7f97b-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7f97b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="7f97b-110">In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft Defender Advanced Threat-service gebruikt.</span><span class="sxs-lookup"><span data-stu-id="7f97b-110">This section addresses issues that might arise as you use the Microsoft Defender Advanced Threat service.</span></span>

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a><span data-ttu-id="7f97b-111">Serverfout : Access wordt geweigerd vanwege ongeldige referenties</span><span class="sxs-lookup"><span data-stu-id="7f97b-111">Server error - Access is denied due to invalid credentials</span></span>
<span data-ttu-id="7f97b-112">Als u een serverfout ondervindt wanneer u toegang probeert te krijgen tot de service, moet u de cookie-instellingen van uw browser wijzigen.</span><span class="sxs-lookup"><span data-stu-id="7f97b-112">If you encounter a server error when trying to access the service, you’ll need to change your browser cookie settings.</span></span>
<span data-ttu-id="7f97b-113">Configureer uw browser om cookies toe te staan.</span><span class="sxs-lookup"><span data-stu-id="7f97b-113">Configure your browser to allow cookies.</span></span>

## <a name="elements-or-data-missing-on-the-portal"></a><span data-ttu-id="7f97b-114">Elementen of gegevens ontbreken in de portal</span><span class="sxs-lookup"><span data-stu-id="7f97b-114">Elements or data missing on the portal</span></span>
<span data-ttu-id="7f97b-115">Als bepaalde elementen of gegevens van de gebruikersinterface ontbreken in het Microsoft Defender-beveiligingscentrum, is het mogelijk dat proxy-instellingen deze blokkeren.</span><span class="sxs-lookup"><span data-stu-id="7f97b-115">If some UI elements or data is missing on Microsoft Defender Security Center it’s possible that proxy settings are blocking it.</span></span>

<span data-ttu-id="7f97b-116">Zorg ervoor dat `*.securitycenter.windows.com` de lijst proxy toestaan is opgenomen.</span><span class="sxs-lookup"><span data-stu-id="7f97b-116">Make sure that `*.securitycenter.windows.com` is included the proxy allow list.</span></span>


> [!NOTE]
> <span data-ttu-id="7f97b-117">U moet het HTTPS-protocol gebruiken bij het toevoegen van de volgende eindpunten.</span><span class="sxs-lookup"><span data-stu-id="7f97b-117">You must use the HTTPS protocol when adding the following endpoints.</span></span>

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a><span data-ttu-id="7f97b-118">Microsoft Defender for Endpoint-service toont gebeurtenis- of foutlogboeken in de Viewer voor gebeurtenissen</span><span class="sxs-lookup"><span data-stu-id="7f97b-118">Microsoft Defender for Endpoint service shows event or error logs in the Event Viewer</span></span>

<span data-ttu-id="7f97b-119">Zie het onderwerp [Gebeurtenissen en fouten controleren met Behulp](event-error-codes.md) van Gebeurtenisviewer voor een lijst met gebeurtenis-ID's die worden gerapporteerd door de Microsoft Defender voor Eindpunt-service.</span><span class="sxs-lookup"><span data-stu-id="7f97b-119">See the topic [Review events and errors using Event Viewer](event-error-codes.md) for a list of event IDs that are reported by the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="7f97b-120">Het onderwerp bevat ook stappen voor het oplossen van problemen met gebeurtenisfouten.</span><span class="sxs-lookup"><span data-stu-id="7f97b-120">The topic also contains troubleshooting steps for event errors.</span></span>

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a><span data-ttu-id="7f97b-121">Microsoft Defender for Endpoint-service kan niet starten na een herstart en geeft fout 577 weer</span><span class="sxs-lookup"><span data-stu-id="7f97b-121">Microsoft Defender for Endpoint service fails to start after a reboot and shows error 577</span></span>

<span data-ttu-id="7f97b-122">Als onboarding-apparaten zijn voltooid, maar Microsoft Defender voor Eindpunt niet start na een herstart en fout 577 wordt weergegeven, controleert u of Windows Defender niet is uitgeschakeld door een beleid.</span><span class="sxs-lookup"><span data-stu-id="7f97b-122">If onboarding devices successfully completes but Microsoft Defender for Endpoint does not start after a reboot and shows error 577, check that Windows Defender is not disabled by a policy.</span></span>

<span data-ttu-id="7f97b-123">Zie Ervoor zorgen dat [Microsoft Defender Antivirus niet is uitgeschakeld door beleid voor meer informatie.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)</span><span class="sxs-lookup"><span data-stu-id="7f97b-123">For more information, see [Ensure that Microsoft Defender Antivirus is not disabled by policy](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy).</span></span>

## <a name="known-issues-with-regional-formats"></a><span data-ttu-id="7f97b-124">Bekende problemen met regionale indelingen</span><span class="sxs-lookup"><span data-stu-id="7f97b-124">Known issues with regional formats</span></span>

<span data-ttu-id="7f97b-125">**Datum- en tijdnotaties**</span><span class="sxs-lookup"><span data-stu-id="7f97b-125">**Date and time formats**</span></span><br>
<span data-ttu-id="7f97b-126">Er zijn enkele bekende problemen met de tijd- en datumnotatie.</span><span class="sxs-lookup"><span data-stu-id="7f97b-126">There are some known issues with the time and date formats.</span></span> 

<span data-ttu-id="7f97b-127">De volgende datumnotaaties worden ondersteund:</span><span class="sxs-lookup"><span data-stu-id="7f97b-127">The following date formats are supported:</span></span>
- <span data-ttu-id="7f97b-128">MM/dd/yyyy</span><span class="sxs-lookup"><span data-stu-id="7f97b-128">MM/dd/yyyy</span></span>
- <span data-ttu-id="7f97b-129">dd/MM/yyyy</span><span class="sxs-lookup"><span data-stu-id="7f97b-129">dd/MM/yyyy</span></span>

<span data-ttu-id="7f97b-130">De volgende datum- en tijdindelingen worden momenteel niet ondersteund:</span><span class="sxs-lookup"><span data-stu-id="7f97b-130">The following date and time formats are currently not supported:</span></span>
- <span data-ttu-id="7f97b-131">Datumnotatie yyy/MM/dd</span><span class="sxs-lookup"><span data-stu-id="7f97b-131">Date format yyyy/MM/dd</span></span>
- <span data-ttu-id="7f97b-132">Datumnotatie dd/MM/yy</span><span class="sxs-lookup"><span data-stu-id="7f97b-132">Date format dd/MM/yy</span></span>
- <span data-ttu-id="7f97b-133">Datumnotatie met yy.</span><span class="sxs-lookup"><span data-stu-id="7f97b-133">Date format with yy.</span></span> <span data-ttu-id="7f97b-134">Toont alleen yyyy.</span><span class="sxs-lookup"><span data-stu-id="7f97b-134">Will only show yyyy.</span></span>
- <span data-ttu-id="7f97b-135">Tijdnotatie HH:mm:ss wordt niet ondersteund (de notatie 12 uur am/PM wordt niet ondersteund).</span><span class="sxs-lookup"><span data-stu-id="7f97b-135">Time format HH:mm:ss is not supported (the 12 hour AM/PM format is not supported).</span></span> <span data-ttu-id="7f97b-136">Alleen de 24-uursindeling wordt ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7f97b-136">Only the 24-hour format is supported.</span></span>

<span data-ttu-id="7f97b-137">**Gebruik van komma's om duizend aan te geven**</span><span class="sxs-lookup"><span data-stu-id="7f97b-137">**Use of comma to indicate thousand**</span></span><br>
<span data-ttu-id="7f97b-138">Ondersteuning voor het gebruik van komma's als scheidingsteken in getallen wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="7f97b-138">Support of use of comma as a separator in numbers are not supported.</span></span> <span data-ttu-id="7f97b-139">Regio's waar een getal wordt gescheiden met een komma om duizend aan te geven, zien alleen het gebruik van een punt als scheidingsteken.</span><span class="sxs-lookup"><span data-stu-id="7f97b-139">Regions where a number is separated with a comma to indicate a thousand, will only see the use of a dot as a separator.</span></span> <span data-ttu-id="7f97b-140">15,5K wordt bijvoorbeeld weergegeven als 15,5K.</span><span class="sxs-lookup"><span data-stu-id="7f97b-140">For example, 15,5K is displayed as 15.5K.</span></span>

><span data-ttu-id="7f97b-141">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7f97b-141">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7f97b-142">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7f97b-142">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a><span data-ttu-id="7f97b-143">Microsoft Defender voor Eindpunt-tenant is automatisch gemaakt in Europa</span><span class="sxs-lookup"><span data-stu-id="7f97b-143">Microsoft Defender for Endpoint tenant was automatically created in Europe</span></span>
<span data-ttu-id="7f97b-144">Wanneer u Azure Security Center gebruikt om servers te controleren, wordt automatisch een Microsoft Defender voor Eindpunt-tenant gemaakt.</span><span class="sxs-lookup"><span data-stu-id="7f97b-144">When you use Azure Security Center to monitor servers, a Microsoft Defender for Endpoint tenant is automatically created.</span></span> <span data-ttu-id="7f97b-145">De Gegevens van Microsoft Defender voor eindpunten worden standaard opgeslagen in Europa.</span><span class="sxs-lookup"><span data-stu-id="7f97b-145">The Microsoft Defender for Endpoint data is stored in Europe by default.</span></span>





## <a name="related-topics"></a><span data-ttu-id="7f97b-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="7f97b-146">Related topics</span></span>
- [<span data-ttu-id="7f97b-147">Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen</span><span class="sxs-lookup"><span data-stu-id="7f97b-147">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
- [<span data-ttu-id="7f97b-148">Gebeurtenissen en fouten controleren met Behulp van Gebeurtenisviewer</span><span class="sxs-lookup"><span data-stu-id="7f97b-148">Review events and errors using Event Viewer</span></span>](event-error-codes.md)
