---
title: Verbindingsgebeurtenissen achter forward-proxies onderzoeken
description: Meer informatie over het gebruik van geavanceerde http-niveaucontrole via netwerkbeveiliging in Microsoft Defender voor Eindpunt, waarmee een reëel doel wordt bereikt in plaats van een proxy.
keywords: proxy, netwerkbeveiliging, doorgestuurde proxy, netwerkgebeurtenissen, audit, blok, domeinnamen, domein
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 47be07759a72a080a3687ed3bb50cef9d0a959b7
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904044"
---
# <a name="investigate-connection-events-that-occur-behind-forward-proxies"></a>Verbindingsgebeurtenissen achter forward-proxies onderzoeken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatemachines-abovefoldlink)

Defender voor Eindpunt ondersteunt netwerkverbindingsmonitoring vanaf verschillende niveaus van de netwerkstapel. Een lastig geval is dat het netwerk een doorgestuurde proxy gebruikt als gateway naar internet.

De proxy doet alsof deze het doel-eindpunt is.  In deze gevallen controleren eenvoudige netwerkverbindingsmonitoren de verbindingen met de proxy die correct is, maar een lagere onderzoekswaarde heeft. 

Defender for Endpoint ondersteunt geavanceerde HTTP-niveaucontrole via netwerkbeveiliging. Wanneer deze is ingeschakeld, wordt er een nieuw type gebeurtenis opgedoken waarin de echte doeldomeinnamen worden bekent.

## <a name="use-network-protection-to-monitor-network-connection-behind-a-firewall"></a>Netwerkbeveiliging gebruiken om de netwerkverbinding achter een firewall te controleren
Het bewaken van de netwerkverbinding achter een doorgestuurde proxy is mogelijk vanwege extra netwerkgebeurtenissen die afkomstig zijn van netwerkbeveiliging. Als u ze wilt zien op een apparaattijdlijn, schakelt u netwerkbeveiliging in (minimaal in de auditmodus). 

Netwerkbeveiliging kan worden beheerd met de volgende modi:

- **Blokkeren** <br> Gebruikers of apps worden geblokkeerd om verbinding te maken met gevaarlijke domeinen. U kunt deze activiteit zien in het Microsoft Defender-beveiligingscentrum.
- **Controle** <br> Gebruikers of apps worden niet geblokkeerd om verbinding te maken met gevaarlijke domeinen. U ziet deze activiteit echter nog steeds in het Microsoft Defender-beveiligingscentrum.


Als u netwerkbeveiliging uitstijt, worden gebruikers of apps niet geblokkeerd om verbinding te maken met gevaarlijke domeinen. U ziet geen netwerkactiviteit in het Microsoft Defender-beveiligingscentrum.

Als u het niet configureert, is netwerkblokkering standaard uitgeschakeld.

Zie Netwerkbeveiliging [inschakelen voor meer informatie.](enable-network-protection.md)

## <a name="investigation-impact"></a>Effect van onderzoek
Wanneer netwerkbeveiliging is ingeschakeld, ziet u dat op de tijdlijn van een apparaat het IP-adres de proxy blijft vertegenwoordigen, terwijl het echte doeladres wordt weergegeven.

![Afbeelding van netwerkgebeurtenissen op de tijdlijn van het apparaat](images/atp-proxy-investigation.png)

Extra gebeurtenissen die door de netwerkbeveiligingslaag worden geactiveerd, zijn nu beschikbaar om de echte domeinnamen boven water te krijgen, zelfs achter een proxy.

De gegevens van de gebeurtenis:

![Afbeelding van één netwerkgebeurtenis](images/atp-proxy-investigation-event.png)



## <a name="hunt-for-connection-events-using-advanced-hunting"></a>Op zoek naar verbindingsgebeurtenissen met behulp van geavanceerde jacht 
Alle nieuwe verbindingsgebeurtenissen zijn beschikbaar waar u ook op kunt jagen door middel van geavanceerde jacht. Aangezien deze gebeurtenissen verbindingsgebeurtenissen zijn, kunt u deze vinden onder de tabel DeviceNetworkEvents onder het `ConnecionSuccess` actietype.

Met deze eenvoudige query ziet u alle relevante gebeurtenissen:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" 
| take 10
```

![Afbeelding van geavanceerde zoekquery](images/atp-proxy-investigation-ah.png)

U kunt ook gebeurtenissen filteren die betrekking hebben op de verbinding met de proxy zelf. 

Gebruik de volgende query om de verbindingen met de proxy te filteren:

```
DeviceNetworkEvents
| where ActionType == "ConnectionSuccess" and RemoteIP != "ProxyIP"  
| take 10
```



## <a name="related-topics"></a>Verwante onderwerpen
- [Netwerkbeveiliging toepassen met GP - CSP-beleid](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection)
