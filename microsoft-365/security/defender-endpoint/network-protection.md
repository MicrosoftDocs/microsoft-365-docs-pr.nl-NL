---
title: Netwerkbeveiliging gebruiken om verbindingen met slechte sites te voorkomen
description: Bescherm uw netwerk door te voorkomen dat gebruikers toegang krijgen tot bekende schadelijke en verdachte netwerkadressen
keywords: Netwerkbeveiliging, exploits, schadelijke website, ip, domein, domeinen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.topic: how-to
ms.openlocfilehash: 2ef3fbeec65be512dfe07f1d533df4d8e9b31532
ms.sourcegitcommit: 437bdbf3f99610869811e80432a59b5f244f7a87
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/08/2021
ms.locfileid: "51644498"
---
# <a name="protect-your-network"></a><span data-ttu-id="09bf3-104">Beveilig uw netwerk</span><span class="sxs-lookup"><span data-stu-id="09bf3-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="09bf3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="09bf3-105">**Applies to:**</span></span>
- [<span data-ttu-id="09bf3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="09bf3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="09bf3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="09bf3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="09bf3-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="09bf3-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="09bf3-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="09bf3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="09bf3-110">Netwerkbeveiliging helpt het aanvalsoppervlak van uw apparaten te beperken door gebeurtenissen op internet.</span><span class="sxs-lookup"><span data-stu-id="09bf3-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="09bf3-111">Hiermee voorkomt u dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten.</span><span class="sxs-lookup"><span data-stu-id="09bf3-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="09bf3-112">Netwerkbeveiliging breidt het bereik van [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) uit om al het uitgaande HTTP-verkeer te blokkeren dat probeert verbinding te maken met bronnen met een lage reputatie (op basis van het domein of de hostnaam).</span><span class="sxs-lookup"><span data-stu-id="09bf3-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="09bf3-113">Netwerkbeveiliging wordt ondersteund in Windows, te beginnen met Windows 10, versie 1709.</span><span class="sxs-lookup"><span data-stu-id="09bf3-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> 

<span data-ttu-id="09bf3-114">Zie Netwerkbeveiliging inschakelen voor meer informatie over het inschakelen van [netwerkbeveiliging.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="09bf3-114">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="09bf3-115">Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.</span><span class="sxs-lookup"><span data-stu-id="09bf3-115">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="09bf3-116">Zie de MICROSOFT Defender ATP-testsite op demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te zien hoe netwerkbeveiliging werkt.</span><span class="sxs-lookup"><span data-stu-id="09bf3-116">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="09bf3-117">Netwerkbeveiliging werkt het beste met [Microsoft Defender voor](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection)Eindpunt, waarmee u gedetailleerde rapportage krijgt over beveiligingsgebeurtenissen en blokken voor beveiligingsbeveiliging als onderdeel van [scenario's voor waarschuwingsonderzoek.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="09bf3-117">Network protection works best with [Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="09bf3-118">Wanneer netwerkbeveiliging een verbinding blokkeert, wordt er een melding weergegeven vanuit het Actiecentrum.</span><span class="sxs-lookup"><span data-stu-id="09bf3-118">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="09bf3-119">Uw beveiligingsteam kan [de melding aanpassen](customize-attack-surface-reduction.md#customize-the-notification) met de gegevens en contactgegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="09bf3-119">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="09bf3-120">Daarnaast kunnen afzonderlijke regels voor het verlagen van de aanvalsoppervlakken worden ingeschakeld en aangepast aan bepaalde technieken die u kunt controleren.</span><span class="sxs-lookup"><span data-stu-id="09bf3-120">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="09bf3-121">U kunt ook de [auditmodus gebruiken om](audit-windows-defender.md) te evalueren hoe netwerkbeveiliging van invloed is op uw organisatie als deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="09bf3-121">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="09bf3-122">Vereisten</span><span class="sxs-lookup"><span data-stu-id="09bf3-122">Requirements</span></span>

<span data-ttu-id="09bf3-123">Netwerkbeveiliging vereist Windows 10 Pro of Enterprise en Microsoft Defender Antivirus realtime beveiliging.</span><span class="sxs-lookup"><span data-stu-id="09bf3-123">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="09bf3-124">Windows-versie</span><span class="sxs-lookup"><span data-stu-id="09bf3-124">Windows version</span></span> | <span data-ttu-id="09bf3-125">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="09bf3-125">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="09bf3-126">Windows 10 versie 1709 of hoger</span><span class="sxs-lookup"><span data-stu-id="09bf3-126">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="09bf3-127">Windows Server 1803 of hoger</span><span class="sxs-lookup"><span data-stu-id="09bf3-127">Windows Server 1803 or later</span></span> | <span data-ttu-id="09bf3-128">[Microsoft Defender Antivirus realtime-beveiliging](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) en [beveiliging in](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) de cloud moeten zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="09bf3-128">[Microsoft Defender Antivirus real-time protection](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="09bf3-129">Nadat u de services hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om de verbindingen tussen de services en uw apparaten toe te staan (ook wel eindpunten genoemd).</span><span class="sxs-lookup"><span data-stu-id="09bf3-129">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- <span data-ttu-id="09bf3-130">.smartscreen.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="09bf3-130">.smartscreen.microsoft.com</span></span>
- <span data-ttu-id="09bf3-131">.smartscreen-prod.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="09bf3-131">.smartscreen-prod.microsoft.com</span></span>

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="09bf3-132">Gebeurtenissen op het gebied van netwerkbeveiliging bekijken in het Microsoft Defender for Endpoint Security Center</span><span class="sxs-lookup"><span data-stu-id="09bf3-132">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="09bf3-133">Microsoft Defender voor Eindpunt biedt gedetailleerde rapportage over gebeurtenissen en blokken als onderdeel van de [scenario's voor waarschuwingsonderzoek.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)</span><span class="sxs-lookup"><span data-stu-id="09bf3-133">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts).</span></span>

<span data-ttu-id="09bf3-134">U kunt Microsoft Defender opvragen voor eindpuntgegevens met behulp van [Geavanceerd zoeken.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection)</span><span class="sxs-lookup"><span data-stu-id="09bf3-134">You can query Microsoft Defender for Endpoint data by using [Advanced hunting](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection).</span></span> <span data-ttu-id="09bf3-135">Als u de [auditmodus gebruikt,](audit-windows-defender.md)kunt u geavanceerd zoeken gebruiken om te zien hoe de netwerkbeveiligingsinstellingen van invloed zijn op uw omgeving als deze zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="09bf3-135">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="09bf3-136">Hier is een voorbeeldquery</span><span class="sxs-lookup"><span data-stu-id="09bf3-136">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="09bf3-137">Netwerkbeveiligingsgebeurtenissen bekijken in Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="09bf3-137">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="09bf3-138">U kunt het Windows-gebeurtenislogboek bekijken om gebeurtenissen te bekijken die worden gemaakt wanneer netwerkbeveiligingsblokken (of audits) toegang tot een schadelijk IP- of domein blokkeert:</span><span class="sxs-lookup"><span data-stu-id="09bf3-138">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="09bf3-139">[Kopieer de XML rechtstreeks.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="09bf3-139">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="09bf3-140">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="09bf3-140">Select **OK**.</span></span>

<span data-ttu-id="09bf3-141">Met deze procedure wordt een aangepaste weergave gemaakt die filtert om alleen de volgende gebeurtenissen weer te geven die betrekking hebben op netwerkbeveiliging:</span><span class="sxs-lookup"><span data-stu-id="09bf3-141">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="09bf3-142">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="09bf3-142">Event ID</span></span> | <span data-ttu-id="09bf3-143">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="09bf3-143">Description</span></span> |
|:---|:---|
| <span data-ttu-id="09bf3-144">5007</span><span class="sxs-lookup"><span data-stu-id="09bf3-144">5007</span></span> | <span data-ttu-id="09bf3-145">Gebeurtenis wanneer instellingen worden gewijzigd</span><span class="sxs-lookup"><span data-stu-id="09bf3-145">Event when settings are changed</span></span> |
| <span data-ttu-id="09bf3-146">1125</span><span class="sxs-lookup"><span data-stu-id="09bf3-146">1125</span></span> | <span data-ttu-id="09bf3-147">Gebeurtenis wanneer netwerkbeveiliging wordt uitgevoerd in de auditmodus</span><span class="sxs-lookup"><span data-stu-id="09bf3-147">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="09bf3-148">1126</span><span class="sxs-lookup"><span data-stu-id="09bf3-148">1126</span></span> | <span data-ttu-id="09bf3-149">Gebeurtenis wanneer netwerkbeveiliging wordt branden in de blokmodus</span><span class="sxs-lookup"><span data-stu-id="09bf3-149">Event when network protection fires in block mode</span></span> |

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="09bf3-150">Problemen met netwerkbeveiliging oplossen</span><span class="sxs-lookup"><span data-stu-id="09bf3-150">Network protection troubleshooting</span></span>

<span data-ttu-id="09bf3-151">Vanwege de omgeving waarin Netwerkbeveiliging wordt uitgevoerd, kan Microsoft mogelijk geen proxy-instellingen voor het besturingssysteem detecteren.</span><span class="sxs-lookup"><span data-stu-id="09bf3-151">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="09bf3-152">In sommige gevallen kunnen Network Protection-clients geen cloudservice bereiken.</span><span class="sxs-lookup"><span data-stu-id="09bf3-152">In some cases, Network Protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="09bf3-153">Als u het verbindingsprobleem wilt oplossen, moeten klanten met E5-licenties een van de volgende registersleutels van Defender configureren:</span><span class="sxs-lookup"><span data-stu-id="09bf3-153">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="09bf3-154">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="09bf3-154">Related articles</span></span>

- <span data-ttu-id="09bf3-155">[Netwerkbeveiliging evalueren |](evaluate-network-protection.md) Maak een snel scenario waarin wordt gedemonstreerd hoe de functie werkt en welke gebeurtenissen gewoonlijk worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="09bf3-155">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="09bf3-156">[Netwerkbeveiliging inschakelen](enable-network-protection.md) | Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.</span><span class="sxs-lookup"><span data-stu-id="09bf3-156">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
