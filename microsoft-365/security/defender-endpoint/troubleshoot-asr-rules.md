---
title: Microsoft Defender voor endpoint ASR-regels rapporteren en oplossen
description: In dit onderwerp wordt beschreven hoe u Microsoft Defender voor Endpoint ASR-regels kunt rapporteren en oplossen
keywords: Attack surface reduction rules, asr, hips, host intrusion prevention system, protection rules, anti-exploit, anti-exploit, exploit, infection prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246059"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>Microsoft Defender voor ATP ASR-regels rapporteren en oplossen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**

- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Het Microsoft 365 beveiligingscentrum is de nieuwe interface voor het bewaken en beheren van beveiliging in uw Microsoft-identiteiten, gegevens, apparaten, apps en infrastructuur. Hier kunt u eenvoudig de beveiligingstoestand van uw organisatie bekijken, in actie komen om apparaten, gebruikers en apps te configureren en waarschuwingen voor verdachte activiteiten te ontvangen. Het Microsoft 365 beveiligingscentrum is bedoeld voor beveiligingsbeheerders en beveiligingsbewerkingsteams om hun organisatie beter te beheren en te beveiligen. Ga naar het Microsoft 365 beveiligingscentrum op https://security.microsoft.com .
In Microsoft 365 beveiligingscentrum bieden we u een volledig overzicht van de huidige configuratie en gebeurtenissen van ASR-regels in uw domein. Houd er rekening mee dat uw apparaten moeten zijn aangesloten bij de Microsoft Defender voor Eindpunt-service om deze rapporten in te vullen.
Hier is een schermafbeelding van het Microsoft 365 beveiligingscentrum (onder **Reports**  >  **Devices**  >  **Attack surface reduction**). Selecteer Configuratie op apparaatniveau **in het** deelvenster Surface Reduction Rules **van Attack.** Het volgende scherm wordt weergegeven, waarin u een specifiek apparaat kunt selecteren en de afzonderlijke ASR-regelconfiguratie kunt controleren.

:::image type="content" source="images/asrrulesnew.png" alt-text="SCHERM ASR-regels":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender for Endpoint – Advanced hunting

Een van de krachtigste functies van Microsoft Defender voor Eindpunt is geavanceerd zoeken. Als u niet bekend bent met geavanceerde jacht, verwijst u proactief [naar bedreigingen met geavanceerde jacht.](advanced-hunting-overview.md)

Advanced hunting is een op query's gebaseerd (Kusto Query Language) threat-hunting tool waarmee u tot 30 dagen van de vastgelegde (onbewerkte) gegevens kunt verkennen, die MDE Endpoint Detection and Response (EDR) van al uw machines verzamelt. Door middel van geavanceerde jacht kunt u gebeurtenissen proactief controleren om interessante indicatoren en entiteiten te vinden. De flexibele toegang tot gegevens helpt ongebreideld zoeken naar bekende en potentiële bedreigingen.

Door middel van geavanceerd zoeken is het mogelijk om ASR-regelsgegevens op te halen, rapporten te maken en uitgebreide informatie te krijgen over de context van een bepaalde ASR-regelcontrole of -gebeurtenis te blokkeren.

Asr-regels kunnen worden opgevraagd in de tabel DeviceEvents in de geavanceerde sectie van de Microsoft Defender-beveiligingscentrum. Een eenvoudige query, zoals de onderstaande, kan bijvoorbeeld alle gebeurtenissen met ASR-regels als gegevensbron rapporteren voor de laatste 30 dagen en deze samenvatten met het aantal ActionType's, dat in dit geval de werkelijke codenaam van de ASR-regel is.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Geavanceerde zoekquery":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="geavanceerd zoekscherm":::

Met geavanceerd zoeken kunt u de query's naar wens vorm geven, zodat u kunt zien wat er gebeurt, ongeacht of u iets op een afzonderlijke computer wilt aanwijzen of dat u inzichten uit uw hele omgeving wilt halen.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Tijdlijn van Microsoft Defender voor eindpunten

Een alternatief voor geavanceerd zoeken, maar met een kleiner bereik, is de tijdlijn van microsoft Defender voor eindpunten. U kunt alle verzamelde gebeurtenissen van een apparaat bekijken, de afgelopen zes maanden, in de Microsoft Defender-beveiligingscentrum, door naar de lijst Machines te gaan, een bepaalde computer te selecteren en vervolgens op het tabblad Tijdlijn te klikken.

