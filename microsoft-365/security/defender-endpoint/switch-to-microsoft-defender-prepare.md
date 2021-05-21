---
title: Overschakelen naar Microsoft Defender voor Eindpunt - Voorbereiden
description: Dit is fase 1, Voorbereiden, voor het migreren naar Microsoft Defender voor Eindpunt.
keywords: migratie, Microsoft Defender voor Eindpunt, edr
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
- m365solution-migratetomdatp
ms.topic: article
ms.custom: migrationguides
ms.date: 05/20/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 92dfc279344b003ab651110375982b0f065dfb0d
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/21/2021
ms.locfileid: "52594167"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-1-prepare"></a>Overschakelen naar Microsoft Defender voor Eindpunt - Fase 1: Voorbereiden

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| ![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)<br/>Fase 1: Voorbereiden | [![Fase 2: Instellen](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Fase 2: Instellen](switch-to-microsoft-defender-setup.md) | [![Fase 3: Onboarden](images/phase-diagrams/onboard.png)](switch-to-microsoft-defender-onboard.md)<br/>[Fase 3: Onboarden](switch-to-microsoft-defender-onboard.md) |
|--|--|--|
|*U bent er!*| | |

**Welkom bij de voorbereidingsfase van het [overstappen naar Defender voor eindpunt.](switch-to-microsoft-defender-migration.md#the-migration-process)** 

Deze migratiefase bevat de volgende stappen:

1. [Updates downloaden en implementeren op de apparaten van uw organisatie](#get-and-deploy-updates-across-your-organizations-devices)
2. [Krijg Defender voor eindpunt](#get-microsoft-defender-for-endpoint).
3. [Toegang verlenen tot de Microsoft Defender-beveiligingscentrum.](#grant-access-to-the-microsoft-defender-security-center)
4. [Instellingen voor apparaatproxy en internetverbinding configureren.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Updates downloaden en implementeren op de apparaten van uw organisatie

Als een goede gewoonte houdt u de apparaten en eindpunten van uw organisatie up-to-date. Zorg ervoor dat uw bestaande endpointbeveiligings- en antivirusoplossing up-to-date is en dat de besturingssystemen en apps van uw organisatie ook de nieuwste updates hebben. Als u dit nu doet, kunt u problemen later voorkomen wanneer u migreert naar Defender voor Eindpunt en Microsoft Defender Antivirus.

### <a name="make-sure-your-existing-solution-is-up-to-date"></a>Zorg ervoor dat uw bestaande oplossing up-to-date is

Houd uw bestaande oplossing voor eindpuntbeveiliging up-to-date en zorg ervoor dat de apparaten van uw organisatie de nieuwste beveiligingsupdates hebben. 

Hulp nodig? Bekijk de documentatie van uw oplossingsprovider.

### <a name="make-sure-your-organizations-devices-are-up-to-date"></a>Zorg ervoor dat de apparaten van uw organisatie up-to-date zijn

Hulp nodig bij het bijwerken van de apparaten van uw organisatie? Zie de volgende bronnen:

|BESTURINGSSYSTEEM | Resource |
|:--|:--|
|Windows |[Microsoft Update](https://www.update.microsoft.com) |
|macOS | [De software op uw Mac bijwerken](https://support.apple.com/HT201541)|
|iOS |[Uw iPhone, iPad of iPod touch bijwerken](https://support.apple.com/HT204204)|
|Android |[Controleren & uw Android-versie bijwerken](https://support.google.com/android/answer/7680439) |
|Linux | [Linux 101: Uw systeem bijwerken](https://www.linux.com/training-tutorials/linux-101-updating-your-system) |

## <a name="get-microsoft-defender-for-endpoint"></a>Microsoft Defender voor eindpunten krijgen

Nu u de apparaten van uw organisatie hebt bijgewerkt, is de volgende stap om Defender voor Eindpunt te krijgen, licenties toe te wijzen en ervoor te zorgen dat de service is ingericht.

1. Koop of probeer Defender voor Eindpunt vandaag nog. [Start een gratis proefversie of vraag een offerte aan.](https://aka.ms/mdatp) 

2. Controleer of uw licenties correct zijn ingericht. [Controleer de licentiestaat.](production-deployment.md#check-license-state)

3. Als globale beheerder of beveiligingsbeheerder kunt u uw speciale cloud-exemplaar van Defender voor Eindpunt instellen. Zie [Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).

4. Als eindpunten (zoals apparaten) in uw organisatie een proxy gebruiken om toegang te krijgen tot internet, zie [Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration).
 
Op dit moment bent u klaar om toegang te verlenen aan uw beveiligingsbeheerders en beveiligingsbeheerders die de Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ). 

> [!NOTE]
> De Microsoft Defender-beveiligingscentrum wordt soms de Defender for Endpoint-portal genoemd en kan worden geopend op [https://securitycenter.windows.com](https://securitycenter.windows.com) . 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Toegang verlenen tot de Microsoft Defender-beveiligingscentrum

De Microsoft Defender-beveiligingscentrum ( ) is de plaats waar u functies en mogelijkheden van Defender voor eindpunten kunt openen [https://securitycenter.windows.com](https://securitycenter.windows.com) en configureren. Zie Overzicht van de [Microsoft Defender-beveiligingscentrum.](use.md)

Machtigingen voor de Microsoft Defender-beveiligingscentrum kunnen worden verleend met basismachtigingen of op rollen gebaseerd toegangsbeheer (RBAC). We raden u aan RBAC te gebruiken, zodat u meer gedetailleerde controle hebt over machtigingen.

1. Plan de rollen en machtigingen voor uw beveiligingsbeheerders en beveiligingsoperatoren. Zie [Toegangsbeheer op basis van rollen](prepare-deployment.md#role-based-access-control).

2. RBAC instellen en configureren. We raden [u aan Intune](/mem/intune/fundamentals/what-is-intune) te gebruiken om RBAC te configureren, vooral als uw organisatie een combinatie van Windows 10, macOS, iOS en Android-apparaten gebruikt. Zie [RBAC instellen met Intune](/mem/intune/fundamentals/role-based-access-control).

    Als uw organisatie een andere methode dan Intune nodig heeft, kiest u een van de volgende opties:

    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Geavanceerd groepsbeleidsbeheer](/microsoft-desktop-optimization-pack/agpm)
    - [Windows Beheercentrum](/windows-server/manage/windows-admin-center/overview)

3. Toegang verlenen tot de Microsoft Defender-beveiligingscentrum. (Hulp nodig? Zie [Portaltoegang beheren met RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Instellingen voor apparaatproxy en internetverbinding configureren

Als u de communicatie tussen uw apparaten en Defender voor Eindpunt wilt inschakelen, configureert u proxy- en internetinstellingen. De volgende tabel bevat koppelingen naar bronnen die u kunt gebruiken om uw proxy- en internetinstellingen voor verschillende besturingssystemen en mogelijkheden te configureren:

| Mogelijkheden  | Besturingssysteem | Resources |
|:--|:--|:--|
| [Eindpuntdetectie en -antwoord](overview-endpoint-detection-response.md) (EDR) | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 of hoger](/windows-server/get-started/whats-new-in-windows-server-1803)  | [Instellingen voor computerproxy en internetverbinding configureren](configure-proxy-internet.md) |
| EDR | [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <p>[Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<p>[Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<p>[Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Instellingen voor proxy- en internetverbinding configureren](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
| EDR  | macOS:<p>11.3.1 (Big Sur)<p>10,15 (Catalina)<p>10,14 (Mojave)   | [Defender voor Eindpunt op macOS: Netwerkverbindingen](microsoft-defender-endpoint-mac.md#network-connections)  |
| [Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) | [Windows 10](/windows/release-health/release-information) <p>[Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<p>[Windows Server 1803 of hoger](/windows-server/get-started/whats-new-in-windows-server-1803) <p>[Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) | [Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
| Antivirus | macOS:<p>11.3.1 (Big Sur)<p>10,15 (Catalina)<p>10,14 (Mojave) | [Defender voor Eindpunt op macOS: Netwerkverbindingen](microsoft-defender-endpoint-mac.md#network-connections) |
| Antivirus | Linux: <p>RHEL 7.2+<p>CentOS Linux 7.2+<p>Ubuntu 16 LTS of hoger LTS<p>SLES 12+<p>Debian 9+<p>Oracle Linux 7.2 | [Defender voor Eindpunt op Linux: Netwerkverbindingen](microsoft-defender-endpoint-linux.md#network-connections) |

## <a name="next-step"></a>Volgende stap

**Gefeliciteerd!** U hebt de **fase** Voorbereiden van overstappen op Defender voor Eindpunt [voltooid!](switch-to-microsoft-defender-migration.md#the-migration-process)

- [Ga verder met het instellen van Defender voor Eindpunt](switch-to-microsoft-defender-setup.md).
