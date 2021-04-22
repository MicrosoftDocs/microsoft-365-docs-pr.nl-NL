---
title: Apparaatwaarde toewijzen - bedreigings- en kwetsbaarheidsbeheer
description: Meer informatie over het toewijzen van een lage, normale of hoge waarde aan een apparaat om onderscheid te maken tussen activumprioriteiten.
keywords: Microsoft Defender for Endpoint device value, threat and vulnerability management device value, high value devices, device value exposure score
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ca6c88b08b331eb65035387a9c070d0914b1651d
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935195"
---
# <a name="assign-device-value---threat-and-vulnerability-management"></a>Apparaatwaarde toewijzen - bedreigings- en kwetsbaarheidsbeheer

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

Als u de waarde van een apparaat definieert, kunt u onderscheid maken tussen activumprioriteiten. De apparaatwaarde wordt gebruikt om de risicobereidheid van een afzonderlijk activum op te nemen in de berekening van blootstellingsscores voor bedreigings- en kwetsbaarheidsbeheer. Apparaten die zijn toegewezen als 'hoge waarde' krijgen meer gewicht.

U kunt ook de [set device value API gebruiken.](set-device-value.md)

Opties voor apparaatwaarde:

- Laag
- Normaal (standaard)
- Hoog

Voorbeelden van apparaten die een hoge waarde moeten krijgen:

- Domeincontrollers, Active Directory
- Apparaten met internet
- VIP-apparaten
- Apparaten die interne/externe productieservices hosten

## <a name="choose-device-value"></a>Apparaatwaarde kiezen

1. Navigeer naar een apparaatpagina, de eenvoudigste plaats is uit de apparaatvoorraad.

2. Selecteer **Apparaatwaarde** op drie puntjes naast de actiebalk boven aan de pagina.

    ![Voorbeeld van de vervolgkeuzekeuze van de apparaatwaarde.](images/tvm-device-value-dropdown.png)

3. Er wordt een flyout weergegeven met de huidige apparaatwaarde en wat dit betekent. Controleer de waarde van het apparaat en kies het apparaat dat het beste bij uw apparaat past.
![Voorbeeld van de flyout van de apparaatwaarde.](images/tvm-device-value-flyout.png)

## <a name="how-device-value-impacts-your-exposure-score"></a>Hoe de apparaatwaarde van invloed is op uw blootstellingsscore

De blootstellingsscore is een gewogen gemiddelde op alle apparaten. Als u apparaatgroepen hebt, kunt u de score ook filteren op apparaatgroep.

- Normale apparaten hebben een gewicht van 1
- Apparaten met een lage waarde hebben een gewicht van 0,75
- Apparaten met een hoge waarde hebben een gewicht van NumberOfAssets / 10.
    - Als u 100 apparaten hebt, heeft elk apparaat met een hoge waarde een gewicht van 10 (100-10)

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van bedreigings- en kwetsbaarheidsbeheer](next-gen-threat-and-vuln-mgt.md)
- [Blootstellingsscore](tvm-exposure-score.md)
- [API‘s](next-gen-threat-and-vuln-mgt.md#apis)