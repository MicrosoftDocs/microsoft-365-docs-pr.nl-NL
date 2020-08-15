---
title: NAT-ondersteuning met Office 365
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
description: In dit artikel vindt u meer informatie over hoe u het aantal clients per IP-adres in uw organisatie met NAT kunt gebruiken.
ms.openlocfilehash: f48874853c3acb80927933761862b14379b6d4bd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46688944"
---
# <a name="nat-support-with-office-365"></a>NAT-ondersteuning met Office 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Eerder werd u aangeraden het maximale aantal Exchange-clients per IP-adres te gebruiken om verbinding te maken met Office 365 via 2.000 clients per netwerkpoort.
  
## <a name="why-use-nat"></a>Het nut van NAT

Met behulp van NAT kunnen duizenden personen in een bedrijfsnetwerk ' delen ' een paar openbaar routerende IP-adressen delen.
  
In de meeste bedrijfsnetwerken wordt de IP-adresruimte van private (RFC1918) gebruikt. Persoonlijke adresruimte wordt toegewezen door de beheerder van Internet toegewezen nummers (IANA) en uitsluitend bedoeld voor netwerken die niet rechtstreeks naar en via het globale Internet worden gerouteerd.
  
Voor het verlenen van toegang tot apparaten via een persoonlijke IP-adresruimte kunnen organisaties gebruikmaken van gateway technologieën zoals firewalls en proxy's die netwerkadresomzetting (NAT) of netwerkadresomzetting (netwerkadresomzetting) bieden. Deze gateways zorgen dat verkeer van interne apparaten naar Internet (waaronder Office 365) afkomstig is van een of meer openbaar routeerbaarere IP-adressen. Elke uitgaande verbinding van een intern apparaat wordt omgezet in een andere bron-TCP-poort voor het openbare IP-adres. 
  
## <a name="why-do-you-need-to-have-so-many-connections-open-to-office-365-at-the-same-time"></a>Waarom moet u ervoor zorgen dat er meerdere verbindingen tegelijk met Office 365 worden geopend?

In Outlook worden acht of meer verbindingen geopend (in situaties waarin er invoegtoepassingen zijn, gedeelde agenda's, postvakken, enzovoort). Aangezien er maximaal 64.000 poorten beschikbaar zijn op een op Windows gebaseerd NAT-apparaat, kunnen er maximaal 8.000 gebruikers achter een IP-adres worden weergegeven voordat de poorten zijn uitgeput. Als klanten niet-Windows-besturingssystemen op basis van de NAT gebruiken, zijn de totale beschikbare poorten afhankelijk van welk NAT-apparaat of welke software wordt gebruikt. In dit scenario kon het maximum aantal poorten kleiner zijn dan 64.000. De beschikbaarheid van poorten wordt ook beïnvloed door andere factoren, zoals Windows-beperkingen voor 4.000-poorten voor eigen gebruik, waardoor het totale aantal beschikbare poorten wordt beperkt tot 60.000. Er kunnen andere toepassingen zijn, zoals Internet Explorer, die tegelijk verbinding konden maken, zodat er extra poorten zijn.
  
## <a name="calculating-maximum-supported-devices-behind-a-single-public-ip-address-with-office-365"></a>Het maximum aantal ondersteunde apparaten per openbaar IP-adres berekenen met Office 365

Als u het maximum aantal apparaten achter één openbaar IP-adres wilt bepalen, dient u netwerkverkeer te controleren om het piek poort verbruik per client te bepalen. Daarnaast moet een piek factor worden gebruikt voor het poort gebruik (minimaal 4). 
  
 **Gebruik de volgende formule voor het berekenen van het aantal ondersteunde apparaten per IP-adres:**
  
Maximum aantal ondersteunde apparaten per openbaar IP-adres = (64.000-beperkte poorten)/(piek poort verbruik + piek factor)
  
 **Als u bijvoorbeeld de volgende beweringen waar is:**
  
- **Beperkte poorten:** 4.000 voor het besturingssysteem

- **Piek verbruik van poort:** 6 per apparaat

- **Piek factor:** 4

Vervolgens worden de maximum aantal ondersteunde apparaten achter één openbaar IP-adres = (64.000-4000)/(6 + 4) = 6.000
  
Met de release van het Office 365-hosting pakket, dat deel uitmaakt van de updates van september 2011 voor Microsoft Office Outlook 2007 of november 2011 voor Microsoft Outlook of een latere update, kan het aantal verbindingen vanuit Outlook (zowel Office Outlook 2010 met Service Pack 2 en Outlook 2007) niet worden gebruikt voor Exchange. U moet een factor opgeven voor de verschillende besturingssystemen, gebruikersgedrag en om het minimum en maximum aantal poorten te bepalen dat uw netwerk nodig heeft op piek.
  
Als u meer apparaten wilt ondersteunen achter één openbaar IP-adres, volgt u de stappen voor het bepalen van het maximum aantal apparaten dat kan worden ondersteund:
  
Controleer netwerkverkeer om het piek poort verbruik per client te bepalen. U dient deze gegevens te verzamelen:
  
- Vanaf meerdere locaties
    
- Vanaf meerdere apparaten
    
- Op meerdere momenten
    
Gebruik de bovenstaande formule voor het berekenen van het maximum aantal gebruikers per IP-adres dat wordt ondersteund in de omgeving.
  
Er zijn verschillende manieren om de belasting van de client te verdelen over extra openbare IP-adressen. Welke strategieën beschikbaar zijn, is afhankelijk van de mogelijkheden van de corporate Gateway-oplossing. De eenvoudigste oplossing is het segmenteren van de adresruimte van uw gebruikers en het statisch toewijzen van een aantal IP-adressen aan elke gateway. U kunt ook een groep IP-adressen gebruiken om een andere optie te gebruiken. Het voordeel van de adresgroep is dat het veel dynamischer en minder waarschijnlijk moet worden aangepast naarmate de basis van de gebruikers breidt.
  
## <a name="see-also"></a>Zie ook

[Office 365-eindpunten beheren](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Veelgestelde vragen over Office 365-eindpunten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
