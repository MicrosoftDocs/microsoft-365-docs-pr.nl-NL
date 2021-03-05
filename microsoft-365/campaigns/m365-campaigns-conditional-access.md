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
description: Informatie over het verplicht stellen van MFA en het instellen van beleidsregels voor voorwaardelijke toegang voor Microsoft 365 voor Bedrijven.
ms.openlocfilehash: e16b7f4ff7d215ee749435806be214a807cc60a4
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453667"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>Meervoudige verificatie vereisen en beleidsregels voor voorwaardelijke toegang instellen

U bebeveiligen de toegang tot uw gegevens met meervoudige verificatie en beleidsregels voor voorwaardelijke toegang. Deze leveren aanzienlijke extra beveiliging op. Microsoft biedt een reeks beleidsregels voor voorwaardelijke toegang volgens de basislijn die voor alle klanten worden aanbevolen. Basislijnbeleid is een reeks vooraf gedefinieerd beleidsregels die organisaties helpen beschermen tegen veel algemene aanvallen. Deze algemene aanvallen kunnen wachtwoordaanvallen, herhaling en phishing zijn.

Voor dit beleid moeten beheerders en gebruikers onder bepaalde voorwaarden een tweede vorm van verificatie (meervoudige verificatie of MFA) invoeren. Als een gebruiker in uw organisatie zich bijvoorbeeld probeert aan te melden bij Microsoft 365 vanuit een ander land of een onbekend apparaat, kan het aanmelden als riskant worden beschouwd. De gebruiker moet een extra vorm van verificatie bieden (zoals een vingerafdruk of een code) om zijn of haar identiteit te bewijzen.

Op dit moment bevat het basislijnbeleid de volgende beleidsregels:

- Instellen in het Microsoft 365-beheercentrum:
  - **MFA vereisen voor beheerders:** meervoudige verificatie is vereist voor de meest bevoegde beheerdersrollen, inclusief globale beheerder.
  - **Beveiliging voor eindgebruikers: meervoudige** verificatie is alleen vereist voor gebruikers wanneer een aanmelding riskant is. 
- Instellen in Azure Active Directory-portal:
  - **Oude verificatie blokkeren:** oudere client-apps en sommige nieuwe apps maken geen gebruik van nieuwere, veiligere verificatieprotocollen. Met deze oudere apps kan beleid voor voorwaardelijke toegang worden overgeslagen en kan er ongeautoriseerde toegang tot uw omgeving worden verkrijgen. Dit beleid blokkeert toegang van clients die geen ondersteuning bieden voor voorwaardelijke toegang. 
  - **MFA vereisen voor servicebeheer:** meervoudige verificatie vereist voor toegang tot beheerhulpprogramma's, met inbegrip van Azure Portal (waar u basislijnbeleid configureert).

U wordt aangeraden al deze basislijnbeleidsregels in teschakelen. Nadat dit beleid is ingeschakeld, wordt beheerders en gebruikers gevraagd zich te registreren voor Azure AD Multi-Factor Authentication.

Zie Wat zijn basislijnbeleidsregels voor meer [informatie over dit beleid?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>MFA vereisen

Als u wilt dat alle gebruikers zich met een tweede id aanmelden:

1. Ga naar het beheercentrum en <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> kies **Setup.**

2. Kies op de pagina Setup de **optie Weergeven** op **de** kaart Aanmelden veiliger maken.

    ![Zorg dat u zich beter kunt aanmelden.](../media/setupmfa.png)
3. Kies Aan de slag op de pagina Aanmelden veiliger **maken.**

4. Schakel in het deelvenster **Aanmeldingsbeveiliging** versterken de selectievakjes naast Meervoudige verificatie vereisen voor beheerders in en gebruikers moeten zich registreren voor meervoudige verificatie en toegang blokkeren als er een risico **is** vastgesteld.
    Zorg ervoor dat u het beheerdersaccount [voor noodgevallen](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) of pauzes uitsluit van de MFA-vereiste in het **vak Gebruikers** zoeken.

    ![De beveiligingspagina voor insing verbeteren.](../media/requiremfa.png)

5. Kies **Beleid maken** onder aan de pagina.

## <a name="set-up-baseline-policies"></a>Basislijnbeleidsregels instellen

1. Ga naar de [Azure-portal](https://portal.azure.com)en ga naar voorwaardelijke toegang voor **Azure Active** \> **Directory-beveiliging** \> **om** een nieuw **beleid te maken.**

Zie de volgende specifieke instructies voor elk beleid: <br>
    - [MFA vereisen voor beheerders](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [MFA vereisen voor gebruikers](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [Verouderde verificatie blokkeren](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [MFA vereisen voor servicebeheer](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> Preview-beleidsregels bestaan niet meer en gebruikers moeten hun eigen beleid maken.

U kunt extra beleid instellen, zoals het vereisen van goedgekeurde client-apps. Zie de documentatie voor voorwaardelijke [toegang voor meer informatie.](https://docs.microsoft.com/azure/active-directory/conditional-access/)
