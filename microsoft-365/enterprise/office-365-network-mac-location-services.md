---
title: Microsoft 365 Locatieservices voor netwerkconnectiviteit
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Locatieservices voor netwerkconnectiviteit
ms.openlocfilehash: ed78d7ba48cd9666ce1aae1af5478e3b7536e1e1
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470446"
---
# <a name="microsoft-365-network-connectivity-location-services"></a>Microsoft 365 Locatieservices voor netwerkconnectiviteit

Het Microsoft 365-beheercentrum bevat nu Netwerkinzichten en prestatieaanbevelingen, die meetwaarden voor liveprestaties zijn die worden verzameld vanuit uw Microsoft 365 tenant. Deze metrische gegevens kunnen alleen worden bekeken door beheerdersgebruikers in uw tenant. Organisatienetwerkconnectiviteit is ontworpen per kantoorlocatie via een netwerklocatie die naar internet gaat. Microsoft 365 clientconnectiviteit maakt gebruik van deze route en vervolgens via internet naar de front-doorservers van de Microsoft-service. Het identificeren van kantoorlocaties is essentieel om deze netwerkinzichten weer te geven.

## <a name="location-in-network-measurements"></a>Locatie in netwerkmetingen

De beheerder van een organisatie kan ervoor kiezen om de locatie op te geven die wordt opgenomen in de netwerkmetingen die door deze functie worden gebruikt. Hiermee kunt u automatisch de plaats ontdekken waar elk kantoor zich bevindt. Locatiegegevens zijn niet nauwkeurig en worden verdu obfusceerd tot 300m en gecategoriseerd per plaats. Op het moment dat de locatie wordt vastgelegd op Windows apparaat, wordt op het apparaat een pictogram Locatie **in** gebruik weergegeven in het hulpmiddelvak. Beheerders willen gebruikers mogelijk op de hoogte stellen van het uiterlijk van dit pictogram. Bij deze verwerking wordt de locatie beschouwd als de kantoorlocatie van de organisatie en niet als de locatie van een persoon of apparaat. Netwerkinzichten kunnen worden weergegeven op deze ontdekte kantoorlocatiesteden. Als u een hogere nauwkeurigheid wilt in de aanbevelingen, kunt u specifieke adressen voor office-locaties invoeren. De netwerkinzichten worden in plaats daarvan samengevoegd tot die locaties. Office locaties kunnen niet meer dan 300 meter worden samengevoegd.

## <a name="location-in-the-microsoft-365-admin-center"></a>Locatie in het Microsoft 365 beheercentrum

In het Microsoft 365 beheercentrum worden Bing kaartbesturingselementen gebruikt om aan te geven waar de kantoorlocaties van de organisatie zich bevinden. De besturingselementen geven ook de netwerkperimetertopologie weer voor een geselecteerde kantoorlocatie. Wanneer een beheerder specifieke adresgegevens toevoegt voor office-locaties, Bing Kaarten ook adressen voorstellen om gegevensinvoer te vergemakkelijken.

## <a name="terms-of-use"></a>Gebruiksvoorwaarden

Alle inhoud die via Bing Kaarten, inclusief geocodes, kan alleen worden gebruikt in het product waarmee de inhoud wordt geleverd. Het gebruik door de klant van de functie Microsoft 365-beheercentrumlocatieservices, mogelijk gemaakt door Bing Kaarten, wordt bepaald door de _Bing Kaarten End-User Gebruiksvoorwaarden_ die beschikbaar zijn op en de <https://go.microsoft.com/?linkid=9710837> [Microsoft-privacyverklaring.](https://go.microsoft.com/fwlink/?LinkID=248686)

Deze functie, die wordt geleverd via Bing Kaarten, wordt ook ondersteund door **TomTom.** Meer informatie over de producten en services van TomTom vindt u op [https://www.tomtom.com/legal](https://www.tomtom.com/legal) .

## <a name="related-topics"></a>Verwante onderwerpen

[Netwerkconnectiviteit in het Microsoft 365 beheercentrum (voorbeeld)](office-365-network-mac-perf-overview.md)

[Microsoft 365 netwerkprestatieinzichten (voorbeeld)](office-365-network-mac-perf-insights.md)

[Microsoft 365 netwerkbeoordeling (voorbeeld)](office-365-network-mac-perf-score.md)

[Microsoft 365 connectiviteitstest in het Microsoft 365-beheercentrum (voorbeeld)](office-365-network-mac-perf-onboarding-tool.md)
