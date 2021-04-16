---
title: Onboard devices to the Microsoft Defender for Endpoint service
description: Onboard Windows 10-apparaten, servers, niet-Windows-apparaten en leer hoe u een detectietest kunt uitvoeren.
keywords: onboarding, microsoft defender for endpoint onboarding, windows atp onboarding, sccm, group policy, mdm, local script, detection test
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
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4aa3e30f34e7d9dc362cc0bbb277aaee5834b4fe
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861369"
---
# <a name="onboard-devices-to-the-microsoft-defender-for-endpoint-service"></a>Onboard devices to the Microsoft Defender for Endpoint service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

U moet naar de onboarding-sectie van de Defender for Endpoint-portal gaan om een van de ondersteunde apparaten aan te sluiten. Afhankelijk van het apparaat wordt u begeleid met de juiste stappen en de opties voor beheer- en implementatieprogramma's die geschikt zijn voor het apparaat. 

In het algemeen gaat het om apparaten aan boord van de service:

- Controleren of het apparaat aan de [minimumvereisten voldoet](minimum-requirements.md)
- Volg, afhankelijk van het apparaat, de configuratiestappen in de onboarding-sectie van de Defender for Endpoint-portal
- Het juiste beheerprogramma en de juiste implementatiemethode voor uw apparaten gebruiken
- Een detectietest uitvoeren om te controleren of de apparaten correct zijn onboarded en rapporteren aan de service

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]

## <a name="onboarding-tool-options"></a>Opties voor onboarding-hulpprogramma's
In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.

| Eindpunt     | Opties voor hulpprogramma's                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokaal script (maximaal 10 apparaten)](configure-endpoints-script.md) <br>  [Groepsbeleid](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br>   [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-scripts](configure-endpoints-vdi.md)   |
| **macOS**    | [Lokale scripts](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokaal script](linux-install-manually.md) <br> [Poppop](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-gebaseerde](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 




## <a name="in-this-section"></a>In deze sectie
Onderwerp | Beschrijving
:---|:---
[Onboarden eerdere versies van Windows](onboard-downlevel.md)| Onboard Windows 7 en Windows 8.1-apparaten naar Defender voor Eindpunt. 
[Onboarden Windows 10-apparaten](configure-endpoints.md) | U moet apparaten aan boord hebben om deze te kunnen rapporteren bij de Service Defender voor eindpunt. Meer informatie over de hulpprogramma's en methoden die u kunt gebruiken om apparaten in uw bedrijf te configureren.
[Onboard-servers](configure-server-endpoints.md) |  Onboard Windows Server 2008 R2 SP1, Windows Server 2012 R2, Windows Server 2016, Windows Server (SAC) versie 1803 en hoger, Windows Server 2019 en hoger en Windows Server 2019 core edition naar Defender voor Eindpunt.
[Onboarden niet-Windows-apparaten](configure-endpoints-non-windows.md) | Defender voor Eindpunt biedt een gecentraliseerde beveiligingsbewerkingservaring voor Windows en niet-Windows-platforms. U kunt waarschuwingen van verschillende ondersteunde besturingssystemen (OS) zien in het Microsoft Defender-beveiligingscentrum en het netwerk van uw organisatie beter beveiligen. Deze ervaring maakt gebruik van de sensorgegevens van een beveiligingsproducten van derden. 
[Een detectietest uitvoeren op een nieuw geonboard apparaat](run-detection-test.md) | Voer een script uit op een nieuw onboarded apparaat om te controleren of het correct rapporteert aan de Defender for Endpoint-service.
[Proxy- en internetinstellingen configureren](configure-proxy-internet.md)| Schakel communicatie met de Defender voor Endpoint-cloudservice in door de proxy- en internetverbindingsinstellingen te configureren.
[Problemen met onboarden oplossen](troubleshoot-onboarding.md) | Meer informatie over het oplossen van problemen die zich kunnen voordoen tijdens onboarding.

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)
