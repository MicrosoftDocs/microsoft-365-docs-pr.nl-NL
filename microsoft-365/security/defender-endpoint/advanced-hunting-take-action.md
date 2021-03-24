---
title: Actie ondernemen op het gebied van geavanceerde resultaten van query's in Microsoft Threat Protection
description: Snel bedreigingen en beïnvloede activa in uw geavanceerde resultaten van de zoekquery aan te pakken
keywords: advanced hunting, threat hunting, cyber threat hunting, mdatp, microsoft defender atp, wdatp search, query, telemetry, custom detections, schema, kusto, avoid timeout, command lines, process id
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 09/20/2020
ms.technology: mde
ms.openlocfilehash: 79d720a8b996f826548b79834e5d5c2048e28c2b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/23/2021
ms.locfileid: "51059969"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Actie ondernemen voor geavanceerde resultaten van query's

**Van toepassing op:**
- [Microsoft Defender voor Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)

> Wilt u Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

Met krachtige en uitgebreide actieopties kunt u snel bedreigingen bevatten of gecompromitteerde activa die u in [geavanceerde](advanced-hunting-overview.md) zoekactie vindt, bevatten. Met deze opties kunt u:

- Verschillende acties uitvoeren op apparaten
- Quarantainebestanden

## <a name="required-permissions"></a>Vereiste machtigingen

Als u actie wilt kunnen ondernemen via geavanceerde zoekacties, hebt u een rol nodig in Defender for Endpoint met machtigingen voor het indienen van herstelacties [op apparaten.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/user-roles#permission-options) Als u geen actie kunt ondernemen, neemt u contact op met een globale beheerder over het verkrijgen van de volgende machtigingen:

*Actieve herstelacties > bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling*

## <a name="take-various-actions-on-devices"></a>Verschillende acties uitvoeren op apparaten

U kunt de volgende acties uitvoeren op apparaten die zijn geïdentificeerd door de `DeviceId` kolom in de queryresultaten:

- Getroffen apparaten isoleren om een infectie te bevatten of om te voorkomen dat aanvallen lateraal worden verplaatst
- Onderzoekspakket verzamelen om meer gerechtelijke informatie te verkrijgen
- Voer een antivirusscan uit om bedreigingen te zoeken en te verwijderen met de meest recente beveiligingsinformatie-updates
- Een geautomatiseerd onderzoek starten om bedreigingen op het apparaat en mogelijk andere getroffen apparaten te controleren en te corrigeren
- De uitvoering van apps beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, waardoor verdere bedreigingsactiviteit via malware of andere niet-vertrouwde uitvoerbare bestanden wordt voorkomen

Voor meer informatie over hoe deze antwoordacties worden uitgevoerd via Defender voor Eindpunt, leest u [meer over antwoordacties op apparaten.](respond-machine-alerts.md)

## <a name="quarantine-files"></a>Quarantainebestanden

U kunt de *quarantaineactie voor* bestanden implementeren, zodat ze automatisch in quarantaine worden geplaatst wanneer ze worden aangetroffen. Wanneer u deze actie selecteert, kunt u kiezen uit de volgende kolommen om te bepalen welke bestanden in de queryresultaten in quarantaine moeten worden geplaatst:

- `SHA1` — In de meeste geavanceerde zoektabellen is dit de SHA-1 van het bestand dat is beïnvloed door de opgenomen actie. Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.
- `InitiatingProcessSHA1` — In de meest geavanceerde zoektabellen is dit het bestand dat verantwoordelijk is voor het starten van de opgenomen actie. Als bijvoorbeeld een onderliggend proces is gestart, is dit het bovenliggende proces. 
- `SHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `SHA1` geïdentificeerd.
- `InitiatingProcessSHA256` — Dit is het SHA-256-equivalent van het bestand dat door de kolom is `InitiatingProcessSHA1` geïdentificeerd.

Voor meer informatie over hoe quarantaineacties worden ondernomen en hoe bestanden kunnen worden hersteld, leest u [meer over reactieacties op bestanden.](respond-file-alerts.md)

>[!NOTE]
>Als u bestanden wilt zoeken en in quarantaine wilt plaatsen, moeten de queryresultaten ook waarden `DeviceId` als apparaataanduidingen bevatten.  

## <a name="take-action"></a>Actie ondernemen

Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in de queryresultaten en selecteert u **Vervolgens Acties uitvoeren.** Een wizard begeleidt u bij het proces van het selecteren en vervolgens indienen van uw gewenste acties.

![Afbeelding van geselecteerde record met deelvenster voor het controleren van de record](images/ah-take-actions.png)

## <a name="review-actions-taken"></a>Acties bekijken die zijn ondernomen

Elke actie wordt afzonderlijk opgenomen in het actiecentrum, onder **Actiecentrumgeschiedenis**  >   [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history) Ga naar het actiecentrum om de status van elke actie te controleren.
 
## <a name="related-topics"></a>Verwante onderwerpen

- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Meer informatie over het schema](advanced-hunting-schema-reference.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Aanbevolen procedures voor query's toepassen](advanced-hunting-best-practices.md)
- [Overzicht van aangepaste detectie](overview-custom-detections.md)
