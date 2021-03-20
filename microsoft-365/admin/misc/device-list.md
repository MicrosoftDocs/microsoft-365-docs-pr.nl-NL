---
title: CSV-bestand met apparatenlijst
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Meer informatie over het maken van een CSV-bestand voor AutoPilot in Microsoft 365 voor Bedrijven.
ms.openlocfilehash: 78a9012bac054329bdb87b02757f49f30dd44f65
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914736"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="45440-103">CSV-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="45440-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="45440-104">Bestandsindeling van .csv-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="45440-104">Device list .csv file format</span></span>

<span data-ttu-id="45440-105">Voor het beheren en implementeren van apparaten via Windows Autopilot hebt u een .csv-bestand nodig dat specifieke informatie over de apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="45440-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="45440-106">De kolommen in het apparatenlijstbestand moeten de volgende kopteksten hebben, in de opgegeven volgorde:</span><span class="sxs-lookup"><span data-stu-id="45440-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="45440-107">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="45440-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="45440-108">Kolom B: leeg laten</span><span class="sxs-lookup"><span data-stu-id="45440-108">Column B: leave blank</span></span>

- <span data-ttu-id="45440-109">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="45440-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="45440-110">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="45440-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="45440-p101">Wanneer u apparaten toevoegt, moet u ze ook toevoegen aan een profiel. Een profiel wordt gebruikt om AutoPilot-implementatieprofielen toe te passen op een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="45440-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="45440-113">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="45440-113">Related articles</span></span>

[<span data-ttu-id="45440-114">Microsoft 365 voor bedrijven-documentatie en -bronnen</span><span class="sxs-lookup"><span data-stu-id="45440-114">Microsoft 365 for business documentation and resources</span></span>](../../business/index.yml)
  
[<span data-ttu-id="45440-115">Aan de slag met Microsoft 365 voor Bedrijven</span><span class="sxs-lookup"><span data-stu-id="45440-115">Get started with Microsoft 365 for business</span></span>](../../business/microsoft-365-business-overview.md)
  
[<span data-ttu-id="45440-116">Microsoft 365 voor Bedrijven beheren</span><span class="sxs-lookup"><span data-stu-id="45440-116">Manage Microsoft 365 for business</span></span>](../../business/manage.md)
