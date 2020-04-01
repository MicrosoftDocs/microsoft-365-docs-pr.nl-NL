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
description: Beheerder kan in Exchange Online en Exchange Online Protection leren hoe u ondersteuning configureert voor anonieme binnenkomende e-mail van IPv6-bronnen.
ms.openlocfilehash: 67e839249d41381be22bbccf6b09d1616c387c66
ms.sourcegitcommit: 748bc3484b7ccbd65b558f495b6fa42196c3c571
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/01/2020
ms.locfileid: "43083639"
---
# <a name="add-support-for-anonymous-inbound-email-over-ipv6-in-office-365"></a>Ondersteuning toevoegen voor anonieme binnenkomende e-mail via IPv6 in Office 365

Office 365-organisaties met Exchange Online-postvakken en zelfstandige Exchange Online Protection -organisaties (EOP)-organisaties zonder Exchange Online-postvakken ondersteunen anonieme binnenkomende e-mail via IPv6. De e-mailserver van de bron-IPv6 moet aan beide volgende vereisten voldoen:

- Het bron-IPv6-adres moet een geldige reverse DNS lookup (PTR)-record hebben waarmee de bestemming de domeinnaam kan vinden vanaf het IPv6-adres.

- De afzender moet slagen voor spf-verificatie (gedefinieerd in [RFC 7208)](https://tools.ietf.org/html/rfc7208)of [DKIM-verificatie](https://dkim.org/) (gedefinieerd in [RFC 6376).](https://www.rfc-editor.org/rfc/rfc6376.txt)

Voordat uw organisatie anonieme binnenkomende e-mail via IPv6 kan ontvangen, moet een beheerder contact opnemen met microsoft-ondersteuning en erom vragen:

1. Open het Microsoft 365-beheercentrum bij <https://admin.microsoft.com/adminportal/home> en klik op **Help** (?).

2. Typ in de **help nodig?** flyout die wordt weergegeven, typ iets beschrijvends in het zoekvak (bijvoorbeeld 'vraag anonieme inkomende IPv6-e-mail' aan en druk op ENTER.

3. Klik onder aan de pagina op **Ondersteuning voor contact opnemen**.

4. Vul op de **ondersteuningspagina Van contact** die wordt weergegeven de gegevens in en verifieer deze (scroll naar beneden als dat nodig is) en klik vervolgens op **Contact met mij**opnemen.

Nadat anonieme inkomende IPv6-berichtondersteuning is ingeschakeld in uw organisatie, wordt het bericht door de normale berichtfiltering uitgevoerd die door de service wordt geleverd.

## <a name="troubleshooting"></a>Problemen oplossen

- Als de brone-mailserver geen IPv6 reverse DNS-opzoekrecord heeft, worden de berichten met de volgende fout geweigerd:

  > 450 4.7.25 Service niet beschikbaar, het verzenden van IPv6-adres [2a01:111:f200:2004::240] moet een omgekeerd DNS-record hebben.

- Als de afzender de SPF- of DKIM-validatie niet doorstaat, worden de berichten met de volgende fout geweigerd:

  > 450 4.7.26 Service niet beschikbaar, bericht verzonden via IPv6 [2a01:111:f200:2004::240] moet slagen voor SPF- of DKIM-validatie.

- Als u anonieme IPv6-berichten probeert te ontvangen voordat u zich hebt aangemeld, wordt het bericht met de volgende fout geweigerd:

  > 550 5.2.1 Service niet beschikbaar, [contoso.com] accepteert geen e-mail via IPv6.

## <a name="for-more-information"></a>Voor meer informatie

[Ondersteuning voor validatie van ondertekende DKIM-berichten](support-for-validation-of-dkim-signed-messages.md)
