---
title: Releasenotities van Microsoft Defender for Endpoint API
description: Releasenotities voor updates die zijn aangebracht in de Microsoft Defender for Endpoint-set API's.
keywords: Microsoft Defender for Endpoint API release notes, mde, API's, Microsoft Defender for Endpoint API, updates, notes, release
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 4f9d3b365fb735805644f33b3a843ad66e777ce4
ms.sourcegitcommit: a6fb731fdf726d7d9fe4232cf69510013f2b54ce
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684121"
---
# <a name="microsoft-defender-for-endpoint-api-release-notes"></a>Releasenotities van Microsoft Defender for Endpoint API

**Van toepassing op:** [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

- Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

De volgende informatie bevat de updates die zijn aangebracht aan de API's van Microsoft Defender voor eindpunten en de datums waarop ze zijn gemaakt.

> [!TIP]
> RSS-feed: Ontvang een melding wanneer deze pagina wordt bijgewerkt door de volgende URL in uw feedlezer te kopiëren en te kopiëren:
>
> ```http
> https://docs.microsoft.com/api/search/rss?search=%22Release+notes+for+updates+made+to+the+Microsoft+Defender+for+Endpoint+set+of+APIs%22&locale=en-us&facet=&%24filter=scopes%2Fany%28t%3A+t+eq+%27Windows+10%27%29
> ```

## <a name="release-notes---newest-to-oldest-ddmmyyyy"></a>Releasenotities - nieuwste naar oudste (dd.mm.yyyy)

### <a name="05252021"></a>05.25.2021

- Nieuwe API [Exportbeoordelingsmethoden en -eigenschappen per apparaat toegevoegd.](get-assessmnt-1methods-properties.md)

### <a name="03052021"></a>03.05.2021

- Nieuwe API toegevoegd: [herstelactiviteitsmethoden en -eigenschappen](get-remediation-methods-properties.md).

### <a name="10022021"></a>10.02.2021

- Nieuwe API toegevoegd: [waarschuwingen voor batchupdates.](batch-update-alerts.md)

### <a name="25012021"></a>25.01.2021

- Bijgewerkte tariefbeperkingen voor [Advanced Hunting API](run-advanced-query-api.md) van 15 tot 45 aanvragen per minuut.

### <a name="21012021"></a>21.01.2021

- Nieuwe API toegevoegd: [Apparaten zoeken op tag](machine-tags.md).
- Nieuwe API toegevoegd: [importindicatoren](import-ti-indicators.md).

### <a name="03012021"></a>03.01.2021

- Bijgewerkte waarschuwingen: toegevoegde eigenschappen ***detectieStatus** _, _*_bovenliggendeProcessFilePath_*_ en _ *_parentProcessFileName_** .
- Bijgewerkte [waarschuwingsentiteit:](alerts.md) ***eigenschap melderid*** toegevoegd.

### <a name="15122020"></a>15.12.2020

- Bijgewerkte apparaatentiteit: ***lijst met IpInterfaces*** toegevoegd. [](machine.md) Zie [Lijstapparaten](get-machines.md).

### <a name="04112020"></a>04.11.2020

- Nieuwe API toegevoegd: [apparaatwaarde instellen.](set-device-value.md)
- Bijgewerkte apparaatentiteit: ***eigenschap apparaatwaarde*** toegevoegd. [](machine.md)

### <a name="01092020"></a>01.09.2020

- De optie Toegevoegd om de entiteit Waarschuwing uit te vouwen met het bijbehorende bewijs. Zie [Lijstwaarschuwingen](get-alerts.md).
