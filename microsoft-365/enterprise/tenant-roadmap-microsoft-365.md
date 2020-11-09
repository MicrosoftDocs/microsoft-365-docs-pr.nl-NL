---
title: Tenant plattegrond voor Microsoft 365
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
ms.openlocfilehash: d2640a036eedda0b0962a15a03dcf0211ea0209b
ms.sourcegitcommit: c84cceb07e748969723a31b350e37f3ec79255ab
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/09/2020
ms.locfileid: "48948395"
---
# <a name="tenant-roadmap-for-microsoft-365"></a>Tenant plattegrond voor Microsoft 365

Uw Microsoft 365-Tenant is de set services die is toegewezen aan uw organisatie. Deze Tenant is meestal gekoppeld aan een of meer van uw openbare DNS-domeinnamen en fungeert als een centrale en geïsoleerde container voor verschillende abonnementen en de licenties binnen de licenties die u toewijst aan gebruikersaccounts. Zie [abonnementen, licenties, accounts en tenants voor Cloud aanbiedingen van Microsoft](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)voor meer informatie.

Wanneer u een Microsoft 365-Tenant maakt, wordt deze toegewezen aan een bepaalde geografische locatie. U kunt ook een Tenant met meerdere geografische locaties hebben en uw Tenant verplaatsen van de ene locatie naar de andere.

Als u wilt dat de Tenant klaar is voor gebruik van gebruikers, groepen, licenties en Cloud-apps, is het belangrijk om uw Tenant configuratie zorgvuldig te plannen en uit te voeren.

## <a name="set-up-your-microsoft-365-tenant"></a>Uw Microsoft 365-Tenant instellen

Nadat u ervoor hebt gezorgd dat uw netwerk voor de toegang tot Microsoft 365 is geoptimaliseerd voor zowel on-premises gebruikers als zelfstandige medewerkers, wordt uw Microsoft 365-Tenant geconfigureerd en geconfigureerd met DNS-domeinnamen, common Services en voor de infrastructuur van de identiteit die een beveiligde gebruikersaanmelding ondersteunt.

### <a name="plan"></a>Plannen

Voor het plannen van uw Tenant-implementatie:

- [Meer informatie over abonnementen, licenties en Azure AD-tenants (Azure Active Directory)](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md)
- [Meer informatie over het gebruik van SSL-certificaten van derden](plan-for-third-party-ssl-certificates.md)
- [Inzicht in de manier waarop een Microsoft 365-Tenant is geïntegreerd met Azure AD Services](integrated-apps-and-azure-ads.md)
- [Ondersteuning voor client-apps plannen](microsoft-365-client-support-certificate-based-authentication.md)
- [Bepalen hoe u moderne verificatie gebruikt](hybrid-modern-auth-overview.md)
- [Abonnement voor Office 2007 en Office 2010 upgraden](plan-upgrade-previous-versions-office.md)
- [Meer informatie over Tenant isolatie](microsoft-365-tenant-isolation-overview.md)

### <a name="deploy"></a>Implementeren

Uw Tenant implementeren: 

- Voeg de [DNS-domeinen](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) voor uw organisatie toe.
- Gebruik de [installatie handleidingen in het Microsoft 365-Beheercentrum](setup-guides-for-microsoft-365.md).
- Maak uw [identiteits infrastructuur](identity-roadmap-microsoft-365.md) en [Beveilig uw gebruikers aanmeld](microsoft-365-secure-sign-in.md).

### <a name="move-a-tenants-geographic-locations"></a>De geografische locaties van een Tenant verplaatsen

Microsoft gaat verder met het openen van nieuwe geografische locaties (GEOS) voor Microsoft 365-Services. Deze nieuwe datacenter GEOS voegt capaciteit toe en berekent bronnen voor de ondersteuning van de vraag en de gebruiks groei van de klant. Daarnaast biedt de nieuwe datacenter GEOS een in-geo data woonplaats voor de primaire klantgegevens.

Zie [Core Data verplaatsen naar nieuwe Microsoft 365 datacenter GEOS](moving-data-to-new-datacenter-geos.md)voor meer informatie.


## <a name="deploy-microsoft-365-multi-geo"></a>Microsoft 365 multi-geo implementeren

Met Microsoft 365 multi-geo kan uw organisatie zijn Microsoft 365-aanwezigheid uitbreiden naar meerdere geografische regio's en/of landen binnen de bestaande Tenant.

Zie [Microsoft 365 multi-geo](microsoft-365-multi-geo.md)voor meer informatie.

## <a name="manage-multiple-microsoft-365-tenants"></a>Meerdere Microsoft 365-tenants beheren 

Hoewel een enkele Tenant voor uw oganization ideaal is, is het mogelijk dat u een van de vele organisaties met meerdere tenants hebt. Redenen zijn fusies en verwervingen, u wilt beheerders isolatie, of u hebt een gedecentraliseerde.

Als u meerdere Microsoft 365-tenants hebt, raadpleegt u de volgende artikelen voor meer informatie over:

- [Samenwerking tussen verschillende tenants](microsoft-365-inter-tenant-collaboration.md)
- [Migratie van postvakken tussen tenants](cross-tenant-mailbox-migration.md)
- [Tenant-naar-tenant-migraties](microsoft-365-tenant-to-tenant-migrations.md)

## <a name="next-step"></a>Volgende stap

Start uw Tenant planning met [abonnementen, licenties, accounts en tenants](subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings.md).
