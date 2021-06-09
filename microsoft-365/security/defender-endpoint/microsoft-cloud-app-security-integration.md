---
title: Overzicht van integratie van Microsoft Cloud App Security
ms.reviewer: ''
description: Microsoft Defender for Endpoint is geïntegreerd met Cloud App Security door alle netwerkactiviteiten voor cloud-apps door testuren.
keywords: cloud, app, netwerken, zichtbaarheid, gebruik
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 5a5a81bde283a9eba4d5db77ed7e4c0b7567abc9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844740"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security in Overzicht van Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Cloud App Security (Cloud App Security) is een uitgebreide oplossing waarmee u inzicht krijgt in cloud-apps en -services doordat u de toegang tot cloud-apps kunt beheren en beperken, terwijl u nalevingsvereisten afdwingt voor gegevens die zijn opgeslagen in de cloud. Zie voor meer informatie [Cloud App Security.](/cloud-app-security/what-is-cloud-app-security)

>[!NOTE]
>Deze functie is beschikbaar met een E5-licentie [voor](https://www.microsoft.com/cloud-platform/enterprise-mobility-security) Enterprise Mobility + Security apparaten met Windows 10 versie 1809 of hoger.

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender voor endpoint- en Cloud App Security-integratie 

Cloud App Security discovery is afhankelijk van cloudverkeerslogboeken die worden doorgestuurd vanuit bedrijfsfirewall- en proxyservers. Microsoft Defender voor Eindpunt is geïntegreerd met Cloud App Security door alle netwerkactiviteiten voor cloud-apps te verzamelen en door testuren, waardoor het gebruik van cloud-apps ongeëvenaard zichtbaar is. De monitoringfunctionaliteit is ingebouwd in het apparaat, wat volledige dekking biedt voor netwerkactiviteit.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4r4yQ]


De integratie biedt de volgende belangrijke verbeteringen in de bestaande Cloud App Security detectie: 

- Overal beschikbaar: aangezien de netwerkactiviteit rechtstreeks vanuit het eindpunt wordt verzameld, is het beschikbaar op elke plaats waar het apparaat zich, in of buiten het bedrijfsnetwerk, bevinden, omdat deze niet meer afhankelijk is van verkeer dat wordt gerouteerd via de bedrijfsfirewall of proxyservers. 

- Werkt out of the box, geen configuratie vereist: het doorsturen van cloudverkeerlogboeken naar Cloud App Security vereist firewall- en proxyserverconfiguratie. Met de Defender voor Eindpunt en Cloud App Security is er geen configuratie vereist. Schakel deze in in Microsoft Defender-beveiligingscentrum instellingen en u bent klaar om te gaan. 

- Apparaatcontext: cloudverkeerslogboeken hebben geen apparaatcontext. Defender voor Endpoint-netwerkactiviteit wordt gerapporteerd met de apparaatcontext (welk apparaat toegang heeft tot de cloud-app), zodat u precies kunt begrijpen waar (apparaat) de netwerkactiviteit heeft plaatsgevonden, naast wie (gebruiker) de activiteit heeft uitgevoerd. 

Zie Werken met ontdekte [apps](/cloud-app-security/discovered-apps)voor meer informatie over clouddetectie.

## <a name="related-topic"></a>Verwant onderwerp

- [Integratie van Microsoft Cloud App Security configureren](microsoft-cloud-app-security-config.md)
