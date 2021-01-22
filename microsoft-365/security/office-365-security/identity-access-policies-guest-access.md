---
title: Identiteits- en apparaattoegangsbeleid voor het toestaan van B2B-toegang van gast en externe gebruiker - Microsoft 365 voor ondernemingen | Microsoft Docs
description: Hier worden de aanbevolen voorwaardelijke toegang en verwante beleidsregels voor de beveiliging van de toegang van gasten en externe gebruikers beschreven.
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
ms.openlocfilehash: 2ef494f8e383f50f16b1e64f6387b6e5d62459c4
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932608"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Beleidsregels voor het toestaan van gasttoegang en B2B-toegang voor externe gebruikers

In dit artikel wordt beschreven hoe u het aanbevolen beleid voor apparaat- en identiteitstoegang kunt aanpassen om toegang toe te staan voor gasten en externe gebruikers met een Azure Active Directory-account (Azure AD) business-to-business-account (B2B). Deze richtlijnen zijn gebaseerd op [het algemene beleid voor identiteits- en apparaattoegang.](identity-access-policies.md)

Deze aanbevelingen zijn bedoeld voor  de basislijnbeveiligingslaag. Maar u kunt de aanbevelingen ook aanpassen op basis van uw specifieke behoeften aan **gevoelige** en **sterk reguleerde** bescherming.

Als een pad wordt gebruikt voor B2B-accounts voor verificatie bij uw Azure AD-tenant, hebben deze accounts niet toegang tot uw hele omgeving. B2B-gebruikers en hun accounts hebben toegang tot services en bronnen, zoals bestanden, die met hen zijn gedeeld via het beleid voor voorwaardelijke toegang.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Het algemene beleid bijwerken om gasten en externe gebruikerstoegang toe te staan en te beschermen

In dit diagram ziet u welk beleid moet worden toegevoegd of bijgewerkt tussen het algemene beleid voor identiteits- en apparaattoegang voor B2B-gasten en externe gebruikerstoegang.

[![Overzicht van beleidsupdates voor het beveiligen van gasttoegang](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Een grotere versie van deze afbeelding bekijken](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

De volgende tabel bevat het beleid dat u moet maken en bijwerken. De koppeling naar de bijbehorende configuratie-instructies in het artikel Common [identity and device access policies (Algemene identiteit en apparaattoegangsbeleid) is](identity-access-policies.md) gekoppeld aan de bijbehorende configuratie-instructies.

|Beveiligingsniveau|Beleidsregels|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA altijd vereisen voor gasten en externe gebruikers](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Maak dit nieuwe beleid en configureer: <ul><li>Voor **opdrachten > gebruikers en** groepen >, kiest u Gebruikers en groepen selecteren en vervolgens Alle gast en **externe gebruikers.**</li><li>Als **voor toewijzingen > de >,** laat u alle opties uitgeschakeld om altijd meervoudige verificatie (MFA) af te dwingen.</li></ul>|
||[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* *of* hoog is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Wijzig dit beleid om gasten en externe gebruikers uit te sluiten.|

Als u gasten en externe gebruikers wilt opnemen > uitsluiten in het beleid voor **voorwaardelijke** toegang, moet u voor Toewijzingen > Gebruikers en groepen > Alle gast en externe gebruikers opnemen of **uitsluiten.** 

![schermopname van besturingselementen voor het uitsluiten van gasten en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Meer informatie

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Gasten en externe gebruikerstoegang met Microsoft Teams

Microsoft Teams definieert de volgende gebruikers:

- **Voor gasttoegang** wordt een B2B Azure AD-account gebruikt dat kan worden toegevoegd als lid van een team en toegang heeft tot de communicatie en bronnen van het team.

- **Externe toegang** is voor een externe gebruiker die geen B2B-account heeft. Externe gebruikerstoegang omvat uitnodigingen, oproepen, chats en vergaderingen, maar omvat geen teamlidmaatschap en toegang tot de resources van het team.

Zie de vergelijking tussen gasten en externe gebruikerstoegang [voor teams voor meer informatie.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)

Zie Beleidsaanbevelingen voor het beveiligen van [Teams-chats,](teams-access-policies.md)-groepen en -bestanden voor meer informatie over het beveiligen van identiteits- en apparaattoegangsbeleid voor Teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA altijd vereisen voor gast- en externe gebruikers

Met dit beleid wordt gasten gevraagd zich te registreren voor MFA in uw tenant, ongeacht of ze zijn geregistreerd voor MFA in hun thuisten tenant. Als u bronnen in uw tenant gebruikt, moeten gasten en externe gebruikers MFA gebruiken voor elke aanvraag.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Gasten en externe gebruikers uitsluiten van risicogebaseerde MFA

Hoewel organisaties risicogebaseerd beleid kunnen afdwingen voor B2B-gebruikers die Azure AD-identiteitsbescherming gebruiken, gelden er beperkingen voor de implementatie van Azure AD-identiteitsbescherming voor B2B-samenwerkingsgebruikers in een resourcemap vanwege hun identiteit die in hun thuismap bestaat. Vanwege deze beperkingen raadt Microsoft u aan gasten uit te sluiten van risicogebaseerd MFA-beleid en deze gebruikers altijd MFA te laten gebruiken.

Zie Beperkingen van [identiteitsbeveiliging voor B2B-samenwerkingsgebruikers voor meer informatie.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)

### <a name="excluding-guests-and-external-users-from-device-management"></a>Gasten en externe gebruikers uitsluiten van apparaatbeheer

Slechts één organisatie kan een apparaat beheren. Als u gasten en externe gebruikers niet uitsluit van beleid waarvoor apparaat compliance is vereist, worden deze gebruikers geblokkeerd door dit beleid.

## <a name="next-step"></a>Volgende stap

![Stap 4: Beleid voor Microsoft 365-cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
