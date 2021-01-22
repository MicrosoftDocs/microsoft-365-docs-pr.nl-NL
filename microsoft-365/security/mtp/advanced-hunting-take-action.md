---
title: Actie ondernemen voor geavanceerde zoekopdrachten in Microsoft 365 Defender
description: Snel bedreigingen en beïnvloede assets adressen in uw geavanceerde queryresultaten
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
ms.openlocfilehash: 9e8ad544cfe17d0d8e5c895e208b42ec56555565
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932176"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Geavanceerde queryresultaten uitvoeren

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

U kunt snel bedreigingen bevatten of gecompromitteerde assets die u vindt in [geavanceerd](advanced-hunting-overview.md) zoeken met behulp van krachtige en uitgebreide actieopties. Met deze opties kunt u:

- Verschillende acties uitvoeren op apparaten
- Quarantainebestanden

## <a name="required-permissions"></a>Vereiste machtigingen
Als u wilt kunnen zoeken op geavanceerde apparaten, moet u een rol hebben in Microsoft Defender for Endpoint met machtigingen om herstelacties op [apparaten in te dienen.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Als u geen actie kunt ondernemen, neemt u contact op met een globale beheerder over het verkrijgen van de volgende machtiging:

*Actieve herstelacties om risico> beveiligingsprobleem te voorkomen - oplossingsafhandeling*

## <a name="take-various-actions-on-devices"></a>Verschillende acties uitvoeren op apparaten
U kunt de volgende acties uitvoeren op apparaten die worden geïdentificeerd door de `DeviceId` kolom in uw queryresultaten:

- Isoleert getroffen apparaten om een virus te voorkomen of om te voorkomen dat aanvallen later worden verplaatst
- Onderzoekspakket verzamelen om meer informatie over het onderzoek te verkrijgen
- Voer een antivirusscan uit om bedreigingen te zoeken en te verwijderen met behulp van de meest recente beveiligingsinformatie-updates
- Start een geautomatiseerd onderzoek om bedreigingen op het apparaat en mogelijk andere getroffen apparaten te controleren en te herstellen
- De uitvoering van apps beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, waardoor volgende bedreigingsactiviteit via malware of andere niet-vertrouwde uitvoerbare bestanden wordt voorkomen

Voor meer informatie over hoe deze antwoordacties worden uitgevoerd via Microsoft Defender voor eindpunt, leest u [meer over antwoordacties op apparaten.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)
   
## <a name="quarantine-files"></a>Quarantainebestanden
U kunt de *quarantaineactie implementeren* voor bestanden, zodat ze automatisch in quarantaine worden geplaatst wanneer ze worden aangetroffen. Wanneer u deze actie selecteert, kunt u kiezen uit de volgende kolommen om te bepalen welke bestanden in de queryresultaten in quarantaine worden geplaatst:

- `SHA1` — In de meeste geavanceerde zoektabellen is dit de SHA-1 van het bestand dat is beïnvloed door de vastgelegde actie. Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.
- `InitiatingProcessSHA1` — In de meeste geavanceerde zoektabellen is dit het bestand dat verantwoordelijk is voor het starten van de opgenomen actie. Als er bijvoorbeeld een onderliggend proces is gestart, is dit het bovenliggende proces. 
- `SHA256` — Dit is het equivalent van SHA-256 van het bestand dat wordt geïdentificeerd door de `SHA1` kolom.
- `InitiatingProcessSHA256` — Dit is het equivalent van SHA-256 van het bestand dat wordt geïdentificeerd door de `InitiatingProcessSHA1` kolom.

Voor meer informatie over hoe quarantaineacties worden ondernomen en hoe bestanden kunnen worden hersteld, leest u [meer over antwoordacties op bestanden.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts)

>[!NOTE]
>Als u bestanden wilt zoeken en in quarantaine wilt plaatsen, moeten de queryresultaten ook waarden `DeviceId` bevatten als apparaat-id's.  

## <a name="take-action"></a>Actie ondernemen
Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in uw queryresultaten en selecteert u **Vervolgens Acties uitvoeren.** Een wizard helpt u bij het selecteren en vervolgens indienen van uw gewenste acties.

![Afbeelding van de geselecteerde record met deelvenster voor het controleren van de record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Acties bekijken die zijn ondernomen
Elke actie wordt afzonderlijk opgenomen in het [actiecentrum](mtp-action-center.md) onder **Geschiedenis** van het actiecentrum  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history) Ga naar het actiecentrum om de status van elke actie te controleren.
 
## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Overzicht van het actiecentrum](mtp-action-center.md)
