---
title: Het COVID-19-antwoord en de ondersteuning van Contoso voor extern en on-site werken
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Inzicht in de manier waarop Contoso B.v. de COVID-19 Pandemic heeft gereageerd en de IT-infrastructuur voor de installatie en het bijwerken van de software voor extern en on-site werken.
ms.openlocfilehash: 8e25b399d7acd2cb3486283623d29315eac9491e
ms.sourcegitcommit: bdf65d48b20f0f428162c39ee997accfa84f4e5d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/20/2020
ms.locfileid: "49371749"
---
# <a name="contosos-covid-19-response-and-support-for-remote-and-onsite-work"></a>Het COVID-19-antwoord en de ondersteuning van Contoso voor extern en on-site werken

Contoso heeft altijd de externe werknemers ondersteund, die on-premises resources openen via een centrale VPN-server in de Headquarters van Parijs. Contoso heeft alle externe werknemers een beheerde laptop verstrekt. On-premises medewerkers hadden een combinatie van desktopcomputers en laptops.

## <a name="contosos-response-to-covid-19"></a>De antwoord van Contoso op COVID-19

Met het begin van de COVID-19 Pandemic, is het voor alle werknemers met een uitzondering op de werknemers. Contoso heeft gereageerd op het verschuiven van de werknemers aan het werk en onderhoudt de primaire activiteiten via externe toegang tot on-premises resources en online via Microsoft 365 cloudservices.

Contoso heeft een RAS-VPN-server in het hoofdkantoor van Parijs voor de ondersteuning van de 25% van het al uw werk op afstand, maar is snel verhuisd om de externe toegangs capaciteit te ondersteunen voor 90% van zijn of haar personeel. Contoso heeft de Remote Access-servers geïmplementeerd voor VPN-servers in elk satellietkantoor, zodat externe medewerkers een onderhouds punt in de buurt willen gebruiken voor toegang tot het contoso intranet.

Contoso heeft de configuratie van VPN-clients die zijn geïnstalleerd op laptops, Tablets en smartphones ook bijgewerkt, zodat verkeer voor de geoptimaliseerde set van Office 365-eindpunten de VPN-verbinding negeert en rechtstreeks via internet is verzonden. Zie [Office 365-connectiviteit optimaliseren voor externe gebruikers met behulp van gesplitste tunneling voor VPN-verbinding](../enterprise/microsoft-365-vpn-split-tunnel.md)voor meer informatie.

Dit zijn de configuraties met VPN-apparaten die zijn geïnstalleerd in de hoofdkantoren van Parijs en elk van de satelliet kantoren. 

![De VPN-infrastructuur van contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Een externe werknemer met de geïnstalleerde VPN-client gebruikt DNS om het land dat het dichtst bij Office te vinden, te vinden en maakt verbinding met het geïnstalleerde VPN-apparaat. Met gesplitste tunneling wordt verkeer naar Microsoft 365 optimaliseren eindpunten rechtstreeks naar het dichtstbijzijnde Microsoft 365-netwerk verplaatst. Alle andere verkeer wordt via de VPN-verbinding naar het VPN-apparaat verzonden.

## <a name="contosos-support-for-remote-and-onsite-work"></a>De ondersteuning van Contoso voor extern en on-site werken

Nadat de eerste wijzigingen zijn aangebracht in het grootste medewerkers van regio-vergrendelingen, heeft Contoso wijzigingen in de infrastructuur aangebracht voor de ondersteuning van de externe en op de volgende werknemer:

- Altijd extern.
- Altijd on-premises.
- Een combinatie van afstand en on-premises.

Microsoft 365 identiteit, beveiliging en compliance-functies zijn ontworpen voor een vertrouwensrelatie van nul en werken ongeacht de locatie van de gebruiker en hun apparaat. Zie voor meer informatie [0 vertrouwen](https://www.microsoft.com/security/business/zero-trust).

Het beheren van nieuwe installaties en updates van software is afhankelijk van de locatie van het apparaat omdat de software die u installeert, beschikbaar is via een on-premises of een Internet bron. Contoso IT-architecten hebben hun nieuwe installaties en updates-infrastructuur ontworpen op basis van de locatie van het apparaat, in plaats van de werknemer.

De persoon heeft twee soorten apparaten aangewezen: gespecialiseerde on-premises en roaming.

### <a name="dedicated-on-premises"></a>Gespecialiseerde on-premises

Een specifiek on-premises apparaat is een desktopcomputer of Server computer waarop het contoso intranet niet mag worden gebruikt en geen VPN-client is geïnstalleerd. Deze on-premises apparaten blijven gebruikmaken van Microsoft Configuration Manager en de distributiepunten voor installaties en updates van Windows 10, Microsoft 365-apps voor Enterprise en de Edge-browser.

### <a name="roaming"></a>Signaal

Met een roaming-apparaat kunt u het intranet van Contoso sluiten en ook laptops opnemen die aan veel Office-medewerkers zijn verleend, en alle externe werknemers en andere apparaten van de organisatie, zoals smartphones en tablets waarop de contoso VPN-client is geïnstalleerd. 

Aangezien deze apparaten op een bepaald moment via het Internet kunnen worden verbonden, gebruiken ze intune-of andere cloudservices voor installaties en updates van Windows 10, Microsoft 365-apps voor Enterprise en Edge. Ze gebruiken geen bestaande distributiepunten voor de configuratie van on-premises Configuration Manager.

Dit betekent dat sommige installaties en updates voor zwervend apparaat via internet plaatsvinden, terwijl ze on-premises zijn en verbonden zijn met het intranet. Met Contoso IT-architecten werd ook besloten dat de eenvoud van configuratie belangrijker is dan de optimalisering van de intranet bandbreedte op internet, met name wanneer de meeste externe medewerkers zelden verbonden zijn met het intranet.

Dit is de daaruit voortvloeiende infrastructuur.

![Infrastructuur van Contoso-installaties en-updates](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Het gedrag voor installeren en bijwerken wordt bepaald door de computeraccounts van apparaten lid te maken van een van de volgende groepen:

- OnPremDevices

  De Configuration Manager-client op het apparaat gebruikt distributiepunten voor installaties en updates.

- RoamingDevices

  InTune en andere instellingen op het apparaat Hiermee geeft u het Microsoft 365-netwerk op voor installaties en updates.

## <a name="new-onboarding-process"></a>Nieuw systeem voor onboarding

Wanneer de werknemer zich aanmeldt, wordt de Configuration Manager-client op basis van het lidmaatschap van het apparaat in de OnPremDevices-groep gedownload en installeert de nieuwste updates voor Windows 10, Microsoft 365-apps voor Enterprise en de Edge-distributiepunten van on-premises Configuration Manager. Wanneer u klaar bent, is het speciale on-premises apparaat gereed voor gebruik en gebruikt u deze distributiepunten voor voortdurende updates.

Wanneer de werknemer zich meldt, op basis van het lidmaatschap van de RoamingDevices-groep, wordt contact gemaakt met de intune-cloudservice en andere services en worden de meest recente updates voor Windows 10, Microsoft 365-apps voor Enterprise en Edge geïnstalleerd en geïnstalleerd door de werknemers die aan een nieuwe werknemer zijn verleend. Wanneer u klaar bent, kunt u het externe apparaat gebruiken en gebruikt u de geïnstalleerde VPN-client voor toegang tot on-premises resources en het Microsoft 365-netwerk voor voortdurende updates.

## <a name="next-step"></a>Volgende stap

[De werknemers](empower-people-to-work-remotely.md) in uw organisatie stimuleren.
