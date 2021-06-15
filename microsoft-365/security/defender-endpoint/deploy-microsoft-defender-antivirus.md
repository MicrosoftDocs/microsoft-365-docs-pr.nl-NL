---
title: Microsoft Defender Antivirus implementeren en inschakelen
description: Implementeer Microsoft Defender Antivirus voor de beveiliging van uw eindpunten met Microsoft Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell-cmdlets of WMI.
keywords: implementeren, inschakelen, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
ms.topic: conceptual
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 01/06/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: a847e65adb0402d4c5f98e19424677ccdc1011da
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925741"
---
# <a name="deploy-and-enable-microsoft-defender-antivirus"></a><span data-ttu-id="811b4-104">Microsoft Defender Antivirus implementeren en inschakelen</span><span class="sxs-lookup"><span data-stu-id="811b4-104">Deploy and enable Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="811b4-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="811b4-105">**Applies to:**</span></span>

- [<span data-ttu-id="811b4-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="811b4-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="811b4-107">Afhankelijk van het beheerprogramma dat u gebruikt, moet u de beveiliging mogelijk specifiek Microsoft Defender Antivirus configureren.</span><span class="sxs-lookup"><span data-stu-id="811b4-107">Depending on the management tool you are using, you may need to specifically enable or configure Microsoft Defender Antivirus protection.</span></span> 

<span data-ttu-id="811b4-108">Zie de tabel in [Implementeren,](deploy-manage-report-microsoft-defender-antivirus.md#ref2) beheren en rapporteren over Microsoft Defender Antivirus voor instructies over het inschakelen van beveiliging met Microsoft Intune, Microsoft Endpoint Configuration Manager, Groepsbeleid, Active Directory, Microsoft Azure, PowerShell-cmdlets en Windows Management Instruction (WMI).</span><span class="sxs-lookup"><span data-stu-id="811b4-108">See the table in [Deploy, manage, and report on Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md#ref2) for instructions on how to enable protection with Microsoft Intune, Microsoft Endpoint Configuration Manager, Group Policy, Active Directory, Microsoft Azure, PowerShell cmdlets, and Windows Management Instruction (WMI).</span></span>

<span data-ttu-id="811b4-109">Voor sommige scenario's is meer informatie nodig over het implementeren of configureren van Microsoft Defender Antivirus beveiliging, zoals VDI-omgevingen (Virtual Desktop Infrastructure).</span><span class="sxs-lookup"><span data-stu-id="811b4-109">Some scenarios require more guidance on how to successfully deploy or configure Microsoft Defender Antivirus protection, such as Virtual Desktop Infrastructure (VDI) environments.</span></span>

<span data-ttu-id="811b4-110">Het resterende artikel in deze sectie bevat end-to-end-adviezen en best practices voor het instellen van Microsoft Defender Antivirus op virtuele [machines (VM's) in een VDI- of Extern Bureaublad Services-omgeving (RDS).](deployment-vdi-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="811b4-110">The remaining article in this section provides end-to-end advice and best practices for [setting up Microsoft Defender Antivirus on virtual machines (VMs) in a VDI or Remote Desktop Services (RDS) environment](deployment-vdi-microsoft-defender-antivirus.md).</span></span>

## <a name="related-articles"></a><span data-ttu-id="811b4-111">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="811b4-111">Related articles</span></span>

- [<span data-ttu-id="811b4-112">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="811b4-112">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="811b4-113">Updates implementeren, beheren en rapporteren op Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="811b4-113">Deploy, manage updates, and report on Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)
- [<span data-ttu-id="811b4-114">Implementatiehandleiding voor Microsoft Defender Antivirus in een VDI-omgeving (Virtual Desktop Infrastructure)</span><span class="sxs-lookup"><span data-stu-id="811b4-114">Deployment guide for Microsoft Defender Antivirus in a virtual desktop infrastructure (VDI) environment</span></span>](deployment-vdi-microsoft-defender-antivirus.md)