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
description: Synchroniseer domeingestuurde gebruikers met Microsoft 365 voor bedrijven.
ms.openlocfilehash: af9cb7c9b2b639edc2375679a73ab41c4cf6de71
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45080057"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>Domeingebruikers synchroniseren met Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. Voorbereiden op directorysynchronisatie 

Voordat u uw gebruikers en computers synchroniseert vanuit het lokale Active Directory-domein, controleert [u Voorbereiden op adreslijstsynchronisatie naar Microsoft 365](https://docs.microsoft.com/office365/enterprise/prepare-for-directory-synchronization). In het bijzonder:

   - Zorg ervoor dat er geen duplicaten in uw map bestaan voor de volgende kenmerken: **e-mail,** **proxyAdressen**en **userPrincipalName**. Deze waarden moeten uniek zijn en eventuele duplicaten moeten worden verwijderd.
   
   - We raden u aan het kenmerk **USERPrincipalName** (UPN) voor elk lokaal gebruikersaccount te configureren op basis van het primaire e-mailadres dat overeenkomt met de gelicentieerde Microsoft 365-gebruiker. Bijvoorbeeld: *mary.shelley@contoso.com* in plaats van *mary@contoso.local*
   
   - Als het Active Directory-domein eindigt in een niet-routeerbaar achtervoegsel zoals *.local* of *.lan*, in plaats van een internetroertable achtervoegsel zoals *.com* of *.org,* past u eerst het UPN-achtervoegsel van het lokale gebruikersaccounts aan zoals beschreven in [Een niet-routeerbaar domein voorbereiden voor adreslijstsynchronisatie](https://docs.microsoft.com/office365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization). 

De **Run IdFix** in stap vier (4) hieronder, zorgt er ook voor dat uw on-premises Active Directory klaar is voor dir-synchronisatie.

## <a name="2-install-and-configure-azure-ad-connect"></a>2. Azure AD Connect installeren en configureren

Als u uw gebruikers, groepen en contactpersonen uit de lokale Active Directory wilt synchroniseren met Azure Active Directory, installeert u Azure Active Directory Connect en stelt u adreslijstsynchronisatie in. 

 1. In het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> de optie **Setup** in het linkernavigatiesysteem.

 2. Kies Onder **Aanmelden en beveiliging**de optie **Weergave** onder Gebruikers synchroniseren in de map van **uw organisatie.**

 3. Kies op de **pagina Gebruikers synchroniseren vanaf de map van uw organisatie** de optie Aan de **slag**.

 4. Voer in de eerste stap idfix-gereedschap uit om u voor te bereiden op Directory-synchronisatie.

 5. Volg de wizardstappen om Azure AD Connect te downloaden en deze te gebruiken om uw domeingestuurde gebruikers te synchroniseren met Microsoft 365.


Zie [Mapsynchronisatie instellen voor Microsoft 365](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization) voor meer informatie.

Terwijl u uw opties voor Azure AD Connect configureert, raden we u aan **wachtwoordsynchronisatie,** **naadloze aanmelding met één aanmelding**en de functie voor het **terugschrijven van wachtwoorden** in te schakelen, die ook wordt ondersteund in Microsoft 365 voor bedrijven.

> [!NOTE]
> Er zijn enkele extra stappen voor het terugschrijven van wachtwoorden buiten het selectievakje in Azure AD Connect. Zie Hoe voor meer [informatie: wachtwoordschrijftijd configureren.](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback) 

Als u ook windows 10-apparaten met domein wilt beheren, [raadpleegt u Windows 10-apparaten inschakelen die door Microsoft 365 Business Premium moeten worden beheerd](manage-windows-devices.md) om een hybride Azure AD Join-join in te stellen. 