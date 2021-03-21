---
title: Hybride identiteits- en adreslijstsynchronisatie voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: conceptual
ms.date: 09/30/2020
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MOE150
- MET150
ms.assetid: d3577c90-dda5-45ca-afb0-370d2889b10f
description: Beschrijft adreslijstsynchronisatie met Microsoft 365, het opschonen van Active Directory Domain Services en het hulpprogramma Azure Active Directory Connect.
ms.openlocfilehash: 7b717f65bb434918a5eb0ab2bf4a5acab2d08eea
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927542"
---
# <a name="hybrid-identity-and-directory-synchronization-for-microsoft-365"></a>Hybride identiteits- en adreslijstsynchronisatie voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Afhankelijk van uw zakelijke behoeften en technische vereisten, is het hybride identiteitsmodel en adreslijstsynchronisatie de meest voorkomende keuze voor zakelijke klanten die Microsoft 365 gebruiken. Met adreslijstsynchronisatie kunt u identiteiten beheren in uw Active Directory Domain Services (AD DS) en worden alle updates voor gebruikersaccounts, groepen en contactpersonen gesynchroniseerd met de Azure Active Directory-tenant (Azure AD) van uw Microsoft 365-abonnement.

>[!Note]
>Wanneer AD DS-gebruikersaccounts voor de eerste keer worden gesynchroniseerd, krijgen ze niet automatisch een Microsoft 365-licentie toegewezen en hebben ze geen toegang tot Microsoft 365-services, zoals e-mail. U moet ze eerst een gebruikslocatie toewijzen. Wijs vervolgens een licentie toe aan deze gebruikersaccounts, afzonderlijk of dynamisch via groepslidmaatschap.
>

## <a name="authentication-for-hybrid-identity"></a>Verificatie voor hybride identiteit

Er zijn twee typen verificatie wanneer u het hybride identiteitsmodel gebruikt:

- Beheerde verificatie

  Azure AD verwerkt het verificatieproces met behulp van een lokaal opgeslagen hashed-versie van het wachtwoord of verzendt de referenties naar een on-premises softwareagent die moet worden geverifieerd door de on-premises AD DS.

- Federatieve verificatie

  Azure AD omgeleid de clientcomputer die verificatie aanvraagt naar een andere identiteitsprovider.

### <a name="managed-authentication"></a>Beheerde verificatie

Er zijn twee typen beheerde verificatie:

- Wachtwoordhashsynchronisatie (PHS)

  Azure AD voert de verificatie zelf uit.

- Pass Through-verificatie (PTA)

  Azure AD heeft AD DS de verificatie laten uitvoeren.


#### <a name="password-hash-synchronization-phs"></a>Wachtwoordhashsynchronisatie (PHS)

Met PHS synchroniseert u uw AD DS-gebruikersaccounts met Microsoft 365 en beheert u uw gebruikers on-premises. Hashes van gebruikerswachtwoorden worden gesynchroniseerd van uw AD DS naar Azure AD, zodat de gebruikers hetzelfde wachtwoord on-premises en in de cloud hebben. Dit is de eenvoudigste manier om verificatie in te schakelen voor AD DS-identiteiten in Azure AD. 

![Wachtwoordhashsynchronisatie (PHS)](../media/plan-for-directory-synchronization/phs-authentication.png)

Wanneer wachtwoorden on-premises worden gewijzigd of opnieuw worden ingesteld, worden de nieuwe wachtwoordhashes gesynchroniseerd met Azure AD, zodat uw gebruikers altijd hetzelfde wachtwoord kunnen gebruiken voor cloudbronnen en on-premises resources. De gebruikerswachtwoorden worden nooit in duidelijke tekst verzonden naar Azure AD of opgeslagen in Azure AD. Voor sommige premiumfuncties van Azure AD, zoals Identiteitsbeveiliging, is PHS vereist, ongeacht welke verificatiemethode is geselecteerd.
  
