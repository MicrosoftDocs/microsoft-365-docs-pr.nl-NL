---
title: Wachtwoorden voor Microsoft 365-gebruikersaccounts beheren
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
description: Meer informatie over het beheren van wachtwoorden voor Microsoft 365-gebruikersaccounts.
ms.openlocfilehash: af64002ad54b517a6e8f0b687a00d6bed9ab0214
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328493"
---
# <a name="manage-microsoft-365-user-account-passwords"></a>Wachtwoorden voor Microsoft 365-gebruikersaccounts beheren

*Dit artikel is van toepassing op Microsoft 365 Enterprise en Office 365 Enterprise.*

U kunt wachtwoorden van gebruikersaccounts van Microsoft 365 op verschillende manieren beheren, afhankelijk van de configuratie van uw identiteit. U kunt gebruikersaccounts beheren in het [Microsoft 365-Beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/), in Active Directory Domain Services (AD DS) of in het Azure Active Directory (Azure AD)-Beheercentrum.

## <a name="plan-for-where-and-how-you-will-manage-your-user-account-passwords"></a>Plannen waar en hoe u uw wachtwoorden voor uw gebruikersaccount beheert

Waar en hoe u uw gebruikersaccounts kunt beheren, is afhankelijk van het identiteits model dat u wilt gebruiken voor uw Microsoft 365. De twee modellen zijn alleen voor de Cloud en hybride.
  
### <a name="cloud-only"></a>Alleen in de cloud

U beheert wachtwoorden van gebruikersaccounts in:

- [Het Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/add-users/)
- Het Azure AD-Beheercentrum
    
### <a name="hybrid"></a>Hybride

Met de Hybrid Identity worden wachtwoorden opgeslagen in AD DS, zodat u on-premises hulpmiddelen voor AD DS moet gebruiken voor het beheren van wachtwoorden van gebruikersaccounts. Ook als u hash-synchronisatie (PHS) gebruikt waarin in azure AD een hash-versie van de al hashed-versie is opgeslagen in AD DS, moeten u en gebruikers hun wachtwoord beheren in AD DS.

Met het [terugschrijven van wachtwoorden](#pw_writeback)kunnen gebruikers hun AD DS-wachtwoorden via Azure AD wijzigen.

## <a name="prevent-bad-passwords"></a>Slechte wachtwoorden voorkomen

Al uw gebruikers dienen de [Wachtwoordondersteuning van Microsoft](https://www.microsoft.com/research/publication/password-guidance) te gebruiken om de wachtwoorden voor hun gebruikersaccounts te maken.

Als u wilt voorkomen dat gebruikers een te makkelijk wachtwoord aanmaken, gebruikt u Azure AD-wachtwoordbeveiliging. Hierbij wordt gebruikgemaakt van een wereldwijd geblokkeerde wachtwoordlijst en een optionele, aangepaste lijst met geblokkeerde wachtwoorden die u kunt vaststellen. U kunt bijvoorbeeld termen op deze lijst zetten die specifiek voor uw organisatie zijn, zoals:

- Merknamen
- Productnamen
- Locaties (zoals bijvoorbeeld het hoofdkantoor van het bedrijf)
- Bedrijfsspecifieke interne termen
- Afkortingen met een specifieke betekenis binnen het bedrijf

U kunt beschadigde wachtwoorden [in de Cloud](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) en voor uw [on-PREMISes AD DS](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)blokkeren.

## <a name="simplify-user-sign-in"></a>Gebruikersaanmelding vereenvoudigen

Probleemloos eenmalige aanmelding met Azure AD (Azure AD naadloos SSO) werkt met PHS en Pass-Through-verificatie (PTA), zodat gebruikers zich kunnen aanmelden bij services die gebruikmaken van Azure AD-gebruikersaccounts zonder dat ze hun wachtwoorden moeten typen, en in veel gevallen, zijn hun gebruikersnamen. Dit geeft uw gebruikers eenvoudiger toegang tot toepassingen in de cloud, zoals Office 365, zonder extra onderdelen op locatie nodig te hebben, zoals identiteitsfederatie-servers.

U configureert naadloze eenmalige aanmelding via Azure AD met het hulpprogramma Azure AD Connect. Zie [instructies voor het configureren naadloze eenmalige aanmelding via Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start).

<a name="pw_writeback"></a>
## <a name="simplify-password-updates-to-ad-ds"></a>Wachtwoord updates vereenvoudigen voor AD DS

Met wachtwoord terugschrijven kunt u toestaan dat gebruikers hun wachtwoord opnieuw kunnen instellen via Azure AD, dat vervolgens wordt gerepliceerd naar AD DS. Gebruikers hoeven geen toegang te krijgen tot hun on-premises AD DS om hun wachtwoord bij te werken. Dit is handig bij roaming en gebruikers die extern werken die geen RAS-verbinding met het on-premises netwerk hebben.

Wachtwoord terugschrijven is vereist om volledig gebruik te kunnen maken van de mogelijkheden van Identity Protection-functies, zoals vereisen dat gebruikers hun on-premises wachtwoorden wijzigen wanneer er een hoog risico op inbreuk van accounts is gedetecteerd.

Zie [Azure AD SSPR met wachtwoord terugschrijven](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback) voor meer informatie en configuratie-instructies.

>[!Note]
>Voer een upgrade uit naar de nieuwste versie van Azure AD Connect om te zorgen voor een optimale ervaring en nieuwe functies zodra deze beschikbaar komen. Zie [Aangepaste installatie van Azure AD Connect](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom) voor meer informatie.
>

## <a name="simplify-password-resets"></a>Het opnieuw instellen van wachtwoorden vereenvoudigen

Met selfservice voor wachtwoordherstel (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen. Als u wilt worden gewaarschuwd voor misbruik, kunt u gebruikmaken van gedetailleerde rapporten die bijhouden en meldingen geven wanneer gebruikers het systeem openen. U moet [wachtwoord terugschrijven](#pw_writeback) inschakelen voordat u het opnieuw instellen van wachtwoorden kunt implementeren.

Zie de [instructies voor het invoeren van wachtwoordherstel](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment).

