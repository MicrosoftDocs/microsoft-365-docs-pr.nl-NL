---
title: Microsoft Defender Antivirus implementeren, beheren en rapporteren
description: U kunt Microsoft Defender Antivirus implementeren en beheren met Intune, Microsoft Endpoint Configuration Manager, Group Policy, PowerShell of WMI
keywords: implementeren, beheren, bijwerken, beschermen, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b44bc529a14d12d2be49854c31a4ea11cdabc7d1
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764841"
---
# <a name="deploy-manage-and-report-on-microsoft-defender-antivirus"></a>Microsoft Defender Antivirus implementeren, beheren en rapporteren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

U kunt Microsoft Defender Antivirus op verschillende manieren implementeren, beheren en rapporteren.

Omdat de Microsoft Defender Antivirus-client is geïnstalleerd als een belangrijk onderdeel van Windows 10, is de traditionele implementatie van een client op uw eindpunten niet van toepassing.

In de meeste gevallen moet u echter nog steeds de beveiligingsservice op uw eindpunten inschakelen met Microsoft Intune, Microsoft Endpoint Configuration Manager, Azure Defender of Groepsbeleidsobjecten, die in de volgende tabel worden beschreven.

U ziet ook extra koppelingen voor:

- Microsoft Defender Antivirusbeveiliging beheren, inclusief het beheren van product- en beveiligingsupdates
- Rapportage over Microsoft Defender Antivirusbeveiliging

> [!IMPORTANT]
> In de meeste gevallen schakelt Windows 10 Microsoft Defender Antivirus uit als er een ander antivirusproduct wordt gevonden dat actief en up-to-date is. U moet antivirusproducten van derden uitschakelen of verwijderen voordat Microsoft Defender Antivirus werkt. Als u antivirusproducten van derden opnieuw in- of installeert, wordt Microsoft Defender Antivirus automatisch uitgeschakeld in Windows 10.

