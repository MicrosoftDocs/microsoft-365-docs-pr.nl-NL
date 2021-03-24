---
title: Nieuwe functies in Microsoft Defender voor Endpoint voor Linux
description: Lijst met belangrijke wijzigingen voor Microsoft Defender ATP voor Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51057486"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a>Nieuwe functies in Microsoft Defender voor Endpoint voor Linux

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

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
