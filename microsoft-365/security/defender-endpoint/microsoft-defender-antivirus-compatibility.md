---
title: Microsoft Defender Antiviruscompatibiliteit met andere beveiligingsproducten
description: Wat u kunt verwachten van Microsoft Defender Antivirus met andere beveiligingsproducten en de besturingssystemen die u gebruikt.
keywords: Windows Defender, volgende generatie, antivirus, compatibiliteit, passieve modus
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8eb52e277f7987477114db9333c3f90bb581ebb5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690097"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antiviruscompatibiliteit

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>Overzicht

Microsoft Defender Antivirus wordt automatisch ingeschakeld en geïnstalleerd op eindpunten en apparaten met Windows 10. Maar wat gebeurt er als er een andere antivirus-/antimalware-oplossing wordt gebruikt? Dit hangt af van of u [Microsoft Defender](microsoft-defender-endpoint.md) voor eindpunt gebruikt samen met uw antivirusbeveiliging.
- Als de eindpunten en apparaten van uw organisatie zijn beveiligd met een niet-Microsoft-antivirus-/antimalware-oplossing en Microsoft Defender voor Eindpunt niet wordt gebruikt, wordt Microsoft Defender Antivirus automatisch uitgeschakeld.
- Als uw organisatie Microsoft Defender voor Eindpunt gebruikt samen met een niet-Microsoft antivirus-/antimalware-oplossing, gaat Microsoft Defender Antivirus automatisch naar de passieve modus. (Realtime beveiliging en bedreigingen worden niet door Microsoft Defender Antivirus gesaneerd.)
- Als uw organisatie Microsoft Defender voor Eindpunt gebruikt samen met een niet-Microsoft antivirus-/antimalware-oplossing en [u EDR in](/microsoft-365/security/defender-endpoint/edr-in-block-mode) de blokmodus hebt ingeschakeld, wordt het artefact geblokkeerd en gesaneerd wanneer een schadelijk artefact wordt gedetecteerd.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>Antivirus en Microsoft Defender voor Eindpunt

In de volgende tabel wordt samengevat wat er gebeurt met Microsoft Defender Antivirus wanneer antivirusproducten van derden samen of zonder Microsoft Defender voor Eindpunt worden gebruikt. 


| Windows-versie   | Antimalware-beveiliging  | Microsoft Defender voor endpoint-inschrijving | Microsoft Defender Antivirus state     |
|------|------|-------|-------|
| Windows 10  | Een product van derden dat niet wordt aangeboden of ontwikkeld door Microsoft | Ja  | Passieve modus  |
| Windows 10  | Een product van derden dat niet wordt aangeboden of ontwikkeld door Microsoft | Nee   | Modus automatisch uitgeschakeld     |
| Windows 10  | Microsoft Defender Antivirus | Ja  | Actieve modus | 
| Windows 10  | Microsoft Defender Antivirus | Nee   | Actieve modus |
| Windows Server, versie 1803 of hoger of Windows Server 2019 | Een product van derden dat niet wordt aangeboden of ontwikkeld door Microsoft | Ja  | Moet zijn ingesteld op passieve modus (handmatig) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, versie 1803 of hoger of Windows Server 2019 | Een product van derden dat niet wordt aangeboden of ontwikkeld door Microsoft | Nee  | Moet zijn uitgeschakeld (handmatig) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, versie 1803 of hoger of Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Actieve modus  |
| Windows Server, versie 1803 of hoger of Windows Server 2019 | Microsoft Defender Antivirus | Nee  | Actieve modus |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Actieve modus |
| Windows Server 2016 | Microsoft Defender Antivirus | Nee | Actieve modus |
| Windows Server 2016 | Een product van derden dat niet wordt aangeboden of ontwikkeld door Microsoft | Ja | Moet zijn uitgeschakeld (handmatig) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Een product van derden dat niet wordt aangeboden of ontwikkeld door Microsoft | Nee | Moet zijn uitgeschakeld (handmatig) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Op Windows Server, versie 1803 of hoger of Windows Server 2019 voert Microsoft Defender Antivirus niet automatisch de passieve modus in wanneer u een niet-Microsoft-antivirusproduct installeert. Stel in dat geval [Microsoft Defender Antivirus](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) in op passieve modus om problemen te voorkomen die worden veroorzaakt doordat meerdere antivirusproducten op een server zijn geïnstalleerd.

Als u Windows Server, versie 1803 of hoger of Windows Server 2019 gebruikt, kunt u Microsoft Defender Antivirus instellen op passieve modus door de volgende registersleutel in te stellen:
- Pad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Naam: `ForcePassiveMode`
- Typ: `REG_DWORD`
- Waarde: `1`

