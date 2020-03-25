---
title: 'Stap 9: Wachtwoordupdates vereenvoudigen'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Lees meer over het terugschrijven van wachtwoorden voor hybride omgevingen.
ms.openlocfilehash: 09679bd732e074ebedac09d1abfce53370610d0c
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/16/2019
ms.locfileid: "42805263"
---
# <a name="step-9-simplify-password-updates"></a>Stap 9: Wachtwoordupdates vereenvoudigen

*Deze stap is optioneel voor hybride omgevingen en geldt voor zowel E3- als E5-versies van Microsoft 365 Enterprise*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

In deze stap laat u gebruikers wachtwoorden opnieuw instellen via Azure Active Directory (AD), die vervolgens worden gerepliceerd naar uw lokale Windows Server Active Directory (AD). Dit proces wordt het terugschrijven van wachtwoorden genoemd. Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises Windows Server AD waar de gebruikersaccounts en de bijbehorende kenmerken zijn opgeslagen. Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.

Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.

Zie [Azure AD SSPR met wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.

>[!Note]
>Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen. Zie [Aangepaste installatie van Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.
>


|||
|:-------|:-----|
|![Testlabrichtlijnen voor de Microsoft-cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testlabrichtlijn: wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md) |
|||

Als tussentijds controlepunt kunt u het [afsluitcriterium](identity-exit-criteria.md#crit-identity-pw-writeback) voor deze stap bekijken.

## <a name="next-step"></a>Volgende stap

|||
|:-------|:-----|
|![](./media/stepnumbers/Step10.png)| [Gebruikersaanmelding vereenvoudigen](identity-single-sign-on.md) |

