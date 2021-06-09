---
title: Microsoft 365 identiteitsmodellen en -Azure Active Directory
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.date: 09/30/2020
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- M365-identity-device-management
- M365-security-compliance
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 06a189e7-5ec6-4af2-94bf-a22ea225a7a9
description: Meer informatie over het beheren van de Azure AD-gebruikersidentiteitsservice in Microsoft 365 met behulp van alleen-cloud- of hybride identiteitsmodellen.
ms.openlocfilehash: b54ccce6ea2a468e02d9db95e7932d847df4e64b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905702"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365 identiteitsmodellen en -Azure Active Directory

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 gebruikt Azure Active Directory (Azure AD), een cloudgebaseerde gebruikersidentiteits- en verificatieservice die is opgenomen in uw Microsoft 365-abonnement, voor het beheren van identiteiten en verificatie voor Microsoft 365. Het correct configureren van uw identiteitsinfrastructuur is essentieel voor het beheren Microsoft 365 gebruikerstoegang en machtigingen voor uw organisatie.

Voordat u begint, bekijkt u deze video voor een overzicht van identiteitsmodellen en verificatie voor Microsoft 365.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Uw eerste planningskeuze is het Microsoft 365 identiteitsmodel.

## <a name="microsoft-365-identity-models"></a>Microsoft 365 identiteitsmodellen

Als u gebruikersaccounts wilt plannen, moet u eerst de twee identiteitsmodellen in Microsoft 365. U kunt de identiteiten van uw organisatie alleen in de cloud behouden of u kunt uw on-premises AD DS-identiteiten (Active Directory Domain Services) behouden en deze gebruiken voor verificatie wanneer gebruikers toegang hebben tot Microsoft 365 cloudservices.  

Hier zijn de twee typen identiteit en de beste pasvorm en voordelen.

| Attribuut | Alleen cloudidentiteit | Hybride identiteit |
|:-------|:-----|:-----|
| **Definitie** | Gebruikersaccount bestaat alleen in de Azure AD-tenant voor uw Microsoft 365 abonnement. | Gebruikersaccount bestaat in AD DS en een kopie bevindt zich ook in de Azure AD-tenant voor uw Microsoft 365 abonnement. Het gebruikersaccount in Azure AD kan ook een gehashte versie van het wachtwoord van het al gehashte AD DS-gebruikersaccount bevatten. |
| **Hoe Microsoft 365 gebruikersreferenties verifieert** | De Azure AD-tenant voor uw Microsoft 365 voert de verificatie uit met het cloudidentiteitsaccount. | De Azure AD-tenant voor Microsoft 365-abonnement verwerkt het verificatieproces of leidt de gebruiker om naar een andere identiteitsprovider. |
| **Het beste voor** | Organisaties die geen on-premises AD DS hebben of nodig hebben. | Organisaties die AD DS of een andere identiteitsprovider gebruiken. |
| **Grootste voordeel** | Eenvoudig te gebruiken. Er zijn geen extra adreslijsthulpmiddelen of -servers vereist. | Gebruikers kunnen dezelfde referenties gebruiken bij het openen van on-premises of cloudbronnen. |
||||

## <a name="cloud-only-identity"></a>Alleen cloudidentiteit

Voor een cloudidentiteit worden gebruikersaccounts gebruikt die alleen in Azure AD bestaan. Cloud-only-identiteit wordt meestal gebruikt door kleine organisaties die geen on-premises servers hebben of GEEN AD DS gebruiken om lokale identiteiten te beheren. 

Hier zijn de basisonderdelen van alleen-cloudidentiteit.
 
![Basisonderdelen van alleen-cloudidentiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

Zowel on-premises als externe (online) gebruikers gebruiken hun Azure AD-gebruikersaccounts en -wachtwoorden om toegang te krijgen tot Microsoft 365 cloudservices. Azure AD verifieert gebruikersreferenties op basis van de opgeslagen gebruikersaccounts en wachtwoorden.

### <a name="administration"></a>Beheer
Omdat gebruikersaccounts alleen worden opgeslagen in Azure AD, beheert u cloudidentiteiten met hulpmiddelen zoals het [Microsoft 365-beheercentrum](../admin/add-users/index.yml) en [Windows PowerShell.](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md) 

## <a name="hybrid-identity"></a>Hybride identiteit

Hybride identiteit maakt gebruik van accounts die afkomstig zijn van een on-premises AD DS en die een kopie hebben in de Azure AD-tenant van een Microsoft 365-abonnement. De meeste wijzigingen stromen echter maar op één manier. Wijzigingen die u aan te brengen in AD DS-gebruikersaccounts worden gesynchroniseerd met de kopie in Azure AD. Wijzigingen in cloudaccounts in Azure AD, zoals nieuwe gebruikersaccounts, worden echter niet gesynchroniseerd met AD DS.

Azure AD Verbinding maken biedt de lopende accountsynchronisatie. Deze wordt uitgevoerd op een on-premises server, controleert op wijzigingen in de AD DS en doorgestuurd naar Azure AD. Azure AD Verbinding maken biedt de mogelijkheid om te filteren welke accounts worden gesynchroniseerd en of u een gehashte versie van gebruikerswachtwoorden wilt synchroniseren, ook wel bekend als wachtwoordhashsynchronisatie (PHS).

Wanneer u hybride identiteit implementeert, is uw on-premises AD DS de gezaghebbende bron voor accountgegevens. Dit betekent dat u beheertaken voornamelijk on-premises uitvoert, die vervolgens worden gesynchroniseerd met Azure AD. 

Hier zijn de onderdelen van hybride identiteit.

![Onderdelen van hybride identiteit](../media/about-microsoft-365-identity/hybrid-identity.png)

De Azure AD-tenant heeft een kopie van de AD DS-accounts. In deze configuratie verifiëren zowel on-premises als externe gebruikers die toegang hebben tot Microsoft 365 cloudservices tegen Azure AD.

>[!Note]
>U moet altijd Azure AD-Verbinding maken gebruiken om gebruikersaccounts te synchroniseren voor hybride identiteit. U hebt de gesynchroniseerde gebruikersaccounts in Azure AD nodig voor het uitvoeren van licentietoewijzing en groepsbeheer, het configureren van machtigingen en andere beheertaken waarbij gebruikersaccounts zijn betrokken.
>

### <a name="administration"></a>Beheer

Omdat de oorspronkelijke en gezaghebbende gebruikersaccounts zijn opgeslagen in de on-premises AD DS, beheert u uw identiteiten met dezelfde hulpprogramma's als uw AD DS. 

U gebruikt het beheercentrum Microsoft 365 PowerShell niet voor Microsoft 365 gesynchroniseerde gebruikersaccounts in Azure AD.

## <a name="next-step"></a>Volgende stap

Zie [Alleen-cloudidentiteit](cloud-only-identities.md)als u het cloud-only-identiteitsmodel nodig hebt.

Zie Hybride identiteit als u het hybride identiteitsmodel [nodig hebt.](plan-for-directory-synchronization.md)


## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise overzicht](microsoft-365-overview.md)