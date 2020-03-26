---
title: 'Stap 15: Dynamisch groepslidmaatschap instellen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Informatie over automatisch groepslidmaatschap en leren configureren op basis van accountkenmerken.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42806617"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>Stap 15: Dynamisch groepslidmaatschap instellen

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In deze stap maakt u een reeks regels om gebruikersaccounts automatisch toe te voegen of te verwijderen als leden van een Azure AD-groep. Dit wordt *dynamisch groepslidmaatschap* genoemd. De regels zijn gebaseerd op kenmerken van gebruikersaccounts, zoals Afdeling of Land.

De regels worden als volgt toegepast:

- Als een nieuw gebruikersaccount aan alle regels voor de groep voldoet, wordt het lid.
- Als een gebruikersaccount geen lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat deze voldoen aan alle regels voor de groep, wordt het account lid van die groep.
- Als een gebruikersaccount niet voldoet aan alle regels voor de groep, wordt het niet toegevoegd aan de groep.
- Als een gebruikersaccount lid is van de groep, maar de bijbehorende kenmerken zodanig worden gewijzigd dat het niet meer voldoet aan alle regels voor de groep, wordt het account als lid van de groep verwijderd.

Als u dynamisch lidmaatschap wilt gebruiken, moet u eerst bepalen welke sets groepen een gemeenschappelijke set gebruikersaccountkenmerken hebben. Zo moeten bijvoorbeeld alle leden van de afdeling Verkoop zich bevinden in de Azure AD-groep Verkoop op basis van het gebruikersaccountkenmerk Afdeling met de waarde Verkoop.

Zie de [instructies voor het maken en configureren van de regels voor een dynamische Azure AD-groep](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).

De resultaten van deze stap zijn:

- Een set Azure AD-groepen die kan worden geconfigureerd voor dynamisch lidmaatschap
- Een set regels voor elke dynamische groep

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: licenties en groepslidmaatschap automatiseren](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-dyn-groups) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

[Afsluitcriterium voor identiteitsinfrastructuur](identity-exit-criteria.md)
