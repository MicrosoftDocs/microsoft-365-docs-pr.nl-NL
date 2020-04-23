---
title: Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Overzicht: Wachtwoord terugschrijven configureren voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: cc71b581730001d8dc021b5074e300fed636e3d9
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632873"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving

*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

Met Wachtwoord terugschrijven kunnen gebruikers hun wachtwoorden opnieuw instellen via Azure Active Directory (Azure AD), die vervolgens worden gerepliceerd naar uw lokale Active Directory Domain Services (AD DS). Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS waar de originele gebruikersaccounts zijn opgeslagen. Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.

In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor Wachtwoord terugschrijven.

Er zijn twee fasen om dit in te stellen:

1.    Maak de Microsoft 365-testomgeving voor uw gesimuleerde onderneming aan met wachtwoord-hash-synchronisatie.
2.    Schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md). Dit is de resulterende configuratie.
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit: 
  
- Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5.
- Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. 
- Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.

Configureer eerst het account gebruiker 1 met de rol globale beheerder.

1. Meld u aan in het [Microsoft 365-beheercentrum](https://portal.microsoft.com) met uw globale beheerdersaccount.

2. Klik op **Actieve gebruikers**.
 
3. Klik in de pagina **Actieve gebruikers** op het account **gebruiker1**,

4. klik in het deelvenster **gebruiker1** op **Bewerken** naast **Rollen**.

5. Klik in het deelvenster **Gebruikersrollen bewerken** voor gebruiker1 op **Globale beheerder**. Klik op **Opslaan** en vervolgens op **Sluiten**.

Configureer vervolgens het account gebruiker 1 met de beveiligingsinstellingen waarmee wachtwoorden kunnen worden gewijzigd namens andere gebruikers in het domein TESTLAB AD DS.

1. Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.

2.  Klik vanuit het bureaublad van APP1 op **Start**, typ **actief** en klik dan op **Active Directory-gebruikers en -computers**.

3. Klik op **Weergave** in de menubalk. Als **Geavanceerde functies** niet is ingeschakeld, klik er dan op om ze in te schakelen.

4. Klik in het structuurvenster met de rechtermuisknop op uw domein, klik op **Eigenschappen** en vervolgens op het tabblad **Beveiliging**.

5. Klik op **Geavanceerd**.

6. Klik op het tabblad **Machtigingen** op **Toevoegen**.

7. Klik op **Een hoofdmachtiging selecteren**, typ **Gebruiker1** en klik dan op **OK**.

8. Selecteer in **Van toepassing op**, **Onderliggende gebruikersobjecten**.

9. Selecteer onder **Machtigingen** het volgende:

    - Wachtwoord wijzigen
    - Wachtwoord opnieuw instellen

10. Selecteer onder **Eigenschappen** het volgende:
    - LockoutTime schrijven
    - pwdLastSet schrijven

11. Klik drie keer op **OK** om de wijzigingen op te slaan.

12. Sluit **Active Directory-gebruikers en -computers**.

Configureer vervolgens Azure AD Connect op APP1 voor Wachtwoord terugschrijven.

1. Verbind indien nodig APP1 met het account TESTLAB\Gebruiker1.

2. Dubbelklik op het bureaublad van APP1 op **Azure AD Connect**.

3. Klik in de **welkomstpagina** op **Configureren**.

4. Klik in de pagina **Aanvullende taken** op **Synchronisatieopties aanpassen** en klik dan op **Volgende**.

5. Voer in de pagina **Verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en klik vervolgens op **Volgende**.

6. Klik in de pagina’s **Mappen verbinden** en **Domein/OE filteren** op **Volgende**.

7. Selecteer in de pagina **Optionele functies**, **Wachtwoord terugschrijven** en klik op **Volgende**. 

8. Klik in de pagina **Klaar om te configureren** op **Configureren** en wacht tot het proces is voltooid.

9. Wanneer u ziet dat de configuratie is voltooid, klikt u op **Afsluiten**.

U kunt nu Wachtwoord terugschrijven testen voor gebruikers op computers die niet zijn verbonden met het virtuele netwerk van uw gesimuleerde intranet.

Dit is de resulterende configuratie:

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Deze configuratie bestaat uit:

- Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5 met het DNS-domein TESTLAB.\<uw domeinnaam> geregistreerd.
- Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. 
- Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein. 
- Wachtwoord terugschrijven is ingeschakeld, zodat gebruikers hun wachtwoorden kunnen wijzigen via Azure AD, zonder te zijn verbonden met het vereenvoudigde intranet.

Zie de stap [Vereenvoudig het updaten van wachtwoorden](identity-add-user-accounts.md#identity-pw-writeback) in de Identiteitsfase voor informatie en koppelingen om Wachtwoord terugschrijven in productie te configureren.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)


