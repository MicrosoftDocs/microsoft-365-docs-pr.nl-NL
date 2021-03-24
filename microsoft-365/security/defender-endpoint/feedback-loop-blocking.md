---
title: Feedback-lus blokkeren
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
ms.openlocfilehash: b1ec879a2f05a0354b1a49cf94fccacb4a382193
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060549"
---
# <a name="feedback-loop-blocking"></a>Feedback-lus blokkeren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

## <a name="overview"></a>Overzicht

Het blokkeren van feedbackluss, ook wel snelle beveiliging genoemd, is een onderdeel van de mogelijkheden voor het blokkeren en inperking van gedrag [in](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) Microsoft Defender [voor Eindpunt.](https://docs.microsoft.com/windows/security/threat-protection/) Met het blokkeren van feedbacklus zijn apparaten in uw organisatie beter beveiligd tegen aanvallen. 

## <a name="how-feedback-loop-blocking-works"></a>Hoe het blokkeren van feedback-loop werkt

Wanneer een verdacht gedrag of bestand wordt gedetecteerd, zoals door [Microsoft Defender Antivirus,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)wordt informatie over dat artefact naar meerdere classificaties verzonden. De engine snelle beveiligingslus controleert en correleert de informatie met andere signalen om tot een beslissing te komen over het blokkeren van een bestand. Het controleren en classificeren van artefacten gebeurt snel. Dit resulteert in een snelle blokkering van bevestigd malware en biedt bescherming in het hele ecosysteem. 

Met snelle beveiliging kan een aanval worden gestopt op een apparaat, andere apparaten in de organisatie en apparaten in andere organisaties, omdat een aanval probeert de voet aan de grond te krijgen.


## <a name="configuring-feedback-loop-blocking"></a>Feedbackloop blokkeren configureren

Als uw organisatie Defender voor Eindpunt gebruikt, is het blokkeren van feedbacklussen standaard ingeschakeld. Snelle beveiliging vindt echter plaats door een combinatie van De mogelijkheden van Defender voor eindpunten, functies voor machine learning-beveiliging en signaal delen in microsoft-beveiligingsservices. Zorg ervoor dat de volgende functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd:

- [Basislijnen van Microsoft Defender voor eindpunten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Apparaten die zijn aan boord van Microsoft Defender voor Eindpunt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR in blokmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Surface-beperking voor aanvallen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Beveiliging van de volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Verwante artikelen

- [Gedrag blokkeren en insluiting](behavioral-blocking-containment.md)

- [(Blog) Blokkering en insluiting van gedrag: optica transformeren in beveiliging](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Nuttige Microsoft Defender voor eindpuntbronnen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