Zie [de juiste verificatiemethode kiezen voor](/azure/active-directory/hybrid/choose-ad-authn) meer informatie.
  
#### <a name="pass-through-authentication-pta"></a>Pass Through-verificatie (PTA)

PTA biedt een eenvoudige wachtwoordvalidatie voor Azure AD-verificatieservices met behulp van een softwareagent die op een of meer on-premises servers wordt uitgevoerd om de gebruikers rechtstreeks met uw AD DS te valideren. Met PTA synchroniseert u AD DS-gebruikersaccounts met Microsoft 365 en beheert u uw gebruikers on-premises. 

![Pass Through-verificatie (PTA)](../media/plan-for-directory-synchronization/pta-authentication.png)

Met PTA kunnen uw gebruikers zich aanmelden bij zowel on-premises als Microsoft 365-resources en -toepassingen met hun on-premises account en wachtwoord. Met deze configuratie worden gebruikerswachtwoorden rechtstreeks gevalideerd op basis van uw on-premises AD DS zonder wachtwoordhashes op te slaan in Azure AD. 

PTA is ook voor organisaties met een beveiligingsvereiste om on-premises gebruikersaccountstaten, wachtwoordbeleid en aanmeldingsuren onmiddellijk af te dwingen. 
  
Zie [de juiste verificatiemethode kiezen voor](/azure/active-directory/hybrid/choose-ad-authn) meer informatie.
  
### <a name="federated-authentication"></a>Federatieve verificatie

Federatieverificatie is voornamelijk bedoeld voor grote ondernemingen met complexere verificatievereisten. AD DS-identiteiten worden gesynchroniseerd met Microsoft 365 en gebruikersaccounts worden on-premises beheerd. Met federatief verificatie hebben gebruikers hetzelfde wachtwoord on-premises en in de cloud en ze moeten zich niet opnieuw aanmelden om Microsoft 365 te gebruiken. 

Federatief verificatie kan aanvullende verificatievereisten ondersteunen, zoals op smartcard gebaseerde verificatie of een meervoudige verificatie van derden en is meestal vereist wanneer organisaties een verificatievereiste hebben die niet inheems wordt ondersteund door Azure AD.
 
Zie [de juiste verificatiemethode kiezen voor](/azure/active-directory/hybrid/choose-ad-authn) meer informatie.
  
#### <a name="third-party-authentication-and-identity-providers"></a>Externe verificatie- en identiteitsproviders

On-premises adreslijstobjecten kunnen worden gesynchroniseerd met Microsoft 365 en cloudresourcetoegang wordt hoofdzakelijk beheerd door een externe identiteitsprovider (IdP). Als uw organisatie een federatieoplossing van derden gebruikt, kunt u aanmelding met die oplossing configureren voor Microsoft 365, mits de federatieoplossing van derden compatibel is met Azure AD.
  
Zie de [compatibiliteitslijst met Azure AD-federaties](/azure/active-directory/connect/active-directory-aadconnect-federation-compatibility) voor meer informatie.
  
## <a name="ad-ds-preparation"></a>AD DS-voorbereiding

Als u wilt zorgen voor een naadloze overgang naar Microsoft 365 met behulp van synchronisatie, moet u uw AD DS-forest voorbereiden voordat u begint met de implementatie van de Microsoft 365-adreslijstsynchronisatie.
  
Uw adreslijstvoorbereiding moet zich richten op de volgende taken:

