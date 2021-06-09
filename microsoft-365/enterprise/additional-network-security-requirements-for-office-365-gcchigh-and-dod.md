---
title: Aanvullende netwerkbeveiligingsvereisten voor Office 365 GCC High en DoD
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
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Overzicht: Office 365 GCC High en DoD hebben extra netwerkbeveiligingsvereisten'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689239"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Aanvullende vereisten voor netwerkbeveiliging voor Office 365 GCC High en DOD

*Dit artikel is van toepassing op Office 365 GCC Hoge, Office 365 DOD, Microsoft 365 GCC Hoog en Microsoft 365 DOD.*

Office 365 GCC High en DOD zijn veilige cloudomgevingen om te voldoen aan de behoeften van de Amerikaanse overheid en haar leveranciers en contractanten.  Deze cloudomgevingen hebben extra netwerkbeperkingen waarvoor de services toegang hebben tot externe eindpunten.

GCC Hoge en dod-klanten die federatief identiteiten of hybride co-bestaan willen gebruiken, kunnen microsoft verplichten om inkomende en/of uitgaande toegang toe te staan tot uw bestaande on-premises implementaties.  Voorbeelden van deze activiteiten zijn:

* Gebruik van federatief identiteiten (met Active Directory Federation Services of soortgelijke ondersteunde STS)
* Hybride coëxistentie met een on-premises Exchange Server of Skype voor Bedrijven implementatie
* Migratie van bestaande gebruikersinhoud vanuit een on-premises systeem

Als u wilt toestaan dat de service met  uw on-premises eindpunten communiceert, moet u een e-mail verzenden naar Office 365 engineering voor netwerkwijzigingen.

> [!WARNING]
> Alle aanvragen hebben een SLA van drie **weken** en kunnen niet worden versneld vanwege de vereiste beveiligings- en compliancecontroles en implementatiepijplijnen.  Dit omvat initiële onboarding-netwerkaanvragen en eventuele wijzigingen nadat u naar de service bent gemigreerd.  Zorg ervoor dat uw netwerkteams op de hoogte zijn van deze tijdlijn en neem deze op in hun planningscyclus.

Stuur een e-mail [naar Office 365 Government whitelist met](mailto:o365gwlt@microsoft.com) de volgende informatie:

* **Naar**: [Office 365 Government Whitelist voor netwerken](mailto:o365gwlt@microsoft.com)
* **Van**: Een tenantbeheerder: de e-mail verzenden **moet overeenkomen** met een globale beheerder in uw tenant
* **E-mailonderwerp:** Office 365 GCC High Network Request - contoso.onmicrosoft.us (vervang dit door uw tenantnaam)

De hoofd van het bericht moet de volgende gegevens bevatten:

* Uw Microsoft Online Services-tenantnaam (dat wil zeggen contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Een e-maildistributielijst met microsoft voor on-going communicatie met betrekking tot netwerkwijzigingen en/of opvolging van ongeldige subnetten
* Geef aan of u van plan bent Microsoft Teams hybride co-existence te gebruiken met uw on-premises implementaties
* Federatief identiteitssysteem voor extern toegankelijke URL (bijvoorbeeld sts.contoso.com) en IP-adresbereik in CIDR-notatie (bijvoorbeeld 10.1.1.0/28)
* On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation
* Extern toegankelijke URL en IP-adresbereik voor Exchange Server on-premises implementatie in CIDR-notatie
* Extern toegankelijke URL en IP-adresbereik voor Skype voor Bedrijven on-premises implementatie in CIDR-notatie

Houd om veiligheids- en nalevingsredenen rekening met de volgende beperkingen voor uw aanvraag:

* Er is een beperking van vier subnets per tenant
* Subnetten moeten in CIDR-notatie zijn (bijvoorbeeld 10.1.1.0/28)
* Subnetbereiken mogen niet groter zijn dan /24
* We **kunnen geen** aanvragen voor toegang tot commerciële cloudservices toestaan (commerciële Office 365, Google G-Suite, Amazon Web Services, enzovoort)

Wanneer uw aanvraag is ontvangen en goedgekeurd door Microsoft, is er een SLA van drie weken voor implementatie en kan deze niet worden versneld.  U ontvangt een eerste bevestiging wanneer we uw aanvraag hebben ontvangen en een definitieve bevestiging zodra deze is voltooid.
