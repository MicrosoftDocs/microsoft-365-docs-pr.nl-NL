---
title: Problemen met Microsoft Defender voor Eindpunt-service oplossen
description: Zoek oplossingen en tijdelijke oplossingen voor bekende problemen, zoals serverfouten bij het openen van de service.
keywords: problemen met Microsoft Defender voor eindpunt, serverfout, toegang geweigerd, ongeldige referenties, geen gegevens, dashboardportal, toestaan, gebeurtenisviewer oplossen
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 8aaea65c617300a16f99a9a3e3a62d94b7983198
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538349"
---
# <a name="troubleshoot-service-issues"></a>Problemen met de service oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


In deze sectie worden problemen opgelost die zich kunnen voordoen wanneer u de Microsoft Defender voor Eindpunt-service gebruikt.

## <a name="server-error---access-is-denied-due-to-invalid-credentials"></a>Serverfout : Access wordt geweigerd vanwege ongeldige referenties
Als u een serverfout ondervindt wanneer u toegang probeert te krijgen tot de service, moet u de cookie-instellingen van uw browser wijzigen.
Configureer uw browser om cookies toe te staan.

## <a name="elements-or-data-missing-on-the-portal"></a>Elementen of gegevens ontbreken in de portal
Als bepaalde elementen of gegevens ontbreken op Microsoft Defender-beveiligingscentrum is het mogelijk dat proxy-instellingen deze blokkeren.

Zorg ervoor dat de proxy allowlist is `*.securitycenter.windows.com` opgenomen.


> [!NOTE]
> U moet het HTTPS-protocol gebruiken bij het toevoegen van de volgende eindpunten.

## <a name="microsoft-defender-for-endpoint-service-shows-event-or-error-logs-in-the-event-viewer"></a>Microsoft Defender for Endpoint-service toont gebeurtenis- of foutlogboeken in de Viewer voor gebeurtenissen

Zie Gebeurtenissen en fouten controleren met Behulp van [Gebeurtenisviewer](event-error-codes.md) voor een lijst met gebeurtenis-ID's die worden gerapporteerd door de Microsoft Defender voor Eindpunt-service. Het artikel bevat ook stappen voor het oplossen van problemen met gebeurtenissen.

## <a name="microsoft-defender-for-endpoint-service-fails-to-start-after-a-reboot-and-shows-error-577"></a>Microsoft Defender for Endpoint-service kan niet starten na een herstart en geeft fout 577 weer

Als onboarding-apparaten zijn voltooid, maar Microsoft Defender voor Eindpunt niet start na een herstart en fout 577 wordt weergegeven, controleert u of Windows Defender niet is uitgeschakeld door een beleid.

Zie Ervoor zorgen dat Microsoft Defender Antivirus [niet is uitgeschakeld door beleid voor meer informatie.](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)

## <a name="known-issues-with-regional-formats"></a>Bekende problemen met regionale indelingen

**Datum- en tijdnotaties**<br>
Er zijn enkele bekende problemen met de tijd- en datumnotatie. 

De volgende datumnotaaties worden ondersteund:
- MM/dd/yyyy
- dd/MM/yyyy

De volgende datum- en tijdindelingen worden momenteel niet ondersteund:
- Datumnotatie yyy/MM/dd
- Datumnotatie dd/MM/yy
- Datumnotatie met yy. Toont alleen yyyy.
- Tijdnotatie HH:mm:ss wordt niet ondersteund (de notatie 12 uur am/PM wordt niet ondersteund). Alleen de 24-uursindeling wordt ondersteund.

**Gebruik van komma's om duizend aan te geven**<br>
Ondersteuning voor het gebruik van komma's als scheidingsteken in getallen wordt niet ondersteund. Regio's waar een getal wordt gescheiden met een komma om duizend aan te geven, zien alleen het gebruik van een punt als scheidingsteken. 15,5K wordt bijvoorbeeld weergegeven als 15,5K.

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshoot-belowfoldlink)

## <a name="microsoft-defender-for-endpoint-tenant-was-automatically-created-in-europe"></a>Microsoft Defender voor Eindpunt-tenant is automatisch gemaakt in Europa
Wanneer u Azure Defender gebruikt om servers te controleren, wordt automatisch een Microsoft Defender voor Eindpunt-tenant gemaakt. De Gegevens van Microsoft Defender voor eindpunten worden standaard opgeslagen in Europa.





## <a name="related-topics"></a>Verwante onderwerpen
- [Problemen met de onboarding van Microsoft Defender voor eindpunten oplossen](troubleshoot-onboarding.md)
- [Gebeurtenissen en fouten controleren met Behulp van Gebeurtenisviewer](event-error-codes.md)
