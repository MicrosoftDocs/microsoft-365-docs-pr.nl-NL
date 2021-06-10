---
title: Downloadbare gereedheidsevaluatie-controle
description: Hiermee worden apparaat- en netwerkinstellingen gecontroleerd, inclusief vereiste eindpunten
keywords: Microsoft Managed Desktop, Microsoft 365, service, documentatie
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: eec6bdff2e494e0f55b06cb581c5775d3ffeb9e3
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581032"
---
# <a name="downloadable-readiness-assessment-checker"></a>Downloadbare gereedheidsevaluatie-controle

Als u goed wilt werken met Microsoft Managed Desktop, moeten apparaten voldoen aan bepaalde vereisten voor hardware en instellingen. Bovendien moet elk apparaat belangrijke eindpunten kunnen bereiken. Download en voer dit hulpprogramma uit om een HTML-rapport te verkrijgen, resultaten weer te geven en actie te ondernemen. U moet het hulpprogramma en de ondersteunende bestanden downloaden en vervolgens handmatig uitvoeren op elk apparaat dat u wilt registreren voor Microsoft Managed Desktop.

Voor elke controle rapporteert het hulpprogramma een van de drie mogelijke resultaten:


|Resultaat  |Betekenis  |
|---------|---------|
|Gereed     | Er is geen actie vereist voordat u de inschrijving voltooit.        |
|Advies    | Volg de stappen in het hulpprogramma voor de beste ervaring met registratie en voor gebruikers. U *kunt* de inschrijving voltooien, maar u moet deze problemen oplossen voordat u uw eerste apparaat implementeert.        |
|Nog niet klaar | *De inschrijving mislukt als* u deze problemen niet op kunt lossen. Volg de stappen in het hulpprogramma om deze op te lossen.        |

## <a name="obtain-the-checker"></a>De controle verkrijgen

Download het .zip bestand van https://aka.ms/mmddratoolv0 .

> [!NOTE]
> De gebruiker die het hulpprogramma gebruikt, moet de lokale beheerdersrechten hebben op het apparaat waarop de functie wordt uitgevoerd.

 Voer het hulpprogramma vervolgens uit door de volgende stappen uit te voeren:

1. Kopieer het gedownloade .zip naar elk apparaat dat u wilt controleren.
2. Haal alle bestanden in de gecomprimeerde download op.
3. Voer **Microsoft.MMD.DeviceReadinessAssessmentTool.exe** uit.
4. Wanneer de prompt Gebruikerstoegangsbesturingselement wordt weergegeven, selecteert u **Ja**. Het hulpprogramma wordt uitgevoerd en opent een rapport in uw standaardbrowser.

U kunt het archief ook downloaden en .zip naar een gedeelde locatie, toegang **tot** Microsoft.MMD.DeviceReadinessAssessmentTool.exeelk apparaat en vervolgens lokaal uitvoeren.


## <a name="checks"></a>Controles

Met het downloadbare hulpprogramma worden deze apparaat- en netwerkgerelateerde items gecontroleerd:

### <a name="hardware"></a>Hardware

Apparaten moeten voldoen aan specifieke hardwarevereisten voor gebruik met Microsoft Managed Desktop. Op dit moment mogen alleen specifieke [goedgekeurde](../service-description/device-list.md) apparaten zich registreren. 

Als uw apparaat een van de controles mislukt, is het niet compatibel met Microsoft Managed Desktop.

### <a name="network-endpoints"></a>Netwerk-eindpunten

Apparaten kunnen veel verschillende belangrijke eindpunten [bereiken om](network.md) te werken met Microsoft Managed Desktop.

Als het hulpprogramma  een niet-gereed resultaat rapporteert, bekijkt u het gedetailleerde rapport om erachter te komen welke eindpunten niet bereikbaar waren. Pas vervolgens uw firewall of andere netwerkinstellingen aan om ervoor te zorgen dat deze eindpunten kunnen worden bereikt.

### <a name="other-settings"></a>Andere instellingen

#### <a name="enterprise-wi-fi-profiles"></a>Enterprise Wi-Fi-profielen

Een **adviesresultaat** betekent dat u bepaalde wi-fi-profielen gebruikt die certificaten en profielen nodig hebben om goed te kunnen werken. Zie Certificaten en [Wi-Fi/VPN-profiel](certs-wifi-lan.md#deploy-certificates-and-wi-fivpn-profile)implementeren voor meer informatie.

#### <a name="lan-profiles"></a>LAN-profielen

Een **adviesresultaat** betekent dat u LN's hebt die certificaten en profielen nodig hebben om goed te kunnen werken. Zie Certificaten en netwerkprofielen voorbereiden [voor](certs-wifi-lan.md)Microsoft Managed Desktop.

#### <a name="vpn-profiles"></a>VPN-profielen

Een **adviesresultaat** betekent dat u een virtueel privénetwerk (VPN) gebruikt. Maak een VPN-profiel dat certificaten implementeert die zijn geïntegreerd met Microsoft Intune. Zie Certificaten en netwerkprofielen voorbereiden [voor](certs-wifi-lan.md)Microsoft Managed Desktop.

#### <a name="mapped-drives"></a>In kaart gebrachte stations

Een **Advisory-resultaat** betekent dat u bepaalde in kaart gebrachte stations hebt, die niet worden aanbevolen. Zie Kaartstations voorbereiden [voor](mapped-drives.md)Microsoft Managed Desktop.

#### <a name="print-queues"></a>Wachtrijen afdrukken

Een **adviesresultaat** betekent dat u een aantal openstaande afdrukwachtrijen hebt, die niet worden aanbevolen. Eén oplossing is het gebruik van cloudafdrukken. Zie Afdrukresources voorbereiden [voor](printing.md)Microsoft Managed Desktop.

#### <a name="proxies"></a>Proxies

Een **adviesresultaat** betekent dat u een proxyserver in gebruik hebt. Zie Netwerkconfiguratie voor [Microsoft Managed Desktop.](network.md)

