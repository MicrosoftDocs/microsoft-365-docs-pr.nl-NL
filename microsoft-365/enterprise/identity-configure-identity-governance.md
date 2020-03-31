---
title: 'Stap 7: Identiteitsbeheer configureren'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Identiteitsbeheer voor uw Azure Active Directory-tenant begrijpen en configureren.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806630"
---
# <a name="step-6-configure-identity-governance"></a>Stap 6: Identiteitsbeheer configureren

![Fase 2-identiteit](../media/deploy-foundation-infrastructure/identity_icon-small.png)

Identiteitsbeheer draait om het beschermen, bewaken en controleren van toegang tot kritieke bedrijfsmiddelen en tegelijkertijd de productiviteit van medewerkers waarborgen. Met identiteitsbeheer kunt u er bijvoorbeeld voor zorgen dat de juiste gebruikers toegang hebben tot de juiste resources en bepalen of de toegang mettertijd wordt aangepast.

Zie [dit artikel](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) voor meer informatie over identiteitsbeheer voor Azure Active Directory (Azure AD).


*Dit is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Azure Active Directory toegangsbeoordelingen instellen

*Dit is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*

In deze stap stelt u de Azure Active Directory toegangsbeoordelingen in, waarmee u de toegang van een gebruiker kunt controleren om ervoor te zorgen dat alleen de juiste personen doorlopend toegang hebben. Bijvoorbeeld:

- Wanneer een nieuwe medewerker aan uw organisatie wordt toegevoegd, moet u er zeker van zijn dat ze over de juiste machtiging beschikken om productief te zijn.
- Als deze werknemer naar andere teams, locaties of afdelingen gaat, moet u ervoor zorgen dat de toegang tot vorige teams, locaties of afdelingen zo nodig wordt verwijderd.
- Wanneer deze werknemer of gast uw organisatie verlaat, moet u ervoor zorgen dat de toegang wordt verwijderd.

Dit is met name belangrijk als uw organisatie afhankelijk is van beveiligingscontroles om te bepalen of gebruikersaccounts te veel toegang hebben. Dit kan leiden tot geldboeten in strijd met de bedrijfstak of regionale voorschriften.

Zie [dit artikel](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview) voor meer informatie over Azure Active Directory toegangsbeoordelingen.

Azure Active Directory Privileged Identity Management (PIM) biedt aanvullende besturingselementen die zijn afgestemd op het beveiligen van toegangsrechten voor resources in Azure Active Directory, Azure en andere Microsoft-cloudservices. Azure Active Directory PIM biedt een uitgebreide set beheerfuncties voor het beveiligen van de resources van uw bedrijf, zoals Directory-, Office 365- en Azure-resourcerollen. Net als bij andere vormen van toegang kunnen organisaties via toegangscontrole terugkerende toegang voor alle gebruikers in de beheerdersrollen configureren. Azure Active Directory PIM is alleen beschikbaar in de E5-versie van Microsoft 365 Enterprise.

Zie de volgende artikelen voor meer informatie over het configureren van toegangsbeoordelingen:

- [Groepen en apps](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-resourcerollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-access-reviews) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

[Afsluitcriterium voor identiteitsinfrastructuur](identity-exit-criteria.md)

