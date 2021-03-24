---
title: Apparaatgroepen instellen in Jamf Pro
description: Informatie over het instellen van apparaatgroepen in Jamf Pro voor Microsoft Defender ATP voor macOS
keywords: apparaat, groep, microsoft, defender, atp, mac, installatie, implementeren, verwijderen, intune, jamfpro, macos, catalina, mojave, high sierra
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
ms.openlocfilehash: 3e330f135e391214ffe25289d58c2d0de3257be0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057402"
---
# <a name="set-up-microsoft-defender-for-endpoint-for-macos-device-groups-in-jamf-pro"></a><span data-ttu-id="b4b79-104">Microsoft Defender voor eindpunt instellen voor macOS-apparaatgroepen in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="b4b79-104">Set up Microsoft Defender for Endpoint for macOS device groups in Jamf Pro</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b4b79-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="b4b79-105">**Applies to:**</span></span>
- [<span data-ttu-id="b4b79-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="b4b79-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="b4b79-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b4b79-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b4b79-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="b4b79-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b4b79-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="b4b79-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="b4b79-110">Stel de apparaatgroepen in die lijken op Group policy organizational unite (OUs), de apparaatverzameling van Microsoft Endpoint Configuration Manager en de apparaatgroepen van Intune.</span><span class="sxs-lookup"><span data-stu-id="b4b79-110">Set up the device groups similar to Group policy  organizational unite (OUs), Microsoft Endpoint Configuration Manager's device collection, and Intune's device groups.</span></span>

1. <span data-ttu-id="b4b79-111">**Navigeer naar statische computergroepen.**</span><span class="sxs-lookup"><span data-stu-id="b4b79-111">Navigate to **Static Computer Groups**.</span></span>

2. <span data-ttu-id="b4b79-112">Selecteer **Nieuw.**</span><span class="sxs-lookup"><span data-stu-id="b4b79-112">Select **New**.</span></span> 

    ![Afbeelding van Jamf Pro1](images/jamf-pro-static-group.png)

3. <span data-ttu-id="b4b79-114">Geef een weergavenaam op en selecteer **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="b4b79-114">Provide a display name and select **Save**.</span></span>

    ![Afbeelding van Jamf Pro2](images/jamfpro-machine-group.png)

4. <span data-ttu-id="b4b79-116">Nu ziet u de **contoso-machinegroep** onder **Statische computergroepen.**</span><span class="sxs-lookup"><span data-stu-id="b4b79-116">Now you will see the **Contoso's Machine Group** under **Static Computer Groups**.</span></span>

    ![Afbeelding van Jamf Pro3](images/contoso-machine-group.png)

## <a name="next-step"></a><span data-ttu-id="b4b79-118">Volgende stap</span><span class="sxs-lookup"><span data-stu-id="b4b79-118">Next step</span></span>
- [<span data-ttu-id="b4b79-119">Microsoft Defender voor eindpunt instellen voor macOS-beleid in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="b4b79-119">Set up Microsoft Defender for Endpoint for macOS policies in Jamf Pro</span></span>](mac-jamfpro-policies.md)
