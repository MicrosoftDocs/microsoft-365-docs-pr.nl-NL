---
title: Beleid voor voorwaardelijke toegang instellen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: Meer informatie over het vereisen van MFA en het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365 voor bedrijven.
ms.openlocfilehash: 917fb52eb5034c3dda28c277b9e86e04db6cac62
ms.sourcegitcommit: 6501e01a9ab131205a3eef910e6cea7f65b3f010
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/30/2020
ms.locfileid: "46527196"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Multi-factor authenticatie vereisen en beleid voor voorwaardelijke toegang instellen

U beschermt de toegang tot uw gegevens met meervoudige verificatie en beleid voor voorwaardelijke toegang. Deze voegen aanzienlijke extra beveiliging toe. Microsoft biedt een set basislijnvoorwaarden voor voorwaardelijke toegang die voor alle klanten worden aanbevolen. Basislijnbeleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veel voorkomende aanvallen. Deze veelvoorkomende aanvallen kunnen wachtwoordspray, herhaling en phishing omvatten.

Dit beleid vereist dat beheerders en gebruikers een tweede vorm van verificatie invoeren (multi-factor authenticatie of MFA genoemd) wanneer aan bepaalde voorwaarden is voldaan. Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of vanaf een onbekend apparaat, kan de aanmelding als riskant worden beschouwd. De gebruiker moet een extra vorm van authenticatie (zoals een vingerafdruk of een code) om hun identiteit te bewijzen. 

Momenteel omvatten basislijnbeleid het volgende:
- Instellen in microsoft 365-beheercentrum:
    - **MFA vereisen voor beheerders** : vereist meervoudige verificatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.
    - **Beveiliging van eindgebruikers** : vereist meervoudige verificatie voor gebruikers alleen wanneer een aanmelding riskant is. 
- Instellen in Azure Active Directory-portal:
    - **Verouderde verificatie blokkeren** - Oudere client-apps en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen. Deze oudere apps kunnen het beleid voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang tot uw omgeving krijgen. Dit beleid blokkeert de toegang van clients die geen voorwaardelijke toegang ondersteunen. 
    - **MFA vereisen voor servicebeheer** : vereist meervoudige verificatie voor toegang tot beheerhulpprogramma's, waaronder Azure-portal (waar u basislijnbeleid configureert). 

Microsoft raadt u aan al deze basislijnbeleid in te schakelen. Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure Multi-Factor-verificatie.

Zie [Wat zijn basislijnbeleid voor](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)meer informatie over dit beleid?


## <a name="require-mfa"></a>MFA vereisen

Als u wilt dat alle gebruikers zich aanmelden met een tweede formulier id:

1. Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Setup**.

2. Kies op de pagina Setup de optie **Weergave** in de **aanmeldingskaart Maken.**


    ![Maak aanmelden veiliger kaart.](../media/setupmfa.png)
3. Kies op de pagina Aanmelden veiliger maken de optie **Aan de slag**.
 
4. Schakel in het beveiligingsvenster Aanmelding versterken de selectievakjes naast **Meervoudige verificatie vereisen voor beheerders** in en gebruikers **verplichten zich te registreren voor meervoudige verificatie en toegang te blokkeren als er risico's worden gedetecteerd.**
    Zorg ervoor dat u het [nood-](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) of "break-glass"-beheerdersaccount uitsluit van de MFA-eis in het vak **Gebruikers zoeken.**
    
    ![Versterking van de beveiligingspagina voor zingen.](../media/requiremfa.png)

5. Kies **Beleid maken** onder aan de pagina.

## <a name="set-up-baseline-policies"></a>Basislijnbeleid instellen

1. Ga naar [Azure-portal](https://portal.azure.com)en navigeer naar **Azure Active Directory** Voorwaardelijke \> **toegang**.
    
    Het basislijnbeleid wordt op de pagina weergegeven en u zien dat **MFA vereisen voor beheerders** en beveiliging van **eindgebruikers** al zijn ingeschakeld nadat u de stappen hebt voltooid [waarin MFA vereist](#require-mfa)is.

    ![Pagina met basislijnbeleid voor voorwaardelijke toegang.](../media/casettings.png)
2. Zie de volgende specifieke instructies voor elk beleid:

    - [MFA nodig voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators)
    - [MFA vereisen voor gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users)  
    - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth)
    - [MFA vereisen voor servicebeheer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

U extra beleidsregels instellen, zoals het vereisen van goedgekeurde client-apps. Zie de documentatie [voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie .
