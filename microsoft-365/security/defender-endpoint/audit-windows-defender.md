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
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7ce652d58be2d9ff28d82c088d5471a7bffdf6dc
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570970"
---
# <a name="test-how-microsoft-defender-for-endpoint-features-work-in-audit-mode"></a>Test hoe Microsoft Defender voor eindpuntfuncties werken in de auditmodus

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


In de auditmodus kunt u regels voor het verminderen van aanvallen, misbruikbeveiliging, netwerkbeveiliging en gecontroleerde maptoegang inschakelen. Met de auditmodus kunt u een record zien van *wat* er zou zijn gebeurd als u de functie had ingeschakeld.

Mogelijk wilt u de auditmodus inschakelen wanneer u test hoe de functies in uw organisatie werken. Dit helpt ervoor te zorgen dat uw line-of-business-apps niet worden beïnvloed. U kunt ook een idee krijgen van het aantal pogingen om verdachte bestanden over een bepaalde periode te wijzigen.

De functies blokkeren of voorkomen niet dat apps, scripts of bestanden worden gewijzigd. In het Windows-gebeurtenislogboek worden echter gebeurtenissen opgeslagen alsof de functies volledig zijn ingeschakeld. In de auditmodus kunt u het gebeurtenislogboek bekijken om te zien welk effect de functie zou hebben gehad als deze was ingeschakeld.

Als u de gecontroleerde vermeldingen wilt vinden, gaat u naar **Toepassingen en services**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel.**

U kunt Defender voor eindpunt gebruiken om meer details voor elke gebeurtenis te krijgen, met name voor het onderzoeken van regels voor het verminderen van de surface van de aanval. Met de Console Defender voor eindpunt kunt u problemen onderzoeken als onderdeel van de [waarschuwingstijdlijn en onderzoeksscenario's.](investigate-alerts.md)

U kunt group policy, PowerShell en configuration service providers (CSP's) gebruiken om de auditmodus in te schakelen.

> [!TIP]
> U kunt ook de Windows Defender [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) Testground-website op demo.wd.microsoft.com om te bevestigen dat de functies werken en te zien hoe ze werken.

 **Controleopties** | **Controlemodus inschakelen** | **Gebeurtenissen weergeven**
|---------|---------|---------|
| Controle is van toepassing op alle gebeurtenissen | [Beheerde maptoegang inschakelen](enable-controlled-folders.md) | [Gebeurtenissen voor gecontroleerde maptoegang](evaluate-controlled-folder-access.md#review-controlled-folder-access-events-in-windows-event-viewer)
| Controle is van toepassing op afzonderlijke regels | [Regels voor het verminderen van aanvalsoppervlakken inschakelen](enable-attack-surface-reduction.md) | [Regelgebeurtenissen voor surface reduction attack](evaluate-attack-surface-reduction.md#review-attack-surface-reduction-events-in-windows-event-viewer)
| Controle is van toepassing op alle gebeurtenissen | [Netwerkbeveiliging inschakelen](enable-network-protection.md) | [Netwerkbeveiligingsgebeurtenissen](evaluate-network-protection.md#review-network-protection-events-in-windows-event-viewer)
| Controle is van toepassing op afzonderlijke risico's | [Bescherming tegen misbruik inschakelen](enable-exploit-protection.md) | [Beveiligingsgebeurtenissen misbruiken](exploit-protection.md#review-exploit-protection-events-in-windows-event-viewer)

## <a name="related-topics"></a>Verwante onderwerpen

* [Apparaten beschermen tegen misbruik](exploit-protection.md)
* [Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval](attack-surface-reduction.md)
* [Beveilig uw netwerk](network-protection.md)
* [Belangrijke mappen beveiligen](controlled-folders.md)
