---
title: Microsoft Defender Antivirus
description: Informatie over het beheren, configureren en gebruiken van Microsoft Defender Antivirus, ingebouwde antimalware- en antivirusbeveiliging.
keywords: Microsoft Defender Antivirus, Windows Defender, antimalware, scep, system center endpoint protection, system center configuration manager, virus, malware, bedreiging, detectie, beveiliging, bescherming
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: ceaf694d8b81e6b06ffe74efc4ad3d4d73471752
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322760"
---
# <a name="microsoft-defender-antivirus-in-windows"></a>Microsoft Defender Antivirus in Windows

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](/microsoft-365/security/defender-endpoint/)

Microsoft Defender Antivirus is een belangrijk onderdeel voor de beveiliging van de volgende generatie in Microsoft Defender voor Eindpunt. Deze beveiliging brengt machine learning, big data-analyse, diepgaand onderzoek naar dreigingsweerstand en de Microsoft-cloudinfrastructuur samen om apparaten (of eindpunten) in je organisatie te beschermen. Microsoft Defender Antivirus is ingebouwd in Windows en werkt met Microsoft Defender voor Eindpunt om beveiliging op je apparaat en in de cloud te bieden. 

## <a name="compatibility-with-other-antivirus-products"></a>Compatibiliteit met andere antivirusproducten

Als je een antivirus-/antimalwareproduct van een andere leverancier dan Microsoft op je apparaat gebruikt, kun je mogelijk Microsoft Defender Antivirus in de passieve modus uitvoeren naast de antivirusoplossing van een andere leverancier dan Microsoft. Dit is afhankelijk van het gebruikte besturingssysteem en of Defender voor Eindpunt is geïmplementeerd op je apparaat. Raadpleeg voor meer informatie [Compatibiliteit van Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).

## <a name="comparing-active-mode-passive-mode-and-disabled-mode"></a>Actieve modus, passieve modus en uitgeschakelde modus vergelijken

In de volgende tabel wordt beschreven wat je kunt verwachten wanneer Microsoft Defender Antivirus in de actieve modus, passieve modus of uitgeschakeld staat.

| Modus  | Wat gebeurt er  |
|---------|---------|
| Actieve modus | In de actieve modus wordt Microsoft Defender Antivirus gebruikt als de primaire antivirusapp op het apparaat. Bestanden worden gescand, bedreigingen worden aangepakt en gedetecteerde bedreigingen worden vermeld in de beveiligingsrapporten van je organisatie en in de Windows-beveiliging-app. |
| Passieve modus | In de passieve modus wordt Microsoft Defender Antivirus niet gebruikt als de primaire antivirusapp op het apparaat. Bestanden worden gescand en gedetecteerde bedreigingen worden gerapporteerd, maar bedreigingen worden niet aangepakt door Microsoft Defender Antivirus.   |
| Uitgeschakeld of verwijderd  | Wanneer Microsoft Defender Antivirus is uitgeschakeld of verwijderd, wordt Microsoft Defender Antivirus niet gebruikt. Bestanden worden niet gescand en bedreigingen worden niet aangepakt. Over het algemeen raden we niet aan om Microsoft Defender Antivirus uit te schakelen of te verwijderen.  |

Raadpleeg voor meer informatie [Compatibiliteit van Microsoft Defender Antivirus](microsoft-defender-antivirus-compatibility.md).

## <a name="check-the-state-of-microsoft-defender-antivirus-on-your-device"></a>Controleer de status van Microsoft Defender Antivirus op je apparaat

Als je de status van Microsoft Defender Antivirus op het apparaat wilt controleren, kun je een van de verschillende methoden gebruiken, zoals de Windows-beveiliging-app of Windows PowerShell.

### <a name="use-the-windows-security-app-to-check-status-of-microsoft-defender-antivirus"></a>De Windows-beveiliging-app gebruiken om de status van Microsoft Defender Antivirus te controleren

1. Selecteer op het Windows-apparaat het Startmenu en begin `Security` te typen. Open vervolgens de Windows-beveiliging-app in de resultaten.

2. Selecteer **Virus- en bedreigingsbeveiliging**.

3. Selecteer onder **Virus- en bedreigingsbeveiliging** de optie **Instellingen beheren**.

Je ziet de naam van je antivirus-/antimalwareoplossing op de instellingenpagina.

### <a name="use-powershell-to-check-status-of-microsoft-defender-antivirus"></a>PowerShell gebruiken om de status van Microsoft Defender Antivirus te controleren

1. Selecteer het Startmenu en begin `PowerShell` te typen. Open vervolgens Windows PowerShell in de resultaten.

2. Typ `Get-MpComputerStatus`.

3. Bekijk in de lijst met resultaten de rij **AMRunningMode**.

   - **Normaal** betekent dat Microsoft Defender Antivirus wordt uitgevoerd in de actieve modus.
   - **Passieve modus** betekent dat Microsoft Defender Antivirus actief is, maar niet het primaire antivirus-/antimalwareproduct op het apparaat is.
   - **EDR-blokkeringsmodus** betekent dat Microsoft Defender Antivirus wordt uitgevoerd en dat een functionaliteit in Microsoft Defender voor Eindpunt die 'EDR-blokkeringsmodus' wordt genoemd, is ingeschakeld. (Raadpleeg [Eindpuntdetectie en -reactie (EDR) in blokkeringsmodus](edr-in-block-mode.md).)
   - **De passieve SxS-modus** betekent dat Microsoft Defender Antivirus wordt uitgevoerd in de passieve modus naast een ander antivirus-/antimalwareproduct en dat Microsoft Defender voor Eindpunt niet op je apparaat is geïmplementeerd. In dat geval wordt beperkt periodiek scannen gebruikt voor Microsoft Defender Antivirus. Raadpleeg voor meer informatie [Beperkt periodiek scannen gebruiken in Microsoft Defender Antivirus](limited-periodic-scanning-microsoft-defender-antivirus.md).

Raadpleeg voor meer informatie over Get-MpComputerStatus PowerShell cmdlet het referentieartikel [Get-MpComputerStatus](/powershell/module/defender/get-mpcomputerstatus).

## <a name="get-your-antivirusantimalware-platform-updates"></a>Updates voor je antivirus- en antimalwareplatform downloaden

Het is belangrijk om Microsoft Defender Antivirus of een andere antivirus-/antimalwareoplossing up-to-date te houden. Microsoft brengt regelmatig updates uit om ervoor te zorgen dat je apparaten over de nieuwste technologie beschikken ter bescherming tegen nieuwe malware en aanvalstechnieken. Raadpleeg voor meer informatie [Updates voor Microsoft Defender Antivirus beheren en basislijnen toepassen](manage-updates-baselines-microsoft-defender-antivirus.md). 

## <a name="see-also"></a>Zie ook

- [Microsoft Defender Antivirus op Windows Server](microsoft-defender-antivirus-on-windows-server.md)
- [Beheer en configuratie van Microsoft Defender Antivirus](configuration-management-reference-microsoft-defender-antivirus.md)
- [Microsoft Defender Antivirusbeveiliging evalueren](evaluate-microsoft-defender-antivirus.md)
