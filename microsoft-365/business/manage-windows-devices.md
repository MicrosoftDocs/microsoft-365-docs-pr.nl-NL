---
title: Ingeschakeld voor windows 10-apparaten met domeindie worden beheerd door Microsoft 365 voor bedrijven
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
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Lees hoe u Microsoft 365 in staat stelt om lokale Windows 10-apparaten met Active Directory in slechts een paar stappen te beschermen.
ms.openlocfilehash: adc125c32fe5aa56be8c17c07f28316602a36594
ms.sourcegitcommit: 46644f9778bc70ab6d62783e0a1e60ba2eccc27f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/08/2020
ms.locfileid: "44165804"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-for-business"></a>Ingeschakeld voor windows 10-apparaten met domeindie worden beheerd door Microsoft 365 voor bedrijven

Als uw organisatie on-premises Windows Server Active Directory gebruikt, u Microsoft 365 voor bedrijven instellen om uw Windows 10-apparaten te beschermen, terwijl u toch toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is.
Als u deze beveiliging wilt instellen, u **hybride Azure AD-apparaten**implementeren. Deze apparaten zijn verbonden met zowel uw on-premises Active Directory als uw Azure Active Directory.

In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario, dat ook wordt beschreven in de volgende stappen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Voorbereiden op adreslijstsynchronisatie 

Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert [u Voorbereiden op adreslijstsynchronisatie naar Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In het bijzonder:

   - Zorg ervoor dat er geen duplicaten in uw map bestaan voor de volgende kenmerken: **e-mail,** **proxyAdressen**en **userPrincipalName**. Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.
   
   - We raden u aan het kenmerk **userPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren op het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker. Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*
   
   - Als het Active Directory-domein eindigt in een niet-routable achtervoegsel zoals *.local* of *.lan,* in plaats van een internetroutable achtervoegsel zoals *.com* of *.org,* past u het UPN-achtervoegsel van de lokale gebruikersaccounts eerst aan zoals beschreven in [Een niet-routeerbaar domein voorbereiden voor adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect installeren en configureren

Als u uw gebruikers, groepen en contactpersonen vanuit de lokale Active Directory wilt synchroniseren met Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in. Zie [Adreslijstsynchronisatie instellen voor Office 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) voor meer informatie.

> [!NOTE]
> De stappen zijn precies hetzelfde voor Microsoft 365 voor bedrijven. 

Terwijl u uw opties voor Azure AD Connect configureert, raden we u aan **wachtwoordsynchronisatie,** **naadloze aanmelding**en de functie **voor het terugschrijven** van wachtwoorden in te schakelen, die ook wordt ondersteund in Microsoft 365 voor bedrijven.

> [!NOTE]
> Er zijn enkele aanvullende stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect. Zie [How-to: wachtwoordterugschrijven configureren](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie. 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Hybride Azure AD configureren Join

Voordat u Windows 10-apparaten hybride Azure AD inschakelt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

   - U voert de nieuwste versie van Azure AD Connect uit.

   - Azure AD Connect heeft alle computerobjecten gesynchroniseerd van de apparaten waaraan hybride Azure AD wilt zijn. Als de computerobjecten deel uitmaken van specifieke organisatie-eenheden (OU), controleert u of deze GEGEVENS ook zijn ingesteld voor synchronisatie in Azure AD-verbinding.

Als u bestaande met een domein verbonden Windows 10-apparaten wilt registreren als Hybride Azure AD is toegetreden, voert u de stappen uit in de [zelfstudie: Hybride Azure Active Directory join configureren voor beheerde domeinen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Met deze hybride kunnen uw bestaande on-premises Active Directory lid worden van Windows 10-computers en maken ze cloudklaar.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Automatische inschrijving inschakelen voor Windows 10

 Zie [Een Windows 10-apparaat automatisch inschrijven voor](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)het beheer van mobiele apparaten in Intune. U het groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen, u de console groepsbeleidsbeheer en ADMX-sjablonen gebruiken om deze groepsbeleidsinstelling op uw domeincontroller te maken.

## <a name="5-configure-seamless-single-sign-on"></a>5. Naadloze aanmelding configureren

  Naadloze SSO ondertekent gebruikers automatisch in hun Microsoft 365-cloudbronnen wanneer ze bedrijfscomputers gebruiken. Implementeer eenvoudig een van de twee groepsbeleidsopties die zijn beschreven in [Azure Active Directory Seamless Single Sign-On: Snel starten](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Met de optie **Groepsbeleid** kunnen gebruikers hun instellingen niet wijzigen, terwijl de optie **Groepsbeleidsvoorkeur** de waarden instelt, maar ze ook door de gebruiker kan worden geconfigureerd.

## <a name="6-set-up-windows-hello-for-business"></a>6. Windows Hello for Business instellen

 Windows Hello for Business vervangt wachtwoorden door sterke tweestapsverificatie (2FA) voor het aanmelden bij een lokale computer. De ene factor is een asymmetrisch sleutelpaar, en de andere is een pincode of een ander lokaal gebaar, zoals vingerafdruk of gezichtsherkenning als uw apparaat dit ondersteunt. We raden u aan om wachtwoorden waar mogelijk te vervangen door 2FA en Windows Hello for Business.

Als u Hybride Windows Hello voor Bedrijven wilt configureren, controleert u de [vertrouwensrelatie met de hybride sleutel windows hello voor bedrijven.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs) Volg vervolgens de instructies in [De vertrouwensinstellingen voor hybride Windows Hello voor Bedrijven configureren.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings) 
