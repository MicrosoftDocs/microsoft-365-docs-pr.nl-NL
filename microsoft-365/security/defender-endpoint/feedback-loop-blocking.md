---
title: Feedbacklus blokkeren
description: Het blokkeren van feedbackluss, ook wel snelle beveiliging genoemd, maakt deel uit van de mogelijkheden voor het blokkeren en inperking van gedrag in Microsoft Defender voor Eindpunt
keywords: gedrag blokkeren, snelle beveiliging, feedback blokkeren, Microsoft Defender voor eindpunt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection: ''
ms.technology: mde
ms.openlocfilehash: 7319ff5a89a20529eed7d36aa0d0b1522013abd4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842456"
---
# <a name="feedback-loop-blocking"></a>Feedbacklus blokkeren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Overzicht

Het blokkeren van feedbackluss, ook wel snelle beveiliging genoemd, is een onderdeel van de mogelijkheden voor het blokkeren en inperking van gedrag [in](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) Microsoft Defender [voor Eindpunt.](/windows/security/threat-protection/) Met het blokkeren van feedbacklus zijn apparaten in uw organisatie beter beveiligd tegen aanvallen. 

## <a name="how-feedback-loop-blocking-works"></a>Hoe het blokkeren van feedback-loop werkt

Wanneer een verdacht gedrag of bestand wordt gedetecteerd, zoals door [Microsoft Defender Antivirus,](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)wordt informatie over dat artefact naar meerdere classificaties verzonden. De engine snelle beveiligingslus controleert en correleert de informatie met andere signalen om tot een beslissing te komen over het blokkeren van een bestand. Het controleren en classificeren van artefacten gebeurt snel. Dit resulteert in een snelle blokkering van bevestigd malware en biedt bescherming in het hele ecosysteem. 

Met snelle beveiliging kan een aanval worden gestopt op een apparaat, andere apparaten in de organisatie en apparaten in andere organisaties, omdat een aanval probeert de voet aan de grond te krijgen.


## <a name="configuring-feedback-loop-blocking"></a>Feedbackloop blokkeren configureren

Als uw organisatie Defender voor Eindpunt gebruikt, is het blokkeren van feedbacklussen standaard ingeschakeld. Snelle beveiliging vindt echter plaats door een combinatie van De mogelijkheden van Defender voor eindpunten, functies voor machine learning-beveiliging en signaal delen in microsoft-beveiligingsservices. Zorg ervoor dat de volgende functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd:

- [Basislijnen van Microsoft Defender voor eindpunten](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Apparaten die zijn aan boord van Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR in blokkeringsmodus](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Kwetsbaarheid voor aanvallen verminderen](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Beveiliging van de volgende generatie](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Aanverwante artikelen

- [Gedragsblokkering en -insluiting](behavioral-blocking-containment.md)

- [(Blog) Blokkering en insluiting van gedrag: optica transformeren in beveiliging](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Nuttige Microsoft Defender voor eindpuntbronnen](/microsoft-365/security/defender-endpoint/helpful-resources)
