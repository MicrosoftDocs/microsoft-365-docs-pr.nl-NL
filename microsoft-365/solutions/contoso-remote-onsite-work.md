---
title: Contoso's COVID-19-antwoord en ondersteuning voor hybride werk
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Begrijp hoe contoso Corporation heeft gereageerd op de COVID-19-epidemie en hoe ze hun software-installatie- en update-infrastructuur voor hybride werk hebben ontworpen.
ms.openlocfilehash: 2d28b0513221f6c14526baba69bf0f5986154805
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788377"
---
# <a name="contosos-covid-19-response-and-support-for-hybrid-work"></a>Contoso's COVID-19-antwoord en ondersteuning voor hybride werk

Contoso heeft haar externe werknemers altijd ondersteund, die on-premises bronnen hebben gebruikt via een centrale VPN-server in het hoofdkantoor van Parijs. Contoso had alle externe werknemers een beheerde laptop uitgegeven. On-premises werknemers hadden een combinatie van desktopcomputers en laptops.

## <a name="contosos-response-to-covid-19"></a>Contoso's antwoord op COVID-19

Met het begin van de COVID-19-epidemie waren alle essentiële werknemers plotseling externe werknemers. Contoso heeft hierop gereageerd door het personeel te verplaatsen naar thuis en zijn primaire activiteiten uit te voeren via externe toegang tot on-premises resources en online met behulp van Microsoft 365 cloudservices.

Contoso had VPN-servers voor externe toegang in het hoofdkantoor van Parijs om de 25% van het al externe personeel te ondersteunen, maar werd snel verplaatst om de capaciteit voor externe toegang op te schalen om 90% van het personeel te ondersteunen. Contoso heeft VPN-servers voor externe toegang geïmplementeerd in elk satellietkantoor, zodat externe werknemers een regionaal sluitend toegangspunt zouden gebruiken voor toegang tot het Contoso-intranet.

Contoso heeft ook de configuratie bijgewerkt van VPN-clients die zijn geïnstalleerd op laptops, tablets en smartphones voor splits tunneling, zodat verkeer voor de set Office 365-eindpunten optimaliseren de VPN-verbinding heeft overgeslagen en rechtstreeks via internet is verzonden. Zie Voor meer informatie De connectiviteit Office 365 externe gebruikers [optimaliseren met vpn-splits tunneling.](../enterprise/microsoft-365-vpn-split-tunnel.md)

Hier is de resulterende configuratie met VPN-apparaten die zijn geïnstalleerd in het hoofdkantoor van Parijs en elk van de satellietkantoren. 

![De VPN-infrastructuur van Contoso](../media/contoso-remote-onsite-work/contoso-vpn-infrastructure.png)

Een externe werknemer met de geïnstalleerde VPN-client gebruikt DNS om het dichtstbijzijnde kantoor te vinden en maakt verbinding met het VPN-apparaat dat daar is geïnstalleerd. Met gesplitste tunneling wordt het verkeer naar Microsoft 365 Eindpunten optimaliseren rechtstreeks verzonden naar de dichtstbijzijnde Microsoft 365 netwerklocatie. Al het andere verkeer wordt via de VPN-verbinding naar het VPN-apparaat verzonden.

## <a name="contosos-support-for-hybrid-work"></a>Ondersteuning van Contoso voor hybride werk

Nadat de eerste wijzigingen zijn aangebracht om voornamelijk externe werknemers te ondersteunen tijdens regionale vergrendelingen, heeft Contoso infrastructuurwijzigingen aangebracht ter ondersteuning van hybride werk waarin een werknemer het volgende kan doen:

- Altijd op afstand.
- Altijd ter plaatse.
- Een combinatie van onsite en remote.

