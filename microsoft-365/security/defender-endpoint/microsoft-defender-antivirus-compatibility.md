---
title: Microsoft Defender Antivirus compatibiliteit met andere beveiligingsproducten
description: Meer informatie Microsoft Defender Antivirus met andere beveiligingsproducten en de besturingssystemen.
keywords: Windows Defender, Defender voor eindpunt, volgende generatie, antivirus, compatibiliteit, passieve modus
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 05/08/2021
ms.openlocfilehash: e4675626e9debf3ef3a295f7c797ac254e82395f
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926017"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender Antivirus compatibiliteit

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>Samenvatting

Microsoft Defender Antivirus wordt automatisch ingeschakeld en geïnstalleerd op eindpunten en apparaten die Windows 10. Maar wat gebeurt er als er een andere antivirus-/antimalwareoplossing (niet van Microsoft) wordt gebruikt? Dit hangt af van of u [Microsoft Defender](microsoft-defender-endpoint.md) voor eindpunt gebruikt samen met uw antivirusbeveiliging. In dit artikel wordt beschreven wat er gebeurt met antivirus-/antimalwareoplossingen wanneer eindpunten zijn onboarded bij Microsoft Defender voor Eindpunt.

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- In de actieve modus wordt Microsoft Defender Antivirus gebruikt als de antivirus-app op de computer. Alle configuraties die zijn gemaakt met Configuratiebeheer, Groepsbeleid, Intune of andere beheerproducten, zijn van toepassing. Bestanden worden gescand en bedreigingen worden verwijderd en detectiegegevens worden gerapporteerd in uw configuratieprogramma (zoals Configuration Manager of de Microsoft Defender Antivirus app op de computer zelf).

- In de passieve modus wordt Microsoft Defender Antivirus niet gebruikt als de antivirus-app en worden bedreigingen niet door de Microsoft Defender Antivirus. Bestanden worden gescand en rapporten worden geleverd voor bedreigingsdetecties die worden gedeeld met de Microsoft Defender voor Eindpunt-service. Mogelijk ziet u waarschuwingen in [het beveiligingscentrum](microsoft-defender-security-center.md) met Microsoft Defender Antivirus als bron, zelfs wanneer Microsoft Defender Antivirus in de passieve modus staat.

- Wanneer [EDR in de](edr-in-block-mode.md) blokmodus is ingeschakeld en Microsoft Defender Antivirus niet de primaire antivirusoplossing is, worden schadelijke items gedetecteerd en gesaneerd. EDR in de blokmodus moet Microsoft Defender Antivirus zijn ingeschakeld in de actieve of passieve modus.

- Wanneer deze is uitgeschakeld, Microsoft Defender Antivirus niet gebruikt als de antivirus-app. Bestanden worden niet gescand en bedreigingen worden niet opgelost. Het uitschakelen of verwijderen van Microsoft Defender Antivirus wordt in het algemeen afgeraden. als dit mogelijk is, Microsoft Defender Antivirus in de passieve modus als u een niet-Microsoft-antimalware-/antivirusoplossing gebruikt.

- Als u bent geregistreerd bij Microsoft Defender voor Eindpunt en u een antimalwareproduct van derden gebruikt, is de passieve modus ingeschakeld. Voor de service is veelvoorkomende informatie delen Microsoft Defender Antivirus service vereist om uw apparaten en netwerk goed te kunnen controleren op inbraakpogingen en aanvallen. Zie voor meer informatie [Microsoft Defender Antivirus compatibiliteit met Microsoft Defender voor Eindpunt.](defender-compatibility.md) 

- Wanneer Microsoft Defender Antivirus in de passieve modus staat, kunt u nog steeds [updates](manage-updates-baselines-microsoft-defender-antivirus.md)voor Microsoft Defender Antivirus; U kunt de Microsoft Defender Antivirus echter niet verplaatsen naar de actieve modus als uw apparaten een up-to-date, niet-Microsoft-antivirusproduct hebben dat realtime bescherming biedt tegen malware. Zorg ervoor dat u de Microsoft Defender Antivirus-beveiliging (Beveiligingsintelligentieupdate, Engine en [Platform)](manage-updates-baselines-microsoft-defender-antivirus.md) bijwerkt, zelfs als Microsoft Defender Antivirus in de passieve modus wordt uitgevoerd.

