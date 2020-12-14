---
title: Verbind uw domein met Microsoft 365
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Lees hier hoe u uw domein kunt verifiëren en DNS-records kunt maken met Microsoft 365.
ms.custom:
- okr_smb
- AdminSurgePortfolio
ms.openlocfilehash: 206b435130e8e77ed1540432e3bbeff7f16463bf
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/11/2020
ms.locfileid: "49658177"
---
# <a name="connect-your-domain-to-microsoft-365"></a>Verbind uw domein met Microsoft 365

> [!NOTE]
> Als u geen domein toevoegt, maken de mensen in uw organisatie gebruik van het domein onmicrosoft.com voor hun e-mailadressen, totdat u dit wel doet. Het is belangrijk om een domein toe te voegen voordat u gebruikers toevoegt, zodat u die niet tweemaal hoeft in te stellen.

[Raadpleeg Veelgestelde vragen over domeinen](../setup/domains-faq.yml) als u hieronder niet kunt vinden wat u zoekt.

## <a name="add-an-mx-record-so-email-for-your-domain-will-come-to-microsoft"></a>Voeg een MX-record toe zodat e-mail voor uw domein naar Microsoft wordt verzonden

U ontvangt de informatie voor de MX-record via de domeininstallatiewizard in Beheercentrum.

Voeg een nieuwe MX-record toe op de website van de hostingprovider.
Zorg dat de velden zijn ingesteld op de volgende waarden:

- Recordtype: `MX`
- Prioriteit: instellen op de hoogst beschikbare waarde, meestal `0`.
- Hostnaam: `@`
- Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.
- TTL: `3600‎` (of de standaardwaarde van uw provider)

Sla de record op en verwijder vervolgens alle andere MX-records.

## <a name="add-a-cname-record-to-connect-users-to-their-mailboxes"></a>Voeg een CNAME-record toe om gebruikers met hun mailbox verbinding te laten maken
U ontvangt de informatie voor de CNAME-records via de domeininstallatiewizard in Beheercentrum.

Voeg de volgende CNAME-record toe op de website van de hostingprovider. Zorg dat de velden zijn ingesteld op de volgende waarden voor elk:

- Recordtype: `CNAME (Alias)`
- Host: plak hier de waarden die u kopieert vanuit Beheercentrum.
- Verwijst naar adres: kopieer de waarde uit het Beheercentrum en plak deze hier.
- TTL: `3600‎` (of de standaardwaarde van uw provider)

## <a name="add-a-txt-record-to-help-prevent-spam"></a>Voeg een TXT-record toe om spam tegen te gaan
**Voordat u begint:** als u al een SPF-record voor uw domein hebt, hoeft u geen nieuwe voor Microsoft 365 aan te maken. In plaats daarvan voegt u de vereiste Microsoft 365-waarden toe aan de huidige record op de website van de hostingprovider, zodat u beschikt over *één* enkel SPF-record waarin beide waardensets zijn opgenomen.

Op de website van de hostingprovider bewerkt u de bestaande SPF-record of maakt u een nieuwe SPF-record aan.
Zorg dat de velden zijn ingesteld op de volgende waarden:

- Recordtype: `TXT (Text)`
- Host: `@`
- TXT-waarde: `v=spf1 include:spf.protection.outlook.com -all`
- TTL: `3600‎` (of de standaardwaarde van uw provider)

Sla de record op.

Voor het valideren van uw SPF-record, gebruikt u een van deze [SPF-validatiehulpmiddelen](https://docs.microsoft.com/office365/admin/setup/domains-faq#how-can-i-validate-spf-records-for-my-domain)

SPF is ontworpen om spoofing te voorkomen, maar er zijn spoofing-technieken waartegen SPF geen bescherming kan bieden. Om u tegen deze technieken te beschermen, moet u, nadat u SPF hebt geconfigureerd, ook DKIM en DMARC voor Microsoft 365 configureren.

Raadpleeg [DKIM gebruiken om uitgaande e-mail te valideren die wordt verzonden vanaf uw domein in Microsoft 365](https://technet.microsoft.com/library/mt695945%28v=exchg.150%29.aspx) en [DMARC gebruiken om e-mail te valideren in Microsoft 365](https://technet.microsoft.com/library/mt734386%28v=exchg.150%29.aspx).

Ga ten slotte terug naar de domeinconfiguratiewizard van het beheercentrum om uw installatie te voltooien.
