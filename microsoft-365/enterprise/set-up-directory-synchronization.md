---
title: Adreslijstsynchronisatie instellen voor Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
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
description: Meer informatie over het instellen van adreslijstsynchronisatie tussen Microsoft 365 en uw on-premises Active Directory.
ms.openlocfilehash: 51cf52bd81004157606c884fd4f0b5d3604b877a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924902"
---
# <a name="set-up-directory-synchronization-for-microsoft-365"></a>Adreslijstsynchronisatie instellen voor Microsoft 365

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

Microsoft 365 gebruikt een Azure Active Directory-tenant (Azure AD) om identiteiten op te slaan en te beheren voor verificatie en machtigingen voor toegang tot cloudbronnen. 

Als u een on-premises AD DS-domein of -forest (Active Directory Domain Services) hebt, kunt u uw AD DS-gebruikersaccounts, groepen en contactpersonen synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement. Dit is een hybride identiteit voor Microsoft 365. Hier zijn de onderdelen.

![Onderdelen van adreslijstsynchronisatie voor Microsoft 365](../media/about-microsoft-365-identity/hybrid-identity.png)

Azure AD Connect wordt uitgevoerd op een on-premises server en synchroniseert uw AD DS met de Azure AD-tenant. Naast adreslijstsynchronisatie kunt u ook de volgende verificatieopties opgeven:

- Wachtwoordhashsynchronisatie (PHS)

  Azure AD voert de verificatie zelf uit.

- Pass Through-verificatie (PTA)

  Azure AD heeft AD DS de verificatie laten uitvoeren.

- Federatieve verificatie

  Azure AD verwijst de clientcomputer die verificatie aanvraagt naar een andere identiteitsprovider.

Zie [Hybride identiteiten voor](plan-for-directory-synchronization.md) meer informatie.
  
## <a name="1-review-prerequisites-for-azure-ad-connect"></a>1. Vereisten voor Azure AD Connect controleren

U krijgt een gratis Azure AD-abonnement met uw Microsoft 365-abonnement. Wanneer u adreslijstsynchronisatie in stelt, installeert u Azure AD Connect op een van uw on-premises servers.
  
Voor Microsoft 365 moet u het volgende doen:
  
- Controleer uw on-premises domein. De wizard Azure AD Connect begeleidt u hier doorheen.
- Verkrijg de gebruikersnamen en wachtwoorden voor de beheerdersaccounts van uw Microsoft 365-tenant en AD DS.

Voor uw on-premises server waarop u Azure AD Connect installeert, hebt u het volgende nodig:
  
|**Server OS**|**Andere software**|
|:-----|:-----|
|Windows Server 2012 R2 en hoger | - PowerShell is standaard geïnstalleerd, er is geen actie vereist.  <br> - Net 4.5.1 en latere versies worden aangeboden via Windows Update. Zorg ervoor dat u de meest recente updates voor Windows Server hebt geïnstalleerd in het Configuratiescherm. |
|Windows Server 2008 R2 met Service Pack 1 (SP1)** of Windows Server 2012 | - De nieuwste versie van PowerShell is beschikbaar in Windows Management Framework 4.0. Zoek deze in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 en latere versies zijn beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |
|Windows Server 2008 | - De meest recente ondersteunde versie van PowerShell is beschikbaar in Windows Management Framework 3.0, beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996)  <br> - .Net 4.5.1 en latere versies zijn beschikbaar in [het Microsoft Downloadcentrum.](https://go.microsoft.com/fwlink/p/?LinkId=717996) |

Zie [Vereisten voor Azure Active Directory Connect](/azure/active-directory/hybrid/how-to-connect-install-prerequisites) voor de details van hardware-, software-, account- en machtigingsvereisten, SSL-certificaatvereisten en objectlimieten voor Azure AD Connect.
  
U kunt ook de versieversiegeschiedenis van Azure AD Connect [bekijken](/azure/active-directory/hybrid/reference-connect-version-history) om te zien wat er is opgenomen en opgelost in elke release.

## <a name="2-install-azure-ad-connect-and-configure-directory-synchronization"></a>2. Azure AD Connect installeren en adreslijstsynchronisatie configureren

Zorg ervoor dat u het volgende hebt voordat u begint:

- De gebruikersnaam en het wachtwoord van een globale Microsoft 365-beheerder
- De gebruikersnaam en het wachtwoord van een AD DS-domeinbeheerder
- Welke verificatiemethode (PHS, PTA, federatief)
- Of u Azure [AD Seamless Single Sign-on (SSO) wilt gebruiken](/azure/active-directory/hybrid/how-to-connect-sso)

Ga als volgt te werk:

1. Meld u aan bij [het Microsoft 365-beheercentrum](https://admin.microsoft.com) ( https://admin.microsoft.com) en kies **Gebruikers** \> **Actieve gebruikers** aan de linkerkant van de navigatie.
2. Kies op **de pagina** Actieve gebruikers de **optie Meer** (drie puntjes) \> **Adreslijstsynchronisatie.**
  
3. Selecteer op **de voorbereidingspagina voor Azure Active Directory** de optie Ga naar het **Downloadcentrum om de koppeling Van het hulpprogramma Azure AD Connect** te downloaden om aan de slag te gaan. 
4. Volg de stappen in [Azure AD Connect en Azure AD Connect Health installation roadmap](/azure/active-directory/hybrid/how-to-connect-install-roadmap).

## <a name="3-finish-setting-up-domains"></a>3. Het instellen van domeinen voltooien

Volg de stappen in [DNS-records maken voor Microsoft 365](/office365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) wanneer u uw DNS-records beheert om het instellen van uw domeinen te voltooien.

## <a name="next-step"></a>Volgende stap

[Licenties aan gebruikersaccounts toewijzen](assign-licenses-to-user-accounts.md)