- Dubbele **proxyAddress-** en **userPrincipalName-kenmerken** verwijderen.
- Lege en ongeldige **userPrincipalName-kenmerken** bijwerken met geldige **userPrincipalName-kenmerken.**
- Verwijder ongeldige en twijfelachtige tekens in de **opgegevenname,** achternaam ( **sn** ), **sAMAccountName**, **displayName**, **e-mail**, **proxyAddresses**, **mailNickname** en **userPrincipalName-kenmerken.** Zie Lijst met kenmerken die worden gesynchroniseerd met het Azure Active Directory Sync Tool voor meer informatie over het voorbereiden [van kenmerken.](https://go.microsoft.com/fwlink/p/?LinkId=396719)

    > [!NOTE]
    > Dit zijn dezelfde kenmerken die door Azure AD Connect worden gesynchroniseerd. 
  
## <a name="multi-forest-deployment-considerations"></a>Overwegingen voor de implementatie van meerdere forests

Gebruik een aangepaste installatie van Azure AD Connect voor meerdere forests en [SSO-opties.](/azure/active-directory/hybrid/how-to-connect-install-custom)
  
Als uw organisatie meerdere forests voor verificatie (aanmeldingsbossen) heeft, raden we ten zeerste het volgende aan:
  
- **Overweeg uw bossen te consolideren.** Over het algemeen is er meer overhead vereist om meerdere bossen te onderhouden. Tenzij uw organisatie beveiligingsbeperkingen heeft die de noodzaak van afzonderlijke bossen bepalen, kunt u overwegen uw on-premises omgeving te vereenvoudigen.
- **Alleen gebruiken in uw primaire aanmeldingsbos.** Overweeg microsoft 365 alleen te implementeren in uw primaire aanmeldingsbos voor de eerste implementatie van Microsoft 365. 

Als u uw AD DS-implementatie met meerdere forests niet kunt samenvoegen of andere adreslijstservices gebruikt om identiteiten te beheren, kunt u deze mogelijk synchroniseren met behulp van Microsoft of een partner.
  
Zie [Excuses voor Azure AD Connect voor](/azure/active-directory/hybrid/plan-connect-topologies) meer informatie.
  
## <a name="features-that-are-dependent-on-directory-synchronization"></a>Functies die afhankelijk zijn van adreslijstsynchronisatie
  
Adreslijstsynchronisatie is vereist voor de volgende functies en functionaliteit:
  
- Azure AD Seamless Single Sign-On (SSO)
- Skype coëxistentie
- Hybride implementatie van Exchange, waaronder:
  - Volledig gedeelde algemene adreslijst (GAL) tussen uw on-premises Exchange-omgeving en Microsoft 365.
  - Gal-informatie uit verschillende e-mailsystemen synchroniseren.
  - De mogelijkheid om gebruikers toe te voegen aan en te verwijderen uit microsoft 365-serviceaanbiedingen. Hiervoor zijn de volgende gegevens vereist:
  - Tweewegsynchronisatie moet worden geconfigureerd tijdens het instellen van adreslijstsynchronisatie. Adreslijstsynchronisatiehulpmiddelen schrijven standaard alleen adreslijstgegevens naar de cloud. Wanneer u tweewegsynchronisatie configureert, stelt u de functie voor terugschrijven in, zodat een beperkt aantal objectkenmerken vanuit de cloud wordt gekopieerd en vervolgens teruggeschreven naar uw lokale AD DS. Terugschrijven wordt ook wel de hybride exchange-modus genoemd. 
  - Een on-premises hybride implementatie van Exchange
  - De mogelijkheid om bepaalde gebruikerspostvakken naar Microsoft 365 te verplaatsen terwijl andere postvakken van gebruikers on-premises blijven.
  - Veilige afzenders en geblokkeerde afzenders on-premises worden gerepliceerd naar Microsoft 365.
  - Basisdelegering en send-on-behalf-of-email-functionaliteit.
  - U hebt een geïntegreerde on-premises smartcard of meervoudige verificatieoplossing.
- Synchronisatie van foto's, miniaturen, vergaderruimten en beveiligingsgroepen

## <a name="next-step"></a>Volgende stap

Zie Voorbereiden op adreslijstsynchronisatie wanneer u klaar bent om hybride identiteit [te implementeren.](prepare-for-directory-synchronization.md)
