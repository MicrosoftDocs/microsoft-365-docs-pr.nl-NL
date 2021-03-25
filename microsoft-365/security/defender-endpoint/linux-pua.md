---
title: Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender ATP voor Linux
description: Detecteer en blokkeer potentieel ongewenste toepassingen (PUA) met Microsoft Defender ATP voor Linux.
keywords: microsoft, defender, atp, linux, pua, pus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
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
ms.openlocfilehash: 40e6099349ff6c62c5e0b6c35fd9940cb9200f05
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187767"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-for-linux"></a>Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender voor Eindpunt voor Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

De mogelijk ongewenste beveiligingsfunctie voor toepassingen (PUA) in Defender voor Eindpunt voor Linux kan PUA-bestanden op eindpunten in uw netwerk detecteren en blokkeren.

Deze toepassingen worden niet beschouwd als virussen, malware of andere soorten bedreigingen, maar kunnen acties uitvoeren op eindpunten die de prestaties of het gebruik ervan nadelig beïnvloeden. PUA kan ook verwijzen naar toepassingen die worden beschouwd als een slechte reputatie.

Deze toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met malware, dat malware-infecties moeilijker te identificeren zijn en dat it-resources worden verspild bij het opruimen van de toepassingen.

## <a name="how-it-works"></a>Hoe het werkt

Defender voor Eindpunt voor Linux kan PUA-bestanden detecteren en rapporteren. Wanneer het bestand is geconfigureerd in de blokkeringsmodus, worden PUA-bestanden verplaatst naar de quarantaine.

Wanneer een PUA wordt gedetecteerd op een eindpunt, houdt Defender voor Endpoint voor Linux een record bij van de infectie in de bedreigingsgeschiedenis. De geschiedenis kan worden gevisualiseerd vanuit de Microsoft Defender-beveiligingscentrumportal of via het `mdatp` opdrachtregelprogramma. De bedreigingsnaam bevat het woord 'Toepassing'.

## <a name="configure-pua-protection"></a>PUA-beveiliging configureren

PUA-beveiliging in Defender voor Endpoint voor Linux kan op een van de volgende manieren worden geconfigureerd:

- **Uit:** PUA-beveiliging is uitgeschakeld.
- **Audit:** PUA-bestanden worden gerapporteerd in de productlogboeken, maar niet in het Microsoft Defender-beveiligingscentrum. Er wordt geen record van de infectie opgeslagen in de bedreigingsgeschiedenis en er wordt geen actie ondernomen door het product.
- **Blokkeren:** PUA-bestanden worden gerapporteerd in de productlogboeken en in het Microsoft Defender-beveiligingscentrum. Een record van de infectie wordt opgeslagen in de bedreigingsgeschiedenis en er wordt actie ondernomen door het product.

>[!WARNING]
>Pua-beveiliging is standaard geconfigureerd in de **auditmodus.**

U kunt configureren hoe PUA-bestanden worden verwerkt vanaf de opdrachtregel of vanaf de beheerconsole.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Gebruik het opdrachtregelhulpmiddel om PUA-beveiliging te configureren:

Voer in Terminal de volgende opdracht uit om PUA-beveiliging te configureren:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Gebruik de beheerconsole om PUA-beveiliging te configureren:

In uw bedrijf kunt u PUA-beveiliging configureren vanuit een beheerconsole, zoals Poppenkast of Ansible, net zoals andere productinstellingen zijn geconfigureerd. Zie de sectie Instellingen voor [bedreigingstype](linux-preferences.md#threat-type-settings) van het artikel Voorkeuren instellen voor [Defender voor eindpunt voor Linux voor meer](linux-preferences.md) informatie.

## <a name="related-articles"></a>Verwante artikelen

- [Voorkeuren instellen voor Defender voor Eindpunt voor Linux](linux-preferences.md)
