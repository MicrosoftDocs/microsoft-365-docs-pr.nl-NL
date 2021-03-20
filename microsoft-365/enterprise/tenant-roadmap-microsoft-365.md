---
title: Tenant roadmap voor Microsoft 365
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- m365initiative-coredeploy
ms.custom: it-pro
description: De routekaart voor het instellen van uw tenants voor Microsoft 365.
ms.openlocfilehash: fb3b6eecd893a5ab9b71bfa7bdfaea53af43470d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909452"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Tenant roadmap voor Microsoft 365

Uw Microsoft 365-tenant is de set services die aan uw organisatie is toegewezen. Deze tenant is meestal gekoppeld aan een of meer van uw openbare DNS-domeinnamen en fungeert als een centrale en geïsoleerde container voor verschillende abonnementen en de licenties die u aan gebruikersaccounts toewijst. Zie [Abonnementen, licenties, accounts](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)en tenants voor het cloudaanbod van Microsoft voor meer informatie.

Wanneer u een Microsoft 365-tenant maakt, wijst u deze toe aan een specifieke geografische locatie. U kunt ook een tenant met meerdere geografische locaties hebben en uw tenant van de ene locatie naar de andere verplaatsen.

Als u uw tenant wilt voorbereiden op gebruikers,groepen, licenties en cloud-apps, is het essentieel om de tenantconfiguratie zorgvuldig te plannen en uit te voeren.

## <a name="set-up-your-microsoft-365-tenant"></a>Uw Microsoft 365-tenant instellen

Nadat u ervoor hebt gezorgd dat uw netwerk is geoptimaliseerd voor toegang tot Microsoft 365 voor zowel on-premises als externe werknemers, zijn uw volgende grote taken van plan om uw Microsoft 365-tenant te configureren voor DNS-domeinnamen, algemene services en voor die identiteitsinfrastructuur die veilige aanmelding van gebruikers ondersteunt.

### <a name="plan"></a>Plannen

Plannen voor de implementatie van uw tenant:

- [Meer inzicht in abonnementen, licenties en Azure Active Directory -tenants (Azure AD)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Meer informatie over het gebruik van SSL-certificaten van derden](plan-for-third-party-ssl-certificates.md)
- [Inzicht in de manieren waarop een Microsoft 365-tenant is geïntegreerd met Azure AD-services](integrated-apps-and-azure-ads.md)
- [Ondersteuning voor client-apps plannen](microsoft-365-client-support-certificate-based-authentication.md)
- [Bepalen hoe u hybride moderne verificatie gebruikt](hybrid-modern-auth-overview.md)
- [Office 2007- en Office 2010-upgrades plannen](plan-upgrade-previous-versions-office.md)
- [Tenantisolatie begrijpen](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Implementeren

Uw tenant implementeren: 

- Voeg de [DNS-domeinen voor](../admin/setup/add-domain.md) uw organisatie toe.
- Gebruik de [installatiehulplijnen in het Microsoft 365-beheercentrum.](setup-guides-for-microsoft-365.md)
- Bouw uw [identiteitsinfrastructuur uit en](identity-roadmap-microsoft-365.md) [beveilig uw aanmeldingen voor gebruikers.](microsoft-365-secure-sign-in.md)

### <a name="move-a-tenants-geographic-locations"></a>Geografische locaties van een tenant verplaatsen

Microsoft blijft nieuwe geografische datacenterlocaties (geos) openen voor Microsoft 365-services. Deze nieuwe datacenter-geo's voegen capaciteits- en rekenbronnen toe om de vraag van klanten en de groei van het gebruik te ondersteunen. Bovendien bieden de nieuwe datacentergeo's in-geogegevenslocatie voor basisgegevens van klanten.

Zie Kerngegevens verplaatsen naar nieuwe [Microsoft 365-datacenter-geo's voor meer informatie.](moving-data-to-new-datacenter-geos.md)


## <a name="deploy-microsoft-365-multi-geo"></a>Microsoft 365 Multi-Geo implementeren

Met Microsoft 365 Multi-Geo kan uw organisatie de aanwezigheid van Microsoft 365 uitbreiden naar meerdere geografische regio's en/of landen binnen uw bestaande tenant.

Zie Microsoft [365 Multi-Geo](microsoft-365-multi-geo.md)voor meer informatie.

## <a name="manage-multiple-microsoft-365-tenants"></a>Meerdere Microsoft 365-tenants beheren 

Hoewel één tenant voor uw oganisatie ideaal is, kunt u een van de vele organisaties zijn die meerdere tenants hebben. Redenen kunnen fusies en overnames zijn, u wilt administratieve isolatie of u hebt een gedecentraliseerde IT.

Als u meerdere Microsoft 365-tenants hebt, bekijkt u deze artikelen voor meer informatie over:

- [Samenwerking tussen verschillende tenants](microsoft-365-inter-tenant-collaboration.md)
- [Migratie van postvakken tussen tenants](cross-tenant-mailbox-migration.md)
- [Tenant-naar-tenant-migraties](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Volgende stap

Start uw tenantplanning [met Abonnementen, licenties, accounts en tenants.](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)