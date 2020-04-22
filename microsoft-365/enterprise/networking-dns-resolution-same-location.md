---
title: 'Stap 2: lokale internetverbindingen configureren voor elk kantoor'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/20/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Begrijp en configureer uw DNS-resolutie voor betere prestaties.
ms.openlocfilehash: bc1460ec40cda26d4784c7af5e909e4dca3c1f24
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583435"
---
# <a name="step-2-configure-local-internet-connections-for-each-office"></a>Stap 2: lokale internetverbindingen configureren voor elk kantoor

*Deze stap is vereist en is van toepassing op zowel de E3- als de E5-versie van Microsoft 365 Enterprise*

![Fase 1-Netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

In stap 2 zorgt u ervoor dat elk van uw kantoren lokale internetverbindingen heeft en lokale DNS-servers gebruikt. Beide elementen zijn vereist om de latentie van verbindingen te verminderen en ervoor te zorgen dat lokale client-computers verbindingen maken met het dichtstbijzijnde toegangspunt tot cloudservices van Microsoft 365.

In traditionele netwerken voor grote organisaties gaat internetverkeer via de netwerk-backbone naar een centrale internetverbinding. Dit werkt niet goed voor het optimaliseren van de prestaties voor een wereldwijd gedistribueerde Software-as-a-Service (SaaS)-infrastructuur, waaronder de Office 365- en Intune-producten in Microsoft 365.

Het Microsoft Global Network omvat een *Distributed Service Front Door*-infrastructuur, een zeer beschikbare en schaalbare netwerkrand met geografisch verspreide locaties. Het verbreekt verbindingen van eindgebruikers op een voordeurserver en routeert het verkeer van eindgebruikers op efficiënte wijze binnen het Microsoft Global Network.

![Het Microsoft Global Network](../media/networking-dns-resolution-same-location/microsoft-global-network.png)

Voor de beste prestaties moeten klanten op locatie toegang hebben tot een voordeurlocatie die zich geografisch het dichtst bij hen bevindt, in plaats van het verkeer via een netwerkbackbone te sturen naar de voordeur die het dichtst bij de centrale internetverbinding van de organisatie ligt.

Hier ziet u een voorbeeld.

![Voorbeeld van het gebruik van het Microsoft Global Network](../media/networking-dns-resolution-same-location/microsoft-global-network-example.png)

Wanneer een gebruiker in het filiaal in Parijs toegang wil krijgen tot een SharePoint Online-site:

1. Er wordt een DNS-query verstuurd om een naam om te zetten, zoals contoso.sharepoint.com. 
2. De DNS-server van de internetprovider stuurt die query door naar een Microsoft DNS-server.
3. De DNS-servers van Microsoft stemmen het bron-IP-adres van de doorgestuurde DNS-query af op de regio van de wereld waaraan dat adres is toegewezen. De Microsoft DNS-server reageert met het IP-adres van de dichtstbijzijnde Microsoft Network-voordeur in Europa.
4. De DNS-server van de internetprovider stuurt dit IP-adres naar de gebruiker.
5. De gebruiker brengt via de voordeur van Europa een verbinding tot stand met de SharePoint-server.

De DNS-servers van Microsoft gebruiken de DNS-query's die overeenkomen met de oorspronkelijke verbindingsaanvragen van de client om een clientaanvraag naar de geografisch dichtstbijzijnde voordeur te sturen. Voor de laagste netwerklatentie is het volgende van belang:

- Alle kantoren van uw organisatie moeten lokale internetverbindingen hebben voor netwerkverkeer in de categorie [optimaliseren](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories).
- Elke lokale internetverbinding moet een regionale, lokale DNS-server gebruiken voor uitgaand internetverkeer vanaf die locatie.

Zie [uitgaande netwerkverbindingen lokaal instellen](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#egress-network-connections-locally)voor meer informatie. 

Gebruik het [Office 365 Network Onboarding-hulpprogramma](https://connectivity.office.com/) om te testen hoe dicht u bij een invoerpunt voor het globale netwerk van Microsoft bent en hoe dicht u bij een punt bent waar uw bedrijfsnetwerk de verbinding maakt met uw ISP.

Als tussentijds controlepunt kunt u de [afsluitcriteria](networking-exit-criteria.md#crit-networking-step2) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 3](../media/stepnumbers/Step3.png)|[Netwerk-hairpins vermijden](networking-avoid-network-hairpins.md)|
