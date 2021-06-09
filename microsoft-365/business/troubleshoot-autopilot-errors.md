---
title: Fouten in AutoPilot-apparaten oplossen
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
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
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Meer informatie over het oplossen van fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium.
ms.openlocfilehash: 1078ab74b07952e4bb565555a081b98ecce9db5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578082"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="b2ab5-103">Fouten in AutoPilot-apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="b2ab5-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="b2ab5-104">Foutberichten van apparaatbestand</span><span class="sxs-lookup"><span data-stu-id="b2ab5-104">Device file error messages</span></span>

<span data-ttu-id="b2ab5-105">Hier vindt u informatie over enkele fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="b2ab5-106">**Foutcode**</span><span class="sxs-lookup"><span data-stu-id="b2ab5-106">**Error code**</span></span>|<span data-ttu-id="b2ab5-107">**Fix om te proberen**</span><span class="sxs-lookup"><span data-stu-id="b2ab5-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b2ab5-108">Ongeldige aanvraag</span><span class="sxs-lookup"><span data-stu-id="b2ab5-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="b2ab5-109">Deze fout gebeurt zelden, als u deze fout ziet, probeert u de bewerking opnieuw.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="b2ab5-110">De hashwaarde voor hardware voor een apparaat is niet correct.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="b2ab5-111">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor de hardware-hash van één apparaat, niet juist is.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="b2ab5-112">Controleer eerst of de waarde correct is getypt.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="b2ab5-113">Als u denkt dat de waarde juist is, maar deze fout nog steeds wordt weergegeven, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="b2ab5-114">Apparaat dat is toegewezen aan een andere tenant</span><span class="sxs-lookup"><span data-stu-id="b2ab5-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="b2ab5-115">Als u deze fout ziet, betekent dit dat de waarde die u hebt opgegeven in uw CSV-bestand voor het serienummer of de productcode van een of meer apparaten niet juist is.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="b2ab5-116">Controleer eerst of de waarde correct is getypt.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="b2ab5-117">Als u denkt dat de waarde juist is, maar deze fout nog steeds wordt weergegeven, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="b2ab5-118">Het CSV-bestand bevat een ongeldig serienummer of productcode</span><span class="sxs-lookup"><span data-stu-id="b2ab5-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="b2ab5-119">Als u deze fout ziet, betekent dit dat het apparaat dat u wilt registreren al is geregistreerd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="b2ab5-120">Als u deze fout wilt oplossen, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="b2ab5-121">Dit apparaat wordt niet ondersteund voor het instellen met Behulp van AutoPilot</span><span class="sxs-lookup"><span data-stu-id="b2ab5-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="b2ab5-122">Deze fout betekent dat het apparaat niet voldoet aan de implementatievereisten voor AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="b2ab5-123">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="b2ab5-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="b2ab5-124">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="b2ab5-125">Nieuwe apparaten die nog niet zijn Windows-out-of-box-ervaring.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="b2ab5-126">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="b2ab5-126">Device not found</span></span>  <br/> |<span data-ttu-id="b2ab5-127">Deze fout betekent dat een of meer apparaten in uw CSV-bestand niet zijn geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="b2ab5-128">Als u dit wilt oplossen, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="b2ab5-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
