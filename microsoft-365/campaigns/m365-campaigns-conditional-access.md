---
title: Beleidsregels voor voorwaardelijke toegang instellen
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
description: Meer informatie over hoe u MFA moet vereisen en regels voor voorwaardelijke toegang voor Microsoft 365 voor bedrijven kunt instellen.
ms.openlocfilehash: 5908a36f09753cd8f66169c6a67be45c748807b7
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071499"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Meervoudige verificatie vereisen en beleid voor voorwaardelijke toegang instellen

U kunt toegang tot uw gegevens beschermen met multi-factor Authentication en voorwaardelijk toegangsbeleid. Deze toevoegen substantiële extra beveiligings. Microsoft biedt een set beleidsregels voor voorwaardelijke toegang die worden aanbevolen voor alle klanten. Basisregels voor basisregels zijn een set vooraf gedefinieerde beleidsregels waarmee organisaties worden beschermd tegen veel voorkomende aanvallen. Deze veelvoorkomende aanvallen kunnen met een wachtwoord, herhaling en phishing behoren.

Voor deze beleidsregels moeten beheerders en gebruikers een tweede vorm van verificatie (zogenaamde meervoudige verificatie of MFA) invoeren wanneer aan bepaalde voorwaarden wordt voldaan. Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of een onbekend apparaat, kan de aanmelding als risico worden beschouwd. De gebruiker moet een extra vorm van verificatie geven (zoals een vingerafdruk of een code) om de identiteit ervan te bewijzen. 

Op dit moment bevat het basislijnbeleid het volgende:
- Instellen in het Microsoft 365-Beheercentrum:
    - **MFA vereisen voor beheerders** : hiervoor is meervoudige verificatie vereist voor de meest beheerdersrollen, waaronder de globale beheerder.
    - **Beveiliging van eindgebruikers** : vereist multi-factor Authentication voor gebruikers alleen wanneer een aanmelding is riskant. 
- Instellen in azure Active Directory portal:
    - **Verouderde verificatie blokkeren** : oudere clienttoepassingen en bepaalde nieuwe apps gebruiken geen nieuwere, veiliger, authenticatie protocollen. Met deze oudere apps kunt u beleidsregels voor voorwaardelijke toegang negeren en onbevoegd toegang krijgen tot uw omgeving. Dit beleid blokkeert de toegang vanaf clients die geen voorwaardelijke toegang ondersteunen. 
    - **MFA vereisen voor Service beheer** : hiervoor is meervoudige verificatie vereist voor de toegang tot beheerprogramma's, waaronder Azure Portal (waar u beleidsregels voor basisregels configureert). 

Microsoft raadt u aan al deze basisregels voor basisregels in te schakelen. Nadat dit beleid is ingeschakeld, wordt beheerders en gebruikers gevraagd zich aan te melden voor Azure multi-factor Authentication.

Zie [Wat zijn basisregels voor basisregels](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)? voor meer informatie over deze beleidsregels.


## <a name="require-mfa"></a>MFA vereisen

Vereisen dat alle gebruikers zich aanmelden met een tweede vorm van ID:

1. Ga naar het Beheercentrum op <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Setup**.

2. Kies op de pagina instellingen de optie **weergeven** in de **beveiligde kaart aanmelden** .


    ![Meld u veilig een beveiligde kaart.](../media/setupmfa.png)
3. Kies op de pagina aanmelden veilig maken de optie aan de **slag**.
 
4. Schakel in het deelvenster aanmeldingsbeveiliging versterken de selectievakjes in naast **Meervoudige verificatie vereisen voor beheerders** en **gebruikers moeten registreren voor meervoudige verificatie en toegang blokkeren indien risico wordt gedetecteerd**.
    Zorg ervoor dat u het beheerdersaccount voor [noodgevallen](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) of een afbreek glas sluit van de MFA-vereiste in het vak **gebruikers zoeken** .
    
    ![De pagina met ingebouwde beveiligingspagina's versterken.](../media/requiremfa.png)

5. Kies **beleid maken** onder aan de pagina.

## <a name="set-up-baseline-policies"></a>Basis voor basisregels instellen

1. Ga naar de [Azure-Portal](https://portal.azure.com)en ga naar **Azure Active Directory** \> **voorwaardelijke toegang** om een **Nieuw beleid** te maken.

Zie de volgende specifieke instructies voor elk beleid: <br>
    - [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [MFA vereisen voor gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [MFA vereisen voor servicebeheer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)
    
> [!NOTE]
> Beleidsregels voor het voorbeeld bestaan niet meer en gebruikers moeten hun eigen beleid maken.


U kunt extra beleidsregels instellen, zoals goedgekeurde clienttoepassingen vereisen. Zie de [documentatie voor voorwaardelijke toegang](https://docs.microsoft.com/azure/active-directory/conditional-access/)voor meer informatie.
