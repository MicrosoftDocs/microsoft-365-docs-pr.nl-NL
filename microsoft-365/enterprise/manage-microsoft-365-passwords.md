---
title: Wachtwoorden voor gebruikersaccounts van Microsoft 365 beheren
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Meer informatie over het beheren van wachtwoorden voor gebruikersaccounts van Microsoft 365.
ms.openlocfilehash: 2062da49310121ec18f7ce21f523531f10d6df9b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905090"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Wachtwoorden voor gebruikersaccounts van Microsoft 365 beheren

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt wachtwoorden voor gebruikersaccounts van Microsoft 365 op verschillende manieren beheren, afhankelijk van uw identiteitsconfiguratie. U kunt gebruikersaccounts beheren in het [Microsoft 365-beheercentrum](../admin/add-users/index.yml), in Ad DS (Active Directory Domain Services) of in het Azure Active Directory-beheercentrum (Azure AD).

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Plannen voor waar en hoe u wachtwoorden voor uw gebruikersaccount gaat beheren

Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteitsmodel dat u wilt gebruiken voor uw Microsoft 365. De twee modellen zijn alleen-in de cloud en hybride.
  
### <a name="cloud-only"></a>Alleen in de cloud

U beheert wachtwoorden voor gebruikersaccounts in:

- [Het Microsoft 365-beheercentrum](../admin/add-users/index.yml)
- Het Azure AD-beheercentrum
    
### <a name="hybrid"></a>Hybride

Bij hybride identiteit worden wachtwoorden opgeslagen in AD DS, dus u moet on-premises AD DS-hulpprogramma's gebruiken om wachtwoorden voor gebruikersaccounts te beheren. Zelfs wanneer u Wachtwoordhashsynchronisatie (PHS) gebruikt, waarin In Azure AD een gehashte versie van de al gehashte versie in AD DS wordt opgeslagen, moeten u en gebruikers hun wachtwoorden beheren in AD DS.

Met [wachtwoordschrijven kunnen](#pw_writeback)uw gebruikers hun AD DS-wachtwoorden wijzigen via Azure AD.

## <a name="prevent-bad-passwords"></a>Slechte wachtwoorden voorkomen

Al uw gebruikers dienen de [Wachtwoordondersteuning van Microsoft](https://www.microsoft.com/research/publication/password-guidance) te gebruiken om de wachtwoorden voor hun gebruikersaccounts te maken.

Als u wilt voorkomen dat gebruikers een te makkelijk wachtwoord aanmaken, gebruikt u Azure AD-wachtwoordbeveiliging. Hierbij wordt gebruikgemaakt van een wereldwijd geblokkeerde wachtwoordlijst en een optionele, aangepaste lijst met geblokkeerde wachtwoorden die u kunt vaststellen. U kunt bijvoorbeeld termen op deze lijst zetten die specifiek voor uw organisatie zijn, zoals:

- Merknamen
- Productnamen
- Locaties (zoals bijvoorbeeld het hoofdkantoor van het bedrijf)
- Bedrijfsspecifieke interne termen
- Afkortingen met een specifieke betekenis binnen het bedrijf

U kunt slechte wachtwoorden [in de cloud en](/azure/active-directory/authentication/concept-password-ban-bad) voor uw [on-premises AD DS verbieden.](/azure/active-directory/authentication/concept-password-ban-bad-on-premises)

## <a name="simplify-user-sign-in"></a>Gebruikersaanmelding vereenvoudigen

Azure AD Seamless Single Sign-On (Azure AD Seamless SSO) werkt met PHS en Pass-Through Authentication (PTA), zodat uw gebruikers zich kunnen aanmelden bij services die Azure AD-gebruikersaccounts gebruiken zonder hun wachtwoorden en in veel gevallen hun gebruikersnaam in te typen. Dit geeft uw gebruikers eenvoudiger toegang tot toepassingen in de cloud, zoals Office 365, zonder extra onderdelen op locatie nodig te hebben, zoals identiteitsfederatie-servers.

U configureert naadloze eenmalige aanmelding via Azure AD met het hulpprogramma Azure AD Connect. Zie [instructies voor het configureren naadloze eenmalige aanmelding via Azure AD](/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Wachtwoordupdates voor AD DS vereenvoudigen

Met wachtwoordschrijven kunt u toestaan dat gebruikers hun wachtwoorden opnieuw instellen via Azure AD, dat vervolgens wordt gerepliceerd naar AD DS. Gebruikers hoeven hun on-premises AD DS niet te openen om hun wachtwoorden bij te werken. Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.

Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.

Zie [Azure AD SSPR met wachtwoord terugschrijven](/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.

>[!Note]
>Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen. Zie [Aangepaste installatie van Azure AD Connect](/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.
>

## <a name="simplify-password-resets"></a>Het opnieuw instellen van wachtwoorden vereenvoudigen

Met SelfService Password Reset (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen. Als u wilt worden gewaarschuwd voor misbruik, kunt u gebruikmaken van gedetailleerde rapporten die bijhouden en meldingen geven wanneer gebruikers het systeem openen. U moet [wachtwoordschrijven inschakelen voordat](#pw_writeback) u wachtwoordinstellingen kunt implementeren.

Zie de [instructies voor het invoeren van wachtwoordherstel](/azure/active-directory/authentication/howto-sspr-deployment).