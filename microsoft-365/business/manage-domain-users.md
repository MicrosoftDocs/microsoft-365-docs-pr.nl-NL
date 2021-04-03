---
title: Domeingebruikers synchroniseren met Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
description: Domeingestuurde gebruikers synchroniseren met Microsoft 365 voor Bedrijven.
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578402"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Domeingebruikers synchroniseren met Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Voorbereidingen treffen voor adreslijstsynchronisatie 

Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, bekijkt u Voorbereiden op [adreslijstsynchronisatie met Microsoft 365.](../enterprise/prepare-for-directory-synchronization.md) In het bijzonder:

   - Zorg ervoor dat er geen duplicaten aanwezig zijn in uw adreslijst voor de volgende kenmerken: **e-mail,** **proxyAddresses** en **userPrincipalName.** Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.
   
   - U wordt aangeraden het **kenmerk userPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren op basis van het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker. Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*
   
   - Als het Active Directory-domein eindigt op een niet-routable achtervoegsel zoals *.local* of *.lan*, in plaats van een internet routable suffix zoals *.com* of *.org*, past u eerst het UPN-achtervoegsel van de lokale gebruikersaccounts aan, zoals beschreven in Een niet-routable domain voorbereiden voor [adreslijstsynchronisatie.](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

Met **IdFix** uitvoeren in stap vier (4) hieronder, wordt er ook voor zorgen dat uw on-premises Active Directory gereed is voor adreslijstsynchronisatie.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect installeren en configureren

Als u uw gebruikers, groepen en contactpersonen vanuit de lokale Active Directory wilt synchroniseren met Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in. 

 1. Selecteer instellen in het linkernavigatienavigatiecentrum **in** het [beheercentrum.](https://go.microsoft.com/fwlink/p/?linkid=2024339)

 2. Kies **onder Aanmelden en beveiliging** de optie **Weergeven** onder Gebruikers synchroniseren vanuit **de adreslijst van uw organisatie.**

 3. Kies op de pagina Gebruikers synchroniseren op de **adreslijstpagina** van uw organisatie de optie **Aan de slag.**

 4. Voer in de eerste stap Het hulpprogramma IdFix uit om de synchronisatie van adreslijst voor te bereiden.

 5. Volg de wizardstappen om Azure AD Connect te downloaden en deze te gebruiken om uw domeingestuurde gebruikers te synchroniseren met Microsoft 365.


Zie [Adreslijstsynchronisatie instellen voor Microsoft 365](../enterprise/set-up-directory-synchronization.md) voor meer informatie.

Wanneer u uw opties configureert voor Azure AD Connect, raden we u aan  wachtwoordsynchronisatie, naadloze een-aan-/uit-tekenfunctie en de functie voor het terugschrijven van wachtwoorden in te stellen, die ook wordt ondersteund in Microsoft 365 voor Bedrijven. 

> [!NOTE]
> Er zijn enkele extra stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect. Zie [How-to: configure password writeback](/azure/active-directory/authentication/howto-sspr-writeback)voor meer informatie. 

Als u ook windows 10-apparaten met een domein wilt beheren, zie Windows [10-apparaten](manage-windows-devices.md) die zijn verbonden met een domein, door Microsoft 365 Business Premium worden beheerd om een hybride Azure AD Join in te stellen.