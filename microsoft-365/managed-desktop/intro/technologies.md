---
title: Technologieën in Microsoft Managed Desktop
description: In dit artikel worden de technologieën en apps beschreven die worden gebruikt in het beheerde bureaublad van Microsoft.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 70e4eb442f9c0e52dbf234280205dd908c135b8d
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233106"
---
# <a name="microsoft-managed-desktop-technologies"></a>Technologieën in Microsoft Managed Desktop

In dit artikel worden de technologieën en apps beschreven die worden gebruikt in het beheerde bureaublad van Microsoft.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licenties zijn vereist voor alle gebruikers van het beheerde bureaublad van Microsoft. Zie Vereisten voor [Microsoft Managed Desktop](../get-ready/prerequisites.md)voor meer informatie over licentievereisten voor de service.

Dit artikel bevat een overzicht van de onderdelen die zijn opgenomen in de vereiste Enterprise-licenties, met een beschrijving van hoe de service elk onderdeel gebruikt met Beheerde bureaublad-apparaten van Microsoft. Specifieke rollen en verantwoordelijkheden voor elk gebied worden in de documentatie van Microsoft Managed Desktop beschreven. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 of E5
 |
 --- | ---
Microsoft 365-apps voor ondernemingen (64-bits) | Deze Office-toepassingen worden geleverd met het apparaat: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, OneNote.<br><br>De 64-bits volledige versies van Microsoft Project en Microsoft Visio zijn niet inbegrepen. Aangezien de installatie van deze toepassingen echter afhankelijk is van de Microsoft 365-apps voor enterprise-installatie, heeft Microsoft Managed Desktop standaard Microsoft Intune-implementaties en beveiligingsgroepen gemaakt die u vervolgens kunt gebruiken om deze toepassingen te implementeren voor gebruikers met een licentie. Zie Microsoft Project of Microsoft Visio installeren op beheerde [Desktop-apparaten van Microsoft voor meer informatie.](../get-started/project-visio.md)
OneDrive |Een aanmelding bij Azure Active Directory is ingeschakeld voor gebruikers wanneer ze zich de eerste keer aanmelden bij OneDrive.<br><br>De mappen Bekende mapomleiding voor 'Bureaublad', 'Document' en 'Afbeeldingen' zijn opgenomen. ingeschakeld en geconfigureerd door het beheerde bureaublad van Microsoft.
Store-apps |    Microsoft Sway en Power BI worden niet bij het apparaat geleverd. Deze apps kunnen worden gedownload in de Microsoft Store.
Win32-toepassingen |    Teams wordt niet bij het apparaat geleverd, maar wordt geleverd door Microsoft voor beheerde desktopapparaten van Microsoft. Azure Information Protection Client wordt niet samen met het apparaat verzonden, maar u kunt het wel laten inpakt voor implementatie.
Webtoepassingen |  Yammer, Office in een browser, Delve, Flow, StaffHub, PowerApps en Planner worden niet bij het apparaat geleverd. Gebruikers hebben via een browser toegang tot de webversie van deze toepassingen.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 of E3 met Microsoft Defender voor eindpunt
Het is raadzaam dat uw IT-beheerders de volgende instellingen configureren. Deze instellingen worden niet opgenomen of beheerd als onderdeel van het beheerde bureaublad van Microsoft.

 |
 --- | ---
