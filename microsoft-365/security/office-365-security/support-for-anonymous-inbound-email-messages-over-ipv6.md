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
description: Beheerder kan informatie krijgen over het configureren van ondersteuning voor anonieme inkomende e-mail vanuit IPv6-bronnen in Exchange Online en Exchange Online Protection.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 63c9434fbd1f69c0cbd3145717b712857eb17e28
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290271"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-microsoft-365"></a>Ondersteuning toevoegen voor anonieme inkomende e-mail via IPv6 in Microsoft 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Van toepassing op**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Abonnement 1 en abonnement 2 voor Microsoft Defender voor Office 365](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Microsoft 365-organisaties met Exchange Online-postvakken en zelfstandige Organisaties van Exchange Online Protection (EOP) zonder Exchange Online-postvakken ondersteunen anonieme inkomende e-mail via IPv6. De bron-IPv6-e-mailserver moet aan beide van de volgende vereisten voldoen:

- Het IPv6-bronadres moet een geldige REVERSE DNS lookup-record (PTR) hebben waarmee de bestemming de domeinnaam kan vinden op basis van het IPv6-adres.

- De afzender moet SPF-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](http://dkim.org/) (gedefinieerd in [RFC 6376) doorgeven.](https://www.rfc-editor.org/rfc/rfc6376.txt)

Voordat uw organisatie anonieme inkomende e-mail kan ontvangen via IPv6, moet een beheerder contact opnemen met microsoft-ondersteuning en hier om vragen. Zie Contact opnemen met ondersteuning voor zakelijke producten - Help voor beheerders voor instructies over het openen [van een ondersteuningsaanvraag.](../../admin/contact-support-for-business-products.md)

Nadat anonieme ondersteuning voor inkomende IPv6-berichten is ingeschakeld in uw organisatie, wordt het bericht gefilterd volgens de normale berichtenfilters die door de service worden aangeboden.

## <a name="troubleshooting"></a>Problemen oplossen

- Als de bron-e-mailserver geen IPv6 reverse DNS-opzoekrecord heeft, worden de berichten geweigerd met de volgende fout:

  > 450 4.7.25 Service niet beschikbaar, verzenden van IPv6-adres [2a01:111:f200:2004::240] moet reverse DNS-record hebben.

- Als de afzender niet door SPF- of DKIM-validatie komt, worden de berichten geweigerd met de volgende fout:

  > 450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet SPF- of DKIM-validatie doorgeven.

- Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt afgemeld, wordt het bericht met de volgende fout geweigerd:

  > 550 5.2.1 Service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.

## <a name="related-topics"></a>Verwante onderwerpen

[Ondersteuning voor validatie van DKIM-ondertekende berichten](support-for-validation-of-dkim-signed-messages.md)
