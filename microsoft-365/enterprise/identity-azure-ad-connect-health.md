---
title: 'Stap 8: Synchronisatiestatus bewaken'
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
description: Azure AD Connect Health doorgronden en configureren.
ms.openlocfilehash: 21cfd88617bccab3f0a2bdb51c0d320cd4568a56
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42810207"
---
# <a name="step-8-monitor-synchronization-health"></a>Stap 8: Synchronisatiestatus bewaken

*Deze stap is optioneel en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In deze stap wordt op elke on-premises identiteitsserver een Azure AD Connect Health-agent geïnstalleerd om de identiteitsinfrastructuur en de synchronisatieservices te bewaken die worden geleverd door Azure AD Connect. De bewakingsinformatie wordt beschikbaar gesteld in een Azure AD Connect Health-portal waar u waarschuwingen, prestatiebewaking, gebruiksanalyses en andere informatie kunt bekijken.

![Componenten van Azure AD Connect Health](./media/identity-azure-ad-connect-health/identity-azure-ad-connect-health.png)

De belangrijkste ontwerpbeslissing over hoe u Azure AD Connect Health gaat gebruiken, is gebaseerd op hoe u Azure AD Connect gebruikt:

- Als u de optie **beheerde verificatie** gebruikt, begint u met [Azure Ad Connect Health gebruiken met synchronisatie](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-sync) om Azure AD Connect Health te doorgronden en te configureren.
- Als u alleen de namen synchroniseert van de accounts en groepen met **federatieve verificatie** met Active Directory Federation Services (AD FS), begint u met [Azure AD Connect Health gebruiken met AD FS](https://docs.microsoft.com/azure/active-directory/connect-health/active-directory-aadconnect-health-adfs) om Azure AD Connect Health te doorgronden en te configureren.

Wanneer u deze stap hebt voltooid, hebt u:

- De Azure AD Connect Health-agent geïnstalleerd op elke on-premises identiteitsserver.
- De Azure AD Connect Health-portal met de huidige status van uw on-premises infrastructuur en synchronisatieactiviteiten met de Azure AD-tenant voor uw Office 365- en EMS-abonnementen.

Als tussentijds controlepunt kunt u de [afsluitcriteria](identity-exit-criteria.md#crit-identity-sync-health) voor deze stap bekijken.


## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![](./media/stepnumbers/Step9.png)| [Wachtwoordupdates vereenvoudigen](identity-password-writeback.md) |

