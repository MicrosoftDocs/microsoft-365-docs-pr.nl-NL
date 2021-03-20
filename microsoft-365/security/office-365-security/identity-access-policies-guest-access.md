---
title: Beleid voor identiteits- en apparaattoegang voor het toestaan van gast- en externe gebruiker B2B-toegang - Microsoft 365 voor bedrijven | Microsoft Docs
description: Beschrijft het aanbevolen beleid voor voorwaardelijke toegang en verwante beleidsregels voor het beschermen van de toegang van gasten en externe gebruikers.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910652"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Beleid voor het toestaan van gasttoegang en B2B-externe gebruikerstoegang

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor apparaat- en identiteitstoegang aanpast om toegang te verlenen aan gasten en externe gebruikers die een Azure Active Directory-account (Azure AD) Business-to-Business (B2B) hebben. Deze richtlijnen zijn gebaseerd op [het algemene beleid voor identiteits- en apparaattoegang.](identity-access-policies.md)

Deze aanbevelingen zijn bedoeld om  van toepassing te zijn op de basislijnbeveiligingslaag. Maar u kunt de aanbevelingen ook aanpassen op basis van uw specifieke behoeften voor **gevoelige** en sterk **gereguleerde** beveiliging.

Als u een pad biedt voor B2B-accounts om te verifiëren met uw Azure AD-tenant, hebben deze accounts geen toegang tot uw hele omgeving. B2B-gebruikers en hun accounts hebben toegang tot services en resources, zoals bestanden, die met hen worden gedeeld via beleid voor voorwaardelijke toegang.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Het algemene beleid bijwerken om gasten en externe gebruikerstoegang toe te staan en te beveiligen

In dit diagram ziet u welk beleid moet worden toegevoegd of bijgewerkt tussen het algemene beleid voor identiteits- en apparaattoegang, voor B2B-gast- en externe gebruikerstoegang.

[![Overzicht van beleidsupdates voor het beschermen van gasttoegang](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

In de volgende tabel ziet u de beleidsregels die u moet maken en bijwerken. De algemene beleidsregels koppelen aan de bijbehorende configuratie-instructies in het artikel Algemene [identiteits-](identity-access-policies.md) en apparaattoegangsbeleid.

|Beveiligingsniveau|Beleid|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA altijd vereisen voor gasten en externe gebruikers](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Maak dit nieuwe beleid en configureer: <ul><li>Voor **Opdrachten > Gebruikers en groepen > Opnemen,** kiest u Gebruikers en groepen selecteren **en** selecteert u vervolgens **Alle gast- en externe gebruikers.**</li><li>Voor **Toewijzingen > voorwaarden > Aanmelden**, laat u alle opties uitgeschakeld om altijd meervoudige verificatie (MFA) af te dwingen.</li></ul>|
||[MFA vereisen wanneer het aanmeldingsrisico gemiddeld *of* *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.|

Als u gasten en externe gebruikers wilt opnemen of uitsluiten in beleidsregels voor voorwaardelijke toegang, controleert u alle gast- en externe gebruikers voor Opdrachten > Gebruikers en groepen **> Opnemen of** **Uitsluiten.**

![schermopname van besturingselementen voor het uitsluiten van gasten en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Meer informatie

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Gasten en externe gebruikerstoegang met Microsoft Teams

Microsoft Teams definieert de volgende gebruikers:

- **Gasttoegang** maakt gebruik van een Azure AD B2B-account dat kan worden toegevoegd als lid van een team en toegang heeft tot de communicatie en bronnen van het team.

- **Externe toegang** is voor een externe gebruiker die geen B2B-account heeft. Externe gebruikerstoegang omvat uitnodigingen, oproepen, chats en vergaderingen, maar omvat geen teamlidmaatschap en toegang tot de resources van het team.

Zie de vergelijking tussen gasten en externe gebruikerstoegang voor [teams voor meer informatie.](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)

Zie Beleidsaanbevelingen voor het beveiligen van [Teams-chats, groepen en bestanden](teams-access-policies.md)voor meer informatie over het beveiligen van identiteits- en apparaattoegangsbeleid voor Teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA altijd vereisen voor gast- en externe gebruikers

Dit beleid vraagt gasten zich te registreren voor MFA in uw tenant, ongeacht of ze zijn geregistreerd voor MFA in hun huisten tenant. Wanneer u toegang hebt tot resources in uw tenant, moeten gasten en externe gebruikers MFA voor elke aanvraag gebruiken.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Gasten en externe gebruikers uitsluiten van risicogebaseerde MFA

Hoewel organisaties op risico's gebaseerde beleidsregels kunnen afdwingen voor B2B-gebruikers die Azure AD Identity Protection gebruiken, gelden er beperkingen voor de implementatie van Azure AD Identity Protection voor B2B-samenwerkingsgebruikers in een resourcemap vanwege hun identiteit die in de thuismap staat. Vanwege deze beperkingen raadt Microsoft u aan gasten uit te sluiten van MFA-beleid op basis van risico's en deze gebruikers altijd MFA te laten gebruiken.

Zie Beperkingen van identiteitsbeveiliging [voor B2B-samenwerkingsgebruikers](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie.

### <a name="excluding-guests-and-external-users-from-device-management"></a>Gasten en externe gebruikers uitsluiten van apparaatbeheer

Slechts één organisatie kan een apparaat beheren. Als u gasten en externe gebruikers niet uitsluit van beleidsregels waarvoor apparaat compliance vereist is, worden deze gebruikers geblokkeerd door dit beleid.

## <a name="next-step"></a>Volgende stap

![Stap 4: Beleidsregels voor Cloud-apps van Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleid voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)