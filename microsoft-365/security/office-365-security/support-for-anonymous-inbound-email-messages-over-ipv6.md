---
title: Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6
f1.keywords:
- NOCSH
author: chrisda
ms.author: chrisda
manager: chrisda
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: b68df621-0a5f-4824-8abc-41e0c4fd1398
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Beheerder kan informatie krijgen over het configureren van ondersteuning voor anonieme inkomende e-mail uit IPv6-bronnen in Exchange Online en Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: df06891401802d212cbfdb55085662901f5546e9
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204637"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Ondersteuning toevoegen voor anonieme inkomende e-mail via IPv6 in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige EOP-organisaties (Exchange Online Protection) zonder Exchange Online-postvakken ondersteunen anonieme inkomende e-mail via IPv6. De bron-IPv6-e-mailserver moet aan beide van de volgende vereisten voldoen:

- Het bron-IPv6-adres moet een geldige PTR-record (Reverse DNS Lookup) hebben waarmee de bestemming de domeinnaam kan vinden op het IPv6-adres.

- De afzender moet SPF-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](http://dkim.org/) (gedefinieerd in [RFC 6376) doorgeven.](https://www.rfc-editor.org/rfc/rfc6376.txt)

Voordat uw organisatie anonieme inkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met microsoft-ondersteuning en om deze vragen. Zie Contact opnemen met ondersteuning voor zakelijke producten - Help voor beheerders voor instructies over het openen van een [ondersteuningsaanvraag.](../../admin/contact-support-for-business-products.md)

Nadat anonieme inkomende IPv6-berichtondersteuning is ingeschakeld in uw organisatie, wordt het bericht door de normale berichtenfilters van de service gefilterd.

## <a name="troubleshooting"></a>Problemen oplossen

- Als de bron-e-mailserver geen reverse DNS-opzoekrecord voor IPv6 heeft, worden de berichten met de volgende fout geweigerd:

  > 450 4.7.25 Service niet beschikbaar, verzenden van IPv6-adres [2a01:111:f200:2004::240] moet reverse DNS-record hebben.

- Als de afzender niet door SPF of DKIM-validatie komt, worden de berichten met de volgende fout geweigerd:

  > 450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet SPF- of DKIM-validatie passeren.

- Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt afgemeld, wordt het bericht met de volgende fout geweigerd:

  > 550 5.2.1 Service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.

## <a name="related-topics"></a>Verwante onderwerpen

[Ondersteuning voor validatie van DKIM-ondertekende berichten](support-for-validation-of-dkim-signed-messages.md)
