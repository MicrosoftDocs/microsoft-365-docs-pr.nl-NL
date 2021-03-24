---
title: Problemen met cloudconnectiviteit oplossen voor Microsoft Defender ATP voor Linux
ms.reviewer: ''
description: Problemen met cloudconnectiviteit oplossen voor Microsoft Defender ATP voor Linux
keywords: microsoft, defender, atp, linux, cloud, connectiviteit, communicatie
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
ms.openlocfilehash: af4f0b00cc4470e855c7c9cb780703d65992c55e
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059118"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="07103-104">Problemen met cloudconnectiviteit oplossen voor Microsoft Defender voor Eindpunt voor Linux</span><span class="sxs-lookup"><span data-stu-id="07103-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="07103-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="07103-105">**Applies to:**</span></span>
- [<span data-ttu-id="07103-106">Microsoft Defender voor Endpoint</span><span class="sxs-lookup"><span data-stu-id="07103-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="07103-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="07103-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="07103-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="07103-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="07103-109">Meld u aan voor een gratis proefabonnement.</span><span class="sxs-lookup"><span data-stu-id="07103-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="07103-110">De connectiviteitstest uitvoeren</span><span class="sxs-lookup"><span data-stu-id="07103-110">Run the connectivity test</span></span>

<span data-ttu-id="07103-111">Als u wilt testen of Defender voor Eindpunt voor Linux met de huidige netwerkinstellingen met de cloud kan communiceren, moet u een connectiviteitstest uitvoeren vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="07103-111">To test if Defender for Endpoint for Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="07103-112">verwachte uitvoer:</span><span class="sxs-lookup"><span data-stu-id="07103-112">expected output:</span></span>

```output
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

<span data-ttu-id="07103-113">Als de [verbindingstest](microsoft-defender-endpoint-linux.md#network-connections) mislukt, controleert u of het apparaat internetverbinding heeft en of een van de eindpunten die vereist zijn voor het product, wordt geblokkeerd door een proxy of firewall.</span><span class="sxs-lookup"><span data-stu-id="07103-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="07103-114">Fouten met krulfout 35 of 60 geven aan dat certificaten zijn geweigerd.</span><span class="sxs-lookup"><span data-stu-id="07103-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="07103-115">Controleer of de verbinding onder SSL- of HTTPS-inspectie valt.</span><span class="sxs-lookup"><span data-stu-id="07103-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="07103-116">Voeg dan Microsoft Defender voor Eindpunt toe aan de lijst toestaan.</span><span class="sxs-lookup"><span data-stu-id="07103-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="07103-117">Stappen voor probleemoplossing voor omgevingen zonder proxy of met transparante proxy</span><span class="sxs-lookup"><span data-stu-id="07103-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="07103-118">Als u wilt testen of een verbinding niet is geblokkeerd in een omgeving zonder proxy of met een transparante proxy, moet u de volgende opdracht uitvoeren in de terminal:</span><span class="sxs-lookup"><span data-stu-id="07103-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="07103-119">De uitvoer van deze opdracht moet vergelijkbaar zijn met:</span><span class="sxs-lookup"><span data-stu-id="07103-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="07103-120">Stappen voor probleemoplossing voor omgevingen met statische proxy</span><span class="sxs-lookup"><span data-stu-id="07103-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="07103-121">PAC-, WPAD- en geverifieerde proxies worden niet ondersteund.</span><span class="sxs-lookup"><span data-stu-id="07103-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="07103-122">Zorg ervoor dat alleen een statische proxy of transparante proxy wordt gebruikt.</span><span class="sxs-lookup"><span data-stu-id="07103-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="07103-123">SSL-inspectie en het onderscheppen van proxies worden ook niet ondersteund om beveiligingsredenen.</span><span class="sxs-lookup"><span data-stu-id="07103-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="07103-124">Configureer een uitzondering voor SSL-inspectie en uw proxyserver om gegevens van Defender voor Endpoint voor Linux rechtstreeks door te geven aan de relevante URL's zonder interceptie.</span><span class="sxs-lookup"><span data-stu-id="07103-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="07103-125">Als u uw interceptiecertificaat toevoegt aan de algemene winkel, is onderschepping niet toegestaan.</span><span class="sxs-lookup"><span data-stu-id="07103-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="07103-126">Als een statische proxy vereist is, voegt u een proxyparameter toe aan de bovenstaande opdracht, waarbij deze overeenkomt `proxy_address:port` met het proxyadres en de poort:</span><span class="sxs-lookup"><span data-stu-id="07103-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="07103-127">Zorg ervoor dat u hetzelfde proxyadres en dezelfde poort gebruikt als geconfigureerd in het `/lib/system/system/mdatp.service` bestand.</span><span class="sxs-lookup"><span data-stu-id="07103-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="07103-128">Controleer de proxyconfiguratie als er fouten zijn in de bovenstaande opdrachten.</span><span class="sxs-lookup"><span data-stu-id="07103-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="07103-129">De statische proxy kan niet worden geconfigureerd via een omgevingsvariabele voor `HTTPS_PROXY` het hele systeem.</span><span class="sxs-lookup"><span data-stu-id="07103-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="07103-130">Zorg er in plaats daarvan voor `HTTPS_PROXY` dat dit correct is ingesteld in het `/lib/system/system/mdatp.service` bestand.</span><span class="sxs-lookup"><span data-stu-id="07103-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="07103-131">Als u een statische proxy wilt gebruiken, moet `mdatp.service` het bestand worden gewijzigd.</span><span class="sxs-lookup"><span data-stu-id="07103-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="07103-132">Zorg ervoor dat de `#` voorlijn wordt verwijderd om de volgende regel uit te `/lib/systemd/system/mdatp.service` zetten:</span><span class="sxs-lookup"><span data-stu-id="07103-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="07103-133">Zorg er ook voor dat het juiste statische proxyadres wordt ingevuld om deze te `address:port` vervangen.</span><span class="sxs-lookup"><span data-stu-id="07103-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="07103-134">Als dit bestand juist is, kunt u de volgende opdracht uitvoeren in de terminal om Defender voor Endpoint voor Linux opnieuw te laden en de instelling door te geven:</span><span class="sxs-lookup"><span data-stu-id="07103-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint for Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="07103-135">Probeer bij succes een andere verbindingstest vanaf de opdrachtregel:</span><span class="sxs-lookup"><span data-stu-id="07103-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="07103-136">Als het probleem zich blijft voordoen, neem dan contact op met de klantondersteuning.</span><span class="sxs-lookup"><span data-stu-id="07103-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="07103-137">Resources</span><span class="sxs-lookup"><span data-stu-id="07103-137">Resources</span></span>

- <span data-ttu-id="07103-138">Zie Microsoft Defender voor eindpunt configureren voor [statische proxydetectie](linux-static-proxy-configuration.md)voor meer informatie over het configureren van het product voor het gebruik van een statische proxy.</span><span class="sxs-lookup"><span data-stu-id="07103-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
