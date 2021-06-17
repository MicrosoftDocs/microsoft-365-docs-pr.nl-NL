---
title: Test hoe Microsoft Defender voor eindpuntfuncties werken in de auditmodus
description: Met de auditmodus kunt u zien hoe Microsoft Defender voor Eindpunt uw apparaten zou beveiligen als deze was ingeschakeld.
keywords: exploit guard, audit, auditing, mode, enabled, disabled, test, demo, evaluate, lab
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.topic: article
ms.technology: mde
ms.date: 06/02/2021
ms.openlocfilehash: 23de13e9a2b0fb02b95c9bb367c3fd99e11e89c8
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985094"
---
# <a name="test-attack-surface-reduction-in-microsoft-defender-for-endpoint"></a>Test attack surface reduction in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Als onderdeel van het beveiligingsteam van uw organisatie kunt u de mogelijkheden voor het verlagen van de surface voor aanvallen configureren om in de auditmodus uit te voeren om te zien hoe ze werken. In de auditmodus kunt u het volgende inschakelen:

- Regels voor het verminderen van kwetsbaarheid voor aanvallen
- Bescherming tegen misbruik
- Netwerkbeveiliging
- En gecontroleerde toegang tot mappen in de auditmodus

Met de auditmodus kunt u een record zien van *wat* er zou zijn gebeurd als u de functie had ingeschakeld.

U kunt de auditmodus inschakelen wanneer u test hoe de functies werken. Dit helpt ervoor te zorgen dat uw line-of-business-apps niet worden beïnvloed. U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.

De functies blokkeren of voorkomen niet dat apps, scripts of bestanden worden gewijzigd. In het Windows gebeurtenislogboek worden echter gebeurtenissen opgeslagen alsof de functies volledig zijn ingeschakeld. In de auditmodus kunt u het gebeurtenislogboek bekijken om te zien wat voor invloed de functie zou hebben gehad als deze was ingeschakeld.

Als u de gecontroleerde vermeldingen wilt vinden, gaat u naar **Toepassingen en services** van  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel**.

Gebruik Defender voor eindpunt om meer details voor elke gebeurtenis te krijgen, met name voor het onderzoeken van regels voor het verminderen van het oppervlak van de aanval. Met de Console Defender voor eindpunt kunt u problemen onderzoeken als onderdeel van de [waarschuwingstijdlijn en onderzoeksscenario's.](investigate-alerts.md)

U kunt de auditmodus inschakelen met group policy, PowerShell en configuration service providers (CSP's).

> [!TIP]
> U kunt ook de website Windows Defender Testground op demo.wd.microsoft.com om te controleren of de functies werken en te zien hoe ze werken. [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)

| Controleopties | Controlemodus inschakelen | Gebeurtenissen weergeven |
|---------|---------|---------|
| Controle is van toepassing op alle gebeurtenissen | [Beheerde maptoegang inschakelen](enable-controlled-folders.md) | [Gebeurtenissen voor gecontroleerde maptoegang](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Controle is van toepassing op afzonderlijke regels | [Regels voor het verminderen van aanvalsoppervlakken inschakelen](enable-attack-surface-reduction.md) | [Regelgebeurtenissen voor surface reduction attack](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Controle is van toepassing op alle gebeurtenissen | [Netwerkbeveiliging inschakelen](enable-network-protection.md) | [Netwerkbeveiligingsgebeurtenissen](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Controle is van toepassing op afzonderlijke risico's | [Bescherming tegen misbruik inschakelen](enable-exploit-protection.md) | [Beveiligingsgebeurtenissen misbruiken](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)
