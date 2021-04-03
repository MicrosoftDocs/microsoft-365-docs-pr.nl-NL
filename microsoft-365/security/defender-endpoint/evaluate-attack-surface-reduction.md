---
title: Regels voor het verminderen van aanvalsoppervlakken evalueren
description: Bekijk hoe aanvalsoppervlakverkorting aanvallen zou blokkeren en voorkomen met het aangepaste demoprogramma.
keywords: Aanvalsoppervlakverminking, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, evaluate, test, demo
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 07573fd92643ce5fdf3e9140031bf5f15ae8f7aa
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570337"
---
# <a name="evaluate-attack-surface-reduction-rules"></a>Regels voor het verminderen van aanvalsoppervlakken evalueren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Met de regels voor het verminderen van aanvallen kunt u voorkomen dat acties die gewoonlijk door malware worden gebruikt om apparaten of netwerken te compromitteerden. Stel regels voor het verminderen van aanvallen in voor apparaten met een van de volgende versies en versies van Windows:

- Windows 10 Pro, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows 10 Enterprise, [versie 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) of hoger
- Windows Server, [versie 1803 (halfjaarlijks kanaal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) of hoger
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Lees hoe u regels voor het verminderen van aanvallen kunt evalueren door de auditmodus in te schakelen om de functie rechtstreeks in uw organisatie te testen.

> [!TIP]
> U kunt ook naar de website voor demoscenario's van Microsoft Defender voor [Eindpunt](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) demo.wd.microsoft.com om te bevestigen dat de functie werkt en te zien hoe deze werkt.

## <a name="use-audit-mode-to-measure-impact"></a>Controlemodus gebruiken om de impact te meten

Schakel regels voor het verminderen van aanvallen in de auditmodus in om een record weer te geven van apps die zouden zijn geblokkeerd als de functie volledig was ingeschakeld. Test hoe de functie in uw organisatie werkt om ervoor te zorgen dat deze geen invloed heeft op uw line-of-business-apps. U kunt ook een idee krijgen van hoe vaak de regels worden gebruikt tijdens normaal gebruik.

Gebruik de volgende PowerShell-cmdlet als u een regel voor het verminderen van het oppervlak van een aanval wilt inschakelen in de auditmodus:

```PowerShell
Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
```

Waar `<rule ID>` is een [GUID-waarde van de regel voor de beperking van het aanvalsoppervlak](attack-surface-reduction.md#attack-surface-reduction-rules).

Gebruik de volgende PowerShell-cmdlet als u alle extra regels voor het verlagen van de surface-aanvallen wilt inschakelen in de auditmodus:

```PowerShell
(Get-MpPreference).AttackSurfaceReductionRules_Ids | Foreach {Add-MpPreference -AttackSurfaceReductionRules_Ids $_ -AttackSurfaceReductionRules_Actions AuditMode}
```

> [!TIP]
> Als u volledig wilt controleren hoe de regels voor het verlagen van de surface voor aanvallen in uw organisatie werken, moet u een beheerhulpmiddel gebruiken om deze instelling te implementeren op apparaten in uw netwerk(en).

U kunt ook configuratieserviceproviders (MDM) (Group Policy, Intune) of Mobile Device Management (MDM) gebruiken om de instelling te configureren en te implementeren. Meer informatie in het [hoofdartikel Van de surface-beperkingsregels van](attack-surface-reduction.md) Attack.

## <a name="review-attack-surface-reduction-events-in-windows-event-viewer"></a>Gebeurtenissen voor het verminderen van aanvallen bekijken in Windows Event Viewer

Als u apps wilt bekijken die zijn geblokkeerd, opent u Gebeurtenisviewer en filtert u op Gebeurtenis-id 1121 in het Microsoft-Windows-Windows Defender/Operationeel logboek. In de volgende tabel worden alle netwerkbeveiligingsgebeurtenissen vermeld.

Gebeurtenis-id | Omschrijving
-|-
 5007 | Gebeurtenis wanneer instellingen worden gewijzigd
 1121 | Gebeurtenis wanneer een regel voor het verminderen van het aanvalsoppervlak wordt gebruikt in de blokmodus
 1122 | Gebeurtenis wanneer een regel voor het verminderen van het oppervlak van een aanval wordt uitgevoerd in de auditmodus

## <a name="customize-attack-surface-reduction-rules"></a>Regels voor het verminderen van aanvalsoppervlakken aanpassen

Tijdens de evaluatie kunt u elke regel afzonderlijk configureren of bepaalde bestanden en processen uitsluiten van de evaluatie door de functie.

Zie [Attack Surface Reduction Rules aanpassen](customize-attack-surface-reduction.md) voor informatie over het configureren van de functie met beheerhulpmiddelen, waaronder Groepsbeleid en MDM CSP-beleid.

## <a name="see-also"></a>Zie ook

* [Aanvalsoppervlakken verminderen met regels voor het beperken van de surface van de aanval](attack-surface-reduction.md)
* [Auditmodus gebruiken om Windows Defender te evalueren](audit-windows-defender.md)
* [Veelgestelde vragen over kwetsbaarheid voor aanvallen verminderen](attack-surface-reduction.md)
