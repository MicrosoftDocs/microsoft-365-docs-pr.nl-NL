---
title: De sectie analistrapport in bedreigingsanalyses begrijpen
ms.reviewer: ''
description: Meer informatie over de sectie analistrapport van elk rapport voor bedreigingsanalyse. Meer informatie over bedreigingen, risicobeperking, detecties, geavanceerde zoekquery's en meer.
keywords: analistrapport, bedreigingsanalyse, detecties, geavanceerde zoekquery's, risicobeperking,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6529f0badd94d6ca4d95dfbb562a9d352fedb76a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935891"
---
# <a name="understand-the-analyst-report-in-threat-analytics"></a>Het analistrapport in bedreigingsanalyses begrijpen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Van toepassing op:**
- [Microsoft Defender voor Eindpunt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Wilt u Microsoft Defender voor Eindpunt ervaren? [Meld u aan voor een gratis proefabonnement.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Elk [rapport voor bedreigingsanalyse](threat-analytics.md) bevat dynamische secties en een uitgebreide, geschreven sectie genaamd _het analistrapport._ Als u deze sectie wilt openen, opent u het rapport over de bijgespoorde bedreiging en selecteert u **het tabblad Rapport analist.**

![Afbeelding van de sectie analistrapport van een rapport over bedreigingsanalyse](images/ta-analyst-report-small.png)

_Rapportsectie van een analyserapport voor bedreigingen_

## <a name="scan-the-analyst-report"></a>Het analistrapport scannen 
Elke sectie van het analyticusrapport is ontworpen om actie-informatie te verstrekken. Hoewel rapporten variëren, bevatten de meeste rapporten de secties die in de volgende tabel worden beschreven.

| Rapportsectie | Beschrijving |
|--|--|
| Samenvatting van leidinggevenden | Overzicht van de bedreiging, inclusief wanneer deze voor het eerst werd gezien, de motivaties, belangrijke gebeurtenissen, belangrijke doelen en verschillende hulpmiddelen en technieken. U kunt deze informatie gebruiken om verder te beoordelen hoe u prioriteit kunt geven aan de bedreiging in de context van uw branche, geografische locatie en netwerk. |
| Analyse | Technische informatie over de bedreigingen, waaronder de details van een aanval en hoe aanvallers een nieuwe techniek of aanvalsoppervlak kunnen gebruiken | 
| MITRE ATT&CK-technieken waargenomen | Hoe waargenomen technieken worden toebesteed aan het [MITRE ATT-&CK-aanvalskader](https://attack.mitre.org/) | 
| [Risico's](#apply-additional-mitigations) | Aanbevelingen die de impact van de bedreiging kunnen stoppen of helpen verminderen. Deze sectie bevat ook mitigaties die niet dynamisch worden bijgespoord als onderdeel van het rapport Bedreigingsanalyse. |
| [Detectiedetails](#understand-how-each-threat-can-be-detected) | Specifieke en algemene detecties die worden geleverd door Microsoft-beveiligingsoplossingen waarmee activiteiten of onderdelen die aan de bedreiging zijn gekoppeld, kunnen worden gedetecteerd. | 
| [Geavanceerd opsporen](#find-subtle-threat-artifacts-using-advanced-hunting) | [Geavanceerde query's voor](advanced-hunting-overview.md) het proactief identificeren van mogelijke bedreigingsactiviteit. De meeste query's worden geleverd ter aanvulling van detecties, met name voor het opsporen van potentieel schadelijke onderdelen of gedragingen die niet dynamisch kunnen worden beoordeeld als schadelijk. | 
| Verwijzingen | Microsoft en publicaties van derden waarnaar door analisten is verwezen tijdens het maken van het rapport. Inhoud van bedreigingsanalyse is gebaseerd op gegevens die zijn gevalideerd door Microsoft-onderzoekers. Informatie uit openbaar beschikbare bronnen van derden wordt duidelijk als zodanig geïdentificeerd. | 
| Logboek wijzigen | De tijd waarop het rapport is gepubliceerd en wanneer er belangrijke wijzigingen zijn aangebracht in het rapport. |

## <a name="apply-additional-mitigations"></a>Aanvullende risico's toepassen
Bedreigingsanalyse houdt dynamisch de [status bij van beveiligingsupdates en veilige configuraties.](threat-analytics.md#mitigations-review-list-of-mitigations-and-the-status-of-your-devices) Deze informatie is beschikbaar als grafieken en tabellen op **het tabblad Risicobeperking.**

Naast deze bij te houden risicobeperking, worden in het analyserapport ook risicobeperkingen besproken die _niet_ dynamisch worden gecontroleerd. Hier volgen enkele voorbeelden van belangrijke risico's die niet dynamisch worden bijgespoord:

- E-mailberichten blokkeren _met LNK-bijlagen_ of andere verdachte bestandstypen
- Wachtwoorden voor lokale beheerders willekeurig maken
- Eindgebruikers informeren over phishing-e-mail en andere bedreigingsvectoren
- Specifieke regels voor [het verlagen van het oppervlak voor aanvallen in- en uit te stellen](attack-surface-reduction.md)

Hoewel u het tabblad **Mitigaties** kunt gebruiken om uw beveiligingshouding tegen een bedreiging te beoordelen, kunt u met deze aanbevelingen extra stappen ondernemen om uw beveiligingshouding te verbeteren. Lees alle mitigatie-richtlijnen in het analistenrapport zorgvuldig en pas deze waar mogelijk toe.

## <a name="understand-how-each-threat-can-be-detected"></a>Begrijpen hoe elke bedreiging kan worden gedetecteerd
Het analistrapport bevat ook de detecties van Microsoft Defender voor endpoint-antivirus- en _eindpuntdetectie-_ en antwoordmogelijkheden (EDR).

### <a name="antivirus-detections"></a>Antivirusdetecties
Deze detecties zijn beschikbaar op apparaten met [Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) ingeschakeld. Wanneer deze detecties plaatsvinden op apparaten die zijn onboarded bij Microsoft Defender voor Eindpunt, worden er ook waarschuwingen uitgevoerd die de grafieken in het rapport aanlichten.

>[!NOTE]
>Het analistrapport bevat ook **algemene detecties** die een breed scala aan bedreigingen kunnen identificeren, naast onderdelen of gedragingen die specifiek zijn voor de bijgespoorde bedreiging. Deze algemene detecties worden niet weergegeven in de grafieken.

### <a name="endpoint-detection-and-response-edr-alerts"></a>EDR-waarschuwingen (Endpoint Detection and Response)
EDR-waarschuwingen worden verhoogd voor [apparaten die zijn aan boord van Microsoft Defender voor Eindpunt](onboard-configure.md). Deze waarschuwingen zijn in het algemeen afhankelijk van beveiligingssignalen die zijn verzameld door de Microsoft Defender voor eindpunten-sensor en andere mogelijkheden voor eindpunten, zoals antivirusprogramma's, netwerkbeveiliging, tamperbeveiliging, die fungeren als krachtige signaalbronnen.

Net als de lijst met antivirusdetecties zijn sommige EDR-waarschuwingen ontworpen om een algemene vlag te geven voor verdacht gedrag dat mogelijk niet is gekoppeld aan de bijgespoorde bedreiging. In dergelijke gevallen wordt in het rapport duidelijk aangegeven dat de waarschuwing 'algemeen' is en dat dit geen invloed heeft op een van de grafieken in het rapport.

## <a name="find-subtle-threat-artifacts-using-advanced-hunting"></a>Subtiele bedreigingsartefacten zoeken met behulp van geavanceerde jacht
Met detecties kunt u de bijgespoorde bedreiging automatisch identificeren en stoppen, maar veel aanvalsactiviteiten laten subtiele sporen achter die extra controle vereisen. Sommige aanvalsactiviteiten vertonen gedrag dat ook normaal kan zijn, dus als u ze dynamisch detecteert, kan dit leiden tot operationele ruis of zelfs onwaar positieven.

[Geavanceerd zoeken](advanced-hunting-overview.md) biedt een queryinterface op basis van kustoquerytaal, die het opsporen van subtiele indicatoren van bedreigingsactiviteit vereenvoudigt. Hiermee kunt u ook contextuele informatie aan de oppervlakte brengen en controleren of indicatoren zijn verbonden met een bedreiging.

Geavanceerde zoekquery's in de analistenrapporten zijn door Microsoft-analisten doorgelicht en zijn klaar om uit te voeren in de [geavanceerde queryeditor.](https://securitycenter.windows.com/advanced-hunting) U kunt de query's ook gebruiken om aangepaste [detectieregels te maken](custom-detection-rules.md) die waarschuwingen voor toekomstige overeenkomsten activeren.


## <a name="related-topics"></a>Verwante onderwerpen
- [Overzicht van dreigingsanalyse](threat-analytics.md)
- [Proactief bedreigingen zoeken met geavanceerde jacht](advanced-hunting-overview.md) 
- [Aangepaste regels voor detectie](custom-detection-rules.md)