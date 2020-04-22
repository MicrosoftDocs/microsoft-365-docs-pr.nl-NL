---
title: 'Stap 3: Netwerkhairpins vermijden'
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
description: Inzicht krijgen in netwerkhairpins en deze verwijderen voor betere prestaties.
ms.openlocfilehash: 1d5e10bdd8b79f5c7ccd646ac08f83bb2c48b6ee
ms.sourcegitcommit: d818828c66cf98b0b0037ba8b3cb790c940281b7
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43583423"
---
# <a name="step-3-avoid-network-hairpins"></a>Stap 3: Netwerkhairpins vermijden

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![Fase 1-netwerken](../media/deploy-foundation-infrastructure/networking_icon-small.png)

Een [netwerkhairpin](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#BKMK_P3) treedt op wanneer het verkeer dat voor een bestemming is bedoeld, eerst wordt doorgestuurd naar een andere tussenliggende locatie, zoals een on-premises beveiligingsstack, een cloud access broker of een cloud-webgateway. Hier volgt een voorbeeld.

![Voorbeeld van een netwerkhairpin](../media/networking-avoid-network-hairpins/network-hairpin-example.png)

Een netwerkhairpin kan ook worden veroorzaakt door een slechte routering op internet vanwege netwerkserviceproviders. 

Een hairpin voegt latentie toe en kan mogelijk verkeer omleiden naar een geografisch afgelegen locatie.

Als u de prestaties van het verkeer naar de cloudservices van Microsoft 365 wilt optimaliseren, controleert u of de internetprovider die de lokale Internet verbinding biedt een directe relatie heeft met het wereldwijde Microsoft-netwerk. Deze verbindingen hebben geen hairpins.

Als u in de cloud-based netwerk- of beveiligingsservices gebruikt voor uw Microsoft 365-verkeer, moet u ervoor zorgen dat het hairpinning-effect wordt geëvalueerd en u inzicht hebt op de invloed op prestaties. Bekijk het volgende:

- Het aantal en de locaties van uw serviceproviders waarmee het verkeer wordt doorgestuurd ten opzichte van de filialen en de peeringpunten van het Microsoft Global Network 
- De kwaliteit van de peeringrelatie op het netwerk van de serviceprovider met uw internetprovider en Microsoft 
- Het prestatieresultaat van het backhaulen in de infrastructuur van de serviceprovider

Configureer zo mogelijk de edge-routers om rechtstreeks vertrouwd Microsoft 365-verkeer te verzenden, in plaats van via een cloud van een derde partij of het netwerk van een cloud-based beveiligingsleverancier voor de verwerking van uw internetverkeer. 

![Hier volgt een voorbeeld van het omzeilen van een netwerkhairpin](../media/networking-avoid-network-hairpins/bypassing-network-hairpin.png)

Gebruik het [Office 365 Network Onboarding-hulpprogramma](https://connectivity.office.com/) om te testen hoe dicht u bij een invoerpunt voor het globale netwerk van Microsoft bent en hoe dicht u bij een punt bent waar uw bedrijfsnetwerk de verbinding maakt met uw ISP.

Als tussentijds controlepunt kunt u de [afsluitcriteria](networking-exit-criteria.md#crit-networking-step3) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![Stap 4](../media/stepnumbers/Step4.png)|[Omleiden van verkeer configureren](networking-configure-proxies-firewalls.md)|
