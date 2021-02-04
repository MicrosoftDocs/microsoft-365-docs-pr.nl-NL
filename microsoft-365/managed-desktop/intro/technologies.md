---
title: Technologieën in Microsoft Managed Desktop
description: In dit artikel worden de technologieën en apps beschreven die in Microsoft Managed Desktop worden gebruikt.
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094865"
---
# <a name="microsoft-managed-desktop-technologies"></a>Technologieën in Microsoft Managed Desktop

In dit artikel worden de technologieën en apps beschreven die in Microsoft Managed Desktop worden gebruikt.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licenties zijn vereist voor alle gebruikers van het beheerde bureaublad van Microsoft. Zie Vereisten voor [Microsoft Managed Desktop](../get-ready/prerequisites.md)voor meer informatie over licentievereisten voor de service.

Dit artikel bevat een overzicht van de onderdelen die zijn opgenomen in de vereiste Enterprise-licenties, met een beschrijving van hoe de service elk onderdeel gebruikt met Beheerde bureaublad-apparaten van Microsoft. Specifieke rollen en verantwoordelijkheden voor elk gebied worden in de documentatie van Microsoft Managed Desktop beschreven. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 of E5
 |
 --- | ---
Microsoft 365-apps voor ondernemingen (64-bits) | Deze Office-toepassingen worden geleverd met het apparaat: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype voor Bedrijven, OneNote.<br><br>De 64-bits volledige versies van Microsoft Project en Microsoft Visio zijn niet inbegrepen. Aangezien de installatie van deze toepassingen echter afhankelijk is van de Microsoft 365-apps voor enterprise-installatie, heeft Microsoft Managed Desktop standaard Microsoft Intune-implementaties en beveiligingsgroepen gemaakt die u vervolgens kunt gebruiken om deze toepassingen te implementeren voor gebruikers met een licentie. Zie Microsoft Project of Microsoft Visio installeren op [beheerde bureaubladapparaten van Microsoft voor meer informatie.](../get-started/project-visio.md)
OneDrive |Een aanmelding bij Azure Active Directory is ingeschakeld voor gebruikers wanneer ze zich voor het eerst aanmelden bij OneDrive.<br><br>De mappen Bekende mapomleiding voor 'Bureaublad', 'Document' en 'Afbeeldingen' zijn opgenomen. ingeschakeld en geconfigureerd door het beheerde bureaublad van Microsoft.
Store-apps |    Microsoft Sway en Power BI worden niet bij het apparaat geleverd. Deze apps kunnen worden gedownload in de Microsoft Store.
Win32-toepassingen |    Teams wordt niet bij het apparaat geleverd, maar wordt geleverd door Microsoft voor beheerde desktopapparaten van Microsoft. Azure Information Protection Client wordt niet samen met het apparaat verzonden, maar u kunt het wel laten inpakt voor implementatie.
Webtoepassingen |  Yammer, Office in een browser, Delve, Flow, StaffHub, PowerApps en Planner worden niet bij het apparaat geleverd. Gebruikers hebben via een browser toegang tot de webversie van deze toepassingen.



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 of E3 met Microsoft Defender voor eindpunt
Aanbevolen
 |
 --- | ---
