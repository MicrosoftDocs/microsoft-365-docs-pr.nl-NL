---
title: Domeingebruikers synchroniseren met Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
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
- MOE150
description: Synchroniseer domein beheerde gebruikers met Microsoft 365 voor bedrijven.
ms.openlocfilehash: 9495d893eb6870ef7c417a78f921296bfc0e6705
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306444"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Domeingebruikers synchroniseren met Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. voorbereiden op adreslijstsynchronisatie 

Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, raadpleegt [u voorbereidingen voor adreslijstsynchronisatie met Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization). Met name:

   - Zorg ervoor dat er geen dubbele waarden in de adreslijst voorkomen voor de volgende kenmerken: **mail**, **proxyAddresses**en **userPrincipalName**. Deze waarden moeten uniek zijn en alle duplicaten moeten worden verwijderd.
   
   - We raden u aan het kenmerk **userPrincipalName** (UPN) te configureren voor elk lokaal gebruikersaccount dat overeenkomt met het primaire e-mailadres dat overeenkomt met de gelicentieerde microsoft 365-gebruiker. Bijvoorbeeld: *Mary.Shelley@contoso.com* in plaats van *Mary@contoso. lokaal*
   
   - Als het Active Directory-domein eindigt op een niet-routeerbaar achtervoegsel zoals *. lokaal* of *. LAN*, in plaats van een routeerbaar achtervoegsel voor Internet, zoals *. com* of *. org*, past u eerst het UPN-achtervoegsel van de lokale gebruikersaccounts aan zoals wordt beschreven in [een niet-routeerbaar domein voorbereiden op adreslijstsynchronisatie](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

Met de **IdFix run** in stap 4, eronder, wordt ook gecontroleerd of uw on-premises Active Directory gereed is voor synchronisatie van dir.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect installeren en configureren

Als u uw gebruikers, groepen en contactpersonen wilt synchroniseren van de lokale Active Directory naar Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in. 

 1. Selecteer in het Beheercentrum in <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> het linkernavigatievenster de optie **instellingen** in de navigatiebalk aan de linkerkant.

 2. Kies onder **Aanmelden en beveiliging**de optie **weergeven**  onder **gebruikers synchroniseren vanuit de adreslijst van uw organisatie**.

 3. Kies op de pagina **gebruikers synchroniseren vanaf de adreslijst van uw organisatie** de optie **aan de slag**.

 4. Voer in het IdFix-hulpprogramma First Step run voor de voorbereiding voor Directory-synchronisatie.

 5. Voer de stappen van de wizard uit om Azure AD Connect te downloaden en te gebruiken voor het synchroniseren van uw door domein beheerde gebruikers voor Microsoft 365.


Zie [adreslijstsynchronisatie voor Microsoft 365 instellen](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) voor meer informatie.

Als u de opties voor Azure AD Connect configureert, is het raadzaam om **Wachtwoordsynchronisatie**, **naadloze eenmalige aanmelding**en de functie voor het **terugschrijven van wachtwoorden** in te schakelen die ook wordt ondersteund in Microsoft 365 voor bedrijven.

> [!NOTE]
> U moet extra stappen uitvoeren voor het terugschrijven van wachtwoorden buiten het selectievakje in azure AD Connect. Zie [procedure: Omschrijf van wachtwoord configureren](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie. 

Als u Windows 10-apparaten die aan het domein zijn toegevoegd ook wilt beheren, raadpleegt u het artikel toevoegen [aan Windows 10-apparaten inschakelen voor beheer door Microsoft 365 Business Premium](manage-windows-devices.md) voor het instellen van een hybride functie voor Azure AD. 