- Wanneer Microsoft Defender Antivirus automatisch is uitgeschakeld, kan deze automatisch opnieuw worden ingeschakeld als de bescherming die wordt geboden door een niet-Microsoft-antivirusproduct verloopt of op andere wijze stopt met het bieden van realtime bescherming tegen virussen, malware of andere bedreigingen. Automatisch opnieuw inschakelen helpt ervoor te zorgen dat antivirusbeveiliging wordt gehandhaafd op uw apparaten. U kunt ook [](limited-periodic-scanning-microsoft-defender-antivirus.md)beperkt periodiek scannen inschakelen, waarbij de Microsoft Defender Antivirus wordt gebruikt om regelmatig te controleren op bedreigingen, naast uw hoofd-antivirus-app.

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender Antivirus en niet-Microsoft antivirus-/antimalware-oplossingen

In de volgende tabel wordt samengevat wat er gebeurt met Microsoft Defender Antivirus wanneer niet-Microsoft antivirus-/antimalware-oplossingen samen of zonder Microsoft Defender voor Eindpunt worden gebruikt. 

| Windows versie   | Antivirus-/antimalwareoplossing  | Onboarded to <br/> Defender voor Eindpunt? | Microsoft Defender Antivirus staat     |
|------|------|-------|-------|
| Windows 10  | Microsoft Defender Antivirus | Ja  | Actieve modus | 
| Windows 10  | Microsoft Defender Antivirus | Nee   | Actieve modus |
| Windows 10  | Een niet-Microsoft-antivirus-/antimalwareoplossing | Ja  | Passieve modus (automatisch) |
| Windows 10  | Een niet-Microsoft-antivirus-/antimalwareoplossing | Nee   | Uitgeschakelde modus (automatisch)    |
| Windows Server, versie 1803 of hoger <p> Windows Server 2019 | Microsoft Defender Antivirus  | Ja |         Actieve modus  |
| Windows Server, versie 1803 of hoger <p> Windows Server 2019 | Microsoft Defender Antivirus | Nee  | Actieve modus |
| Windows Server, versie 1803 of hoger <p> Windows Server 2019 | Een niet-Microsoft-antivirus-/antimalwareoplossing | Ja  | Microsoft Defender Antivirus moet zijn ingesteld op passieve modus (handmatig) <sup> [[1](#fn1)]<sup>  | 
| Windows Server, versie 1803 of hoger <p> Windows Server 2019 | Een niet-Microsoft-antivirus-/antimalwareoplossing | Nee  | Microsoft Defender Antivirus moet worden uitgeschakeld (handmatig) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server 2016 | Microsoft Defender Antivirus | Ja | Actieve modus |
| Windows Server 2016 | Microsoft Defender Antivirus | Nee | Actieve modus |
| Windows Server 2016 | Een niet-Microsoft-antivirus-/antimalwareoplossing | Ja | Microsoft Defender Antivirus moet worden uitgeschakeld (handmatig) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Een niet-Microsoft-antivirus-/antimalwareoplossing | Nee | Microsoft Defender Antivirus moet worden uitgeschakeld (handmatig) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1</a>) Op Windows Server, versie 1803 of hoger of Windows Server 2019 voert Microsoft Defender Antivirus niet automatisch de passieve modus in wanneer u een niet-Microsoft-antivirusproduct installeert. Stel in dat geval de Microsoft Defender Antivirus passieve [modus in](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) om problemen te voorkomen die worden veroorzaakt doordat meerdere antivirusproducten op een server zijn geïnstalleerd. U kunt de Microsoft Defender Antivirus passieve modus instellen met PowerShell, Groepsbeleid of een registersleutel.

Als u Windows Server, versie 1803 of hoger of Windows Server 2019 gebruikt, kunt u Microsoft Defender Antivirus instellen op passieve modus door de volgende registersleutel in te stellen:
- Pad: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- Naam: `ForceDefenderPassiveMode`
- Typ: `REG_DWORD`
- Waarde: `1`

> [!NOTE]
> Passieve modus wordt niet ondersteund op Windows Server 2016. De `ForcePassiveMode` registersleutel kan worden gebruikt op Windows Server, versie 1803 of hoger of Windows Server 2019, maar niet Windows Server 2016. 

(<a id="fn2">2</a>) Als Windows Server 2016 antivirusproduct van niet-Microsoft gebruikt, kunt u Microsoft Defender Antivirus passieve modus of actieve modus niet uitvoeren. In dergelijke gevallen [kunt u de](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) Microsoft Defender Antivirus handmatig uitschakelen of verwijderen om problemen te voorkomen die worden veroorzaakt doordat meerdere antivirusproducten op een server zijn geïnstalleerd.

Zie [Microsoft Defender Antivirus op Windows Server](microsoft-defender-antivirus-on-windows-server.md) voor belangrijke verschillen en beheeropties voor Windows Server-installaties.

> [!IMPORTANT]
> Microsoft Defender Antivirus is alleen beschikbaar op apparaten met Windows 10, Windows Server 2016, Windows Server, versie 1803 of hoger en Windows Server 2019.
>
> In Windows 8.1 en Windows Server 2012 wordt antivirusbeveiliging op ondernemingsniveau aangeboden als System Center Endpoint Protection [,](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))die wordt beheerd via Microsoft Endpoint Configuration Manager.
>
> Windows Defender wordt ook aangeboden voor consumentenapparaten op [Windows 8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)en Windows Server 2012, maar biedt geen ondernemingsbeheer (of een interface op Windows Server 2012 Server Core-installaties).

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>Hoe Microsoft Defender Antivirus van invloed is op de functionaliteit van Defender voor eindpunten

