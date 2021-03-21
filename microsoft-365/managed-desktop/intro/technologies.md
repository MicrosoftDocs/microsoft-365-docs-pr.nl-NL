---
title: Technologieën in Microsoft Managed Desktop
description: In dit artikel worden de technologieën en apps vermeld die worden gebruikt in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920574"
---
# <a name="microsoft-managed-desktop-technologies"></a>Technologieën in Microsoft Managed Desktop

In dit artikel worden de technologieën en apps vermeld die worden gebruikt in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licenties zijn vereist voor alle gebruikers van Microsoft Managed Desktop. Zie Vereisten voor [Microsoft Managed Desktop](../get-ready/prerequisites.md)voor meer informatie over licentievereisten voor de service.

In dit artikel worden de onderdelen samengevat die zijn opgenomen in de vereiste Enterprise-licenties, met een beschrijving van hoe de service elk onderdeel gebruikt met Microsoft Managed Desktop-apparaten. Specifieke rollen en verantwoordelijkheden voor elk gebied worden beschreven in microsoft Managed Desktop-documentatie. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 of E5
 |
 --- | ---
Microsoft 365 Apps voor ondernemingen (64-bits) | Deze Office-toepassingen worden verzonden met het apparaat: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, OneNote.<br><br>De 64-bits volledige versies van Microsoft Project en Microsoft Visio zijn niet inbegrepen. Aangezien de installatie van deze toepassingen echter afhankelijk is van de installatie van Microsoft 365 Apps voor ondernemingen, heeft Microsoft Managed Desktop standaard Microsoft Intune-implementaties en beveiligingsgroepen gemaakt die u vervolgens kunt gebruiken om deze toepassingen te implementeren voor gelicentieerde gebruikers. Zie Microsoft Project of Microsoft Visio installeren op [Microsoft Managed Desktop-apparaten](../get-started/project-visio.md)voor meer informatie.
OneDrive |Azure Active Directory Single Sign On is ingeschakeld voor gebruikers wanneer ze zich voor het eerst aanmelden bij OneDrive.<br><br>Omleiding van bekende mappen voor 'Bureaublad', 'Document' en 'Afbeeldingen' is inbegrepen. ingeschakeld en geconfigureerd door Microsoft Managed Desktop.
Store-apps |    Microsoft Sway en Power BI worden niet geleverd met het apparaat. Deze apps kunnen worden gedownload vanuit de Microsoft Store.
Win32-toepassingen |    Teams wordt niet verzonden met het apparaat, maar is verpakt en geleverd door Microsoft voor Microsoft Managed Desktop-apparaten. Azure Information Protection Client wordt niet verzonden met het apparaat, maar u kunt het wel laten verpakken voor implementatie.
Webtoepassingen |  Yammer, Office in een browser, Delve, Flow, StaffHub, PowerApps en Planner worden niet geleverd met het apparaat. Gebruikers hebben toegang tot de webversie van deze toepassingen met een browser.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 of E3 met Microsoft Defender voor Eindpunt
Het is raadzaam dat uw IT-beheerders de volgende instellingen configureren. Deze instellingen worden niet opgenomen of beheerd als onderdeel van Microsoft Managed Desktop.

 |
 --- | ---
