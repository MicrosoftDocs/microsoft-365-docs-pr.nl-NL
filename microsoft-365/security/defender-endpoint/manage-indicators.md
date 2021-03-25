---
title: Indicatoren maken
ms.reviewer: ''
description: Maak indicatoren voor een bestandshash, IP-adres, URL's of domeinen die de detectie, preventie en uitsluiting van entiteiten definiëren.
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
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
ms.openlocfilehash: d54ab8eaa1e17be82752c480c963d3a24af56389
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187575"
---
# <a name="create-indicators"></a>Indicatoren maken

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

Indicator voor compromissen (IOC's) is een essentiële functie in elke oplossing voor eindpuntbeveiliging. Deze mogelijkheid biedt SecOps de mogelijkheid om een lijst met indicatoren in te stellen voor detectie en voor blokkeren (preventie en reactie).

Maak indicatoren die de detectie, preventie en uitsluiting van entiteiten definiëren. U kunt de actie definiëren die moet worden ondernomen, evenals de duur voor het toepassen van de actie en het bereik van de apparaatgroep waarop deze moet worden toegepast.

Momenteel ondersteunde bronnen zijn de clouddetectie-engine van Defender voor Eindpunt, de geautomatiseerde onderzoeks- en herstelprogramma en de endpoint prevention engine (Microsoft Defender AV).

**Clouddetectie-engine**<br>
De clouddetectie-engine van Defender voor Eindpunt scant regelmatig verzamelde gegevens en probeert de indicatoren die u hebt ingesteld, aan te passen. Wanneer er een overeenkomst is, wordt actie ondernomen op basis van de instellingen die u hebt opgegeven voor de IoC.

**Preventieprogramma voor eindpunten**<br>
Dezelfde lijst met indicatoren wordt geëerd door het preventiemiddel. Dit betekent dat als Microsoft Defender AV de primaire AV is geconfigureerd, de overeenkomende indicatoren worden behandeld volgens de instellingen. Als de actie bijvoorbeeld 'Waarschuwing en blokkering' is, voorkomt Microsoft Defender AV dat bestandsuitvoeringen worden uitgevoerd (blokkeren en herstellen) en wordt een bijbehorende waarschuwing opgeheven. Als de actie is ingesteld op 'Toestaan', wordt het bestand niet gedetecteerd of geblokkeerd door Microsoft Defender AV.

**Geautomatiseerde onderzoeks- en herstel-engine**<BR>
Het automatische onderzoek en de herstelmaatregelen gedragen zich hetzelfde. Als een indicator is ingesteld op 'Toestaan', wordt automatisch onderzoek en herstel een 'slecht' vonnis voor de indicator genegeerd. Als deze is ingesteld op 'Blokkeren', wordt dit als 'slecht' behandeld door automatisch onderzoek en herstel.


De huidige ondersteunde acties zijn:
- Toestaan
- Alleen waarschuwing
- Waarschuwing en blokkering


U kunt een indicator maken voor:
- [Bestanden](indicator-file.md)
- [IP-adressen, URL's/domeinen](indicator-ip-domain.md)
- [Certificaten](indicator-certificates.md)


>[!NOTE]
>Er is een limiet van 15.000 indicatoren per tenant.


## <a name="related-topics"></a>Verwante onderwerpen

- [Contextuele IoC maken](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [De API met Microsoft Defender voor eindpuntindicatoren gebruiken](ti-indicator.md)
- [Geïntegreerde partneroplossingen gebruiken](partner-applications.md)
