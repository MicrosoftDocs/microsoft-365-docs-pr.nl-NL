---
title: Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: De beheerder kan leren hoe u ondersteuning configureert voor anonieme inkomende e-mail van IPv6-bronnen in Exchange Online en Exchange Online Protection.
ms.openlocfilehash: 7384c1044cc02ec20079dc03068c2ca99e68d2c2
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826775"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Ondersteuning toevoegen voor anonieme inkomende e-mail via IPv6 in Microsoft 365

Microsoft 365-organisaties met postvakken van Exchange Online en standalone Exchange Online Protection (EOP)-organisaties zonder Exchange Online-postvakken ondersteunen anonieme inkomende e-mail via IPv6. De e-mailserver voor bron IPv6 moet aan de volgende vereisten voldoen:

- Het bron-IPv6-adres moet een geldige DNS-opzoek record (PTR) bevatten waarmee de bestemming de domeinnaam van het IPv6-adres kan vinden.

- De afzender moet authenticatie via SPF (gedefinieerd in [rfc 7208](https://tools.ietf.org/html/rfc7208)) of [dkim-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376](https://www.rfc-editor.org/rfc/rfc6376.txt)) passeren.

Voordat uw organisatie anonieme inkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met Microsoft ondersteuning en vragen. Zie [contact opnemen met ondersteuning voor bedrijfsproducten-Help voor beheerders](../../admin/contact-support-for-business-products.md)voor meer informatie over het openen van een ondersteuningsaanvraag.

Wanneer anoniem e-mailbericht ondersteuning voor anonieme ondersteuning in uw organisatie is ingeschakeld, wordt het bericht weergegeven met het filter voor normale berichten dat wordt geleverd door de service.

## <a name="troubleshooting"></a>Problemen oplossen

- Als de bron-e-mailserver geen IPv6-lookup record voor IPv6 bevat, worden de berichten genegeerd met de volgende fout:

  > de 4.7.25-service van 450 is niet beschikbaar en het verzenden van IPv6-adres [2a01:111: F200:2004:: 240] moet omgekeerde DNS-record hebben.

- Als de afzender SPF-of DKIM-validatie niet doorgeeft, worden de berichten genegeerd met de volgende fout:

  > 450 4.7.26 service niet beschikbaar, bericht verzonden via IPv6 [2a01:120: F200:2004:: 240] moet SPF-of DKIM validering passeren.

- Als u probeert anonieme IPv6-berichten te ontvangen voordat u zich aanmeldt, wordt het bericht genegeerd met de volgende fout:

  > 550 5.2.1-service niet beschikbaar, [contoso.com] aanvaardt geen e-mail via IPv6.

## <a name="related-topics"></a>Verwante onderwerpen

[Ondersteuning voor validatie van DKIM-ondertekende berichten](support-for-validation-of-dkim-signed-messages.md)