Windows Hello voor Bedrijven | U moet Windows Hello voor Bedrijven implementeren om wachtwoorden te vervangen door sterke tweestapsverificatie voor Microsoft Managed Desktop-apparaten. Zie Windows Hello voor Bedrijven voor [meer informatie.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Toepassingsvirtualisatie | U kunt App-V-pakketten (Application Virtualization) implementeren met de App-beheerclient van Intune Win32. Zie Toepassingsvirtualisatie [voor meer informatie.](/windows/application-management/app-v/appv-technical-reference)
Preventie van gegevensverlies in Microsoft 365 | U moet microsoft 365 preventie van gegevensverlies implementeren om de acties te controleren die worden uitgevoerd op items die u hebt vastgesteld dat ze gevoelig zijn en om te voorkomen dat deze items onbedoeld worden gedeeld. Zie Preventie van [gegevensverlies in Microsoft 365 voor meer informatie.](../../compliance/endpoint-dlp-learn-about.md)


Functies die zijn opgenomen en beheerd als onderdeel van Microsoft Managed Desktop:

 |
 --- | ---
BitLocker-stationversleuteling | BitLocker-stationsversleuteling wordt gebruikt om alle systeemstations te versleutelen. Zie [BitLocker-stationversleuteling](/windows/security/information-protection/bitlocker/bitlocker-overview)voor meer informatie.
Windows Defender System Guard | Beschermt de integriteit van het systeem bij het opstarten en valideert dat de systeemintegriteit echt is gehandhaafd. Zie Windows [Defender System Guard voor meer informatie.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard gebruikt virtualisatiebeveiliging om geheimen te isoleren, zodat alleen bevoorrechte systeemsoftware ze kan openen. Zie Windows [Defender System Guard voor meer informatie.]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender voor eindpunt - Endpoint Detection and Response | Microsoft Managed Desktop Security Operations reageert op waarschuwingen en onderneemt actie om bedreigingen te corrigeren met Endpoint Detection and Response. Zie Microsoft [Defender for Endpoint - Endpoint Detection and Response voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender voor eindpunt - Bedreigingsexperts | Microsoft Managed Desktop is geïntegreerd met inzichten en gegevens van Threat Experts via gerichte aanvalsmeldingen. U moet aanvullende toestemming geven voordat deze service is ingeschakeld. Zie Microsoft [Defender for Endpoint - Threat Experts voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender voor Eindpunt - Bedreigings- en kwetsbaarheidsbeheer | Vereist voor toekomstig gebruik in het Microsoft Managed Desktop-serviceplan. Zie Microsoft [Defender for Endpoint - Threat and Vulnerability Management voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender for Endpoint - Attack Surface Reduction | Attack surface reduction targets risky software behaviors that are often abused by attackers. Zie Microsoft [Defender for Endpoint - Attack Surface Reduction voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender for Endpoint - Exploit Protection | Beschermt tegen malware die exploits gebruikt om apparaten te infecteren en te verspreiden door gebruiksbeperkingstechnieken automatisch toe te passen op zowel besturingssysteemprocessen als apps. Zie Microsoft [Defender for Endpoint - Exploit Protection voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender voor Eindpunt - Netwerkbeveiliging | Netwerkbeveiliging breidt het bereik van Microsoft Defender SmartScreen uit om al het uitgaande HTTP- en HTTPS-verkeer te blokkeren dat probeert verbinding te maken met bronnen met een lage reputatie. Zie [Microsoft Defender for Endpoint - Network Protection voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Microsoft Defender Tamper Protection | Windows Tamper Protection wordt gebruikt om te voorkomen dat beveiligingsinstellingen, zoals antivirusbeveiliging, worden gewijzigd. Zie Microsoft Defender Tamper Protection voor meer [informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Microsoft Defender Antivirus Behavior-based, heuristic, and real-time antivirus protection | Altijd bezig met het scannen van bestands- en procesrisico's die mogelijk niet als malware worden gedetecteerd. Zie Microsoft [Defender Antivirus Behavior-based, heuristic and real-time antivirus protection]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)voor meer informatie.
Microsoft Defender Antivirus Cloud-geleverde beveiliging | Biedt dynamische, geautomatiseerde bescherming tegen nieuwe en nieuwe bedreigingen. Zie Microsoft [Defender Antivirus Cloud-delivered Protection](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)voor meer informatie.
Microsoft Defender "Blok op het eerste gezicht" | Biedt detectie en blokkering van nieuwe malware wanneer Windows een verdacht of onbekend bestand detecteert. Zie Microsoft Defender Block op het [eerste gezicht voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV Potentieel ongewenste toepassingen | Potentieel ongewenste toepassingen worden gebruikt om apps te blokkeren waardoor uw computer traag kan worden uitgevoerd, onverwachte advertenties kan weergeven of in het slechtste geval andere software kan installeren die onverwacht of ongewenst kan zijn. Zie Microsoft [Defender AV Potentieel ongewenste toepassingen voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender Firewall met geavanceerde beveiliging | Op host gebaseerde, tweeweg netwerkverkeersfilters voor een apparaat, blokkeert Windows Defender Firewall ongeautoriseerd netwerkverkeer dat in of uit het lokale apparaat stroomt. Zie Windows [Defender Firewall with Advanced Security (Windows Defender Firewall with Advanced Security) voor meer informatie.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Gebruikersaccountbeheer | Gebruikersaccountbeheer schakelt over naar het beveiligde bureaublad wanneer voor een taak of actie de beheerdersaccounttypetoegang is vereist. Microsoft Managed Desktop-gebruikers krijgen standaardgebruikerstoegang toegewezen bij inschrijving. Zie Gebruikersaccountbeheer voor [meer informatie.](/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    U kunt alle functies van Enterprise Mobility + Security E3 en Azure Active Directory Premium P2 gebruiken om MDM-apparaten te beheren.
Microsoft Cloud App Security |  U kunt deze optionele functie gebruiken met Microsoft Managed Desktop.
Azure Information Protection P2  | U kunt deze optionele functie gebruiken met Microsoft Managed Desktop.