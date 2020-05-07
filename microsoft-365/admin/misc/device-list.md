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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 932e3676-2491-49f0-9177-d893d2f5276e
ROBOTS: NOINDEX
description: Meer informatie over het maken van een CSV-bestand voor AutoPilot in Microsoft 365 voor bedrijven.
ms.openlocfilehash: c83862675db1372aa2cef27c727c04577b4cf5a3
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2020
ms.locfileid: "44064649"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="d20b1-103">CSV-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="d20b1-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="d20b1-104">Bestandsindeling van .csv-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="d20b1-104">Device list .csv file format</span></span>

<span data-ttu-id="d20b1-105">Voor het beheren en implementeren van apparaten via Windows Autopilot hebt u een .csv-bestand nodig dat specifieke informatie over de apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="d20b1-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="d20b1-106">De kolommen in het apparatenlijstbestand moeten de volgende kopteksten hebben, in de opgegeven volgorde:</span><span class="sxs-lookup"><span data-stu-id="d20b1-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="d20b1-107">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="d20b1-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="d20b1-108">Kolom B: laat leeg</span><span class="sxs-lookup"><span data-stu-id="d20b1-108">Column B: leave blank</span></span>

- <span data-ttu-id="d20b1-109">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="d20b1-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="d20b1-110">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="d20b1-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="d20b1-p101">Wanneer u apparaten toevoegt, moet u ze ook toevoegen aan een profiel. Een profiel wordt gebruikt om AutoPilot-implementatieprofielen toe te passen op een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="d20b1-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="d20b1-113">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="d20b1-113">Related articles</span></span>

[<span data-ttu-id="d20b1-114">Microsoft 365 voor bedrijfsdocumentatie en -bronnen</span><span class="sxs-lookup"><span data-stu-id="d20b1-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="d20b1-115">Aan de slag met Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="d20b1-115">Get started with Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/microsoft-365-business-overview)
  
[<span data-ttu-id="d20b1-116">Microsoft 365 voor bedrijven beheren</span><span class="sxs-lookup"><span data-stu-id="d20b1-116">Manage Microsoft 365 for business</span></span>](https://docs.microsoft.com/microsoft-365/business/manage)
  