> [!NOTE]
> De `ForcePassiveMode` registersleutel wordt niet ondersteund op Windows Server 2016.

(<a id="fn2">2</a>) In Windows Server 2016 voert Microsoft Defender Antivirus niet automatisch de passieve modus in wanneer u een niet-Microsoft-antivirusproduct installeert. Daarnaast wordt Microsoft Defender Antivirus niet ondersteund in de passieve modus. In die gevallen schakelt [u Microsoft Defender Antivirus](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) handmatig uit of verwijdert u deze om problemen te voorkomen die worden veroorzaakt doordat meerdere antivirusproducten op een server zijn geïnstalleerd.

Zie [Microsoft Defender Antivirus op Windows Server voor](microsoft-defender-antivirus-on-windows-server.md) belangrijke verschillen en beheeropties voor Windows Server-installaties.

> [!IMPORTANT]
> Microsoft Defender Antivirus is alleen beschikbaar op apparaten met Windows 10, Windows Server 2016, Windows Server, versie 1803 of hoger en Windows Server 2019.
>
> In Windows 8.1 en Windows Server 2012 wordt antivirusbeveiliging op ondernemingsniveau aangeboden als [System Center Endpoint Protection,](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))dat wordt beheerd via Microsoft Endpoint Configuration Manager.
>
> Windows Defender wordt ook aangeboden voor consumentenapparaten [op Windows 8.1 en Windows Server 2012,](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)maar biedt geen bedrijfsbeheer (of een interface op Windows Server 2012 Server Core-installaties).

## <a name="functionality-and-features-available-in-each-state"></a>Functionaliteit en functies die beschikbaar zijn in elke status

De tabel in deze sectie bevat een overzicht van de functionaliteit en functies die beschikbaar zijn in elke status. De tabel is alleen bedoeld als informatief. Het is bedoeld om de functies & functies te beschrijven die actief werken of niet, afhankelijk van of Microsoft Defender Antivirus zich in de actieve modus, in passieve modus of uitgeschakeld/verwijderd. 

> [!IMPORTANT]
> Schakel geen mogelijkheden uit, zoals realtime beveiliging, beveiliging in de cloud of beperkt periodiek scannen, als u Microsoft Defender Antivirus gebruikt in de passieve modus of als u EDR gebruikt in de blokmodus. 

