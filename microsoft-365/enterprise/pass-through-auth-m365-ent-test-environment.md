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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: Configureer Pass Through-verificatie voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: cdbb6927fb8ca0001e3089c7169ce9046208e8f8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921526"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a>Pass Through-verificatie voor uw Microsoft 365-testomgeving

*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*

Organisaties die rechtstreeks gebruik willen maken van hun on-premises infrastructuur met Active Directory Domain Services (AD DS) voor verificatie bij Microsoft-cloudservices en -toepassingen, kunnen Pass Through-verificatie gebruiken. In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor Pass Through-verificatie, met de volgende configuratie als resultaat:
  
![De gesimuleerde onderneming in een testomgeving met Pass-Through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
Er zijn twee fasen om deze testomgeving in te stellen:

1.    Maak de Microsoft 365-testomgeving met gesimuleerde onderneming voor wachtwoord-hash-synchronisatie.
2.    Configureer Azure AD Connect op APP1 voor Pass Through-verificatie.
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik op [Hier](../downloads/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving

Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Dit is de resulterende configuratie.
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit: 
  
- Microsoft 365 E5 proefabonnement of betaald abonnement.
- Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a>Fase 2: Azure AD Connect op APP1 configureren voor Pass Through-verificatie

In deze fase configureert u Azure AD Connect op APP1 voor het gebruik van Pass Through-verificatie. Vervolgens controleert u of dit werkt.

### <a name="configure-azure-ad-connect-on-app1"></a>Azure AD Connect configureren op APP1

1.    Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.

2.    Voer Azure AD Connect uit vanaf het bureaublad van APP1.

3.    Klik op de **welkomstpagina** op **Configureren**.

4.    Klik op de pagina Extra taken op **Gebruikersaanmelding wijzigen** en klik vervolgens op **Volgende**.

5.    Voer op de pagina **Verbinding maken met Azure AD** de referenties in van uw globale beheerdersaccount en klik vervolgens op **Volgende**.

6.    Klik op de pagina **Gebruikersaanmelding** op **Pass Through-verificatie** en klik vervolgens op **Volgende**.

7.    Klik op de pagina **Gereed om te configureren** op **Configureren**.

8.    Klik op de pagina **Configuratie voltooid** op **Afsluiten**.

9.    Klik vanuit Azure Portal in het linkerdeelvenster op **Azure Active Directory > Azure AD Connect**. Controleer of de functie **Pass Through-verificatie** wordt weergegeven als **Ingeschakeld**.

10.    Klik op **Pass Through-verificatie**. In het deelvenster **Pass Through-verificatie** worden de servers weergegeven waarop uw verificatie-agenten zijn geïnstalleerd. U ziet nu APP1 in de lijst. Sluit het deelvenster **Pass Through-verificatie**.

Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met de <strong>user1@testlab.</strong>\<your public domain> van het gebruiker1-account.

1. Meld u af bij APP1 en meld u weer aan met een ander account.

2. Wanneer u om een gebruikersnaam en wachtwoord wordt gevraagd, typt u <strong>gebruiker1@testlab.</strong>\<your public domain> en het wachtwoord voor gebruiker1. U moet u nu kunnen aanmelden als Gebruiker1.

Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar Gebruiker1 is geen globale beheerder. Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.

Dit is de resulterende configuratie:

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
Deze configuratie bestaat uit:

- Een Microsoft 365 E5 of betaalde abonnementen met het DNS-domeintestlab.\<your domain name> geregistreerd.
- Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. Er wordt een verificatieagent uitgevoerd op APP1 voor het verwerken van Pass Through-verificatieaanvragen van de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)