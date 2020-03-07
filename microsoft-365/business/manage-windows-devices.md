---
title: Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd
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
description: Meer informatie over het inschakelen van Microsoft 365 om lokale Windows 10-apparaten met Active-Directory in slechts enkele stappen te beschermen.
ms.openlocfilehash: 625eb7ac344b060409101d650ff30044d073f5bf
ms.sourcegitcommit: 217de0fc54cbeaea32d253f175eaf338cd85f5af
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/07/2020
ms.locfileid: "42561455"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd

Als uw organisatie On-premises gebruik maakt van Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beschermen, terwijl u nog steeds toegang behoudt tot on-premises bronnen waarvoor lokale verificatie vereist is.
Als u deze beveiliging wilt instellen, u **hybride Azure AD-verbonden apparaten**implementeren. Deze apparaten worden samengevoegd met zowel uw on-premises Active Directory als uw Azure Active Directory.

In deze video worden de stappen beschreven voor het instellen van dit scenario voor het meest voorkomende scenario, dat ook wordt beschreven in de stappen die volgen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. Voorbereiden op adreslijstsynchronisatie 

Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert u [Voorbereiden op adreslijstsynchronisatie naar Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In het bijzonder:

   - Zorg ervoor dat er geen duplicaten bestaan in uw map voor de volgende kenmerken: **e-mail,** **proxyAdressen**en **userPrincipalName**. Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.
   
   - We raden u aan het kenmerk **userPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren dat overeenkomt met het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker. Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*
   
   - Als het Active Directory-domein eindigt in een niet-routable achtervoegsel zoals *.local* of ** *.lan*, pas u het UPN-achtervoegsel van de lokale gebruikersaccounts eerst aan zoals beschreven in [Een niet-routeerbaar domein voorbereiden op adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). ** 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect installeren en configureren

Als u uw gebruikers, groepen en contactpersonen vanuit de lokale Active Directory wilt synchroniseren in Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in. Zie [Adreslijstsynchronisatie instellen voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) voor meer informatie.

> [!NOTE]
> De stappen zijn precies hetzelfde voor Microsoft 365 Business. 

Terwijl u uw opties voor Azure AD Connect configureert, raden we u aan **wachtwoordsynchronisatie,** **naadloze single sign-on**en de **functie voor het terugschrijven** van wachtwoorden in te schakelen, die ook wordt ondersteund in Microsoft 365 Business.

> [!NOTE]
> Er zijn enkele extra stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect. Zie [How-to: configureer password writeback](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie. 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. Hybride Azure AD-join configureren

Voordat u Windows 10-apparaten inschakelt om hybride Azure AD te zijn, moet u ervoor zorgen dat u aan de volgende voorwaarden voldoet:

   - U voert de nieuwste versie van Azure AD Connect uit.

   - Azure AD connect heeft alle computerobjecten gesynchroniseerd van de apparaten waaraan u hybride Azure AD wilt deelnemen. Als de computerobjecten tot specifieke organisatie-eenheden (OU) behoren, controleert u of deze OU's zijn ingesteld voor synchronisatie in Azure AD connect.

Als u bestaande windows 10-apparaten met domein wilt registreren terwijl hybride Azure AD is samengevoegd, voert u de stappen uit in de [zelfstudie: Hybride Azure Active Directory-join configureren voor beheerde domeinen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Deze hybride maakt uw bestaande on-premises Active Directory aangesloten bij Windows 10-computers en maakt ze cloudklaar.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. Automatische inschrijving voor Windows 10 inschakelen

 Zie Een [Windows 10-apparaat automatisch](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy)inschrijven met groepsbeleid als u Windows 10-apparaten automatisch wilt inschrijven voor beheer van mobiele apparaten voor mobiel apparaat in Intune. U het groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen, u de groepsbeleidsbeheerconsole en ADMX-sjablonen gebruiken om deze groepsbeleidsinstelling op uw domeincontroller te maken.

## <a name="5-configure-seamless-single-sign-on"></a>5. Naadloze aanmelding configureren

  Naadloze SSO ondertekent gebruikers automatisch in hun Microsoft 365-cloudbronnen wanneer ze bedrijfscomputers gebruiken. Implementeer eenvoudig een van de twee groepsbeleidsopties die zijn beschreven in [Azure Active Directory Seamless Single Sign-On: Snel aanmelding.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature) Met de optie **Groepsbeleid** kunnen gebruikers hun instellingen niet wijzigen, terwijl de optie **Groepsbeleidsvoorkeur** de waarden instelt, maar ze ook door de gebruiker configureerbaar laat.

## <a name="6-set-up-windows-hello-for-business"></a>6. Windows Hello voor Bedrijven instellen

 Windows Hello for Business vervangt wachtwoorden door sterke tweestapsverificatie (2FA) voor het aanmelden bij een lokale computer. Een factor is een asymmetrisch sleutelpaar, en de andere is een pincode of een andere lokale beweging, zoals vingerafdruk of gezichtsherkenning als uw apparaat het ondersteunt. We raden u aan wachtwoorden waar mogelijk te vervangen door 2FA en Windows Hello for Business.

Als u Hybride Windows Hello voor Bedrijven wilt configureren, bekijkt u de [vereisten voor windows hello voor bedrijven voor](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs)hybride sleutel vertrouwen. Volg vervolgens de instructies in De belangrijkste vertrouwensinstellingen van [Windows Hello voor Bedrijven configureren.](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings) 
