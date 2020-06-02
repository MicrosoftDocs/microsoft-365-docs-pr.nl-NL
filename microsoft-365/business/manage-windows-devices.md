---
title: Inschakelen domein-aangesloten Windows 10-apparaten worden beheerd door Microsoft 365 voor bedrijven
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Meer informatie over het inschakelen van Microsoft 365 om lokale Windows 10-apparaten met Actieve Directory in slechts een paar stappen te beschermen.
ms.openlocfilehash: 7bfe5da8701a17712fa249eac99a22b8d5a1b2d1
ms.sourcegitcommit: 2d664a95b9875f0775f0da44aca73b16a816e1c3
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/01/2020
ms.locfileid: "44471042"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Inschakelen domein-aangesloten Windows 10-apparaten worden beheerd door Microsoft 365 Business Premium

Als uw organisatie on-premises Windows Server Active Directory gebruikt, u Microsoft 365 Business Premium instellen om uw Windows 10-apparaten te beschermen, terwijl u toch toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is.
Als u deze beveiliging wilt instellen, u **hybride azure ad-apparaten**implementeren. Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.

In deze video worden de stappen beschreven voor het instellen van dit voor het meest voorkomende scenario, dat ook wordt beschreven in de volgende stappen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Voorbereiden op directorysynchronisatie 

Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert [u Voorbereiden op adreslijstsynchronisatie naar Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In het bijzonder:

   - Zorg ervoor dat er geen duplicaten in uw map bestaan voor de volgende kenmerken: **e-mail,** **proxyAdressen**en **userPrincipalName**. Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.
   
   - We raden u aan het kenmerk **USERPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren op basis van het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker. Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*
   
   - Als het Active Directory-domein eindigt in een niet-routeerbaar achtervoegsel zoals *.local* of *.lan*, in plaats van een internetroertable achtervoegsel zoals *.com* of *.org,* past u eerst het UPN-achtervoegsel van het lokale gebruikersaccounts aan zoals beschreven in [Een niet-routeerbaar domein voorbereiden voor adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect installeren en configureren

Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory wilt synchroniseren met Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in. Zie [Adreslijstsynchronisatie instellen voor Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) voor meer informatie.

> [!NOTE]
> De stappen zijn precies hetzelfde voor Microsoft 365 voor bedrijven. 

Terwijl u uw opties voor Azure AD Connect configureert, raden we u aan **wachtwoordsynchronisatie,** **naadloze aanmelding met één aanmelding**en de functie voor het **terugschrijven van wachtwoorden** in te schakelen, die ook wordt ondersteund in Microsoft 365 voor bedrijven.

> [!NOTE]
> Er zijn enkele extra stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect. Zie Hoe voor meer [informatie: wachtwoordschrijftijd configureren.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Hybride Azure AD Join configureren

Voordat u Windows 10-apparaten inschakelt als Hybride Azure AD, moet u ervoor zorgen dat u aan de volgende voorwaarden voldoet:

   - U voert de nieuwste versie van Azure AD Connect uit.

   - Azure AD connect heeft alle computerobjecten gesynchroniseerd van de apparaten waaraan u hybride Azure AD wilt zijn. Als de computerobjecten behoren tot specifieke organisatie-eenheden (OU), controleert u of deze OE's ook zijn ingesteld voor synchronisatie in Azure AD connect.

Als u bestaande windows 10-apparaten met een domein wilt registreren als Hybride Azure AD is aangesloten, voert u de stappen uit in de [zelfstudie: Hybride Azure Active Directory-join configureren voor beheerde domeinen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Met deze hybride mogelijkheid biedt uw bestaande on-premises Active Directory zich aan aangesloten bij Windows 10-computers en maken ze klaar voor de cloud.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Automatische inschrijving inschakelen voor Windows 10

 Zie [Automatisch een Windows 10-apparaat inschrijven met groepsbeleid](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)als u Windows 10-apparaten automatisch wilt inschrijven voor beheer van mobiele apparaten in Intune. U het groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen u de sjablonen Groepsbeleidsbeheer en ADMX gebruiken om deze groepsbeleidsinstelling op uw domeincontroller te maken.

## <a name="5-configure-seamless-single-sign-on"></a>5. Naadloos aanmelden configureren

  Seamless SSO meldt gebruikers automatisch aan bij hun Microsoft 365-cloudbronnen wanneer ze bedrijfscomputers gebruiken. Implementeer eenvoudig een van de twee opties voor groepsbeleid die zijn beschreven in [Azure Active Directory Naadloze aanmelding: Snel starten](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Met de optie **Groepsbeleid** kunnen gebruikers hun instellingen niet wijzigen, terwijl de optie **Groepsbeleidsvoorkeur** de waarden instelt, maar ze ook door de gebruiker kan worden geconfigureerd.

## <a name="6-set-up-windows-hello-for-business"></a>6. Windows Hello voor Bedrijven instellen

 Windows Hello voor Bedrijven vervangt wachtwoorden door sterke tweestapsverificatie (2FA) voor het aanmelden bij een lokale computer. De ene factor is een asymmetrisch sleutelpaar en de andere is een pincode of een andere lokale beweging, zoals vingerafdruk of gezichtsherkenning als uw apparaat dit ondersteunt. We raden u aan wachtwoorden te vervangen door 2FA en Windows Hello for Business waar mogelijk.

Als u Hybride Windows Hello voor Bedrijven wilt configureren, controleert u de vereisten voor hybride [sleutelvertrouwen in Windows Hello voor bedrijven](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Volg vervolgens de instructies in [De vertrouwensinstellingen voor hybride Windows Hello voor Bedrijven configureren.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings) 
