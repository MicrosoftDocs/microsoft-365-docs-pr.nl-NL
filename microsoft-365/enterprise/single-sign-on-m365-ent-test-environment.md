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
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: configureer en test naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: f98f82de50feb2a9f92d1ecc4775c5307b314a72
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487598"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

Met behulp van Sign-On naadloze eenmalige aanmelding van Azure ACTIVEert u automatisch gebruikers op hun Pc's of apparaten die zijn verbonden met het netwerk van de organisatie. Naadloze eenmalige aanmelding via Azure AD biedt gebruikers eenvoudige toegang tot toepassingen in de Cloud, zonder dat ze hier extra onderdelen op locatie voor nodig hebben.

In dit artikel wordt uitgelegd hoe u uw Microsoft 365-testomgeving voor Azure AD perfect SSO kunt configureren.

Het instellen van Azure AD perfect SSO omvat twee fasen:
- [Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: Configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

De uiteindelijke configuratie ziet er als volgt uit:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit:
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.
- Azure AD Connect wordt uitgevoerd op APP1 om periodiek het TESTLAB Active Directory Domain Services (AD DS) te synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.

In deze fase configureert u Azure AD Connect op APP1 voor Azure AD perfect SSO en controleert u vervolgens of het werkt.

### <a name="configure-azure-ad-connect-on-app1"></a>Azure AD Connect op APP1 configureren

1. Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.

2. Voer in het APP1-bureaublad Azure AD Connect uit.

3. Selecteer **configureren**op de **welkomstpagina**.

4. Selecteer op de pagina **extra taken** de optie **gebruikersaanmelding wijzigen**en selecteer **volgende**.

5. Voer op de pagina **verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en selecteer **volgende**.

6. Selecteer op de aanmeldingspagina van de **gebruiker** de optie **eenmalige aanmelding inschakelen**en selecteer **volgende**.

7. Selecteer op de pagina **eenmalige aanmelding inschakelen** de optie **referenties invoeren**.

8. Voer in het dialoogvenster **Windows** -beveiliging **gebruiker1** in en het wachtwoord van het account gebruiker1, selecteer **OK**en selecteer vervolgens **volgende**.

9. Selecteer **configureren**op de pagina **klaar voor de configuratie** .

10. Selecteer op de pagina **configuratie voltooid** de optie **Afsluiten**.

11. Selecteer in het linkerdeelvenster van de Azure-Portal **Azure Active Directory**  >  **Azure AD CONNECT**. Controleer of de **Naadloze eenmalige aanmelding**-functie wordt weergegeven als **Ingeschakeld**.

Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met het <strong>user1@testlab.</strong>\<*your public domain*> van het gebruiker1-account.

1. Selecteer in Internet Explorer op APP1 het pictogram instellingen en selecteer vervolgens **Internet opties**.
 
2. Klik in **Internet opties**op het tabblad **beveiliging** .

3. Selecteer **Lokaal intranet**en selecteer vervolgens **sites**.

4. Selecteer in het **lokale intranet**de optie **Geavanceerd**.

5. Voer in het dialoogvenster **deze website aan de zone toevoegen** **https<span>://</span>AutoLogon.microsoftazuread-SSO.com**in en selecteer **toevoegen**  >  **sluiten**  >  **OK**  >  **OK**.

6. Meld u af en meld u vervolgens weer aan met een ander account.

7. Wanneer u wordt gevraagd u aan te melden, geeft u <strong>user1@testlab op.</strong>\<*your public domain*> naam en selecteer vervolgens **volgende**. U zou zich moeten kunnen aanmelden als Gebruiker1 zonder dat u om een wachtwoord wordt gevraagd. Dit bewijst dat de naadloze eenmalige aanmelding via Azure AD werkt.

Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar is Gebruiker1 geen globale beheerder voor Azure AD. Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.

Dit is de resulterende configuratie:

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Deze configuratie bestaat uit:

- Een Microsoft 365 E5-proefabonnement of betaalde abonnementen met de DNS-domein testlab.\<*your domain name*> geregistreerd.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.
- Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.
- Naadloze SSO van Azure AD is ingeschakeld, zodat computers in het gesimuleerde intranet zich kunnen aanmelden bij Microsoft 365 Cloud-bronnen zonder dat het wachtwoord van een gebruiker wordt opgegeven.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
