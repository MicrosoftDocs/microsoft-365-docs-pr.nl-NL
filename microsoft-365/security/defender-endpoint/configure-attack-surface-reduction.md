---
title: Mogelijkheden voor het verminderen van kwetsbaarheid voor aanvallen configureren
description: Gebruik Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-cmdlets en Groepsbeleid om de oppervlakbeperking van aanvallen te configureren.
keywords: asr, attack surface reduction, windows defender, microsoft defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 948b5dc201526bf54aae0e857cfd40dcc9fe1e19
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984446"
---
# <a name="configure-attack-surface-reduction-capabilities"></a><span data-ttu-id="738c1-104">Mogelijkheden voor het verminderen van kwetsbaarheid voor aanvallen configureren</span><span class="sxs-lookup"><span data-stu-id="738c1-104">Configure attack surface reduction capabilities</span></span>

<span data-ttu-id="738c1-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="738c1-105">**Applies to:**</span></span>

- [<span data-ttu-id="738c1-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="738c1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="738c1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="738c1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="738c1-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="738c1-108">Want to experience Defender for Endpoint?</span></span> <span data-ttu-id="738c1-109">[Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)</span><span class="sxs-lookup"><span data-stu-id="738c1-109">[Sign up for a free trial](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink).</span></span>

<span data-ttu-id="738c1-110">Defender voor Eindpunt bevat verschillende mogelijkheden voor het verminderen van de surface van de aanval.</span><span class="sxs-lookup"><span data-stu-id="738c1-110">Defender for Endpoint includes several attack surface reduction capabilities.</span></span> <span data-ttu-id="738c1-111">Zie Overzicht van de mogelijkheden voor het verminderen van de surface [van de aanval voor meer informatie.](overview-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="738c1-111">To learn more, see [Overview of attack surface reduction capabilities](overview-attack-surface-reduction.md).</span></span> <span data-ttu-id="738c1-112">Als u de beperking van het oppervlak van de aanval in uw omgeving wilt configureren, gaat u als volgt te werk:</span><span class="sxs-lookup"><span data-stu-id="738c1-112">To configure attack surface reduction in your environment, follow these steps:</span></span>

1. <span data-ttu-id="738c1-113">[Schakel isolatie op basis van hardware in voor Microsoft Edge.](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard)</span><span class="sxs-lookup"><span data-stu-id="738c1-113">[Enable hardware-based isolation for Microsoft Edge](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard).</span></span>

2. <span data-ttu-id="738c1-114">Toepassingsbeheer inschakelen.</span><span class="sxs-lookup"><span data-stu-id="738c1-114">Enable application control.</span></span>

   1. <span data-ttu-id="738c1-115">Bekijk basisbeleid in Windows.</span><span class="sxs-lookup"><span data-stu-id="738c1-115">Review base policies in Windows.</span></span> <span data-ttu-id="738c1-116">Zie [Voorbeeldbasisbeleid.](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies)</span><span class="sxs-lookup"><span data-stu-id="738c1-116">See [Example Base Policies](/windows/security/threat-protection/windows-defender-application-control/example-wdac-base-policies).</span></span>
   2. <span data-ttu-id="738c1-117">Zie de [Windows Defender ontwerphandleiding voor toepassingsbeheer.](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide)</span><span class="sxs-lookup"><span data-stu-id="738c1-117">See the [Windows Defender Application Control design guide](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-design-guide).</span></span>
   3. <span data-ttu-id="738c1-118">Raadpleeg [Implementatie van Windows Defender WDAC-beleid (Application Control).](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide)</span><span class="sxs-lookup"><span data-stu-id="738c1-118">Refer to [Deploying Windows Defender Application Control (WDAC) policies](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control-deployment-guide).</span></span>

3. <span data-ttu-id="738c1-119">[Gecontroleerde maptoegang inschakelen.](enable-controlled-folders.md)</span><span class="sxs-lookup"><span data-stu-id="738c1-119">[Enable controlled folder access](enable-controlled-folders.md).</span></span>

4. <span data-ttu-id="738c1-120">[Schakel Netwerkbeveiliging in.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="738c1-120">[Turn on Network protection](enable-network-protection.md).</span></span>

5. <span data-ttu-id="738c1-121">[Exploitbeveiliging inschakelen.](enable-exploit-protection.md)</span><span class="sxs-lookup"><span data-stu-id="738c1-121">[Enable exploit protection](enable-exploit-protection.md).</span></span>

6. <span data-ttu-id="738c1-122">[Regels voor het verlagen van het oppervlak van de aanval configureren.](enable-attack-surface-reduction.md)</span><span class="sxs-lookup"><span data-stu-id="738c1-122">[Configure attack surface reduction rules](enable-attack-surface-reduction.md).</span></span>

7. <span data-ttu-id="738c1-123">Stel uw netwerkfirewall in.</span><span class="sxs-lookup"><span data-stu-id="738c1-123">Set up your network firewall.</span></span>

   1. <span data-ttu-id="738c1-124">Krijg een overzicht van [Windows Defender Firewall met geavanceerde beveiliging.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)</span><span class="sxs-lookup"><span data-stu-id="738c1-124">Get an overview of [Windows Defender Firewall with advanced security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).</span></span>
   2. <span data-ttu-id="738c1-125">Gebruik de [Windows Defender Firewall-ontwerphandleiding](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) om te bepalen hoe u uw firewallbeleid wilt ontwerpen.</span><span class="sxs-lookup"><span data-stu-id="738c1-125">Use the [Windows Defender Firewall design guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-design-guide) to decide how you want to design your firewall policies.</span></span>
   3. <span data-ttu-id="738c1-126">Gebruik de [Windows Defender firewall-implementatiehandleiding](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) om de firewall van uw organisatie in te stellen met geavanceerde beveiliging.</span><span class="sxs-lookup"><span data-stu-id="738c1-126">Use the [Windows Defender Firewall deployment guide](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide) to set up your organization's firewall with advanced security.</span></span>

> [!TIP]
> <span data-ttu-id="738c1-127">In de meeste gevallen kunt u bij het configureren van de mogelijkheden voor het verlagen van het oppervlak van de aanval kiezen uit verschillende methoden:</span><span class="sxs-lookup"><span data-stu-id="738c1-127">In most cases, when you configure attack surface reduction capabilities, you can choose from among several methods:</span></span>

> - <span data-ttu-id="738c1-128">Microsoft Endpoint Manager (die nu Microsoft Intune en Microsoft Endpoint Configuration Manager)</span><span class="sxs-lookup"><span data-stu-id="738c1-128">Microsoft Endpoint Manager (which now includes Microsoft Intune and Microsoft Endpoint Configuration Manager)</span></span>
> - <span data-ttu-id="738c1-129">Groepsbeleid</span><span class="sxs-lookup"><span data-stu-id="738c1-129">Group Policy</span></span>
> - <span data-ttu-id="738c1-130">PowerShell-cmdlets</span><span class="sxs-lookup"><span data-stu-id="738c1-130">PowerShell cmdlets</span></span>
