---
title: Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving
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
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: configureer en test naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: d2b17acb2b57e379fe204e3ea4402b3f00ef7d6c
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806819"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving

*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Met de naadloze eenmalige aanmelding via Azure AD worden gebruikers automatisch aangemeld wanneer ze gebruikmaken van pc's of apparaten die zijn verbonden met het bedrijfsnetwerk. Naadloze eenmalige aanmelding via Azure AD biedt gebruikers eenvoudige toegang tot toepassingen in de Cloud, zonder dat ze hier extra onderdelen op locatie voor nodig hebben.

In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving kunt configureren voor naadloze eenmalige aanmelding via Azure AD.

Er zijn twee fasen om dit in te stellen:

1.  Maak de Microsoft 365-testomgeving voor uw gesimuleerde onderneming aan met wachtwoord-hash-synchronisatie.
2.  Configureer Azure Active Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: Configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Dit is de resulterende configuratie.
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit: 
  
- Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5.
- Een vereenvoudigde organisatie-intranet verbonden met het internet, bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. 
- Azure AD Connect draait op APP1 om het TESTLAD AD DS-domein (Active Directory Domain Services) periodiek te synchroniseren met de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.

In deze fase configureert u Azure AD Connect op APP1 voor het gebruik van naadloze eenmalige aanmelding via Azure AD, waarna u controleert of dit werkt.

### <a name="configure-azure-ad-connect-on-app1"></a>Azure AD Connect op APP1 configureren

1. Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.

2. Voer Azure AD Connect uit vanaf het bureaublad van APP1.

3. Klik op de **welkomstpagina** op **Configureren**.

4. Klik op de pagina **Aanvullende taken** op **Gebruikersaanmelding wijzigen**en klik vervolgens op **Volgende**.

5. Voer op de pagina **Verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en klik vervolgens op **Volgende**.

6. Selecteer op de pagina **Gebruikersaanmelding** de optie **Eenmalige aanmelding inschakelen** en klik vervolgens op **Volgende**.

7. Klik op de pagina **Eenmalige aanmelding inschakelen** op **Referenties invoeren**.

8. Typ in het dialoogvenster **Windows Security** in **gebruiker1** en het wachtwoord van het Gebruiker1-account en klik vervolgens op **OK**. Klik op **Volgende**.

9. Klik op de pagina **Gereed voor configureren** op **Configureren**.

10. Klik op de pagina **Configuratie voltooid** op **Afsluiten**.

11. Klik in het Azure-portal in het linkerdeelvenster op **Azure Active Directory > Azure AD Connect**. Controleer of de **Naadloze eenmalige aanmelding**-functie wordt weergegeven als **Ingeschakeld**.

Test vervolgens of u zich kunt aanmelden bij uw abonnement met <strong>gebruiker1@testlab.</strong>\<uw openbare domein> gebruikersnaam van het Gebruiker1-account.

1. Klik in Internet Explorer via APP1 op het instellingenpictogram en vervolgens op **Internet-opties**.
 
2. Klik bij **Internet-opties** op het tabblad **Beveiliging**.

3. Klik op **Lokaal intranet** en vervolgens op **Sites**.

4. Klik in **Lokaal intranet** op **Geavanceerd**.

5. Bij **Deze website aan de zone toevoegen** typt u **https<span>://</span>autologon.microsoftazuread-sso.com** en klik op **Toevoegen > Afsluiten > OK > OK**.

6. Meld u af en meld u vervolgens weer aan met een ander account.

7. Wanneer u wordt gevraagd om u aan te melden, vult u in <strong>user1@testlab.</strong>\<uw openbare domein> naam en klikt u op **Volgende**. U zou zich moeten kunnen aanmelden als Gebruiker1 zonder dat u om een wachtwoord wordt gevraagd. Dit bewijst dat de naadloze eenmalige aanmelding via Azure AD werkt.

Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar is Gebruiker1 geen globale beheerder voor Azure AD. Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.

Dit is de resulterende configuratie:

![De gesimuleerde enterprise met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
Deze configuratie bestaat uit:

- Een betaald of proefabonnement op Microsoft 365 E5 of Office 365 E5 met het DNS-domein testlab.\<uw domeinnaam> geregistreerd.
- Een vereenvoudigde organisatie-intranet verbonden met het internet, bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. 
- Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365- of Office 365-abonnement te synchroniseren met het TESTLAB AD DS-domein. 
- De naadloze eenmalige aanmelding van Azure is ingeschakeld, zodat computers op het gesimuleerde intranet zich kunnen aanmelden bij Microsoft 365 Cloud-bronnen, zonder het wachtwoord voor een gebruikersaccount in te hoeven vullen.

Zie de stap [Vereenvoudig gebruikersaanmelding](identity-secure-your-passwords.md#identity-sso) in de identiteitsfase voor informatie over en links voor het configureren van de naadloze eenmalige aanmelding via Azure AD.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise implementeren](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)


