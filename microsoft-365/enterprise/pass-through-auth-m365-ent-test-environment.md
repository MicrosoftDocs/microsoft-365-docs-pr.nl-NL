---
title: Pass Through-verificatie voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: Configureer Pass Through-verificatie voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: 4f9941b017f00b40a6ae7e893211131cae51c611
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42812022"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Pass Through-verificatie voor uw Microsoft 365-testomgeving

*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Organisaties die rechtstreeks gebruik willen maken van hun on-premises infrastructuur met Active Directory Domain Services (AD DS) voor verificatie bij Microsoft-cloudservices en -toepassingen, kunnen Pass Through-verificatie gebruiken. In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor Pass Through-verificatie, met de volgende configuratie als resultaat:
  
![De gesimuleerde onderneming in een testomgeving met Pass-Through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Er zijn twee fasen om deze testomgeving in te stellen:

1.  Maak de Microsoft 365-testomgeving met gesimuleerde onderneming voor wachtwoord-hash-synchronisatie.
2.  Configureer Azure AD Connect op APP1 voor Pass Through-verificatie.
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen in de stack met Microsoft 365 Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: Wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving

Volg de instructies in [Wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Dit is de resulterende configuratie.
  
![De gesimuleerde onderneming in een testomgeving voor wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit: 
  
- Een proef- of betaald abonnement op Microsoft 365 E5 of Office 365 E5.
- Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit drie virtuele machines (DC1, APP1 en CLIENT1) op een subnet van een virtueel Azure-netwerk. Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB periodiek te synchroniseren met de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: Azure AD Connect op APP1 configureren voor Pass Through-verificatie

In deze fase configureert u Azure AD Connect op APP1 voor het gebruik van Pass Through-verificatie. Vervolgens controleert u of dit werkt.

### <a name="configure-azure-ad-connect-on-app1"></a>Azure AD Connect configureren op APP1

1.  Ga naar [Azure Portal](https://portal.azure.com), meld u aan met uw globale-beheerdersaccount en maak vervolgens verbinding met APP1 via het account TESTLAB\Gebruiker1.

2.  Voer Azure AD Connect uit vanaf het bureaublad van APP1.

3.  Klik op de **welkomstpagina** op **Configureren**.

4.  Klik op de pagina Extra taken op **Gebruikersaanmelding wijzigen**en klik vervolgens op **Volgende**.

5.  Voer op de pagina **Verbinding maken met Azure AD** de referenties in van uw globale beheerdersaccount en klik vervolgens op **Volgende**.

6.  Klik op de pagina **Gebruikersaanmelding** op **Pass Through-verificatie**en klik vervolgens op **Volgende**.

7.  Klik op de pagina **Gereed om te configureren** op **Configureren**.

8.  Klik op de pagina **Configuratie voltooid** op **Afsluiten**.

9.  Klik vanuit Azure Portal in het linkerdeelvenster op **Azure Active Directory > Azure AD Connect**. Controleer of de functie **Pass Through-verificatie** wordt weergegeven als **Ingeschakeld**.

10. Klik op **Pass Through-verificatie**. In het deelvenster **Pass Through-verificatie** worden de servers weergegeven waarop uw verificatie-agenten zijn geïnstalleerd. U ziet nu APP1 in de lijst. Sluit het deelvenster **Pass Through-verificatie**.

Test vervolgens of u zich kunt aanmelden bij uw abonnement met <strong>gebruiker1@testlab.</strong>\<uw openbare domein> gebruikersnaam van het account Gebruiker1.

1. Meld u af bij APP1 en meld u weer aan met een ander account.

2. Wanneer u om een gebruikersnaam en wachtwoord wordt gevraagd, typt u <strong>gebruiker1@testlab.</strong>\<uw openbare domein> en het wachtwoord voor Gebruiker1. U moet u nu kunnen aanmelden als Gebruiker1.

Zoals u ziet, heeft Gebruiker1 machtigingen van een domeinbeheerder voor het AD DS-domein TESTLAB, maar Gebruiker1 is geen globale beheerder. Daarom wordt het pictogram van de **-beheerder** niet weergegeven als optie.

Dit is de resulterende configuratie:

![De gesimuleerde onderneming in een testomgeving met Pass-Through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Deze configuratie bestaat uit:

- Een proef- of betaald abonnement op Microsoft 365 E5 of Office 365 E5 met het DNS-domein Testlab.\<uw domeinnaam> geregistreerd.
- Een vereenvoudigde organisatie die via intranet is verbonden met internet, bestaande uit drie virtuele machines (DC1, APP1 en CLIENT1) op een subnet van een virtueel Azure-netwerk. Er wordt een verificatieagent uitgevoerd op APP1 voor het verwerken van Pass Through-verificatieaanvragen van de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
