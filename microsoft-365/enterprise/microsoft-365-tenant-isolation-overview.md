---
title: Tenantisolatie in Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Dit artikel bevat een overzicht van hoe Microsoft tenantisolatie afdwingt in cloudservices zoals Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7c5be65186b75f6056a64b776e4f0d25bcd55eb1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923074"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Tenantisolatie in Microsoft 365

Een van de belangrijkste voordelen van cloud computing is het concept van een gedeelde, gemeenschappelijke infrastructuur voor meerdere klanten tegelijk, wat leidt tot schaalvoordelen. Dit concept wordt *multi-tenancy genoemd.* Microsoft werkt voortdurend om ervoor te zorgen dat de architectuur met meerdere tenants van onze cloudservices beveiligings-, vertrouwelijkheids-, privacy-, integriteits- en beschikbaarheidsstandaarden op ondernemingsniveau ondersteunt.

Op basis van de aanzienlijke investeringen en ervaring die afkomstig zijn van [Betrouwbaar](https://www.microsoft.com/trust-center) computergebruik en de levenscyclus van beveiligingsontwikkeling, [](https://www.microsoft.com/securityengineering/sdl/)zijn Microsoft-cloudservices ontworpen met de veronderstelling dat alle tenants potentieel negatief tegenover alle andere tenants staan. We hebben beveiligingsmaatregelen geïmplementeerd om te voorkomen dat de acties van een tenant van invloed zijn op de beveiliging of service van een andere tenant of toegang hebben tot de inhoud van een andere tenant.

De twee primaire doelen voor het behoud van tenantisolatie in een omgeving met meerdere tenants zijn:

1.    Het voorkomen van lekkage van of ongeautoriseerde toegang tot klantinhoud in tenants; en
2.    Voorkomen dat de acties van een tenant de service voor een andere tenant nadelig beïnvloeden

Er zijn meerdere vormen van beveiliging geïmplementeerd in Microsoft 365 om te voorkomen dat klanten Microsoft 365 services of toepassingen in gevaar brengen of onbevoegde toegang krijgen tot de informatie van andere tenants of het Microsoft 365-systeem zelf, waaronder:

- Logische isolatie van klantinhoud binnen elke tenant voor Microsoft 365 services wordt bereikt Azure Active Directory autorisatie en toegangsbeheer op basis van rollen.
- SharePoint Online biedt gegevensisolatiemechanismen op opslagniveau.
- Microsoft gebruikt strikte fysieke beveiliging, achtergrondscreening en een versleutelingsstrategie met meerdere lagen om de vertrouwelijkheid en integriteit van klantinhoud te beschermen. Alle Microsoft 365 datacenters hebben biometrische toegangsbesturingselementen, waarbij de meeste handpalmafdrukken nodig zijn om fysieke toegang te krijgen. Bovendien moeten alle Werknemers van Microsoft in de Verenigde Staten een standaardachtergrondcontrole voltooien als onderdeel van het wervingsproces. Zie voor meer informatie over de besturingselementen die worden gebruikt voor beheertoegang in Microsoft 365 beheertoegang [Microsoft 365 Beheertoegangsbesturingselementen.](/compliance/assurance/assurance-administrative-access-controls-overview)
- Microsoft 365 gebruikt servicetechnologieën die klantinhoud in rust en doorvoer versleutelen, waaronder BitLocker, versleuteling per bestand, Transport Layer Security (TLS) en Internet Protocol Security (IPsec). Zie Gegevensversleutelingstechnologieën in Microsoft 365 voor meer informatie over versleuteling [in Microsoft 365.](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)

Samen bieden de bovenstaande beveiligingen krachtige logische isolatiebesturingselementen die bedreigingsbeveiliging en -beperking bieden die vergelijkbaar zijn met die van alleen fysieke isolatie.

## <a name="related-links"></a>Gerelateerde koppelingen

- [Isolatie en toegankelijkheid beheren in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Tenant isolatie in Office Graph en Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Tenantisolatie in Microsoft 365 Zoeken](microsoft-365-isolation-in-microsoft-365-search.md)
- [Tenantisolatie in Office 365 Video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Resourcelimieten](/compliance/assurance/assurance-resource-limits)
- [Tenant grenzen controleren en testen](/compliance/assurance/assurance-monitoring-and-testing)
- [Isolatie en Toegangsbeheer in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)