---
title: Microsoft Defender voor eindpunten beheren na de migratie
description: Nu u de overstap hebt gemaakt naar Microsoft Defender voor Eindpunt, is de volgende stap het beheren van uw beveiligingsfuncties voor bedreigingen
keywords: post-migration, manage, operations, maintenance, utilization, Microsoft Defender for Endpoint, edr
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
ms.topic: conceptual
ms.date: 01/26/2021
ms.reviewer: chventou
ms.openlocfilehash: ea5e4cb1c4a93f5f8bd5da1c0c94b095d03ac680
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845616"
---
# <a name="manage-microsoft-defender-for-endpoint-post-migration"></a>Microsoft Defender voor Eindpunt beheren, na migratie

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Nadat u van uw vorige endpointbeveiligings- en antivirusoplossing naar Microsoft Defender voor Eindpunt bent over stappen, is de volgende stap het beheren van uw functies en mogelijkheden. We raden u [aan Microsoft Endpoint Manager](/mem/endpoint-manager-overview), waaronder Microsoft Intune [en](/mem/intune/fundamentals/what-is-intune) [Microsoft Endpoint Configuration Manager,](/mem/configmgr/core/understand/introduction)te gebruiken om de apparaten en beveiligingsinstellingen van uw organisatie te beheren. U kunt echter andere hulpprogramma's/methoden gebruiken, zoals [Groepsbeleidsobjecten in Azure Active Directory Domain Services.](/azure/active-directory-domain-services/manage-group-policy) 

De volgende tabel bevat verschillende hulpmiddelen/methoden die u kunt gebruiken, met koppelingen voor meer informatie. 
<br/><br/>

|Hulpmiddel/methode  |Beschrijving  |
|---------|---------|
|**[Bedreigings- vulnerability management dashboardinzichten](/windows/security/threat-protection/microsoft-defender-atp/tvm-dashboard-insights)** in de Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) |Het bedreigingsdashboard & vulnerability management actie-informatie die uw beveiligingsteam kan gebruiken om de blootstelling te beperken en de beveiliging van uw organisatie te verbeteren. <br/><br/>Zie [Bedreiging & vulnerability management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt) en overzicht van de [Microsoft Defender-beveiligingscentrum.](/microsoft-365/security/defender-endpoint/use)  |
|**[Microsoft Intune](/mem/intune/fundamentals/what-is-intune)** (aanbevolen)    |Microsoft Intune (Intune), een onderdeel van [Microsoft Endpoint Manager](/mem/endpoint-manager-overview), richt zich op mobile device management (MDM) en mobile application management (MAM). Met Intune kunt u bepalen hoe de apparaten van uw organisatie worden gebruikt, waaronder mobiele telefoons, tablets en laptops. U kunt ook specifieke beleidsregels configureren voor het beheer van toepassingen. <br/><br/>Zie [Microsoft Defender voor eindpunt beheren met Intune](manage-atp-post-migration-intune.md).         |
|**[Microsoft Endpoint Configuration Manager](/mem/configmgr/core/understand/introduction)**     |Microsoft Endpoint Manager (Configuration Manager), voorheen bekend als System Center Configuration Manager, is een onderdeel van [Microsoft Endpoint Manager.](/mem/endpoint-manager-overview) Configuration Manager is een krachtig hulpmiddel om uw gebruikers, apparaten en software te beheren.<br/><br/>Zie [Microsoft Defender voor eindpunt beheren met Configuration Manager.](manage-atp-post-migration-configuration-manager.md)        |
|**[Groepsbeleidsobjecten in Azure Active Directory Domain Services](/azure/active-directory-domain-services/manage-group-policy)** |[Azure Active Directory Domain Services](/azure/active-directory-domain-services/overview) bevat ingebouwde groepsbeleidsobjecten voor gebruikers en apparaten. U kunt de ingebouwde groepsbeleidsobjecten zo nodig aanpassen voor uw omgeving en aangepaste groepsbeleidsobjecten en organisatie-eenheden (OUs) maken. <br/><br/>Zie [Microsoft Defender voor eindpunt beheren met groepsbeleidsobjecten](manage-atp-post-migration-group-policy-objects.md). |
|**[PowerShell, WMI en MPCmdRun.exe](manage-atp-post-migration-other-tools.md)** |*Het is raadzaam om Microsoft Endpoint Manager (waaronder Intune en Configuration Manager) te gebruiken om functies voor bedreigingsbeveiliging op de apparaten van uw organisatie te beheren. U kunt echter enkele instellingen configureren, zoals Microsoft Defender Antivirus instellingen op afzonderlijke apparaten (eindpunten) met PowerShell, WMI of het MPCmdRun.exe hulpprogramma.*<br/><br/>U kunt PowerShell gebruiken om uw Microsoft Defender Antivirus te beheren, bescherming te gebruiken en de surface reduction-regels voor uw aanval te gebruiken. Zie [Microsoft Defender voor eindpunt configureren met PowerShell.](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-powershell)<br/><br/>U kunt Windows Management Instrumentation (WMI) gebruiken om Microsoft Defender Antivirus en uitsluitingen te beheren. Zie [Microsoft Defender voor eindpunt configureren met WMI](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-windows-management-instrumentation-wmi).<br/><br/>U kunt de Microsoft Malware Protection Command-Line Utility (MPCmdRun.exe) gebruiken om Microsoft Defender Antivirus en uitsluitingen te beheren en verbindingen tussen uw netwerk en de cloud te valideren. Zie [Microsoft Defender voor eindpunt configureren met MPCmdRun.exe. ](manage-atp-post-migration-other-tools.md#configure-microsoft-defender-for-endpoint-with-microsoft-malware-protection-command-line-utility-mpcmdrunexe) |

## <a name="see-also"></a>Zie ook

- [Actie ondernemen voor fout-positieven/-negatieven in Microsoft Defender voor Eindpunt](defender-endpoint-false-positives-negatives.md)
