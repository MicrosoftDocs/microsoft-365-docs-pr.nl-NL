---
title: Aanvullende vereisten voor netwerkbeveiliging voor Office 365 GCC High en DoD
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
description: 'Overzicht: Office 365 GCC High en DoD hebben extra vereisten voor netwerkbeveiliging'
hideEdit: true
ms.openlocfilehash: 4817edfcea638324e26eb855d1ea33936be1bfb4
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689239"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a>Aanvullende vereisten voor netwerkbeveiliging voor Office 365 GCC High en DOD

*Dit artikel is van toepassing op Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High en Microsoft 365 DOD.*

Office 365 GCC High en DOD is een veilig cloudomgeving om te voldoen aan de behoeften van de Amerikaanse overheid en de leveranciers van de Verenigde Staten.  Voor deze Cloud omgevingen gelden extra netwerkbeperkingen voor de externe eindpunten van de services die toegang mogen hebben.

Voor klanten met een GCC voor hoog en DOD mag Microsoft de mogelijkheid van inkomende en/of uitgaande toegang tot uw bestaande on-premises implementaties worden vereist.  Voorbeelden van deze activiteiten zijn:

* Gebruik van federatieve identiteiten (met Active Directory Federation Services of vergelijkbaar ondersteunde STS)
* Hybride samenwerking met een on-premises Exchange-Server of Skype voor bedrijven-implementatie
* Migratie van bestaande gebruikers inhoud vanuit een on-premises systeem

Als u de service wilt toestaan om te communiceren met uw on-premises eindpunten, **moet** u een e-mailbericht verzenden naar Office 365 engineering voor netwerk wijzigingen.

> [!WARNING]
> Alle aanvragen hebben een sla met **drie weken** en kunnen niet worden getransporteerd vanwege de vereiste besturingselementen voor beveiliging en compliance en implementatie pijplijnen.  Dit geldt ook voor de aanvankelijke netwerkaanvragen voor onboarding en eventuele wijzigingen nadat u de service hebt gemigreerd naar de service.  Zorg ervoor dat uw netwerk teams op de hoogte zijn van deze tijdlijn en neem deze op in de plannings cyclussen.

Stuur een e-mailbericht naar [Office 365 Government Network whitelist](mailto:o365gwlt@microsoft.com) en voer de volgende informatie in:

* **Naar**: [Office 365 Government netwerk whitelist](mailto:o365gwlt@microsoft.com)
* **Van**: een tenantbeheerder-de e-mail verzenden **moet** overeenkomen met een contactpersoon van een globale beheerder in uw Tenant
* **Onderwerp e-mail**: Office 365 gcc High netwerk Request-contoso.onmicrosoft.us (vervangt dit door de naam van de Tenant)

De hoofdtekst van het bericht moet de volgende gegevens bevatten:

* De naam van de Microsoft Online service-Tenant (bijv. contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)
* Een distributielijst met e-mailberichten waarop Microsoft communiceert voor voortdurende berichten die betrekking hebben op netwerk wijzigingen en/of opvolgen voor ongeldige subnetten
* Aangeven of u van plan bent om hybride medewerking van Microsoft teams te gebruiken met uw on-premises implementaties
* Extern, federatieve identiteits systeem extern toegankelijke URL (bijvoorbeeld sts.contoso.com) en IP-adresbereik in CIDR-notatie (bijv. 10.1.1.0/28)
* URL en IP-adresbereik voor de intrekkingslijst van een certificeringsinstantie met een on-premises adreslijst
* Extern toegankelijke URL en IP-adresbereik voor Exchange Server on-premises implementatie in CIDR-notatie
* Extern toegankelijke URL en IP-adresbereik voor de on-premises implementatie van Skype voor bedrijven in CIDR-notatie

Ter bescherming van beveiligings-en nalevings redenen dient u rekening te houden met de volgende beperkingen voor uw aanvraag:

* Er geldt een limiet van vier subnetten per Tenant
* De subnetten moeten in CIDR-notatie staan (bijvoorbeeld 10.1.1.0/28)
* Subnetobject mag niet groter zijn dan/24
* We **kunnen geen** aanvragen indienen voor het verlenen van toegang tot commerciële cloudservices (commercial Office 365, Google G-suite, Amazon Web Services, etc.)

Wanneer uw aanvraag is ontvangen en goedgekeurd door Microsoft, is er een SLA met drie weken voor de implementatie en kan deze niet worden getransporteerd.  U ontvangt een eerste bevestiging wanneer uw aanvraag en de laatste bevestiging eenmaal zijn ontvangen.
