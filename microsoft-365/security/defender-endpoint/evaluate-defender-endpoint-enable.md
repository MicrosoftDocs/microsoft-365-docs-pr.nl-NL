---
title: Pilot Defender voor endpoint-evaluatie
description: Schakel uw Microsoft 365 Defender proeflaboratorium of testomgeving in.
keywords: Microsoft 365 Defender proefversie, probeer Microsoft 365 Defender, evalueer Microsoft 365 Defender, Microsoft 365 Defender evaluatielaboratorium, Microsoft 365 Defender-pilot, cyberbeveiliging, geavanceerde permanente bedreiging, bedrijfsbeveiliging, apparaten, apparaat, identiteit, gebruikers, gegevens, toepassingen, incidenten, geautomatiseerd onderzoek en herstel, geavanceerd zoeken
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4345ac0a2758e87160be83c6abd96cdbaa6822dc
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457842"
---
# <a name="pilot-mde-evaluation"></a>Pilot MDE-evaluatie

>[!NOTE]
>Om u te begeleiden bij een normale implementatie, wordt in dit scenario alleen het gebruik van Microsoft Endpoint Configuration Manager. Defender voor Eindpunt ondersteunt het gebruik van andere onboarding-hulpprogramma's, maar deze scenario's worden niet in de implementatiehandleiding bestrijken. Zie Onboard devices to Microsoft Defender for Endpoint (Onboard [devices to Microsoft Defender for Endpoint) voor meer informatie.](onboard-configure.md)

## <a name="step-1-check-license-state"></a>Stap 1. Licentiestaat controleren

Controleren op de licentiestaat en of deze goed is ingericht, kan via het beheercentrum of via de **Microsoft Azure portal.**

1. Als u uw licenties wilt bekijken, gaat u naar de **Microsoft Azure portal** en gaat u naar de [Microsoft Azure portallicentiesectie.](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products)

   ![Afbeelding van de pagina Azure Licensing](images/atp-licensing-azure-portal.png)

1. U kunt ook in het beheercentrum naar  >  **Factureringsabonnementen gaan.**

    Op het scherm ziet u alle inrichtende licenties en de huidige **status.**

    ![Afbeelding van factureringslicenties](images/atp-billing-subscriptions.png)

## <a name="step-2-onboard-endpoints-using-any-of-the-supported-management-tools"></a>Stap 2. Onboard-eindpunten met behulp van een van de ondersteunde beheerhulpmiddelen

Het [implementatieonderwerp](deployment-strategy.md) Plannen bevat een overzicht van de algemene stappen die u moet ondernemen om Defender voor Eindpunt te implementeren.  

Bekijk deze video voor een kort overzicht van het onboardingproces en lees meer over de beschikbare hulpprogramma's en methoden.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bGqr]

Nadat u de architectuur hebt identificeren, moet u bepalen welke implementatiemethode u wilt gebruiken. Het implementatieprogramma dat u kiest, is van invloed op de manier waarop u eindpunten aan boord van de service inwerkt.

### <a name="onboarding-tool-options"></a>Opties voor onboarding-hulpprogramma's

In de volgende tabel ziet u de beschikbare hulpprogramma's op basis van het eindpunt dat u nodig hebt om aan boord te gaan.

| Eindpunt     | Opties voor hulpprogramma's                       |
|--------------|------------------------------------------|
| **Windows**  |  [Lokaal script (maximaal 10 apparaten)](../defender-endpoint/configure-endpoints-script.md) <br> [Groepsbeleid](../defender-endpoint/configure-endpoints-gp.md) <br> [Microsoft Endpoint Manager/ Mobile Device Manager](../defender-endpoint/configure-endpoints-mdm.md) <br> [Microsoft Endpoint Configuration Manager](../defender-endpoint/configure-endpoints-sccm.md) <br> [VDI-scripts](../defender-endpoint/configure-endpoints-vdi.md) <br> [Integratie met Azure Defender](../defender-endpoint/configure-server-endpoints.md#integration-with-azure-defender) |
| **macOS**    | [Lokale scripts](../defender-endpoint/mac-install-manually.md) <br> [Microsoft Endpoint Manager](../defender-endpoint/mac-install-with-intune.md) <br> [JAMF-Pro](../defender-endpoint/mac-install-with-jamf.md) <br> [Mobile Device Management](../defender-endpoint/mac-install-with-other-mdm.md) |
| **Linux Server** | [Lokaal script](../defender-endpoint/linux-install-manually.md) <br> [Poppop](../defender-endpoint/linux-install-with-puppet.md) <br> [Ansible](../defender-endpoint/linux-install-with-ansible.md)|
| **iOS**      | [App-gebaseerde](../defender-endpoint/ios-install.md)                                |
| **Android**  | [Microsoft Endpoint Manager](../defender-endpoint/android-intune.md)               |
