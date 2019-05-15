---
title: Fouten in AutoPilot-apparaten oplossen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: troubleshooting
f1_keywords:
- ZTDTroubleshootDeviceErrors
- O365E_ZTDTroubleshootDeviceErrors
- BCS365_ZTDTroubleshootDeviceErrors
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Informatie over het oplossen van problemen met automatische piloot fouten in het bestand.
ms.openlocfilehash: 88b59ec20ddda401c1dac45ff729ac38497a767e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074355"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="a1fa4-103">Fouten in AutoPilot-apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="a1fa4-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="a1fa4-104">Foutberichten van apparaat-bestand</span><span class="sxs-lookup"><span data-stu-id="a1fa4-104">Device file error messages</span></span>

<span data-ttu-id="a1fa4-105">Hier volgt informatie over enkele van de fouten ziet u tijdens het werken met automatische piloot apparaatbestanden in Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="a1fa4-106">**Foutcode**</span><span class="sxs-lookup"><span data-stu-id="a1fa4-106">**Error code**</span></span>|<span data-ttu-id="a1fa4-107">**Oplossing om te proberen**</span><span class="sxs-lookup"><span data-stu-id="a1fa4-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a1fa4-108">Ongeldige aanvraag body</span><span class="sxs-lookup"><span data-stu-id="a1fa4-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="a1fa4-109">Deze fout zelden, er moet gebeuren als u deze fout ziet, probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="a1fa4-110">Hardware-hash-waarde voor een apparaat is niet juist.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="a1fa4-111">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in het CSV-bestand voor de hardware-hash van een apparaat niet correct is.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="a1fa4-112">Controleer eerst of de waarde juist is getypt.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="a1fa4-113">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, uw hardwareleverancier om hulp vragen.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a1fa4-114">Apparaat is toegewezen aan een andere huurder</span><span class="sxs-lookup"><span data-stu-id="a1fa4-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="a1fa4-115">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in het CSV-bestand voor het serienummer of de productcode van een of meer apparaten niet correct is.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="a1fa4-116">Controleer eerst of de waarde juist is getypt.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="a1fa4-117">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, uw hardwareleverancier om hulp vragen.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a1fa4-118">Het CSV-bestand bevat een ongeldig serieel getal of een productcode</span><span class="sxs-lookup"><span data-stu-id="a1fa4-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="a1fa4-119">Als u deze fout betekent dat het apparaat dat u opgetreden bij een poging om te registreren al door een andere organisatie is geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-119">If you see this error it means that the device you are tyring to register is already registered by an other organization.</span></span> <span data-ttu-id="a1fa4-120">U kunt dit oplossen door de hardwareleverancier om hulp te vragen.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-120">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="a1fa4-121">Dit apparaat wordt niet ondersteund voor installatie via automatische piloot</span><span class="sxs-lookup"><span data-stu-id="a1fa4-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="a1fa4-122">Deze fout geeft aan dat het apparaat voldoet niet aan de vereisten voor het implementeren van automatische piloot.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-122">This error means the device does not meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="a1fa4-123">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="a1fa4-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="a1fa4-124">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="a1fa4-125">Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="a1fa4-126">Apparaat is niet gevonden</span><span class="sxs-lookup"><span data-stu-id="a1fa4-126">Device not found</span></span>  <br/> |<span data-ttu-id="a1fa4-127">Deze fout geeft aan dat een of meer apparaten in uw CSV-bestand is niet geregistreerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-127">This error means that one or more devices in your CSV file is not registered to your organization.</span></span> <span data-ttu-id="a1fa4-128">U kunt dit oplossen door de hardwareleverancier om hulp te vragen.</span><span class="sxs-lookup"><span data-stu-id="a1fa4-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
