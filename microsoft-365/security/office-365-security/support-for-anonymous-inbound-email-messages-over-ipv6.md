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
# <a name="support-for-anonymous-inbound-email-messages-over-ipv6"></a><span data-ttu-id="e3cde-103">Ondersteuning voor anonieme binnenkomende e-mailberichten via IPv6</span><span class="sxs-lookup"><span data-stu-id="e3cde-103">Support for anonymous inbound email messages over IPv6</span></span>

<span data-ttu-id="e3cde-104">Ondersteuning voor Exchange Online Protection (EOP) en Exchange Online en ondersteuning voor het ontvangen van anonieme binnenkomende e-mailberichten via IPv6-berichten van afzenders die geen berichten verzenden via TLS (Transport Layer Security).</span><span class="sxs-lookup"><span data-stu-id="e3cde-104">Exchange Online Protection (EOP) and Exchange Online support receiving anonymous inbound email messages over IPv6 communications from senders who don't send messages over Transport Layer Security (TLS).</span></span> <span data-ttu-id="e3cde-105">U zich aanmelden om berichten via IPv6 te ontvangen door deze functionaliteit aan te vragen [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home)bij Microsoft Support door het Microsoft 365-beheercentrum te openen op, op **Ondersteuning**te klikken en vervolgens op **Nieuw serviceverzoek**te klikken ).</span><span class="sxs-lookup"><span data-stu-id="e3cde-105">You can opt-in to receive messages over IPv6 by requesting this functionality from Microsoft Support by opening the Microsoft 365 admin center at [https://admin.microsoft.com/adminportal/home](https://admin.microsoft.com/adminportal/home), clicking **Support**, and then clicking **New service request**).</span></span> <span data-ttu-id="e3cde-106">Als u zich niet opt-inschrijft voor IPv6, blijft u berichten ontvangen via IPv4.</span><span class="sxs-lookup"><span data-stu-id="e3cde-106">If you don't opt-in to IPv6 you'll continue to receive messages over IPv4.</span></span>
  
<span data-ttu-id="e3cde-107">Afzenders die berichten naar de service verzenden via IPv6 moeten voldoen aan de volgende twee vereisten:</span><span class="sxs-lookup"><span data-stu-id="e3cde-107">Senders who transmit messages to the service over IPv6 must comply with the following two requirements:</span></span>
  
1. <span data-ttu-id="e3cde-108">Het verzendende IPv6-adres moet een geldige PTR-record hebben[(reverse DNS-record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) van het verzendende IPv6-adres).</span><span class="sxs-lookup"><span data-stu-id="e3cde-108">The sending IPv6 address must have a valid PTR record ([reverse DNS record](https://en.wikipedia.org/wiki/Reverse_DNS_lookup) of the sending IPv6 address).</span></span> 
    
2. <span data-ttu-id="e3cde-109">De afzender moet slagen voor de SPF-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span><span class="sxs-lookup"><span data-stu-id="e3cde-109">The sender must pass either SPF verification (defined in [RFC 7208](https://tools.ietf.org/html/rfc7208)) or [DKIM verification](https://dkim.org/) (defined in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).</span></span>
    
<span data-ttu-id="e3cde-110">Voldoen aan deze vereisten is verplicht, ongeacht uw configuratie voordat u zich aankiest voor IPv6.</span><span class="sxs-lookup"><span data-stu-id="e3cde-110">Meeting these requirements is mandatory regardless of your configuration prior to opting-in to IPv6.</span></span> <span data-ttu-id="e3cde-111">Als aan beide vereisten is voldaan, gaat het bericht door de normale filtering van e-mailberichten die door de service worden geleverd.</span><span class="sxs-lookup"><span data-stu-id="e3cde-111">If both requirements are met, the message will go through normal email message filtering provided by the service.</span></span> <span data-ttu-id="e3cde-112">Als niet wordt voldaan aan het ene of het andere bericht, wordt het bericht geweigerd met een van de volgende 450 reacties:</span><span class="sxs-lookup"><span data-stu-id="e3cde-112">If one or the other isn't met, the message will be rejected with one of the following 450 responses:</span></span>
  
-  `450 4.7.25 Service unavailable, sending IPv6 address [2a01:111:f200:2004::240] must have reverse DNS record.`
    
-  `450 4.7.26 Service unavailable, message sent over IPv6 [2a01:111:f200:2004::240] must pass either SPF or DKIM validation.`
    
<span data-ttu-id="e3cde-113">Als u niet bent aangemeld om berichten via IPv6 te ontvangen en de afzender een bericht via IPv6 probeert te forceren door handmatig verbinding te maken met de e-mailserver, wordt het bericht geweigerd met een antwoord van 550 dat lijkt op het volgende:</span><span class="sxs-lookup"><span data-stu-id="e3cde-113">If you aren't opted in to receive messages over IPv6 and the sender tries to force a message over IPv6 by manually connecting to the mail server, the message will be rejected with a 550 response that looks similar to the following:</span></span>
  
 `550 5.2.1 Service unavailable, [contoso.com] does not accept email over IPv6.`
  
## <a name="for-more-information"></a><span data-ttu-id="e3cde-114">Voor meer informatie</span><span class="sxs-lookup"><span data-stu-id="e3cde-114">For more information</span></span>

[<span data-ttu-id="e3cde-115">Ondersteuning voor validatie van door DKIM ondertekende berichten</span><span class="sxs-lookup"><span data-stu-id="e3cde-115">Support for validation of DKIM signed messages</span></span>](support-for-validation-of-dkim-signed-messages.md)
  