De tabel in deze sectie bevat een overzicht van de functionaliteit en functies die beschikbaar zijn in elke status. De tabel is alleen bedoeld als informatief. Het is bedoeld om de functies & functies te beschrijven die actief werken of niet, afhankelijk van of Microsoft Defender Antivirus zich in de actieve modus, in passieve modus of uitgeschakeld/verwijderd. 

> [!IMPORTANT]
> Schakel geen mogelijkheden uit, zoals realtime beveiliging, beveiliging in de cloud of beperkt periodiek scannen, als u Microsoft Defender Antivirus gebruikt in de passieve modus of als u EDR gebruikt in de blokmodus. 

|Beveiliging |Actieve modus |Passieve modus |EDR in blokkeringsmodus |Uitgeschakeld of verwijderd |
|:---|:---|:---|:---|:---|
| [Realtime beveiliging en](configure-real-time-protection-microsoft-defender-antivirus.md) [beveiliging in de cloud](enable-cloud-protection-microsoft-defender-antivirus.md) | Ja | Nee <sup> [[3](#fn3)]<sup> | Nee | Nee |
| [Beperkte beschikbaarheid van periodiek scannen](limited-periodic-scanning-microsoft-defender-antivirus.md) | Nee | Nee | Nee | Ja |
| [Gegevens over het scannen en opsporen van bestanden](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nee |
|  [Herstel van bedreigingen](configure-remediation-microsoft-defender-antivirus.md) | Ja | Zie opmerking <sup> [[4](#fn4)]<sup> | Ja | Nee |
| [Beveiligingsintelligentie-updates](manage-updates-baselines-microsoft-defender-antivirus.md) | Ja | Ja | Ja | Nee |

(<a id="fn3">3</a>) Wanneer Microsoft Defender Antivirus in de passieve modus is, biedt realtimebeveiliging over het algemeen geen blokkering of afdwinging, ook al is deze ingeschakeld en in de passieve modus. 

(<a id="fn4">4</a>) Wanneer Microsoft Defender Antivirus in de passieve modus is, zijn functies voor het herstellen van bedreigingen alleen actief tijdens geplande of on-demand scans.

> [!NOTE]
> [Microsoft 365 bescherming tegen](/microsoft-365/compliance/endpoint-dlp-learn-about) gegevensverlies van eindpunten blijft normaal werken wanneer Microsoft Defender Antivirus actief of passief is.

## <a name="why-defender-for-endpoint-matters"></a>Waarom Defender voor Eindpunt belangrijk is

Overweeg om uw eindpunten te onboarden bij Defender voor Eindpunt, zelfs als u een niet-Microsoft-antivirus-/antimalware-oplossing gebruikt. In de meeste gevallen kunt u, wanneer u uw apparaten aan boord van uw apparaten bij Defender voor Eindpunt, Microsoft Defender Antivirus naast uw niet-Microsoft-antivirusoplossing gebruiken voor extra beveiliging. U kunt bijvoorbeeld EDR [in](edr-in-block-mode.md)de blokmodus gebruiken, waarmee schadelijke artefacten worden geblokkeerd en gesaneerd die mogelijk door uw primaire antivirusoplossing zijn gemist. 

Dit werkt als volgende:

- Als de clientapparaten van uw organisatie zijn beveiligd door een niet-Microsoft-antivirus-/antimwalware-oplossing, gaat Microsoft Defender Antivirus automatisch in de passieve modus wanneer deze apparaten zijn onboarded bij Defender for Endpoint. In dit geval vinden bedreigingsdetecties plaats, maar worden realtime beveiliging en bedreigingen niet door de Microsoft Defender Antivirus. **OPMERKING:** Dit specifieke scenario is niet van toepassing op eindpunten met Windows Server.

- Als de clientapparaten van uw organisatie zijn beveiligd door een niet-Microsoft antivirus-/antimalware-oplossing en deze apparaten niet zijn onboarded bij Microsoft Defender voor Eindpunt, wordt Microsoft Defender Antivirus automatisch in uitgeschakelde modus. In dit geval worden bedreigingen niet gedetecteerd of door de Microsoft Defender Antivirus. **OPMERKING:** Dit specifieke scenario is niet van toepassing op eindpunten met Windows Server.

- Als de eindpunten van uw organisatie Windows Server worden uitgevoerd en deze eindpunten worden beveiligd door een niet-Microsoft-antivirus-/antimalware-oplossing, gaan Microsoft Defender Antivirus niet automatisch in de passieve modus of de uitgeschakelde modus wanneer deze eindpunten zijn aan boord van Defender voor Endpoint. In dit specifieke scenario moet u de Windows Server-eindpunten op de juiste manier configureren. 

   - Op Windows Server, versie 1803 of hoger en Windows Server 2019 kunt u instellen dat Microsoft Defender Antivirus in passieve modus wordt uitgevoerd. 
   - Op Windows Server 2016 moet Microsoft Defender Antivirus uitgeschakeld zijn (passieve modus wordt niet ondersteund op Windows Server 2016).

- Als de eindpunten van uw organisatie zijn beveiligd door een niet-Microsoft-antivirus-/antimalware-oplossing, wanneer deze apparaten zijn onboarded bij Defender voor Eindpunt met [EDR in](/microsoft-365/security/defender-endpoint/edr-in-block-mode) de blokmodus ingeschakeld, blokkeert en herstelt Defender voor Eindpunt schadelijke artefacten. **OPMERKING:** Dit specifieke scenario is niet van toepassing op Windows Server 2016. EDR in de blokmodus moet Microsoft Defender Antivirus zijn ingeschakeld in de actieve of passieve modus.


> [!WARNING]
> Schakel de bijbehorende services die worden gebruikt door Microsoft Defender Antivirus, Microsoft Defender voor Eindpunt of de app Windows-beveiliging niet uit, stop of wijzig deze niet. Deze aanbeveling omvat *de services en processen wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* of *MsMpEng.* Het handmatig wijzigen van deze services kan ernstige instabiliteit op uw apparaten veroorzaken en uw netwerk kwetsbaar maken. Het uitschakelen, stoppen of wijzigen van deze services kan ook problemen veroorzaken bij het gebruik van niet-Microsoft-antivirusoplossingen en de manier waarop de gegevens worden weergegeven in de Windows-beveiliging [app.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>Zie ook

- [Microsoft Defender Antivirus in Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Microsoft Defender Antivirus op Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [EDR in blokkeringsmodus](edr-in-block-mode.md)
- [Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Actie ondernemen voor fout-positieven/-negatieven in Microsoft Defender voor Eindpunt](defender-endpoint-false-positives-negatives.md)
- [Meer informatie over Microsoft 365 Eindpunt-DLP](/microsoft-365/compliance/endpoint-dlp-learn-about)
