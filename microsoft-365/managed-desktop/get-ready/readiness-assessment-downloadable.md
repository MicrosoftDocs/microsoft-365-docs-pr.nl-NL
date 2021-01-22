---
title: Downloadbare gereedheidscontrole
description: Controleert apparaat- en netwerkinstellingen, inclusief vereiste eindpunten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2080b2fc924320f38d9972c82c0425fa1d8026e7
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921969"
---
# <a name="downloadable-readiness-assessment-checker"></a>Downloadbare gereedheidscontrole

Als u goed wilt werken met het beheerde bureaublad van Microsoft, moeten apparaten voldoen aan bepaalde vereisten voor hardware en instellingen. Bovendien moet elk apparaat belangrijke eindpunten kunnen bereiken. Download en voer dit hulpprogramma uit om een HTML-rapport te verkrijgen, resultaten te bekijken en vervolgens actie te ondernemen. U moet het hulpprogramma en de ondersteunende bestanden downloaden en vervolgens handmatig uitvoeren op elk apparaat dat u wilt registreren in het beheerde bureaublad van Microsoft.

Bij elke controle wordt een van de drie mogelijke resultaten door het hulpmiddel rapporteren:


|Resultaat  |Betekenis  |
|---------|---------|
|Klaar     | U hoeft niets te doen voordat u de inschrijving voltooit.        |
|Advies    | Volg de stappen in het hulpprogramma voor een optimaal gebruik van de inschrijving en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Nog niet gereed | *De inschrijving mislukt als* u deze problemen niet op kunt lossen. Volg de stappen in het hulpprogramma om deze problemen op te lossen.        |

## <a name="obtain-the-checker"></a>De controle verkrijgen

Download het ZIP-bestand van https://aka.ms/mmddratoolv0 .

> [!NOTE]
> De gebruiker die het hulpprogramma gebruikt, moet lokale beheerdersrechten hebben op het apparaat waarop het programma wordt uitgevoerd.

 Voer het hulpprogramma vervolgens uit door deze stappen te volgen:

1. Kopieer het gedownloade ZIP-bestand naar elk apparaat dat u wilt controleren.
2. Alle bestanden in de gecomprimeerde download uitpakken.
3. Voer **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** uit.
4. Wanneer de vraag van Gebruikerstoegangsbeheer wordt weergegeven, selecteert u **Ja.** Het hulpprogramma wordt uitgevoerd en er wordt een rapport geopend in uw standaardbrowser.

U kunt het ZIP-archief ook downloaden en  uitpakken naar een gedeelde locatie,Microsoft.MMD.DeviceReadinessAssessmentTool.exeelk apparaat openen en lokaal uitvoeren.


## <a name="checks"></a>Controles

Met het downloadbare hulpprogramma worden deze apparaat- en netwerkgerelateerde items gecontroleerd:

### <a name="hardware"></a>Hardware

Apparaten moeten voldoen aan specifieke hardwarevereisten om met het beheerde bureaublad van Microsoft te kunnen werken. Momenteel kunnen alleen specifieke [goedgekeurde apparaten](../service-description/device-list.md) zich registreren. 

Als uw apparaat na een van de controles mislukt, is het niet compatibel met het beheerde bureaublad van Microsoft.

### <a name="network-endpoints"></a>Netwerk-eindpunten

Apparaten hebben veel toegang tot verschillende [belangrijke eindpunten voor](network.md) gebruik met het beheerde bureaublad van Microsoft.

Als het hulpprogramma een **niet-gereed** resultaat meldt, bekijkt u het gedetailleerde rapport om erachter te komen welke eindpunten niet bereikbaar zijn. Pas vervolgens uw firewall of andere netwerkinstellingen aan om ervoor te zorgen dat deze eindpunten bereikbaar zijn.

### <a name="other-settings"></a>Overige instellingen

#### <a name="enterprise-wi-fi-profiles"></a>Wi-Fi-profielen voor ondernemingen

Een **adviesresultaat** betekent dat u gebruik maakt van een aantal Wi-Fi-profielen die certificaten en profielen nodig hebben om goed te werken. Zie Certificaten en een [Wi-Fi-/VPN-profiel implementeren voor meer informatie.](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)

#### <a name="lan-profiles"></a>LAN-profielen

Een **adviesresultaat** betekent dat u lans hebt die certificaten en profielen nodig hebben om goed te werken. Zie Certificaten en netwerkprofielen voorbereiden voor beheerd bureaublad [van Microsoft voor meer informatie.](certs-wifi-lan.md)

#### <a name="vpn-profiles"></a>VPN-profielen

Een **adviesresultaat** betekent dat u een VPN (Virtual Private Network) gebruikt. Maak een VPN-profiel voor het implementeren van certificaten die zijn geïntegreerd met Microsoft Intune. Zie Certificaten en netwerkprofielen voorbereiden voor beheerd bureaublad [van Microsoft voor meer informatie.](certs-wifi-lan.md)

#### <a name="mapped-drives"></a>Kaartstations

Een **adviesresultaat** betekent dat u een aantal kaartstations hebt, die niet worden aanbevolen. Zie Kaartstations voorbereiden voor Microsoft Managed Desktop voor [meer informatie.](mapped-drives.md)

#### <a name="print-queues"></a>Wachtrijen afdrukken

Een **adviesresultaat** betekent dat u een aantal openstaande afdrukwachtrijen hebt, die niet worden aanbevolen. Eén oplossing is het gebruik van afdrukken in de cloud. Zie Afdrukresources [voorbereiden voor het beheerde bureaublad van Microsoft voor meer informatie.](printing.md)

#### <a name="proxies"></a>Proxies

Een **adviesresultaat** betekent dat er een proxyserver in gebruik is. Zie Netwerkconfiguratie voor Microsoft Managed Desktop voor [meer informatie.](network.md)

