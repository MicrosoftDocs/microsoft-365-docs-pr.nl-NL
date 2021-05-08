---
title: Microsoft Defender Antivirusbeveiligingsfuncties in- en configureren
description: Schakel op gedrag gebaseerde, heuristische en realtime beveiliging in microsoft Defender AV in.
keywords: heuristisch, machine-learning, gedragsmonitor, realtime beveiliging, always-on, Microsoft Defender Antivirus, antimalware, beveiliging, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 53b1e1474e0870388ec1cfaf214190eb0bdf7beb
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274600"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Gedrag, heuristiek en realtime bescherming configureren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus gebruikt verschillende methoden om bedreigingsbeveiliging te bieden:

- Beveiliging in de cloud voor bijna direct detecteren en blokkeren van nieuwe en nieuwe bedreigingen
- Always-on scanning, using file and process behavior monitoring and other heuristics (ook wel 'real-time protection' genoemd)
- Speciale beveiligingsupdates op basis van machine learning, menselijke en geautomatiseerde analyse van big data en uitgebreid onderzoek naar bedreigingsresistentie

U kunt configureren hoe Microsoft Defender Antivirus deze methoden gebruikt met Groepsbeleid, Systeemcentrumconfiguratie beheren, PowerShell-cmdlets en Windows Management Instrumentation (WMI).

In deze sectie vindt u informatie over de configuratie voor altijd-on scannen, inclusief het detecteren en blokkeren van apps die als onveilig worden beschouwd, maar mogelijk niet worden gedetecteerd als malware.

Zie [Next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection(Next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection).

## <a name="in-this-section"></a>In deze sectie

 Onderwerp | Omschrijving
---|---
[Mogelijk ongewenste toepassingen detecteren en blokkeren](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Apps detecteren en blokkeren die ongewenst kunnen zijn in uw netwerk, zoals malware, browsermodules en werkbalken, en malafide of nep-antivirus-apps
[Microsoft Defender Antivirus protection capabilities inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) | Realtime beveiliging, heuristische functies en andere functies voor het controleren van Microsoft Defender Antivirus inschakelen en configureren