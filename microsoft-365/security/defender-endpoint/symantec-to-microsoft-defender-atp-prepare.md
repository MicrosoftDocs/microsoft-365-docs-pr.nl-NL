---
title: Symantec to Microsoft Defender for Endpoint - Phase 1, Preparing
description: Dit is Fase 1, Voorbereiden, van de migratie van Symantec naar Microsoft Defender voor Eindpunt.
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
- m365solution-symantecmigrate
ms.topic: article
ms.date: 03/03/2021
ms.custom: migrationguides
ms.reviewer: depicker, yongrhee, chriggs
ms.openlocfilehash: bba48803863cd330b371c24600239462b1ca9250
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327412"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migreren van Symantec - Fase 1: Voorbereiden op uw migratie

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)<br/>Fase 1: Voorbereiden |[![Fase 2: Instellen](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Instellen](symantec-to-microsoft-defender-atp-setup.md) |[![Fase 3: Onboarden](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: Onboarden](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*U bent er!*| | |


**Welkom bij de fase Voorbereiden van [de migratie van Symantec naar Microsoft Defender voor Eindpunt.](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)** 

Deze migratiefase bevat de volgende stappen:
1. [Microsoft Defender voor eindpunt krijgen.](#get-microsoft-defender-for-endpoint)
2. [Toegang verlenen tot het Microsoft Defender-beveiligingscentrum](#grant-access-to-the-microsoft-defender-security-center).
3. [Instellingen voor apparaatproxy en internetverbinding configureren.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-microsoft-defender-for-endpoint"></a>Microsoft Defender voor eindpunten krijgen

Als u wilt beginnen, moet u Microsoft Defender voor Eindpunt hebben, met licenties toegewezen en ingericht.

1. Koop of probeer microsoft Defender voor eindpunt vandaag nog. [Ga naar Microsoft Defender voor Eindpunt om een gratis proefversie te starten of een offerte aan te vragen.](https://aka.ms/mdatp) 
2. Controleer of uw licenties correct zijn ingericht. [Controleer de licentiestaat.](production-deployment.md#check-license-state)
3. Als globale beheerder of beveiligingsbeheerder stelt u uw speciale cloud-exemplaar van Microsoft Defender voor Eindpunt in. Zie [Microsoft Defender for Endpoint setup: Tenant configuration](production-deployment.md#tenant-configuration).
4. Zie [Microsoft Defender for Endpoint setup: Network configuration](production-deployment.md#network-configuration)(Netwerkconfiguratie) als eindpunten (zoals apparaten) in uw organisatie een proxy gebruiken om toegang te krijgen tot internet.
 
Op dit moment bent u klaar om toegang te verlenen aan uw beveiligingsbeheerders en beveiligingsoperatoren die het Microsoft Defender-beveiligingscentrum () zullen [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) gebruiken. 

> [!NOTE]
> Het Microsoft Defender-beveiligingscentrum wordt soms de Microsoft Defender voor Eindpunt-portal genoemd. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Toegang verlenen tot het Microsoft Defender-beveiligingscentrum

Het Microsoft Defender-beveiligingscentrum () is de plek waar u functies en mogelijkheden van Microsoft Defender voor eindpunten kunt openen [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) en configureren. Zie Overzicht van het [Microsoft Defender-beveiligingscentrum](use.md)voor meer informatie.

Machtigingen voor het Microsoft Defender-beveiligingscentrum kunnen worden verleend met basismachtigingen of op rollen gebaseerd toegangsbeheer (RBAC). We raden u aan RBAC te gebruiken, zodat u meer gedetailleerde controle hebt over machtigingen.

1. Plan de rollen en machtigingen voor uw beveiligingsbeheerders en beveiligingsoperatoren. Zie [Toegangsbeheer op basis van rollen](prepare-deployment.md#role-based-access-control).
2. RBAC instellen en configureren. We raden [u aan Intune](/mem/intune/fundamentals/what-is-intune) te gebruiken om RBAC te configureren, vooral als uw organisatie een combinatie van Windows 10-, macOS-, iOS- en Android-apparaten gebruikt. Zie [RBAC instellen met Intune](/mem/intune/fundamentals/role-based-access-control).<br/>
   Als uw organisatie een andere methode dan Intune nodig heeft, kiest u een van de volgende opties:
    - [Configuration Manager](/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Geavanceerd groepsbeleidsbeheer](/microsoft-desktop-optimization-pack/agpm)
    - [Windows-beheercentrum](/windows-server/manage/windows-admin-center/overview)
3. Toegang verlenen tot het Microsoft Defender-beveiligingscentrum. (Hulp nodig? Zie [Portaltoegang beheren met RBAC](rbac.md)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Instellingen voor apparaatproxy en internetverbinding configureren

Als u communicatie tussen uw apparaten en Microsoft Defender voor Eindpunt wilt inschakelen, configureert u proxy- en internetinstellingen. De volgende tabel bevat koppelingen naar bronnen die u kunt gebruiken om uw proxy- en internetinstellingen voor verschillende besturingssystemen en mogelijkheden te configureren:

|Mogelijkheden  | Besturingssysteem | Resources |
|:----|:----|:---|
|[Eindpuntdetectie en -antwoord](overview-endpoint-detection-response.md) (EDR) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 of hoger](/windows-server/get-started/whats-new-in-windows-server-1803)  |[Instellingen voor computerproxy en internetverbinding configureren](configure-proxy-internet.md) |
|EDR |- [Windows Server 2016](/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Instellingen voor proxy- en internetverbinding configureren](onboard-downlevel.md#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave) <br/>- 10,13 (High Sierra)  |[Microsoft Defender voor Eindpunt op macOS: Netwerkverbindingen](microsoft-defender-endpoint-mac.md#network-connections) |
|[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) |- [Windows 10](/windows/release-health/release-information/) <br/>- [Windows Server 2019](/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 of hoger](/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](/windows-server/get-started/whats-new-in-windows-server-2016) |[Netwerkverbindingen van Microsoft Defender Antivirus configureren en valideren](configure-network-connections-microsoft-defender-antivirus.md)<br/> |
|Antivirus |macOS: <br/>- 11.3.1 (Big Sur)<br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave)  |[Microsoft Defender voor Eindpunt op Mac: Netwerkverbindingen](microsoft-defender-endpoint-mac.md#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender voor Eindpunt op Linux: Netwerkverbindingen](microsoft-defender-endpoint-linux.md#network-connections)  |

## <a name="next-step"></a>Volgende stap

**Gefeliciteerd!** U hebt de fase **Voorbereiden** van de [migratie van Symantec naar Microsoft Defender voor Eindpunt voltooid!](symantec-to-microsoft-defender-endpoint-migration.md#the-migration-process)
- [Ga verder met het instellen van Microsoft Defender voor Eindpunt](symantec-to-microsoft-defender-atp-setup.md).
