---
title: Beheerfuncties voor toegankelijkheid in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
f1.keywords:
- NOCSH
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Dit artikel bevat een overzicht van de beheerbare besturingselementen en gegevens categorisatie in Microsoft 365.
ms.openlocfilehash: b5063f89e89b6cffffda53a5df3088a80f89c242
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689001"
---
# <a name="administrative-access-controls-in-microsoft-365"></a>Beheerfuncties voor toegankelijkheid in Microsoft 365 

Microsoft heeft sterk geïnvesteerd in systemen en besturingselementen waarmee de meeste Microsoft 365-bewerkingen worden geautomatiseerd en de toegang tot de inhoud van klanten door Microsoft wordt beperkt. Mensen die de service beheersen, en software exploiteert de dienst. Daardoor kan Microsoft Microsoft 365 beheren op schaal en de Risico's van interne bedreigingen voor klant inhoud beheren.

Standaard hebben Microsoft-technici een beheerdersbevoegdheid voor de permanente beheerder en is er geen toegang tot de inhoud van klanten in Microsoft 365. Een Microsoft-engineer kan de inhoud van een klant beperkt, gecontroleerd en beveiligd zijn gedurende een beperkte periode. Access is alleen indien nodig voor serviceactiviteiten en alleen wanneer deze is goedgekeurd door een lid van Microsoft Senior Management. Voor klanten-lockbox-licenties biedt de klant toestemming voor toegang tot de inhoud van de klant in Microsoft 365.

Microsoft biedt online services via meerdere vormen van Cloud levering:

- **Openbare wolken:** Waaronder meerdere Tenant versies van Microsoft 365, Azure en andere services die worden gehost in Noord-Amerika, Zuid-Amerika, Europa, Zuid-Oost, Australië enzovoort.
- **Nationale wolken:** Omvat alle soevereine en derden Bedien bare wolken buiten de Verenigde Staten (met uitzondering van de Verenigde Staten), zoals Microsoft 365 in China (beheerd door 21Vianet), en Microsoft 365 in Duitsland (beheerd door Microsoft, maar onder een model waarin een Duitse gegevensbeheerder, Duitse Telekom, besturingselementen en monitoren de toegang van klantgegevens en systemen van klantgegevens bevat
- **Overheids wolken:** Dit omvat Microsoft 365 en Azure Services die beschikbaar zijn voor klanten van de Verenigde Staten.

Voor de toepassing van dit artikel omvat Microsoft 365-Services:

- [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online)
- [Exchange Online Protection](https://docs.microsoft.com/Office365/SecurityCompliance/eop/exchange-online-protection-overview)
- [SharePoint Online](https://docs.microsoft.com/sharepoint/sharepoint-online)
- [OneDrive voor Bedrijven](https://docs.microsoft.com/OneDrive/onedrive)
- [Skype voor Bedrijven](https://docs.microsoft.com/SkypeForBusiness/skype-for-business-online)
- [Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/Teams-overview)
- [Yammer](https://docs.microsoft.com/yammer/yammer-landing-page)

## <a name="microsoft-365-access-controls"></a>Microsoft 365 Access-besturingselementen

Microsoft categoriseert Microsoft 365-gegevens als klantgegevens of een ander type gegevens voor toegangsbeheer doeleinden.

### <a name="customer-data"></a>Klantgegevens

Klantgegevens zijn alle gegevens verstrekt door of namens een klant met behulp van Microsoft 365-Services. Deze klant inhoud wordt direct gemaakt of geüpload door Microsoft 365-gebruikers, waaronder:

- Sturen
- SharePoint Online-inhoud
- Chatberichten
- Agenda-items
- Faxdocumenten
- Contactpersonen
- Identificeerbare informatie van door de gebruiker gerichte informatie (EUII) (gegevens die uniek is voor een gebruiker of die kan worden gekoppeld aan een individuele gebruiker, maar bevat geen klant inhoud)

### <a name="other-types-of-data"></a>Andere gegevenstypen

Andere gegevenstypen zijn:

- **Account gegevens:** Inclusief beheergegevens (informatie van beheerders die worden verstrekt door beheerders wanneer ze zich aanmelding of de aankoop van Services), en betalingsgegevens (informatie over betaalinstrumenten, zoals creditcardgegevens).
- **Organisatie-identificeerbare informatie:** Bevat gegevens die worden gebruikt voor het identificeren van een Tenant, gebruiksgegevens en die niet kunnen worden gekoppeld aan een individuele gebruiker of die is opgenomen in de inhoud van de klant.
- **Systeem metagegevens:** Bevat servicelogboeken die configuratie-instellingen, systeemstatus, Microsoft IP-adressen en technische informatie over abonnementen en tenants bevatten.

Microsoft heeft de mechanismen voor toegangsbeheer opgezet om te voorkomen dat niemand toegang heeft tot klantgegevens of toegangsbeheer gegevens. Met toegangsbeheer gegevens wordt de toegang tot andere gegevenstypen of functies binnen de omgeving beheerd, waaronder toegang tot inhoud van de klant of EUII, Microsoft-wachtwoorden, beveiligingscertificaten en andere verificatie-gerelateerde gegevens. Methoden voor toegangsbeheer bieden ook bescherming tegen niet-goedgekeurde fysieke, logische of externe toegang tot de Microsoft 365-productieomgeving.

Er worden drie categorieën met toegangsbeheer voor Microsoft gebruikt voor de werking van Microsoft 365:

- Isolatie besturingselementen
- Personeels besturingselementen
- Technologie regeling

Met deze besturingselementen kunt u schadelijke acties in Microsoft 365 helpen voorkomen en detecteren. Naast de besturingselementen voor isolatie, medewerkers en technologie die door Microsoft worden gebruikt, is er een vierde categorie met besturingselementen: de functies die door klanten zijn geïmplementeerd.

Met Microsoft 365 kunt u gegevens beheren op dezelfde manier als gegevens worden beheerd in on-premises omgevingen. De persoon die een organisatie registreert voor Microsoft 365, wordt automatisch een globale beheerder. De globale beheerder heeft toegang tot alle functies in beheerportals en kan:

- Gebruikers maken of bewerken
- Beheerdersrollen toewijzen aan anderen
- Gebruikerswachtwoorden opnieuw instellen
- Gebruikerslicenties beheren
- Domeinen beheren
- Klanten-lockbox-aanvragen goedkeuren

We raden u aan elke organisatie minstens twee beheerdersaccounts te configureren. Voor grote Enterprise-organisaties wordt u aangeraden gespecialiseerde beheerdersaccounts voor verschillende functies aan te bieden.

Zie [beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/assign-admin-roles) en [beheerdersrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)toewijzen voor meer informatie over het toewijzen van beheerdersrollen en machtigingen.

## <a name="related-links"></a>Verwante koppelingen

- [Isolatie besturingselementen](microsoft-365-isolation-controls.md)
- [Personeels besturingselementen](microsoft-365-personnel-controls.md)
- [Technologie regeling](microsoft-365-technology-controls.md)
- [Toegangsbeheer controleren en controleren](microsoft-365-monitoring-and-auditing-access-controls.md)
- [Enterprise Access-besturingselementen voor Yammer](microsoft-365-yammer-enterprise-access-controls.md)
