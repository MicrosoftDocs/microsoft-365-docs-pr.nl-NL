---
title: Microsoft 365-identiteits modellen en Azure Active Directory
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
description: Meer informatie over het beheren van de Azure AD User Identity-service in Microsoft 365 met Cloud only of Hybrid Identity types.
ms.openlocfilehash: 6b5b80584408671a1925e32df1fbf458b7c16139
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327949"
---
# <a name="microsoft-365-identity-models-and-azure-active-directory"></a>Microsoft 365-identiteits modellen en Azure Active Directory

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 maakt gebruik van Azure Active Directory (Azure AD), een op de cloud gebaseerde gebruikers-id en verificatieservice die deel uitmaakt van uw Microsoft 365-abonnement, voor het beheren van identiteiten en verificatie voor Microsoft 365. De juiste configuratie van de identiteits infrastructuur is essentieel voor het beheren van gebruikers toegang en machtigingen voor Microsoft 365 voor uw organisatie.

Bekijk deze video voor een overzicht van identiteits modellen en authenticatie voor Microsoft 365 voordat u begint.

<p> </p>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

Uw eerste planning is het identiteits model van Microsoft 365.

## <a name="microsoft-365-identity-models"></a>Microsoft 365-identiteits modellen

Voor het plannen van gebruikersaccounts moet u eerst inzicht krijgen in de twee identiteits modellen in Microsoft 365. U kunt de identiteiten van uw organisatie alleen in de Cloud behouden, maar u kunt ook uw on-premises Active Directory Domain Services (AD DS)-id's bijhouden en ze gebruiken voor verificatie wanneer gebruikers toegang krijgen tot de Cloud Services van Microsoft 365.  

Dit zijn de twee typen identiteiten, en het best passende en voordelen.

| Attribuut | Alleen cloudidentiteit | Hybride identiteit |
|:-------|:-----|:-----|
| **Definitie** | Het gebruikersaccount bestaat alleen in de Azure AD-Tenant voor uw Microsoft 365-abonnement. | Gebruikersaccount bestaat in AD DS en een kopie bevindt zich ook in de Azure AD-Tenant voor uw Microsoft 365-abonnement. Het gebruikersaccount in azure AD kan ook een gehasheerde versie van het wachtwoord voor een gehasheerde gebruikersaccount bevatten. |
| **Hoe Microsoft 365 gebruikersreferenties verifieert** | Met de Azure AD-Tenant voor uw Microsoft 365-abonnement wordt de authenticatie met de Cloud-identiteits account uitgevoerd. | Met de Azure AD-Tenant voor uw Microsoft 365-abonnement wordt het verificatieproces verwerkt of wordt de gebruiker omgeleid naar een andere identiteitsprovider. |
| **Geschikt voor** | Organisaties die geen on-premises AD DS hebben of behoefte hebben. | Organisaties die AD DS of een andere identiteitsprovider gebruiken. |
| **Grootste voordeel** | Eenvoudig te gebruiken. Geen extra hulpmiddelen voor directory's of servers vereist. | Gebruikers kunnen dezelfde referenties gebruiken voor het openen van on-premises of Cloud bronnen. |
||||

## <a name="cloud-only-identity"></a>Alleen cloudidentiteit

Een identiteit in de Cloud maakt gebruik van gebruikersaccounts die alleen bestaan in azure AD. Alleen in de cloud worden identiteiten in kleine organisaties gebruikt die geen on-premises servers hebben of geen gebruikmaken van AD DS voor het beheren van lokale identiteiten. 

Hier volgen de basisonderdelen van de identiteit van de Cloud.
 
![Basisonderdelen van de alleen-Cloud identiteit](../media/about-microsoft-365-identity/cloud-only-identity.png)

Gebruikers van on-premises en externe gebruikers (online) gebruiken hun gebruikersaccounts en wachtwoorden van Azure AD om toegang te krijgen tot de cloudservices van Microsoft 365. Azure AD verifieert gebruikersreferenties op basis van zijn opgeslagen gebruikersaccounts en wachtwoorden.

### <a name="administration"></a>Beheer
Aangezien gebruikersaccounts alleen in azure AD zijn opgeslagen, beheert u Cloud Identities met hulpprogramma's zoals het [Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/) en [Windows PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md). 

## <a name="hybrid-identity"></a>Hybride identiteit

De Hybrid Identity gebruikt accounts die afkomstig zijn van een on-premises AD DS en die een kopie hebben in de Azure AD-Tenant van een abonnement van Microsoft 365. De meeste wijzigingen zijn echter maar één manier. Wijzigingen die u aanbrengt in AD DS-gebruikersaccounts, worden gesynchroniseerd met hun kopie in azure AD. Wijzigingen die zijn aangebracht in Cloud accounts in azure AD, zoals nieuwe gebruikersaccounts, worden niet gesynchroniseerd met AD DS.

Azure AD Connect biedt de voortdurende synchronisatie van uw account. De app wordt uitgevoerd op een on-premises server, controleert op wijzigingen in de AD DS en stuurt deze wijzigingen door naar Azure AD. Azure AD Connect biedt de mogelijkheid om te filteren welke accounts worden gesynchroniseerd en of u een gehasheerde versie van gebruikerswachtwoorden wilt synchroniseren, ook wel hash-synchronisatie (PHS) genoemd.

Wanneer u hybride identiteit implementeert, is uw on-premises AD DS de gezaghebbende bron voor de accountgegevens. Dit betekent dat u beheertaken doorgaans on-premise uitvoert, die vervolgens worden gesynchroniseerd met Azure AD. 

Hier volgen de onderdelen van de Hybrid Identity.

![Onderdelen van een hybride identiteit](../media/about-microsoft-365-identity/hybrid-identity.png)

De Azure AD-Tenant heeft een kopie van de AD DS-accounts. In deze configuratie wordt zowel on-premises als externe gebruikers die toegang hebben tot Microsoft 365 cloudservices verifiëren tegen Azure AD.

>[!Note]
>U moet altijd Azure AD Connect gebruiken om gebruikersaccounts voor Hybrid Identity te synchroniseren. Voor het uitvoeren van licentietoewijzing en groepsbeheer kunt u de gesynchroniseerde gebruikersaccounts in azure AD uitvoeren, machtigingen configureren en andere beheertaken waarbij gebruikersaccounts worden gebruikt.
>

### <a name="administration"></a>Beheer

Aangezien de oorspronkelijke en de gezaghebbende gebruikersaccounts zijn opgeslagen in de on-premises AD DS, beheert u uw identiteiten met dezelfde hulpmiddelen als voor het beheren van de AD DS. 

U gebruikt het Microsoft 365-Beheercentrum of PowerShell voor Microsoft 365 niet voor het beheren van gesynchroniseerde gebruikersaccounts in azure AD.

## <a name="next-step"></a>Volgende stap

Als u het identiteits model voor de Cloud only nodig hebt, raadpleegt u de [Cloud-only-identiteit](cloud-only-identities.md).

Als u het Hybrid Identity model nodig hebt, raadpleegt u [hybride identiteit](plan-for-directory-synchronization.md).


## <a name="see-also"></a>Zie ook

[Overzicht van Microsoft 365 Enterprise](microsoft-365-overview.md)
