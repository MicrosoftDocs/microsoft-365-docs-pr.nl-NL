---
title: Microsoft Defender voor Eindpunt op Mac
ms.reviewer: ''
description: Meer informatie over het installeren, configureren, bijwerken en gebruiken van Microsoft Defender voor Eindpunt op Mac.
keywords: microsoft, defender, Microsoft Defender for Endpoint, mac, installation, deploy, uninstallation, intune, jamf, macos, big sur, catalina, mojave, mde for mac
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 365fed8b5f7c7fc617ea068e324da541f7f1b187
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301774"
---
# <a name="microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="144bb-104">Microsoft Defender voor Eindpunt op Mac</span><span class="sxs-lookup"><span data-stu-id="144bb-104">Microsoft Defender for Endpoint on Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="144bb-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="144bb-105">**Applies to:**</span></span>
- [<span data-ttu-id="144bb-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="144bb-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="144bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="144bb-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="144bb-108">Wilt u Microsoft Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="144bb-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="144bb-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="144bb-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="144bb-110">In dit onderwerp wordt beschreven hoe u Defender voor Eindpunt op Mac kunt installeren, configureren, bijwerken en gebruiken.</span><span class="sxs-lookup"><span data-stu-id="144bb-110">This topic describes how to install, configure, update, and use Defender for Endpoint on Mac.</span></span>

> [!CAUTION]
> <span data-ttu-id="144bb-111">Het uitvoeren van andere endpointbeveiligingsproducten van derden naast Microsoft Defender voor Eindpunt op Mac kan waarschijnlijk leiden tot prestatieproblemen en onvoorspelbare bijwerkingen.</span><span class="sxs-lookup"><span data-stu-id="144bb-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Mac is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="144bb-112">Als niet-Microsoft-eindpuntbeveiliging een absolute vereiste is in uw omgeving, kunt u na het configureren van de antivirusfunctionaliteit in de passieve modus nog steeds veilig profiteren van De functionaliteit van Defender voor Eindpunt op Mac [EDR.](mac-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="144bb-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Mac EDR functionality after configuring the antivirus functionality to run in [Passive mode](mac-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="whats-new-in-the-latest-release"></a><span data-ttu-id="144bb-113">Nieuwe functies in de nieuwste release</span><span class="sxs-lookup"><span data-stu-id="144bb-113">What’s new in the latest release</span></span>

[<span data-ttu-id="144bb-114">Wat is er nieuw in Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="144bb-114">What's new in Microsoft Defender for Endpoint</span></span>](whats-new-in-microsoft-defender-atp.md)

[<span data-ttu-id="144bb-115">Nieuwe functies in Microsoft Defender voor Eindpunt op Mac</span><span class="sxs-lookup"><span data-stu-id="144bb-115">What's new in Microsoft Defender for Endpoint on Mac</span></span>](mac-whatsnew.md)

> [!TIP]
> <span data-ttu-id="144bb-116">Als u feedback hebt die u wilt delen, verzendt u deze door Microsoft Defender voor Eindpunt op Mac te openen op uw apparaat en te navigeren naar **Help**  >  **Feedback verzenden.**</span><span class="sxs-lookup"><span data-stu-id="144bb-116">If you have any feedback that you would like to share, submit it by opening Microsoft Defender for Endpoint on Mac on your device and navigating to **Help** > **Send feedback**.</span></span>

<span data-ttu-id="144bb-117">Als u de nieuwste functies wilt downloaden, waaronder preview-mogelijkheden (zoals eindpuntdetectie en -respons voor uw Mac-apparaten), configureert u uw macOS-apparaat met Microsoft Defender voor Eindpunt als een Insider-apparaat.</span><span class="sxs-lookup"><span data-stu-id="144bb-117">To get the latest features, including preview capabilities (such as endpoint detection and response for your Mac devices), configure your macOS device running Microsoft Defender for Endpoint to be an "Insider" device.</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="144bb-118">Microsoft Defender voor Eindpunt installeren op Mac</span><span class="sxs-lookup"><span data-stu-id="144bb-118">How to install Microsoft Defender for Endpoint on Mac</span></span>

### <a name="prerequisites"></a><span data-ttu-id="144bb-119">Vereisten</span><span class="sxs-lookup"><span data-stu-id="144bb-119">Prerequisites</span></span>

- <span data-ttu-id="144bb-120">Een Defender for Endpoint-abonnement en toegang tot de Microsoft Defender-beveiligingscentrum portal</span><span class="sxs-lookup"><span data-stu-id="144bb-120">A Defender for Endpoint subscription and access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="144bb-121">Beginnerservaring in macOS- en BASH-scripting</span><span class="sxs-lookup"><span data-stu-id="144bb-121">Beginner-level experience in macOS and BASH scripting</span></span>
- <span data-ttu-id="144bb-122">Beheerdersbevoegdheden op het apparaat (in geval van handmatige implementatie)</span><span class="sxs-lookup"><span data-stu-id="144bb-122">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="144bb-123">Installatie-instructies</span><span class="sxs-lookup"><span data-stu-id="144bb-123">Installation instructions</span></span>

<span data-ttu-id="144bb-124">Er zijn verschillende methoden en implementatiehulpmiddelen die u kunt gebruiken om Defender voor Eindpunt op Mac te installeren en te configureren.</span><span class="sxs-lookup"><span data-stu-id="144bb-124">There are several methods and deployment tools that you can use to install and configure Defender for Endpoint on Mac.</span></span>

- <span data-ttu-id="144bb-125">Beheerhulpmiddelen van derden:</span><span class="sxs-lookup"><span data-stu-id="144bb-125">Third-party management tools:</span></span>
    - [<span data-ttu-id="144bb-126">Implementatie op basis van Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="144bb-126">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md)
    - [<span data-ttu-id="144bb-127">IMPLEMENTATIE OP BASIS VAN JAMF</span><span class="sxs-lookup"><span data-stu-id="144bb-127">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
    - [<span data-ttu-id="144bb-128">Andere MDM-producten</span><span class="sxs-lookup"><span data-stu-id="144bb-128">Other MDM products</span></span>](mac-install-with-other-mdm.md)

- <span data-ttu-id="144bb-129">Opdrachtregelhulpmiddel:</span><span class="sxs-lookup"><span data-stu-id="144bb-129">Command-line tool:</span></span>
    - [<span data-ttu-id="144bb-130">Handmatige implementatie</span><span class="sxs-lookup"><span data-stu-id="144bb-130">Manual deployment</span></span>](mac-install-manually.md)

### <a name="system-requirements"></a><span data-ttu-id="144bb-131">Systeemvereisten</span><span class="sxs-lookup"><span data-stu-id="144bb-131">System requirements</span></span>

<span data-ttu-id="144bb-132">De drie meest recente grote versies van macOS worden ondersteund.</span><span class="sxs-lookup"><span data-stu-id="144bb-132">The three most recent major releases of macOS are supported.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="144bb-133">Voor macOS 11 (Big Sur) vereist Microsoft Defender voor Eindpunt extra configuratieprofielen.</span><span class="sxs-lookup"><span data-stu-id="144bb-133">On macOS 11 (Big Sur), Microsoft Defender for Endpoint requires additional configuration profiles.</span></span> <span data-ttu-id="144bb-134">Als u een bestaande klant bent die upgradet van eerdere versies van macOS, moet u de aanvullende configuratieprofielen implementeren die worden vermeld in Nieuwe configuratieprofielen voor [macOS Catalina](mac-sysext-policies.md)en nieuwere versies van macOS.</span><span class="sxs-lookup"><span data-stu-id="144bb-134">If you are an existing customer upgrading from earlier versions of macOS, make sure to deploy the additional configuration profiles listed on [New configuration profiles for macOS Catalina and newer versions of macOS](mac-sysext-policies.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="144bb-135">Ondersteuning voor macOS 10.13 (High Sierra) is stopgezet vanaf 15 februari 2021.</span><span class="sxs-lookup"><span data-stu-id="144bb-135">Support for macOS 10.13 (High Sierra) has been discontinued as of February 15th, 2021.</span></span>

- <span data-ttu-id="144bb-136">11 (Big Sur), 10,15 (Catalina), 10,14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="144bb-136">11 (Big Sur), 10.15 (Catalina), 10.14 (Mojave)</span></span>
- <span data-ttu-id="144bb-137">Schijfruimte: 1 GB</span><span class="sxs-lookup"><span data-stu-id="144bb-137">Disk space: 1GB</span></span>

<span data-ttu-id="144bb-138">Bètaversies van macOS worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="144bb-138">Beta versions of macOS are not supported.</span></span>

<span data-ttu-id="144bb-139">macOS-apparaten met M1-processors worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="144bb-139">macOS devices with M1 processors are not supported.</span></span>

<span data-ttu-id="144bb-140">Nadat u de service hebt ingeschakeld, moet u mogelijk uw netwerk of firewall configureren om uitgaande verbindingen tussen de service en uw eindpunten toe te staan.</span><span class="sxs-lookup"><span data-stu-id="144bb-140">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

### <a name="licensing-requirements"></a><span data-ttu-id="144bb-141">Licentievereisten</span><span class="sxs-lookup"><span data-stu-id="144bb-141">Licensing requirements</span></span>

<span data-ttu-id="144bb-142">Voor Microsoft Defender voor Eindpunt op Mac is een van de volgende Microsoft Volume Licensing-aanbiedingen vereist:</span><span class="sxs-lookup"><span data-stu-id="144bb-142">Microsoft Defender for Endpoint on Mac requires one of the following Microsoft Volume Licensing offers:</span></span>

- <span data-ttu-id="144bb-143">Microsoft 365 E5 (M365 E5)</span><span class="sxs-lookup"><span data-stu-id="144bb-143">Microsoft 365 E5 (M365 E5)</span></span>
- <span data-ttu-id="144bb-144">Microsoft 365 E5 Security</span><span class="sxs-lookup"><span data-stu-id="144bb-144">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="144bb-145">Microsoft 365 A5 (M365 A5)</span><span class="sxs-lookup"><span data-stu-id="144bb-145">Microsoft 365 A5 (M365 A5)</span></span>
- <span data-ttu-id="144bb-146">Windows 10 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="144bb-146">Windows 10 Enterprise E5</span></span>
- <span data-ttu-id="144bb-147">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="144bb-147">Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="144bb-148">In aanmerking komende gebruikers met een licentie kunnen Microsoft Defender voor Eindpunt gebruiken op maximaal vijf gelijktijdige apparaten.</span><span class="sxs-lookup"><span data-stu-id="144bb-148">Eligible licensed users may use Microsoft Defender for Endpoint on up to five concurrent devices.</span></span>
> <span data-ttu-id="144bb-149">Microsoft Defender voor Eindpunt is ook beschikbaar voor aankoop via een Cloud Solution Provider (CSP).</span><span class="sxs-lookup"><span data-stu-id="144bb-149">Microsoft Defender for Endpoint is also available for purchase from a Cloud Solution Provider (CSP).</span></span> <span data-ttu-id="144bb-150">Bij aankoop via een CSP zijn er geen aanbiedingen voor Microsoft Volume Licensing vereist.</span><span class="sxs-lookup"><span data-stu-id="144bb-150">When purchased via a CSP, it does not require Microsoft Volume Licensing offers listed.</span></span>

### <a name="network-connections"></a><span data-ttu-id="144bb-151">Netwerkverbindingen</span><span class="sxs-lookup"><span data-stu-id="144bb-151">Network connections</span></span>

<span data-ttu-id="144bb-152">In de volgende downloadbare spreadsheet vindt u de services en bijbehorende URL's waar uw netwerk verbinding mee moet kunnen maken.</span><span class="sxs-lookup"><span data-stu-id="144bb-152">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="144bb-153">U moet ervoor zorgen dat er geen firewall- of netwerkfilterregels zijn die de  toegang tot deze URL's weigeren, of u moet mogelijk een regel voor toestaan speciaal voor deze url's maken.</span><span class="sxs-lookup"><span data-stu-id="144bb-153">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>



|<span data-ttu-id="144bb-154">**Spreadsheet met domeinenlijst**</span><span class="sxs-lookup"><span data-stu-id="144bb-154">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="144bb-155">**Beschrijving**</span><span class="sxs-lookup"><span data-stu-id="144bb-155">**Description**</span></span>|
|:-----|:-----|
|![Thumb image for Microsoft Defender for Endpoint URLLs spreadsheet](images/mdatp-urls.png)<br/>  | <span data-ttu-id="144bb-157">Spreadsheet met specifieke DNS-records voor servicelocaties, geografische locaties en besturingssysteem.</span><span class="sxs-lookup"><span data-stu-id="144bb-157">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br><span data-ttu-id="144bb-158">Download de spreadsheet hier: [mdatp-urls.xlsx. ](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)</span><span class="sxs-lookup"><span data-stu-id="144bb-158">Download the spreadsheet here: [mdatp-urls.xlsx](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx).</span></span>

<span data-ttu-id="144bb-159">Microsoft Defender voor Eindpunt kan een proxyserver vinden met behulp van de volgende detectiemethoden:</span><span class="sxs-lookup"><span data-stu-id="144bb-159">Microsoft Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="144bb-160">Proxy autoconfig (PAC)</span><span class="sxs-lookup"><span data-stu-id="144bb-160">Proxy autoconfig (PAC)</span></span>
- <span data-ttu-id="144bb-161">Web proxy Autodiscovery Protocol (WPAD)</span><span class="sxs-lookup"><span data-stu-id="144bb-161">Web Proxy Autodiscovery Protocol (WPAD)</span></span>
- <span data-ttu-id="144bb-162">Handmatige statische proxyconfiguratie</span><span class="sxs-lookup"><span data-stu-id="144bb-162">Manual static proxy configuration</span></span>

<span data-ttu-id="144bb-163">Als een proxy of firewall anoniem verkeer blokkeert, moet u ervoor zorgen dat anoniem verkeer is toegestaan in de eerder genoemde URL's.</span><span class="sxs-lookup"><span data-stu-id="144bb-163">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="144bb-164">Geverifieerde proxies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="144bb-164">Authenticated proxies are not supported.</span></span> <span data-ttu-id="144bb-165">Zorg ervoor dat alleen PAC, WPAD of een statische proxy wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="144bb-165">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span>
>
> <span data-ttu-id="144bb-166">SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="144bb-166">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="144bb-167">Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Microsoft Defender voor Eindpunt op macOS rechtstreeks door te geven aan de relevante URL's zonder interceptie.</span><span class="sxs-lookup"><span data-stu-id="144bb-167">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="144bb-168">Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="144bb-168">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="144bb-169">Open en in een browser om te testen of een verbinding niet [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) is geblokkeerd.</span><span class="sxs-lookup"><span data-stu-id="144bb-169">To test that a connection is not blocked, open [https://x.cp.wd.microsoft.com/api/report](https://x.cp.wd.microsoft.com/api/report) and [https://cdn.x.cp.wd.microsoft.com/ping](https://cdn.x.cp.wd.microsoft.com/ping) in a browser.</span></span>

<span data-ttu-id="144bb-170">Als u de voorkeur geeft aan de opdrachtregel, kunt u ook de verbinding controleren door de volgende opdracht uit te voeren in Terminal:</span><span class="sxs-lookup"><span data-stu-id="144bb-170">If you prefer the command line, you can also check the connection by running the following command in Terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="144bb-171">De uitvoer van deze opdracht moet ongeveer hetzelfde zijn:</span><span class="sxs-lookup"><span data-stu-id="144bb-171">The output from this command should be similar to the following:</span></span>

 `OK https://x.cp.wd.microsoft.com/api/report`

 `OK https://cdn.x.cp.wd.microsoft.com/ping`

> [!CAUTION]
> <span data-ttu-id="144bb-172">We raden u aan [om System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) ingeschakeld te houden op clientapparaten.</span><span class="sxs-lookup"><span data-stu-id="144bb-172">We recommend that you keep [System Integrity Protection](https://support.apple.com/en-us/HT204899) (SIP) enabled on client devices.</span></span> <span data-ttu-id="144bb-173">SIP is een ingebouwde beveiligingsfunctie voor macOS die voorkomt dat er op laag niveau wordt geknoeid met het besturingssysteem en standaard is ingeschakeld.</span><span class="sxs-lookup"><span data-stu-id="144bb-173">SIP is a built-in macOS security feature that prevents low-level tampering with the OS, and is enabled by default.</span></span>

<span data-ttu-id="144bb-174">Nadat Microsoft Defender voor Eindpunt is geïnstalleerd, kan de connectiviteit worden gevalideerd door de volgende opdracht uit te voeren in Terminal:</span><span class="sxs-lookup"><span data-stu-id="144bb-174">Once Microsoft Defender for Endpoint is installed, connectivity can be validated by running the following command in Terminal:</span></span>
```bash
mdatp connectivity test
```

## <a name="how-to-update-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="144bb-175">Microsoft Defender voor eindpunt bijwerken op Mac</span><span class="sxs-lookup"><span data-stu-id="144bb-175">How to update Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="144bb-176">Microsoft publiceert regelmatig software-updates om de prestaties, beveiliging en nieuwe functies te verbeteren.</span><span class="sxs-lookup"><span data-stu-id="144bb-176">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="144bb-177">Als u Microsoft Defender voor Eindpunt op Mac wilt bijwerken, wordt een programma met de naam Microsoft AutoUpdate (MAU) gebruikt.</span><span class="sxs-lookup"><span data-stu-id="144bb-177">To update Microsoft Defender for Endpoint on Mac, a program named Microsoft AutoUpdate (MAU) is used.</span></span> <span data-ttu-id="144bb-178">Zie Updates implementeren voor Microsoft Defender voor Eindpunt op Mac voor meer [informatie.](mac-updates.md)</span><span class="sxs-lookup"><span data-stu-id="144bb-178">To learn more, see [Deploy updates for Microsoft Defender for Endpoint on Mac](mac-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-mac"></a><span data-ttu-id="144bb-179">Microsoft Defender voor Eindpunt configureren op Mac</span><span class="sxs-lookup"><span data-stu-id="144bb-179">How to configure Microsoft Defender for Endpoint on Mac</span></span>

<span data-ttu-id="144bb-180">Richtlijnen voor het configureren van het product in bedrijfsomgevingen zijn beschikbaar in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span><span class="sxs-lookup"><span data-stu-id="144bb-180">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Mac](mac-preferences.md).</span></span>

## <a name="macos-kernel-and-system-extensions"></a><span data-ttu-id="144bb-181">macOS-kernel- en systeemextensies</span><span class="sxs-lookup"><span data-stu-id="144bb-181">macOS kernel and system extensions</span></span>

<span data-ttu-id="144bb-182">In overeenstemming met de ontwikkeling van macOS bereiden we een Update van Microsoft Defender voor Eindpunt op Mac voor die gebruik maakt van systeemextensies in plaats van kernelextensies.</span><span class="sxs-lookup"><span data-stu-id="144bb-182">In alignment with macOS evolution, we are preparing a Microsoft Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="144bb-183">Zie Nieuw in Microsoft Defender voor Eindpunt op Mac voor relevante [informatie.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="144bb-183">For relevant details, see [What's new in Microsoft Defender for Endpoint on Mac](mac-whatsnew.md).</span></span>

## <a name="resources"></a><span data-ttu-id="144bb-184">Resources</span><span class="sxs-lookup"><span data-stu-id="144bb-184">Resources</span></span>

- <span data-ttu-id="144bb-185">Zie Resources [for Microsoft Defender for Endpoint on Mac](mac-resources.md)(Bronnen voor Microsoft Defender voor Eindpunt op Mac) voor meer informatie over logboekregistratie, het verwijderen of andere onderwerpen.</span><span class="sxs-lookup"><span data-stu-id="144bb-185">For more information about logging, uninstalling, or other topics, see [Resources for Microsoft Defender for Endpoint on Mac](mac-resources.md).</span></span>

- <span data-ttu-id="144bb-186">[Privacy voor Microsoft Defender voor Eindpunt op Mac](mac-privacy.md).</span><span class="sxs-lookup"><span data-stu-id="144bb-186">[Privacy for Microsoft Defender for Endpoint on Mac](mac-privacy.md).</span></span>
