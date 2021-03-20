---
title: Actie ondernemen voor geavanceerde zoekqueryresultaten in Microsoft 365 Defender
description: Snel bedreigingen en beïnvloede activa in uw geavanceerde resultaten van de zoekquery aan te pakken
keywords: advanced hunting, threat hunting, cyber threat hunting, microsoft threat protection, microsoft 365, mtp, m365, search, query, telemetry, take action
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: fbd49806913b5f01ccc3127d6b596db140d2e2aa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904006"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Actie ondernemen voor geavanceerde resultaten van query's

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

Met krachtige en uitgebreide actieopties kunt u snel bedreigingen bevatten of gecompromitteerde activa die u in [geavanceerde](advanced-hunting-overview.md) zoekactie vindt, bevatten. Met deze opties kunt u:

- Verschillende acties uitvoeren op apparaten
- Quarantainebestanden

## <a name="required-permissions"></a>Vereiste machtigingen
Als u actie wilt kunnen ondernemen via geavanceerde zoekacties, hebt u een rol nodig in Microsoft Defender voor Eindpunt met machtigingen voor het indienen van herstelacties [op apparaten.](/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Als u geen actie kunt ondernemen, neemt u contact op met een globale beheerder over het verkrijgen van de volgende machtigingen:

*Actieve herstelacties > bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling*

## <a name="take-various-actions-on-devices"></a>Verschillende acties uitvoeren op apparaten
U kunt de volgende acties uitvoeren op apparaten die zijn geïdentificeerd door de `DeviceId` kolom in de queryresultaten:

- Getroffen apparaten isoleren om een infectie te bevatten of om te voorkomen dat aanvallen lateraal worden verplaatst
- Onderzoekspakket verzamelen om meer gerechtelijke informatie te verkrijgen
- Voer een antivirusscan uit om bedreigingen te zoeken en te verwijderen met de meest recente beveiligingsinformatie-updates
- Een geautomatiseerd onderzoek starten om bedreigingen op het apparaat en mogelijk andere getroffen apparaten te controleren en te corrigeren
- De uitvoering van apps beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, waardoor verdere bedreigingsactiviteit via malware of andere niet-vertrouwde uitvoerbare bestanden wordt voorkomen

Lees meer over reactieacties op apparaten voor meer informatie over hoe deze antwoordacties worden uitgevoerd via Microsoft Defender voor [Eindpunt.](/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Quarantainebestanden
U kunt de *quarantaineactie voor* bestanden implementeren, zodat ze automatisch in quarantaine worden geplaatst wanneer ze worden aangetroffen. Wanneer u deze actie selecteert, kunt u kiezen uit de volgende kolommen om te bepalen welke bestanden in de queryresultaten in quarantaine moeten worden geplaatst:

- `SHA1` — In de meeste geavanceerde zoektabellen is dit de SHA-1 van het bestand dat is beïnvloed door de opgenomen actie. Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.
- `InitiatingProcessSHA1` — In de meest geavanceerde zoektabellen is dit het bestand dat verantwoordelijk is voor het starten van de opgenomen actie. Als bijvoorbeeld een onderliggend proces is gestart, is dit het bovenliggende proces. 
- `SHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `SHA1` geïdentificeerd.
- `InitiatingProcessSHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `InitiatingProcessSHA1` geïdentificeerd.

Voor meer informatie over hoe quarantaineacties worden ondernomen en hoe bestanden kunnen worden hersteld, leest u [meer over reactieacties op bestanden.](/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>Als u bestanden wilt zoeken en in quarantaine wilt plaatsen, moeten de queryresultaten ook waarden `DeviceId` als apparaataanduidingen bevatten.  

## <a name="take-action"></a>Actie ondernemen
Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in de queryresultaten en selecteert u **Vervolgens Acties uitvoeren.** Een wizard begeleidt u bij het proces van het selecteren en vervolgens indienen van uw gewenste acties.

![Afbeelding van geselecteerde record met deelvenster voor het controleren van de record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Acties bekijken die zijn ondernomen
Elke actie wordt afzonderlijk opgenomen in het [actiecentrum](mtp-action-center.md) onder **Actiecentrumgeschiedenis**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history) Ga naar het actiecentrum om de status van elke actie te controleren.
 
## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Overzicht van actiecentrum](mtp-action-center.md)