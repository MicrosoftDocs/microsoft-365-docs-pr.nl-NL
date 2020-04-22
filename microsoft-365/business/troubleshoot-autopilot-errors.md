---
title: Fouten in AutoPilot-apparaten oplossen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 1f468690-530c-47ea-918f-fede24607c53
description: Meer informatie over het oplossen van fouten die u zien tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium.
ms.openlocfilehash: 0c0742e5bf17c85cedfb421cabfd87c0e2184ba5
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43635039"
---
# <a name="troubleshoot-autopilot-device-errors"></a><span data-ttu-id="ed176-103">Fouten in AutoPilot-apparaten oplossen</span><span class="sxs-lookup"><span data-stu-id="ed176-103">Troubleshoot AutoPilot device errors</span></span>

## <a name="device-file-error-messages"></a><span data-ttu-id="ed176-104">Foutberichten voor apparaatbestanden</span><span class="sxs-lookup"><span data-stu-id="ed176-104">Device file error messages</span></span>

<span data-ttu-id="ed176-105">Hier vindt u informatie over enkele fouten die u mogelijk ziet tijdens het werken met AutoPilot-apparaatbestanden in Microsoft 365 Business Premium.</span><span class="sxs-lookup"><span data-stu-id="ed176-105">Here's info on some of the errors you might see while working with AutoPilot device files in Microsoft 365 Business Premium.</span></span> 
  
|<span data-ttu-id="ed176-106">**Foutcode**</span><span class="sxs-lookup"><span data-stu-id="ed176-106">**Error code**</span></span>|<span data-ttu-id="ed176-107">**Oplossing om te proberen**</span><span class="sxs-lookup"><span data-stu-id="ed176-107">**Fix to try**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ed176-108">Ongeldige aanvraaginstantie</span><span class="sxs-lookup"><span data-stu-id="ed176-108">Invalid request body</span></span>  <br/> |<span data-ttu-id="ed176-109">Deze fout moet zelden gebeuren, als u deze fout ziet, probeer de bewerking opnieuw.</span><span class="sxs-lookup"><span data-stu-id="ed176-109">This error should happen rarely, if you see this error, try the operation again.</span></span>  <br/> |
|<span data-ttu-id="ed176-110">De waarde van hardwarehash voor een apparaat is niet correct.</span><span class="sxs-lookup"><span data-stu-id="ed176-110">Hardware hash value for a device isn't correct.</span></span>  <br/> |<span data-ttu-id="ed176-111">Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor de hardwarehash van één apparaat niet correct is.</span><span class="sxs-lookup"><span data-stu-id="ed176-111">If you see this error, it means that the value you provided in your CSV file for the hardware hash of one device isn't correct.</span></span> <span data-ttu-id="ed176-112">Controleer eerst of de waarde correct is getypt.</span><span class="sxs-lookup"><span data-stu-id="ed176-112">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="ed176-113">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="ed176-113">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ed176-114">Apparaat toegewezen aan een andere tenant</span><span class="sxs-lookup"><span data-stu-id="ed176-114">Device assigned to another tenant</span></span>  <br/> |<span data-ttu-id="ed176-115">Als u deze fout ziet, betekent dit dat de waarde die u in uw CSV-bestand hebt opgegeven voor het serienummer of de productcode van een of meer apparaten niet correct is.</span><span class="sxs-lookup"><span data-stu-id="ed176-115">If you see this error, it means that the value you provided in your CSV file for either the serial number or the product key of one or more devices isn't correct.</span></span> <span data-ttu-id="ed176-116">Controleer eerst of de waarde correct is getypt.</span><span class="sxs-lookup"><span data-stu-id="ed176-116">First, verify that the value was typed correctly.</span></span> <span data-ttu-id="ed176-117">Als u denkt dat de waarde juist is, maar deze fout nog steeds gebeurt, vraag uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="ed176-117">If you think that the value is correct, but this error is still happening, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ed176-118">Het CSV-bestand bevat een ongeldig serienummer of productcode</span><span class="sxs-lookup"><span data-stu-id="ed176-118">The CSV file contains an invalid serial number or product key</span></span>  <br/> |<span data-ttu-id="ed176-119">Als u deze fout ziet, betekent dit dat het apparaat dat u probeert te registreren al is geregistreerd door een andere organisatie.</span><span class="sxs-lookup"><span data-stu-id="ed176-119">If you see this error, it means that the device you are trying to register is already registered by another organization.</span></span> <span data-ttu-id="ed176-120">Als u deze fout wilt oplossen, vraagt u uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="ed176-120">To fix this error, ask your hardware vendor for help.</span></span>  <br/> |
|<span data-ttu-id="ed176-121">Dit apparaat wordt niet ondersteund voor het instellen met Behulp van AutoPilot</span><span class="sxs-lookup"><span data-stu-id="ed176-121">This device is not supported for setup by using AutoPilot</span></span>  <br/> | <span data-ttu-id="ed176-122">Deze fout betekent dat het apparaat niet voldoet aan de implementatievereisten van AutoPilot.</span><span class="sxs-lookup"><span data-stu-id="ed176-122">This error means the device doesn't meet AutoPilot deployment requirements.</span></span> <span data-ttu-id="ed176-123">Apparaten moeten aan deze vereisten voldoen:</span><span class="sxs-lookup"><span data-stu-id="ed176-123">Devices need to meet these requirements:</span></span>  <br/>  <span data-ttu-id="ed176-124">Windows 10 versie 1703 of hoger.</span><span class="sxs-lookup"><span data-stu-id="ed176-124">Windows 10, version 1703 or later.</span></span>  <br/>  <span data-ttu-id="ed176-125">Nieuwe apparaten die niet zijn door Windows out-of-box ervaring.</span><span class="sxs-lookup"><span data-stu-id="ed176-125">New devices that haven't been through Windows out-of-box experience.</span></span>  <br/> |
|<span data-ttu-id="ed176-126">Apparaat niet gevonden</span><span class="sxs-lookup"><span data-stu-id="ed176-126">Device not found</span></span>  <br/> |<span data-ttu-id="ed176-127">Deze fout betekent dat een of meer apparaten in uw CSV-bestand niet zijn geregistreerd bij uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="ed176-127">This error means that one or more devices in your CSV file isn't registered to your organization.</span></span> <span data-ttu-id="ed176-128">Om dit op te lossen, vraag uw hardwareleverancier om hulp.</span><span class="sxs-lookup"><span data-stu-id="ed176-128">To fix this, ask your hardware vendor for help.</span></span>  <br/> |
