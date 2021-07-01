---
title: Microsoft Defender voor eindpunt beheren met Intune
description: Meer informatie over het beheren van Microsoft Defender voor Eindpunt met Intune
keywords: post-migration, manage, operations, maintenance, utilization, intune, Microsoft Defender for Endpoint, edr
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
ms.openlocfilehash: 5ca16e125b1eb8377c3a591d039eb7da65b873fb
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229093"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Microsoft Defender voor eindpunt beheren met Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefversie.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Het is raadzaam [Microsoft Endpoint Manager](/mem)te gebruiken , waaronder Microsoft Intune (Intune) voor het beheren van de beveiligingsfuncties voor bedreigingen van uw organisatie voor apparaten (ook wel eindpunten genoemd). [Meer informatie over Endpoint Manager.](/mem/endpoint-manager-overview)

In dit artikel wordt beschreven hoe u de instellingen van Microsoft Defender voor eindpunten kunt vinden in Intune en worden verschillende taken beschreven die u kunt uitvoeren.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Uw Instellingen voor Microsoft Defender voor eindpunten zoeken in Intune

> [!IMPORTANT]
> U moet een globale beheerder of servicebeheerder in Intune zijn om de instellingen te configureren die in dit artikel worden beschreven. Zie Typen **[beheerders (Intune) voor meer informatie.](/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Ga naar de Azure-portal [https://portal.azure.com](https://portal.azure.com) () en meld u aan.

2. Kies **onder Azure Services** de optie **Intune**.

3. Kies in het navigatiedeelvenster aan de **linkerkant Apparaatconfiguratie** en kies vervolgens onder **Beheren** de optie **Profielen.**

4. Selecteer een bestaand profiel of maak een nieuw profiel.

> [!TIP]
> Hulp nodig? Zie **[Microsoft Defender voor eindpunt gebruiken met Intune](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**.  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Microsoft Defender voor eindpunt configureren met Intune

De volgende tabel bevat verschillende taken die u kunt uitvoeren om Microsoft Defender voor Eindpunt te configureren met Intune. U hoeft niet alles in één keer te configureren. kies een taak, lees de bijbehorende resources en ga vervolgens verder.

|Taak  |Informatiebronnen  |
|---------|---------|
|**De apparaten van uw organisatie beheren met Intune om** deze apparaten en gegevens op deze apparaten te beveiligen     |[Apparaten beveiligen met Microsoft Intune](/mem/intune/protect/device-protect)         |
|**Microsoft Defender voor eindpunt integreren met Intune** als een mobile threat defense-oplossing <br/>*(voor Android-apparaten en apparaten met Windows 10 of hoger)*   |[Naleving afdwingen voor Microsoft Defender voor Eindpunt met Voorwaardelijke toegang in Intune](/mem/intune/protect/advanced-threat-protection)         |
|**Voorwaardelijke toegang gebruiken** om de apparaten en apps te beheren die verbinding kunnen maken met uw e-mail en bedrijfsbronnen |[Voorwaardelijke toegang configureren in Microsoft Defender voor eindpunt](/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Instellingen Microsoft Defender Antivirus configureren** met de beleidsconfiguratieserviceprovider [(CSP-beleid)](/windows/client-management/mdm/policy-configuration-service-provider) |[Apparaatbeperkingen: Microsoft Defender Antivirus](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[Beleids-CSP - Microsoft Defender voor Eindpunt](/windows/client-management/mdm/policy-csp-defender)  | 
|**Geef zo nodig uitsluitingen op voor Microsoft Defender Antivirus** <br/><br/>*Over het algemeen hoeft u geen uitsluitingen toe te passen. Microsoft Defender Antivirus bevat een aantal automatische uitsluitingen op basis van bekende gedragingen van het besturingssysteem en gebruikelijke beheerbestanden, zoals die worden gebruikt in ondernemingsbeheer, databasebeheer en andere ondernemingsscenario's.* |[Aanbevelingen voor virusscans voor Enterprise-computers waarop momenteel ondersteunde versies van Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Apparaatbeperkingen: Microsoft Defender Antivirus uitsluitingen voor Windows 10 apparaten](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Microsoft Defender Antivirus uitsluitingen configureren op Windows Server 2016 of 2019](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**De surface reduction-regels voor aanvallen configureren** om te richten op softwaregedrag dat vaak wordt misbruikt door aanvallers<br/><br/>*Configureer eerst de surface reduction-regels voor aanvallen in [de auditmodus](/microsoft-365/security/defender-endpoint/audit-windows-defender) (minimaal één week en maximaal twee maanden). U kunt de status controleren Power BI ( haal onze [sjabloon](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)) in en stel deze regels in op de actieve modus wanneer u klaar bent.* |[Auditmodus in Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Endpoint protection: Attack Surface Reduction](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Meer informatie over regels voor het verlagen van de surface-aanval](/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Tech Community-blogbericht: Demystifying attack surface reduction rules - Part 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Uw netwerkfilter configureren** om uitgaande verbindingen te blokkeren van een app naar IP-adressen of domeinen met een lage reputatie  <br/><br/>*Netwerkfilters worden ook wel [netwerkbeveiliging genoemd.](/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Zorg ervoor dat Windows 10 apparaten de nieuwste updates voor [antimalwareplatforms hebben](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) geïnstalleerd.*|[Endpoint protection: Network filtering](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Netwerkbeveiligingsgebeurtenissen bekijken in Windows Event Viewer](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Beheerde maptoegang configureren om** te beschermen tegen ransomware <br/><br/>*[Gecontroleerde maptoegang](/microsoft-365/security/defender-endpoint/controlled-folders) wordt ook wel antiransomwarebeveiliging genoemd.*  |[Endpoint protection: Gecontroleerde maptoegang](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Gecontroleerde maptoegang inschakelen in Intune](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Exploitbeveiliging configureren** om de apparaten van uw organisatie te beschermen tegen malware die exploits gebruikt om andere apparaten te verspreiden en te infecteren <br/><br/> *[Exploitbeveiliging](/microsoft-365/security/defender-endpoint/exploit-protection) wordt ook wel Exploit Guard genoemd.* |[Eindpuntbeveiliging: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Exploitbeveiliging inschakelen in Intune](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Configureer Microsoft Defender SmartScreen** te beschermen tegen schadelijke sites en bestanden op internet. <br/><br/> *Microsoft Edge moet worden geïnstalleerd op de apparaten van uw organisatie. Voor beveiliging in google Chrome- en FireFox-browsers configureert u bescherming tegen misbruik.*  |[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Apparaatbeperkingen: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Beleidsinstellingen voor het beheren van SmartScreen in Intune](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Microsoft Defender Firewall configureren** om ongeautoriseerd netwerkverkeer te blokkeren dat in of uit de apparaten van uw organisatie stroomt  |[Endpoint protection: Microsoft Defender Firewall](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Microsoft Defender Firewall met geavanceerde beveiliging](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Versleuteling en BitLocker configureren** om informatie te beveiligen op de apparaten van uw organisatie met Windows |[Eindpuntbeveiliging: Windows versleuteling](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker voor Windows 10 apparaten](/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Microsoft Defender Credential Guard configureren om** te beschermen tegen referentiesdiefstalaanvallen |Voor Windows 10, Windows Server 2016 en Windows Server 2019, zie [Endpoint protection: Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>Voor Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 en Windows Server 2012 R2, zie [Mitigating Pass-the-Hash (PtH) Attacks and Other Credential Theft, Versions 1 and 2](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**Microsoft Defender Application Control configureren** om te kiezen of u apps wilt controleren of vertrouwen op de apparaten van uw organisatie <br/><br/>*Microsoft Defender Application Control wordt ook wel [AppLocker genoemd.](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)*|[Microsoft Defender Application Control-beleid implementeren met behulp van Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Endpoint protection: Microsoft Defender Application Control](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](/windows/client-management/mdm/applocker-csp)|
|**Apparaatbesturing en toegang tot USB-randapparatuur configureren** om te voorkomen dat bedreigingen in niet-geautoriseerde randapparatuur uw apparaten in gevaar brengen |[USB-apparaten en andere verwisselbare media beheren met Microsoft Defender voor Eindpunt en Intune](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Uw Microsoft Defender-beveiligingscentrum

Als u dit nog niet hebt gedaan, configureert u uw Microsoft 365 Defender-portal om waarschuwingen weer te geven, functies voor bedreigingsbeveiliging te configureren en gedetailleerde informatie weer te geven over de algehele beveiligingsstatus van uw organisatie. Zie [Microsoft Defender-beveiligingscentrum](microsoft-defender-security-center.md). U kunt ook configureren of en welke functies eindgebruikers kunnen zien in de Microsoft 365 Defender portal.

- [Overzicht van de Microsoft Defender-beveiligingscentrum](/microsoft-365/security/defender-endpoint/use)

- [Eindpuntbeveiliging: Microsoft Defender-beveiligingscentrum](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Volgende stappen

- [Een overzicht van Threat and Vulnerability Management](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Ga naar het Microsoft Defender-beveiligingscentrum dashboard voor beveiligingsbewerkingen](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
