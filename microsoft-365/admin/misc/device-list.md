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
description: Meer informatie over het maken van een CSV-bestand voor AutoPilo-blik Microsoft 365 Business.
ms.openlocfilehash: 56d8fb234a1b526192468309c93c638694b92c6e
ms.sourcegitcommit: 812aab5f58eed4bf359faf0e99f7f876af5b1023
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/02/2020
ms.locfileid: "42808537"
---
# <a name="device-list-csv-file"></a><span data-ttu-id="666e9-103">CSV-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="666e9-103">Device list CSV-file</span></span>

## <a name="device-list-csv-file-format"></a><span data-ttu-id="666e9-104">Bestandsindeling van .csv-bestand met apparatenlijst</span><span class="sxs-lookup"><span data-stu-id="666e9-104">Device list .csv file format</span></span>

<span data-ttu-id="666e9-105">Voor het beheren en implementeren van apparaten via Windows Autopilot hebt u een .csv-bestand nodig dat specifieke informatie over de apparaten bevat.</span><span class="sxs-lookup"><span data-stu-id="666e9-105">To manage and deploy devices through Windows Autopilot, you'll need a .csv file that contains specific information about the devices.</span></span>
  
<span data-ttu-id="666e9-106">De kolommen in het apparatenlijstbestand moeten de volgende kopteksten hebben, in de opgegeven volgorde:</span><span class="sxs-lookup"><span data-stu-id="666e9-106">Columns in the device list file must have the following headers in the specified order:</span></span>
  
- <span data-ttu-id="666e9-107">Kolom A: Serienummer van apparaat</span><span class="sxs-lookup"><span data-stu-id="666e9-107">Column A: Device Serial Number</span></span>

- <span data-ttu-id="666e9-108">Kolom B: laat leeg</span><span class="sxs-lookup"><span data-stu-id="666e9-108">Column B: leave blank</span></span>

- <span data-ttu-id="666e9-109">Kolom C: Hardware-hash</span><span class="sxs-lookup"><span data-stu-id="666e9-109">Column C: Hardware Hash</span></span>

<span data-ttu-id="666e9-110">U kunt deze informatie van uw hardwareleverancier krijgen of u kunt het [Get-WindowsAutoPilotInfo-PowerShell-script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) gebruiken, waarmee een CSV-bestand wordt gegenereerd.</span><span class="sxs-lookup"><span data-stu-id="666e9-110">You can get this information from your hardware vendor, or you can use the [Get-WindowsAutoPilotInfo PowerShell script](https://www.powershellgallery.com/packages/Get-WindowsAutoPilotInfo) that will generate a CSV file.</span></span> 

<span data-ttu-id="666e9-p101">Wanneer u apparaten toevoegt, moet u ze ook toevoegen aan een profiel. Een profiel wordt gebruikt om AutoPilot-implementatieprofielen toe te passen op een apparaat of een groep apparaten.</span><span class="sxs-lookup"><span data-stu-id="666e9-p101">When you add devices, you also need to add them to a Profile. A profile is used to apply AutoPilot deployment profiles to a device or a group of devices.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="666e9-113">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="666e9-113">Related articles</span></span>

[<span data-ttu-id="666e9-114">Documentatie en informatiebronnen voor Microsoft 365 Business (Engelstalig)</span><span class="sxs-lookup"><span data-stu-id="666e9-114">Microsoft 365 Business documentation and resources</span></span>](https://go.microsoft.com/fwlink/p/?linkid=853701)
  
[<span data-ttu-id="666e9-115">Aan de slag met Microsoft 365 Business</span><span class="sxs-lookup"><span data-stu-id="666e9-115">Get started with Microsoft 365 Business</span></span>](https://support.office.com/article/496e690b-b75d-4ff5-bf34-cc32905d0364)
  
[<span data-ttu-id="666e9-116">Microsoft 365 Business beheren</span><span class="sxs-lookup"><span data-stu-id="666e9-116">Manage Microsoft 365 Business</span></span>](https://support.office.com/article/27ff1678-865a-4707-8145-e1155aa815d6)
  
