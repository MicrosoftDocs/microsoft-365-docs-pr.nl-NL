---
title: Microsoft Defender voor eindpunt beheren met groepsbeleidsobjecten
description: Meer informatie over het beheren van Microsoft Defender voor Eindpunt met groepsbeleidsobjecten
keywords: post-migration, manage, operations, maintenance, utilization, PowerShell, windows defender advanced threat protection, atp, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: 6d10bd932d9414f1460076d3fe7ca8dbed8041a6
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185651"
---
# <a name="manage-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Microsoft Defender voor eindpunt beheren met groepsbeleidsobjecten

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


> [!NOTE]
> We raden u [aan Microsoft Endpoint Manager](https://docs.microsoft.com/mem) te gebruiken om de beveiligingsfuncties voor bedreigingen van uw organisatie te beheren voor apparaten (ook wel eindpunten genoemd). Endpoint Manager bevat [Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune) en [Microsoft Endpoint Configuration Manager.](https://docs.microsoft.com/mem/configmgr/core/understand/introduction) **[Meer informatie over Endpoint Manager.](https://docs.microsoft.com/mem/endpoint-manager-overview)** 

U kunt groepsbeleidsobjecten in Azure Active Directory Domain Services gebruiken om bepaalde instellingen in Microsoft Defender voor Eindpunt te beheren.

## <a name="configure-microsoft-defender-for-endpoint-with-group-policy-objects"></a>Microsoft Defender voor eindpunt configureren met groepsbeleidsobjecten

In de volgende tabel ziet u verschillende taken die u kunt uitvoeren om Microsoft Defender voor Eindpunt te configureren met groepsbeleidsobjecten.

|Taak  |Informatiebronnen  |
|---------|---------|
|**Instellingen voor gebruikers- en computerobjecten beheren** <br/><br/>*Pas ingebouwde groepsbeleidsobjecten aan of maak aangepaste groepsbeleidsobjecten en organisatie-eenheden die aan uw organisatiebehoeften voldoen.*     |[Groepsbeleid beheren in een beheerd domein van Azure Active Directory Domain Services](https://docs.microsoft.com/azure/active-directory-domain-services/manage-group-policy)   |
|**Microsoft Defender Antivirus configureren** <br/><br/>*Antivirusfuncties configureren & mogelijkheden, zoals beleidsinstellingen, uitsluitingen, herstel en geplande scans op de apparaten van uw organisatie (ook wel eindpunten genoemd).*   |[Groepsbeleidsinstellingen gebruiken om Microsoft Defender Antivirus te configureren en te beheren](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/use-group-policy-microsoft-defender-antivirus) <br/><br/>[Groepsbeleid gebruiken om beveiliging via de cloud in te stellen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus#use-group-policy-to-enable-cloud-delivered-protection)      |
|**De regels voor de beperking van de attack surface van uw organisatie beheren** <br/><br/>*Pas de regels voor de beperking van uw aanvalsoppervlak aan door bestanden & mappen uit te sluiten of door aangepaste tekst toe te voegen aan meldingen die worden weergegeven op apparaten van gebruikers.* |[Surface Reduction-regels voor aanvallen aanpassen met groepsbeleidsobjecten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-attack-surface-reduction#use-group-policy-to-exclude-files-and-folders) |
|**Beveiligingsinstellingen voor misbruik beheren**<br/><br/>*U kunt uw beveiligingsinstellingen voor exploits aanpassen, een configuratiebestand importeren en vervolgens Groepsbeleid gebruiken om dat configuratiebestand te implementeren.*  |[Beveiligingsinstellingen voor exploits aanpassen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/customize-exploit-protection) <br/><br/>[Configuraties voor exploitbeveiliging importeren, exporteren en implementeren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml)<br/><br/>[Groepsbeleid gebruiken om de configuratie te distribueren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/import-export-exploit-protection-emet-xml#use-group-policy-to-distribute-the-configuration)  |
|**Netwerkbeveiliging inschakelen** om te voorkomen dat werknemers apps gebruiken die schadelijke inhoud op internet bevatten <br/><br/>*Het is raadzaam eerst [de auditmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection) te gebruiken voor netwerkbeveiliging in een testomgeving om te zien welke apps worden geblokkeerd voordat ze worden uitgerold.* |[Netwerkbeveiliging in- en uit te zetten met groepsbeleid](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-network-protection#group-policy)  |
|**Beheerde maptoegang configureren om** te beschermen tegen ransomware <br/><br/>*[Gecontroleerde maptoegang](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) wordt ook wel antiransomwarebeveiliging genoemd.*  |[Gecontroleerde maptoegang inschakelen met groepsbeleid](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#group-policy) |
|**Configureer Microsoft Defender SmartScreen** om te beschermen tegen schadelijke sites en bestanden op internet.  |[Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy configureren Microsoft Defender SmartScreen Group Policy and mobile device management (MDM) settings using Group Policy](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#group-policy-settings)  |
|**Versleuteling en BitLocker configureren** om informatie te beveiligen op de apparaten van uw organisatie met Windows |[BitLocker-groepsbeleidsinstellingen](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-group-policy-settings) |
|**Microsoft Defender Credential Guard configureren om** te beschermen tegen referentiesdiefstalaanvallen |[Windows Defender Credential Guard inschakelen met groepsbeleid](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard-manage#enable-windows-defender-credential-guard-by-using-group-policy) |

## <a name="configure-your-microsoft-defender-security-center"></a>Uw Microsoft Defender-beveiligingscentrum configureren

Als u dit nog niet hebt gedaan, configureert u het **Microsoft Defender-beveiligingscentrum** () om waarschuwingen weer te geven, functies voor bedreigingsbeveiliging te configureren en gedetailleerde informatie weer te geven over de algehele beveiligingsstatus van uw [https://securitycenter.windows.com](https://securitycenter.windows.com) organisatie. 

U kunt ook configureren of en welke functies eindgebruikers kunnen zien in het Microsoft Defender-beveiligingscentrum.

- [Overzicht van het Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpoint protection: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Volgende stappen

- [Een overzicht krijgen van bedreigings- en kwetsbaarheidsbeheer](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Ga naar het dashboard beveiligingsbewerkingen van het Microsoft Defender-beveiligingscentrum](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)

- [Microsoft Defender voor eindpunt beheren met Intune](manage-atp-post-migration-intune.md)
