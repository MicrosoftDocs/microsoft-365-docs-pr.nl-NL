---
title: Veelgestelde vragen over apparaatdetectie
description: Antwoorden zoeken op veelgestelde vragen (veelgestelde vragen) over apparaatdetectie
keywords: apparaatdetectie, ontdekken, passief, proactief, netwerk, zichtbaarheid, server, werkstation, onboard, onbeheerde apparaten
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 1c61e69b5c8d414ab229fa8bf64eb657a6e40304
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245958"
---
# <a name="device-discovery-frequently-asked-questions"></a>Veelgestelde vragen over apparaatdetectie

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Antwoorden vinden op veelgestelde vragen (veelgestelde vragen) over apparaatdetectie.

## <a name="what-is-basic-discovery-mode"></a>Wat is de basisdetectiemodus?
Met deze modus kan elk apparaat met aan boord van Microsoft Defender for Endpoint netwerkgegevens verzamelen en naburige apparaten ontdekken. Ingebouwde eindpunten verzamelen passief gebeurtenissen in het netwerk en halen daar apparaatgegevens uit op. Er wordt geen netwerkverkeer gestart. Onboarded-eindpunten halen eenvoudig gegevens op uit elk netwerkverkeer dat wordt gezien door een onboarded-apparaat. Deze gegevens worden gebruikt om niet-gebruikte apparaten in uw netwerk op te geven.

## <a name="can-i-disable-basic-discovery"></a>Kan ik Basisdetectie uitschakelen?
U hebt de optie om apparaatdetectie uit te schakelen via de [pagina Geavanceerde functies.](advanced-features.md) U verliest echter de zichtbaarheid op niet-bemande apparaten in uw netwerk. 

## <a name="what-is-standard-discovery-mode"></a>Wat is de standaarddetectiemodus?
 In deze modus kunnen eindpunten die zijn onboarded bij Microsoft Defender voor Eindpunt, actief geobserveerde apparaten in het netwerk onderzoeken om verzamelde gegevens te verrijken (met weinig netwerkverkeer). Deze modus wordt ten zeerste aanbevolen voor het maken van een betrouwbare en coherente apparaatvoorraad. Als u ervoor kiest om deze modus uit te schakelen en de basisdetectiemodus selecteert, krijgt u waarschijnlijk slechts beperkte zichtbaarheid van niet-bemande eindpunten in uw netwerk.

## <a name="can-i-control-which-devices-perform-standard-discovery"></a>Kan ik bepalen welke apparaten Standaarddetectie uitvoeren?
 U kunt de lijst met apparaten aanpassen die worden gebruikt om Standaarddetectie uit te voeren. U kunt Standaarddetectie inschakelen op alle onboarded-apparaten die deze mogelijkheid ook ondersteunen (momenteel alleen Windows 10 apparaten) of een subset of subset van uw apparaten selecteren door hun apparaatlabels op te geven. In dit geval worden alle andere apparaten geconfigureerd om alleen Basisdetectie uit te voeren. De configuratie is beschikbaar op de pagina Apparaatdetectie-instellingen.

## <a name="can-i-exclude-unmanaged-devices-from-the-device-inventory-list"></a>Kan ik niet-beheerde apparaten uitsluiten uit de lijst met apparaatvoorraad?
Ja, u kunt filters toepassen om niet-beheerde apparaten uit de lijst met apparaatvoorraad uit te sluiten. U kunt ook de kolom onboardingstatus op API-query's gebruiken om niet-gebouwde apparaten te filteren. 


## <a name="which-onboarded-devices-can-perform-discovery"></a>Welke onboarded-apparaten kunnen detectie uitvoeren?
 Onboarded-apparaten die op Windows 10 versie 1809 of hoger worden uitgevoerd, kunnen detectie uitvoeren.

## <a name="what-happens-if-my-onboarded-devices-is-connected-to-my-home-network-or-to-public-access-point"></a>Wat gebeurt er als mijn onboarded-apparaten zijn verbonden met mijn thuisnetwerk of met het openbare toegangspunt?
 De detectie-engine maakt onderscheid tussen netwerkgebeurtenissen die worden ontvangen in het bedrijfsnetwerk en buiten het bedrijfsnetwerk. Door netwerkaanduidingen te correleren tussen alle tenant-clients, worden gebeurtenissen gedifferentieerd tussen gebeurtenissen die zijn ontvangen van privénetwerken en bedrijfsnetwerken. Als de meeste apparaten in het netwerk bijvoorbeeld melden dat ze zijn verbonden met dezelfde netwerknaam, met hetzelfde standaardgateway- en DHCP-serveradres, kan ervan worden uitgegaan dat dit netwerk waarschijnlijk een bedrijfsnetwerk is. Privénetwerkapparaten worden niet vermeld in de inventaris en worden niet actief onderzocht.

