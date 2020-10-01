---
title: Beleid voor identiteits-en toegangsbeleid voor het verlenen van toegang via gast en externe B2B-Microsoft 365 voor Enterprise | Microsoft docs
description: Een beschrijving van de aanbevolen voorwaardelijke toegang en gerelateerde beleidsregels voor de bescherming van de toegang van gasten en externe gebruikers.
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
ms.openlocfilehash: 3afc818f9461ad0cc5ca65ea86d5e90f61f64d9b
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327865"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Beleid voor het toestaan van toegang via gast en externe B2B

In dit artikel wordt uitgelegd hoe u de aanbevolen beleidsregels voor identiteit en Apparaattoegang aanpast om toegang te krijgen tot gast en externe gebruikers die een Azure Active Directory-Business-to-Business-account (B2B) bieden. Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).

Deze aanbevelingen zijn bedoeld om toe te passen op de **basis** niveau beveiliging. U kunt echter ook de aanbevelingen aanpassen op basis van de granulatie van uw behoeften voor **gevoelige** en **sterk gereguleerde** bescherming. 

Als u een pad opgeeft voor B2B-accounts voor verificatie met de Azure AD-Tenant, bieden deze accounts geen toegang tot uw gehele omgeving. B2B-gebruikers en hun accounts hebben alleen toegang tot de bronnen die met hen zijn gedeeld (zoals bestanden) binnen de services die zijn toegewezen aan voorwaardelijke toegangsbeleid.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Veelgebruikte beleidsregels bijwerken om gast en externe toegang toe te staan en te beschermen 

In het volgende diagram ziet u welke beleidsregels u toevoegt of bijwerkt in de algemene beleidsregels voor identiteit en Apparaattoegang om gast en externe toegang te beschermen met Azure AD B2B-accounts. 

[![Overzicht van beleidsupdates voor de bescherming van gasttoegang](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Een grotere versie van deze afbeelding weergeven](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

In de volgende tabel vindt u een overzicht van de beleidsregels die u moet maken en bijwerken. De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .

|Beveiligingsniveau|Lijnen|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen altijd voor gast en externe gebruikers](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Maak dit nieuwe beleid en configureer de volgende opties: <ul><li> Voor **toewijzingen > gebruikers en groepen > toevoegen**, kiest **u gebruikers en groepen selecteren**en selecteert u vervolgens **alle gast en externe gebruikers**. </li><li> Voor **toewijzingen > voorwaarden > aanmelden**, schakelt u alle opties uit als u meervoudige verificatie (MFA) altijd wilt afdwingen.</li>|
|        |[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.|

Als u gast en externe gebruikers wilt opnemen in en uitsluiten van beleidsregels voor voorwaardelijke toegang voor **toewijzingen > gebruikers en groepen > toevoegen** of **uitsluiten**, controleert u **alle gast en externe gebruikers**.

![schermopname van besturingselementen voor exclusief gast en externe gebruikers](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Meer informatie

### <a name="guest-and-external-access-with-microsoft-teams"></a>Gast en externe toegang met Microsoft teams

In Microsoft teams wordt het volgende gedefinieerd:

- **Gasttoegang** maakt gebruik van een Azure AD B2B-account dat kan worden toegevoegd als lid van een team en gemachtigd zijn om toegang te krijgen tot de communicatie en de bronnen van het team.

- **Externe toegang** is bedoeld voor externe gebruikers die geen B2B-account hebben. Externe toegang omvat uitnodigingen en deelnemen aan gesprekken, chats en vergaderingen, maar omvat geen team lidmaatschap en toegang tot de bronnen van het team.

Zie de [vergelijking tussen gast en externe toegang voor teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)voor meer informatie.

Beleidsregels voor voorwaardelijke toegang gelden alleen voor gasttoegang in teams omdat er een Azure AD B2B-account is.

Raadpleeg [beleids aanbevelingen voor het beveiligen van teams-chats,-groepen en-bestanden](teams-access-policies.md) voor meer informatie over het beveiligen van identiteits-en Apparaattoegang voor teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA vereisen altijd voor gast en externe gebruikers
Dit beleid vraagt bezoekers zich voor MFA aan te melden bij uw Tenant, ongeacht of ze zich voor MFA registreren in hun thuis Tenant. Bij het openen van bronnen in de Tenant zijn gast en externe gebruikers verplicht MFA te gebruiken voor elke aanvraag. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Gast en externe gebruikers uitsluiten van MFA op basis van risico
Organisaties kunnen op basis van risico beleid voor B2B-gebruikers die gebruikmaken van Azure Active Directory-identiteitsbeveiliging, beperkingen instellen voor de implementatie van Azure AD-identiteitsbeveiliging voor B2B-samenwerkings gebruikers in een resource directory, omdat hun identiteit in hun basismap zich bevindt. Vanwege deze beperkingen adviseert Microsoft gastgebruikers uit te sluiten van op riskniveau MFA-beleidsregels en vragen deze gebruikers altijd MFA te gebruiken. 

Zie [beperkingen van identiteits bescherming voor B2B-samenwerkings gebruikers](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie. 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Gebruikers van het beheer van apparaten zonder gast en externe gebruikers uitsluiten 
Er kan slechts één organisatie een apparaat beheren. Als u gast en externe gebruikers niet uitsluiten van beleidsregels waarvoor de naleving van een apparaat is vereist, blok keert dit beleid deze gebruikers. 

## <a name="next-step"></a>Volgende stap

![Stap 4: beleidsregels voor Microsoft 365 Cloud-apps](../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

Beleidsregels voor voorwaardelijke toegang configureren voor:

- [Microsoft Teams](teams-access-policies.md)
- [Exchange Online](secure-email-recommended-policies.md)
- [SharePoint](secure-email-recommended-policies.md)

