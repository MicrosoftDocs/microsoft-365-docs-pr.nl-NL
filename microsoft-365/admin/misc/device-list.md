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
ms.openlocfilehash: b1154d639ba23180f637520750d94f00e997cfc4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43627858"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="b84df-103">CSV-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="b84df-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="b84df-104">Bestandsindeling van .csv-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="b84df-104">Device list .csv file format</span></span>

<span data-ttu-id="b84df-105">Voor het beheren en implementeren van apparaten via Windows Autopilot hebt u een .csv-bestand nodig dat specifieke informatie over de apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="b84df-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="b84df-106">De kolommen in het apparatenlijstbestand moeten de volgende kopteksten hebben, in de opgegeven volgorde:</span><span class="sxs-lookup"><span data-stu-id="b84df-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="b84df-107">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="b84df-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="b84df-108">Kolom B: laat leeg</span><span class="sxs-lookup"><span data-stu-id="b84df-108">Column B: leave blank</span></span>

- <span data-ttu-id="b84df-109">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="b84df-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="b84df-110">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="b84df-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="b84df-p101">Wanneer u apparaten toevoegt, moet u ze ook toevoegen aan een profiel. Een profiel wordt gebruikt om AutoPilot-implementatieprofielen toe te passen op een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="b84df-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="b84df-113">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="b84df-113">Related articles</span></span>

[<span data-ttu-id="b84df-114">Microsoft 365 voor bedrijfsdocumentatie en -bronnen</span><span class="sxs-lookup"><span data-stu-id="b84df-114">Microsoft 365 for business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="b84df-115">Aan de slag met Microsoft 365 voor bedrijven</span><span class="sxs-lookup"><span data-stu-id="b84df-115">Get started with Microsoft 365 for business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="b84df-116">Microsoft 365 voor bedrijven beheren</span><span class="sxs-lookup"><span data-stu-id="b84df-116">Manage Microsoft 365 for business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
