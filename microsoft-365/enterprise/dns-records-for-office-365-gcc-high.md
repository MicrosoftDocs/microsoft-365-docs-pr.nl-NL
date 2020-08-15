---
title: DNS-records voor Office 365 GCC High
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Overzicht: DNS-records voor Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689152"
---
# <a name="dns-records-for-office-365-gcc-high"></a>DNS-records voor Office 365 GCC High

*Dit artikel is van toepassing op Office 365 GCC High en Microsoft 365 GCC High*

Als onderdeel van de onboarding van Office 365 GCC, moet u uw SMTP-en SIP-domeinen toevoegen aan uw online services-Tenant.  U doet dit met behulp van de New-MsolDomain-cmdlet in azure AD PowerShell of de [Azure Government Portal](https://portal.azure.us) gebruiken om het proces voor het toevoegen van een domein en het eigendom ervan te starten.

Wanneer u uw domein hebt toegevoegd aan de Tenant en gevalideerd, gebruikt u de volgende richtlijnen om de juiste DNS-records voor de services toe te voegen.  Mogelijk moet u de onderstaande tabel aanpassen aan de behoeften van uw organisatie met betrekking tot de inkomende MX-record (s) en eventuele bestaande Exchange Autodiscover-record (s) die u hebt geïnstalleerd.  We raden u ten zeerste aan om deze DNS-records met uw berichten team te coördineren om te voorkomen dat u een e-mailbericht veroudert of niet.

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | Host name | Verwijst naar het adres of de waarde | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *Tenant*. mail.Protection.office365.us (zie hieronder voor meer informatie) | 1 uur |
| TXT | - | @ | v = spf1 include:SPF. Protection. office365. us-all | 1 uur |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 uur |

### <a name="exchange-autodiscover-record"></a>Record Exchange automatisch opsporen

Als u Exchange Server on-premises hebt, wordt u aangeraden uw bestaande record te verlaten terwijl u migreert naar Exchange Online en de record bij te werken wanneer u de migratie hebt voltooid. 

### <a name="exchange-online-mx-record"></a>MX-record voor Exchange Online

De MX-recordwaarde voor uw geaccepteerde domeinen volgt een standaardindeling zoals hierboven aangegeven: *Tenant*. mail.Protection.office365.us, waarbij de *Tenant* wordt vervangen door het eerste deel van de standaardnaam van de Tenant.

Als de naam van de Tenant bijvoorbeeld contoso.onmicrosoft.us is, gebruikt u **contoso.mail.Protection.office365.us** als de waarde voor uw MX-record.

## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

### <a name="cname-records"></a>CNAME-records

| Type | Host name | Verwijst naar het adres of de waarde | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 uur |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 uur |

### <a name="srv-records"></a>SRV-records

| Type | Service | Protocol | Poort | Dikte | Priority | Naam | Doel | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_TLS | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 uur |
| SRV | \_sipfederationtls | \_TCP | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 uur |

## <a name="additional-dns-records"></a>Extra DNS-records

> [!IMPORTANT]
> Als u een bestaande *msoid* CNAME-record hebt in uw DNS-zone, moet u de record op dit moment **verwijderen** uit DNS.  De msoid-record is niet compatibel met Microsoft 365 Enterprise *-apps (voorheen Office 365 ProPlus)* en kan de activering van de Cloud verhinderen.
