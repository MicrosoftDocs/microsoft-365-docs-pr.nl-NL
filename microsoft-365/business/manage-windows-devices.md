---
title: Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd
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
ms.custom: OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informatie over het inschakelen van Microsoft 365 voor het beveiligen van lokale AD gekoppelde Windows 10-apparaten.
ms.openlocfilehash: d1dbfc6a35d54db653ae0f911fad05ac2ce0a993
ms.sourcegitcommit: 6003d6da0a85c97357eb3dba3918eb145f381fe1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/27/2019
ms.locfileid: "37288030"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd

Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist.
Als u dit wilt instellen, u **hybride Azure AD gekoppelde apparaten**implementeren. Dit zijn apparaten die zijn gekoppeld aan uw on-premises Active Directory en uw Azure Active Directory.

De volgende Videodetails de stappen voor het instellen van dit voor de meest voorkomende scenario dat ook wordt beschreven in de volgende stappen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="1-prepare-for-directory-synchronization"></a>1. voorbereiden voor adreslijstsynchronisatie 

Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert u de [voorbereidingen voor adreslijstsynchronisatie naar Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In het bijzonder:

   - Zorg ervoor dat er geen duplicaten in uw Directory voor de volgende kenmerken zijn: **mail**, **proxyAddresses**, en **userPrincipalName**. Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd..
   
   - We raden aan dat het kenmerk **userPrincipalName** (UPN) voor elke lokale gebruikersaccount is geconfigureerd zodat deze overeenkomt met het primaire e-mailadres dat overeenkomt met de gelicentieerde microsoft 365-gebruiker. Bijvoorbeeld *Mary. Shelley @<span>contoso.<span> com* in plaats van *Mary @ contoso. local*
   
   - Als het Active Directory-domein wordt beëindigd in een niet-routeerbaar achtervoegsel zoals *. local* of *. LAN*, in plaats van een Internet routeerbaar achtervoegsel zoals *. com* of *. org*, moet u het UPN-achtervoegsel van de lokale gebruikersaccounts eerst aanpassen, zoals wordt beschreven in [Een niet-routeerbaar domein voorbereiden voor adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Installeer en configureer Azure AD Connect

Voor het synchroniseren van uw gebruikers, groepen en contactpersonen uit de lokale Active Directory in azure Active Directory, installeert u Azure Active Directory Connect en Directory synchronisatie instellen. Zie [adreslijstsynchronisatie instellen voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) voor meer informatie.

> [!NOTE]
> De stappen zijn precies hetzelfde voor Microsoft 365 Business. 

Als u uw opties voor Azure AD Connect configureert, wordt u aangeraden **Wachtwoordsynchronisatie** en **naadloze eenmalige aanmelding**, evenals de functie **wachtwoord terugwrite back** , die ook wordt ondersteund in Microsoft 365 Business inschakelen.

> [!NOTE]
> Er zijn enkele extra stappen voor het terugzoeken van wachtwoorden buiten het selectievakje in azure AD Connect. Zie voor meer informatie, [How-to: write-back van wachtwoord configureren](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 

## <a name="3-configure-hybrid-azure-ad-join"></a>3. hybride Azure AD join configureren

Voordat u Windows 10-apparaten als hybride Azure AD gekoppeld inschakelen, moet u ervoor zorgen dat u aan de volgende vereisten voldoen:

   - U gebruikt de nieuwste versie van Azure AD Connect.

   - Azure AD Connect is gesynchroniseerd met alle computer objecten van de apparaten die u wilt worden hybride Azure AD toegevoegd. Als de computer objecten deel uitmaken van specifieke organisatie-eenheden (OE), zorg ervoor dat deze organisatie-eenheid zijn ingesteld voor synchronisatie in azure AD Connect ook.

Als u wilt registreren bestaande domein Windows 10-apparaten als hybride Azure AD join, volg de stappen in de [Zelfstudie: hybride Azure Active Directory join configureren voor beheerde domeinen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Dit hybride-inschakelen van uw bestaande on-premises Active Directory is gekoppeld aan Windows 10-computers en maken ze klaar voor de Cloud.
    
## <a name="4-enable-automatic-enrollment-for-windows-10"></a>4. automatische inschrijving voor Windows 10 inschakelen

 Zie voor het automatisch inschrijven van Windows 10-apparaten voor Mobile Device Management in intune [inschrijven een Windows 10-apparaat automatisch met behulp van Groepsbeleid](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). U het Groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen, u deze instelling voor Groepsbeleid op uw domein controller met behulp van de Group Policy Management Console en ADMX-sjablonen maken.

## <a name="5-configure-seamless-single-sign-on"></a>5. Configureer naadloze eenmalige aanmelding

  Naadloze eenmalige aanmelding zal gebruikers automatisch aanmelden bij hun Microsoft 365 cloud-resources wanneer ze bedrijfscomputers gebruiken. Implementeer eenvoudig een van de twee groeps beleidsopties die worden beschreven in [Azure Active Directory naadloze eenmalige aanmelding: Quick Start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Met de optie **Groepsbeleid** kunnen gebruikers hun instellingen niet wijzigen, terwijl de **voorkeursoptie Groepsbeleid** de waarden instelt, maar ook door de gebruiker kan worden geconfigureerd.

## <a name="6-set-up-windows-hello-for-business"></a>6. Windows hello voor bedrijven instellen

 Windows hello voor bedrijven vervangt wachtwoorden met sterke tweeledige verificatie (2FA) voor aanmelding bij een lokale computer. Een factor is een asymmetrisch sleutelpaar, en de andere is een pincode of ander lokaal gebaar zoals vingerafdruk-of gezichtsherkenning als uw apparaat dit ondersteunt. We raden u aan om wachtwoorden te vervangen door 2FA en Windows hello voor bedrijven, waar mogelijk.

Voor het configureren van hybride Windows hello voor bedrijven, controleert u de [hybride sleutel vertrouwen Windows hello voor zakelijke vereisten](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Volg de instructies in [configureren hybride Windows hello voor bedrijven sleutel vertrouwensinstellingen](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
