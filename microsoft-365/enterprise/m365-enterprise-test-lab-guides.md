---
title: Microsoft 365 Enterprise-testlabrichtlijnen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2019
audience: ITPro
ms.topic: hub-page
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 706d5449-45e5-4b0c-a012-ab60501899ad
description: Gebruik de volgende testlabrichtlijnen voor het instellen van een demonstratie, testen van concept of ontwikkelomgevingen voor Microsoft 365 Enterprise.
ms.openlocfilehash: a006f549d0ac68562faee9c935df7f15161b2f12
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909596"
---
# <a name="microsoft-365-for-enterprise-test-lab-guides"></a>Microsoft 365 Enterprise-testlabrichtlijnen

*Dit is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Met testlabrichtlijnen (TLG's) kunt u snel meer informatie krijgen over Microsoft-producten. Zij bieden instructies voor het configureren van vereenvoudigde maar representatieve testomgevingen. U kunt deze omgevingen gebruiken voor demonstratie, aanpassing of het maken van complexe testconcepten voor de duur van een proefabonnement of een betaald abonnement.

TLG's zijn modulair ontworpen. Ze zijn op elkaar gebaseerd voor het maken van meerdere configuraties die beter aansluiten bij de behoeften van uw leer- en testconfiguratie. De hands-on ervaring 'I built it out myself and it works' helpt u inzicht te krijgen in de implementatievereisten van een nieuw product of scenario, zodat u het beter kunt plannen voor het hosten ervan in productie.

U kunt ook TLGs gebruiken om representatieve omgevingen te maken voor het ontwikkelen en testen van toepassingen, ook wel dev-/testomgevingen genoemd.
  
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, vouwt u de volgende afbeelding uit of gaat u naar Microsoft 365 voor de enterprise [Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).

[![Microsoft 365 Enterprise-testlabrichtlijnen-stack](../media/m365-enterprise-test-lab-guides/microsoft-365-enterprise-tlg-stack.png)](../downloads/Microsoft365EnterpriseTLGStack.pdf)

## <a name="base-configuration"></a>Basisconfiguratie

Maak eerst een testomgeving voor Microsoft 365 [voor ondernemingen.](/microsoft-365-enterprise/) U kunt twee soorten basisconfiguraties maken:

- [Lichtgewicht basisconfiguratie:](lightweight-base-configuration-microsoft-365-enterprise.md) gebruik deze configuratie wanneer u Microsoft 365 wilt configureren en demonstreren voor bedrijfsfuncties en -mogelijkheden in een cloudomgeving, die geen on-premises onderdelen bevat.

- [Gesimuleerde](simulated-ent-base-configuration-microsoft-365-enterprise.md) ondernemingsbasisconfiguratie: gebruik deze optie wanneer u Microsoft 365 wilt configureren en demonstreren voor bedrijfsfuncties en -mogelijkheden in een hybride cloudomgeving, waarin on-premises onderdelen worden gebruikt, zoals een AD DS-domein (Active Directory Domain Services).

U kunt ook testomgevingen voor Office 365 E5 maken door niet de Microsoft 365 E5-licentie toe te voegen aan uw proefabonnement of productietestomgeving.
    
## <a name="identity"></a>Identiteit

Zie voor meer informatie over identiteiten en functionaliteit:

- [Wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md)
  
   Wachtwoord-hash-synchronisatie inschakelen en testen vanuit een AD DS-domeincontroller.

- [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md)
  
   Pass-through-verificatie inschakelen en testen vanuit een AD DS-domeincontroller.

- [Federatieve verificatie](federated-identity-for-your-microsoft-365-dev-test-environment.md)
  
   Federatieve verificatie inschakelen en testen vanuit een AD DS-domeincontroller.

- [Microsoft Azure Active Directory naadloze SSO](single-sign-on-m365-ent-test-environment.md)
  
   Azure AD Seamless Single Sign-on (Seamless SSO) inschakelen en testen met een AD DS-domeincontroller.

- [Meervoudige verificatie](multi-factor-authentication-microsoft-365-test-environment.md)
  
   Meervoudige verificatie op een smartphone inschakelen en testen voor een specifieke gebruikersaccount.

- [Wereldwijde beheerdersaccounts beveiligen](protect-global-administrator-accounts-microsoft-365-test-environment.md)

   Vergrendel uw wereldwijde beheerdersaccounts met voorwaardelijke toegangsbeleid.

- [Wachtwoord write-back](password-writeback-m365-ent-test-environment.md)

   Wachtwoord write-back gebruiken om het wachtwoord van uw AD DS-gebruikersaccount in Microsoft Azure Active Directory te wijzigen.

- [Wachtwoordherstel](password-reset-m365-ent-test-environment.md)

   Gebruik selfservicewachtwoord opnieuw instellen om uw wachtwoord opnieuw in te stellen.

- [Automatische licentie en groepslidmaatschap](automate-licenses-group-membership-microsoft-365-test-environment.md)

   Het beheren van nieuwe accounts is eenvoudiger dan ooit dankzij automatische licentieverlening en dynamisch groepslidmaatschap.

- [Azure AD Identity Protection](azure-ad-identity-protection-microsoft-365-test-environment.md)

   Uw huidige gebruikersaccounts scannen op beveiligingsproblemen.

- [Identiteit en apparaattoegang](identity-device-access-m365-test-environment.md)

   Een omgeving maken voor het testen van aanbevolen identiteits- en toegangsconfiguraties en regels voor voorwaardelijke toegang.

## <a name="mobile-device-management"></a>Mobile Device Management

Zie voor meer informatie over de functies en functionaliteiten van Mobile Device Management:

- [Nalevingsbeleid voor apparaten](mam-policies-for-your-microsoft-365-enterprise-dev-test-environment.md)
    
   Een gebruikersgroep en nalevingsbeleid voor Windows 10-apparaten maken.
    
- [IOS- en Android-apparaten registreren](enroll-ios-and-android-devices-in-your-microsoft-enterprise-365-dev-test-environ.md)
   
   IOS- of Android-apparaten inschrijven en deze extern beheren.

## <a name="information-protection"></a>Gegevensbeveiliging

Zie voor meer informatie over beveiligingsfuncties en -functionaliteiten:

- [Verbeterde Microsoft 365-beveiliging](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)
    
   Instellingen configureren voor verbeterde Microsoft 365-beveiliging en ingebouwde beveiligingshulpprogramma's onderzoeken.
  
- [Gegevensclassificatie](data-classification-microsoft-365-enterprise-dev-test-environment.md)
    
   Labels op een document op een SharePoint Online-team site configureren en toepassen.
    
- [Privileged Access Management](privileged-access-microsoft-365-enterprise-dev-test-environment.md)
    
   Privileged Access Management configureren voor just-in-time-toegang tot verhoogde en bevoegde taken in uw organisatie.