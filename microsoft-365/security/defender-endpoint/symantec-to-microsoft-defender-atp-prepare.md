---
title: Symantec to Microsoft Defender for Endpoint - Phase 1, Preparing
description: Dit is Fase 1, Voorbereiden, van de migratie van Symantec naar Microsoft Defender voor Eindpunt.
keywords: migratie, windows defender advanced threat protection, atp, edr
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
ms.openlocfilehash: 8784c8d608666946461ddc27aa2e7f2b740276a0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185488"
---
# <a name="migrate-from-symantec---phase-1-prepare-for-your-migration"></a>Migreren van Symantec - Fase 1: Voorbereiden op uw migratie

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)<br/>Fase 1: Voorbereiden |[![Fase 2: Instellen](images/phase-diagrams/setup.png)](symantec-to-microsoft-defender-atp-setup.md)<br/>[Fase 2: Instellen](symantec-to-microsoft-defender-atp-setup.md) |[![Fase 3: Onboard](images/phase-diagrams/onboard.png)](symantec-to-microsoft-defender-atp-onboard.md)<br/>[Fase 3: Onboard](symantec-to-microsoft-defender-atp-onboard.md) |
|--|--|--|
|*U bent er!*| | |


**Welkom bij de fase Voorbereiden van [de migratie van Symantec naar Microsoft Defender voor Eindpunt.](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)** 

Deze migratiefase bevat de volgende stappen:
1. [Microsoft Defender voor eindpunt krijgen.](#get-microsoft-defender-for-endpoint)
2. [Toegang verlenen tot het Microsoft Defender-beveiligingscentrum](#grant-access-to-the-microsoft-defender-security-center).
3. [Instellingen voor apparaatproxy en internetverbinding configureren.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-microsoft-defender-for-endpoint"></a>Microsoft Defender voor eindpunten krijgen

Als u wilt beginnen, moet u Microsoft Defender voor Eindpunt hebben, met licenties toegewezen en ingericht.

1. Koop of probeer microsoft Defender voor eindpunt vandaag nog. [Ga naar Microsoft Defender voor Eindpunt om een gratis proefversie te starten of een offerte aan te vragen.](https://aka.ms/mdatp) 
2. Controleer of uw licenties correct zijn ingericht. [Controleer de licentiestaat.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#check-license-state)
3. Als globale beheerder of beveiligingsbeheerder stelt u uw speciale cloud-exemplaar van Microsoft Defender voor Eindpunt in. Zie [Microsoft Defender for Endpoint setup: Tenant configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#tenant-configuration).
4. Zie [Microsoft Defender for Endpoint setup: Network configuration](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/production-deployment#network-configuration)(Netwerkconfiguratie) als eindpunten (zoals apparaten) in uw organisatie een proxy gebruiken om toegang te krijgen tot internet.
 
Op dit moment bent u klaar om toegang te verlenen aan uw beveiligingsbeheerders en beveiligingsoperatoren die het Microsoft Defender-beveiligingscentrum () zullen [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) gebruiken. 

> [!NOTE]
> Het Microsoft Defender-beveiligingscentrum wordt soms de Microsoft Defender voor Eindpunt-portal genoemd. 

## <a name="grant-access-to-the-microsoft-defender-security-center"></a>Toegang verlenen tot het Microsoft Defender-beveiligingscentrum

Het Microsoft Defender-beveiligingscentrum () is de plek waar u functies en mogelijkheden van Microsoft Defender voor eindpunten kunt openen [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) en configureren. Zie Overzicht van het [Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)voor meer informatie.

Machtigingen voor het Microsoft Defender-beveiligingscentrum kunnen worden verleend met basismachtigingen of op rollen gebaseerd toegangsbeheer (RBAC). We raden u aan RBAC te gebruiken, zodat u meer gedetailleerde controle hebt over machtigingen.

1. Plan de rollen en machtigingen voor uw beveiligingsbeheerders en beveiligingsoperatoren. Zie [Toegangsbeheer op basis van rollen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/prepare-deployment#role-based-access-control).
2. RBAC instellen en configureren. We raden [u aan Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) te gebruiken om RBAC te configureren, vooral als uw organisatie een combinatie van Windows 10-, macOS-, iOS- en Android-apparaten gebruikt. Zie [RBAC instellen met Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).<br/>
   Als uw organisatie een andere methode dan Intune nodig heeft, kiest u een van de volgende opties:
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Geavanceerd groepsbeleidsbeheer](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows-beheercentrum](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)
3. Toegang verlenen tot het Microsoft Defender-beveiligingscentrum. (Hulp nodig? Zie [Portaltoegang beheren met RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Instellingen voor apparaatproxy en internetverbinding configureren

Als u communicatie tussen uw apparaten en Microsoft Defender voor Eindpunt wilt inschakelen, configureert u proxy- en internetinstellingen. De volgende tabel bevat koppelingen naar bronnen die u kunt gebruiken om uw proxy- en internetinstellingen voor verschillende besturingssystemen en mogelijkheden te configureren:

|Mogelijkheden  | Besturingssysteem | Resources |
|:----|:----|:---|
|[Eindpuntdetectie en -antwoord](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 of hoger](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Instellingen voor computerproxy en internetverbinding configureren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Instellingen voor proxy- en internetverbinding configureren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave) <br/>- 10,13 (High Sierra)  |[Microsoft Defender voor Eindpunt voor Mac: Netwerkverbindingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information/) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 of hoger](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Microsoft Defender Antivirus-netwerkverbindingen configureren en valideren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivirus |macOS: <br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave) <br/>- 10,13 (High Sierra) |[Microsoft -Defender voor Eindpunt voor Mac: Netwerkverbindingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender voor Eindpunt voor Linux: Netwerkverbindingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections)  |

## <a name="next-step"></a>Volgende stap

**Gefeliciteerd!** U hebt de fase **Voorbereiden** van de [migratie van Symantec naar Microsoft Defender voor Eindpunt voltooid!](symantec-to-microsoft-defender-atp-migration.md#the-migration-process)
- [Ga verder met het instellen van Microsoft Defender voor Eindpunt](symantec-to-microsoft-defender-atp-setup.md).
