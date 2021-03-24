---
title: Ondersteunde API's van Microsoft Defender Advanced Threat Protection
description: Meer informatie over de specifieke responsgerelateerde Microsoft Defender Advanced Threat Protection API-oproepen.
keywords: antwoord-api's, graph api, ondersteunde api's, actor, waarschuwingen, apparaat, gebruiker, domein, ip, bestand
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.openlocfilehash: 93184cc82972a4b1c970b026ceff78adbc1fb7f8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057322"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a><span data-ttu-id="7bb6d-104">Ondersteunde API's voor Microsoft Defender voor eindpuntquery's</span><span class="sxs-lookup"><span data-stu-id="7bb6d-104">Supported Microsoft Defender for Endpoint query APIs</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7bb6d-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="7bb6d-105">**Applies to:**</span></span>
- [<span data-ttu-id="7bb6d-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="7bb6d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)

> [!TIP]
> <span data-ttu-id="7bb6d-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="7bb6d-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="7bb6d-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-supported-response-apis-abovefoldlink) 

<span data-ttu-id="7bb6d-109">Meer informatie over de ondersteunde API-oproepen die u kunt uitvoeren en details, zoals de vereiste aanvraagkoppen en de verwachte reactie van de oproepen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-109">Learn about the supported response-related API calls you can run and details such as the required request headers, and expected response from the calls.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="7bb6d-110">In deze sectie</span><span class="sxs-lookup"><span data-stu-id="7bb6d-110">In this section</span></span>
<span data-ttu-id="7bb6d-111">Onderwerp</span><span class="sxs-lookup"><span data-stu-id="7bb6d-111">Topic</span></span> | <span data-ttu-id="7bb6d-112">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="7bb6d-112">Description</span></span>
:---|:---
<span data-ttu-id="7bb6d-113">Onderzoekspakket verzamelen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-113">Collect investigation package</span></span> | <span data-ttu-id="7bb6d-114">Voer deze API uit om een onderzoekspakket van een apparaat te verzamelen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-114">Run this API to collect an investigation package from a device.</span></span>
<span data-ttu-id="7bb6d-115">Apparaat isoleren</span><span class="sxs-lookup"><span data-stu-id="7bb6d-115">Isolate device</span></span> | <span data-ttu-id="7bb6d-116">Voer deze API uit om een apparaat van het netwerk te isoleren.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-116">Run this API to isolate a device from the network.</span></span>
<span data-ttu-id="7bb6d-117">Unisolate-apparaat</span><span class="sxs-lookup"><span data-stu-id="7bb6d-117">Unisolate device</span></span> | <span data-ttu-id="7bb6d-118">Een apparaat uit isolatie verwijderen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-118">Remove a device from isolation.</span></span> 
<span data-ttu-id="7bb6d-119">De uitvoering van code beperken</span><span class="sxs-lookup"><span data-stu-id="7bb6d-119">Restrict code execution</span></span> | <span data-ttu-id="7bb6d-120">Voer deze API uit om een aanval te bevatten door schadelijke processen te stoppen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-120">Run this API to contain an attack by stopping malicious processes.</span></span> <span data-ttu-id="7bb6d-121">U kunt ook een apparaat vergrendelen en voorkomen dat volgende pogingen van potentieel schadelijke programma's worden uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-121">You can also lock down a device and prevent subsequent attempts of potentially malicious programs from running.</span></span>
<span data-ttu-id="7bb6d-122">Unrestrict code execution</span><span class="sxs-lookup"><span data-stu-id="7bb6d-122">Unrestrict code execution</span></span> | <span data-ttu-id="7bb6d-123">Voer dit uit om de beperking van het toepassingsbeleid terug te draaien nadat u hebt geverifieerd dat het gecompromitteerde apparaat is opgelost.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-123">Run this to reverse the restriction of applications policy after you have verified that the compromised device has been remediated.</span></span>
<span data-ttu-id="7bb6d-124">Antivirusscan uitvoeren</span><span class="sxs-lookup"><span data-stu-id="7bb6d-124">Run antivirus scan</span></span> | <span data-ttu-id="7bb6d-125">Start op afstand een antivirusscan om malware te identificeren en te herstellen die mogelijk aanwezig is op een gecompromitteerd apparaat.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-125">Remotely initiate an antivirus scan to help identify and remediate malware that might be present on a compromised device.</span></span>
<span data-ttu-id="7bb6d-126">Bestand stoppen en in quarantaine plaatsen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-126">Stop and quarantine file</span></span> |  <span data-ttu-id="7bb6d-127">Voer deze oproep uit om het uitvoeren van processen, quarantainebestanden en het verwijderen van de persistentie, zoals registersleutels, te stoppen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-127">Run this call to stop running processes, quarantine  files, and delete persistency such as registry keys.</span></span>
<span data-ttu-id="7bb6d-128">Voorbeeld aanvragen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-128">Request sample</span></span> | <span data-ttu-id="7bb6d-129">Voer deze oproep uit om een voorbeeld van een bestand op te vragen vanaf een bepaald apparaat.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-129">Run this call to request a sample of a file from a specific device.</span></span> <span data-ttu-id="7bb6d-130">Het bestand wordt verzameld vanaf het apparaat en geüpload naar een veilige opslag.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-130">The file will be collected from the device and uploaded to a secure storage.</span></span>
<span data-ttu-id="7bb6d-131">Bestand blokkeren</span><span class="sxs-lookup"><span data-stu-id="7bb6d-131">Block file</span></span> | <span data-ttu-id="7bb6d-132">Voer deze API uit om verdere verspreiding van een aanval in uw organisatie te voorkomen door potentieel schadelijke bestanden of vermoedelijke malware te verbieden.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-132">Run this API to prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> 
<span data-ttu-id="7bb6d-133">Bestand deblokkeren</span><span class="sxs-lookup"><span data-stu-id="7bb6d-133">Unblock file</span></span> | <span data-ttu-id="7bb6d-134">Een bestand toestaan dat in de organisatie wordt uitgevoerd met Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-134">Allow a file run in the organization using Microsoft Defender Antivirus.</span></span>
<span data-ttu-id="7bb6d-135">Sas URI-pakket krijgen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-135">Get package SAS URI</span></span> | <span data-ttu-id="7bb6d-136">Voer deze API uit om een URI te downloaden waarmee u een onderzoekspakket kunt downloaden.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-136">Run this API to get a URI that allows downloading an investigation package.</span></span>
<span data-ttu-id="7bb6d-137">MachineAction-object krijgen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-137">Get MachineAction object</span></span> | <span data-ttu-id="7bb6d-138">Voer deze API uit om MachineAction-object op te halen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-138">Run this API to get MachineAction object.</span></span>
<span data-ttu-id="7bb6d-139">MachineActions-verzameling ophalen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-139">Get MachineActions collection</span></span> | <span data-ttu-id="7bb6d-140">Voer dit uit om MachineAction-verzameling op te halen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-140">Run this to get MachineAction collection.</span></span>
<span data-ttu-id="7bb6d-141">FileActions-verzameling ophalen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-141">Get FileActions collection</span></span> | <span data-ttu-id="7bb6d-142">Voer deze API uit om FileActions-verzameling op te halen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-142">Run this API to get FileActions collection.</span></span>
<span data-ttu-id="7bb6d-143">Object FileMachineAction downloaden</span><span class="sxs-lookup"><span data-stu-id="7bb6d-143">Get FileMachineAction object</span></span> | <span data-ttu-id="7bb6d-144">Voer deze API uit om FileMachineAction-object op te halen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-144">Run this API to get FileMachineAction object.</span></span>
<span data-ttu-id="7bb6d-145">FileMachineActions-verzameling ophalen</span><span class="sxs-lookup"><span data-stu-id="7bb6d-145">Get FileMachineActions collection</span></span> | <span data-ttu-id="7bb6d-146">Voer deze API uit om FileMachineAction-verzameling op te halen.</span><span class="sxs-lookup"><span data-stu-id="7bb6d-146">Run this API to get FileMachineAction collection.</span></span>
