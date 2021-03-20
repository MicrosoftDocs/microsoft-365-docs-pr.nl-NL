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
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904862"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a>Naadloze eenmalige aanmelding via Azure AD voor uw Microsoft 365-testomgeving

*Deze testlaborator kan worden gebruikt voor testomgevingen van Microsoft 365 voor bedrijven en Office 365 Enterprise.*

Azure AD Seamless Single Sign-On (Seamless SSO) meldt zich automatisch aan bij gebruikers wanneer ze zich op hun pc's of apparaten die zijn verbonden met hun organisatienetwerk. Naadloze eenmalige aanmelding via Azure AD biedt gebruikers eenvoudige toegang tot toepassingen in de Cloud, zonder dat ze hier extra onderdelen op locatie voor nodig hebben.

In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving configureert voor Naadloze aanmelding voor Azure AD.

Het instellen van Azure AD Seamless SSO omvat twee fasen:
- [Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving

Volg de instructies in [wachtwoord-hash-synchronisatie voor Microsoft 365](password-hash-sync-m365-ent-test-environment.md). 

De resulterende configuratie ziet er als volgende uit:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit:
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.
- Azure AD Connect wordt uitgevoerd op APP1 om het DOMEIN TESTLAB Active Directory Domain Services (AD DS) regelmatig te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a>Fase 2: Configureer Azure AD Connect op APP1 voor naadloze eenmalige aanmelding via Azure AD.

In deze fase configureert u Azure AD Connect op APP1 voor Azure AD Seamless SSO en controleert u of dit werkt.

### <a name="configure-azure-ad-connect-on-app1"></a>Azure AD Connect op APP1 configureren

1. Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.

2. Voer Azure AD Connect uit op het bureaublad van APP1.

3. Selecteer **configureren op de** **welkomstpagina.**

4. Selecteer op **de pagina** Extra taken de optie Gebruikers **aanmelden wijzigen** en selecteer vervolgens **Volgende**.

5. Voer op **de pagina Verbinding maken met Azure AD** uw globale beheerdersaccountreferenties in en selecteer **volgende**.

6. Selecteer op **de pagina Gebruiker** aanmelden de optie Eén aanmelding **inschakelen** en selecteer vervolgens **Volgende**.

7. Selecteer op **de pagina Eén aanmelding inschakelen** de optie Referenties **invoeren.**

8. Voer in **het dialoogvenster Windows Beveiliging** **gebruiker1** en het wachtwoord van het gebruikersaccount in, selecteer **OK** en selecteer **volgende**.

9. Selecteer **configureren** op de pagina Gereed voor **configureren.**

10. Selecteer op **de pagina Configuratie** voltooid de optie **Afsluiten.**

11. Selecteer azure **Active Directory** Azure AD Connect in het linkerdeelvenster in de  >  **Azure Portal.** Controleer of de **Naadloze eenmalige aanmelding**-functie wordt weergegeven als **Ingeschakeld**.

Test vervolgens de mogelijkheid om u aan te melden bij uw abonnement met de <strong>user1@testlab.</strong>\<*your public domain*> van het gebruiker1-account.

1. Selecteer in Internet Explorer op APP1 het pictogram Instellingen en selecteer **vervolgens Internetopties.**
 
2. Selecteer **in Internetopties** het **tabblad** Beveiliging.

3. Selecteer **Lokaal intranet** en selecteer vervolgens **Sites.**

4. Selecteer Geavanceerd in  **lokaal intranet.**

5. In **Deze website toevoegen aan de zone**, voert u https **<span>://</span>autologon.microsoftazuread-sso.com**, selecteer **Sluiten**  >    >  **OK**  >  **toevoegen.**

6. Meld u af en meld u vervolgens weer aan met een ander account.

7. Wanneer u wordt gevraagd u aan te melden, geeft <strong>u user1@testlab.</strong>\<*your public domain*> en selecteer vervolgens **Volgende**. U zou zich moeten kunnen aanmelden als Gebruiker1 zonder dat u om een wachtwoord wordt gevraagd. Dit bewijst dat de naadloze eenmalige aanmelding via Azure AD werkt.

Zoals u ziet, heeft Gebruiker1 de machtigingen van een domeinbeheerder voor het TESTLAB AD DS-domein, maar is Gebruiker1 geen globale beheerder voor Azure AD. Daarom wordt het pictogram van de **Beheerder** niet weergegeven als optie.

Dit is de resulterende configuratie:

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Deze configuratie bestaat uit:

- Een proefversie van Microsoft 365 E5 of betaalde abonnementen met het DNS-domeintestlab.\<*your domain name*> geregistreerd.
- Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.
- Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.
- Azure AD Seamless SSO is ingeschakeld, zodat computers op het gesimuleerde intranet zich kunnen aanmelden bij cloudbronnen van Microsoft 365 zonder een wachtwoord voor een gebruikersaccount op te geven.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)