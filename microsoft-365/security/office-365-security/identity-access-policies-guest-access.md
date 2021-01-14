---
title: Beleid voor identiteits-en toegangsbeleid voor het toestaan van gastgebruikers en externe gebruikers B2B Access-Microsoft 365 voor ondernemingen | Microsoft docs
description: Een beschrijving van de aanbevolen voorwaardelijke toegang en gerelateerde beleidsregels voor het beschermen van de toegang van gasten en externe gebruikers.
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845074"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a>Beleid voor het verlenen van toegang tot gasttoegang en B2B-toegang tot externe gebruikers

Dit artikel bevat informatie over het aanpassen van het aanbevolen beleid voor het aanwijzen van gebruikers en het instellen van toegangsbeleid voor gasten en externe gebruikers die een Azure Active Directory-account (Azure AD) voor Business-to-Business (B2B) hebben. Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).

Deze aanbevelingen zijn bedoeld om toe te passen op de **basis** niveau beveiliging. U kunt ook de aanbevelingen aanpassen op basis van uw specifieke behoeften voor **gevoelige** en **sterk begereglementeerde** bescherming.

Als u een pad opgeeft voor B2B-accounts voor verificatie met de Azure AD-Tenant, bieden deze accounts geen toegang tot uw gehele omgeving. B2B-gebruikers en hun accounts hebben toegang tot services en bronnen, zoals bestanden, gedeeld door het beleid voor voorwaardelijke toegang.

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a>Veelgebruikte beleidsregels bijwerken om gasten en externe gebruikers toegang toe te staan en te beschermen

In dit diagram ziet u welke beleidsregels u kunt toevoegen of bijwerken tussen de veelgebruikte beleidsregels voor identiteits-en Apparaattoegang, voor B2B-gasten en externe gebruikers toegang.

[![Overzicht van beleidsupdates voor de bescherming van gasttoegang](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Een grotere versie van deze afbeelding weergeven](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

In de volgende tabel vindt u een overzicht van de beleidsregels die u moet maken en bijwerken. De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .

|Beveiligingsniveau|Lijnen|Meer informatie|
|---|---|---|
|**Basislijn**|[MFA vereist altijd voor gasten en externe gebruikers](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Maak dit nieuwe beleid en configureer de volgende opties: <ul><li>Voor **toewijzingen > gebruikers en groepen > toevoegen**, kiest **u gebruikers en groepen selecteren** en selecteert u vervolgens **alle gast en externe gebruikers**.</li><li>Voor **toewijzingen > voorwaarden > aanmelden**, schakelt u alle opties uit als u meervoudige verificatie (MFA) altijd wilt afdwingen.</li></ul>|
||[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Dit beleid wijzigen om gasten en externe gebruikers uit te sluiten.|
||[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Dit beleid wijzigen om gasten en externe gebruikers uit te sluiten.|

Als u gasten en externe gebruikers in beleidsregels voor voorwaardelijke toegang wilt opnemen of uitsluiten, schakelt u de selectievakjes voor **toewijzingen > gebruikers en groepen > toevoegen** of **uitsluiten** in en schakelt u **alle gast en externe gebruikers** in.

![schermopname van besturingselementen voor exclusief gasten en externe gebruikers](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Meer informatie

### <a name="guests-and-external-user-access-with-microsoft-teams"></a>Gasten en externe gebruikers toegang met Microsoft teams

In Microsoft teams worden de volgende gebruikers gedefinieerd:

- **Gasttoegang** maakt gebruik van een Azure AD B2B-account dat kan worden toegevoegd als lid van een team en toegang hebben tot de communicatie en de bronnen van het team.

- **Externe toegang** is bedoeld voor externe gebruikers die geen B2B-account hebben. Toegang tot externe gebruikers omvat uitnodigingen, gesprekken, chats en vergaderingen, maar omvat geen team lidmaatschap en toegang tot de bronnen van het team.

Zie de [vergelijking tussen gasten en externe gebruikers toegang voor teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)voor meer informatie.

Zie [aanbevelingen voor het beveiligen van teams-chats,-groepen en-bestanden](teams-access-policies.md)voor meer informatie over het beveiligen van beleidsregels voor identiteit en Apparaattoegang voor teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA vereisen altijd voor gast en externe gebruikers

Dit beleid vraagt bezoekers zich voor MFA aan te melden bij uw Tenant, ongeacht of ze zich voor MFA registreren in hun thuis Tenant. Bij het openen van bronnen in de Tenant zijn gasten en externe gebruikers verplicht MFA te gebruiken voor elke aanvraag.

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a>Gasten en externe gebruikers uitsluiten van MFA op basis van risico

Organisaties kunnen op basis van risico beleid voor B2B-gebruikers die gebruikmaken van Azure Active Directory-identiteitsbeveiliging, beperkingen instellen voor de implementatie van Azure AD-identiteitsbeveiliging voor B2B-samenwerkings gebruikers in een resource directory, omdat hun identiteit in hun basismap zich bevindt. Als gevolg van deze beperkingen adviseert Microsoft gasten niet uit te sluiten op basis van Risk MFA-beleidsregels en vragen deze gebruikers altijd MFA te gebruiken.

Zie [beperkingen van identiteits bescherming voor B2B-samenwerkings gebruikers](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie.

### <a name="excluding-guests-and-external-users-from-device-management"></a>Gasten en externe gebruikers uitsluiten van Apparaatbeheer

Er kan slechts één organisatie een apparaat beheren. Als u gasten en externe gebruikers niet uitsluiten van beleidsregels waarvoor de naleving van een apparaat is vereist, blok keert dit beleid deze gebruikers.

## <a name="next-step"></a>Volgende stap

![Stap 4: beleidsregels voor Microsoft 365 Cloud-apps](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](sharepoint-file-access-policies.md)
