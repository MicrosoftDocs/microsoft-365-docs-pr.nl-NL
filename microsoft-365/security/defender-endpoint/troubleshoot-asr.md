---
title: Problemen met regels voor het verminderen van de surface-aanval oplossen
description: Resources en voorbeeldcode voor het oplossen van problemen met regels voor het verminderen van de surface attack in Microsoft Defender voor Eindpunt.
keywords: probleemoplossing, fout, fix, windows defender, asr, regels, hips, troubleshoot, audit, exclusion, false positive, broken, blocking, microsoft defender for endpoint, microsoft defender advanced threat protection
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.date: 03/27/2019
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: d483c098f221e2d4d2e61a10393154b8f5d1498d
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198739"
---
# <a name="troubleshoot-attack-surface-reduction-rules"></a>Problemen met regels voor het verminderen van aanvallen oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


Wanneer u de [surface reduction-regels voor](attack-surface-reduction.md) aanvallen gebruikt, kunnen er problemen zijn, zoals:

- Een regel blokkeert een bestand, proces of voert een andere actie uit die niet mag worden uitgevoerd (onwaar positief)

- Een regel werkt niet zoals beschreven, of blokkeert geen bestand of proces dat moet worden gebruikt (onwaar negatief)

Er zijn vier stappen om deze problemen op te lossen:

