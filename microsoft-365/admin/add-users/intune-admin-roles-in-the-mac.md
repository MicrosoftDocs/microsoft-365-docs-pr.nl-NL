---
title: 'Informatie over Intune-beheerdersrollen in het Microsoft 365-beheercentrum '
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
description: Beheerdersrollen worden toegewezen aan bedrijfsfuncties en geven machtigingen om specifieke taken uit te voeren in het Beheercentrum. De Servicebeheerder opent bijvoorbeeld supporttickets met Microsoft.
ms.openlocfilehash: 48bb0f3d1a3a239025017fda261945094a3eda79
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126079"
---
# <a name="intune-admin-roles-in-the-microsoft-365-admin-center"></a>Intune-beheerdersrollen in het Microsoft 365-beheercentrum 

Uw abonnement op Microsoft 365 of Office 365 wordt geleverd met een set beheerdersrollen die u kunt toewijzen aan gebruikers in uw organisatie via het Microsoft 365-beheercentrum. Elke beheerdersrol wordt toegewezen aan algemene bedrijfsfuncties en machtigt personen in uw organisatie om specifieke taken uit te voeren in de beheercentra.

In het Microsoft 365-beheercentrum kunt u een aantal Microsoft Intune-rollen beheren. Deze rollen vormen echter een subset van de rollen die beschikbaar zijn in het Intune-beheercentrum. Op zoek naar de gedetailleerde rolbeschrijvingen voor Microsoft Intune? Bekijk [op rollen gebaseerd toegangsbeheer (RBAC) met Microsoft Intune](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control).

Zie [beheerdersrollen toewijzen](assign-admin-roles.md)voor meer informatie over het toewijzen van rollen in het Microsoft 365-beheercentrum.

::: moniker range="o365-worldwide"

In het Microsoft 365-beheercentrum kunt u naar **Rollen** gaan en vervolgens een rol selecteren om het detailvenster te openen. Selecteer het tabblad **Machtigingen** om de gedetailleerde takenlijst weer te geven met wat de beheerders die aan die rol zijn toegewezen kunnen doen. Selecteer het tabblad **toegewezen** of **toegewezen beheerders** om gebruikers toe te voegen aan rollen.

::: moniker-end

## <a name="microsoft-intune-roles-available-in-the-microsoft-365-admin-center"></a>Microsoft Intune-rollen die beschikbaar zijn in het Microsoft 365-beheercentrum

|Beheerdersrol     |Aan wie moet deze rol worden toegewezen?  |
|---------|---------|
|Toepassingsbeheerder     |   Wijs de rol van Applicatiebeheerder toe aan gebruikers die de applicatielevenscyclus voor mobiele apps beheren, door beleid beheerde apps configureren en apparaatinformatie en configuratieprofielen bekijken.  |
|Helpdesk-operator     |   Wijs de rol van helpdesk-operator toe aan gebruikers die apps en beleid toewijzen aan gebruikers en apparaten. |
|InTune-beheerdersrol    |   Wijs de rol van Intune-beheerder toe aan gebruikers die Intune-machtigingen aan andere beheerders kunnen toewijzen en die aangepaste en ingebouwde Intune-rollen kunnen beheren.   |
|Beleids- en profielbeheerder     |   Wijs de rol van beleids- en profielbeheerder toe aan gebruikers die nalevingsbeleid, configuratieprofielen en Apple-inschrijving beheren.   |
|Alleen-lezen operator     |   Wijs de rol van alleen-lezen operator toe aan gebruikers die gebruikers, apparaten, registratiedetails en configuraties alleen kunnen bekijken.   |
|Schoolbeheerder     |   Wijs de rol van schoolbeheerder toe aan gebruikers die volledige toegang nodig hebben voor het beheren van Windows 10- en iOS-apparaten, apps en configuraties in Intune voor het onderwijs.   |

## <a name="delegated-administration-for-microsoft-partners"></a>Gedelegeerd beheer voor Microsoft-partners

Als u met een Microsoft-partner werkt, kunt u aan uw partner beheerdersrollen toewijzen. Zij kunnen op hun beurt gebruikers in uw bedrijf, of hun bedrijf, beheerdersrollen toewijzen. U wilt misschien dat ze dit doen, bijvoorbeeld als ze uw online organisatie voor u opzetten en beheren.
  
Een partner kan deze rollen toewijzen: 
  
- Volledig beheer, met de bevoegdheden die equivalent zijn aan een globale beheerder, met uitzondering van het beheren van meervoudige verificatie via het Partnercentrum.

- Beperkt beheer: de bevoegdheden van deze rol zijn te vergelijken met die van een helpdesk-beheerder.

Voordat de partner deze rollen aan gebruikers kan toewijzen, moet u de partner als gedelegeerde beheerder aan uw account toevoegen. Dit proces wordt geïnitieerd door een geautoriseerde partner. De partner stuurt u een e-mailbericht waarin u wordt gevraagd of u de partner toestemming wilt geven om te fungeren als gedelegeerde beheerder. Zie [Partnerrelaties autoriseren of verwijderen](https://docs.microsoft.com/microsoft-365/admin/misc/add-partner)voor instructies.
  
## <a name="related-articles"></a>Verwante artikelen

[Over Microsoft 365-beheersrollen](about-admin-roles.md)

[Beheerdersrollen toewijzen](assign-admin-roles.md)

[Activiteitenoverzichten in het Microsoft 365-beheercentrum](../activity-reports/activity-reports.md)