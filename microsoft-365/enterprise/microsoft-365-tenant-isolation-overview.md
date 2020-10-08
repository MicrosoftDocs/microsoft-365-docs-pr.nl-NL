---
title: Tenant isolatie in Microsoft 365
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
description: Dit artikel bevat een overzicht van hoe Microsoft Tenant isolatie afdwingt in cloudservices zoals Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c9af522c71f3b089c8f2f198f861bcac8a0011a2
ms.sourcegitcommit: 11d1044c6600b1f568b6dc8a53db9b07f2f0ad1c
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/08/2020
ms.locfileid: "48384941"
---
# <a name="tenant-isolation-in-microsoft-365"></a>Tenant isolatie in Microsoft 365

Een van de belangrijkste voordelen van Cloud Computing is concept van een gemeenschappelijke, gemeenschappelijke infrastructuur in meerdere klanten, zodat u deze kunt schalen. Dit concept heet multitenancy *.* Microsoft werkt continu, zodat de architecturen voor meerdere tenants van onze cloudservices ondersteuning bieden voor beveiliging van ondernemingen, vertrouwelijkheid, privacy, integriteit en beschikbaarheid.

Op basis van de substantiële investeringen en ervaring van [Trustworthy Computing](https://www.microsoft.com/trust-center) en de [levenscyclus](https://www.microsoft.com/securityengineering/sdl/)van de veiligheid werden Microsoft-cloudservices ontworpen met de hypothese dat alle tenants potentieel vijandelijk zijn voor alle andere tenants en kunnen we beveiligingsmaatregelen implementeren om te voorkomen dat de acties van een bepaalde Tenant van invloed zijn op de beveiliging of service van een andere Tenant

De twee belangrijkste doelstellingen voor de handhaving van Tenant isolatie in een omgeving met meerdere tenants zijn:

1.    Het verhinderen van lekkage van toegang tot inhoud van klanten via tenants voorkomen; en
2.    Verhinderen dat de acties van een Tenant de service nadelig beïnvloeden voor een andere Tenant

Er zijn meerdere vormen van bescherming geïmplementeerd in Microsoft 365 om te voorkomen dat klanten Microsoft 365-Services of-toepassingen in gevaar brengen of om onbevoegde toegang tot de gegevens van andere tenants of het Microsoft 365-systeem zelf te verkrijgen, waaronder:

- De logische isolatie van de inhoud van klanten binnen elke Tenant voor Microsoft 365-Services wordt gerealiseerd via Azure Active Directory-autorisatie en op rollen gebaseerd toegangsbeheer.
- SharePoint Online biedt mechanismen voor gegevensisolatie op opslagniveau.
- Microsoft gebruikt strikte fysieke beveiliging, achtergrondcontrole en een meerlaagse versleutelings strategie om de vertrouwelijkheid en integriteit van klant inhoud te beschermen. Alle Microsoft 365-datacenters beschikken over besturingselementen voor biometrische toegang, met de meeste Palm afdrukken, zodat u fysieke toegang krijgt. Daarnaast zijn alle op de VS gebaseerde Microsoft-werknemers nodig om een standaardachtergrond controle uit te voeren als onderdeel van het wervingsproces. Zie voor meer informatie over de besturingselementen die worden gebruikt voor beheerderstoegang in Microsoft 365, [Microsoft 365 Administrative Access controls](microsoft-365-administrative-access-controls-overview.md).
- Microsoft 365 maakt gebruik van technologieën voor de service die de inhoud van een klant versleutelen en in transit, waaronder BitLocker, eenmalige versleuteling, TLS (Transport Layer Security) en IPsec (Internet Protocol Security). Zie [technologieën voor gegevensversleuteling in Microsoft 365](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)voor specifieke informatie over versleuteling in microsoft 365.

De hierboven genoemde bescherming biedt een robuuste logische isolatie regeling die de bescherming van de bescherming en de beperking van de schade biedt.

## <a name="related-links"></a>Verwante koppelingen

- [Isolatie en toegankelijkheid beheren in Azure Active Directory](microsoft-365-isolation-in-azure-active-directory.md)
- [Tenant isolatie in Office Graph en Delve](microsoft-365-isolation-in-graph-and-delve.md)
- [Tenant isolatie in Microsoft 365 zoeken](microsoft-365-isolation-in-microsoft-365-search.md)
- [Tenant isolatie in Office 365 video](microsoft-365-isolation-in-microsoft-365-video.md)
- [Resourcelimieten](microsoft-365-resource-limits.md)
- [Tenant grenzen controleren en testen](microsoft-365-monitoring-and-testing.md)
- [Isolatie en toegangsbeheer in Microsoft 365](microsoft-365-isolation-in-microsoft-365.md)
