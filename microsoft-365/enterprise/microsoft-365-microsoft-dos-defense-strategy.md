---
title: Microsoft 365 denial-of-service verdedigings strategie
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: None
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In dit artikel vindt u een overzicht van de Microsoft-verdedigings strategie voor denial-of-service-aanvallen (DoS).
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f28f7bcb9c6241404c8101bffe7268c5a1917ffa
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689424"
---
# <a name="microsoft-365-denial-of-service-defense-strategy"></a>Microsoft 365 denial-of-service verdedigings strategie

De strategie van Microsoft om te voorkomen dat aanvallen met een denial-in-service (DoS) op basis van de schaal en de wereldwijde footprint van de service liggen. Met deze schaal kan Microsoft strategieën en technieken voor het toepassen van bepaalde organisaties, providers of klant overeenkomsten gebruiken. De hoekstenen van de VVV strategie is onze algemene aanwezigheid. Microsoft is betrokken bij Internet providers, peer-to-peer providers en privé bedrijven, overal ter wereld. Dit maakt Microsoft een belangrijke Internet aanwezigheid en helpt Microsoft bij het absorberen van aanvallen via een groot oppervlak.

Gezien deze unieke aard, gebruikt Microsoft detectie-en risico processen die verschillen van die van grote ondernemingen. De strategie is gebaseerd op een scheiding van detectie en globale gedistribueerde beperking door middel van veel netwerk randen. Veel ondernemingen gebruiken oplossingen van derden om aanvallen op de Edge te detecteren en te beperken. Aangezien de Edge-capaciteit voor Microsoft groeide, wist dit de betekenis van een aanval tegen afzonderlijke of bepaalde randen slecht. Vanwege deze unieke configuratie worden de onderdelen voor detectie en beveiliging door Microsoft gescheiden. Microsoft implementeert detectie systemen met meerdere lagen om aanvallen dichter bij hun verzadigings punten te detecteren, terwijl de algemene beperking aan de rand wordt gehandhaafd. Deze strategie zorgt ervoor dat we meerdere simultane aanvallen kunnen afhandelen.

Een van de meest effectieve en voordelige verdedigings producten die door Microsoft worden gebruikt tegen DoS-aanvallen, reduceert de service attack. Ongewenst verkeer wordt verwijderd op de netwerk Edge in plaats van de gegevens inline te analyseren, verwerken en reinigen.

Op de interface met het openbare netwerk gebruikt Microsoft speciale beveiligingsapparaten voor Firewall, netwerkadresomzetting en IP-filterfuncties. Microsoft gebruikt ook een algemene, gelijke routering met meerdere paden (ECMP). Een globale ECMP-routering is een netwerk raamwerk, zodat u zeker weet dat er meerdere globale paden zijn om een service te bereiken. Met deze paden zijn de aanvallen tegen Servicebeperkingen beperkt tot de regio waar de aanval vandaan komt. Deze aanval is niet van invloed op andere regio's, aangezien eindgebruikers andere paden kunnen gebruiken om de service in die regio's te bereiken. Microsoft heeft ook interne detectie-en detectie systemen ontwikkeld die gebruikmaken van stroom gegevens, prestatie metrieken en andere informatie. Dit is een hyperscale-cloudservice in Microsoft Azure, waarmee gegevens van diverse punten op Microsoft-netwerken en-services worden geanalyseerd. Een van de taken van een cross-werkbelasting, antwoord team identificeert de rollen en verantwoordelijkheden tussen teams, de criteria voor escalaties en de protocollen voor het nemen van verschillende teams en voor het verwerken van incidenten. Deze oplossingen bieden een netwerkbeveiliging tegen DoS-aanvallen.

Tot slot worden Clouds op basis van de Cloud geconfigureerd met geoptimaliseerde drempelwaarden, op basis van hun protocol en bandbreedte, zodat de belasting van de Cloud veilig is.
