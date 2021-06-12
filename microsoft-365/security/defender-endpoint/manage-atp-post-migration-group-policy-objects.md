---
title: Microsoft Defender voor eindpunt beheren met groepsbeleidsobjecten
description: Meer informatie over het beheren van Microsoft Defender voor Eindpunt met groepsbeleidsobjecten
keywords: post-migration, manage, operations, maintenance, utilization, PowerShell, Microsoft Defender for Endpoint, edr
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
ms.openlocfilehash: ce204c1a90e57a651cf9c97974a8b35d405878cc
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908290"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Microsoft Defender voor eindpunt beheren met groepsbeleidsobjecten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> We raden u [aan Microsoft Endpoint Manager](/mem) voor het beheren van de beveiligingsfuncties voor bedreigingen van uw organisatie voor apparaten (ook wel eindpunten genoemd). Endpoint Manager bevat [Microsoft Intune](/mem/intune/fundamentals/what-is-intune) en [Microsoft Endpoint Configuration Manager.](/mem/configmgr/core/understand/introduction) **[Meer informatie over Endpoint Manager.](/mem/endpoint-manager-overview)** 

U kunt groepsbeleidsobjecten in Azure Active Directory Domain Services gebruiken om bepaalde instellingen in Microsoft Defender voor Eindpunt te beheren.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Microsoft Defender voor eindpunt configureren met groepsbeleidsobjecten

In de volgende tabel ziet u verschillende taken die u kunt uitvoeren om Microsoft Defender voor Eindpunt te configureren met groepsbeleidsobjecten.

|Taak  |Informatiebronnen  |
|---------|---------|
|**Instellingen voor gebruikers- en computerobjecten beheren** <br/><br/>*Pas ingebouwde groepsbeleidsobjecten aan of maak aangepaste groepsbeleidsobjecten en organisatie-eenheden die aan uw organisatiebehoeften voldoen.*     |[Groepsbeleid beheren in een Azure Active Directory domein beheerd domein van Domain Services](/azure/active-directory-domain-services/manage-group-policy)   |
|**Microsoft Defender Antivirus** <br/><br/>*Antivirusfuncties configureren & mogelijkheden, zoals beleidsinstellingen, uitsluitingen, herstel en geplande scans op de apparaten van uw organisatie (ook wel eindpunten genoemd).*   |[Groepsbeleidsinstellingen gebruiken voor het configureren en beheren van Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Groepsbeleid gebruiken om beveiliging via de cloud in te stellen](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**De regels voor de beperking van de attack surface van uw organisatie beheren** <br/><br/>*Pas de regels voor de beperking van uw aanvalsoppervlak aan door bestanden & mappen uit te sluiten of door aangepaste tekst toe te voegen aan meldingen die worden weergegeven op apparaten van gebruikers.* |[Surface Reduction-regels voor aanvallen aanpassen met groepsbeleidsobjecten](/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Beveiligingsinstellingen voor misbruik beheren**<br/><br/>*U kunt uw beveiligingsinstellingen voor exploits aanpassen, een configuratiebestand importeren en vervolgens Groepsbeleid gebruiken om dat configuratiebestand te implementeren.*  |[Beveiligingsinstellingen voor exploits aanpassen](/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Configuraties voor misbruikbeveiliging importeren, exporteren en implementeren](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Groepsbeleid gebruiken om de configuratie te distribueren](/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Netwerkbeveiliging inschakelen** om te voorkomen dat werknemers apps gebruiken die schadelijke inhoud op internet bevatten <br/><br/>*Het is raadzaam eerst [de auditmodus](/microsoft-365/security/defender-endpoint/evaluate-network-protection) te gebruiken voor netwerkbeveiliging in een testomgeving om te zien welke apps worden geblokkeerd voordat ze worden uitgerold.* |[Netwerkbeveiliging in- en uit te zetten met groepsbeleid](/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Beheerde maptoegang configureren om** te beschermen tegen ransomware <br/><br/>*[Gecontroleerde maptoegang](/microsoft-365/security/defender-endpoint/controlled-folders) wordt ook wel antiransomwarebeveiliging genoemd.*  |[Gecontroleerde maptoegang inschakelen met groepsbeleid](/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Configureer Microsoft Defender SmartScreen** te beschermen tegen schadelijke sites en bestanden op internet.  |[Instellingen Microsoft Defender SmartScreen groepsbeleid en MDM (Mobile Device Management) configureren met groepsbeleid](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Versleuteling en BitLocker** configureren om gegevens te beveiligen op de apparaten van uw organisatie met Windows |[BitLocker Groepsbeleidsinstellingen](/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Microsoft Defender Credential Guard configureren om** te beschermen tegen referentiesdiefstalaanvallen |[Groepen Windows Defender Credential Guard groepsbeleid inschakelen](/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Uw Microsoft Defender-beveiligingscentrum

Als u dit nog niet hebt gedaan, configureert u uw Microsoft 365 Defender-portal om waarschuwingen weer te geven, functies voor bedreigingsbeveiliging te configureren en gedetailleerde informatie weer te geven over de algehele beveiligingsstatus van uw organisatie. Zie [Microsoft Defender-beveiligingscentrum](microsoft-defender-security-center.md). U kunt ook configureren of en welke functies eindgebruikers kunnen zien in de Microsoft 365 Defender-portal.

- [Overzicht van de Microsoft Defender-beveiligingscentrum](/microsoft-365/security/defender-endpoint/use)

- [Eindpuntbeveiliging: Microsoft Defender-beveiligingscentrum](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Volgende stappen

- [Een overzicht van Threat and Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Ga naar het Microsoft Defender-beveiligingscentrum dashboard voor beveiligingsbewerkingen](/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Microsoft Defender voor eindpunt beheren met Intune](manage-atp-post-migration-intune.md)
