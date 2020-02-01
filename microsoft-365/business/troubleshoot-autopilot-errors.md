---
title: Fouten in AutoPilot-apparaten oplossen
f1.keywords:
- NOCSH
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
description: Meer informatie over het oplossen van autopilot-apparaatbestandsfouten.
ms.openlocfilehash: 8390f695a3e11386ae2617da4061bed1d8214375
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594203"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="bc8c8-103">Fouten in AutoPilot-apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="bc8c8-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="bc8c8-104">Foutberichten in apparaatbestanden</span><span class="sxs-lookup"><span data-stu-id="bc8c8-104">Device file error messages</span></span>

<span data-ttu-id="bc8c8-105">Hier vindt u informatie over enkele fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business.</span></span> 
  
|<span data-ttu-id="bc8c8-106">**Foutcode**</span><span class="sxs-lookup"><span data-stu-id="bc8c8-106">**Error code**</span></span>|<span data-ttu-id="bc8c8-107">**Oplossen om te proberen**</span><span class="sxs-lookup"><span data-stu-id="bc8c8-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bc8c8-108">Ongeldige aanvraaginstantie</span><span class="sxs-lookup"><span data-stu-id="bc8c8-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="bc8c8-109">Deze fout moet zelden voorkomen, als u deze fout ziet, probeer de bewerking opnieuw.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="bc8c8-110">Hardwarehashwaarde voor een apparaat is niet correct.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="bc8c8-111">Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor de hardwarehash van één apparaat niet correct is.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="bc8c8-112">Controleer eerst of de waarde correct is getypt.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="bc8c8-113">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag dan uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="bc8c8-114">Apparaat toegewezen aan een andere tenant</span><span class="sxs-lookup"><span data-stu-id="bc8c8-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="bc8c8-115">Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor het serienummer of de productcode van een of meer apparaten niet correct is.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="bc8c8-116">Controleer eerst of de waarde correct is getypt.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="bc8c8-117">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag dan uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="bc8c8-118">Het CSV-bestand bevat een ongeldig serienummer of productcode</span><span class="sxs-lookup"><span data-stu-id="bc8c8-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="bc8c8-119">Als u deze fout ziet, betekent dit dat het apparaat dat u probeert te registreren, al is geregistreerd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="bc8c8-120">Als u deze fout wilt verhelpen, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="bc8c8-121">Dit apparaat wordt niet ondersteund voor installatie met Behulp van AutoPilot</span><span class="sxs-lookup"><span data-stu-id="bc8c8-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="bc8c8-122">Deze fout betekent dat het apparaat niet voldoet aan de implementatievereisten van AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="bc8c8-123">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="bc8c8-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="bc8c8-124">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="bc8c8-125">Nieuwe apparaten die niet zijn door Windows out-of-box ervaring.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="bc8c8-126">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="bc8c8-126">Device not found</span></span>  <br/> |<span data-ttu-id="bc8c8-127">Deze fout betekent dat een of meer apparaten in uw CSV-bestand niet zijn geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="bc8c8-128">Om dit op te lossen, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="bc8c8-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
