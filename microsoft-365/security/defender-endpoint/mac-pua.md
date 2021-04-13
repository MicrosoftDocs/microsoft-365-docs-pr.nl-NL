---
title: Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender ATP voor Mac
description: Detecteer en blokkeer potentieel ongewenste toepassingen (PUA) met Microsoft Defender ATP voor Mac.
keywords: microsoft, defender, atp, mac, pua, pus
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
ms.openlocfilehash: cf61c6a501a53ac03d3c4cc28068f7af4c0f88d6
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688103"
---
# <a name="detect-and-block-potentially-unwanted-applications-with-microsoft-defender-for-endpoint-on-macos"></a>Potentieel ongewenste toepassingen detecteren en blokkeren met Microsoft Defender voor Eindpunt op macOS

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


De potentieel ongewenste beveiligingsfunctie voor toepassingen (PUA) in Microsoft Defender voor Eindpunt op macOS kan PUA-bestanden op eindpunten in uw netwerk detecteren en blokkeren.

Deze toepassingen worden niet beschouwd als virussen, malware of andere soorten bedreigingen, maar kunnen acties uitvoeren op eindpunten die de prestaties of het gebruik ervan nadelig beïnvloeden. PUA kan ook verwijzen naar toepassingen die worden beschouwd als een slechte reputatie.

Deze toepassingen kunnen het risico vergroten dat uw netwerk wordt geïnfecteerd met malware, dat malware-infecties moeilijker te identificeren zijn en dat it-resources worden verspild bij het opruimen van de toepassingen.

## <a name="how-it-works"></a>Hoe het werkt

Microsoft Defender voor Eindpunt op macOS kan PUA-bestanden detecteren en rapporteren. Wanneer het bestand is geconfigureerd in de blokkeringsmodus, worden PUA-bestanden verplaatst naar de quarantaine.

Wanneer een PUA wordt gedetecteerd op een eindpunt, wordt in Microsoft Defender voor Eindpunt in macOS een melding aan de gebruiker voorgemeld, tenzij meldingen zijn uitgeschakeld. De bedreigingsnaam bevat het woord 'Toepassing'.

## <a name="configure-pua-protection"></a>PUA-beveiliging configureren

PUA-beveiliging in Microsoft Defender voor Eindpunt op macOS kan op een van de volgende manieren worden geconfigureerd:

- **Uit:** PUA-beveiliging is uitgeschakeld.
- **Audit:** PUA-bestanden worden gerapporteerd in de productlogboeken, maar niet in het Microsoft Defender-beveiligingscentrum. Er wordt geen melding weergegeven aan de gebruiker en er wordt geen actie ondernomen door het product.
- **Blokkeren:** PUA-bestanden worden gerapporteerd in de productlogboeken en in het Microsoft Defender-beveiligingscentrum. De gebruiker krijgt een melding te zien en er wordt actie ondernomen door het product.

>[!WARNING]
>Pua-beveiliging is standaard geconfigureerd in de **auditmodus.**

U kunt configureren hoe PUA-bestanden worden verwerkt vanaf de opdrachtregel of vanaf de beheerconsole.

### <a name="use-the-command-line-tool-to-configure-pua-protection"></a>Gebruik het opdrachtregelhulpmiddel om PUA-beveiliging te configureren:

Voer in Terminal de volgende opdracht uit om PUA-beveiliging te configureren:

```bash
mdatp threat policy set --type potentially_unwanted_application --action [off|audit|block]
```

### <a name="use-the-management-console-to-configure-pua-protection"></a>Gebruik de beheerconsole om PUA-beveiliging te configureren:

In uw bedrijf kunt u PUA-beveiliging configureren vanuit een beheerconsole, zoals JAMF of Intune, net zoals andere productinstellingen zijn geconfigureerd. Zie de sectie Instellingen voor [bedreigingstype](mac-preferences.md#threat-type-settings) van het onderwerp Voorkeuren instellen voor [Microsoft Defender voor Eindpunt voor macOS voor meer](mac-preferences.md) informatie.

## <a name="related-topics"></a>Verwante onderwerpen

- [Voorkeuren instellen voor Microsoft Defender voor Eindpunt op macOS](mac-preferences.md)
