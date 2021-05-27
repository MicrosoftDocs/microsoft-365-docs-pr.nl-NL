---
title: De Microsoft Defender Antivirus configureren met Microsoft Endpoint Manager
description: Gebruik Microsoft Endpoint Manager en Microsoft Intune voor het configureren van Microsoft Defender AV en Endpoint Protection
keywords: scep, intune, endpointbeveiliging, configuratie
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 05/24/2021
ms.reviewer: phuijbr, oogunrinde
manager: dansimp
ms.technology: mde
audience: ITPro
ms.topic: how-to
ms.openlocfilehash: ab77f3ab5ac9385d1ce049061730d2192e3bcb0c
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52683749"
---
# <a name="use-microsoft-endpoint-manager-to-configure-and-manage-microsoft-defender-antivirus"></a><span data-ttu-id="e2488-104">Gebruik Microsoft Endpoint Manager voor het configureren en beheren van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e2488-104">Use Microsoft Endpoint Manager to configure and manage Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e2488-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e2488-105">**Applies to:**</span></span>

- [<span data-ttu-id="e2488-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e2488-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e2488-107">U kunt [de](/mem/endpoint-manager-overview) Microsoft Endpoint Manager gebruiken om de Microsoft Defender Antivirus configureren.</span><span class="sxs-lookup"><span data-stu-id="e2488-107">You can use [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) to configure Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="e2488-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) en [Configuration Manager](/mem/configmgr/core/understand/introduction) maken nu deel uit van Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="e2488-108">[Microsoft Intune](/mem/intune/fundamentals/what-is-intune) and [Configuration Manager](/mem/configmgr/core/understand/introduction) are now part of Endpoint Manager.</span></span>  

## <a name="configure-microsoft-defender-antivirus-scans-in-endpoint-manager"></a><span data-ttu-id="e2488-109">Configureer Microsoft Defender Antivirus scans in Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e2488-109">Configure Microsoft Defender Antivirus scans in Endpoint Manager</span></span>

1. <span data-ttu-id="e2488-110">Ga naar het Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () en meld u aan.</span><span class="sxs-lookup"><span data-stu-id="e2488-110">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), and sign in.</span></span>

2. <span data-ttu-id="e2488-111">Ga naar **Endpoint-beveiliging.**</span><span class="sxs-lookup"><span data-stu-id="e2488-111">Navigate to **Endpoint Security**.</span></span>

3. <span data-ttu-id="e2488-112">Kies **onder Beheren** de optie **Antivirus.**</span><span class="sxs-lookup"><span data-stu-id="e2488-112">Under **Manage**, choose **Antivirus**.</span></span>

4. <span data-ttu-id="e2488-113">Selecteer uw Microsoft Defender Antivirus beleid.</span><span class="sxs-lookup"><span data-stu-id="e2488-113">Select your Microsoft Defender Antivirus policy.</span></span> 

5. <span data-ttu-id="e2488-114">Klik onder **Beheren** op **Eigenschappen**.</span><span class="sxs-lookup"><span data-stu-id="e2488-114">Under **Manage**, choose **Properties**.</span></span>

6. <span data-ttu-id="e2488-115">Kies na **Configuratie-instellingen** de optie **Bewerken**.</span><span class="sxs-lookup"><span data-stu-id="e2488-115">Next to **Configuration settings**, choose **Edit**.</span></span>

7. <span data-ttu-id="e2488-116">Vouw de **sectie Scannen** uit en bekijk of bewerk uw scaninstellingen.</span><span class="sxs-lookup"><span data-stu-id="e2488-116">Expand the **Scan** section, and review or edit your scanning settings.</span></span>

8. <span data-ttu-id="e2488-117">Kies **Controleren + opslaan**</span><span class="sxs-lookup"><span data-stu-id="e2488-117">Choose **Review + save**</span></span>


> [!TIP]
> <span data-ttu-id="e2488-118">Hulp nodig?</span><span class="sxs-lookup"><span data-stu-id="e2488-118">Need help?</span></span> <span data-ttu-id="e2488-119">Zie [Beveiliging van eindpunten beheren in Microsoft Intune.](/mem/intune/protect/endpoint-security)</span><span class="sxs-lookup"><span data-stu-id="e2488-119">See [Manage endpoint security in Microsoft Intune](/mem/intune/protect/endpoint-security).</span></span>


## <a name="related-articles"></a><span data-ttu-id="e2488-120">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e2488-120">Related articles</span></span>

- [<span data-ttu-id="e2488-121">Naslagartikelen voor beheer- en configuratiehulpmiddelen</span><span class="sxs-lookup"><span data-stu-id="e2488-121">Reference articles for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e2488-122">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="e2488-122">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)