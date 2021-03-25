---
title: Aanvalsoppervlakverkorting configureren
description: Gebruik Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets en Groepsbeleid om de surface-beperking van aanvallen te configureren.
keywords: asr, attack surface reduction, windows defender, microsoft defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166159"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="87db0-104">Aanvalsoppervlakverkorting configureren</span><span class="sxs-lookup"><span data-stu-id="87db0-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="87db0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="87db0-105">**Applies to:**</span></span>
- [<span data-ttu-id="87db0-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="87db0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="87db0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87db0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="87db0-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="87db0-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="87db0-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="87db0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="87db0-110">U kunt de beperking van de attack surface configureren met veel hulpmiddelen, waaronder:</span><span class="sxs-lookup"><span data-stu-id="87db0-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="87db0-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="87db0-111">Microsoft Intune</span></span>
* <span data-ttu-id="87db0-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="87db0-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="87db0-113">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="87db0-113">Group Policy</span></span>
* <span data-ttu-id="87db0-114">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="87db0-114">PowerShell cmdlets</span></span>

<span data-ttu-id="87db0-115">Artikel</span><span class="sxs-lookup"><span data-stu-id="87db0-115">Article</span></span> | <span data-ttu-id="87db0-116">Beschrijving</span><span class="sxs-lookup"><span data-stu-id="87db0-116">Description</span></span>
-|-
[<span data-ttu-id="87db0-117">Isolatie op basis van hardware inschakelen voor Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="87db0-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="87db0-118">Application Guard voorbereiden en installeren, inclusief hardware- en softwarevereisten</span><span class="sxs-lookup"><span data-stu-id="87db0-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="87db0-119">Toepassingsbesturingselement inschakelen</span><span class="sxs-lookup"><span data-stu-id="87db0-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="87db0-120">Toepassingen van gebruikers controleren en kernelmodusprocessen beveiligen</span><span class="sxs-lookup"><span data-stu-id="87db0-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="87db0-121">Beveiliging misbruiken</span><span class="sxs-lookup"><span data-stu-id="87db0-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="87db0-122">Gebruiksbeperkingstechnieken automatisch toepassen op zowel besturingssysteemprocessen als op afzonderlijke apps</span><span class="sxs-lookup"><span data-stu-id="87db0-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="87db0-123">Netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="87db0-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="87db0-124">Voorkomen dat gebruikers apps gebruiken om toegang te krijgen tot gevaarlijke domeinen</span><span class="sxs-lookup"><span data-stu-id="87db0-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="87db0-125">Gecontroleerde maptoegang</span><span class="sxs-lookup"><span data-stu-id="87db0-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="87db0-126">Waardevolle gegevens beschermen tegen schadelijke apps</span><span class="sxs-lookup"><span data-stu-id="87db0-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="87db0-127">Surface-beperking voor aanvallen</span><span class="sxs-lookup"><span data-stu-id="87db0-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="87db0-128">Acties en apps voorkomen die gewoonlijk worden gebruikt door malware die op zoek is naar misbruik</span><span class="sxs-lookup"><span data-stu-id="87db0-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="87db0-129">Netwerkfirewall</span><span class="sxs-lookup"><span data-stu-id="87db0-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="87db0-130">Apparaten en gegevens in een netwerk beveiligen</span><span class="sxs-lookup"><span data-stu-id="87db0-130">How to protect devices and data across a network</span></span>

