---
title: Actie ondernemen voor geavanceerde jacht-queryresultaten in Microsoft 365 Defender
description: Snel bedreigingen en beïnvloede assets in uw geavanceerde zoekresultaten voor de jacht
keywords: geavanceerde jacht, bedreigings jacht, Cyber Threat jacht, Microsoft Threat Protection, Microsoft 365, MTP, m365, Search, query, telemetrie, actie ondernemen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 506af82ec08ad6cd8dbeece5c1c2741e09e4817a
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842462"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Actie ondernemen op geavanceerde zoekresultaten van de jacht

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Van toepassing op:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

U kunt snel bedreigingen of opgetaste activa opnemen in een [geavanceerde jacht](advanced-hunting-overview.md) met krachtige en uitgebreide actie opties. Met deze opties kunt u:

- Verschillende acties op apparaten uitvoeren
- Quarantine-bestanden

## <a name="required-permissions"></a>Vereiste machtigingen
U kunt pas actie ondernemen via een geavanceerde jacht als u een rol hebt in Microsoft Defender voor het eindpunt met [machtigingen voor het verzenden van herstelacties op apparaten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options). Als u geen actie onderneemt, neemt u contact op met een globale beheerder voor het verkrijgen van de volgende machtigingen:

*Actieve herstelacties > Threat en beveiligingslek beheer-herstelbewerkingen*

## <a name="take-various-actions-on-devices"></a>Verschillende acties op apparaten uitvoeren
U kunt de volgende acties uitvoeren op apparaten die zijn gedefinieerd door de `DeviceId` kolom in de queryresultaten:

- Geïsoleerde apparaten isoleren met een infectie en om te voorkomen dat aanvallen later worden verplaatst
- Onderzoek pakket verzamelen om meer Forensic-informatie te verkrijgen
- Voer een antivirus scan uit om bedreigingen te zoeken en te verwijderen met behulp van de meest recente updates voor beveiligingsinformatie.
- Een geautomatiseerd onderzoek initiëren om bedreigingen op het apparaat te controleren en te herstellen, en mogelijk andere getroffen apparaten
- De uitvoering van de app beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, verdere bedreigings activiteiten via malware of andere niet-vertrouwde uitvoerbare bestand voorkomen

Meer informatie over de manier waarop deze antwoord acties worden uitgevoerd via Microsoft Defender voor eindpunten, [vindt u in antwoord acties op apparaten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts).
   
## <a name="quarantine-files"></a>Quarantine-bestanden
U kunt de actie *Quarantine* op een bestand implementeren, zodat de actie automatisch wordt gemigreerd wanneer deze wordt aangetroffen. Wanneer u deze actie selecteert, kunt u kiezen tussen de volgende kolommen om te bepalen welke bestanden in uw queryresultaten in quarantaine zijn:

- `SHA1` (In de meeste geavanceerde jagers tabellen is dit de SHA-1 van het bestand dat is beïnvloed door de opgenomen actie. Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.
- `InitiatingProcessSHA1` (In de meeste geavanceerde jagers tabellen is dit het bestand dat verantwoordelijk is voor de initiëring van de opgenomen actie. Als er bijvoorbeeld een onderliggend proces werd gestart, is dit het bovenliggende proces. 
- `SHA256` : Dit is het SHA-256-equivalent van het bestand dat wordt aangeduid door de `SHA1` kolom.
- `InitiatingProcessSHA256` : Dit is het SHA-256-equivalent van het bestand dat wordt aangeduid door de `InitiatingProcessSHA1` kolom.

Meer informatie over de manier waarop u quarantaine acties kunt uitvoeren en hoe u bestanden kunt herstellen, kunt u [lezen over antwoord acties op bestanden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Om bestanden te zoeken en te plaatsen, moeten de queryresultaten ook `DeviceId` waarden als apparaat-id's opnemen.  

## <a name="take-action"></a>Actie ondernemen
Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in de queryresultaten en selecteert u vervolgens **acties ondernemen**. Een wizard begeleidt u door het proces voor het selecteren en verzenden van de gewenste acties.

![Afbeelding van geselecteerde record met deelvenster voor inspectie van de record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Bekijk de gebruikte acties
Elke actie wordt afzonderlijk opgenomen in het [Actiecentrum](mtp-action-center.md) onder **Actiecentrum**  >  **geschiedenis** ( [Security.Microsoft.com/Action-Center/History](https://security.microsoft.com/action-center/history)). Ga naar het Actiecentrum om de status van elke actie te controleren.
 
## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Overzicht van Onderhoudscentrum](mtp-action-center.md)
