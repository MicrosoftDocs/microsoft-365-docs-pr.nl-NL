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
ms.openlocfilehash: 6dca58070d21271ffc832bcd628679303736f99e
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108137"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Microsoft Defender voor eindpunt configureren op Linux voor statische proxydetectie

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender voor Eindpunt kan een proxyserver ontdekken met behulp van de ```HTTPS_PROXY``` omgevingsvariabele. Deze instelling moet zowel **tijdens** de installatie als nadat het product is geïnstalleerd, zijn geconfigureerd.

## <a name="installation-time-configuration"></a>Installatietijdconfiguratie

Tijdens de installatie moet de ```HTTPS_PROXY``` omgevingsvariabele worden doorgegeven aan de package manager. De package manager kan deze variabele op een van de volgende manieren lezen:

- De ```HTTPS_PROXY``` variabele wordt gedefinieerd met de volgende ```/etc/environment``` regel:

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- De `HTTPS_PROXY` variabele wordt gedefinieerd in de globale configuratie van Package Manager. In Ubuntu 18.04 kunt u bijvoorbeeld de volgende regel toevoegen `/etc/apt/apt.conf.d/proxy.conf` aan:
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > Houd er rekening mee dat bovenstaande twee methoden de proxy kunnen definiëren die moet worden gebruikt voor andere toepassingen op uw systeem. Gebruik deze methode voorzichtig of alleen als dit een algemene configuratie is.
  
- De `HTTPS_PROXY` variabele wordt voorbereid op de installatie- of verwijderingsopdrachten. Met de APT-pakketbeheerder kunt u bijvoorbeeld de variabele als volgt voorbereiden bij de installatie van Microsoft Defender voor eindpunt: 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > Voeg geen sudo toe tussen de definitie van de omgevingsvariabele en apt, anders wordt de variabele niet doorgegeven.

De `HTTPS_PROXY` omgevingsvariabele kan op dezelfde manier worden gedefinieerd tijdens het verwijderen.

Houd er rekening mee dat de installatie en verwijdering niet per se mislukt als een proxy vereist is, maar niet is geconfigureerd. Telemetrie wordt echter niet verzonden en de bewerking kan veel langer duren vanwege netwerk time-outs.

## <a name="post-installation-configuration"></a>Configuratie na installatie
  
Na de installatie moet de `HTTPS_PROXY` omgevingsvariabele zijn gedefinieerd in het Servicebestand van Defender voor Eindpunt. U doet dit door in een `/lib/systemd/system/mdatp.service` teksteditor te openen terwijl u als hoofdgebruiker wordt uitgevoerd. U kunt de variabele vervolgens op twee manieren doorgeven aan de service:

    > [!NOTE]
    > On CentOS or RedHat Linux distributions the location of the Endpoint service file is `/usr/lib/systemd/system/mdatp.service`.

- Decommenteer de regel `#Environment="HTTPS_PROXY=http://address:port"` en geef uw statische proxyadres op.

- Een regel `EnvironmentFile=/path/to/env/file` toevoegen. Dit pad kan naar of een aangepast bestand wijzen, waarbij de volgende regel `/etc/environment` moet worden toegevoegd:
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

Nadat u het bestand `mdatp.service` hebt gewijzigd, kunt u het opslaan en sluiten. Start de service opnieuw, zodat de wijzigingen kunnen worden toegepast. In Ubuntu gaat het om twee opdrachten:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
