---
title: Controleren en rapporteren over Microsoft Defender Antivirus beveiliging
description: Gebruik Configuratiebeheer of hulpprogramma's voor beveiligingsgegevens en gebeurtenisbeheer (SIEM) om rapporten te gebruiken en Microsoft Defender AV te controleren met PowerShell en WMI.
keywords: siem, monitor, rapport, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/07/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 91891af35def83f21b3db8c7e8fa4b320bef563c
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926161"
---
# <a name="report-on-microsoft-defender-antivirus"></a><span data-ttu-id="59f55-104">Rapporteren in Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="59f55-104">Report on Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="59f55-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="59f55-105">**Applies to:**</span></span>

- [<span data-ttu-id="59f55-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="59f55-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="59f55-107">Microsoft Defender Antivirus is ingebouwd in Windows 10, Windows Server 2019 en Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="59f55-107">Microsoft Defender Antivirus is built into Windows 10, Windows Server 2019, and Windows Server 2016.</span></span> <span data-ttu-id="59f55-108">Microsoft Defender Antivirus is van uw volgende generatie beveiliging in Microsoft Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="59f55-108">Microsoft Defender Antivirus is of your next-generation protection in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="59f55-109">Beveiliging van de volgende generatie helpt uw apparaten te beschermen tegen softwaredreigingen zoals virussen, malware en spyware in e-mail, apps, de cloud en het web.</span><span class="sxs-lookup"><span data-stu-id="59f55-109">Next-generation protection helps protect your devices from software threats like viruses, malware, and spyware across email, apps, the cloud, and the web.</span></span>

<span data-ttu-id="59f55-110">Met Microsoft Defender Antivirus hebt u verschillende opties voor het controleren van de beveiligingsstatus en waarschuwingen.</span><span class="sxs-lookup"><span data-stu-id="59f55-110">With Microsoft Defender Antivirus, you have several options for reviewing protection status and alerts.</span></span> <span data-ttu-id="59f55-111">U kunt de Microsoft Endpoint Manager gebruiken om [de Microsoft Defender Antivirus te](/configmgr/protect/deploy-use/monitor-endpoint-protection) controleren of [e-mailwaarschuwingen te maken.](/configmgr/protect/deploy-use/endpoint-configure-alerts)</span><span class="sxs-lookup"><span data-stu-id="59f55-111">You can use Microsoft Endpoint Manager to [monitor Microsoft Defender Antivirus](/configmgr/protect/deploy-use/monitor-endpoint-protection) or [create email alerts](/configmgr/protect/deploy-use/endpoint-configure-alerts).</span></span> <span data-ttu-id="59f55-112">U kunt ook de beveiliging controleren [met](/intune/introduction-intune)Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="59f55-112">Or, you can monitor protection using [Microsoft Intune](/intune/introduction-intune).</span></span>  

<span data-ttu-id="59f55-113">Microsoft Operations Management Suite heeft een [update compliance-invoegvoeging](/windows/deployment/update/update-compliance-get-started) die rapporteert over belangrijke Microsoft Defender Antivirus problemen, waaronder beveiligingsupdates en realtime beveiligingsinstellingen.</span><span class="sxs-lookup"><span data-stu-id="59f55-113">Microsoft Operations Management Suite has an [Update Compliance add-in](/windows/deployment/update/update-compliance-get-started) that reports on key Microsoft Defender Antivirus issues, including protection updates and real-time protection settings.</span></span>

<span data-ttu-id="59f55-114">Als u een SIEM-server (Security Information and Event Management) van derden hebt, kunt u ook de clientgebeurtenissen Windows Defender [gebruiken.](/windows/win32/events/windows-events)</span><span class="sxs-lookup"><span data-stu-id="59f55-114">If you have a third-party security information and event management (SIEM) server, you can also consume [Windows Defender client events](/windows/win32/events/windows-events).</span></span> 

<span data-ttu-id="59f55-115">Windows gebeurtenissen bestaan uit verschillende bronnen voor beveiligingsgebeurtenissen, waaronder SAM-gebeurtenissen (verbeterd voor[Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), zie ook het onderwerp [Beveiligingsaudit)](/windows/device-security/auditing/security-auditing-overview) [en Windows Defender gebeurtenissen.](troubleshoot-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="59f55-115">Windows events comprise several security event sources, including Security Account Manager (SAM) events ([enhanced for Windows 10](/windows/whats-new/whats-new-windows-10-version-1507-and-1511), also see the [Security auditing](/windows/device-security/auditing/security-auditing-overview) topic) and  [Windows Defender events](troubleshoot-microsoft-defender-antivirus.md).</span></span> 

<span data-ttu-id="59f55-116">Deze gebeurtenissen kunnen centraal worden samengevoegd met de [Windows gebeurtenisverzamelaar.](/windows/win32/wec/windows-event-collector)</span><span class="sxs-lookup"><span data-stu-id="59f55-116">These events can be centrally aggregated using the [Windows event collector](/windows/win32/wec/windows-event-collector).</span></span> <span data-ttu-id="59f55-117">SIEM-servers hebben vaak connectors voor Windows gebeurtenissen, zodat u alle beveiligingsgebeurtenissen in uw SIEM-server kunt correleren.</span><span class="sxs-lookup"><span data-stu-id="59f55-117">Often, SIEM servers have connectors for Windows events, allowing you to correlate all security events in your SIEM server.</span></span> 

<span data-ttu-id="59f55-118">U kunt ook [malwaregebeurtenissen controleren met behulp van de malwarebeoordelingsoplossing in Log Analytics.](/azure/log-analytics/log-analytics-malware)</span><span class="sxs-lookup"><span data-stu-id="59f55-118">You can also [monitor malware events using the Malware Assessment solution in Log Analytics](/azure/log-analytics/log-analytics-malware).</span></span>

<span data-ttu-id="59f55-119">Zie de tabel [(Implementatie,](deploy-manage-report-microsoft-defender-antivirus.md#ref2)beheer en rapportageopties) voor het controleren of bepalen van de status met PowerShell, WMI of Microsoft Azure.</span><span class="sxs-lookup"><span data-stu-id="59f55-119">For monitoring or determining status with PowerShell, WMI, or Microsoft Azure, see the [(Deployment, management, and reporting options table)](deploy-manage-report-microsoft-defender-antivirus.md#ref2).</span></span>

## <a name="related-articles"></a><span data-ttu-id="59f55-120">Aanverwante artikelen</span><span class="sxs-lookup"><span data-stu-id="59f55-120">Related articles</span></span>

- [<span data-ttu-id="59f55-121">Microsoft Defender Antivirus in Windows 10</span><span class="sxs-lookup"><span data-stu-id="59f55-121">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="59f55-122">Microsoft Defender Antivirus op Windows Server 2016 en 2019</span><span class="sxs-lookup"><span data-stu-id="59f55-122">Microsoft Defender Antivirus on Windows Server 2016 and 2019</span></span>](microsoft-defender-antivirus-on-windows-server.md)
- [<span data-ttu-id="59f55-123">Implementatie van Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="59f55-123">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)