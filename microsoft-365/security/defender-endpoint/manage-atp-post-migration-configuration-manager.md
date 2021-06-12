---
title: Microsoft Defender voor Eindpunt beheren met Configuration Manager
description: Meer informatie over het beheren van Microsoft Defender voor Eindpunt met Configuration Manager
keywords: post-migration, manage, operations, maintenance, utilization, Configuration Manager, Microsoft Defender for Endpoint, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: 5fde3bfad69a5851dd94b76afb262f8be12d0360
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908255"
---
# <a name="manage-microsoft-defender-for-endpoint-with-configuration-manager"></a>Microsoft Defender voor eindpunt beheren met Configuration Manager

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


We raden u aan [Microsoft Endpoint Manager](/mem)te gebruiken, waaronder [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) (Intune) en [Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction) (Configuration Manager) voor het beheren van de beveiligingsfuncties voor bedreigingen van uw organisatie voor apparaten (ook wel eindpunten genoemd). 
- [Meer informatie over Endpoint Manager](/mem/endpoint-manager-overview)
- [Co-manage Microsoft Defender for Endpoint op Windows 10 apparaten met Configuration Manager en Intune](manage-atp-post-migration-intune.md)

## <a name="configure-microsoft-defender-for-endpoint-with-configuration-manager"></a>Microsoft Defender voor eindpunt configureren met Configuration Manager

|Taak  |Informatiebronnen  |
|---------|---------|
|**Installeer de Configuration Manager-console** als u deze nog niet hebt<br/><br/>*Als u de configuratie-mangerconsole nog niet hebt, gebruikt u deze bronnen om de bits op te halen en te installeren.* |[Het installatiemedia](/mem/configmgr/core/servers/deploy/install/get-install-media)<br/><br/>[Configuratiebeheer-console installeren](/mem/configmgr/core/servers/deploy/install/install-consoles)  |
|**Configuration Manager gebruiken om apparaten aan te nemen** bij Microsoft Defender voor Eindpunt <br/><br/> *Als u apparaten (of eindpunten) nog niet hebt aan boord van Microsoft Defender voor Eindpunt, kunt u dat doen met Configuration Manager.*   |[Onboard to Microsoft Defender for Endpoint with Configuration Manager](/mem/configmgr/protect/deploy-use/defender-advanced-threat-protection#about-onboarding-to-atp-with-configuration-manager)      |
|**Antimalware-beleid beheren en Windows firewallbeveiliging voor** clientcomputers (eindpunten)<br/><br/>*Configureer endpoint protection features, including Microsoft Defender for Endpoint, exploit protection, application control, antimalware, firewall settings, and more.*  |[Configuration Manager: Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection)       |
|**Methoden kiezen voor het bijwerken van antimalware-updates** op de apparaten van uw organisatie <br/><br/>*Met Endpoint Protection in Configuration Manager kunt u kiezen uit verschillende methoden om antimalwaredefinities up-to-date te houden op de apparaten van uw organisatie.* |[Definitie-updates configureren voor Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-definition-updates) <br/><br/>[Configuration Manager gebruiken om definitie-updates te leveren](/mem/configmgr/protect/deploy-use/endpoint-definitions-configmgr) |
|**Netwerkbeveiliging inschakelen** om te voorkomen dat werknemers apps gebruiken die schadelijke inhoud op internet bevatten <br/><br/>*Het is raadzaam eerst [de auditmodus](/microsoft-365/security/defender-endpoint/evaluate-network-protection) te gebruiken voor netwerkbeveiliging in een testomgeving om te zien welke apps worden geblokkeerd voordat ze worden uitgerold.* |[Netwerkbeveiliging in- en uit te zetten met Configuration Manager](/microsoft-365/security/defender-endpoint/enable-network-protection#microsoft-endpoint-configuration-manager)  |
|**Beheerde maptoegang configureren om** te beschermen tegen ransomware <br/><br/>*Gecontroleerde maptoegang wordt ook wel antiransomwarebeveiliging genoemd.*   |[Endpoint protection: Gecontroleerde maptoegang](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Gecontroleerde maptoegang inschakelen in Microsoft Endpoint Configuration Manage](/microsoft-365/security/defender-endpoint/enable-controlled-folders#microsoft-endpoint-configuration-manager) |

## <a name="configure-your-microsoft-defender-security-center"></a>Uw Microsoft Defender-beveiligingscentrum

Als u dit nog niet hebt gedaan, configureert u uw Microsoft 365 Defender-portal om waarschuwingen weer te geven, functies voor bedreigingsbeveiliging te configureren en gedetailleerde informatie weer te geven over de algehele beveiligingsstatus van uw organisatie. Zie [Microsoft Defender-beveiligingscentrum](microsoft-defender-security-center.md). U kunt ook configureren of en welke functies eindgebruikers kunnen zien in de Microsoft 365 Defender-portal.

- [Overzicht van de Microsoft Defender-beveiligingscentrum](/microsoft-365/security/defender-endpoint/use)

- [Eindpuntbeveiliging: Microsoft Defender-beveiligingscentrum](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Volgende stappen

- [Een overzicht van Threat and Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Ga naar het Microsoft Defender-beveiligingscentrum dashboard voor beveiligingsbewerkingen](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Microsoft Defender voor eindpunt beheren met Intune](manage-atp-post-migration-intune.md)
