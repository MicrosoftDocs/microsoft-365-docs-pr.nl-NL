---
title: McAfee naar Microsoft Defender voor Eindpunt - Voorbereiden
description: Dit is fase 1, Voorbereiden, voor het migreren van McAfee naar Microsoft Defender ATP.
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
- m365solution-mcafeemigrate
- m365solution-scenario
ms.topic: article
ms.custom: migrationguides
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 049539cc5c19d3c6683815d0da949c2a3de10f93
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687791"
---
# <a name="migrate-from-mcafee---phase-1-prepare-for-your-migration"></a>Migreren van McAfee - Fase 1: Voorbereiden op uw migratie

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

|![Fase 1: Voorbereiden](images/phase-diagrams/prepare.png)<br/>Fase 1: Voorbereiden |[![Fase 2: Instellen](images/phase-diagrams/setup.png)](mcafee-to-microsoft-defender-setup.md)<br/>[Fase 2: Instellen](mcafee-to-microsoft-defender-setup.md) |[![Fase 3: Onboarden](images/phase-diagrams/onboard.png)](mcafee-to-microsoft-defender-onboard.md)<br/>[Fase 3: Onboarden](mcafee-to-microsoft-defender-onboard.md) |
|--|--|--|
|*U bent er!*| | |


Welkom bij de fase Voorbereiden van de migratie van **[McAfee Endpoint Security (McAfee) naar Microsoft Defender voor Eindpunt.](mcafee-to-microsoft-defender-migration.md#the-migration-process)** 

Deze migratiefase bevat de volgende stappen:
1. [Updates downloaden en implementeren op de apparaten van uw organisatie](#get-and-deploy-updates-across-your-organizations-devices)
2. [Microsoft Defender voor eindpunt krijgen.](#get-microsoft-defender-for-endpoint)
3. [Toegang verlenen tot het Microsoft Defender-beveiligingscentrum](#grant-access-to-the-microsoft-defender-security-center).
4. [Instellingen voor apparaatproxy en internetverbinding configureren.](#configure-device-proxy-and-internet-connectivity-settings)

## <a name="get-and-deploy-updates-across-your-organizations-devices"></a>Updates downloaden en implementeren op de apparaten van uw organisatie

Als een goede gewoonte houdt u de apparaten en eindpunten van uw organisatie up-to-date. Zorg ervoor dat uw McAfee Endpoint Security -oplossing (McAfee) up-to-date is en dat de besturingssystemen en apps van uw organisatie ook de nieuwste updates hebben. Als u dit nu doet, kunt u problemen later voorkomen wanneer u migreert naar Microsoft Defender voor Eindpunt en Microsoft Defender Antivirus.

### <a name="make-sure-your-mcafee-solution-is-up-to-date"></a>Zorg ervoor dat uw McAfee-oplossing up-to-date is

Houd McAfee up-to-date en zorg ervoor dat de apparaten van uw organisatie de nieuwste beveiligingsupdates hebben. Hulp nodig? Hier zijn enkele McAfee-bronnen:

- [McAfee Enterprise Product Documentation: How Endpoint Security Works](https://docs.mcafee.com/bundle/endpoint-security-10.7.x-common-product-guide-windows/page/GUID-1207FF39-D1D2-481F-BBD9-E4079112A8DD.html)

- [Technisch artikel mcAfee Knowledge Center: Windows Security Center meldt af en toe onjuist dat Endpoint-beveiliging is uitgeschakeld wanneer deze wordt uitgevoerd op Windows 10](https://kc.mcafee.com/corporate/index?page=content&id=KB91830) 

- [McAfee Knowledge Center Technical Article: Windows Security Center reports Endpoint Security is disabled when Endpoint Security is running](https://kc.mcafee.com/corporate/index?page=content&id=KB91428)

- Uw McAfee-ondersteuning ServicePortal ( [http://mysupport.mcafee.com](http://mysupport.mcafee.com) )

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

Nu u de apparaten van uw organisatie hebt bijgewerkt, is de volgende stap om Microsoft Defender voor Eindpunt te krijgen, licenties toe te wijzen en ervoor te zorgen dat de service is ingericht.

1. Koop of probeer microsoft Defender voor eindpunt vandaag nog. [Start een gratis proefversie of vraag een offerte aan.](https://aka.ms/mdatp) 

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

2. RBAC instellen en configureren. We raden [u aan Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) te gebruiken om RBAC te configureren, vooral als uw organisatie een combinatie van Windows 10-, macOS-, iOS- en Android-apparaten gebruikt. Zie [RBAC instellen met Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

    Als uw organisatie een andere methode dan Intune nodig heeft, kiest u een van de volgende opties:
    - [Configuration Manager](https://docs.microsoft.com/mem/configmgr/core/servers/deploy/configure/configure-role-based-administration)
    - [Geavanceerd groepsbeleidsbeheer](https://docs.microsoft.com/microsoft-desktop-optimization-pack/agpm)
    - [Windows-beheercentrum](https://docs.microsoft.com/windows-server/manage/windows-admin-center/overview)

3. Toegang verlenen tot het Microsoft Defender-beveiligingscentrum. (Hulp nodig? Zie [Portaltoegang beheren met RBAC](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/rbac)).

## <a name="configure-device-proxy-and-internet-connectivity-settings"></a>Instellingen voor apparaatproxy en internetverbinding configureren

Als u communicatie tussen uw apparaten en Microsoft Defender voor Eindpunt wilt inschakelen, configureert u proxy- en internetinstellingen. De volgende tabel bevat koppelingen naar bronnen die u kunt gebruiken om uw proxy- en internetinstellingen voor verschillende besturingssystemen en mogelijkheden te configureren:

|Mogelijkheden  | Besturingssysteem | Resources |
|--|--|--|
|[Eindpuntdetectie en -antwoord](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response) (EDR) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 of hoger](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803)  |[Instellingen voor computerproxy en internetverbinding configureren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet) |
|EDR |- [Windows Server 2016](https://docs.microsoft.com/windows/release-health/status-windows-10-1607-and-windows-server-2016) <br/>- [Windows Server 2012 R2](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows Server 2008 R2 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1)<br/>- [Windows 8.1](https://docs.microsoft.com/windows/release-health/status-windows-8.1-and-windows-server-2012-r2)<br/>- [Windows 7 SP1](https://docs.microsoft.com/windows/release-health/status-windows-7-and-windows-server-2008-r2-sp1) |[Instellingen voor proxy- en internetverbinding configureren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#configure-proxy-and-internet-connectivity-settings) |
|EDR  |macOS: <br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave) <br/>- 10,13 (High Sierra)  |[Microsoft Defender voor Eindpunt op macOS: Netwerkverbindingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) |- [Windows 10](https://docs.microsoft.com/windows/release-health/release-information) <br/>- [Windows Server 2019](https://docs.microsoft.com/windows/release-health/status-windows-10-1809-and-windows-server-2019)<br/>- [Windows Server 1803 of hoger](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) <br/>- [Windows Server 2016](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-2016) |[Microsoft Defender Antivirus-netwerkverbindingen configureren en valideren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)<br/> |
|Antivirus |macOS: <br/>- 10,15 (Catalina)<br/>- 10,14 (Mojave) <br/>- 10,13 (High Sierra) |[Microsoft Defender voor Eindpunt op macOS: Netwerkverbindingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac#network-connections) |
|Antivirus |Linux: <br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS of hoger LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Microsoft Defender voor Eindpunt op Linux: Netwerkverbindingen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux#network-connections) 

## <a name="next-step"></a>Volgende stap

**Gefeliciteerd!** U hebt de fase **Voorbereiden** van de [migratie van McAfee naar Microsoft Defender voor Eindpunt voltooid!](mcafee-to-microsoft-defender-migration.md#the-migration-process)

- [Ga verder met het instellen van Microsoft Defender voor Eindpunt](mcafee-to-microsoft-defender-setup.md).
