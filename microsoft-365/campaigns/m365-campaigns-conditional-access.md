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
description: Meer informatie over het vereisen van MFA en het instellen van beleid voor voorwaardelijke toegang voor Microsoft 365 voor Bedrijven.
ms.openlocfilehash: dcb79ed060dd15fd288cdcfb9e3739a788f5fbc2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912184"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Meervoudige verificatie vereisen en beleid voor voorwaardelijke toegang instellen

U beschermt de toegang tot uw gegevens met meervoudige verificatie en beleid voor voorwaardelijke toegang. Deze bieden aanzienlijke extra beveiliging. Microsoft biedt een set beleidsregels voor basislijn voorwaardelijke toegang die worden aanbevolen voor alle klanten. Basislijnbeleid is een set vooraf gedefinieerde beleidsregels die organisaties helpen beschermen tegen veelvoorkomende aanvallen. Deze veelvoorkomende aanvallen kunnen wachtwoordsproeien, herhalen en phishing zijn.

Voor dit beleid moeten beheerders en gebruikers onder bepaalde voorwaarden een tweede vorm van verificatie invoeren (meervoudige verificatie of MFA genoemd). Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of vanaf een onbekend apparaat, kan de aanmelding als riskant worden beschouwd. De gebruiker moet een extra vorm van verificatie (zoals een vingerafdruk of een code) verstrekken om zijn of haar identiteit te bewijzen.

Op dit moment bevat het basislijnbeleid de volgende beleidsregels:

- Instellen in microsoft 365-beheercentrum:
  - **MFA vereisen voor beheerders:** vereist meervoudige verificatie voor de meest bevoorrechte beheerdersrollen, inclusief globale beheerder.
  - **Beveiliging van eindgebruikers:** meervoudige verificatie is alleen vereist voor gebruikers wanneer een aanmelding riskant is. 
- Instellen in de Azure Active Directory-portal:
  - **Oudere verificatie blokkeren:** oudere client-apps en sommige nieuwe apps gebruiken geen nieuwere, veiligere verificatieprotocollen. Deze oudere apps kunnen beleidsregels voor voorwaardelijke toegang omzeilen en ongeautoriseerde toegang krijgen tot uw omgeving. Dit beleid blokkeert toegang van clients die geen ondersteuning bieden voor voorwaardelijke toegang. 
  - **MFA vereisen voor servicebeheer:** vereist meervoudige verificatie voor toegang tot beheerhulpmiddelen, waaronder Azure Portal (waar u basislijnbeleid configureert).

U wordt aangeraden al deze basislijnbeleidsregels in te stellen. Nadat dit beleid is ingeschakeld, worden beheerders en gebruikers gevraagd zich te registreren voor Azure AD Multifactor Authentication.

Zie Wat zijn basislijnbeleid? voor [meer informatie over dit beleid.](/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>MFA vereisen

Als u wilt dat alle gebruikers zich aanmelden met een tweede id-formulier:

1. Ga naar het beheercentrum bij <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> en kies **Setup.**

2. Kies op de pagina Setup **de optie Weergeven** in de **aanmeldingskaart veiliger** maken.

    ![Maak aanmelding veiliger.](../media/setupmfa.png)
3. Kies op de pagina Aanmelden veiliger maken de optie **Aan de slag.**

4. Schakel in het deelvenster **Aanmeldingsbeveiliging** versterken de selectievakjes in naast Meervoudige verificatie vereisen voor beheerders en Gebruikers verplichten zich te registreren voor meervoudige verificatie en toegang te blokkeren als er risico **wordt gedetecteerd.**
    Zorg ervoor dat u het beheerdersaccount [voor](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) noodgevallen of 'break-glass' uitsluit van de MFA-vereiste in **het vak Gebruikers zoeken.**

    ![De beveiligingspagina voor sing-in versterken.](../media/requiremfa.png)

5. Kies **Beleid maken** onder aan de pagina.

## <a name="set-up-baseline-policies"></a>Basislijnbeleid instellen

1. Ga naar de [Azure-portal](https://portal.azure.com)en ga vervolgens naar **voorwaardelijke toegang** voor Azure Active \> **Directory-beveiliging** \>  om een nieuw beleid **te maken.**

Zie de volgende specifieke instructies voor elk beleid: <br>
    - [MFA vereisen voor beheerders](/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [MFA vereisen voor gebruikers](/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Verouderde verificatie blokkeren](/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [MFA vereisen voor servicebeheer](/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Voorbeeldbeleid bestaat niet meer en gebruikers moeten hun eigen beleid maken.

U kunt extra beleid instellen, zoals het vereisen van goedgekeurde client-apps. Zie de documentatie voor Voorwaardelijke toegang voor [meer informatie.](/azure/active-directory/conditional-access/)