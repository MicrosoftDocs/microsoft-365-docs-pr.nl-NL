---
title: 'Stap 12: Automatische licentie instellen'
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
description: Licenties op groepsbasis voor Azure AD-groepen doorgronden en configureren.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42809823"
---
# <a name="step-12-set-up-automatic-licensing"></a>Stap 12: Automatische licentie instellen

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In deze stap worden beveiligingsgroepen in Azure AD geconfigureerd om automatisch licenties van een verzameling abonnementen toe te wijzen aan alle leden van de groep. Dit wordt *licenties op groepsbasis* genoemd. Als een gebruikersaccount wordt toegevoegd aan of verwijderd uit een groep worden de licenties voor de groepsabonnementen automatisch toegewezen aan of verwijderd van de gebruikersaccount. 

Voor Microsoft 365 Enterprise worden Azure AD-beveiligingsgroepen geconfigureerd om deze beide licenties toe te wijzen:

- Office 365 Enterprise E3 of E5
- Enterprise Mobility + Security (EMS) E3 of E5

Zoek in de groepen die u in stap 2 hebt geïdentificeerd naar groepen die een lijst bevatten met accounts waarin alle gebruikers in die groep zowel Office 365- als EMS-licenties moeten hebben. Zorg ervoor dat u genoeg licenties hebt voor alle groepsleden. Als u niet genoeg licenties hebt, krijgen nieuwe gebruikers geen licenties totdat er weer licenties beschikbaar zijn.

>[!Note]
>Voor groepen die Azure B2B-accounts (business-to-business) bevatten, moet u *licenties op groepsbasis* niet configureren.
>

Zie [De beginselen van licenties op groepsbasis in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal) voor meer informatie.

Zie de [stappen om licenties op groepsbasis te configureren voor een Azure-beveiligingsgroep](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).

De resultaten van deze stap zijn:

- U hebt vastgesteld welke beveiligingsgroepen geschikt zijn voor licenties op groepsbasis.
- U hebt deze groepen geconfigureerd voor licenties op groepsbasis.

|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: licenties en groepslidmaatschap automatiseren](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-group-license) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [Tenant- en aanmeldingsactiviteit controleren](identity-azure-ad-access-usage-reporting.md) |

