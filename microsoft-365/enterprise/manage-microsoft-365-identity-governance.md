---
title: Microsoft 365 Identity governance beheren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Lees meer over het gebruik van functies voor Microsoft 365 Identity governance.
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328494"
---
# <a name="manage-microsoft-365-identity-governance"></a>Microsoft 365 Identity governance beheren

Identiteitsbeheer draait om het beschermen, bewaken en controleren van toegang tot kritieke bedrijfsmiddelen en tegelijkertijd de productiviteit van medewerkers waarborgen. Met identiteitsbeheer kunt u er bijvoorbeeld voor zorgen dat de juiste gebruikers toegang hebben tot de juiste resources en bepalen of de toegang mettertijd wordt aangepast.

Zie dit artikel voor meer informatie over [Identity governance voor Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview).

## <a name="set-up-azure-ad-access-reviews"></a>Azure Active Directory toegangsbeoordelingen instellen

Via Azure AD Access kunt u de toegang van een gebruiker controleren om ervoor te zorgen dat alleen de juiste personen toegang hebben. Bijvoorbeeld:

- Wanneer een nieuwe medewerker aan uw organisatie wordt toegevoegd, moet u er zeker van zijn dat ze over de juiste machtiging beschikken om productief te zijn.
- Als deze werknemer naar andere teams, locaties of afdelingen gaat, moet u ervoor zorgen dat de toegang tot vorige teams, locaties of afdelingen zo nodig wordt verwijderd.
- Wanneer deze werknemer of gast uw organisatie verlaat, moet u ervoor zorgen dat de toegang wordt verwijderd.

Dit is met name belangrijk als uw organisatie afhankelijk is van beveiligingscontroles om te bepalen of gebruikersaccounts te veel toegang hebben. Dit kan leiden tot geldboeten in strijd met de bedrijfstak of regionale voorschriften.

Zie het [overzicht van beoordelingen over Access](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)voor meer informatie.

Azure Active Directory Privileged Identity Management (PIM) biedt aanvullende besturingselementen die zijn afgestemd op het beveiligen van toegangsrechten voor resources in Azure Active Directory, Azure en andere Microsoft-cloudservices. Azure Active Directory PIM biedt een uitgebreide set beheerfuncties voor het beveiligen van de resources van uw bedrijf, zoals Directory-, Office 365- en Azure-resourcerollen. Net als bij andere vormen van toegang kunnen organisaties via toegangscontrole terugkerende toegang voor alle gebruikers in de beheerdersrollen configureren. Azure Active Directory PIM is alleen beschikbaar in de E5-versie van Microsoft 365 Enterprise.

Zie de volgende artikelen voor meer informatie over het configureren van toegangsbeoordelingen:

- [Groepen en apps](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD-rollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure-resourcerollen](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Rechtenbeheer voor Azure AD instellen

Wiht Azure AD beleggings beheer kunt u de identiteit en de toegang tot uw identiteit beheren via de werkstroom voor toegangsaanvragen, Access-opdrachten, recensies en verloop.

Uw werknemers moeten toegang hebben tot diverse groepen, toepassingen en sites om hun taak uit te voeren. Het beheren van deze toegang kan lastig zijn omdat de vereisten zijn gewijzigd, nieuwe toepassingen worden toegevoegd of gebruikers hebben extra toegangsrechten nodig. Wanneer u samenwerkt met andere organisaties, weet u mogelijk niet welke personen in de andere organisatie toegang nodig hebben tot de bronnen van uw organisatie en kunnen gebruikers van buiten gebruikers weten welke toepassingen, groepen of sites door uw organisatie worden gebruikt.

Azure AD begrenzend beheer kan u helpen om de toegang tot groepen, toepassingen en SharePoint-sites efficiënt te beheren voor interne en externe gebruikers.
 
Voor meer informatie raadpleegt u het [overzicht van het beheer van rechten van Azure AD](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview).
