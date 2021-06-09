---
title: Indicatoren maken voor IP's en URL's/domeinen
ms.reviewer: ''
description: Maak indicatoren voor IPs en URL's/domeinen die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: ip, url, domain, manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: e7dc11fe709a6d04b6309706df90f0ebbc177e25
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841064"
---
# <a name="create-indicators-for-ips-and-urlsdomains"></a>Indicatoren maken voor IP's en URL's/domeinen 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



> [!TIP]
> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


Defender voor Eindpunt kan blokkeren wat Microsoft als schadelijke URL's/URL's ziet, via Windows Defender SmartScreen voor Microsoft-browsers en via Netwerkbeveiliging voor niet-Microsoft-browsers of oproepen die buiten een browser worden gedaan.

De gegevensset voor bedreigingsinformatie hiervoor is beheerd door Microsoft.

Door indicatoren te maken voor IPs en URL's of domeinen, kunt u nu IPs, URL's of domeinen toestaan of blokkeren op basis van uw eigen bedreigingsinformatie. U kunt dit doen via de instellingenpagina of per machinegroep als u bepaalde groepen meer of minder risico's acht dan andere.

> [!NOTE]
> Classless Inter-Domain Routing (CIDR) notatie voor IP-adressen wordt niet ondersteund. 

### <a name="before-you-begin"></a>Voordat u begint
Het is belangrijk om de volgende vereisten te begrijpen voordat u indicatoren maakt voor IPS, URL's of domeinen:
- URL/IP allow and block is afhankelijk van de Defender for Endpoint-component Network Protection die moet worden ingeschakeld in de blokmodus. Zie Netwerkbeveiliging inschakelen voor meer informatie over netwerkbeveiliging en [configuratie-instructies.](enable-network-protection.md)
- De versie van de Antimalware-client moet 4.18.1906.x of hoger zijn. 
- Ondersteund op machines op Windows 10, versie 1709 of hoger. 
- Controleer of **aangepaste netwerkindicatoren** zijn ingeschakeld in Microsoft Defender-beveiligingscentrum > Instellingen > **Geavanceerde functies.** Zie Geavanceerde functies [voor meer informatie.](advanced-features.md)
- Zie Aangepaste indicatoren [configureren](/microsoft-365/security/defender-endpoint/ios-configure-features#configure-custom-indicators)voor ondersteuning van indicatoren in iOS.


> [!IMPORTANT]
> Alleen externe IP's kunnen worden toegevoegd aan de lijst met indicatoren. Indicatoren kunnen niet worden gemaakt voor interne IPs.
> Voor scenario's voor webbeveiliging wordt u aangeraden de ingebouwde mogelijkheden in Microsoft Edge. Microsoft Edge maakt gebruik [van Netwerkbeveiliging om](network-protection.md) netwerkverkeer te controleren en maakt blokken voor TCP, HTTP en HTTPS (TLS) mogelijk. Als er conflicterende URL-indicatorbeleidsregels zijn, wordt het langere pad toegepast. Het beleid voor URL-indicator heeft `https:\\support.microsoft.com/en-us/office` bijvoorbeeld voorrang op het URL-indicatorbeleid. `https:\\support.microsoft.com`

> [!NOTE]
> Voor alle andere processen maken scenario's voor webbeveiliging gebruik van Netwerkbeveiliging voor inspectie en handhaving: 
> - IP wordt ondersteund voor alle drie protocollen
> - Alleen enkele IP-adressen worden ondersteund (geen CIDR-blokken of IP-bereik)
> - Versleutelde URL's (volledig pad) kunnen alleen worden geblokkeerd in first party browsers (Internet Explorer, Edge)
> - Versleutelde URL's (alleen FQDN) kunnen worden geblokkeerd buiten first party browsers (Internet Explorer, Edge)
> - Volledige URL-padblokken kunnen worden toegepast op het domeinniveau en alle niet-versleutelde URL's
 
> [!NOTE]
> Er kan maximaal 2 uur latentie zijn (meestal minder) tussen de tijd dat de actie wordt uitgevoerd en de URL en HET IP-adres worden geblokkeerd. 

### <a name="create-an-indicator-for-ips-urls-or-domains-from-the-settings-page"></a>Een indicator voor IPs, URL's of domeinen maken op de pagina Instellingen

1. Selecteer in het navigatiedeelvenster **Instellingen**  >  **Indicatoren.**  

2. Selecteer het **tabblad IP-adressen of URL's/domeinen.**

3. Selecteer **Item toevoegen.**

4. Geef de volgende details op:
   - Indicator: geef de details van de entiteit op en definieer de afloop van de indicator.
   - Actie: geef de actie op die moet worden ondernomen en geef een beschrijving op.
   - Bereik: definieer het bereik van de machinegroep.

5. Bekijk de details op het tabblad Overzicht en klik vervolgens op **Opslaan.**

## <a name="related-topics"></a>Verwante onderwerpen
- [Indicatoren maken](manage-indicators.md)
- [Indicatoren voor bestanden maken](indicator-file.md)
- [Indicatoren maken op basis van certificaten](indicator-certificates.md)
- [Indicatoren beheren](indicator-manage.md)
