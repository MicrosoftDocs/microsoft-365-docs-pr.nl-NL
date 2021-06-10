---
title: Gedragsblokkering van cliënt
description: Clientgedragsblokkering maakt deel uit van de mogelijkheden voor het blokkeren en inperking van gedrag in Microsoft Defender voor eindpunt
keywords: behavior blocking, rapid protection, client behavior, Microsoft Defender for Endpoint
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: 295987ad28675b4381e266539846563240c0a528
ms.sourcegitcommit: 2cf7293d610a676726ac891b89366e23810d9142
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52866653"
---
# <a name="client-behavioral-blocking"></a>Gedragsblokkering van cliënt

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Overzicht

Clientgedragsblokkering is een onderdeel van de mogelijkheden voor het blokkeren en [inperking](behavioral-blocking-containment.md) van gedrag in Defender voor Eindpunt. Aangezien verdacht gedrag wordt gedetecteerd op apparaten (ook wel clients of eindpunten genoemd), worden artefacten (zoals bestanden of toepassingen) automatisch geblokkeerd, gecontroleerd en gesaneerd. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- en clientbeveiliging":::

Antivirusbeveiliging werkt het beste in combinatie met cloudbeveiliging.

## <a name="how-client-behavioral-blocking-works"></a>Hoe clientgedragsblokkering werkt

[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) kan verdacht gedrag, schadelijke code, bestandsloze en in-memory-aanvallen en meer detecteren op een apparaat. Wanneer verdacht gedrag wordt gedetecteerd, Microsoft Defender Antivirus en verzendt u die verdachte gedragingen en hun procesbomen naar de cloudbeveiligingsservice. Machine learning maakt binnen milliseconden onderscheid tussen schadelijke toepassingen en goed gedrag en classificeert elk artefact. In bijna realtime, zodra een artefact schadelijk blijkt te zijn, wordt het geblokkeerd op het apparaat. 

Wanneer een verdacht gedrag wordt gedetecteerd, wordt er een [waarschuwing](alerts-queue.md) gegenereerd en is deze zichtbaar in de Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

Clientgedragsblokkering is effectief omdat hiermee niet alleen wordt voorkomen dat een aanval wordt gestart, maar het kan ook helpen een aanval te stoppen die is begonnen met uitvoeren. En, met [het blokkeren van feedback-loop](feedback-loop-blocking.md) (een andere mogelijkheid voor het blokkeren en inperking van gedrag) worden aanvallen op andere apparaten in uw organisatie voorkomen.

## <a name="behavior-based-detections"></a>Detecties op basis van gedrag

Op gedrag gebaseerde detecties worden benoemd op basis van de [MITRE ATT-&CK Matrix voor Enterprise.](https://attack.mitre.org/matrices/enterprise) De naamgevingsconventie helpt bij het identificeren van de aanvalsfase waarin het schadelijke gedrag is waargenomen:


|Tactiek |   Naam van detectiebedreiging |
|----|----|
|Eerste toegang | `Behavior:Win32/InitialAccess.*!ml` |
|Uitvoering  | `Behavior:Win32/Execution.*!ml` |
|Persistentie    | `Behavior:Win32/Persistence.*!ml` |
|Escalatie van bevoegdheden   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|Defense Ontwijking    | `Behavior:Win32/DefenseEvasion.*!ml` |
|Referentietoegang  | `Behavior:Win32/CredentialAccess.*!ml` |
|Detectie  | `Behavior:Win32/Discovery.*!ml` |
|Zijbeweging | `Behavior:Win32/LateralMovement.*!ml` |
|Verzameling |   `Behavior:Win32/Collection.*!ml` |
|Command and Control | `Behavior:Win32/CommandAndControl.*!ml` |
|Exfiltration   | `Behavior:Win32/Exfiltration.*!ml` |
|Gevolg | `Behavior:Win32/Impact.*!ml` |
|Niet-gecategoriseerd  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> Zie recente wereldwijde bedreigingsactiviteit voor meer informatie **[over specifieke bedreigingen.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Clientgedragsblokkering configureren

Als uw organisatie Defender voor Eindpunt gebruikt, is clientgedragsblokkering standaard ingeschakeld. Zorg er echter voor dat de volgende [](behavioral-blocking-containment.md)functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd om te profiteren van alle Mogelijkheden van Defender voor eindpunten, inclusief het blokkeren en inperking van gedragingen:

- [Defender voor eindpunten](configure-machines-security-baseline.md)

- [Apparaten die zijn aan boord van Defender voor Eindpunt](onboard-configure.md)

- [EDR in blokkeringsmodus](edr-in-block-mode.md)

- [Kwetsbaarheid voor aanvallen verminderen](attack-surface-reduction.md)

- [Beveiliging van de volgende generatie](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware en andere mogelijkheden voor bedreigingsbeveiliging)

