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
description: Informatie over het oplossen van fouten met AutoPilot-apparaten.
ms.openlocfilehash: 1b5358bd6686c2548e82ec5297ac0ad675835718
ms.sourcegitcommit: 6a413a65b8c2e10cea08f0a15635b28a1362a582
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/19/2019
ms.locfileid: "38718694"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="3f324-103">Fouten in AutoPilot-apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="3f324-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="3f324-104">Foutberichten van apparaatbestand</span><span class="sxs-lookup"><span data-stu-id="3f324-104">Device file error messages</span></span>

<span data-ttu-id="3f324-105">Hier vindt u informatie over enkele van de fouten die u zien tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="3f324-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="3f324-106">**Error code**</span><span class="sxs-lookup"><span data-stu-id="3f324-106">**Error code**</span></span>|<span data-ttu-id="3f324-107">**Oplossing om te proberen**</span><span class="sxs-lookup"><span data-stu-id="3f324-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3f324-108">Ongeldige aanvraagtekst</span><span class="sxs-lookup"><span data-stu-id="3f324-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="3f324-109">Deze fout moet zelden gebeuren, als u deze fout ziet, probeer de bewerking opnieuw.</span><span class="sxs-lookup"><span data-stu-id="3f324-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="3f324-110">Hardware-hashwaarde voor een apparaat is niet correct.</span><span class="sxs-lookup"><span data-stu-id="3f324-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="3f324-111">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor de hardware-hash van een apparaat niet correct is.</span><span class="sxs-lookup"><span data-stu-id="3f324-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="3f324-112">Controleer eerst of de waarde juist is getypt.</span><span class="sxs-lookup"><span data-stu-id="3f324-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="3f324-113">Als u denkt dat de waarde juist is, maar deze fout nog steeds optreedt, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="3f324-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="3f324-114">Apparaat toegewezen aan een andere Tenant</span><span class="sxs-lookup"><span data-stu-id="3f324-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="3f324-115">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor het serienummer of de productcode van een of meer apparaten niet correct is.</span><span class="sxs-lookup"><span data-stu-id="3f324-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="3f324-116">Controleer eerst of de waarde juist is getypt.</span><span class="sxs-lookup"><span data-stu-id="3f324-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="3f324-117">Als u denkt dat de waarde juist is, maar deze fout nog steeds optreedt, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="3f324-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="3f324-118">Het CSV-bestand bevat een ongeldig serienummer of productcode</span><span class="sxs-lookup"><span data-stu-id="3f324-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="3f324-119">Als u deze fout ziet, betekent dit dat het apparaat dat u probeert te registreren al is geregistreerd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="3f324-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="3f324-120">U deze fout oplossen door uw hardwareleverancier om hulp te vragen.</span><span class="sxs-lookup"><span data-stu-id="3f324-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="3f324-121">Dit apparaat wordt niet ondersteund voor Setup met behulp van AutoPilot</span><span class="sxs-lookup"><span data-stu-id="3f324-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="3f324-122">Deze fout betekent dat het apparaat niet voldoet aan de vereisten voor de AutoPilot-implementatie.</span><span class="sxs-lookup"><span data-stu-id="3f324-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="3f324-123">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="3f324-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="3f324-124">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="3f324-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="3f324-125">Nieuwe apparaten die niet via Windows out-of-Box-ervaring.</span><span class="sxs-lookup"><span data-stu-id="3f324-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="3f324-126">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="3f324-126">Device not found</span></span>  <br/> |<span data-ttu-id="3f324-127">Deze fout betekent dat een of meer apparaten in uw CSV-bestand is niet geregistreerd voor uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="3f324-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="3f324-128">Om dit op te lossen, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="3f324-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