Microsoft 365-, beveiligings- en compliancefuncties zijn ontworpen voor Zero Trust en om te werken, ongeacht de locatie van de gebruiker en hun apparaat. Zie Vertrouwen nul [voor meer informatie.](https://www.microsoft.com/security/business/zero-trust)

Het beheren van nieuwe installaties en updates van software is echter afhankelijk van de locatie van het apparaat, omdat de te installeren software afkomstig kan zijn van een on-premises of een internetbron. Contoso IT-architecten hebben hun nieuwe installaties en updates-infrastructuur ontworpen op basis van de locatie van het apparaat, in plaats van de werknemer.

Ze hebben twee typen apparaten aangewezen: dedicated on-premises en roaming.

### <a name="dedicated-on-premises"></a>Dedicated on-premises

Een speciaal on-premises apparaat is een desktop- of servercomputer die nooit het intranet van Contoso verlaat en geen VPN-client heeft geïnstalleerd. Deze on-premises apparaten blijven Microsoft Endpoint Configuration Manager en de distributiepunten gebruiken voor installaties en updates van Windows 10, Microsoft 365-apps voor ondernemingen en de Edge-browser.

### <a name="roaming"></a>Roaming

Een roamingapparaat kan het Contoso-intranet verlaten en bevat laptops die zijn uitgegeven aan veel kantoormedewerkers en alle externe werknemers en andere apparaten die eigendom zijn van de organisatie, zoals smartphones en tablets, met de Contoso VPN-client geïnstalleerd. 

Omdat deze apparaten op elk moment met internet kunnen worden verbonden, gebruiken ze Intune of andere cloudservices voor installaties en updates van Windows 10, Microsoft 365-apps voor ondernemingen en Edge. Ze maken geen gebruik van de bestaande on-premises Configuration Manager-distributiepunten.

Dit betekent dat sommige installaties en updates voor roamingapparaat via internet worden uitgevoerd terwijl ze on-premises zijn en verbonden zijn met het intranet. Maar Contoso IT-architecten besloten dat de eenvoud van configuratie belangrijker was dan het optimaliseren van intranetbandbreedte op internet, vooral wanneer de meeste externe werknemers zelden met het intranet zijn verbonden.

Hier is de resulterende infrastructuur.

![De installatie- en updatesinfrastructuur van Contoso](../media/contoso-remote-onsite-work/contoso-updates-infrastructure.png)

Het installatie- en updategedrag wordt bepaald door de computeraccounts van apparaten lid te maken van een van deze groepen:

- OnPremDevices

  De Configuration Manager-client op het apparaat gebruikt distributiepunten voor installaties en updates.

- RoamingDevices

  Intune en andere instellingen op het apparaat geven het gebruik van het Microsoft 365 voor installaties en updates op.

## <a name="new-onboarding-process"></a>Nieuw onboardingproces

Voor een nieuw, specifiek on-premises apparaat dat is uitgegeven aan een nieuwe werknemer of voor een nieuwe server in een datacenter, downloadt en installeert de client Configuration Manager op basis van het lidmaatschap van het apparaat in de OnPremDevices-groep de nieuwste updates voor Windows 10, Microsoft 365-apps voor ondernemingen en Edge van on-premises Configuration Manager-distributiepunten. Wanneer het apparaat is voltooid, is het toegewezen on-premises apparaat klaar voor gebruik en worden deze distributiepunten gebruikt voor doorlopende updates.

Voor een nieuw extern apparaat dat is uitgegeven aan een nieuwe werknemer, neemt het apparaat, op basis van het lidmaatschap van de groep RoamingDevices, contact op met de Intune-cloudservice en andere services en downloadt en installeert het de nieuwste updates voor Windows 10, Microsoft 365-apps voor ondernemingen en Edge. Wanneer het apparaat is voltooid, is het klaar voor gebruik en wordt de geïnstalleerde VPN-client gebruikt voor toegang tot on-premises resources en het Microsoft 365 netwerk voor lopende updates.

## <a name="next-step"></a>Volgende stap

[Uw infrastructuur instellen voor hybride werk](empower-people-to-work-remotely.md) in uw organisatie.