## <a name="what-protocols-are-you-capturing-and-analyzing"></a>Welke protocollen legt u vast en analyseert u?
 Standaard worden alle onboarded-apparaten die op Windows 10 versie 1809 of hoger worden uitgevoerd, de volgende protocollen vastleggen en analyseren: ARP, CDP, DHCP, DHCPv6, IP (headers), LLDP, LLMNR, mDNS, MNDP, NBNS, SSDP, TCP (headers), UDP (headers), WSD

## <a name="which-protocols-do-you-use-for-active-probing-in-standard-discovery"></a>Welke protocollen gebruikt u voor actief onderzoek in Standaarddetectie?
 Wanneer een apparaat is geconfigureerd voor het uitvoeren van standaarddetectie, worden blootgestelde services getest met behulp van de volgende protocollen: ARP, FTP, HTTP, ICMP, LLMNR, NBNS, RDP, SIP, SMTP, SNMP, SSH, Telnet, UPNP, WSD, SMB, NBSS, IPP, PJL

## <a name="how-can-i-exclude-targets-from-being-probed-with-standard-discovery"></a>Hoe kan ik uitsluiten dat doelen worden onderzocht met standaarddetectie?
 Als er apparaten in uw netwerk zijn die niet actief moeten worden onderzocht, kunt u ook een lijst met uitsluitingen definiëren om te voorkomen dat ze worden gescand. De configuratie is beschikbaar op de pagina Apparaatdetectie-instellingen.

## <a name="can-i-exclude-devices-from-being-discovered"></a>Kan ik uitsluiten dat apparaten worden gevonden?
 Wanneer apparaatdetectie passieve methoden gebruikt om apparaten in het netwerk te ontdekken, kan elk apparaat dat communiceert met uw onboarded-apparaten in het bedrijfsnetwerk worden gevonden en vermeld in de inventaris. U kunt apparaten alleen uitsluiten van actief probing.

## <a name="how-frequent-is-the-active-probing"></a>Hoe vaak is het actieve probing?
 Apparaten worden actief onderzocht wanneer wijzigingen in apparaatkenmerken worden waargenomen (elke 1 tot 3 weken) om ervoor te zorgen dat de bestaande informatie up-to-date is.

## <a name="my-security-tool-raised-alert-on-unicastscannerps1-or-port-scanning-activity-initiated-by-it-what-should-i-do"></a>Mijn beveiligingshulpmiddel heeft een waarschuwing UnicastScanner.ps1 de scanactiviteit voor de poort of de poort die door het programma is gestart, wat moet ik doen?
 De actieve scripts zijn ondertekend door Microsoft en zijn veilig. U kunt het volgende pad toevoegen aan uw uitsluitingslijst: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps`


## <a name="what-is-the-amount-of-traffic-being-generated-by-the-standard-discovery-active-probe"></a>Wat is de hoeveelheid verkeer die wordt gegenereerd door de actieve detectie-sonde Standaarddetectie?
 Actief probing kan tot 5.000 verkeer genereren tussen het onboarded-apparaat en het apparaat met een sonde, elke poging om te probing

## <a name="why-is-there-a-discrepancy-between-can-be-onboarded-devices-in-the-device-inventory-and-the-number-of-devices-to-onboard-in-the-dashboard-tile"></a>Waarom is er een verschil tussen 'can be onboarded' apparaten in de apparaatvoorraad en het aantal 'apparaten aan boord' in de dashboardtegel?
Mogelijk ziet u verschillen tussen het aantal vermelde apparaten onder 'kan worden aan boord' weergegeven in de apparaatvoorraad, 'onboard to Microsoft Defender for Endpoint' beveiligingsaanbeveling en 'apparaten aan boord' dashboardwidget.

 De beveiligingsaanbeveling en de dashboardwidget zijn voor apparaten die stabiel zijn in het netwerk. met uitzondering van vluchtige apparaten, gastapparaten en andere apparaten. Het idee is om aan te bevelen op permanente apparaten, die ook de algehele beveiligingsscore van de organisatie impliceren.

## <a name="can-i-onboard-unmanaged-devices-that-were-found"></a>Kan ik onaangemande apparaten aan boord nemen die zijn gevonden?
 Ja. Niet-bemande eindpunten in uw netwerk brengen beveiligingslekken en risico's voor uw netwerk met zich mee. Als u deze inwerkt bij de service, kunt u de zichtbaarheid van de beveiliging ervan vergroten. 


