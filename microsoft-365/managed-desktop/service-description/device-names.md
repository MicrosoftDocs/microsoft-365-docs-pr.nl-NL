---
title: Apparaatnamen
description: Hoe Microsoft Managed Desktop apparaatnamen beheert
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893774"
---
# <a name="device-names"></a><span data-ttu-id="59344-103">Apparaatnamen</span><span class="sxs-lookup"><span data-stu-id="59344-103">Device names</span></span>

<span data-ttu-id="59344-104">Microsoft Managed Desktop gebruikt Windows Autopilot, Azure Active Directory en Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="59344-104">Microsoft Managed Desktop uses Windows Autopilot, Azure Active Directory, and Microsoft Intune.</span></span> <span data-ttu-id="59344-105">Om deze services naadloos samen te laten werken, hebben apparaten consistente, gestandaardiseerde namen nodig.</span><span class="sxs-lookup"><span data-stu-id="59344-105">For these services to work together seamlessly, devices need consistent, standardized names.</span></span> <span data-ttu-id="59344-106">Microsoft Managed Desktop past een gestandaardiseerde naamnotatie toe (van het formulier *MMD-%RAND11)* wanneer apparaten zijn geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="59344-106">Microsoft Managed Desktop applies a standardized name format (of the form *MMD-%RAND11*) when devices are enrolled.</span></span> <span data-ttu-id="59344-107">Deze namen worden toegewezen door Windows Autopilot.</span><span class="sxs-lookup"><span data-stu-id="59344-107">Windows Autopilot assigns these names.</span></span> <span data-ttu-id="59344-108">Zie [First-run experience with Autopilot and the Enrollment Status Page (First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md)) voor meer informatie over Autopilot.</span><span class="sxs-lookup"><span data-stu-id="59344-108">For more information about Autopilot, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

## <a name="automated-name-changes"></a><span data-ttu-id="59344-109">Geautomatiseerde naamwijzigingen</span><span class="sxs-lookup"><span data-stu-id="59344-109">Automated name changes</span></span>

<span data-ttu-id="59344-110">Als de naam van een apparaat later wordt gewijzigd, wordt de naam van een apparaat automatisch gewijzigd in een nieuwe naam in de gestandaardiseerde indeling.</span><span class="sxs-lookup"><span data-stu-id="59344-110">If a device gets renamed later, Microsoft Managed Desktop will automatically rename it to a new name in the standardized format.</span></span> <span data-ttu-id="59344-111">Dit proces vindt elke vier uur plaats.</span><span class="sxs-lookup"><span data-stu-id="59344-111">This process occurs every four hours.</span></span> <span data-ttu-id="59344-112">De naamswijziging vindt plaats de volgende keer dat de gebruiker het apparaat opnieuw start.</span><span class="sxs-lookup"><span data-stu-id="59344-112">The name change takes place the next time the user restarts the device.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="59344-113">Als uw omgeving afhankelijk is van specifieke apparaatnamen (bijvoorbeeld om een bepaalde netwerkconfiguratie te ondersteunen), moet u opties onderzoeken om die afhankelijkheid te verwijderen voordat u zich inschrijft bij Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="59344-113">If your environment depends on specific device names (for example, to support a particular network configuration), you should investigate options to remove that dependency before enrolling in Microsoft Managed Desktop.</span></span> <span data-ttu-id="59344-114">Als u de naamafhankelijkheid moet behouden, kunt u een aanvraag indienen via de [beheerportal](../working-with-managed-desktop/admin-support.md) om de naamswijzigingsfunctie uit te schakelen en de gewenste naamnotatie te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="59344-114">If you must keep the name dependency, you can submit a request through the [Admin portal](../working-with-managed-desktop/admin-support.md) to disable the renaming function and use your desired name format.</span></span>