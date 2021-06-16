---
title: Adreslijstsynchronisatie instellen voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED15
- MBS150
- BCS160
ms.assetid: 1b3b5318-6977-42ed-b5c7-96fa74b08846
description: Meer informatie over het instellen van adreslijstsynchronisatie tussen Microsoft 365 en uw on-premises Active Directory.
ms.openlocfilehash: 14b44523c0a560a71ed8dc9182f677f2ebc0b865
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926524"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Adreslijstsynchronisatie instellen voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 gebruikt een Azure Active Directory (Azure AD)-tenant om identiteiten op te slaan en te beheren voor verificatie en machtigingen voor toegang tot cloudbronnen. 

Als u een on-premises AD DS-domein of -forest (Active Directory Domain Services) hebt, kunt u uw AD DS-gebruikersaccounts, groepen en contactpersonen synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement. Dit is een hybride identiteit voor Microsoft 365. Hier zijn de onderdelen.

![Onderdelen van adreslijstsynchronisatie voor Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Verbinding maken wordt uitgevoerd op een on-premises server en synchroniseert uw AD DS met de Azure AD-tenant. Naast adreslijstsynchronisatie kunt u ook de volgende verificatieopties opgeven:

- Wachtwoordhashsynchronisatie (PHS)

  Azure AD voert de verificatie zelf uit.

- Pass Through-verificatie (PTA)

  Azure AD heeft AD DS de verificatie laten uitvoeren.

- Federatieve verificatie

  Azure AD verwijst de clientcomputer die verificatie aanvraagt naar een andere identiteitsprovider.

Zie [Hybride identiteiten voor](plan-for-directory-synchronization.md) meer informatie.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Controleer vereisten voor Azure AD-Verbinding maken

U krijgt een gratis Azure AD-abonnement met uw Microsoft 365 abonnement. Wanneer u adreslijstsynchronisatie in stelt, installeert u Azure AD Verbinding maken op een van uw on-premises servers.
  
Voor Microsoft 365 moet u het volgende doen:
  
- Controleer uw on-premises domein. De wizard Azure AD Verbinding maken begeleidt u hier doorheen.
- Verkrijg de gebruikersnamen en wachtwoorden voor de beheerdersaccounts van uw Microsoft 365 tenant en AD DS.

Voor uw on-premises server waarop u Azure AD Verbinding maken, hebt u het volgende nodig:
  
|**Server OS**|**Andere software**|
|:-----|:-----|
|Windows Server 2012 R2 en hoger | - PowerShell is standaard geïnstalleerd, er is geen actie vereist.  <br> - Net 4.5.1 en latere versies worden aangeboden via Windows Update. Zorg ervoor dat u de meest recente updates hebt geïnstalleerd Windows Server in het Configuratiescherm. |
|Windows Server 2008 R2 met Service Pack 1 (SP1)** of Windows Server 2012 | - De nieuwste versie van PowerShell is beschikbaar in Windows Management Framework 4.0. Zoek deze in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 en latere versies zijn beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |
|Windows Server 2008 | - De meest recente ondersteunde versie van PowerShell is beschikbaar in Windows Management Framework 3.0, beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 en latere versies zijn beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |

Zie [Vereisten voor Azure Active Directory Verbinding maken](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) voor de details van hardware-, software-, account- en machtigingsvereisten, SSL-certificaatvereisten en objectlimieten voor Azure AD-Verbinding maken.
  
U kunt ook de versieversiegeschiedenis van Azure AD Verbinding maken [bekijken](/azure/active-directory/hybrid/reference-connect-version-history) om te zien wat er is opgenomen en opgelost in elke release.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure AD installeren Verbinding maken adreslijstsynchronisatie configureren

Zorg ervoor dat u het volgende hebt voordat u begint:

- De gebruikersnaam en het wachtwoord van een Microsoft 365 globale beheerder
- De gebruikersnaam en het wachtwoord van een AD DS-domeinbeheerder
- Welke verificatiemethode (PHS, PTA, federatief)
- Of u Azure [AD Seamless Single Sign-on (SSO) wilt gebruiken](/azure/active-directory/hybrid/how-to-connect-sso)

Volg deze stappen:

1. Meld u aan bij [het Microsoft 365 beheercentrum](https://admin.microsoft.com) ( https://admin.microsoft.com) en kies **Gebruikers** \> **actieve gebruikers** aan de linkerkant van de navigatie.
2. Kies op **de pagina** Actieve gebruikers de **optie Meer** (drie puntjes) \> **Adreslijstsynchronisatie.**
  
3. Selecteer op **Azure Active Directory pagina Voorbereiding** de optie Ga naar het Downloadcentrum om de koppeling Azure AD Verbinding maken **aan** de slag te gaan. 
4. Volg de stappen in [Azure AD Verbinding maken en Azure AD Verbinding maken Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).

## <a name="3-finish-setting-up-domains"></a>3. Het instellen van domeinen voltooien

Volg de stappen in [DNS-records maken voor Microsoft 365 wanneer](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) u uw DNS-records beheert om het instellen van uw domeinen te voltooien.

## <a name="next-step"></a>Volgende stap

[Licenties aan gebruikersaccounts toewijzen](assign-licenses-to-user-accounts.md)