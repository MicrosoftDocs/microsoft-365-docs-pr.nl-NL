---
title: Problemen met licenties oplossen voor Microsoft Defender ATP voor Mac
description: Problemen met licenties oplossen in Microsoft Defender ATP voor Mac.
keywords: microsoft, defender, atp, mac, performance
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
ms.openlocfilehash: 69dd85394837bb7f37e7d277110c8a5dbf7b6506
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689111"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="df625-104">Problemen met licenties oplossen voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="df625-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="df625-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="df625-105">**Applies to:**</span></span>

- [<span data-ttu-id="df625-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="df625-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="df625-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="df625-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="df625-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df625-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="df625-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="df625-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="df625-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="df625-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="df625-111">Terwijl u door Microsoft Defender voor Eindpunt [](mac-install-manually.md) op [macOS](microsoft-defender-endpoint-mac.md) en Handmatige implementatietests of een Proof Of Concept (PoC) gaat, krijgt u mogelijk de volgende foutmelding:</span><span class="sxs-lookup"><span data-stu-id="df625-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Afbeelding van licentiefout](images/no-license-found.png)

<span data-ttu-id="df625-113">**Bericht:**</span><span class="sxs-lookup"><span data-stu-id="df625-113">**Message:**</span></span> 

<span data-ttu-id="df625-114">Geen licentie gevonden</span><span class="sxs-lookup"><span data-stu-id="df625-114">No license found</span></span>

<span data-ttu-id="df625-115">Het lijkt erop dat uw organisatie geen licentie voor Microsoft 365 Enterprise-abonnement heeft.</span><span class="sxs-lookup"><span data-stu-id="df625-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="df625-116">Neem contact op met uw beheerder voor hulp.</span><span class="sxs-lookup"><span data-stu-id="df625-116">Contact your administrator for help.</span></span>

<span data-ttu-id="df625-117">**Oorzaak:**</span><span class="sxs-lookup"><span data-stu-id="df625-117">**Cause:**</span></span> 

<span data-ttu-id="df625-118">U hebt het Microsoft Defender for Endpoint op macOS-pakket ('Installatiepakket downloaden') geïmplementeerd en/of geïnstalleerd, maar mogelijk hebt u het configuratiescript ("Onboarding-pakket downloaden") uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="df625-118">You deployed and/or installed the Microsoft Defender for Endpoint on macOS package ("Download installation package") but you might have run the configuration script ("Download onboarding package").</span></span>

<span data-ttu-id="df625-119">**Oplossing:**</span><span class="sxs-lookup"><span data-stu-id="df625-119">**Solution:**</span></span>

<span data-ttu-id="df625-120">Volg de MicrosoftDefenderATPOnboardingMacOs.py instructies die hier worden beschreven: [Clientconfiguratie](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="df625-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>