Windows Hello voor Bedrijven | Implementeert Windows Hello voor Bedrijven om wachtwoorden te vervangen door sterke tweestapsverificatie voor beheerde desktopapparaten van Microsoft. Zie Windows Hello voor Bedrijven voor [meer informatie.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Application Virtualization | U kunt Application Virtualization-pakketten (App-V) implementeren met de Intune Win32-app management-client. Zie Application Virtualization voor [meer informatie.](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference)
Microsoft 365 preventie van gegevensverlies | Implementeert Microsoft 365 voor preventie van gegevensverlies om te controleren welke acties worden uitgevoerd op items die volgens u gevoelig zijn en om te voorkomen dat deze items onbedoeld worden gedeeld. Zie Microsoft [365](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about)voor meer informatie over preventie van gegevensverlies.


Functies inbegrepen en beheerd als onderdeel van Microsoft Managed Desktop:

 |
 --- | ---
BitLocker-stationversleuteling | BitLocker-stationsversleuteling wordt gebruikt om alle systeemstations te versleutelen. Zie [BitLocker-schijfversleuteling voor meer informatie.](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Beschermt de integriteit van het systeem bij het opstarten en controleert of de systeemintegriteit echt behouden blijft. Zie Windows Defender System Guard voor [meer informatie.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard gebruikt beveiliging op basis van virtualisatie om geheimen te isoleren, zodat alleen bevoorrechte systeemsoftware ze kan openen. Zie Windows Defender System Guard voor [meer informatie.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender voor eindpunt - Detectie en reactie van eindpunt | Microsoft Managed Desktop Security Operations reageert op waarschuwingen en onderneemt actie om bedreigingen te herstellen met behulp van eindpuntdetectie en -reactie. Zie Microsoft Defender for Endpoint - Detectie en reactie [van eindpunt voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender voor Eindpunt - Bedreigingsexperts | Microsoft Managed Desktop integreert met inzichten en gegevens van bedreigingsexperts via specifieke meldingen over aanvallen. U moet aanvullende toestemming geven voordat deze service wordt ingeschakeld. Zie Microsoft [Defender for Endpoint - Threat Experts voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender for Endpoint - Bedreigings- en beveiligingsprobleembeheer | Vereist voor toekomstig gebruik in het Microsoft Managed Desktop-serviceplan. Zie Microsoft [Defender for Endpoint - Bedreigings- en beveiligingsprobleembeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)voor meer informatie.
Microsoft Defender voor eindpunt - Surface-aanvalsbeperking | Een risico op aanvallen is gericht op riskant softwaregedrag dat vaak door kwaadwillende gebruikers wordt misbruik. Zie Microsoft [Defender for Endpoint - Attack Surface Reduction voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender for Endpoint - Exploit Protection | Beschermt tegen malware die misbruik maakt om apparaten te infecteren en te verspreiden door automatisch technieken voor risicobeperking van misbruik toe te passen op processen en apps van het besturingssysteem. Zie Microsoft [Defender for Endpoint - Exploit Protection voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender voor Eindpunt - Netwerkbeveiliging | Netwerkbeveiliging breidt het bereik van Microsoft Defender SmartScreen uit om al het uitgaande HTTP- en HTTPS-verkeer te blokkeren dat verbinding probeert te maken met bronnen met een slechte reputatie. Zie Microsoft [Defender for Endpoint - Network Protection voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Microsoft Defender Tamper Protection | Windows Tamper Protection wordt gebruikt om te voorkomen dat beveiligingsinstellingen, zoals de beveiliging tegen virussen, worden gewijzigd. Zie Microsoft Defender Tamper Protection voor meer [informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Microsoft Defender Antivirus Behavior-based, heuristic, and real-time antivirus protection | Altijd op zoek naar bestands- en procesrisico's die mogelijk niet als malware worden gedetecteerd. Zie Microsoft [Defender Antivirus Behavior-, heuristic en real-time antivirusbescherming voor]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)meer informatie.
Microsoft Defender Antivirus Cloud-delivered Protection | Biedt dynamische, directe, geautomatiseerde beveiliging tegen nieuwe en nieuwe bedreigingen. Zie Microsoft [Defender Antivirus Cloud-delivered Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)voor meer informatie.
Microsoft Defender "Blok op het eerste gezicht" | Biedt detectie en blokkering van nieuwe malware wanneer Windows een verdacht of onbekend bestand detecteert. Zie Microsoft Defender Block op het eerste gezicht [voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Potentieel ongewenste toepassingen van Microsoft Defender AV | Mogelijk ongewenste toepassingen worden gebruikt om apps te blokkeren waardoor uw computer traag wordt, onverwachte advertenties kan weergeven of in het slechtste geval andere software installeert die mogelijk onverwacht of ongewenst is. Zie Microsoft Defender AV potentieel [ongewenste toepassingen voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender Firewall met Geavanceerde beveiliging | Met Windows Defender Firewall in twee richting wordt er gefilterd op netwerkverkeer in twee richting voor een apparaat. Met Windows Defender Firewall wordt geblokkeerd dat ongeautoriseerd netwerkverkeer het lokale apparaat binnen of uit stroomt. Zie Windows Defender Firewall met [Advanced Security voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Gebruikersaccountbeheer | Gebruikersaccountbeheer schakelt over naar Beveiligd bureaublad als voor een taak of actie toegang van het beheerdersaccounttype is vereist. Aan microsoft Beheerd bureaublad-gebruikers wordt standaardgebruikerstoegang toegewezen bij de inschrijving. Zie [Gebruikersaccountbeheer voor meer informatie.](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    U kunt alle functies van Enterprise Mobility + Security E3 en Azure Active Directory Premium P2 gebruiken om MDM-apparaten te beheren.
Microsoft Cloud App Security |  U kunt deze optionele functie gebruiken met het beheerde bureaublad van Microsoft.
Azure Information Protection P2  | U kunt deze optionele functie gebruiken met het beheerde bureaublad van Microsoft.