[Windows Hello voor Bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | Klanten wordt aangeraden Windows Hello voor Bedrijven te implementeren om wachtwoorden te vervangen door sterke tweestapsverificatie die wordt gebruikt op beheerde desktopapparaten van Microsoft.
[Application Virtualization](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | Klanten kunnen Application Virtualization-pakketten (App-V) implementeren met de Intune Win32-app management-client.
[Microsoft 365 preventie van gegevensverlies](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | Klanten wordt aangeraden Microsoft 365 voor preventie van gegevensverlies (DLP) te implementeren om te controleren welke acties worden uitgevoerd op items die u hebt vastgesteld dat ze gevoelig zijn en om te voorkomen dat deze items onbedoeld worden gedeeld.   

Opgenomen en beheerd in de service
 |
 --- | ---
[BitLocker-stationversleuteling](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | BitLocker-stationsversleuteling wordt gebruikt om alle systeemstations te versleutelen. 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | Beschermt de integriteit van het systeem bij het starten en controleert of de systeemintegriteit echt behouden blijft.
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender Credential Guard gebruikt beveiliging op basis van virtualisatie om geheimen te isoleren, zodat alleen bevoorrechte systeemsoftware ze kan openen.
[Microsoft Defender voor eindpunt | Eindpuntdetectie en -reactie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft Managed Desktop Security Operations reageert op waarschuwingen en onderneemt actie om bedreigingen te herstellen met behulp van eindpuntdetectie en -reactie.
[Microsoft Defender voor eindpunt | Bedreigingsexperts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Microsoft Managed Desktop integreert met inzichten en gegevens van bedreigingsexperts via specifieke meldingen over aanvallen. Klanten moeten aanvullende toestemming geven voordat deze service wordt ingeschakeld.  
[Microsoft Defender voor eindpunt | Bedreigings- en beveiligingsprobleembeheer](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Vereist voor toekomstig gebruik in het Microsoft Managed Desktop-serviceplan.
[Microsoft Defender voor eindpunt | Attack Surface Reduction](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | Een risico op aanvallen is gericht op riskant softwaregedrag dat vaak door kwaadwillende gebruikers wordt misbruik.
[Microsoft Defender voor eindpunt | Exploit Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | Beschermt tegen malware die misbruik maakt om apparaten te infecteren en te verspreiden door automatisch technieken voor risicobeperking van misbruik toe te passen op processen en apps van het besturingssysteem.
[Microsoft Defender voor eindpunt | Netwerkbeveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | Netwerkbeveiliging breidt het bereik van Microsoft Defender SmartScreen uit om al het uitgaande HTTP-verkeer dat verbinding probeert te maken met bronnen met een slechte reputatie te blokkeren.
[Microsoft Defender Tamper Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Windows Tamper Protection wordt gebruikt om te voorkomen dat beveiligingsinstellingen, zoals de beveiliging tegen virussen, worden gewijzigd.
[Microsoft Defender Antivirus Behavior-based, heuristic, and real-time antivirus protection]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | Altijd op zoek naar bestands- en procesrisico's die mogelijk niet als malware worden gedetecteerd.
[Microsoft Defender Antivirus Cloud-delivered Protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | Biedt dynamische, directe, geautomatiseerde beveiliging tegen nieuwe en nieuwe bedreigingen.
[Microsoft Defender Block op het eerste gezicht](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Biedt detectie en blokkering van nieuwe malware wanneer Windows een verdacht of onbekend bestand detecteert.
[Potentieel ongewenste toepassingen van Microsoft Defender AV](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | Mogelijk ongewenste toepassingen (PUA) worden gebruikt om apps te blokkeren waardoor uw computer traag wordt, onverwachte advertenties kan weergeven of in het slechtste geval andere software installeert die mogelijk onverwacht of ongewenst is.
[Windows Defender Firewall met Geavanceerde beveiliging](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | Met Windows Defender Firewall in twee richting wordt er gefilterd op netwerkverkeer in twee richting voor een apparaat. Met Windows Defender Firewall wordt geblokkeerd dat ongeautoriseerd netwerkverkeer het lokale apparaat binnen of uit stroomt.
[Gebruikersaccountbeheer](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | Gebruikersaccountbeheer schakelt over naar Beveiligd bureaublad als voor een taak of actie toegang tot het administratoraccounttype is vereist. Aan microsoft Beheerd bureaublad-gebruikers wordt standaardgebruikerstoegang toegewezen bij de inschrijving. 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    U kunt alle functies van Enterprise Mobility + Security E3 en Azure Active Directory Premium P2 gebruiken om MDM-apparaten te beheren.
Microsoft Cloud App Security |  U kunt deze optionele functie gebruiken met het beheerde bureaublad van Microsoft.
Azure Information Protection P2  | U kunt deze optionele functie gebruiken met het beheerde bureaublad van Microsoft.