Hieronder ziet u een schermafbeelding van de tijdlijnweergave van deze gebeurtenissen op een bepaald eindpunt.  In deze weergave kunt u de lijst met gebeurtenissen filteren op basis van een van de gebeurtenisgroepen in het rechterdeelvenster. U kunt vlaggeveerde en uitgebreide gebeurtenissen ook in- of uitschakelen tijdens het weergeven van waarschuwingen en het scrollen door de historische tijdlijn.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="tijdlijn van het Microsoft Defender-beveiligingscentrum":::

## <a name="how-to-troubleshoot-asr-rules"></a>Problemen met ASR-regels oplossen?

De eerste en meest directe manier is om lokaal op een Windows-apparaat te controleren welke ASR-regels zijn ingeschakeld (en de configuratie) met behulp van de PowerShell-cmdlets.

Hier volgen enkele andere informatiebronnen die Windows bieden, om de gevolgen en werking van ASR-regels op te lossen.

### <a name="querying-which-rules-are-active"></a>Query's uitvoeren welke regels actief zijn
Een van de eenvoudigste manieren om te bepalen of ASR-regels al zijn ingeschakeld, en is via een PowerShell-cmdlet, Get-MpPreference.
Hier volgt een voorbeeld:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference-script krijgen":::

Er zijn meerdere ASR-regels actief, met verschillende geconfigureerde acties.

Als u de bovenstaande informatie over ASR-regels wilt uitbreiden, kunt u de eigenschappen **AttackSurfaceReductionRules_Ids** en/of **AttackSurfaceReductionRules_Actions.**

Voorbeeld:

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="voorbeeld van mpreference krijgen":::

In het bovenstaande ziet u alle ID's voor ASR-regels die een andere instelling hebben dan 0 (niet geconfigureerd).

De volgende stap is om de werkelijke acties (Blokkeren of Audit) op te nemen met welke regel elke regel is geconfigureerd. 

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="voorbeeld van mppreference krijgen2":::

### <a name="querying-blocking-and-auditing-events"></a>Query's blokkeren en controleren
ASR-regelgebeurtenissen kunnen worden bekeken in het Windows Defender logboek.

Als u deze wilt openen, opent u Windows Viewer voor gebeurtenissen en bladert u naar Toepassingen en **serviceslogboeken** van  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operationeel.**

:::image type="content" source="images/eventviewerscrnew.png" alt-text="gebeurtenisviewer scr":::

## <a name="microsoft-defender-malware-protection-logs"></a>Microsoft Defender Malware Protection Logs
U kunt ook regelgebeurtenissen weergeven via het Microsoft Defender Antivirus speciaal opdrachtregelprogramma, dat kan worden gebruikt om taken te beheren en te configureren en te `*mpcmdrun.exe*` automatiseren, indien nodig.

U vindt dit hulpprogramma in *%ProgramFiles%\Windows Defender\MpCmdRun.exe.* U moet deze uitvoeren vanuit een opdrachtprompt met verhoogde opdracht (dat wil zeggen uitvoeren als beheerder).

Als u de ondersteuningsgegevens wilt genereren, *typtMpCmdRun.exe -getfiles*. Na een tijdje worden verschillende logboeken in een archief (MpSupportFiles.cab) verpakt en beschikbaar gesteld in *C:\ProgramData\Microsoft\Windows Defender\Support.*

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="malwarebeveiligingslogboeken":::

Haal dat archief op en u hebt veel bestanden beschikbaar voor probleemoplossingsdoeleinden.

De meest relevante bestanden zijn als volgt:

- **MPOperationalEvents.txt:** dit bestand bevat hetzelfde informatieniveau dat wordt gevonden in Gebeurtenisviewer voor Windows Defender het operationele logboek van de groep.
- **MPRegistry.txt:** in dit bestand kunt u alle huidige Windows Defender analyseren, vanaf het moment dat de ondersteuningslogboeken zijn vastgelegd.
- **MPLog.txt:** dit logboek bevat uitgebreidere informatie over alle acties/bewerkingen van de Windows Defender.
