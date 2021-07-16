---
title: Microsoft Defender controleren voor de architectuurvereisten voor eindpunten en belangrijke concepten
description: Het technische diagram voor Microsoft Defender voor Eindpunt in Microsoft 365 Defender helpt u identiteit te begrijpen in Microsoft 365 voordat u uw proeflaboratorium of testomgeving maakt.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 4df1ac2ca5fdfaa88ec2d08c85112f52da26b873
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/15/2021
ms.locfileid: "53457818"
---
# <a name="review-microsoft-defender-for-endpoint-architecture-requirements-and-key-concepts"></a>Microsoft Defender controleren voor de architectuurvereisten voor eindpunten en belangrijke concepten

**Is van toepassing op:** Microsoft 365 Defender

In dit artikel wordt u begeleid bij het instellen van de evaluatie voor Microsoft Defender voor endpoint-omgeving.

Zie het [overzichtsartikel](eval-defender-endpoint-overview.md)voor meer informatie over dit proces.

Voordat u Microsoft Defender voor Eindpunt inschakelen, moet u de architectuur begrijpen en aan de vereisten voldoen.

## <a name="understand-the-architecture"></a>De architectuur begrijpen

Het volgende diagram illustreert Microsoft Defender voor eindpuntarchitectuur en -integraties. 

![Stappen voor het toevoegen van Microsoft Defender Office aan de evaluatieomgeving van Defender](../../media/defender/m365-defender-endpoint-architecture.png)

In de volgende tabel wordt de afbeelding beschreven.

Uitroepen | Omschrijving
:---|:---|
1 | Apparaten zijn aan boord via een van de ondersteunde beheerhulpmiddelen. 
2 | On-boarded devices provide and respond to Microsoft Defender for Endpoint signal data.
3 | Beheerde apparaten worden samengevoegd en/of geregistreerd in Azure Active Directory.
4 | Domain-joined Windows 10 apparaten worden gesynchroniseerd met Azure Active Directory met Azure Active Directory Verbinding maken.
5 | Waarschuwingen, onderzoeken en antwoorden van Microsoft Defender voor eindpunten worden beheerd in Microsoft 365 Defender.

## <a name="understand-key-concepts"></a>Belangrijke concepten begrijpen

In de volgende tabel worden belangrijke concepten geïdentificeerd die belangrijk zijn om te begrijpen bij het evalueren, configureren en implementeren van Microsoft Defender voor Eindpunt: 

Concept | Omschrijving | Meer informatie
:---|:---|:---|
Beheerportal | Microsoft 365 Defender portal om te controleren en te helpen bij het reageren op waarschuwingen van potentiële geavanceerde permanente bedreigingsactiviteit of datalekken. | [Overzicht van de Portal van Microsoft Defender voor Eindpunt](/defender-endpoint/portal-overview)
Surface Reduction aanvallen | Verminder uw aanvalsoppervlakken door de plaatsen waar uw organisatie kwetsbaar is voor cyberaanvallen en aanvallen te minimaliseren. | [Overzicht van kwetsbaarheid voor aanvallen verminderen](/defender-endpoint/overview-attack-surface-reduction)
Eindpuntdetectie en -antwoord | De mogelijkheden voor eindpuntdetectie en -respons bieden geavanceerde detecties voor aanvallen die in realtime en actie kunnen worden ondernomen. | [Overzicht van eindpuntdetectie en -respons mogelijkheden](/defender-endpoint/overview-endpoint-detection-response)
Gedrag blokkeren en insluiting | Mogelijkheden voor het blokkeren en inperken van gedrag kunnen helpen bij het identificeren en stoppen van bedreigingen, op basis van hun gedrag en procesbomen, zelfs wanneer de bedreiging is gestart met de uitvoering. | [Gedragsblokkering en -insluiting](/defender-endpoint/behavioral-blocking-containment)
Geautomatiseerd onderzoek en antwoord | Voor geautomatiseerd onderzoek worden verschillende inspectiealgoritmen gebruikt op basis van processen die door beveiligingsanalisten worden gebruikt en die zijn ontworpen om waarschuwingen te onderzoeken en onmiddellijk actie te ondernemen om inbreuken op te lossen. | [Geautomatiseerde onderzoeken gebruiken om bedreigingen te onderzoeken en te corrigeren](/defender-endpoint/automated-investigations)
Geavanceerd opsporen | Geavanceerd zoeken is een op query's gebaseerd hulpprogramma voor bedreigingsjacht waarmee u tot 30 dagen onbewerkte gegevens kunt verkennen, zodat u gebeurtenissen in uw netwerk proactief kunt controleren om bedreigingsindicatoren en entiteiten te zoeken. | [Overzicht van geavanceerde jacht](/defender-endpoint/advanced-hunting-overview)
Dreigingsanalyse | Bedreigingsanalyse is een reeks rapporten van deskundige Microsoft-beveiligingsonderzoekers over de meest relevante bedreigingen. | [Nieuwe bedreigingen traceren en hierop reageren](/defender-endpoint/threat-analytics)


Zie Wat is Microsoft Defender voor eindpunt voor meer informatie over de mogelijkheden van Microsoft Defender [voor Eindpunt.](/defender-endpoint/microsoft-defender-endpoint)

## <a name="siem-integration"></a>SIEM-integratie

U kunt Microsoft Defender voor Eindpunt integreren met Azure Sentinel om beveiligingsgebeurtenissen in uw organisatie uitgebreider te analyseren en playbooks te maken voor een effectieve en onmiddellijke reactie. 

Microsoft Defender voor Eindpunt kan ook worden geïntegreerd in andere SIEM-oplossingen (Security Information and Event Management). Zie [SiEM-integratie inschakelen in Microsoft Defender voor eindpunt voor meer informatie.](/defender-endpoint/enable-siem-integration)


## <a name="next-steps"></a>Volgende stappen
[De evaluatie inschakelen](eval-defender-endpoint-enable-eval.md)

Terug naar het overzicht voor [Microsoft Defender evalueren voor eindpunt](eval-defender-endpoint-overview.md)

Ga terug naar het overzicht voor [Evalueren en Microsoft 365 Defender](eval-overview.md)