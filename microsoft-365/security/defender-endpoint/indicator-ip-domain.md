---
title: Indicatoren maken voor IPs en URL's/domeinen
ms.reviewer: ''
description: Maak indicatoren voor IPs en URL's/domeinen die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: ip, url, domain, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d468a77d2c1ab4f1b363e2e91b6e8507a5390d93
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198481"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a><span data-ttu-id="55302-104">Indicatoren maken voor IPs en URL's/domeinen</span><span class="sxs-lookup"><span data-stu-id="55302-104">Create indicators for IPs and URLs/domains</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="55302-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="55302-105">**Applies to:**</span></span>
- [<span data-ttu-id="55302-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="55302-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="55302-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="55302-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> <span data-ttu-id="55302-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="55302-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="55302-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="55302-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


<span data-ttu-id="55302-110">Defender voor Eindpunt kan blokkeren wat Microsoft als schadelijke URL's/URL's ziet, via Windows Defender SmartScreen voor Microsoft-browsers en via Netwerkbeveiliging voor niet-Microsoft-browsers of oproepen die buiten een browser worden gemaakt.</span><span class="sxs-lookup"><span data-stu-id="55302-110">Defender for Endpoint can block what Microsoft deems as malicious IPs/URLs, through Windows Defender SmartScreen for Microsoft browsers, and through Network Protection for non-Microsoft browsers or calls made outside of a browser.</span></span>

<span data-ttu-id="55302-111">De gegevensset voor bedreigingsinformatie hiervoor is beheerd door Microsoft.</span><span class="sxs-lookup"><span data-stu-id="55302-111">The threat intelligence data set for this has been managed by Microsoft.</span></span>

<span data-ttu-id="55302-112">Door indicatoren te maken voor IPs en URL's of domeinen, kunt u nu IPs, URL's of domeinen toestaan of blokkeren op basis van uw eigen bedreigingsinformatie.</span><span class="sxs-lookup"><span data-stu-id="55302-112">By creating indicators for IPs and URLs or domains, you can now allow or block IPs, URLs, or domains based on your own threat intelligence.</span></span> <span data-ttu-id="55302-113">U kunt dit doen via de instellingenpagina of per machinegroep als u bepaalde groepen meer of minder risico's acht dan andere.</span><span class="sxs-lookup"><span data-stu-id="55302-113">You can do this through the settings page or by machine groups if you deem certain groups to be more or less at risk than others.</span></span>

> [!NOTE]
> <span data-ttu-id="55302-114">Classless Inter-Domain Routing (CIDR) notatie voor IP-adressen wordt niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="55302-114">Classless Inter-Domain Routing (CIDR) notation for IP addresses is not supported.</span></span> 

### <a name="before-you-begin"></a><span data-ttu-id="55302-115">Voordat u begint</span><span class="sxs-lookup"><span data-stu-id="55302-115">Before you begin</span></span>
<span data-ttu-id="55302-116">Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren maakt voor IPS, URL's of domeinen:</span><span class="sxs-lookup"><span data-stu-id="55302-116">It's important to understand the following prerequisites prior to creating indicators for IPS, URLs, or domains:</span></span>
- <span data-ttu-id="55302-117">URL/IP allow and block is afhankelijk van de Defender for Endpoint-component Network Protection die moet worden ingeschakeld in de blokmodus.</span><span class="sxs-lookup"><span data-stu-id="55302-117">URL/IP allow and block relies on the Defender for Endpoint component Network Protection to be enabled in block mode.</span></span> <span data-ttu-id="55302-118">Zie Netwerkbeveiliging inschakelen voor meer informatie over netwerkbeveiliging en [configuratie-instructies.](enable-network-protection.md)</span><span class="sxs-lookup"><span data-stu-id="55302-118">For more information on Network Protection and configuration instructions, see [Enable network protection](enable-network-protection.md).</span></span>
- <span data-ttu-id="55302-119">De versie van de Antimalware-client moet 4.18.1906.x of hoger zijn.</span><span class="sxs-lookup"><span data-stu-id="55302-119">The Antimalware client version must be 4.18.1906.x or later.</span></span> 
- <span data-ttu-id="55302-120">Ondersteund op computers in Windows 10, versie 1709 of hoger.</span><span class="sxs-lookup"><span data-stu-id="55302-120">Supported on machines on Windows 10, version 1709 or later.</span></span> 
- <span data-ttu-id="55302-121">Controleer of **aangepaste netwerkindicatoren** zijn ingeschakeld in het Microsoft Defender-beveiligingscentrum > **instellingen > Geavanceerde functies.**</span><span class="sxs-lookup"><span data-stu-id="55302-121">Ensure that **Custom network indicators** is enabled in **Microsoft Defender Security Center > Settings > Advanced features**.</span></span> <span data-ttu-id="55302-122">Zie Geavanceerde functies [voor meer informatie.](advanced-features.md)</span><span class="sxs-lookup"><span data-stu-id="55302-122">For more information, see [Advanced features](advanced-features.md).</span></span>
- <span data-ttu-id="55302-123">Zie Aangepaste indicatoren [configureren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)voor ondersteuning van indicatoren in iOS.</span><span class="sxs-lookup"><span data-stu-id="55302-123">For support of indicators on iOS, see [Configure custom indicators](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="55302-124">Alleen externe IP's kunnen worden toegevoegd aan de lijst met indicatoren.</span><span class="sxs-lookup"><span data-stu-id="55302-124">Only external IPs can be added to the indicator list.</span></span> <span data-ttu-id="55302-125">Indicatoren kunnen niet worden gemaakt voor interne IPs.</span><span class="sxs-lookup"><span data-stu-id="55302-125">Indicators cannot be created for internal IPs.</span></span>
> <span data-ttu-id="55302-126">Voor scenario's voor webbeveiliging wordt u aangeraden de ingebouwde mogelijkheden in Microsoft Edge te gebruiken.</span><span class="sxs-lookup"><span data-stu-id="55302-126">For web protection scenarios, we recommend using the built-in capabilities in Microsoft Edge.</span></span> <span data-ttu-id="55302-127">Microsoft Edge maakt gebruik van [Netwerkbeveiliging om](network-protection.md) netwerkverkeer te controleren en maakt blokken voor TCP, HTTP en HTTPS (TLS) mogelijk.</span><span class="sxs-lookup"><span data-stu-id="55302-127">Microsoft Edge leverages [Network Protection](network-protection.md) to inspect network traffic and allows blocks for TCP, HTTP, and HTTPS (TLS).</span></span> <span data-ttu-id="55302-128">Als er conflicterende URL-indicatorbeleidsregels zijn, wordt het langere pad toegepast.</span><span class="sxs-lookup"><span data-stu-id="55302-128">If there are conflicting URL indicator policies, the longer path is applied.</span></span> <span data-ttu-id="55302-129">Het beleid voor URL-indicator heeft `https:\\support.microsoft.com/en-us/office` bijvoorbeeld voorrang op het URL-indicatorbeleid. `https:\\support.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="55302-129">For example, the URL indicator policy `https:\\support.microsoft.com/en-us/office` takes precedence over the URL indicator policy `https:\\support.microsoft.com`.</span></span>

> [!NOTE]
> <span data-ttu-id="55302-130">Voor alle andere processen maken scenario's voor webbeveiliging gebruik van Netwerkbeveiliging voor inspectie en handhaving:</span><span class="sxs-lookup"><span data-stu-id="55302-130">For all other processes, web protection scenarios leverage Network Protection for inspection and enforcement:</span></span> 
> - <span data-ttu-id="55302-131">IP wordt ondersteund voor alle drie protocollen</span><span class="sxs-lookup"><span data-stu-id="55302-131">IP is supported for all three protocols</span></span>
> - <span data-ttu-id="55302-132">Alleen enkele IP-adressen worden ondersteund (geen CIDR-blokken of IP-bereik)</span><span class="sxs-lookup"><span data-stu-id="55302-132">Only single IP addresses are supported (no CIDR blocks or IP ranges)</span></span>
> - <span data-ttu-id="55302-133">Versleutelde URL's (volledig pad) kunnen alleen worden geblokkeerd in first party browsers (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="55302-133">Encrypted URLs (full path) can only be blocked on first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="55302-134">Versleutelde URL's (alleen FQDN) kunnen worden geblokkeerd buiten first party browsers (Internet Explorer, Edge)</span><span class="sxs-lookup"><span data-stu-id="55302-134">Encrypted URLS (FQDN only) can be blocked outside of first party browsers (Internet Explorer, Edge)</span></span>
> - <span data-ttu-id="55302-135">Volledige URL-padblokken kunnen worden toegepast op het domeinniveau en alle niet-versleutelde URL's</span><span class="sxs-lookup"><span data-stu-id="55302-135">Full URL path blocks can be applied on the domain level and all unencrypted URLs</span></span>
 
> [!NOTE]
> <span data-ttu-id="55302-136">Er kan maximaal 2 uur latentie zijn (meestal minder) tussen de tijd dat de actie wordt uitgevoerd en de URL en HET IP-adres worden geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="55302-136">There may be up to 2 hours of latency (usually less) between the time the action is taken, and the URL and IP being blocked.</span></span> 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a><span data-ttu-id="55302-137">Een indicator voor IPs, URL's of domeinen maken op de pagina Instellingen</span><span class="sxs-lookup"><span data-stu-id="55302-137">Create an indicator for IPs, URLs, or domains from the settings page</span></span>

1. <span data-ttu-id="55302-138">Selecteer instellingenindicatoren in het  >  **navigatiedeelvenster.**</span><span class="sxs-lookup"><span data-stu-id="55302-138">In the navigation pane, select **Settings** > **Indicators**.</span></span>  

2. <span data-ttu-id="55302-139">Selecteer het **tabblad IP-adressen of URL's/domeinen.**</span><span class="sxs-lookup"><span data-stu-id="55302-139">Select the **IP addresses or URLs/Domains** tab.</span></span>

3. <span data-ttu-id="55302-140">Selecteer **Item toevoegen.**</span><span class="sxs-lookup"><span data-stu-id="55302-140">Select **Add item**.</span></span>

4. <span data-ttu-id="55302-141">Geef de volgende details op:</span><span class="sxs-lookup"><span data-stu-id="55302-141">Specify the following details:</span></span>
   - <span data-ttu-id="55302-142">Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.</span><span class="sxs-lookup"><span data-stu-id="55302-142">Indicator - Specify the entity details and define the expiration of the indicator.</span></span>
   - <span data-ttu-id="55302-143">Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.</span><span class="sxs-lookup"><span data-stu-id="55302-143">Action - Specify the action to be taken and provide a description.</span></span>
   - <span data-ttu-id="55302-144">Bereik: definieer het bereik van de machinegroep.</span><span class="sxs-lookup"><span data-stu-id="55302-144">Scope - Define the scope of the machine group.</span></span>

5. <span data-ttu-id="55302-145">Bekijk de details op het tabblad Overzicht en klik vervolgens op **Opslaan.**</span><span class="sxs-lookup"><span data-stu-id="55302-145">Review the details in the Summary tab, then click **Save**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="55302-146">Verwante onderwerpen</span><span class="sxs-lookup"><span data-stu-id="55302-146">Related topics</span></span>
- [<span data-ttu-id="55302-147">Indicatoren maken</span><span class="sxs-lookup"><span data-stu-id="55302-147">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="55302-148">Indicatoren voor bestanden maken</span><span class="sxs-lookup"><span data-stu-id="55302-148">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="55302-149">Indicatoren maken op basis van certificaten</span><span class="sxs-lookup"><span data-stu-id="55302-149">Create indicators based on certificates</span></span>](indicator-certificates.md)
- [<span data-ttu-id="55302-150">Indicatoren beheren</span><span class="sxs-lookup"><span data-stu-id="55302-150">Manage indicators</span></span>](indicator-manage.md)
