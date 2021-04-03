---
title: Dashboardinzichten - bedreigings- en kwetsbaarheidsbeheer
description: Het dashboard bedreigings- en kwetsbaarheidsbeheer kan SecOps en beveiligingsbeheerders helpen bij het aanpakken van cyberbeveiligingsdreigingen en het opbouwen van de beveiligingsweerbaarheid van hun organisatie.
keywords: mdatp-tvm, mdatp-tvm dashboard, threat & vulnerability management, threat and vulnerability management, risk-based threat & vulnerability management, security configuration, Microsoft Secure Score for Devices, exposure score
search.appverid: met150
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 35dd300d828bfa48ad753d7c65f36b2555cf4f60
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500175"
---
# <a name="dashboard-insights---threat-and-vulnerability-management"></a>Dashboardinzichten - bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

Bedreigings- en kwetsbaarheidsbeheer is een onderdeel van Defender voor Eindpunt en biedt zowel beveiligingsbeheerders als beveiligingsbewerkingsteams unieke waarde, waaronder:


- Realtime inzichten in eindpuntdetectie en -antwoord (EDR) die zijn gecorreleerd met eindpuntproblemen
- Zeer waardevolle apparaatprobleemcontext tijdens incidentonderzoeken
- Ingebouwde herstelprocessen via Microsoft Intune en Microsoft Endpoint Configuration Manager  
  
U kunt de mogelijkheid voor bedreigings- en kwetsbaarheidsbeheer in [het Microsoft Defender-beveiligingscentrum](https://securitycenter.windows.com/) gebruiken om:

- U blootstellingsscore en Microsoft Secure Score voor apparaten weergeven, samen met de beste beveiligingsaanbevelingen, softwareprobleem, herstelactiviteiten en blootgestelde apparaten
- EDR-inzichten correleren met eindpuntproblemen en deze verwerken
- Opties voor herstel selecteren om de hersteltaken te triageren en bij te houden
- Uitzonderingsopties selecteren en actieve uitzonderingen bijhouden

> [!NOTE]
> Apparaten die niet actief zijn in de afgelopen 30 dagen, worden niet meegeholpen aan de gegevens die de blootstellingsscore voor bedreigings- en kwetsbaarheidsbeheer van uw organisatie weerspiegelen en Microsoft Secure Score voor apparaten.

Bekijk deze video voor een kort overzicht van wat er in het dashboard voor bedreigings- en kwetsbaarheidsbeheer staat.

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r1nv]

## <a name="threat-and-vulnerability-management-dashboard"></a>Dashboard Bedreigings- en kwetsbaarheidsbeheer

 ![Microsoft Defender voor endpoint-portal](images/tvm-dashboard-devices.png)

Gebied | Omschrijving
:---|:---
**Geselecteerde apparaatgroepen (#/#)**   | Filter de gegevens voor bedreigings- en kwetsbaarheidsbeheer die u wilt zien in het dashboard en kaarten op apparaatgroepen. Wat u selecteert in het filter, is van toepassing op de pagina's bedreigings- en kwetsbaarheidsbeheer.
[**Blootstellingsscore**](tvm-exposure-score.md)   | Bekijk de huidige status van de blootstelling van uw organisatie aan bedreigingen en beveiligingsproblemen. Verschillende factoren zijn van invloed op de blootstellingsscore van uw organisatie: zwakke punten die zijn ontdekt op uw apparaten, de kans dat uw apparaten worden geschonden, de waarde van de apparaten voor uw organisatie en relevante waarschuwingen die met uw apparaten zijn gevonden. Het doel is om de blootstellingsscore van uw organisatie te verlagen om veiliger te zijn. Als u de score wilt verlagen, moet u de gerelateerde beveiligingsconfiguratieproblemen oplossen die in de beveiligingsaanbevelingen worden vermeld.
[**Microsoft Secure Score voor apparaten**](tvm-microsoft-secure-score-devices.md) | Bekijk de beveiligingsstatus van het besturingssysteem, de toepassingen, het netwerk, de accounts en de beveiligingsbesturingselementen van uw organisatie. Het doel is om de gerelateerde beveiligingsconfiguratieproblemen op te lossen om uw score voor apparaten te verhogen. Als u de balken selecteert, gaat u naar de **pagina Beveiligingsaanbeveling.**
**Verdeling van apparaatblootstelling** | Bekijk hoeveel apparaten worden blootgesteld op basis van hun blootstellingsniveau. Selecteer een sectie in het ringdiagram om naar de lijstpagina Apparaten te gaan en de namen van het betreffende apparaat, blootstellingsniveau, risiconiveau en andere details weer te geven, zoals domein, besturingssysteemplatform, de status ervan, wanneer deze voor het laatst is gezien en de tags. 
**Belangrijkste beveiligingsaanbevelingen** | Bekijk de gesorteerde beveiligingsaanbevelingen die zijn gesorteerd en geprioriteerd op basis van de risicoblootstelling van uw organisatie en de urgentie die hiervoor nodig is. Selecteer **Meer tonen** om de rest van de beveiligingsaanbevelingen in de lijst weer te geven. Selecteer **Uitzonderingen voor** de lijst met aanbevelingen met een uitzondering.
**Meest kwetsbare software** | Krijg realtime inzicht in de softwarevoorraad van uw organisatie met een lijst met kwetsbare software die op de apparaten van uw netwerk is geïnstalleerd en hoe deze van invloed zijn op de blootstellingsscore van uw organisatie. Selecteer een item voor meer informatie of **Meer bekijken** om de rest van de lijst met kwetsbare software op de **pagina Softwarevoorraad weer te** geven.
**Belangrijkste herstelactiviteiten** | Houd de herstelactiviteiten bij die zijn gegenereerd op basis van de beveiligingsaanbevelingen. U kunt elk item in de lijst  selecteren om de  details op de pagina Herstel weer te geven of selecteer Meer weergeven om de rest van de herstelactiviteiten en actieve uitzonderingen weer te geven.
**Best belichte apparaten** | Bekijk de namen van blootgestelde apparaten en hun blootstellingsniveau. Selecteer een apparaatnaam in de lijst om naar de apparaatpagina te gaan waar u de waarschuwingen, risico's, incidenten, beveiligingsaanbevelingen, geïnstalleerde software en gevonden beveiligingsproblemen kunt bekijken die zijn gekoppeld aan de blootgestelde apparaten. Selecteer **Meer tonen** om de rest van de lijst met blootgestelde apparaten weer te geven. In de lijst met apparaten kunt u tags beheren, geautomatiseerde onderzoeken starten, een livereactiesessie starten, een onderzoekspakket verzamelen, antivirusscans uitvoeren, de uitvoering van apps beperken en apparaat isoleren.

Zie [Microsoft Defender voor eindpuntpictogrammen](portal-overview.md#microsoft-defender-for-endpoint-icons)voor meer informatie over de pictogrammen die in de portal worden gebruikt.


## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Blootstellingsscore](tvm-exposure-score.md)
- [Microsoft Secure Score voor apparaten](tvm-microsoft-secure-score-devices.md)
- [Beveiligingsaanbevelingen](tvm-security-recommendation.md)
- [Software-inventaris](tvm-software-inventory.md)
- [Tijdlijn van het evenement](threat-and-vuln-mgt-event-timeline.md)

