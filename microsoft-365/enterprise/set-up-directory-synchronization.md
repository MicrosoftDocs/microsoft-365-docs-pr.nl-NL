---
title: Adreslijstsynchronisatie voor Microsoft 365 instellen
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 06/15/2020
audience: Admin
ms.topic: get-started-article
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
description: Leer hoe u adreslijstsynchronisatie tussen Microsoft 365 en uw on-premises Active Directory kunt instellen.
ms.openlocfilehash: 3a846a6c558f221c1869dce6da27e3d34680f75d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46689007"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Adreslijstsynchronisatie voor Microsoft 365 instellen

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

In Microsoft 365 wordt een Azure Active Directory (Azure AD)-Tenant gebruikt voor het opslaan en beheren van identiteiten voor verificatie en machtigingen voor toegang tot Cloud bronnen. 

Als u een on-premises Active Directory Domain Services (AD DS) hebt, kunt u uw gebruikersaccounts, groepen en contactpersonen van AD DS synchroniseren met de Azure AD-Tenant van uw Microsoft 365-abonnement. Dit is de hybride identiteit voor Microsoft 365. Hier volgen de onderdelen.

![Onderdelen van adreslijstsynchronisatie voor Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect wordt uitgevoerd op een on-premises server en de AD DS wordt gesynchroniseerd met de Azure AD-Tenant. Naast adreslijstsynchronisatie kunt u ook deze verificatie-opties opgeven:

- Synchronisatie van wachtwoord hash (PHS)

  Azure AD voert de authenticatie zelf uit.

- Pass Through-verificatie (PTA)

  Azure AD Active Directory heeft de authenticatie uitvoeren.

- Federatieve verificatie

  Azure AD stuurt de clientcomputer om authenticatie vragen om contact op te nemen met een andere identiteitsprovider.

Zie [hybride identiteiten](plan-for-directory-synchronization.md) voor meer informatie.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. vereisten voor Azure AD Connect controleren

U krijgt een gratis Azure AD-abonnement met uw abonnement op Microsoft 365. Wanneer u adreslijstsynchronisatie instelt, installeert u Azure AD Connect op een van uw on-premises servers.
  
Voor Microsoft 365 moet u het volgende doen:
  
- Controleer uw on-premises domein. Met de wizard Azure AD Connect wordt u begeleid.
- Download de gebruikersnamen en wachtwoorden voor de beheerdersaccounts van uw Microsoft 365-Tenant en AD DS.

Voor uw on-premises server waarop u Azure AD Connect installeert, hebt u het volgende nodig:
  
|**Server OS**|**Overige software**|
|:-----|:-----|
|Windows Server 2012 R2 en hoger | -PowerShell is standaard geïnstalleerd; geen actie vereist.  <br> -Net 4.5.1 en nieuwere versies zijn beschikbaar via Windows Update. Zorg dat u de meest recente updates voor Windows Server hebt geïnstalleerd in het Configuratiescherm. |
|Windows Server 2008 R2 met Service Pack 1 (SP1) * * of Windows Server 2012 | -De nieuwste versie van PowerShell is beschikbaar in Windows Management Framework 4,0. Zoek de app op het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> -.Net 4.5.1 en nieuwere releases zijn beschikbaar in het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996). |
|Windows Server 2008 | -De nieuwste ondersteunde versie van PowerShell is beschikbaar in Windows Management Framework 3,0, dat beschikbaar is in het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996).  <br> -.Net 4.5.1 en nieuwere releases zijn beschikbaar in het [Microsoft Download centrum](https://go.microsoft.com/fwlink/p/?LinkId=717996). |

Zie vereisten [voor Azure Active Directory Connect](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-prerequisites) voor de details van hardware, software, account-en machtigings vereisten, vereisten voor de SSL-certificaten en de object limieten voor Azure AD Connect.
  
U kunt ook de geschiedenis van de [release geschiedenis](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history) van Azure AD Connect bekijken om te zien wat er is inbegrepen en opgelost in elke versie.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure AD Connect installeren en Adreslijstsynchronisatie configureren

Voordat u begint, moet u het volgende doen:

- De gebruikersnaam en het wachtwoord van een globale beheerder van Microsoft 365
- De gebruikersnaam en het wachtwoord van een AD DS-domeinbeheerder
- Welke verificatiemethode (PHS, PTA, federatieve)
- Of u gebruikmaakt [van eenmalige aanmelding via Azure AD (SSO)](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso)

Volg deze stappen:

1. Meld u aan bij het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) ( https://admin.microsoft.com) en kies **gebruikers** \> **actieve gebruikers** in de navigatie aan de linkerkant.
2. Kies op de pagina **actieve gebruikers** de optie **meer** (drie stippen) \> **adreslijstsynchronisatie**.
  
3. Selecteer op de pagina **Azure Active Directory Preparation** de optie **Ga naar het Download centrum om de koppeling naar het Azure AD Connect-hulpprogramma** te downloaden om aan de slag te gaan. 
4. Voer de stappen uit in [Azure AD Connect en Azure AD Connect Health Installation](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-install-roadmap).

## <a name="3-finish-setting-up-domains"></a>3. het instellen van domeinen voltooien

Volg de stappen in [DNS-records voor Microsoft 365 maken wanneer u uw DNS-records beheert](https://docs.microsoft.com/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) om het instellen van uw domein te voltooien.

## <a name="next-step"></a>Volgende stap

[Licenties toewijzen aan gebruikersaccounts](assign-licenses-to-user-accounts.md)
