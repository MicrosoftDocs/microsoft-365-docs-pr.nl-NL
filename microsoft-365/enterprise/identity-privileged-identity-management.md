---
title: 'Stap 3: Globale beheerders op aanvraag instellen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lees meer over en configureer Azure Active Directory Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42812021"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>Stap 3: Globale beheerders op aanvraag instellen

*Deze stap is optioneel en geldt voor alleen voor de E5-versie van Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In deze stap stelt u de Azure Active Directory Privileged Identity Management (PIM) in om de tijd te verminderen dat uw globale beheerdersaccounts kwetsbaar zijn voor aanvallen door kwaadwillende gebruikers. Met PIM kunt u op aanvraag een just-in-time-instructie van de globale beheerdersrol inschakelen.  

In plaats van uw globale beheerdersaccounts een permanente beheerder te worden, worden ze in aanmerking komende beheerders. De globale beheerdersrol is inactief totdat iemand deze nodig heeft. Vervolgens voert u een activeringsprocedure uit om de globale beheerdersrol gedurende een bepaalde tijd toe te voegen aan het globale beheerdersaccount. Als de tijd is verstreken, verwijdert PIM de globale beheerdersrol uit het globale beheerdersaccount.

PIM is beschikbaar met Azure Active Directory Premium P2, dat inbegrepen is bij Microsoft 365 Enterprise E5. U kunt ook afzonderlijke Azure Active Directory Premium P2-licenties aanschaffen voor uw globale-beheerdersaccounts.

Als u Azure PIM wilt inschakelen voor uw Azure Active Directory tenant -en globale beheerdersaccounts, raadpleegt u de [stappen voor het configureren van PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).

U kunt een uitgebreide roadmap ontwikkelen om bevoegde toegang te beveiligen tegen cyberaanvallers, zie [Bevoegde toegang voor hybride en cloudimplementaties in Azure Active Directory beveiligen](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-pim) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [Het opnieuw instellen van wachtwoorden vereenvoudigen](identity-password-reset.md) |