|Beveiliging |Actieve modus |Passieve modus |EDR in blokkeringsmodus |Uitgeschakeld of verwijderd |
|:---|:---|:---|:---|:---|
| [Realtime beveiliging en](./configure-real-time-protection-microsoft-defender-antivirus.md) [beveiliging in de cloud](./enable-cloud-protection-microsoft-defender-antivirus.md) | Ja | Nee <sup> [[3](#fn3)]<sup> | Nee | Nee |
| [Beperkte beschikbaarheid van periodiek scannen](./limited-periodic-scanning-microsoft-defender-antivirus.md) | Nee | Nee | Nee | Ja |
| [Gegevens over het scannen en opsporen van bestanden](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nee |
|  [Herstel van bedreigingen](./configure-remediation-microsoft-defender-antivirus.md) | Ja | Zie opmerking <sup> [[4](#fn4)]<sup> | Ja | Nee |
| [Beveiligingsintelligentie-updates](./manage-updates-baselines-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nee |

(<a id="fn3">3</a>) Wanneer Microsoft Defender Antivirus in de passieve modus is, biedt realtimebeveiliging over het algemeen geen blokkering of handhaving, ook al is het ingeschakeld en in de passieve modus. 

(<a id="fn4">4</a>) Wanneer Microsoft Defender Antivirus in de passieve modus staat, zijn functies voor het herstellen van bedreigingen alleen actief tijdens geplande of on-demand scans.

> [!NOTE]
> [Beveiliging tegen gegevensverlies van Microsoft 365 Endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about) blijft normaal werken wanneer Microsoft Defender Antivirus actief of passief is.

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- In de actieve modus wordt Microsoft Defender Antivirus gebruikt als de antivirus-app op de computer. Alle configuraties die zijn gemaakt met Configuratiebeheer, Groepsbeleid, Intune of andere beheerproducten, zijn van toepassing. Bestanden worden gescand en bedreigingen worden verwijderd en detectiegegevens worden gerapporteerd in uw configuratieprogramma (zoals Configuration Manager of de Microsoft Defender Antivirus-app op de computer zelf).

- In de passieve modus wordt Microsoft Defender Antivirus niet gebruikt als de antivirus-app en worden bedreigingen niet door Microsoft Defender Antivirus gesaneerd. Bestanden worden gescand en rapporten worden geleverd voor bedreigingsdetecties die worden gedeeld met de Microsoft Defender voor Eindpunt-service. Daarom kunt u waarschuwingen tegenkomen in de console van het beveiligingscentrum met Microsoft Defender Antivirus als bron, zelfs wanneer Microsoft Defender Antivirus in de passieve modus staat.

- Wanneer [EDR in de blokmodus](/microsoft-365/security/defender-endpoint/edr-in-block-mode) is ingeschakeld en Microsoft Defender Antivirus niet de primaire antivirusoplossing is, kunnen schadelijke items nog steeds worden gedetecteerd en gesaneerd.

- Wanneer deze is uitgeschakeld, wordt Microsoft Defender Antivirus niet gebruikt als de antivirus-app. Bestanden worden niet gescand en bedreigingen worden niet opgelost. Het uitschakelen/verwijderen van Microsoft Defender Antivirus wordt in het algemeen afgeraden. indien mogelijk, houdt u Microsoft Defender Antivirus in de passieve modus als u een niet-Microsoft-antimalware-/antivirusoplossing gebruikt.

- Als u bent geregistreerd bij Microsoft Defender voor Eindpunt en u een antimalwareproduct van derden gebruikt, is de passieve modus ingeschakeld. [Voor de service is veelvoorkomende informatie](/microsoft-365/security/defender-endpoint/defender-compatibility) delen vereist van de Microsoft Defender Antivirus-service om uw apparaten en netwerk op de juiste manier te kunnen controleren op inbraakpogingen en aanvallen.

- Wanneer Microsoft Defender Antivirus automatisch wordt uitgeschakeld, kan deze automatisch opnieuw worden ingeschakeld als de bescherming die wordt geboden door een niet-Microsoft antivirusproduct verloopt of op andere wijze stopt met het bieden van realtime bescherming tegen virussen, malware of andere bedreigingen. Automatisch opnieuw inschakelen helpt ervoor te zorgen dat antivirusbeveiliging wordt gehandhaafd op uw apparaten. U kunt ook [](limited-periodic-scanning-microsoft-defender-antivirus.md)beperkt periodiek scannen inschakelen, waarbij de Microsoft Defender Antivirus-engine wordt gebruikt om regelmatig te controleren op bedreigingen, naast uw hoofd-antivirus-app.

- Wanneer Microsoft Defender Antivirus in de passieve modus staat, kunt u nog steeds [updates voor Microsoft Defender Antivirus beheren;](manage-updates-baselines-microsoft-defender-antivirus.md) U kunt Microsoft Defender Antivirus echter niet naar de actieve modus verplaatsen als uw apparaten een up-to-date, niet-Microsoft-antivirusproduct hebben dat realtime bescherming biedt tegen malware. Zorg ervoor dat u de [Microsoft Defender Antivirus-beveiliging (Beveiligingsinformatieupdate, Engine](./manage-updates-baselines-microsoft-defender-antivirus.md) en Platform) bijwerkt, zelfs als Microsoft Defender Antivirus actief is in de passieve modus voor optimale beveiliging en detectie.

   Als u het niet-Microsoft-antivirusproduct verwijdert en Microsoft Defender Antivirus gebruikt om uw apparaten te beschermen, keert Microsoft Defender Antivirus automatisch terug naar de normale actieve modus.

> [!WARNING]
> Schakel de bijbehorende services die worden gebruikt door Microsoft Defender Antivirus, Microsoft Defender voor Eindpunt of de Windows Security-app niet uit, stop of wijzig deze niet. Deze aanbeveling omvat *de services en processen wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* of *MsMpEng.* Het handmatig wijzigen van deze services kan ernstige instabiliteit op uw apparaten veroorzaken en uw netwerk kwetsbaar maken. Het uitschakelen, stoppen of wijzigen van deze services kan ook problemen veroorzaken bij het gebruik van niet-Microsoft-antivirusoplossingen en de manier waarop de gegevens worden weergegeven in de [Windows Security-app.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Zie ook

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus op Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR in blokkeringsmodus](edr-in-block-mode.md)
- [Endpoint Protection configureren](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Vals-positieven/-negatieven in Microsoft Defender voor Eindpunt aanpakken](defender-endpoint-false-positives-negatives.md)
- [Meer informatie over preventie van gegevensverlies in Microsoft 365 Endpoint](/microsoft-365/compliance/endpoint-dlp-learn-about)