---
title: Plan regelmatig snelle en volledige scans met Microsoft Defender Antivirus
description: Terugkerende (geplande) scans instellen, inclusief wanneer ze moeten worden uitgevoerd en of ze als volledige of snelle scans moeten worden uitgevoerd
keywords: quick scan, full scan, quick vs full, schedule scan, daily, weekly, time, scheduled, recurring, regular
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 06/09/2021
ms.reviewer: pauhijbr, ksarens
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 5566050e4a64713f6f8b4ac2cb4a7188d3a241c8
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879684"
---
# <a name="configure-scheduled-quick-or-full-microsoft-defender-antivirus-scans"></a>Geplande snelle of volledige Microsoft Defender Antivirus-scans configureren

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Naast always-on, realtime beveiliging en [on-demand](run-scan-microsoft-defender-antivirus.md) antivirusscans, kunt u regelmatig geplande antivirusscans instellen. U kunt het type scan configureren, wanneer de scan moet [](manage-protection-updates-microsoft-defender-antivirus.md) plaatsvinden en of de scan moet plaatsvinden na een beveiligingsupdate of wanneer er geen eindpunt wordt gebruikt. U kunt ook speciale scans instellen om herstelacties zo nodig te voltooien.

## <a name="what-do-you-want-to-do"></a>Wat wilt u doen?

- [Meer informatie over snelle scans, volledige scans en aangepaste scans](#quick-scan-full-scan-and-custom-scan)
- [Groepsbeleid gebruiken om antivirusscans te plannen](schedule-antivirus-scans-group-policy.md)
- [Gebruik Windows PowerShell om antivirusscans te plannen](schedule-antivirus-scans-powershell.md)
- [Gebruik Windows Management Instrumentation om antivirusscans te plannen](schedule-antivirus-scans-wmi.md)

## <a name="keep-the-following-points-in-mind"></a>Houd rekening met de volgende punten

- Standaard wordt Microsoft Defender Antivirus 15 minuten vóór de tijd van geplande scans gecontroleerd op een update. U kunt [de planning beheren voor wanneer beveiligingsupdates moeten worden gedownload](manage-protection-update-schedule-microsoft-defender-antivirus.md) en toegepast om deze standaard te overschrijven. 

- Als een apparaat wordt losgekoppeld en op de batterij wordt uitgevoerd tijdens een geplande volledige scan, stopt de geplande scan met gebeurtenis 1002, waarin staat dat de scan is gestopt vóór voltooiing. Microsoft Defender Antivirus wordt op de volgende geplande tijd een volledige scan uitgevoerd.

## <a name="quick-scan-full-scan-and-custom-scan"></a>Snelle scan, volledige scan en aangepaste scan

Wanneer u geplande scans in stelt, kunt u opgeven of de scan een volledige scan of een snelle scan moet zijn. In de meeste gevallen wordt een snelle scan aanbevolen. 

| Snelle scan  | Volledige scan  | Aangepaste scan |
|---------|---------|---------|
| (Aanbevolen) Een snelle scan bekijkt alle locaties waar malware kan zijn geregistreerd om te beginnen met het systeem, zoals registersleutels en bekende Windows opstartmappen. <p>Gecombineerd met altijd-aan, realtime beveiliging, die bestanden controleert wanneer ze worden geopend en gesloten, en wanneer een gebruiker naar een map navigeert, biedt een snelle scan een sterke bescherming tegen malware die begint met malware op systeem- en kernelniveau. <p>In de meeste gevallen is een snelle scan voldoende en is dit de aanbevolen optie voor geplande scans. | Een volledige scan begint met een snelle scan en gaat vervolgens verder met een sequentiële bestandsscan van alle vaste schijven en verwisselbare/netwerkstations (als de volledige scan is geconfigureerd om dit te doen). <p>Een volledige scan kan enkele uren of dagen duren, afhankelijk van de hoeveelheid en het type gegevens dat moet worden gescand.<p>Wanneer de volledige scan is voltooid, is er nieuwe beveiligingsinformatie beschikbaar en is er een nieuwe scan vereist om ervoor te zorgen dat er geen andere bedreigingen worden gedetecteerd met de nieuwe beveiligingsintelligentie. <p>Vanwege de tijd en resources die betrokken zijn bij een volledige scan, wordt in het algemeen niet aangeraden volledige scans te plannen.  | Een aangepaste scan is een snelle scan die wordt uitgevoerd op de bestanden en mappen die u opgeeft. U kunt er bijvoorbeeld voor kiezen om een USB-station of een specifieke map op het lokale station van uw apparaat te scannen. <p> | 

> [!NOTE]
> Standaard worden snelle scans uitgevoerd op geïnstalleerde verwisselbare apparaten, zoals USB-stations.

## <a name="how-do-i-know-which-scan-type-to-choose"></a>Hoe weet ik welk scantype ik moet kiezen?

Gebruik de volgende tabel om een scantype te kiezen.

| Scenario  | Aanbevolen scantype  |
|---------|---------|
| U wilt normale, geplande scans instellen     | Snelle scan <p>Met een snelle scan worden de processen, het geheugen, de profielen en bepaalde locaties op het apparaat gecontroleerd. In combinatie [met realtime-beveiliging](configure-real-time-protection-microsoft-defender-antivirus.md)die altijd wordt gebruikt, biedt een snelle scan een sterke dekking voor malware die begint met het systeem en malware op kernelniveau. Realtime beveiliging controleert bestanden wanneer ze worden geopend en gesloten en wanneer een gebruiker naar een map navigeert.         |
| Bedreigingen, zoals malware, worden gedetecteerd op een afzonderlijk apparaat     | Snelle scan <p>In de meeste gevallen wordt met een snelle scan gedetecteerde malware gedetecteerd en verwijderd.   |
| U wilt een [scan op aanvraag uitvoeren](run-scan-microsoft-defender-antivirus.md)     | Snelle scan       |
| U wilt ervoor zorgen dat een draagbaar apparaat, zoals een USB-station, geen malware bevat | Aangepaste scan <p>Met een aangepaste scan kunt u specifieke locaties, mappen of bestanden selecteren en wordt een snelle scan uitgevoerd. |

## <a name="what-else-do-i-need-to-know-about-quick-and-full-scans"></a>Wat moet ik nog meer weten over snelle en volledige scans?

- Schadelijke bestanden kunnen worden opgeslagen op locaties die niet zijn opgenomen in een snelle scan. In realtime-beveiliging worden echter alle bestanden die worden geopend en gesloten, en alle bestanden in mappen die door een gebruiker worden geopend, gereviewd. De combinatie van realtimebeveiliging en een snelle scan biedt een sterke bescherming tegen malware.

- On-access protection with [cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) help ensure that all the files accessed on the system are being scand with the latest security intelligence and cloud machine learning models.

- Wanneer realtimebeveiliging malware detecteert en de omvang van de getroffen bestanden in eerste instantie niet wordt bepaald, wordt Microsoft Defender Antivirus een volledige scan gestart als onderdeel van het herstelproces.

- Met een volledige scan kunnen schadelijke bestanden worden gedetecteerd die niet zijn gedetecteerd door andere scans, zoals een snelle scan. Een volledige scan kan echter even duren en kostbare systeembronnen gebruiken om deze te voltooien.

- Als een apparaat langere tijd offline is, kan het langer duren om een volledige scan te voltooien. 

