---
title: CSV-bestand met apparatenlijst
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Meer informatie over het maken van een CSV-bestand voor AutoPilot in Microsoft 365 voor bedrijven.
ms.openlocfilehash: 13d7fbffd8d6fbe1af0dde55a4e98688060d9da8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579216"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="5397a-103">CSV-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="5397a-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="5397a-104">Bestandsindeling van .csv-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="5397a-104">Device list .csv file format</span></span>

<span data-ttu-id="5397a-105">Voor het beheren en implementeren van apparaten via Windows Autopilot hebt u een .csv-bestand nodig dat specifieke informatie over de apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="5397a-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="5397a-106">De kolommen in het apparatenlijstbestand moeten de volgende kopteksten hebben, in de opgegeven volgorde:</span><span class="sxs-lookup"><span data-stu-id="5397a-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="5397a-107">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="5397a-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="5397a-108">Kolom B: leeg laten</span><span class="sxs-lookup"><span data-stu-id="5397a-108">Column B: leave blank</span></span>

- <span data-ttu-id="5397a-109">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="5397a-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="5397a-110">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="5397a-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="5397a-p101">Wanneer u apparaten toevoegt, moet u ze ook toevoegen aan een profiel. Een profiel wordt gebruikt om AutoPilot-implementatieprofielen toe te passen op een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="5397a-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="5397a-113">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="5397a-113">Related articles</span></span>

[<span data-ttu-id="5397a-114">Microsoft 365 voor zakelijke documentatie en resources</span><span class="sxs-lookup"><span data-stu-id="5397a-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="5397a-115">Aan de slag met Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="5397a-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="5397a-116">Beheer Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="5397a-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
