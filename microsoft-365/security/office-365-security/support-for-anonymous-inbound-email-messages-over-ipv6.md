---
title: Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Admin kan leren hoe u ondersteuning voor anonieme binnenkomende e-mail van IPv6-bronnen configureert in Exchange Online en Exchange Online Protection.
ms.openlocfilehash: fbbcba3631c7b2a7060f07011c119ee973fdf4af
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818707"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6 in Microsoft 365

Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken ondersteunen anonieme binnenkomende e-mail via IPv6. De iPv6-e-mailserver voor bron moet aan beide volgende vereisten voldoen:

- Het bron-IPv6-adres moet een geldige REVERSE DNS-lookup (PTR)-record hebben waarmee de bestemming de domeinnaam kan vinden vanaf het IPv6-adres.

- De afzender moet slagen voor de SPF-verificatie (gedefinieerd in [RFC 7208](https://tools.ietf.org/html/rfc7208)) of [de DKIM-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)).

Voordat uw organisatie anonieme binnenkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met microsoft-ondersteuning en erom vragen. Zie [Contact opnemen met ondersteuning voor zakelijke producten - Help voor beheerders](../../admin/contact-support-for-business-products.md).

Nadat anonieme ondersteuning voor binnenkomende IPv6-berichten is ingeschakeld in uw organisatie, gaat het bericht door de normale berichtfiltering die door de service wordt geleverd.

## <a name="troubleshooting"></a>Problemen oplossen

- Als de brone-mailserver geen IPv6 reverse DNS-opzoekrecord heeft, worden de berichten geweigerd met de volgende fout:

  > 450 4.7.25 Service niet beschikbaar, verzenden van IPv6-adres [2a01:111:f200:2004::240] moet reverse DNS-record hebben.

- Als de afzender de SPF- of DKIM-validatie niet doorstaat, worden de berichten geweigerd met de volgende fout:

  > 450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet SPF- of DKIM-validatie doorstaan.

- Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt aangemeld, wordt het bericht geweigerd met de volgende fout:

  > 550 5.2.1-service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.

## <a name="related-topics"></a>Verwante onderwerpen

[Ondersteuning voor validatie van DKIM-ondertekende berichten](support-for-validation-of-dkim-signed-messages.md)