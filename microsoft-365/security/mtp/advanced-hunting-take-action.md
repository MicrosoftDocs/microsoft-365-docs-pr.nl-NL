---
title: Onderneem actie op geavanceerde jachtqueryresultaten in Microsoft Threat Protection
description: Pak bedreigingen en getroffen assets snel aan in uw geavanceerde jachtqueryresultaten
keywords: geavanceerde jacht, bedreiging jacht, cyber bedreiging jacht, Microsoft threat protection, Microsoft 365, mtp, m365, zoeken, query, telemetrie, actie ondernemen
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 4ebf220472db69d48127b805256e15246bd400cb
ms.sourcegitcommit: 89178b8f20d59ca88cfca303a13062b91fbeae9d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/04/2020
ms.locfileid: "46552730"
---
# <a name="take-action-on-advanced-hunting-query-results"></a>Actie ondernemen op geavanceerde jachtqueryresultaten

**Van toepassing op:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

U snel bedreigingen bevatten of gecompromitteerde activa aanpakken die u in [geavanceerde jacht](advanced-hunting-overview.md) vindt met behulp van krachtige en uitgebreide actieopties. Met deze opties u:

- Verschillende acties uitvoeren op apparaten
- Quarantainebestanden

## <a name="required-permissions"></a>Vereiste machtigingen
Om actie te kunnen ondernemen door middel van geavanceerde jacht, heb je een rol nodig in Microsoft Defender ATP met [machtigingen om herstelacties in te dienen op apparaten.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles#permission-options) Als u geen actie ondernemen, neemt u contact op met een globale beheerder over het verkrijgen van de volgende machtiging:

*Actieve herstelacties > bedreigings- en kwetsbaarheidsbeheer - Herstelafhandeling*

## <a name="take-various-actions-on-devices"></a>Verschillende acties uitvoeren op apparaten
U de volgende acties uitvoeren op apparaten die door de kolom in de queryresultaten zijn `DeviceId` geïdentificeerd:

- Getroffen apparaten isoleren om een infectie te bevatten of te voorkomen dat aanvallen lateraal bewegen
- Verzamel onderzoekspakket om meer forensische informatie te verkrijgen
- Een antivirusscan uitvoeren om bedreigingen te vinden en te verwijderen met behulp van de nieuwste updates van beveiligingsinformatie
- Start een geautomatiseerd onderzoek om bedreigingen op het apparaat en mogelijk andere getroffen apparaten te controleren en te herstellen
- App-uitvoering beperken tot alleen door Microsoft ondertekende uitvoerbare bestanden, waardoor latere bedreigingsactiviteit wordt voorkomen door middel van malware of andere niet-vertrouwde uitvoerbare bestanden

[Lees meer over de](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-machine-alerts)manier waarop deze reactieacties worden uitgevoerd via Microsoft Defender ATP.
   
## <a name="quarantine-files"></a>Quarantainebestanden
U de *quarantaineactie* implementeren op bestanden, zodat ze automatisch in quarantaine worden geplaatst wanneer ze worden aangetroffen. Wanneer u deze actie selecteert, u kiezen uit de volgende kolommen om te bepalen welke bestanden in uw queryresultaten in quarantaine moeten worden geplaatst:

- `SHA1`— In de meeste geavanceerde jachttafels is dit de SHA-1 van het bestand dat werd beïnvloed door de geregistreerde actie. Als een bestand bijvoorbeeld is gekopieerd, is dit het gekopieerde bestand.
- `InitiatingProcessSHA1`— In de meeste geavanceerde jachttabellen is dit het bestand dat verantwoordelijk is voor het initiëren van de geregistreerde actie. Als er bijvoorbeeld een onderliggend proces is gestart, is dit het bovenliggende proces. 
- `SHA256`— Dit is het SHA-256-equivalent van het bestand dat door de kolom wordt `SHA1` geïdentificeerd.
- `InitiatingProcessSHA256`— Dit is het SHA-256-equivalent van het bestand dat door de kolom wordt `InitiatingProcessSHA1` geïdentificeerd.

Lees meer over de manier waarop quarantaineacties worden uitgevoerd en hoe bestanden kunnen worden hersteld, [over reactieacties in bestanden](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/respond-file-alerts).

>[!NOTE]
>Als u bestanden wilt zoeken en in quarantaine wilt plaatsen, moeten de queryresultaten ook `DeviceId` waarden als apparaat-id's bevatten.  

## <a name="take-action"></a>Actie ondernemen
Als u een van de beschreven acties wilt uitvoeren, selecteert u een of meer records in uw queryresultaten en selecteert u **Acties uitvoeren**. Een wizard begeleidt u bij het selecteren en vervolgens indienen van uw gewenste acties.

![Afbeelding van geselecteerde record met deelvenster voor het inspecteren van de record](../../media/mtp-ah/ah-take-actions.png)

## <a name="review-actions-taken"></a>Acties bekijken
Elke actie wordt individueel geregistreerd in het [actiecentrum](mtp-action-center.md) onder **Geschiedenis van het Actiecentrum**  >  **History** [(security.microsoft.com/action-center/history).](https://security.microsoft.com/action-center/history) Ga naar het actiecentrum om de status van elke actie te controleren.
 
## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van geavanceerd opsporen](advanced-hunting-overview.md)
- [De querytaal leren](advanced-hunting-query-language.md)
- [Werken met queryresultaten](advanced-hunting-query-results.md)
- [Meer informatie over het schema](advanced-hunting-schema-tables.md)
- [Overzicht van het Onderhoudscentrum](mtp-action-center.md)