1. [Vereisten bevestigen](#confirm-prerequisites)

2. [Controlemodus gebruiken om de regel te testen](#use-audit-mode-to-test-the-rule)

3. [Uitsluitingen toevoegen voor de opgegeven regel](#add-exclusions-for-a-false-positive) (voor onwaar-positieven)

4. [Ondersteuningslogboeken verzenden](#collect-diagnostic-data-for-file-submissions)

## <a name="confirm-prerequisites"></a>Vereisten bevestigen

Surface Reduction-regels voor aanvallen werken alleen op apparaten met de volgende voorwaarden:

- Eindpunten worden uitgevoerd met Windows 10 Enterprise, versie 1709 (ook wel de Fall Creators Update genoemd).

- Eindpunten gebruiken Microsoft Defender Antivirus als de enige antivirusbeveiligings-app. [Als u een andere antivirus-app gebruikt,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)kan Microsoft Defender AV zichzelf uitschakelen.

- [Realtime beveiliging](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus) is ingeschakeld.

- Controlemodus is niet ingeschakeld. Gebruik Groepsbeleid om de regel in te stellen **op Uitgeschakeld** (waarde: **0**) zoals beschreven in [Surface reduction rules voor aanvallen inschakelen.](enable-attack-surface-reduction.md)

Als aan deze vereisten is voldaan, gaat u verder met de volgende stap om de regel in de auditmodus te testen.

## <a name="use-audit-mode-to-test-the-rule"></a>Controlemodus gebruiken om de regel te testen

U kunt naar de website van Windows Defender Test ground bij [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) gaan om te bevestigen dat regels voor het verminderen van aanvallen over het algemeen werken voor vooraf geconfigureerde scenario's en processen op een apparaat, of u kunt de auditmodus gebruiken, zodat alleen regels kunnen worden gemeld.

Volg deze instructies in [Het demoprogramma gebruiken](evaluate-attack-surface-reduction.md) om te zien hoe regels voor het verminderen van aanvallen werken om de specifieke regel te testen waarmee u problemen ondervindt.

1. Schakel de auditmodus in voor de specifieke regel die u wilt testen. Gebruik Groepsbeleid om de regel in te stellen op **de auditmodus** (waarde: **2)** zoals beschreven in Regels voor het inschakelen van de [surface reduction van aanvallen.](enable-attack-surface-reduction.md) Met de controlemodus kan de regel het bestand of proces rapporteren, maar kan deze nog steeds worden uitgevoerd.

2. Voer de activiteit uit die een probleem veroorzaakt (bijvoorbeeld het bestand of proces openen of uitvoeren dat moet worden geblokkeerd, maar wordt toegestaan).

3. [Bekijk de gebeurtenislogboeken van](attack-surface-reduction.md) de attack surface reduction rule om te zien of de regel het bestand of proces zou hebben geblokkeerd als de regel was ingesteld op **Ingeschakeld.**

Als een regel een bestand of proces dat u verwacht, niet blokkeert, controleert u eerst of de auditmodus is ingeschakeld.

De auditmodus is mogelijk ingeschakeld voor het testen van een andere functie, of door een geautomatiseerd PowerShell-script, en is mogelijk niet uitgeschakeld nadat de tests zijn voltooid.

Als u de regel hebt getest met het demoprogramma en met de auditmodus en de regels voor de beperking van de aanvalsoppervlakken werken aan vooraf geconfigureerde scenario's, maar de regel werkt niet zoals verwacht, gaat u naar een van de volgende secties op basis van uw situatie:

1. Als de surface reduction-regel voor aanvallen iets blokkeert dat niet mag worden geblokkeerd (ook wel een onwaar positief genoemd), kunt u eerst een uitsluitingsregel voor de beperking van het oppervlak van de aanval [toevoegen.](#add-exclusions-for-a-false-positive)

2. Als de surface reduction-regel van de aanval niet iets blokkeert dat moet worden geblokkeerd (ook wel een onwaar negatief genoemd), kunt u direct verdergaan met de laatste stap, diagnostische gegevens verzamelen en het probleem bij ons [indienen.](#collect-diagnostic-data-for-file-submissions)

## <a name="add-exclusions-for-a-false-positive"></a>Uitsluitingen toevoegen voor een onwaar positief

Als de surface reduction-regel van de aanval iets blokkeert dat niet mag worden geblokkeerd (ook wel een onwaar positief genoemd), kunt u uitsluitingen toevoegen om te voorkomen dat regels voor het verminderen van aanvallen de uitgesloten bestanden of mappen evalueren.

Zie Surface reduction aanpassen om een uitsluiting [toe te voegen.](customize-attack-surface-reduction.md)

>[!IMPORTANT]
>U kunt afzonderlijke bestanden en mappen opgeven die moeten worden uitgesloten, maar u kunt geen afzonderlijke regels opgeven.
>Dit betekent dat alle bestanden of mappen die zijn uitgesloten, worden uitgesloten van alle ASR-regels.

## <a name="report-a-false-positive-or-false-negative"></a>Een onwaar positief of onwaar negatief rapporteren

Gebruik het [webinzendingsformulier](https://www.microsoft.com/wdsi/filesubmission) van Windows Defender Security Intelligence om een onwaar negatief of onwaar positief voor netwerkbeveiliging te melden. Met een Windows E5-abonnement kunt u ook een koppeling naar [een bijbehorende waarschuwing geven.](alerts-queue.md)

## <a name="collect-diagnostic-data-for-file-submissions"></a>Diagnostische gegevens verzamelen voor bestandsinzendingen

Wanneer u een probleem rapporteert met regels voor het verminderen van de surface attack, wordt u gevraagd diagnostische gegevens te verzamelen en in te dienen die kunnen worden gebruikt door ondersteunings- en technische teams van Microsoft om problemen op te lossen.

1. Open een opdrachtprompt met verhoogde opdracht en wijzig in de Windows Defender-adreslijst:

   ```console
   cd "c:\program files\windows defender"
   ```

2. Voer deze opdracht uit om de diagnostische logboeken te genereren:

   ```console
   mpcmdrun -getfiles
   ```

3. Standaard worden ze opgeslagen in `C:\ProgramData\Microsoft\Windows Defender\Support\MpSupportFiles.cab` . Voeg het bestand toe aan het inzendingsformulier.

## <a name="related-articles"></a>Verwante artikelen

- [Surface Reduction-regels voor aanvallen](attack-surface-reduction.md)

- [Regels voor het verlagen van de surface voor aanvallen inschakelen](enable-attack-surface-reduction.md)

- [Regels voor het verlagen van het oppervlak van de aanval evalueren](evaluate-attack-surface-reduction.md)
