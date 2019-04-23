---
title: Fouten in AutoPilot-apparaten oplossen
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
ms.openlocfilehash: 9d4a47f78c38d8c076f5b3876a36b6bf46eaaaf3
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279833"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="cb4f9-103">Fouten in AutoPilot-apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="cb4f9-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="cb4f9-104">Foutberichten van apparaat-bestand</span><span class="sxs-lookup"><span data-stu-id="cb4f9-104">Device file error messages</span></span>

<span data-ttu-id="cb4f9-105">Hier volgt informatie over enkele van de fouten ziet u tijdens het werken met automatische piloot apparaatbestanden in Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="cb4f9-106">**Foutcode**</span><span class="sxs-lookup"><span data-stu-id="cb4f9-106">**Error code**</span></span>|<span data-ttu-id="cb4f9-107">**Oplossing om te proberen**</span><span class="sxs-lookup"><span data-stu-id="cb4f9-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cb4f9-108">Ongeldige aanvraag body</span><span class="sxs-lookup"><span data-stu-id="cb4f9-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="cb4f9-109">Deze fout zelden, er moet gebeuren als u deze fout ziet, probeer het opnieuw.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="cb4f9-110">Hardware-hash-waarde voor een apparaat is niet juist.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="cb4f9-111">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in het CSV-bestand voor de hardware-hash van een apparaat niet correct is.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="cb4f9-112">Controleer eerst of de waarde juist is getypt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="cb4f9-113">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, uw hardwareleverancier om hulp vragen.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="cb4f9-114">Apparaat is toegewezen aan een andere huurder</span><span class="sxs-lookup"><span data-stu-id="cb4f9-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="cb4f9-115">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in het CSV-bestand voor het serienummer of de productcode van een of meer apparaten niet correct is.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="cb4f9-116">Controleer eerst of de waarde juist is getypt.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="cb4f9-117">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, uw hardwareleverancier om hulp vragen.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="cb4f9-118">Het CSV-bestand bevat een ongeldig serieel getal of een productcode</span><span class="sxs-lookup"><span data-stu-id="cb4f9-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="cb4f9-119">Als u deze fout betekent dat het apparaat dat u opgetreden bij een poging om te registreren al door een andere organisatie is geregistreerd.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-119">If you see this error it means that the device you are tyring to register is already registered by an other organization.</span></span> <span data-ttu-id="cb4f9-120">U kunt dit oplossen door de hardwareleverancier om hulp te vragen.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-120">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="cb4f9-121">Dit apparaat wordt niet ondersteund voor installatie via automatische piloot</span><span class="sxs-lookup"><span data-stu-id="cb4f9-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="cb4f9-122">Deze fout geeft aan dat het apparaat voldoet niet aan de vereisten voor het implementeren van automatische piloot.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-122">This error means the device does not meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="cb4f9-123">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="cb4f9-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="cb4f9-124">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="cb4f9-125">Nieuwe apparaten die niet de Out-of-Box Experience van Windows hebben doorlopen.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-125">New devices that have not been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="cb4f9-126">Apparaat is niet gevonden</span><span class="sxs-lookup"><span data-stu-id="cb4f9-126">Device not found</span></span>  <br/> |<span data-ttu-id="cb4f9-127">Deze fout geeft aan dat een of meer apparaten in uw CSV-bestand is niet geregistreerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-127">This error means that one or more devices in your CSV file is not registered to your organization.</span></span> <span data-ttu-id="cb4f9-128">U kunt dit oplossen door de hardwareleverancier om hulp te vragen.</span><span class="sxs-lookup"><span data-stu-id="cb4f9-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
   
