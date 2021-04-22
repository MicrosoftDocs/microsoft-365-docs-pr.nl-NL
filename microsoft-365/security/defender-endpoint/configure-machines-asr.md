---
title: Asr-regelimplementatie en -detecties optimaliseren
description: Optimaliseer de ASR-regels (Attack Surface Reduction) om typische malware-exploits te identificeren en te voorkomen.
keywords: onboard, Intune management, Microsoft Defender for Endpoint, Microsoft Defender, Windows Defender, attack surface reduction, ASR, security baseline
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 91295135c833c6b403078bdfd517c7b84ec7d630
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932845"
---
# <a name="optimize-asr-rule-deployment-and-detections"></a>Asr-regelimplementatie en -detecties optimaliseren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

[Asr-regels (Attack Surface Reduction)](./attack-surface-reduction.md) identificeren en voorkomen typische malware-exploits. Ze bepalen wanneer en hoe potentieel schadelijke code kan worden uitgevoerd. Ze kunnen bijvoorbeeld voorkomen dat JavaScript of VBScript een gedownloade uitvoerbare start, Win32 API-oproepen van Office-macro's blokkeren en processen blokkeren die worden uitgevoerd via USB-stations.

![Surface-beheerkaart voor aanvallen](images/secconmgmt_asr_card.png)<br>
*Surface-beheerkaart voor aanvallen*

De *Surface Management-kaart Attack* is een toegangspunt voor hulpprogramma's in het Microsoft 365-beveiligingscentrum waarmee u het volgende kunt doen:

* Meer inzicht in de manier waarop ASR-regels momenteel worden geïmplementeerd in uw organisatie.
* Controleer ASR-detecties en identificeer mogelijke onjuiste detecties.
* Analyseer de impact van uitsluitingen en genereer de lijst met bestandspaden die u wilt uitsluiten.

Selecteer **Ga naar aanval op surface management** Monitoring & rapporten > Attack surface reduction rules > Add  >  **exclusions**. Hier kunt u naar andere secties van het Microsoft 365-beveiligingscentrum navigeren.

![Tabblad Uitsluitingen toevoegen op de pagina Surface-regels voor aanvallen in het Microsoft 365-beveiligingscentrum](images/secconmgmt_asr_m365exlusions.png)<br>
Het ***tabblad Uitsluitingen toevoegen** op de pagina Surface-regels voor aanvallen in het Microsoft 365-beveiligingscentrum*

> [!NOTE]
> Als u toegang wilt tot het Microsoft 365-beveiligingscentrum, hebt u een Microsoft 365 E3- of E5-licentie en een account met bepaalde rollen in Azure Active Directory nodig. [Lees meer over vereiste licenties en machtigingen.](https://docs.microsoft.com/office365/securitycompliance/microsoft-security-and-compliance#required-licenses-and-permissions)

Zie Asr-regelimplementatie en -detecties bewaken en beheren voor meer informatie over de implementatie van [ASR-regels](https://docs.microsoft.com/office365/securitycompliance/monitor-devices#monitor-and-manage-asr-rule-deployment-and-detections)in het Microsoft 365-beveiligingscentrum.

**Verwante onderwerpen**

* [Controleren of uw apparaten juist zijn geconfigureerd](configure-machines.md)
* [Apparaten in gebruik nemen bij Microsoft Defender voor Eindpunt](configure-machines-onboarding.md)
* [Naleving van de beveiligingslijn van Microsoft Defender voor eindpunt controleren](configure-machines-security-baseline.md)
