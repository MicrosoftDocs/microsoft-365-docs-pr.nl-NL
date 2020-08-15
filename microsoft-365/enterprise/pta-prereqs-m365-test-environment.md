---
title: Vereisten voor identiteits- en apparaattoegang voor pass-through-verificatie in uw Microsoft 365-testomgeving.
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Maak een Microsoft 365-omgeving voor het testen van identiteits- en apparaattoegang met de vereisten voor pass-through-verificatie.
ms.openlocfilehash: eeb6c1d1313c95e920b20cce419118fe1e61ad6e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685640"
---
# <a name="identity-and-device-access-prerequisites-for-pass-through-authentication-in-your-microsoft-365-test-environment"></a>Vereisten voor identiteits- en apparaattoegang voor pass-through-verificatie in uw Microsoft 365-testomgeving.

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

[Configuraties voor identiteits-en Apparaattoegang](microsoft-365-policies-configurations.md) zijn een set configuraties en regels voor voorwaardelijke toegang om toegang te krijgen tot alle services in microsoft 365 for Enterprise die zijn geïntegreerd in azure Active Directory (Azure AD).

In dit artikel wordt beschreven hoe u een Microsoft 365-testomgeving kunt configureren die voldoet aan de vereisten van de [configuratie voor pass-through-verificatie](identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang.

Er zijn acht fasen om deze testomgeving in te stellen:

1.  Uw gesimuleerde Enterprise uitbreiden met een Microsoft 365-testomgeving met pass-through-verificatie
2.  Naadloze eenmalige Azure AD-aanmelding configureren
3.  Benoemde locaties configureren
4.  Wachtwoord terugschrijven configureren
5.  Self-service voor wachtwoordherstel configureren
6.  Meervoudige verificatie configureren
7.  Azure AD Identity Protection inschakelen
8.  Moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online

## <a name="phase-1-build-out-your-simulated-enterprise-with-pass-through-authentication-microsoft-365-test-environment"></a>Fase 1: Uw gesimuleerde Enterprise uitbreiden met een Microsoft 365-testomgeving met pass-through-verificatie

Volg de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).

Dit is de resulterende configuratie.

![De gesimuleerde Enterprise met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
## <a name="phase-2-configure-azure-ad-seamless-single-sign-on"></a>Fase 2: Naadloze eenmalige Azure AD-aanmelding configureren

Volg de instructies in [Fase 2 van testlabrichtlijn Naadloze eenmalige Azure AD-aanmelding](single-sign-on-m365-ent-test-environment.md#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso).

## <a name="phase-3-configure-named-locations"></a>Fase 3: Benoemde locaties configureren

Bepaal eerst de openbare IP-adressen of adresbereiken die worden gebruikt door uw organisatie.

Volg daarna de instructies in [Benoemde locaties configureren in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) om de adressen of adresbereiken als benoemde locaties toe te voegen. 

## <a name="phase-4-configure-password-writeback"></a>Fase 4: Wachtwoord terugschrijven configureren

Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-5-configure-self-service-password-reset"></a>Fase 5: Self-service voor wachtwoordherstel configureren

Volg de instructies in [Fase 3 van testlabrichtlijn Wachtwoordherstel](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Wanneer u wachtwoordherstel inschakelt voor de accounts in een specifieke Azure AD-groep, voegt u deze accounts toe aan de groep **Wachtwoord opnieuw instellen**:

- Gebruiker 2
- Gebruiker 3
- Gebruiker 4
- Gebruiker 5

Test wachtwoordherstel alleen voor het Gebruiker 2-account.

## <a name="phase-6-configure-multi-factor-authentication"></a>Fase 6: Meervoudige verificatie configureren

Volg de instructies in [Fase 2 van testlabrichtlijn Meervoudige verificatie](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) voor de volgende gebruikersaccounts:

- Gebruiker 2
- Gebruiker 3
- Gebruiker 4
- Gebruiker 5

Test meervoudige verificatie alleen voor het Gebruiker 2-account.

## <a name="phase-7-enable-azure-ad-identity-protection"></a>Fase 7: Azure AD Identity Protection inschakelen

Volg de instructies in [Fase 2 van testlabrichtlijn Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-8-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 8: Moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online

Volg voor Exchange Online [deze instructies](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online#enable-or-disable-modern-authentication-in-exchange-online-for-client-connections-in-outlook-2013-or-later). 

Voor Skype voor Bedrijven Online:

1. Maak verbinding met [Skype voor Bedrijven Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

2. Voer deze opdracht uit.

  ```powershell
  Set-CsOAuthConfiguration -ClientAdalAuthOverride Allowed
  ```

3. Controleer of het wijzigen met behulp van deze opdracht is gelukt.

  ```powershell
  Get-CsOAuthConfiguration
  ```

Het resultaat is een testomgeving die voldoet aan de vereisten van de [vereiste configuratie van pass-through-verificatie](identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang. 

## <a name="next-step"></a>Volgende stap

Gebruik [algemeen beleid voor identiteits- en apparaattoegang](identity-access-policies.md) voor het configureren van het beleid dat is gebaseerd op de vereisten, en bescherm identiteiten en apparaten.

## <a name="see-also"></a>Zie ook

[Aanvullende testlabrichtlijnen voor identiteit](m365-enterprise-test-lab-guides.md#identity)

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)

