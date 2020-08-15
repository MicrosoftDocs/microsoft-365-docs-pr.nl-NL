---
title: Vereisten voor identiteits- en apparaattoegang voor de cloud alleen in uw Microsoft 365-testomgeving.
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
description: Maak een Microsoft 365-omgeving voor het testen van identiteits- en apparaattoegang met de vereisten voor verificatie alleen in de cloud.
ms.openlocfilehash: a8025a2543a53a229be13d19c246165fe88ad433
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46685782"
---
# <a name="identity-and-device-access-prerequisites-for-cloud-only-in-your-microsoft-365-test-environment"></a>Vereisten voor identiteits- en apparaattoegang voor de cloud alleen in uw Microsoft 365-testomgeving.

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

[Configuraties voor identiteits-en Apparaattoegang](microsoft-365-policies-configurations.md) zijn een set configuraties en regels voor voorwaardelijke toegang om toegang te beschermen tot alle services die zijn geïntegreerd in azure Active Directory (Azure AD).

In dit artikel wordt beschreven hoe een Microsoft 365-testomgeving kan worden geconfigureerd die voldoet aan de voorwaarden van de [vereiste configuratie alleen in de cloud](identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang.

Er zijn zeven fasen om deze testomgeving in te stellen:

1.  Uw lichte testomgeving uitbouwen
2.  Benoemde locaties configureren
3.  Wachtwoord terugschrijven configureren
4.  Selfservice voor wachtwoordherstel configureren
5.  Meervoudige verificatie configureren
6.  Azure AD Identity Protection inschakelen
7.  Moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online

## <a name="phase-1-build-out-your-lightweight-microsoft-365-test-environment"></a>Fase 1: uw lichte Microsoft 365-testomgeving uitbouwen

Volg de instructies in [Lichtgewicht basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).
Dit is de resulterende configuratie.

![De lichtgewicht Microsoft 3656 Enterprise-testomgeving](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)
 

## <a name="phase-2-configure-named-locations"></a>Fase 2: benoemde locaties configureren

Bepaal eerst de openbare IP-adressen of adresbereiken die worden gebruikt door uw organisatie.

Volg daarna de instructies in [Benoemde locaties configureren in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/reports-monitoring/quickstart-configure-named-locations) om de adressen of adresbereiken als benoemde locaties toe te voegen. 

## <a name="phase-3-configure-password-writeback"></a>Fase 3: wachtwoord terugschrijven configureren

Volg de instructies in [Fase 2 van het wachtwoord terugschrijven in het testlabrichtlijn](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

## <a name="phase-4-configure-self-service-password-reset"></a>Fase 4: selfservice voor wachtwoordherstel configureren

Volg de instructies in [Fase 3 van testlabrichtlijn Wachtwoordherstel](password-reset-m365-ent-test-environment.md#phase-3-configure-and-test-password-reset). 

Wanneer u wachtwoordherstel inschakelt voor de accounts in een specifieke Azure AD-groep, voegt u deze accounts toe aan de groep **Wachtwoord opnieuw instellen**:

- Gebruiker 2
- Gebruiker 3
- Gebruiker 4
- Gebruiker 5

Test wachtwoordherstel alleen voor het Gebruiker 2-account.

## <a name="phase-5-configure-multi-factor-authentication"></a>Fase 5: meervoudige verificatie configureren

Volg de instructies in [Fase 2 van testlabrichtlijn Meervoudige verificatie](multi-factor-authentication-microsoft-365-test-environment.md#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account) voor de volgende gebruikersaccounts:

- Gebruiker 2
- Gebruiker 3
- Gebruiker 4
- Gebruiker 5

Test meervoudige verificatie alleen voor het Gebruiker 2-account.

## <a name="phase-6-enable-azure-ad-identity-protection"></a>Fase 6: Azure Active Directory Identity Protection inschakelen

Volg de instructies in [Fase 2 van het Azure Active Directory Identity Protection-testlabrichtlijn](azure-ad-identity-protection-microsoft-365-test-environment.md#phase-2-use-azure-ad-identity-protection). 

## <a name="phase-7-enable-modern-authentication-for-exchange-online-and-skype-for-business-online"></a>Fase 7: moderne verificatie inschakelen voor Exchange Online en Skype voor Bedrijven Online

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

Het resultaat is een testomgeving die voldoet aan de vereisten van de [vereiste configuratie alleen in de cloud](identity-access-prerequisites.md#prerequisites) voor identiteits- en apparaattoegang. 

## <a name="next-step"></a>Volgende stap

Gebruik [algemeen beleid voor identiteits- en apparaattoegang](identity-access-policies.md) voor het configureren van het beleid dat is gebaseerd op de vereisten, en bescherm identiteiten en apparaten.

## <a name="see-also"></a>Zie ook

[Aanvullende testlabrichtlijnen voor identiteit](m365-enterprise-test-lab-guides.md#identity)

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
