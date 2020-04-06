---
title: 'Fase 1: Afsluitcriteria netwerkinfrastructuur'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Zorg ervoor dat uw configuratie voldoet aan de Microsoft 365 Enterprise-criteria voor de netwerkinfrastructuur.
ms.openlocfilehash: 1ace68fd19c62e4dc389604c1b0c02ddc18b52dc
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42809132"
---
# <a name="phase-1-networking-infrastructure-exit-criteria"></a>Fase 1: Afsluitcriteria netwerkinfrastructuur

![Fase 1-Netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Zorg ervoor dat de netwerkinfrastructuur aan de volgende vereiste criteria voldoet en dat u de optionele criteria hebt overwogen.

<a name="crit-networking-step1"></a>
## <a name="required-your-network-is-ready-for-microsoft-365-enterprise"></a>Vereist: uw netwerk is gereed voor Microsoft 365 Enterprise

- Uw kantoren hebben een adequate internet-bandbreedte voor Microsoft 365-verkeer, waaronder Office 365-, Microsoft Intune- en Windows 10 Enterprise-installatie en -updates.
- Uw algehele netwerk is gekoppeld aan een [Office 365-referentiearchitectuur](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P2).
- De wijzigingen in uw netwerk zijn getest en getest en voldoen aan de vereisten voor uw netwerklatentie.

[Stap 1](networking-provide-bandwidth-cloud-services.md) kan u indien nodig helpen bij dit vereiste.

<a name="crit-networking-step2"></a>
## <a name="required-your-local-offices-have-local-internet-connections-and-name-resolution"></a>Vereist: uw lokale kantoren hebben lokale internetverbindingen en naamomzetting

U hebt elk lokale kantoor uitgerust met een internetverbinding met een lokale internetprovider, wiens DNS-servers een lokaal openbaar IP-adres gebruiken waarmee de locatie op internet wordt aangeduid. Dit garandeert de best mogelijke prestaties voor gebruikers die toegang hebben tot de cloudservices van Microsoft 365.

Als u geen lokale internetprovider gebruikt voor elk filiaal, kan het zijn dat de prestaties hieronder leiden, aangezien het netwerkverkeer dan moet worden omgeleid langs de backbone van de organisatie of gegevensaanvragen door front-end servers moeten worden verwerkt.

### <a name="how-to-test"></a>Testen
Gebruik een hulpprogramma of website vanaf een apparaat in dat kantoor om te bepalen welk openbare IP-adres de proxyserver gebruikt. Gebruik bijvoorbeeld de [Wat is mijn IP-adres](https://www.whatismypublicip.com/)-webpagina. Dit openbare IP-adres dat is toegewezen door uw internetprovider, zou geografisch lokaal moeten zijn. Het mag niet afkomstig zijn van een openbaar IP-adresbereik voor een centraal kantoor of een netwerkbeveiligingsleverancier in de Cloud.

[Stap 2](networking-dns-resolution-same-location.md) kan u indien nodig helpen bij dit vereiste.

<a name="crit-networking-step3"></a>
## <a name="optional-unnecessary-network-hairpins-are-removed"></a>Optioneel: onnodige netwerkhairpins worden verwijderd

U hebt uw netwerkhairpins onderzocht en de effecten ervan op de prestaties van al uw kantoren bepaald. U hebt de netwerkhairpins waar mogelijk verwijderd of met uw externe netwerk- of beveiligingsprovider samengewerkt om optimale Microsoft 365-peering voor hun netwerk te implementeren.

[Stap 3](networking-avoid-network-hairpins.md) kan u indien nodig helpen bij deze optie.


<a name="crit-networking-step4"></a>
## <a name="optional-you-have-configured-traffic-bypass-on-your-internet-browsers-and-edge-devices"></a>Optioneel: u hebt het omleiden van verkeer op uw internetbrowsers en randapparaten geconfigureerd

U hebt de nieuwste PAC-bestanden geïmplementeerd in uw internetbrowsers op locatie, zodat verkeer naar DNS-domeinnamen van Microsoft 365 niet via de proxyservers wordt geleid.

U hebt de apparaten voor uw netwerkperimeter geconfigureerd - zoals firewalls, SSL Break and Inspect en inspectieapparaten voor pakketten - om verkeer om te leiden of om het verkeer te beperken tot de categorieën Optimaliseren en toestaan van Microsoft 365-eindpunten.


### <a name="how-to-test"></a>Testen

Gebruik de hulpprogramma's voor logboekregistratie op uw apparaten voor uw netwerkperimeter om ervoor te zorgen dat verkeer naar Microsoft 365-bestemmingen niet wordt gecontroleerd, gedecodeerd of anderszins wordt belemmerd.

[Stap 4](networking-configure-proxies-firewalls.md) kan u indien nodig helpen bij deze optie.


<a name="crit-networking-step5"></a>
## <a name="optional-your-clients-and-office-365-applications-are-configured-for-optimal-performance"></a>Optioneel: uw clients en Office 365-toepassingen zijn geconfigureerd voor optimale prestaties

U hebt de TCP-instellingen (Transmission Control Protocol) geoptimaliseerd op uw clientapparaten en voor Exchange Online-, Skype voor Bedrijven Online-, SharePoint Online- en Project Online-services.

[Stap 5](networking-optimize-tcp-performance.md) kan u indien nodig helpen bij deze optie.

## <a name="results-and-next-steps"></a>Resultaten en volgende stappen

Uw intranet-gebruikers zijn nu klaar om Microsoft 365-cloudservices te gebruiken via een efficiënt netwerkpad naar en via internet.

|||
|:-------|:-----|
|![Fase 2-Identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)| Als u de fasen voor de end-to-end-implementatie van Microsoft 365 Enterprise volgt, is [Identiteit](identity-infrastructure.md) de volgende fase. |
