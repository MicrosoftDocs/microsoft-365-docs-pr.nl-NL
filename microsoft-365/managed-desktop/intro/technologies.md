---
title: Technologieën in Microsoft Managed Desktop
description: In dit artikel vindt u een overzicht van de technologieën en apps die in Microsoft Managed Desktop.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8a2a3f83995bf4248b2cb72a848a1def83ae9c50
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203266"
---
# <a name="microsoft-managed-desktop-technologies"></a>Technologieën in Microsoft Managed Desktop

In dit artikel vindt u een overzicht van de technologieën en apps die in Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise is vereist voor alle Microsoft Managed Desktop gebruikers. Zie Vereisten voor Microsoft Managed Desktop voor meer informatie over [licentievereisten voor de service.](../get-ready/prerequisites.md)

In dit artikel worden de onderdelen samengevat die zijn opgenomen in de vereiste Enterprise-licenties, met een beschrijving van hoe de service elk onderdeel gebruikt met Microsoft Managed Desktop apparaten. Specifieke rollen en verantwoordelijkheden voor elk gebied worden in de Microsoft Managed Desktop beschreven. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 of E5
| Product |Informatie |
--- |--- 
Microsoft 365-apps voor ondernemingen (64-bits) | Deze Office worden verzonden met het apparaat: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, OneNote.<br><br>De 64-bits volledige versies van Microsoft Project en Microsoft-Visio zijn niet inbegrepen. Aangezien de installatie van deze toepassingen echter afhankelijk is van de Microsoft 365-apps voor ondernemingen-installatie, heeft Microsoft Managed Desktop standaard-Microsoft Intune-implementaties en beveiligingsgroepen gemaakt die u vervolgens kunt gebruiken om deze toepassingen te implementeren voor gelicentieerde gebruikers. Zie Installatie van Microsoft Project of Microsoft Visio op Microsoft Managed Desktop [apparaten voor meer informatie.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Enkel aanmelden is ingeschakeld voor gebruikers wanneer ze zich voor het eerst aanmelden bij OneDrive.<br><br>Omleiding van bekende mappen voor 'Bureaublad', 'Document' en 'Afbeeldingen' is inbegrepen. ingeschakeld en geconfigureerd per Microsoft Managed Desktop.
Store-apps |    Microsoft Sway en Power BI worden niet verzonden met het apparaat. Deze apps zijn beschikbaar om te downloaden van Microsoft Store.
Win32-toepassingen |    Teams wordt niet verzonden met het apparaat, maar is verpakt en geleverd door Microsoft voor Microsoft Managed Desktop apparaten. Azure Information Protection Client wordt niet verzonden met het apparaat, maar u kunt het wel laten verpakken voor implementatie.
Webtoepassingen |  Yammer, Office in een browser, Delve, Flow, StaffHub, PowerApps en Planner worden niet verzonden met het apparaat. Gebruikers hebben toegang tot de webversie van deze toepassingen met een browser.



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 of E3 met Microsoft Defender voor Eindpunt
Het is raadzaam dat uw IT-beheerders de volgende instellingen configureren. Deze instellingen worden niet opgenomen of beheerd als onderdeel van Microsoft Managed Desktop.

Product  |Informatie
--- | ---
Windows Hello voor Bedrijven | U moet Windows Hello voor Bedrijven implementeren om wachtwoorden te vervangen door sterke tweestapsverificatie voor Microsoft Managed Desktop apparaten. Zie Windows Hello [voor Bedrijven voor meer informatie.](/windows/security/identity-protection/hello-for-business/hello-identity-verification)
Toepassingsvirtualisatie | U kunt App-V-pakketten (Application Virtualization) implementeren met de App-beheerclient van Intune Win32. Zie Toepassingsvirtualisatie [voor meer informatie.](/windows/application-management/app-v/appv-technical-reference)
Microsoft 365 preventie van gegevensverlies | U moet Microsoft 365 preventie van gegevensverlies implementeren om de acties te controleren die worden uitgevoerd op items die u hebt vastgesteld dat ze gevoelig zijn en om te voorkomen dat deze items onbedoeld worden gedeeld. Zie voor meer informatie [Microsoft 365 preventie van gegevensverlies.](../../compliance/endpoint-dlp-learn-about.md)


Functies opgenomen en beheerd als onderdeel van Microsoft Managed Desktop:

Product |Informatie
--- |--- 
BitLocker-stationversleuteling | BitLocker-stationsversleuteling wordt gebruikt om alle systeemstations te versleutelen. Zie [BitLocker-stationversleuteling](/windows/security/information-protection/bitlocker/bitlocker-overview)voor meer informatie.
Windows Defender Systeembeveiliger | Beschermt de integriteit van het systeem bij het opstarten en valideert dat de systeemintegriteit echt is gehandhaafd. Zie voor meer informatie [Windows Defender System Guard.](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Windows Defender Credential Guard | Windows Defender Credential Guard gebruikt beveiliging op basis van virtualisatie om geheimen te isoleren, zodat alleen bevoorrechte systeemsoftware er toegang toe heeft. Zie voor meer informatie [Windows Defender System Guard.](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows)
Microsoft Defender voor eindpunt - Endpoint Detection and Response | Microsoft Managed Desktop Beveiligingsbewerkingen reageert op waarschuwingen en onderneemt actie om bedreigingen te corrigeren met endpointdetectie en -antwoord. Zie Microsoft [Defender for Endpoint - Endpoint Detection and Response voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender voor eindpunt - Bedreigingsexperts | Microsoft Managed Desktop integratie met inzichten en gegevens van Threat Experts via gerichte aanvalsmeldingen. U moet aanvullende toestemming geven voordat deze service is ingeschakeld. Zie Microsoft [Defender for Endpoint - Threat Experts voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender voor Eindpunt - Bedreigings- en kwetsbaarheidsbeheer | Vereist voor toekomstig gebruik in het Microsoft Managed Desktop serviceplan. Zie Microsoft [Defender for Endpoint - Threat and Vulnerability Management voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender for Endpoint - Attack Surface Reduction | Attack surface reduction targets risky software behaviors that are often abused by attackers. Zie Microsoft [Defender for Endpoint - Attack Surface Reduction voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender for Endpoint - Exploit Protection | Beschermt tegen malware die exploits gebruikt om apparaten te infecteren en te verspreiden door gebruiksbeperkingstechnieken automatisch toe te passen op zowel besturingssysteemprocessen als apps. Zie Microsoft [Defender for Endpoint - Exploit Protection voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender voor Eindpunt - Netwerkbeveiliging | Netwerkbeveiliging vergroot het bereik van Microsoft Defender SmartScreen om al het uitgaande HTTP- en HTTPS-verkeer te blokkeren dat probeert verbinding te maken met bronnen met een lage reputatie. Zie [Microsoft Defender for Endpoint - Network Protection voor meer informatie.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Microsoft Defender Tamper Protection | Windows Tamper Protection wordt gebruikt om te voorkomen dat beveiligingsinstellingen, zoals antivirusbeveiliging, worden gewijzigd. Zie Microsoft Defender Tamper Protection voor meer [informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection)
Microsoft Defender Antivirus Op gedrag gebaseerde, heuristische en realtime antivirusbeveiliging | Altijd bezig met het scannen van bestands- en procesrisico's die mogelijk niet als malware worden gedetecteerd. Zie voor meer informatie [Microsoft Defender Antivirus op gedrag gebaseerde, heuristische en realtime antivirusbeveiliging.](../../security/defender-endpoint/microsoft-defender-antivirus-in-windows-10.md)
Microsoft Defender Antivirus Beveiliging in de cloud | Biedt dynamische, geautomatiseerde bescherming tegen nieuwe en nieuwe bedreigingen. Zie voor meer informatie [Microsoft Defender Antivirus beveiliging in de cloud.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Blok op het eerste gezicht" | Biedt detectie en blokkering van nieuwe malware wanneer Windows een verdacht of onbekend bestand detecteert. Zie Microsoft Defender Block op het [eerste gezicht voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Microsoft Defender AV Potentieel ongewenste toepassingen | Potentieel ongewenste toepassingen worden gebruikt om apps te blokkeren waardoor uw computer traag kan worden uitgevoerd, onverwachte advertenties kan weergeven of in het slechtste geval andere software kan installeren die onverwacht of ongewenst kan zijn. Zie Microsoft [Defender AV Potentieel ongewenste toepassingen voor meer informatie.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender Firewall met geavanceerde beveiliging | Host-based, two-way network traffic filtering for a device, Windows Defender Firewall blocks unauthorized network traffic flowing into or out of the local device. Zie firewall met [geavanceerde beveiliging Windows Defender voor meer informatie.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Gebruikersaccountbeheer | Gebruikersaccountbeheer schakelt over naar het beveiligde bureaublad wanneer voor een taak of actie de beheerdersaccounttypetoegang is vereist. Microsoft Managed Desktop gebruikers krijgen standaardgebruikerstoegang toegewezen bij inschrijving. Zie Gebruikersaccountbeheer voor [meer informatie.](/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

Product |Informatie 
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    U kunt alle functies van Enterprise Mobility + Security E3 MDM-apparaten beheren. U kunt de Azure Active Directory Premium P2 gebruiken als een optionele functie met Microsoft Managed Desktop.
Microsoft Cloud App Security |  U kunt deze optionele functie gebruiken met Microsoft Managed Desktop.
Azure Information Protection P2  | U kunt deze optionele functie gebruiken met Microsoft Managed Desktop.
