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
ms.topic: how-to
ms.openlocfilehash: ae7dbea7d476e8a8f6198378e1d1bb29e24c37a2
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688343"
---
# <a name="protect-your-network"></a><span data-ttu-id="e1da0-104">Beveilig uw netwerk</span><span class="sxs-lookup"><span data-stu-id="e1da0-104">Protect your network</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e1da0-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="e1da0-105">**Applies to:**</span></span>
- [<span data-ttu-id="e1da0-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="e1da0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e1da0-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e1da0-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="e1da0-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="e1da0-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e1da0-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="e1da0-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e1da0-110">Netwerkbeveiliging helpt het aanvalsoppervlak van uw apparaten te beperken door gebeurtenissen op internet.</span><span class="sxs-lookup"><span data-stu-id="e1da0-110">Network protection helps reduce the attack surface of your devices from Internet-based events.</span></span> <span data-ttu-id="e1da0-111">Hiermee voorkomt u dat werknemers elke toepassing gebruiken om toegang te krijgen tot gevaarlijke domeinen die phishingpraktijken, exploits en andere schadelijke inhoud op internet kunnen hosten.</span><span class="sxs-lookup"><span data-stu-id="e1da0-111">It prevents employees from using any application to access dangerous domains that might host phishing scams, exploits, and other malicious content on the Internet.</span></span> <span data-ttu-id="e1da0-112">Netwerkbeveiliging breidt het bereik van [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) uit om al het uitgaande HTTP-verkeer te blokkeren dat probeert verbinding te maken met bronnen met een lage reputatie (op basis van het domein of de hostnaam).</span><span class="sxs-lookup"><span data-stu-id="e1da0-112">Network protection expands the scope of [Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) to block all outbound HTTP(s) traffic that attempts to connect to low-reputation sources (based on the domain or hostname).</span></span>

<span data-ttu-id="e1da0-113">Netwerkbeveiliging wordt ondersteund in Windows, te beginnen met Windows 10, versie 1709.</span><span class="sxs-lookup"><span data-stu-id="e1da0-113">Network protection is supported on Windows, beginning with Windows 10, version 1709.</span></span> <span data-ttu-id="e1da0-114">Netwerkbeveiliging wordt nog niet ondersteund op andere besturingssystemen, maar webbeveiliging wordt ondersteund met behulp van de nieuwe Microsoft Edge op basis van Chromium.</span><span class="sxs-lookup"><span data-stu-id="e1da0-114">Network protection is not yet supported on other operating systems, but web protection is supported using th new Microsoft Edge based on Chromium.</span></span> <span data-ttu-id="e1da0-115">Zie Webbeveiliging voor [meer informatie.](web-protection-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-115">To learn more, see [Web protection](web-protection-overview.md).</span></span>

<span data-ttu-id="e1da0-116">netwerkbeveiliging breidt de beveiliging in [webbeveiliging uit](web-protection-overview.md) tot het besturingssysteemniveau.</span><span class="sxs-lookup"><span data-stu-id="e1da0-116">network protection extends the protection in [Web protection](web-protection-overview.md) to the operating system level.</span></span> <span data-ttu-id="e1da0-117">Het biedt functionaliteit voor webbeveiliging in Edge voor andere ondersteunde browsers en niet-browsertoepassingen.</span><span class="sxs-lookup"><span data-stu-id="e1da0-117">It provides web protection functionality in Edge to other supported browsers and non-browser applications.</span></span> <span data-ttu-id="e1da0-118">Daarnaast biedt netwerkbeveiliging zichtbaarheid en blokkering van indicatoren voor compromissen (IOC's) wanneer deze worden gebruikt met [de detectie en reactie van eindpunten.](overview-endpoint-detection-response.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-118">In addition, network protection provides visibility and blocking of indicators of compromise (IOCs) when used with [Endpoint detection and response](overview-endpoint-detection-response.md).</span></span> <span data-ttu-id="e1da0-119">Netwerkbeveiliging werkt bijvoorbeeld met uw [aangepaste indicatoren.](manage-indicators.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-119">For example, network protection works with your [custom indicators](manage-indicators.md).</span></span>

<span data-ttu-id="e1da0-120">Zie Netwerkbeveiliging inschakelen voor meer informatie over het inschakelen van [netwerkbeveiliging.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-120">For more information about how to enable network protection, see [Enable network protection](enable-network-protection.md).</span></span> <span data-ttu-id="e1da0-121">Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.</span><span class="sxs-lookup"><span data-stu-id="e1da0-121">Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>

> [!TIP]
> <span data-ttu-id="e1da0-122">Zie de MICROSOFT Defender ATP-testsite op demo.wd.microsoft.com [om](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) te zien hoe netwerkbeveiliging werkt.</span><span class="sxs-lookup"><span data-stu-id="e1da0-122">See the Microsoft Defender ATP testground site at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to see how network protection works.</span></span>

<span data-ttu-id="e1da0-123">Netwerkbeveiliging werkt het beste met [Microsoft Defender voor](microsoft-defender-endpoint.md)Eindpunt, waarmee u gedetailleerde rapportage krijgt over beveiligingsgebeurtenissen en blokken voor beveiligingsbeveiliging als onderdeel van [scenario's voor waarschuwingsonderzoek.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-123">Network protection works best with [Microsoft Defender for Endpoint](microsoft-defender-endpoint.md), which gives you detailed reporting into exploit protection events and blocks as part of [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="e1da0-124">Wanneer netwerkbeveiliging een verbinding blokkeert, wordt er een melding weergegeven vanuit het Actiecentrum.</span><span class="sxs-lookup"><span data-stu-id="e1da0-124">When network protection blocks a connection, a notification is displayed from the Action Center.</span></span> <span data-ttu-id="e1da0-125">Uw beveiligingsteam kan [de melding aanpassen](customize-attack-surface-reduction.md#customize-the-notification) met de gegevens en contactgegevens van uw organisatie.</span><span class="sxs-lookup"><span data-stu-id="e1da0-125">Your security operations team can [customize the notification](customize-attack-surface-reduction.md#customize-the-notification) with your organization's details and contact information.</span></span> <span data-ttu-id="e1da0-126">Daarnaast kunnen afzonderlijke regels voor het verlagen van de aanvalsoppervlakken worden ingeschakeld en aangepast aan bepaalde technieken die u kunt controleren.</span><span class="sxs-lookup"><span data-stu-id="e1da0-126">In addition, individual attack surface reduction rules can be enabled and customized to suit certain techniques to monitor.</span></span>

<span data-ttu-id="e1da0-127">U kunt ook de [auditmodus gebruiken om](audit-windows-defender.md) te evalueren hoe netwerkbeveiliging van invloed is op uw organisatie als deze is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1da0-127">You can also use [audit mode](audit-windows-defender.md) to evaluate how network protection would impact your organization if it were enabled.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1da0-128">Vereisten</span><span class="sxs-lookup"><span data-stu-id="e1da0-128">Requirements</span></span>

<span data-ttu-id="e1da0-129">Netwerkbeveiliging vereist Windows 10 Pro of Enterprise en Microsoft Defender Antivirus realtime beveiliging.</span><span class="sxs-lookup"><span data-stu-id="e1da0-129">Network protection requires Windows 10 Pro or Enterprise, and Microsoft Defender Antivirus real-time protection.</span></span>

| <span data-ttu-id="e1da0-130">Windows-versie</span><span class="sxs-lookup"><span data-stu-id="e1da0-130">Windows version</span></span> | <span data-ttu-id="e1da0-131">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="e1da0-131">Microsoft Defender Antivirus</span></span> |
|:---|:---|
| <span data-ttu-id="e1da0-132">Windows 10 versie 1709 of hoger</span><span class="sxs-lookup"><span data-stu-id="e1da0-132">Windows 10 version 1709 or later</span></span> <p><span data-ttu-id="e1da0-133">Windows Server 1803 of hoger</span><span class="sxs-lookup"><span data-stu-id="e1da0-133">Windows Server 1803 or later</span></span> | <span data-ttu-id="e1da0-134">[Microsoft Defender Antivirus realtime-beveiliging](configure-real-time-protection-microsoft-defender-antivirus.md) en [beveiliging in](enable-cloud-protection-microsoft-defender-antivirus.md) de cloud moeten zijn ingeschakeld</span><span class="sxs-lookup"><span data-stu-id="e1da0-134">[Microsoft Defender Antivirus real-time protection](configure-real-time-protection-microsoft-defender-antivirus.md) and [cloud-delivered protection](enable-cloud-protection-microsoft-defender-antivirus.md) must be enabled</span></span> |

<span data-ttu-id="e1da0-135">Nadat u de services hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om de verbindingen tussen de services en uw apparaten toe te staan (ook wel eindpunten genoemd).</span><span class="sxs-lookup"><span data-stu-id="e1da0-135">After you have enabled the services, you might need to configure your network or firewall to allow the connections between the services and your devices (also referred to as endpoints).</span></span>  

- `.smartscreen.microsoft.com`
- `.smartscreen-prod.microsoft.com`

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a><span data-ttu-id="e1da0-136">Gebeurtenissen op het gebied van netwerkbeveiliging bekijken in het Microsoft Defender for Endpoint Security Center</span><span class="sxs-lookup"><span data-stu-id="e1da0-136">Review network protection events in the Microsoft Defender for Endpoint Security Center</span></span>

<span data-ttu-id="e1da0-137">Microsoft Defender voor Eindpunt biedt gedetailleerde rapportage over gebeurtenissen en blokken als onderdeel van de [scenario's voor waarschuwingsonderzoek.](investigate-alerts.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-137">Microsoft Defender for Endpoint provides detailed reporting into events and blocks as part of its [alert investigation scenarios](investigate-alerts.md).</span></span>

<span data-ttu-id="e1da0-138">U kunt Microsoft Defender opvragen voor eindpuntgegevens met behulp van [geavanceerd zoeken.](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-138">You can query Microsoft Defender for Endpoint data by using [advanced hunting](advanced-hunting-overview.md).</span></span> <span data-ttu-id="e1da0-139">Als u de [auditmodus gebruikt,](audit-windows-defender.md)kunt u geavanceerd zoeken gebruiken om te zien hoe de netwerkbeveiligingsinstellingen van invloed zijn op uw omgeving als deze zijn ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="e1da0-139">If you're using [audit mode](audit-windows-defender.md), you can use advanced hunting to see how network protection settings would affect your environment if they were enabled.</span></span>

<span data-ttu-id="e1da0-140">Hier is een voorbeeldquery</span><span class="sxs-lookup"><span data-stu-id="e1da0-140">Here is an example query</span></span>

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a><span data-ttu-id="e1da0-141">Netwerkbeveiligingsgebeurtenissen bekijken in Windows Event Viewer</span><span class="sxs-lookup"><span data-stu-id="e1da0-141">Review network protection events in Windows Event Viewer</span></span>

<span data-ttu-id="e1da0-142">U kunt het Windows-gebeurtenislogboek bekijken om gebeurtenissen te bekijken die worden gemaakt wanneer netwerkbeveiligingsblokken (of audits) toegang tot een schadelijk IP- of domein blokkeert:</span><span class="sxs-lookup"><span data-stu-id="e1da0-142">You can review the Windows event log to see events that are created when network protection blocks (or audits) access to a malicious IP or domain:</span></span>

1. <span data-ttu-id="e1da0-143">[Kopieer de XML rechtstreeks.](event-views.md)</span><span class="sxs-lookup"><span data-stu-id="e1da0-143">[Copy the XML directly](event-views.md).</span></span>

2. <span data-ttu-id="e1da0-144">Kies **OK**.</span><span class="sxs-lookup"><span data-stu-id="e1da0-144">Select **OK**.</span></span>

<span data-ttu-id="e1da0-145">Met deze procedure wordt een aangepaste weergave gemaakt die filtert om alleen de volgende gebeurtenissen weer te geven die betrekking hebben op netwerkbeveiliging:</span><span class="sxs-lookup"><span data-stu-id="e1da0-145">This procedure creates a custom view that filters to only show the following events related to network protection:</span></span>

| <span data-ttu-id="e1da0-146">Gebeurtenis-id</span><span class="sxs-lookup"><span data-stu-id="e1da0-146">Event ID</span></span> | <span data-ttu-id="e1da0-147">Omschrijving</span><span class="sxs-lookup"><span data-stu-id="e1da0-147">Description</span></span> |
|:---|:---|
| <span data-ttu-id="e1da0-148">5007</span><span class="sxs-lookup"><span data-stu-id="e1da0-148">5007</span></span> | <span data-ttu-id="e1da0-149">Gebeurtenis wanneer instellingen worden gewijzigd</span><span class="sxs-lookup"><span data-stu-id="e1da0-149">Event when settings are changed</span></span> |
| <span data-ttu-id="e1da0-150">1125</span><span class="sxs-lookup"><span data-stu-id="e1da0-150">1125</span></span> | <span data-ttu-id="e1da0-151">Gebeurtenis wanneer netwerkbeveiliging wordt uitgevoerd in de auditmodus</span><span class="sxs-lookup"><span data-stu-id="e1da0-151">Event when network protection fires in audit mode</span></span> |
| <span data-ttu-id="e1da0-152">1126</span><span class="sxs-lookup"><span data-stu-id="e1da0-152">1126</span></span> | <span data-ttu-id="e1da0-153">Gebeurtenis wanneer netwerkbeveiliging wordt branden in de blokmodus</span><span class="sxs-lookup"><span data-stu-id="e1da0-153">Event when network protection fires in block mode</span></span> |

## <a name="considerations-for-windows-virtual-desktop-running-windows-10-enterprise-multi-session"></a><span data-ttu-id="e1da0-154">Aandachtspunten voor windows virtual desktop met Windows 10 Enterprise Multi-Session</span><span class="sxs-lookup"><span data-stu-id="e1da0-154">Considerations for Windows virtual desktop running Windows 10 Enterprise Multi-Session</span></span>

<span data-ttu-id="e1da0-155">Houd rekening met de verschillende gebruikers van Windows 10 Enterprise:</span><span class="sxs-lookup"><span data-stu-id="e1da0-155">Due to the multi-user nature of Windows 10 Enterprise, keep the following points in mind:</span></span>

1. <span data-ttu-id="e1da0-156">Netwerkbeveiliging is een functie voor het hele apparaat en kan niet worden gericht op specifieke gebruikerssessies.</span><span class="sxs-lookup"><span data-stu-id="e1da0-156">Network protection is a device-wide feature and cannot be targeted to specific user sessions.</span></span>

2. <span data-ttu-id="e1da0-157">Filterbeleid voor webinhoud is ook apparaatbreed.</span><span class="sxs-lookup"><span data-stu-id="e1da0-157">Web content filtering policies are also device wide.</span></span>

3. <span data-ttu-id="e1da0-158">Als u onderscheid wilt maken tussen gebruikersgroepen, kunt u afzonderlijke Windows Virtual Desktop-hostgroepen en -toewijzingen maken.</span><span class="sxs-lookup"><span data-stu-id="e1da0-158">If you need to differentiate between user groups, consider creating separate Windows Virtual Desktop host pools and assignments.</span></span>

4. <span data-ttu-id="e1da0-159">Test netwerkbeveiliging in de auditmodus om het gedrag ervan te beoordelen voordat u deze uitrolt.</span><span class="sxs-lookup"><span data-stu-id="e1da0-159">Test network protection in audit mode to assess its behavior before rolling out.</span></span> 

5. <span data-ttu-id="e1da0-160">U kunt het formaat van uw implementatie mogelijk ook als u een groot aantal gebruikers of een groot aantal sessies met meerdere gebruikers hebt.</span><span class="sxs-lookup"><span data-stu-id="e1da0-160">Consider resizing your deployment if you have a large number of users or a large number of multi-user sessions.</span></span>

### <a name="alternative-option-for-network-protection"></a><span data-ttu-id="e1da0-161">Alternatieve optie voor netwerkbeveiliging</span><span class="sxs-lookup"><span data-stu-id="e1da0-161">Alternative option for network protection</span></span>

<span data-ttu-id="e1da0-162">Voor Windows 10 Enterprise Multi-Session 1909 en hoger, gebruikt in Windows Virtual Desktop op Azure, kan netwerkbeveiliging voor Microsoft Edge worden ingeschakeld met de volgende methode:</span><span class="sxs-lookup"><span data-stu-id="e1da0-162">For Windows 10 Enterprise Multi-Session 1909 and up, used in Windows Virtual Desktop on Azure, network protection for Microsoft Edge can be enabled using the following method:</span></span>

1. <span data-ttu-id="e1da0-163">Gebruik [Netwerkbeveiliging in-en](enable-network-protection.md) volg de instructies om uw beleid toe te passen.</span><span class="sxs-lookup"><span data-stu-id="e1da0-163">Use [Turn on network protection](enable-network-protection.md) and follow the instructions to apply your policy.</span></span>

2. <span data-ttu-id="e1da0-164">Voer de volgende PowerShell-opdracht uit: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span><span class="sxs-lookup"><span data-stu-id="e1da0-164">Execute the following PowerShell command: `Set-MpPreference -AllowNetworkProtectionOnWinServer 1`</span></span>

## <a name="network-protection-troubleshooting"></a><span data-ttu-id="e1da0-165">Problemen met netwerkbeveiliging oplossen</span><span class="sxs-lookup"><span data-stu-id="e1da0-165">Network protection troubleshooting</span></span>

<span data-ttu-id="e1da0-166">Vanwege de omgeving waarin Netwerkbeveiliging wordt uitgevoerd, kan Microsoft mogelijk geen proxy-instellingen voor het besturingssysteem detecteren.</span><span class="sxs-lookup"><span data-stu-id="e1da0-166">Due to the environment where Network Protection runs, Microsoft might not be able to detect operating system proxy settings.</span></span> <span data-ttu-id="e1da0-167">In sommige gevallen kunnen netwerkbeveiligings clients geen cloudservice bereiken.</span><span class="sxs-lookup"><span data-stu-id="e1da0-167">In some cases, network protection clients are unable to reach Cloud Service.</span></span> <span data-ttu-id="e1da0-168">Als u het verbindingsprobleem wilt oplossen, moeten klanten met E5-licenties een van de volgende registersleutels van Defender configureren:</span><span class="sxs-lookup"><span data-stu-id="e1da0-168">To resolve the connectivity problem, customers with E5 licenses should configure one of the following Defender registry keys:</span></span>

```console
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyServer /d "<proxy IP address: Port>" /f
reg add "HKLM\Software\Microsoft\Windows Defender" /v ProxyPacUrl /d "<Proxy PAC url>" /f

```

## <a name="related-articles"></a><span data-ttu-id="e1da0-169">Verwante artikelen</span><span class="sxs-lookup"><span data-stu-id="e1da0-169">Related articles</span></span>

- <span data-ttu-id="e1da0-170">[Netwerkbeveiliging evalueren |](evaluate-network-protection.md) Maak een snel scenario waarin wordt gedemonstreerd hoe de functie werkt en welke gebeurtenissen gewoonlijk worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="e1da0-170">[Evaluate network protection](evaluate-network-protection.md) | Undertake a quick scenario that demonstrates how the feature works, and what events would typically be created.</span></span>

- <span data-ttu-id="e1da0-171">[Netwerkbeveiliging inschakelen](enable-network-protection.md) | Gebruik Groepsbeleid, PowerShell- of MDM-CSP's om netwerkbeveiliging in uw netwerk in te stellen en te beheren.</span><span class="sxs-lookup"><span data-stu-id="e1da0-171">[Enable network protection](enable-network-protection.md) | Use Group Policy, PowerShell, or MDM CSPs to enable and manage network protection in your network.</span></span>
