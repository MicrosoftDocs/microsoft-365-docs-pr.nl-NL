---
title: Microsoft Defender for Endpoint on Linux static proxy discovery
ms.reviewer: ''
description: Hier wordt beschreven hoe u Microsoft Defender configureert voor Eindpunt op Linux, voor statische proxydetectie.
keywords: microsoft, defender, Microsoft Defender voor Endpoint, linux, installatie, proxy
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5a8e1cbda5f4361532c7fac0892be7ffe72f64ca
ms.sourcegitcommit: 8b79d276f71f22bcaeb150e78e35101cb1ae0375
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53114729"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a><span data-ttu-id="37fe3-104">Microsoft Defender voor eindpunt configureren op Linux voor statische proxydetectie</span><span class="sxs-lookup"><span data-stu-id="37fe3-104">Configure Microsoft Defender for Endpoint on Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="37fe3-105">**Van toepassing op:**</span><span class="sxs-lookup"><span data-stu-id="37fe3-105">**Applies to:**</span></span>
- [<span data-ttu-id="37fe3-106">Microsoft Defender voor Eindpunt</span><span class="sxs-lookup"><span data-stu-id="37fe3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="37fe3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="37fe3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="37fe3-108">Wilt u Defender voor Eindpunt ervaren?</span><span class="sxs-lookup"><span data-stu-id="37fe3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="37fe3-109">Meld u aan voor een gratis proefversie.</span><span class="sxs-lookup"><span data-stu-id="37fe3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="37fe3-110">Microsoft Defender voor Eindpunt kan een proxyserver ontdekken met behulp van de `HTTPS_PROXY` omgevingsvariabele.</span><span class="sxs-lookup"><span data-stu-id="37fe3-110">Microsoft Defender for Endpoint can discover a proxy server using the `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="37fe3-111">Deze instelling moet zowel **tijdens** de installatie als nadat het product is geïnstalleerd, zijn geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="37fe3-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="37fe3-112">Installatietijdconfiguratie</span><span class="sxs-lookup"><span data-stu-id="37fe3-112">Installation time configuration</span></span>

<span data-ttu-id="37fe3-113">Tijdens de installatie moet de `HTTPS_PROXY` omgevingsvariabele worden doorgegeven aan de package manager.</span><span class="sxs-lookup"><span data-stu-id="37fe3-113">During installation, the `HTTPS_PROXY` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="37fe3-114">De package manager kan deze variabele op een van de volgende manieren lezen:</span><span class="sxs-lookup"><span data-stu-id="37fe3-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="37fe3-115">De `HTTPS_PROXY` variabele wordt gedefinieerd met de volgende `/etc/environment` regel:</span><span class="sxs-lookup"><span data-stu-id="37fe3-115">The `HTTPS_PROXY` variable is defined in `/etc/environment` with the following line:</span></span>

  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

- <span data-ttu-id="37fe3-116">De `HTTPS_PROXY` variabele wordt gedefinieerd in de globale configuratie van Package Manager.</span><span class="sxs-lookup"><span data-stu-id="37fe3-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="37fe3-117">In Ubuntu 18.04 kunt u bijvoorbeeld de volgende regel toevoegen `/etc/apt/apt.conf.d/proxy.conf` aan:</span><span class="sxs-lookup"><span data-stu-id="37fe3-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
  ```bash
  Acquire::https::Proxy "http://proxy.server:port/";
  ```

  > [!CAUTION]
  > <span data-ttu-id="37fe3-118">Houd er rekening mee dat bovenstaande twee methoden de proxy kunnen definiëren die moet worden gebruikt voor andere toepassingen op uw systeem.</span><span class="sxs-lookup"><span data-stu-id="37fe3-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="37fe3-119">Gebruik deze methode voorzichtig of alleen als dit een algemene configuratie is.</span><span class="sxs-lookup"><span data-stu-id="37fe3-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="37fe3-120">De `HTTPS_PROXY` variabele wordt voorbereid op de installatie- of verwijderingsopdrachten.</span><span class="sxs-lookup"><span data-stu-id="37fe3-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="37fe3-121">Met de APT-pakketbeheerder kunt u bijvoorbeeld de variabele als volgt voorbereiden bij de installatie van Microsoft Defender voor eindpunt:</span><span class="sxs-lookup"><span data-stu-id="37fe3-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

  ```bash  
  HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
  ```

  > [!NOTE]
  > <span data-ttu-id="37fe3-122">Voeg geen sudo toe tussen de definitie van de omgevingsvariabele en apt, anders wordt de variabele niet doorgegeven.</span><span class="sxs-lookup"><span data-stu-id="37fe3-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="37fe3-123">De `HTTPS_PROXY` omgevingsvariabele kan op dezelfde manier worden gedefinieerd tijdens het verwijderen.</span><span class="sxs-lookup"><span data-stu-id="37fe3-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="37fe3-124">Houd er rekening mee dat de installatie en verwijdering niet per se mislukt als een proxy vereist is, maar niet is geconfigureerd.</span><span class="sxs-lookup"><span data-stu-id="37fe3-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="37fe3-125">Telemetrie wordt echter niet verzonden en de bewerking kan veel langer duren vanwege netwerk time-outs.</span><span class="sxs-lookup"><span data-stu-id="37fe3-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="37fe3-126">Configuratie na installatie</span><span class="sxs-lookup"><span data-stu-id="37fe3-126">Post installation configuration</span></span>
  
<span data-ttu-id="37fe3-127">Na de installatie moet de `HTTPS_PROXY` omgevingsvariabele zijn gedefinieerd in het Servicebestand van Defender voor Eindpunt.</span><span class="sxs-lookup"><span data-stu-id="37fe3-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="37fe3-128">U doet dit door in een `/lib/systemd/system/mdatp.service` teksteditor te openen terwijl u als hoofdgebruiker wordt uitgevoerd.</span><span class="sxs-lookup"><span data-stu-id="37fe3-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="37fe3-129">U kunt de variabele vervolgens op twee manieren doorgeven aan de service:</span><span class="sxs-lookup"><span data-stu-id="37fe3-129">You can then propagate the variable to the service in one of two ways:</span></span>

> [!NOTE]
> <span data-ttu-id="37fe3-130">Op CentOS- of RedHat Linux-distributies is de locatie van het Endpoint-servicebestand `/usr/lib/systemd/system/mdatp.service` .</span><span class="sxs-lookup"><span data-stu-id="37fe3-130">On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service`.</span></span>

- <span data-ttu-id="37fe3-131">Decommenteer de regel `#Environment="HTTPS_PROXY=http://address:port"` en geef uw statische proxyadres op.</span><span class="sxs-lookup"><span data-stu-id="37fe3-131">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="37fe3-132">Een regel `EnvironmentFile=/path/to/env/file` toevoegen.</span><span class="sxs-lookup"><span data-stu-id="37fe3-132">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="37fe3-133">Dit pad kan naar of een aangepast bestand wijzen, waarbij de volgende regel `/etc/environment` moet worden toegevoegd:</span><span class="sxs-lookup"><span data-stu-id="37fe3-133">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
  ```bash
  HTTPS_PROXY="http://proxy.server:port/"
  ```

<span data-ttu-id="37fe3-134">Nadat u het bestand `mdatp.service` hebt gewijzigd, kunt u het opslaan en sluiten.</span><span class="sxs-lookup"><span data-stu-id="37fe3-134">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="37fe3-135">Start de service opnieuw, zodat de wijzigingen kunnen worden toegepast.</span><span class="sxs-lookup"><span data-stu-id="37fe3-135">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="37fe3-136">In Ubuntu gaat het om twee opdrachten:</span><span class="sxs-lookup"><span data-stu-id="37fe3-136">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
