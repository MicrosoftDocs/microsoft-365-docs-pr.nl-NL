---
title: Ondersteuning voor anonieme binnenkomende e-mailberichten via IPv6
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
description: Meer informatie over het configureren van ondersteuning voor anonieme berichten uit IPv6-bronnen voor Exchange Online Protection en Exchange Online.
ms.openlocfilehash: 1cd38798aa644b79c8f1d6362edd17a515b5c98d
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42810442"
---
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a>Ondersteuning voor anonieme binnenkomende e-mailberichten via IPv6

Ondersteuning voor Exchange Online Protection (EOP) en Exchange Online en ondersteuning voor het ontvangen van anonieme binnenkomende e-mailberichten via IPv6-berichten van afzenders die geen berichten verzenden via TLS (Transport Layer Security). U zich aanmelden om berichten via IPv6 te ontvangen door deze functionaliteit aan te vragen [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)bij Microsoft Support door het Microsoft 365-beheercentrum te openen op, op **Ondersteuning**te klikken en vervolgens op **Nieuw serviceverzoek**te klikken ). Als u zich niet opt-inschrijft voor IPv6, blijft u berichten ontvangen via IPv4.
  
Afzenders die berichten naar de service verzenden via IPv6 moeten voldoen aan de volgende twee vereisten:
  
1. Het verzendende IPv6-adres moet een geldige PTR-record hebben[(reverse DNS-record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) van het verzendende IPv6-adres). 
    
2. De afzender moet slagen voor de SPF-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).
    
Voldoen aan deze vereisten is verplicht, ongeacht uw configuratie voordat u zich aankiest voor IPv6. Als aan beide vereisten is voldaan, gaat het bericht door de normale filtering van e-mailberichten die door de service worden geleverd. Als niet wordt voldaan aan het ene of het andere bericht, wordt het bericht geweigerd met een van de volgende 450 reacties:
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
Als u niet bent aangemeld om berichten via IPv6 te ontvangen en de afzender een bericht via IPv6 probeert te forceren door handmatig verbinding te maken met de e-mailserver, wordt het bericht geweigerd met een antwoord van 550 dat lijkt op het volgende:
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a>Voor meer informatie

[Ondersteuning voor validatie van door DKIM ondertekende berichten](support-for-validation-of-dkim-signed-messages.md)
  

