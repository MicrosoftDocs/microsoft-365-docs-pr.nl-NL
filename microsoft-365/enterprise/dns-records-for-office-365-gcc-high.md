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
description: 'Samenvatting: DNS-records voor Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689152"
---
# <a name="dns-records-for-office-365-gcc-high"></a>DNS-records voor Office 365 GCC High

*Dit artikel is van toepassing op Office 365 GCC Hoog en Microsoft 365 GCC Hoog*

Als onderdeel van onboarding Office 365 GCC High, moet u uw SMTP- en SIP-domeinen toevoegen aan uw Online Services-tenant.  U doet dit met de New-MsolDomain cmdlet in Azure AD PowerShell of gebruik de [Azure Government Portal](https://portal.azure.us) om het proces van het toevoegen van het domein te starten en het eigendom te bewijzen.

Nadat u uw domeinen hebt toegevoegd aan uw tenant en hebt gevalideerd, gebruikt u de volgende richtlijnen om de juiste DNS-records toe te voegen voor de onderstaande services.  Mogelijk moet u de onderstaande tabel aanpassen aan de behoeften van uw organisatie met betrekking tot de inkomende MX-record(s) en eventuele bestaande Exchange Autodiscover-record(s) die u hebt.  We raden u ten zeerste aan deze DNS-records te coördineren met uw berichtenteam om uitval of onjuiste bezorging van e-mail te voorkomen.

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | Hostnaam | Wijst naar adres of waarde | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *tenant*.mail.protection.office365.us (zie hieronder voor meer informatie) | 1 uur |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 uur |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 uur |

### <a name="exchange-autodiscover-record"></a>Exchange Autodiscover-record

Als u on-premises Exchange Server, raden we u aan uw bestaande record op zijn plaats te laten terwijl u migreert naar Exchange Online en deze record bij te werken nadat u de migratie hebt voltooid. 

### <a name="exchange-online-mx-record"></a>Exchange Online MX-record

De MX-recordwaarde voor uw geaccepteerde domeinen volgt een standaardnotatie zoals hierboven vermeld: *tenant*.mail.protection.office365.us, die *tenant* vervangt door het eerste deel van de standaardtenatienaam.

Als de naam van uw tenant bijvoorbeeld contoso.onmicrosoft.us,  gebruikt u contoso.mail.protection.office365.us als de waarde voor uw MX-record.

## <a name="skype-for-business-online"></a>Skype voor Bedrijven Online

### <a name="cname-records"></a>CNAME-records

| Type | Hostnaam | Wijst naar adres of waarde | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 uur |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 uur |

### <a name="srv-records"></a>SRV-records

| Type | Service | Protocol | Poort | Gewicht | Priority | Naam | Doel | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 uur |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 uur |

## <a name="additional-dns-records"></a>Extra DNS-records

> [!IMPORTANT]
> Als u een bestaande *msoid* CNAME-record in  uw DNS-zone hebt, moet u de record op dit moment verwijderen uit DNS.  De msoidrecord is niet compatibel met Microsoft 365 Enterprise Apps *(voorheen Office 365 ProPlus)* en voorkomt dat activering slaagt.
