---
title: De rapportsectie van de analist in bedreigingsanalyse
ms.reviewer: ''
description: Meer informatie over de rapportsectie van de analisten van elk rapport voor bedreigingsanalyses. Meer informatie over bedreigingen, risicobeperking, detecties, geavanceerde zoekquery's en meer.
keywords: analistrapport, bedreigingsanalyse, detecties, geavanceerde zoekquery's, risicobeperking,
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
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 650282e0dce49cc392eeb7501f91b3ffed9f0707
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/09/2021
ms.locfileid: "50167563"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Inzicht in het analistrapport in Bedreigingsanalyse

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Van toepassing op:**
- Microsoft 365 Defender

> Wilt u ervaring met Microsoft 365 Defender? U kunt [dit evalueren in een testomgeving](https://aka.ms/mtp-trial-lab) of uw [pilotproject in productie nemen.](https://aka.ms/m365d-pilotplaybook)
>

[!INCLUDE [Prerelease](../includes/prerelease.md)]

Elk [rapport van bedreigingsanalyses](threat-analytics.md) bevat dynamische secties en een uitgebreide geschreven sectie, het _analistenrapport._ Als u deze sectie wilt openen, opent u het rapport over de bij tracked threat en selecteert u het **tabblad Analistrapport.**

![Afbeelding van de rapportsectie van de analist van een rapport voor bedreigingsanalyses](../../media/threat-analytics/ta_analystreport_mtp.png)

_Rapportsectie van analist van een rapport voor bedreigingsanalyse_

## <a name="scan-the-analyst-report"></a>Scan het analistrapport 
Elke sectie van het analistrapport is ontworpen om informatie te bieden die actie kan ondernemen. Hoewel de rapporten variëren, bevatten de meeste rapporten de secties die in de volgende tabel worden beschreven.

| Rapportsectie | Beschrijving |
|--|--|
| Samenvatting van leidinggevenden | Overzicht van de bedreiging, inclusief toen deze voor het eerst werd gezien, de motivatie, aanzienlijke gebeurtenissen, belangrijke doelen, en unieke hulpmiddelen en technieken. U kunt deze gegevens gebruiken om nader te beoordelen hoe u prioriteit kunt geven aan de bedreiging in de context van uw branche, geografische locatie en netwerk. |
| Analyse | Technische informatie over de bedreigingen, met inbegrip van de details van een aanval en hoe aanvallers een nieuwe techniek of aanvalsoppervlak kunnen gebruiken | 
| MITRE ATT&waargenomen CK-technieken | Hoe waargenomen technieken zijn toe te passen op het [MITRE ATT&CK-aanvalskader](https://attack.mitre.org/) | 
| [Risico's](#apply-additional-mitigations) | Aanbevelingen die de bedreiging kunnen stoppen of beperken. Deze sectie bevat ook risicobeperking die niet dynamisch worden bij houden als onderdeel van het rapport risicoanalyse. |
| [Details van detectie](#understand-how-each-threat-can-be-detected) | Specifieke en algemene detecties die worden geleverd door Microsoft-beveiligingsoplossingen waarmee activiteit of onderdelen die aan de bedreiging zijn gekoppeld, aan het oppervlak kunnen komen. | 
| [Geavanceerd opsporen](#find-subtle-threat-artifacts-using-advanced-hunting) | [Geavanceerde zoekquery's](advanced-hunting-overview.md) om proactief mogelijke bedreigingsactiviteit te identificeren. De meeste query's worden geleverd als aanvulling op detecties, met name voor het opsporen van potentieel schadelijke onderdelen of gedrag dat niet dynamisch kan worden geëvalueerd als schadelijk. | 
| Verwijzingen | Microsoft- en publicaties van derden waarnaar wordt verwezen door analisten tijdens het opstellen van het rapport. Inhoud van bedreigingsanalyses is gebaseerd op gegevens die door Microsoft worden gevalideerd. Informatie uit openbaar beschikbare bronnen van derden wordt duidelijk als zodanig geïdentificeerd. | 
| Logboek wijzigen | Het tijdstip waarop het rapport is gepubliceerd en het moment waarop belangrijke wijzigingen in het rapport zijn aangebracht. |

## <a name="apply-additional-mitigations"></a>Aanvullende risicobeperking toepassen
Bedreigingsanalyse houdt dynamisch de [status van beveiligingsupdates en beveiligde configuraties bij.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Deze informatie is beschikbaar als grafieken en tabellen op het **tabblad Risicobeperking.**

Naast deze bij te houden risico's, worden in het analistrapport ook risicobeperking besproken die _niet_ dynamisch worden gecontroleerd. Hier volgen enkele voorbeelden van belangrijke risico's die niet dynamisch worden bij te houden:

- E-mailberichten _met LNK-bijlagen_ of andere verdachte bestandstypen blokkeren
- Lokale beheerderswachtwoorden willekeurig instellen
- Eindgebruikers informeren over phishing-e-mail en andere bedreigingsvectoren
- Specifieke regels voor het [verminderen van aanvallen van het surface in te stellen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)

Hoewel u het  tabblad Risicobeperking kunt gebruiken om uw beveiligingsbeperking tegen een bedreiging te beoordelen, kunt u met deze aanbevelingen extra stappen ondernemen om uw beveiligingsbeperking te verbeteren. Lees zorgvuldig alle richtlijnen voor risicobeperking in het rapport van de analist en pas deze waar mogelijk toe.

## <a name="understand-how-each-threat-can-be-detected"></a>Begrijpen hoe elke bedreiging kan worden gedetecteerd
Het analistrapport biedt ook de detecties van  Antivirus- en antwoordmogelijkheden van Microsoft Defender voor eindpunten.

### <a name="antivirus-detections"></a>Antivirusdetectie
Deze detecties zijn beschikbaar op apparaten met [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) ingeschakeld. Wanneer deze detecties plaatsvinden op apparaten die zijn onboarded bij Microsoft Defender for Endpoint, worden er ook waarschuwingen uitgevoerd die de grafieken in het rapport oplichten.

>[!NOTE]
>Het analistrapport bevat ook **algemene detecties die** een breed scala van bedreigingen kunnen identificeren, in aanvulling op onderdelen of gedrag specifiek voor de gevolgde bedreiging. Deze algemene detecties worden niet weergegeven in de grafieken.

### <a name="endpoint-detection-and-response-edr-alerts"></a>Waarschuwingen voor eindpuntdetectie en -antwoorden
EDR-waarschuwingen worden verhoogd voor [apparaten die zijn onboarded bij Microsoft Defender voor eindpunt.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/onboard-configure) Deze waarschuwingen zijn in het algemeen afhankelijk van beveiligingssignalen die worden verzameld door de Microsoft Defender for Endpoint-sensor en andere eindpuntfuncties, zoals antivirussoftware, netwerkbeveiliging en tamperbeveiliging, die fungeren als krachtige signaalbronnen.

Net als de lijst met antivirusdetecties zijn sommige EDR-waarschuwingen ontworpen om verdacht gedrag dat mogelijk niet is gekoppeld aan de bijgenomen bedreiging, algemeen te markeren. In dergelijke gevallen wordt de waarschuwing duidelijk als 'algemeen' aangegeven en heeft het geen invloed op een van de grafieken in het rapport.

### <a name="email-related-detections-and-mitigations"></a>E-maildetectie en risicobeperking
E-maildetecties en risicobeperking van Microsoft Defender voor Office 365 worden opgenomen in analistenrapporten, naast de eindpuntgegevens die al beschikbaar zijn van Microsoft Defender voor eindpunt. 

Informatie over mislukte e-mailpogingen geeft u inzicht in of uw organisatie het doel was van de bedreiging die in het analistrapport is aan pakken, zelfs als de aanval effectief is geblokkeerd voordat deze wordt afgeleverd in de map Ongewenste e-mail.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Subtiele bedreigings-artefacten zoeken met behulp van geavanceerd zoeken
Hoewel detecties het mogelijk maken om de bijhoudt bedreiging automatisch te identificeren en te stoppen, laten veel aanvallen subtiele traces achter die aanvullende controle vereisen. Sommige aanvallen hebben gedrag van activiteiten dat ook normaal kan zijn, dus dynamisch detecteren kan leiden tot operationele ruis of zelfs fout-positieven.

[Geavanceerd zoeken](advanced-hunting-overview.md) biedt een query-interface op basis van Kusto-querytaal, zodat subtiele indicatoren van bedreigingsactiviteit eenvoudiger te vinden zijn. U kunt hiermee ook contextuele informatie naar boven brengen en controleren of indicatoren zijn verbonden met een bedreiging.

Geavanceerde zoekquery's in de analistenrapporten zijn door Microsoft-analisten gescreend en staan klaar om te worden uitgevoerd in de geavanceerde [queryeditor.](https://security.microsoft.com/advanced-hunting) U kunt de query's ook gebruiken om aangepaste detectieregels [te](custom-detection-rules.md) maken die waarschuwingen activeren voor toekomstige overeenkomsten.


>[!NOTE]
> Bedreigingsanalyse is ook beschikbaar in [Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-analytics) De gegevensintegratie tussen Microsoft Defender voor Office en Microsoft Defender voor het eindpunt van Microsoft 365 Defender Threat Analytics is echter niet beschikbaar.


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van dreigingsanalyse](threat-analytics.md)
- [Proactief bedreigingen vinden met geavanceerd zoeken](advanced-hunting-overview.md) 
- [Aangepaste detectieregels](custom-detection-rules.md)
