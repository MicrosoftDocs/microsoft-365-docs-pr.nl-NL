---
title: Beveiligingsfuncties voor Microsoft Defender Antivirus inschakelen en configureren
description: Schakel op gedrag gebaseerde, heuristische en realtime beveiliging in microsoft Defender AV in.
keywords: heuristisch, machine-learning, gedragsmonitor, realtime beveiliging, always-on, Microsoft Defender Antivirus, antimalware, beveiliging, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925553"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a>Gedrag, heuristiek en realtime bescherming configureren


**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus verschillende methoden gebruikt om bedreigingsbeveiliging te bieden:

- Beveiliging in de cloud voor bijna direct detecteren en blokkeren van nieuwe en nieuwe bedreigingen
- Always-on scanning, using file and process behavior monitoring and other heuristics (ook wel 'real-time protection' genoemd)
- Speciale beveiligingsupdates op basis van machine learning, menselijke en geautomatiseerde analyse van big data en uitgebreid onderzoek naar bedreigingsresistentie

U kunt configureren hoe Microsoft Defender Antivirus deze methoden gebruikt met groepsbeleid, System Center Configuratiebeheer, PowerShell-cmdlets en Windows Management Instrumentation (WMI).

In deze sectie vindt u informatie over de configuratie voor altijd-on scannen, inclusief het detecteren en blokkeren van apps die als onveilig worden beschouwd, maar mogelijk niet worden gedetecteerd als malware.

Zie [Next-gen Microsoft Defender Antivirus cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) gebruiken voor het in- en configureren van Microsoft Defender Antivirus beveiliging in de cloud.

## <a name="in-this-section"></a>In deze sectie

 Onderwerp | Omschrijving
---|---
[Mogelijk ongewenste toepassingen detecteren en blokkeren](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | Apps detecteren en blokkeren die ongewenst kunnen zijn in uw netwerk, zoals malware, browsermodules en werkbalken, en malafide of nep-antivirus-apps
[Beveiligingsfuncties voor Microsoft Defender Antivirus inschakelen en configureren](configure-real-time-protection-microsoft-defender-antivirus.md) | Realtime beveiliging, heuristische functies en andere functies voor het controleren van Microsoft Defender Antivirus inschakelen en configureren
