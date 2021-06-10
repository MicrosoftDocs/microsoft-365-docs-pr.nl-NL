---
title: Isolatie op basis van hardware (Windows 10)
ms.reviewer: ''
description: Meer informatie over hoe isolatie op basis van hardware in Windows 10 helpt bij het bestrijden van malware.
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.author: macapara
ms.date: 09/07/2018
ms.technology: mde
ms.openlocfilehash: b3babf858ac19e70119a2dc6a58b25359f1b05c1
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842984"
---
# <a name="hardware-based-isolation-in-windows-10"></a><span data-ttu-id="df12c-103">Hardwaregebaseerde isolatie in Windows 10</span><span class="sxs-lookup"><span data-stu-id="df12c-103">Hardware-based isolation in Windows 10</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="df12c-104">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="df12c-104">**Applies to:**</span></span>
- [<span data-ttu-id="df12c-105">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="df12c-105">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="df12c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="df12c-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="df12c-107">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="df12c-107">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="df12c-108">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="df12c-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="df12c-109">Op hardware gebaseerde isolatie beschermt de systeemintegriteit in Windows 10 en is geïntegreerd met Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="df12c-109">Hardware-based isolation helps protect system integrity in Windows 10 and is integrated with Microsoft Defender for Endpoint.</span></span> 

| <span data-ttu-id="df12c-110">Functie</span><span class="sxs-lookup"><span data-stu-id="df12c-110">Feature</span></span> | <span data-ttu-id="df12c-111">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="df12c-111">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="df12c-112">Windows Defender Application Guard</span><span class="sxs-lookup"><span data-stu-id="df12c-112">Windows Defender Application Guard</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/md-app-guard-overview.md) | <span data-ttu-id="df12c-113">Application Guard beschermt uw apparaat tegen geavanceerde aanvallen terwijl u productief blijft.</span><span class="sxs-lookup"><span data-stu-id="df12c-113">Application Guard protects your device from advanced attacks while keeping you productive.</span></span> <span data-ttu-id="df12c-114">Met behulp van een unieke isolatiebenadering op hardwarebasis is het doel om niet-vertrouwde websites en PDF-documenten te isoleren in een lichtgewicht container die is gescheiden van het besturingssysteem via de native Windows Hypervisor.</span><span class="sxs-lookup"><span data-stu-id="df12c-114">Using a unique hardware-based isolation approach, the goal is to isolate untrusted websites and PDF documents inside a lightweight container that is separated from the operating system via the native Windows Hypervisor.</span></span> <span data-ttu-id="df12c-115">Als een niet-vertrouwde site of PDF-document schadelijk blijkt te zijn, blijft het nog steeds opgenomen in de beveiligde container van Application Guard, waardoor de desktop-pc wordt beveiligd en de aanvaller niet wordt verwijderd van uw bedrijfsgegevens.</span><span class="sxs-lookup"><span data-stu-id="df12c-115">If an untrusted site or PDF document turns out to be malicious, it still remains contained within Application Guard’s secure container, keeping the desktop PC protected and the attacker away from your enterprise data.</span></span> |
| [<span data-ttu-id="df12c-116">Windows Defender Systeembeveiliger</span><span class="sxs-lookup"><span data-stu-id="df12c-116">Windows Defender System Guard</span></span>](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows.md) | <span data-ttu-id="df12c-117">System Guard beschermt en behoudt de integriteit van het systeem wanneer het wordt gestart en nadat het wordt uitgevoerd, en valideert de systeemintegriteit met behulp van een bevestiging.</span><span class="sxs-lookup"><span data-stu-id="df12c-117">System Guard protects and maintains the integrity of the system as it starts and after it's running, and validates system integrity by using attestation.</span></span>  |

