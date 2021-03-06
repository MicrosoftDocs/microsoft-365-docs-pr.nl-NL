---
title: Nieuwe functies in Microsoft Defender voor Endpoint op Linux
description: Lijst met belangrijke wijzigingen voor Microsoft Defender voor Eindpunt op Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
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
ms.openlocfilehash: 0adcecefc19c681ef68498a3e7c375913d85985d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651126"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a>Nieuwe functies in Microsoft Defender voor Endpoint op Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a>101.29.64 (30.121042.12964.0)

- Vanaf deze versie worden bedreigingen die zijn gedetecteerd tijdens on-demand antivirusscans die worden geactiveerd via de opdrachtregelclient, automatisch verwijderd. Bedreigingen die zijn gedetecteerd tijdens scans die via de gebruikersinterface worden geactiveerd, vereisen nog steeds handmatige actie.
- `mdatp diagnostic real-time-protection-statistics` ondersteunt nu twee extra schakelopties:
  - `--sort`: sorteert de uitvoer aflopend op het totale aantal gescande bestanden
  - `--top N`: geeft de hoogste N-resultaten weer (werkt alleen als `--sort` deze ook is opgegeven)
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1012572-30121022125630"></a>101.25.72 (30.121022.12563.0)

- Microsoft Defender voor Eindpunt op Linux is nu beschikbaar in preview voor klanten van de Amerikaanse overheid. Zie Microsoft [Defender for Endpoint voor klanten](gov.md)van de Amerikaanse overheid voor meer informatie.
- Er is een probleem opgelost waarbij het gebruik van Microsoft Defender voor Eindpunt op Linux op systemen met FUSE-bestandssystemen leidde tot vastloper van besturingssysteem
- Prestatieverbeteringen & andere oplossingen voor fouten

## <a name="1012563-30121022125630"></a>101.25.63 (30.121022.12563.0)

- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1012364-30121021123640"></a>101.23.64 (30.121021.12364.0)

- Prestatieverbetering voor de situatie waarin een volledig bevestigingspunt wordt toegevoegd aan de lijst met antivirusuitsluitingen. Vóór deze versie is de bestandsactiviteit die afkomstig is van het bevestigingspunt, nog steeds verwerkt door het product. Vanaf deze versie wordt bestandsactiviteit voor uitgesloten bevestigingspunten onderdrukt, wat leidt tot betere productprestaties
- Er is een nieuwe optie toegevoegd aan het opdrachtregelprogramma om informatie over de laatste scan op aanvraag weer te geven. Als u informatie wilt weergeven over de laatste scan op aanvraag, voer dan `mdatp health --details antivirus`
- Andere prestatieverbeteringen & bug fixes

## <a name="1011853"></a>101.18.53

- EDR voor Linux is nu [algemeen beschikbaar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)
- Een nieuwe opdrachtregelschakelaar () toegevoegd om AV-uitsluitingen `--ignore-exclusions` te negeren tijdens aangepaste scans ( `mdatp scan custom` )
- Uitgebreid met een nieuwe parameter ( ) waarmee de diagnostische `mdatp diagnostic create` `--path [directory]` logboeken kunnen worden opgeslagen in een andere adreslijst
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1011299"></a>101.12.99

- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1010476"></a>101.04.76

- Bug fixes

## <a name="1010348"></a>101.03.48

- Bug fixes

## <a name="1010255"></a>101.02.55

- Er is een probleem opgelost waarbij het product soms niet begint na een herstart/upgrade
- Er is een probleem opgelost waarbij proxy-instellingen niet worden gebruikt voor productupgrades

## <a name="1010075"></a>101.00.75

- Ondersteuning toegevoegd voor de volgende bestandssysteemtypen: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` en `vfat`
- Nieuwe syntaxis voor het [opdrachtregelhulpmiddel](linux-resources.md#configure-from-the-command-line).
- Prestatieverbeteringen & oplossingen voor fouten

## <a name="1009070"></a>100.90.70

> [!WARNING]
> Bij het upgraden van het geïnstalleerde pakket van een productversie eerder dan 100.90.70, kan de update mislukken in de distributies Red Hat en SLES. Dit komt door een belangrijke wijziging in een bestandspad. Een tijdelijke oplossing is om het oudere pakket te verwijderen en vervolgens het nieuwere pakket te installeren. Dit probleem bestaat niet in nieuwere versies.

- [Antivirusuitsluitingen ondersteunen nu jokertekens](linux-exclusions.md#supported-exclusion-types)
- De mogelijkheid toegevoegd om [prestatieproblemen op te lossen](linux-support-perf.md) via het `mdatp` opdrachtregelhulpmiddel
- Verbeteringen om de installatie van het pakket krachtiger te maken
- Prestatieverbeteringen & oplossingen voor fouten
