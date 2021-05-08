---
title: Compatibiliteit met antivirusoplossingen met Defender voor Eindpunt
description: Meer informatie over hoe Windows Defender werkt met Microsoft Defender voor Eindpunt en hoe deze werkt wanneer een antimalwareclient van derden wordt gebruikt.
keywords: windows defender compatibility, defender, Microsoft Defender for Endpoint, defender for endpoint, antivirus, mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: 84c523b721596d9c467f01cf6b8a0685b2091669
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274878"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>Compatibiliteit met antivirusoplossingen met Microsoft Defender voor Eindpunt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

De Microsoft Defender voor Eindpunt-agent is afhankelijk van Microsoft Defender Antivirus voor bepaalde mogelijkheden, zoals bestandsscans.

>[!IMPORTANT]
>Defender voor Eindpunt voldoet niet aan de instellingen voor Microsoft Defender Antivirus Exclusions. 

U moet beveiligingsintelligentie-updates configureren op de Defender voor Eindpunt-apparaten, ongeacht of Microsoft Defender Antivirus de actieve antimalware is of niet. Zie Microsoft [Defender Antivirus-updates](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)beheren en basislijnen toepassen voor meer informatie.

Als een onboarded-apparaat is beveiligd door een antimalwareclient van derden, gaat Microsoft Defender Antivirus op dat eindpunt in de passieve modus.

Microsoft Defender Antivirus blijft updates ontvangen en het *mspeng.exe-proces* wordt weergegeven als een service die wordt uitgevoerd, maar er worden geen scans uitgevoerd en de lopende antimalwareclient van derden wordt niet vervangen.

De Microsoft Defender Antivirus-interface wordt uitgeschakeld en gebruikers op het apparaat kunnen Microsoft Defender Antivirus niet gebruiken om on-demand scans uit te voeren of de meeste opties te configureren.

Zie het onderwerp [Microsoft Defender Antivirus and Defender for Endpoint compatibility topic (Microsoft Defender Antivirus and Defender for Endpoint compatibility topic) voor meer informatie.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)
