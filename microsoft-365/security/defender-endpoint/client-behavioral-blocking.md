---
title: Clientgedragsblokkering
description: Clientgedragsblokkering maakt deel uit van de mogelijkheden voor het blokkeren en inperking van gedrag in Microsoft Defender ATP
keywords: behavior blocking, rapid protection, client behavior, Microsoft Defender ATP
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
ms.openlocfilehash: c37a1180f9def51daa4229418b05abe7cf787aa3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165259"
---
# <a name="client-behavioral-blocking"></a>Clientgedragsblokkering

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>Overzicht

Clientgedragsblokkering is een onderdeel van de mogelijkheden voor het blokkeren en [inperking](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) van gedrag in Defender voor Eindpunt. Aangezien verdacht gedrag wordt gedetecteerd op apparaten (ook wel clients of eindpunten genoemd), worden artefacten (zoals bestanden of toepassingen) automatisch geblokkeerd, gecontroleerd en gesaneerd. 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- en clientbeveiliging":::

Antivirusbeveiliging werkt het beste in combinatie met cloudbeveiliging.

## <a name="how-client-behavioral-blocking-works"></a>Hoe clientgedragsblokkering werkt

[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) kan verdacht gedrag, schadelijke code, bestandsloze en in-memory-aanvallen en meer detecteren op een apparaat. Wanneer verdacht gedrag wordt gedetecteerd, controleert en verzendt Microsoft Defender Antivirus deze verdachte gedragingen en hun procesbomen naar de cloudbeveiligingsservice. Machine learning maakt binnen milliseconden onderscheid tussen schadelijke toepassingen en goed gedrag en classificeert elk artefact. In bijna realtime, zodra een artefact schadelijk blijkt te zijn, wordt het geblokkeerd op het apparaat. 

Wanneer een verdacht gedrag wordt gedetecteerd, wordt er een [waarschuwing](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) gegenereerd en is deze zichtbaar in het Microsoft Defender-beveiligingscentrum ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ).

Clientgedragsblokkering is effectief omdat hiermee niet alleen wordt voorkomen dat een aanval wordt gestart, maar het kan ook helpen een aanval te stoppen die is begonnen met uitvoeren. En, met [het blokkeren van feedback-loop](feedback-loop-blocking.md) (een andere mogelijkheid voor het blokkeren en inperking van gedrag) worden aanvallen op andere apparaten in uw organisatie voorkomen.

## <a name="behavior-based-detections"></a>Detecties op basis van gedrag

Op gedrag gebaseerde detecties worden benoemd op basis van de [MITRE ATT-&CK Matrix voor Enterprise.](https://attack.mitre.org/matrices/enterprise) De naamgevingsconventie helpt bij het identificeren van de aanvalsfase waarin het schadelijke gedrag is waargenomen:


|Tactiek |   Naam van detectiebedreiging |
|----|----|
|Eerste toegang | Gedrag:Win32/InitialAccess.*!ml |
|Uitvoering  | Gedrag:Win32/Execution.*!ml |
|Persistentie    | Gedrag:Win32/Persistentie.*!ml |
|Escalatie van bevoegdheden   | Gedrag:Win32/PrivilegeEscalation.*!ml |
|Defense Ontwijking    | Gedrag:Win32/DefenseEvasion.*!ml |
|Referentietoegang  | Gedrag:Win32/CredentialAccess.*!ml |
|Detectie  | Gedrag:Win32/Discovery.*!ml |
|Zijbeweging | Gedrag:Win32/LateralMovement.*!ml |
|Verzameling |   Gedrag:Win32/Collection.*!ml |
|Command and Control | Gedrag:Win32/CommandAndControl.*!ml |
|Exfiltration   | Gedrag:Win32/Exfiltration.*!ml |
|Gevolg | Gedrag:Win32/Impact.*!ml |
|Niet-gecategoriseerd  | Gedrag:Win32/Generic.*!ml |

> [!TIP]
> Zie recente wereldwijde bedreigingsactiviteit voor meer informatie **[over specifieke bedreigingen.](https://www.microsoft.com/wdsi/threats)**


## <a name="configuring-client-behavioral-blocking"></a>Clientgedragsblokkering configureren

Als uw organisatie Defender voor Eindpunt gebruikt, is clientgedragsblokkering standaard ingeschakeld. Zorg er echter voor dat de volgende [](behavioral-blocking-containment.md)functies en mogelijkheden van Defender voor Eindpunt zijn ingeschakeld en geconfigureerd om te profiteren van alle Mogelijkheden van Defender voor eindpunten, inclusief het blokkeren en inperking van gedragingen:

- [Defender voor eindpunten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [Apparaten die zijn aan boord van Defender voor Eindpunt](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [EDR in blokmodus](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [Surface-beperking voor aanvallen](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [Beveiliging van de volgende generatie](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)

## <a name="related-articles"></a>Verwante artikelen

- [Gedrag blokkeren en insluiting](behavioral-blocking-containment.md)

- [Feedback-lus blokkeren](feedback-loop-blocking.md)

- [(Blog) Blokkering en insluiting van gedrag: optica transformeren in beveiliging](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [Nuttige Defender voor eindpuntresources](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
