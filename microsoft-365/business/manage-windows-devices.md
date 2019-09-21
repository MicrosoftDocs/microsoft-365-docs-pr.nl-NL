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
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: Informatie over het inschakelen van Microsoft 365 voor het beveiligen van lokale AD gekoppelde Windows 10-apparaten.
ms.openlocfilehash: 9bfd540c0ff113762485f62707f1975ff53accc4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/20/2019
ms.locfileid: "37068100"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>Toestaan dat aan een domein toegevoegde Windows 10-apparaten door Microsoft 365 Business worden beheerd

Als uw organisatie gebruikmaakt van on-premises Windows Server Active Directory, u Microsoft 365 Business instellen om uw Windows 10-apparaten te beveiligen, terwijl u nog steeds toegang hebt tot on-premises bronnen waarvoor lokale verificatie is vereist. U dit instellen door eerst uw Active Directory synchroniseren met Azure Active Directory, gevolgd door het registreren van de Windows 10-apparaten met Azure AD en ze inschrijven voor Mobile Device Management door Microsoft 365 Business.
De volgende Videodetails de stappen voor het instellen van dit voor de meest voorkomende scenario.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>Domein apparaten instellen die moeten worden beheerd door Microsoft 365 Business

Als u wilt instellen van uw organisatie domein apparaten om te profiteren van de mogelijkheden die worden geleverd door Azure Active Directory naast on-premises Active Directory, u **hybride Azure AD gekoppelde apparaten**implementeren. Dit zijn apparaten die zijn gekoppeld aan uw on-premises Active Directory en uw Azure Active Directory. Hybride Azure AD gekoppelde apparaten kunnen worden beveiligd en beheerd door Microsoft 365 Business. 
  
Voltooi de onderstaande stappen om uw Windows 10-apparaten hybride Azure AD toegevoegd en beheerd door Microsoft 365 Business.
  
1. **Voorbereiden voor adreslijstsynchronisatie**: voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert u de [voorbereidingen voor adreslijstsynchronisatie naar Office 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In het bijzonder:

   - Zorg ervoor dat er geen duplicaten in uw Directory voor de volgende kenmerken zijn: **mail**, **proxyAddresses**, en **userPrincipalName**. Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd..
   
   - We raden aan dat het kenmerk **userPrincipalName** (UPN) voor elke lokale gebruikersaccount is geconfigureerd zodat deze overeenkomt met het primaire e-mailadres dat overeenkomt met de gelicentieerde microsoft 365-gebruiker. Bijvoorbeeld **Mary.Shelley@contoso.com** in plaats van **Mary @ contoso. local**
   
   - Als het Active Directory-domein wordt beëindigd in een niet-routeerbaar achtervoegsel zoals **. local** of **. LAN**, in plaats van een Internet routeerbaar achtervoegsel zoals **. com** of **. org**, moet u het UPN-achtervoegsel van de lokale gebruikersaccounts eerst aanpassen, zoals wordt beschreven in [Een niet-routeerbaar domein voorbereiden voor adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

2. **Installeren en configureren van Azure AD Connect**: als u wilt synchroniseren van uw gebruikers, groepen en contactpersonen van de lokale Active Directory in azure Active Directory, voert u de wizard Directory-synchronisatie van Azure Active Directory verbinding maken. Zie [adreslijstsynchronisatie instellen voor Office 365](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846) voor meer informatie.
    
    > [!NOTE]
    > De stappen zijn precies hetzelfde voor Microsoft 365 Business. 
    
Als u uw opties voor Azure AD Connect configureert, wordt u aangeraden **Wachtwoordsynchronisatie** en **naadloze eenmalige aanmelding**, evenals de functie **wachtwoord terugwrite back** , die ook wordt ondersteund in Microsoft 365 Business inschakelen.

> [!NOTE]
> Er zijn enkele extra stappen voor het terugzoeken van wachtwoorden buiten het selectievakje in azure AD Connect. Raadpleeg [How-to: wachtwoord terugschrijven configureren](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). 
     
3. **Hybride Azure AD join configureren**: voordat u Windows 10-apparaten als hybride Azure AD gekoppeld inschakelen, moet u ervoor zorgen dat u aan de volgende vereisten voldoen:

   - U gebruikt de nieuwste versie van Azure AD Connect.

   - Azure AD Connect is gesynchroniseerd met alle computer objecten van de apparaten die u wilt worden hybride Azure AD toegevoegd. Als de computer objecten deel uitmaken van specifieke organisatie-eenheden (OE), zorg ervoor dat deze organisatie-eenheid zijn ingesteld voor synchronisatie in azure AD Connect ook.

Als u wilt registreren bestaande domein Windows 10-apparaten als hybride Azure AD join, volg de stappen in de [Zelfstudie: hybride Azure Active Directory join configureren voor beheerde domeinen](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). Dit hybride-inschakelen van uw bestaande on-premises Active Directory is gekoppeld aan Windows 10-computers en maken ze klaar voor de Cloud.
    
4. **Automatische inschrijving voor Windows 10 inschakelen**: als u Windows 10-apparaten automatisch wilt inschrijven voor Mobile Device Management in intune, raadpleegt u [automatisch een Windows 10-apparaat inschrijven met Groepsbeleid](https://docs.microsoft.com/windows/client-management/mdm/enroll-a-windows-10-device-automatically-using-group-policy). U het Groepsbeleid instellen op lokaal computerniveau of voor bulkbewerkingen, u deze instelling voor Groepsbeleid op uw domein controller met behulp van de Group Policy Management Console en ADMX-sjablonen maken.

5. **Naadloze eenmalige aanmelding configureren**: naadloze eenmalige aanmelding wordt automatisch gebruikers aanmelden bij hun microsoft 365 cloud-resources wanneer ze bedrijfscomputers gebruiken. Implementeer eenvoudig een van de twee groeps beleidsopties die worden beschreven in [Azure Active Directory naadloze eenmalige aanmelding: Quick Start](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso-quick-start#step-2-enable-the-feature). Met de optie **Groepsbeleid** kunnen gebruikers hun instellingen niet wijzigen, terwijl de **voorkeursoptie Groepsbeleid** de waarden instelt, maar ook door de gebruiker kan worden geconfigureerd.

6. **Windows hello voor bedrijven instellen**: Windows hello voor bedrijven vervangt wachtwoorden met sterke tweeledige verificatie (2fa) voor aanmelding bij een lokale computer. Een factor is een asymmetrisch sleutelpaar, en de andere is een pincode of ander lokaal gebaar zoals vingerafdruk-of gezichtsherkenning als uw apparaat dit ondersteunt. We raden u aan om wachtwoorden te vervangen door 2FA en Windows hello voor bedrijven, waar mogelijk.

Voor het configureren van hybride Windows hello voor bedrijven, controleert u de [hybride sleutel vertrouwen Windows hello voor zakelijke vereisten](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-trust-prereqs). Volg de instructies voor het [configureren van hybride Windows hello voor Business Key Trust instellingen](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-hybrid-key-whfb-settings). 