Hulpmiddel|Implementatieopties (<a href="#fn2" id="ref2">2</a>)|Beheeropties (netwerkbrede configuratie en beleid of basislijnimplementatie) ([3](#fn3))|Rapportageopties  
---|---|---|---  
Microsoft Intune|[Instellingen voor eindpuntbeveiliging toevoegen in Intune](/intune/endpoint-protection-configure)|[Instellingen voor apparaatbeperkingen configureren in Intune](/intune/device-restrictions-configure)| [De Intune-console gebruiken om apparaten te beheren](/intune/device-management)  
Microsoft Endpoint Manager ([1](#fn1))|De rol [van het endpoint protection point site system gebruiken][] en [Endpoint Protection inschakelen met aangepaste clientinstellingen][]|Met [standaard- en aangepaste antimalwarebeleidsregels][] en [clientbeheer][]|Met de [standaardwerkruimte Configuration Manager Monitoring en][] [e-mailwaarschuwingen][]  
Groepsbeleid en Active Directory (domeingevoegd)|Gebruik een groepsbeleidsobject om configuratiewijzigingen te implementeren en ervoor te zorgen dat Microsoft Defender Antivirus is ingeschakeld.|Groepsbeleidsobjecten (GPOs) gebruiken om [updateopties][] voor Microsoft Defender Antivirus te configureren en [Windows Defender-functies te configureren][]|Eindpuntrapportage is niet beschikbaar met groepsbeleid. U kunt een lijst met groepsbeleidsregels genereren om te bepalen of [instellingen of beleidsregels niet worden toegepast][]
PowerShell|Implementeren met groepsbeleid, Microsoft Endpoint Configuration Manager of handmatig op afzonderlijke eindpunten.|Gebruik de [cmdlets Set-MpPreference] en [Update-MpSignature] die beschikbaar zijn in de Defender-module.|De juiste [Get-cmdlets gebruiken die beschikbaar zijn in de Defender-module][]
Windows Management Instrumentation|Implementeren met groepsbeleid, Microsoft Endpoint Configuration Manager of handmatig op afzonderlijke eindpunten.|Gebruik de [methode Set van de MSFT_MpPreference klas][] en de methode Bijwerken van de MSFT_MpSignature [klas][]|Gebruik de [MSFT_MpComputerStatus][] en de methode voor het krijgen van bijbehorende klassen in de [Windows Defender WMIv2-provider][]
Microsoft Azure|Implementeer Microsoft Antimalware voor Azure in de Azure-portal, met behulp van virtual machineconfiguratie van Visual Studio of met [azure PowerShell-cmdlets.](/azure/security/azure-security-antimalware#antimalware-deployment-scenarios) U kunt ook [Endpoint-beveiliging installeren in Azure Defender*](/azure/security-center/security-center-install-endpoint-protection)|[Microsoft Antimalware configureren voor virtuele machines en cloudservices met Azure PowerShell-cmdlets](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) of [codevoorbeelden gebruiken](https://gallery.technet.microsoft.com/Antimalware-For-Azure-5ce70efe)|Gebruik [Microsoft Antimalware voor virtuele machines en cloudservices met Azure PowerShell-cmdlets](/azure/security/azure-security-antimalware#enable-and-configure-antimalware-using-powershell-cmdlets) om monitoring in te stellen. U kunt ook gebruiksrapporten in Azure Active Directory [][] controleren om verdachte activiteiten te bepalen, waaronder het rapport Mogelijk geïnfecteerde apparaten en een SIEM-hulpprogramma configureren om te rapporteren over [Microsoft Defender Antivirus-gebeurtenissen][] en dat hulpprogramma als een app toe te voegen in AAD.

1. <span id="fn1" />De beschikbaarheid van bepaalde functies en functies, met name met betrekking tot beveiliging in de cloud, verschilt tussen Microsoft Endpoint Manager (Current Branch) en System Center 2012 Configuration Manager. In deze bibliotheek hebben we ons gericht op Windows 10, Windows Server 2016 en Microsoft Endpoint Manager (Current Branch). Zie [Microsoft Cloud-beveiliging gebruiken in Microsoft Defender Antivirus](cloud-protection-microsoft-defender-antivirus.md) voor een tabel waarin de belangrijkste verschillen worden beschreven. [(Terug naar tabel)](#ref2)
  
2.  <span id="fn2" />In Windows 10 is Microsoft Defender Antivirus een onderdeel dat beschikbaar is zonder installatie of implementatie van een extra client of service. Deze wordt automatisch ingeschakeld wanneer antivirusproducten van derden worden verwijderd of verouderd zijn ( behalve[op Windows Server 2016).](microsoft-defender-antivirus-on-windows-server.md) Traditionele implementatie is daarom niet vereist. Implementatie hier verwijst naar ervoor zorgen dat het Microsoft Defender Antivirus-onderdeel beschikbaar is en is ingeschakeld op eindpunten of servers. [(Terug naar tabel)](#ref2)

3. <span id="fn3" />Configuratie van functies en beveiliging, waaronder het configureren van product- en beveiligingsupdates, worden verder beschreven in de sectie Antivirusfuncties van [Microsoft Defender configureren](configure-notifications-microsoft-defender-antivirus.md) in deze bibliotheek. [(Terug naar tabel)](#ref2)

[Systeemrol van eindpuntbeveiligingspuntsite]: /configmgr/protect/deploy-use/endpoint-protection-site-role
[standaard- en aangepaste antimalwarebeleidsregels]:  /configmgr/protect/deploy-use/endpoint-antimalware-policies
[clientbeheer]:  /configmgr/core/clients/manage/manage-clients
[Endpoint Protection inschakelen met aangepaste clientinstellingen]:  /configmgr/protect/deploy-use/endpoint-protection-configure-client
[Werkruimte Configuratiebeheercontrole]:  /configmgr/protect/deploy-use/monitor-endpoint-protection
[e-mailwaarschuwingen]:  /configmgr/protect/deploy-use/endpoint-configure-alerts
[Deploy the Microsoft Intune client to endpoints]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune
[custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection
 [custom Intune policy]:  /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#configure-microsoft-intune-endpoint-protection 
[manage tasks]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#choose-management-tasks-for-endpoint-protection
[Monitor endpoint protection in the Microsoft Intune administration console]: /intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune#monitor-endpoint-protection
[Setmethode van de MSFT_MpPreference klas]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[Updatemethode van de MSFT_MpSignature klas]:  /previous-versions/windows/desktop/defender/set-msft-mppreference
[MSFT_MpComputerStatus]:  /previous-versions/windows/desktop/defender/msft-mpcomputerstatus
[Windows Defender WMIv2-provider]: /previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal
[Set-MpPreference]:  https://technet.microsoft.com/itpro/powershell/windows/defender/set-mppreference.md
[Update-MpSignature]: /powershell/module/defender/update-mpsignature
[Get-cmdlets beschikbaar in de Defender-module]: /powershell/module/defender/
[Updateopties configureren voor Microsoft Defender Antivirus]: manage-updates-baselines-microsoft-defender-antivirus.md
[Windows Defender-functies configureren]: configure-microsoft-defender-antivirus-features.md
[Groepsbeleid om te bepalen of instellingen of beleidsregels niet worden toegepast]: /previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc771389(v=ws.11)
[Mogelijk geïnfecteerde apparaten]: /azure/active-directory/active-directory-reporting-sign-ins-from-possibly-infected-devices
[Microsoft Defender Antivirus-gebeurtenissen]: troubleshoot-microsoft-defender-antivirus.md

## <a name="in-this-section"></a>In deze sectie

Onderwerp | Beschrijving
---|---
[Microsoft Defender Antivirusbeveiliging implementeren en inschakelen](deploy-microsoft-defender-antivirus.md) | Hoewel de client is geïnstalleerd als een belangrijk onderdeel van Windows 10 en traditionele implementatie niet van toepassing is, moet u de client op uw eindpunten nog steeds inschakelen met Microsoft Endpoint Configuration Manager, Microsoft Intune of Groepsbeleidsobjecten. 
[Microsoft Defender Antivirus-updates beheren en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md) | Er zijn twee onderdelen voor het bijwerken van Microsoft Defender Antivirus: het bijwerken van de client op eindpunten (productupdates) en het bijwerken van beveiligingsinformatie (beveiligingsupdates). U kunt beveiligingsinformatie op verschillende manieren bijwerken met Behulp van Microsoft Endpoint Configuration Manager, Groepsbeleid, PowerShell en WMI.
[Microsoft Defender Antivirusbeveiliging controleren en rapporteren](report-monitor-microsoft-defender-antivirus.md) | U kunt Microsoft Intune, Microsoft Endpoint Configuration Manager, de invoegpositie Update Compliance voor Microsoft Operations Management Suite of een SIEM-product van derden (door windows-gebeurtenislogboeken te consumeren) gebruiken om de beveiligingsstatus te controleren en rapporten over eindpuntbeveiliging te maken.