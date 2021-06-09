---
title: Problemen met licenties oplossen voor Microsoft Defender voor Eindpunt op Mac
description: Problemen met licenties oplossen in Microsoft Defender voor Eindpunt op Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, performance
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
ms.openlocfilehash: 1f8428c2995eec2dece290049eda67a3683b4c1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244978"
---
# <a name="troubleshoot-license-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="8b16f-104">Problemen met licenties oplossen voor Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="8b16f-104">Troubleshoot license issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="8b16f-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="8b16f-105">**Applies to:**</span></span>

- [<span data-ttu-id="8b16f-106">Microsoft Defender voor Eindpunt op macOS</span><span class="sxs-lookup"><span data-stu-id="8b16f-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="8b16f-107">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="8b16f-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="8b16f-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b16f-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8b16f-109">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="8b16f-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8b16f-110">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="8b16f-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="8b16f-111">Terwijl u door Microsoft Defender voor Eindpunt [](mac-install-manually.md) op [macOS](microsoft-defender-endpoint-mac.md) en Handmatige implementatietests of een Proof Of Concept (PoC) gaat, krijgt u mogelijk de volgende foutmelding:</span><span class="sxs-lookup"><span data-stu-id="8b16f-111">While you are going through [Microsoft Defender for Endpoint on macOS](microsoft-defender-endpoint-mac.md) and [Manual deployment](mac-install-manually.md) testing or a Proof Of Concept (PoC), you might get the following error:</span></span>

![Afbeelding van licentiefout](images/no-license-found.png)

<span data-ttu-id="8b16f-113">**Bericht:**</span><span class="sxs-lookup"><span data-stu-id="8b16f-113">**Message:**</span></span> 

<span data-ttu-id="8b16f-114">Geen licentie gevonden</span><span class="sxs-lookup"><span data-stu-id="8b16f-114">No license found</span></span>

<span data-ttu-id="8b16f-115">Het lijkt erop dat uw organisatie geen licentie heeft voor Microsoft 365 Enterprise abonnement.</span><span class="sxs-lookup"><span data-stu-id="8b16f-115">Looks like your organization does not have a license for Microsoft 365 Enterprise subscription.</span></span>

<span data-ttu-id="8b16f-116">Neem contact op met uw beheerder voor hulp.</span><span class="sxs-lookup"><span data-stu-id="8b16f-116">Contact your administrator for help.</span></span>

<span data-ttu-id="8b16f-117">**Oorzaak:**</span><span class="sxs-lookup"><span data-stu-id="8b16f-117">**Cause:**</span></span> 

<span data-ttu-id="8b16f-118">U hebt het Microsoft Defender voor Eindpunt voor macOS-pakket ('Installatiepakket downloaden') geïmplementeerd en/of geïnstalleerd, maar u hebt mogelijk het configuratiescript ("Onboarding-pakket downloaden" uitgevoerd), of u hebt geen licentie toegewezen aan de gebruiker.</span><span class="sxs-lookup"><span data-stu-id="8b16f-118">You deployed and/or installed the Microsoft Defender for Endpoint for macOS package ("Download installation package"), but you might have run the configuration script ("Download onboarding package"), or you have not assigned a license to the user.</span></span>

<span data-ttu-id="8b16f-119">**Oplossing:**</span><span class="sxs-lookup"><span data-stu-id="8b16f-119">**Solution:**</span></span>

<span data-ttu-id="8b16f-120">Volg de MicrosoftDefenderATPOnboardingMacOs.py instructies die hier worden beschreven: [Clientconfiguratie](mac-install-manually.md#client-configuration)</span><span class="sxs-lookup"><span data-stu-id="8b16f-120">Follow the MicrosoftDefenderATPOnboardingMacOs.py instructions documented here: [Client configuration](mac-install-manually.md#client-configuration)</span></span>
