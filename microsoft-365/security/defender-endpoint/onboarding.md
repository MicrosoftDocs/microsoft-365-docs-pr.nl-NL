---
title: Onboard to the Microsoft Defender for Endpoint service
description: Meer informatie over het onboarden van eindpunten aan Microsoft Defender voor endpoint-service
keywords: Microsoft Defender voor eindpunt, onboard, deploy
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 2a3325a290dc985bdb99a5a843b4b9e1f642a62b
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861801"
---
# <a name="onboard-to-the-microsoft-defender-for-endpoint-service"></a>Onboard to the Microsoft Defender for Endpoint service

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Meer informatie over de verschillende fasen van de implementatie van Microsoft Defender voor Eindpunt en hoe u de mogelijkheden binnen de oplossing configureert. 

Het implementeren van Defender voor Eindpunt is een proces in drie fasen:

| [![implementatiefase - voorbereiden](images/phase-diagrams/prepare.png)](prepare-deployment.md)<br>[Fase 1: Voorbereiden](prepare-deployment.md) | [![implementatiefase - installatie](images/phase-diagrams/setup.png)](production-deployment.md)<br>[Fase 2: Instellen](production-deployment.md) | ![implementatiefase - onboard](images/phase-diagrams/onboard.png)<br>Fase 3: Onboarden |
| ----- | ----- | ----- |
| | |*U bent er!*|

U bent momenteel bezig met de onboardingfase.

Dit zijn de stappen die u moet ondernemen om Defender voor Eindpunt te implementeren:

- Stap 1: Eindpunten aan boord van de service 
- Stap 2: Mogelijkheden configureren 

## <a name="step-1-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Stap 1: Onboard-eindpunten met behulp van een van de ondersteunde beheerhulpmiddelen
Het [implementatieonderwerp](deployment-strategy.md) Plannen bevat een overzicht van de algemene stappen die u moet ondernemen om Defender voor Eindpunt te implementeren.  


Bekijk deze video voor een kort overzicht van het onboardingproces en lees meer over de beschikbare hulpprogramma's en methoden.
<br />
<br />

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4bGqr]



Nadat u de architectuur hebt identificeren, moet u bepalen welke implementatiemethode u wilt gebruiken. Het implementatieprogramma dat u kiest, is van invloed op de manier waarop u eindpunten aan boord van de service inwerkt. 

### <a name="onboarding-tool-options"></a>Opties voor onboarding-hulpprogramma's

In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.

| Eindpunt     | Opties voor hulpprogramma's                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokaal script (maximaal 10 apparaten)](configure-endpoints-script.md) <br>  [Groepsbeleid](configure-endpoints-gp.md) <br>  [Microsoft Endpoint Manager/ Mobile Device Manager](configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](configure-endpoints-sccm.md) <br> [VDI-scripts](configure-endpoints-vdi.md) <br> [Azure Security Center](configure-server-endpoints.md#integration-with-azure-security-center) |
| **macOS**    | [Lokale scripts](mac-install-manually.md) <br> [Microsoft Endpoint Manager](mac-install-with-intune.md) <br> [JAMF Pro](mac-install-with-jamf.md) <br> [Mobile Device Management](mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokaal script](linux-install-manually.md) <br> [Poppop](linux-install-with-puppet.md) <br> [Ansible](linux-install-with-ansible.md)|
| **iOS**      | [App-gebaseerde](ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](android-intune.md)               | 


## <a name="step-2-configure-capabilities"></a>Stap 2: Mogelijkheden configureren
Nadat u de eindpunten hebt onboarding, configureert u vervolgens de verschillende mogelijkheden, zoals eindpuntdetectie en -reactie, beveiliging van de volgende generatie en de beperking van het oppervlak van de aanval. 


## <a name="example-deployments"></a>Voorbeeldimplementaties
In deze implementatiehandleiding begeleiden we u bij het gebruik van twee implementatiehulpmiddelen voor het onboarden van eindpunten en het configureren van mogelijkheden.

De hulpprogramma's in de voorbeeldimplementaties zijn:
- [Onboarden met behulp van Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Onboarden met behulp van Microsoft Endpoint Manager](onboarding-endpoint-manager.md)

Met behulp van de bovenstaande implementatiehulpmiddelen wordt u begeleid bij het configureren van de volgende Mogelijkheden van Defender voor Eindpunt:
- Configuratie van eindpuntdetectie en -antwoord
- Beveiligingsconfiguratie van de volgende generatie
- Surface Reduction-configuratie voor aanvallen

## <a name="related-topics"></a>Verwante onderwerpen
- [Onboarden met behulp van Microsoft Endpoint Configuration Manager](onboarding-endpoint-configuration-manager.md)
- [Onboarden met behulp van Microsoft Endpoint Manager](onboarding-endpoint-manager.md)
- [Veilige documenten in Microsoft 365 E5](../office-365-security/safe-docs.md)
