---
title: Problemen met Microsoft Defender voor Eindpunt op Android oplossen
description: Problemen oplossen voor Microsoft Defender voor Eindpunt op Android
keywords: microsoft, defender, Microsoft Defender voor Eindpunt, mde, android, cloud, connectiviteit, communicatie
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5f57d14427ef68280a065489e068955db9e5045a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934799"
---
# <a name="troubleshooting-issues-on-microsoft-defender-for-endpoint-on-android"></a><span data-ttu-id="e8c8d-104">Problemen met Microsoft Defender voor Eindpunt op Android oplossen</span><span class="sxs-lookup"><span data-stu-id="e8c8d-104">Troubleshooting issues on Microsoft Defender for Endpoint on Android</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e8c8d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-105">**Applies to:**</span></span>
- [<span data-ttu-id="e8c8d-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e8c8d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e8c8d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e8c8d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e8c8d-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e8c8d-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e8c8d-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

<span data-ttu-id="e8c8d-110">Wanneer u een apparaat onboardt, ziet u mogelijk aanmeldingsproblemen nadat de app is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-110">When onboarding a device, you might see sign in issues after the app is installed.</span></span>

<span data-ttu-id="e8c8d-111">Tijdens onboarding kunt u problemen ondervinden bij het aanmelden nadat de app op uw apparaat is geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-111">During onboarding, you might encounter sign in issues after the app is installed on your device.</span></span>

<span data-ttu-id="e8c8d-112">In dit artikel vindt u oplossingen voor het oplossen van aanmeldingsproblemen.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-112">This article provides solutions to help address the sign-on issues.</span></span>  

## <a name="sign-in-failed---unexpected-error"></a><span data-ttu-id="e8c8d-113">Aanmelden mislukt - onverwachte fout</span><span class="sxs-lookup"><span data-stu-id="e8c8d-113">Sign in failed - unexpected error</span></span>
<span data-ttu-id="e8c8d-114">**Aanmelden is mislukt: Onverwachte** *fout, probeer het later*</span><span class="sxs-lookup"><span data-stu-id="e8c8d-114">**Sign in failed:** *Unexpected error, try later*</span></span>

![Afbeelding van fout bij aanmelden mislukt Onverwachte fout](images/f9c3bad127d636c1f150d79814f35d4c.png)

<span data-ttu-id="e8c8d-116">**Bericht:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-116">**Message:**</span></span>

<span data-ttu-id="e8c8d-117">Onverwachte fout, probeer het later</span><span class="sxs-lookup"><span data-stu-id="e8c8d-117">Unexpected error, try later</span></span>

<span data-ttu-id="e8c8d-118">**Oorzaak:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-118">**Cause:**</span></span>

<span data-ttu-id="e8c8d-119">Er is een oudere versie van de App Microsoft Authenticator op uw apparaat geïnstalleerd.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-119">You have an older version of "Microsoft Authenticator" app installed on your device.</span></span>

<span data-ttu-id="e8c8d-120">**Oplossing:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-120">**Solution:**</span></span>

<span data-ttu-id="e8c8d-121">De nieuwste versie en [Microsoft Authenticator installeren](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) vanuit de Google Play Store en het opnieuw proberen</span><span class="sxs-lookup"><span data-stu-id="e8c8d-121">Install latest version and of [Microsoft Authenticator](https://play.google.com/store/apps/details?androidid=com.azure.authenticator) from Google Play Store and try again</span></span>

## <a name="sign-in-failed---invalid-license"></a><span data-ttu-id="e8c8d-122">Aanmelden mislukt - ongeldige licentie</span><span class="sxs-lookup"><span data-stu-id="e8c8d-122">Sign in failed - invalid license</span></span>

<span data-ttu-id="e8c8d-123">**Aanmelden mislukt:** *Ongeldige licentie, neem contact op met beheerder*</span><span class="sxs-lookup"><span data-stu-id="e8c8d-123">**Sign in failed:** *Invalid license, please contact administrator*</span></span>

![Afbeelding van aanmelden mislukt neem contact op met beheerder](images/920e433f440fa1d3d298e6a2a43d4811.png)

<span data-ttu-id="e8c8d-125">**Bericht:** *Ongeldige licentie, neem contact op met de beheerder*</span><span class="sxs-lookup"><span data-stu-id="e8c8d-125">**Message:** *Invalid license, please contact administrator*</span></span>

<span data-ttu-id="e8c8d-126">**Oorzaak:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-126">**Cause:**</span></span>

<span data-ttu-id="e8c8d-127">U hebt geen Microsoft 365-licentie toegewezen of uw organisatie heeft geen licentie voor microsoft 365 Enterprise-abonnement.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-127">You do not have Microsoft 365 license assigned, or your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="e8c8d-128">**Oplossing:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-128">**Solution:**</span></span>

<span data-ttu-id="e8c8d-129">Neem contact op met uw beheerder voor hulp.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-129">Contact your administrator for help.</span></span>

## <a name="phishing-pages-arent-blocked-on-some-oem-devices"></a><span data-ttu-id="e8c8d-130">Phishingpagina's worden niet geblokkeerd op sommige OEM-apparaten</span><span class="sxs-lookup"><span data-stu-id="e8c8d-130">Phishing pages aren't blocked on some OEM devices</span></span>

<span data-ttu-id="e8c8d-131">**Van toepassing op:** Alleen specifieke OEM's</span><span class="sxs-lookup"><span data-stu-id="e8c8d-131">**Applies to:** Specific OEMs only</span></span>

-   <span data-ttu-id="e8c8d-132">**Xiaomi**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-132">**Xiaomi**</span></span>

<span data-ttu-id="e8c8d-133">Phishing en schadelijke webbedreigingen die worden gedetecteerd door Defender voor Eindpunt voor Android, worden niet geblokkeerd op sommige Xiaomi-apparaten.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-133">Phishing and harmful web threats that are detected by Defender for Endpoint for Android are not blocked on some Xiaomi devices.</span></span> <span data-ttu-id="e8c8d-134">De volgende functionaliteit werkt niet op deze apparaten.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-134">The following functionality doesn't work on these devices.</span></span>

![Afbeelding van site die onveilig is gerapporteerd](images/0c04975c74746a5cdb085e1d9386e713.png)


<span data-ttu-id="e8c8d-136">**Oorzaak:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-136">**Cause:**</span></span>

<span data-ttu-id="e8c8d-137">Xiaomi-apparaten bevatten een nieuw machtigingsmodel.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-137">Xiaomi devices include a new permission model.</span></span> <span data-ttu-id="e8c8d-138">Hierdoor wordt voorkomen dat in Defender voor Eindpunt voor Android pop-upvensters worden weergegeven terwijl deze op de achtergrond wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-138">This prevents Defender for Endpoint for Android from displaying pop-up windows while it runs in the background.</span></span>

<span data-ttu-id="e8c8d-139">Machtiging voor Xiaomi-apparaten: 'Pop-upvensters weergeven terwijl u op de achtergrond werkt'.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-139">Xiaomi devices permission: "Display pop-up windows while running in the background."</span></span>

![Afbeelding van pop-upinstelling](images/6e48e7b29daf50afddcc6c8c7d59fd64.png)

<span data-ttu-id="e8c8d-141">**Oplossing:**</span><span class="sxs-lookup"><span data-stu-id="e8c8d-141">**Solution:**</span></span>

<span data-ttu-id="e8c8d-142">Schakel de vereiste machtiging in op Xiaomi-apparaten.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-142">Enable the required permission on Xiaomi devices.</span></span>

- <span data-ttu-id="e8c8d-143">Pop-upvensters weergeven terwijl deze op de achtergrond worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="e8c8d-143">Display pop-up windows while running in the background.</span></span>
