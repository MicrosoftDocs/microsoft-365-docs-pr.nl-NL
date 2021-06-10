---
title: Uw organisatie beschermen tegen webbedreigingen
description: Meer informatie over webbeveiliging in Microsoft Defender voor Endpoint en hoe het uw organisatie kan beschermen.
keywords: webbeveiliging, bescherming tegen bedreigingen op het web, surfen op het web, beveiliging, phishing, malware, misbruik, websites, netwerkbeveiliging, Edge, Internet Explorer, Chrome, Firefox, webbrowser
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0c42c05e318390741b94b6d7d1b5394fca961714
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51688943"
---
# <a name="protect-your-organization-against-web-threats"></a>Uw organisatie beschermen tegen webbedreigingen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink&rtc=1)

Webbedreigingsbeveiliging maakt deel uit [van webbeveiliging](web-protection-overview.md) in Defender voor Eindpunt. Er wordt [netwerkbeveiliging gebruikt](network-protection.md) om uw apparaten te beveiligen tegen webbedreigingen. Door te integreren met Microsoft Edge en populaire browsers van derden, zoals Chrome en Firefox, worden webbedreigingen gestopt zonder een webproxy en kunnen apparaten worden beschermd terwijl ze niet of on-premises zijn. Beveiliging tegen webbedreigingen stopt de toegang tot phishingsites, malwarevectoren, misbruiksites, niet-vertrouwde of slechte reputatiesites, evenals sites die u hebt geblokkeerd in de lijst met aangepaste [indicatoren.](manage-indicators.md)

>[!Note]
>Het kan tot een uur duren voordat apparaten nieuwe aangepaste indicatoren ontvangen.

## <a name="prerequisites"></a>Vereisten
Webbeveiliging gebruikt netwerkbeveiliging om webbrowserbeveiliging te bieden in Microsoft Edge webbrowsers van derden.

Netwerkbeveiliging op uw apparaten in- en uit te zetten:
- Bewerk de beveiligingslijn Defender voor Eindpunt onder **Web & Netwerkbeveiliging** om netwerkbeveiliging in te stellen voordat u deze implementeert of opnieuw implementeert. [Meer informatie over het controleren en toewijzen van de beveiligingslijn defender voor eindpunt](configure-machines-security-baseline.md#review-and-assign-the-microsoft-defender-for-endpoint-security-baseline)
- Schakel netwerkbeveiliging in met de configuratie van Intune-apparaten, SCCM, Groepsbeleid of uw MDM-oplossing. [Meer informatie over het inschakelen van netwerkbeveiliging](enable-network-protection.md)  

>[!Note]
>Als u netwerkbeveiliging in stelt op **Alleen controleren,** is blokkeren niet beschikbaar. U kunt ook pogingen om toegang tot schadelijke en ongewenste websites op Microsoft Edge detecteren en loggen.

## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht webbeveiliging](web-protection-overview.md)
- [Webbedreigingsbeveiliging](web-threat-protection.md)
- [Webbeveiliging monitoren](web-protection-monitoring.md)
- [Reageren op webbedreigingen](web-protection-response.md)
- [Netwerkbeveiliging](network-protection.md)
