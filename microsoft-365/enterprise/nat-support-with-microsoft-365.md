---
title: Ondersteuning voor NAT met Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 1/24/2017
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: 170e96ea-d65d-4e51-acac-1de56abe39b9
description: In dit artikel vindt u informatie over het benaderen van het aantal clients dat u per IP-adres in uw organisatie kunt gebruiken met NAT.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688944"
---
# <a name="nat-support-with-office-365"></a>Ondersteuning voor NAT met Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Eerder werd voorgesteld dat het maximum aantal Exchange clients dat u per IP-adres moet gebruiken om verbinding te maken met Office 365 ongeveer 2.000 clients per netwerkpoort was.
  
## <a name="why-use-nat"></a>Waarom NAT gebruiken?

Met NAT kunnen duizenden personen in een bedrijfsnetwerk een paar openbare IP-adressen 'delen'.
  
De meeste bedrijfsnetwerken gebruiken persoonlijke IP-adresruimte (RFC1918). Persoonlijke adresruimte wordt toegewezen door de Internet Assigned Numbers Authority (IANA) en is uitsluitend bedoeld voor netwerken die niet rechtstreeks van en naar het globale internet worden gerouteerd.
  
Als u internettoegang wilt bieden tot apparaten op een privé-IP-adresruimte, gebruiken organisaties gatewaytechnologieën zoals firewalls en proxies die nat- of poortadresvertalingsservices (NETWORK Address Translation) bieden. Met deze gateways lijkt het verkeer van interne apparaten naar internet (inclusief Office 365) afkomstig te zijn van een of meer openbare IP-adressen. Elke uitgaande verbinding van een intern apparaat wordt vertaald naar een andere bron-TCP-poort op het openbare IP-adres. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Waarom moeten er zoveel verbindingen tegelijk Office 365?

Outlook kan acht of meer verbindingen openen (in situaties waarin er invoegvoegingen, gedeelde agenda's, postvakken, enzovoort zijn). Omdat er maximaal 64.000 poorten beschikbaar zijn op een nat-apparaat op basis van Windows, kunnen er maximaal 8.000 gebruikers achter een IP-adres zitten voordat de poorten leeg zijn. Houd er rekening mee dat als klanten niet-Windows voor NAT gebruiken, de totale beschikbare poorten afhankelijk zijn van welk NAT-apparaat of welke software wordt gebruikt. In dit scenario kan het maximum aantal poorten kleiner zijn dan 64.000. De beschikbaarheid van poorten wordt ook beïnvloed door andere factoren, zoals Windows het beperken van 4.000 poorten voor eigen gebruik, waardoor het totale aantal beschikbare poorten wordt beperkt tot 60.000. Er kunnen andere toepassingen zijn, zoals Internet Explorer, die tegelijkertijd verbinding kunnen maken, waarvoor extra poorten nodig zijn.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Maximaal ondersteunde apparaten berekenen achter één openbaar IP-adres met Office 365

Als u het maximum aantal apparaten achter één openbaar IP-adres wilt bepalen, moet u netwerkverkeer controleren om het piekportverbruik per client te bepalen. Ook moet een piekfactor worden gebruikt voor het poortgebruik (minimaal 4). 
  
 **Gebruik de volgende formule om het aantal ondersteunde apparaten per IP-adres te berekenen:**
  
Maximaal ondersteunde apparaten achter één openbaar IP-adres = (64.000 - beperkte poorten)/(Piekpoortverbruik + piekfactor)
  
 **Als bijvoorbeeld het volgende waar is:**
  
- **Beperkte poorten:** 4.000 voor het besturingssysteem

- **Piekpoortverbruik:** 6 per apparaat

- **Piekfactor:** 4

Vervolgens worden de maximaal ondersteunde apparaten achter één openbaar IP-adres = (64.000 - 4.000)/(6 + 4) = 6.000
  
Met de release van Office 365 hostingpack, opgenomen in de updates van september 2011 voor Microsoft Office Outlook 2007 of november 2011 voor Microsoft Outlook 2010 of een latere update, kan het aantal verbindingen uit Outlook (zowel Office Outlook 2007 met Service Pack 2 als Outlook 2010) tot Exchange slechts 2 zijn. U moet rekening houden met de verschillende besturingssystemen, gebruikersgedrag, en ga zo maar door om het minimum- en maximumaantal poorten te bepalen dat uw netwerk op piekmomenten nodig heeft.
  
Als u meer apparaten achter één openbaar IP-adres wilt ondersteunen, volgt u de stappen die worden beschreven om het maximum aantal apparaten te beoordelen dat kan worden ondersteund:
  
Houd netwerkverkeer in de gaten om het piekverbruik per client te bepalen. U moet deze gegevens verzamelen:
  
- Vanuit meerdere locaties
    
- Vanaf meerdere apparaten
    
- Op meerdere momenten
    
Gebruik de voorgaande formule om de maximale gebruikers per IP-adres te berekenen die in hun omgeving kunnen worden ondersteund.
  
Er zijn verschillende methoden voor het distribueren van clientbelasting over extra openbare IP-adressen. Beschikbare strategieën zijn afhankelijk van de mogelijkheden van de bedrijfsgatewayoplossing. De eenvoudigste oplossing is om uw gebruikersadresruimte te segmenteren en statisch een aantal IP-adressen aan elke gateway toe te wijzen. Een ander alternatief dat veel gateway-apparaten bieden, is de mogelijkheid om een groep IP-adressen te gebruiken. Het voordeel van de adresgroep is dat deze veel dynamischer is en minder waarschijnlijk aanpassing nodig heeft naarmate uw gebruikersbestand groeit.
  
## <a name="see-also"></a>Zie ook

[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Veelgestelde vragen over Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
