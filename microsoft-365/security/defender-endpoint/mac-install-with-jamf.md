---
title: Microsoft Defender ATP voor macOS implementeren met Jamf Pro
description: Microsoft Defender ATP voor macOS implementeren met Jamf Pro
keywords: microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a8015221f26250451a6cbcab8e66f35aafdc0767
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689706"
---
# <a name="deploying-microsoft-defender-for-endpoint-on-macos-with-jamf-pro"></a><span data-ttu-id="233bf-104">Microsoft Defender voor eindpunt implementeren in macOS met Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="233bf-104">Deploying Microsoft Defender for Endpoint on macOS with Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="233bf-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="233bf-105">**Applies to:**</span></span>
- [<span data-ttu-id="233bf-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="233bf-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="233bf-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="233bf-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="233bf-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="233bf-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="233bf-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="233bf-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="233bf-110">Meer informatie over het implementeren van Microsoft Defender voor Eindpunt in macOS met Jamf Pro.</span><span class="sxs-lookup"><span data-stu-id="233bf-110">Learn how to deploy Microsoft Defender for Endpoint on macOS with Jamf Pro.</span></span>

> [!NOTE]
> <span data-ttu-id="233bf-111">Zie Nieuwe configuratieprofielen voor [macOS Catalina](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies)en nieuwere versies van macOS als u macOS Catalina (10.15.4) of nieuwere versies van macOS gebruikt.</span><span class="sxs-lookup"><span data-stu-id="233bf-111">If you are using macOS Catalina (10.15.4) or newer versions of macOS, see [New configuration profiles for macOS Catalina and newer versions of macOS](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/mac-sysext-policies).</span></span>

<span data-ttu-id="233bf-112">Dit is een proces met meerdere stappen.</span><span class="sxs-lookup"><span data-stu-id="233bf-112">This is a multi step process.</span></span> <span data-ttu-id="233bf-113">U moet alle volgende stappen voltooien:</span><span class="sxs-lookup"><span data-stu-id="233bf-113">You'll need to complete all of the following steps:</span></span>

- [<span data-ttu-id="233bf-114">Aanmelden bij de Jamf-portal</span><span class="sxs-lookup"><span data-stu-id="233bf-114">Login to the Jamf Portal</span></span>](mac-install-jamfpro-login.md)
- [<span data-ttu-id="233bf-115">Microsoft Defender voor eindpunt instellen voor macOS-apparaatgroepen in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="233bf-115">Setup the Microsoft Defender for Endpoint on macOS device groups in Jamf Pro</span></span>](mac-jamfpro-device-groups.md)
- [<span data-ttu-id="233bf-116">Microsoft Defender voor Eindpunt instellen voor macOS-beleid in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="233bf-116">Setup the Microsoft Defender for Endpoint on macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
- [<span data-ttu-id="233bf-117">Het Microsoft Defender voor eindpunt op macOS-apparaten registreren bij Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="233bf-117">Enroll the Microsoft Defender for Endpoint on macOS devices into Jamf Pro</span></span>](mac-jamfpro-enroll-devices.md)




