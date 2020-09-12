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
ms.openlocfilehash: a88fc5f46a6dafda72a24ba5e80587b24a216955
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546470"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Beleid voor het toestaan van toegang via gast en externe B2B

In dit artikel wordt uitgelegd hoe u de aanbevolen beleidsregels voor identiteits-en Apparaattoegang kunt aanpassen, zodat u toegang hebt tot een account van Business-to-Business (B2B) en externe gebruikers. Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).

Deze aanbevelingen zijn bedoeld om toe te passen op de **basis** niveau beveiliging. U kunt echter ook de aanbevelingen aanpassen op basis van de granulatie van uw behoeften voor **gevoelige** en **sterk gereguleerde** bescherming. 

Als u een pad opgeeft voor B2B-gebruikers die zich in de Tenant van Azure Active Directory (Azure AD) bevinden, bieden deze gebruikers geen toegang tot uw gehele omgeving. B2B-gebruikers hebben alleen toegang tot bronnen die met hen zijn gedeeld (zoals bestanden) binnen de services die in het beleid voor voorwaardelijke toegang zijn verleend.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Veelgebruikte beleidsregels bijwerken om gast en externe toegang toe te staan en te beschermen 

In het volgende diagram ziet u welke beleidsregels u toevoegt of bijwerkt vanuit de veelgebruikte beleidsregels identiteit en Apparaattoegang. 

[![Overzicht van beleidsupdates voor de bescherming van gasttoegang](../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

[Een grotere versie van deze afbeelding weergeven](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

In de volgende tabel vindt u een overzicht van de beleidsregels die u moet bijwerken of nieuw moet maken. De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .

|Beveiligingsniveau|Lijnen|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen altijd voor gast en externe gebruikers](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Dit nieuwe beleid maken en toepassen op gasten en externe gebruikers. Schakel onder **risico voor aanmelden**de optie alle opties uit als u meervoudige verificatie (MFA) altijd wilt afdwingen.|
|        |[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Dit beleid wijzigen om gast en externe gebruikers uit te sluiten.|

Als u gasten en externe gebruikers wilt opnemen of uitsluiten in regels voor voorwaardelijke toegang, klikt u op het tabblad **opnemen** of **uitsluiten** en schakelt u **alle gasten en externe gebruikers**in.

![schermopname van besturingselementen voor exclusief gasten](../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Meer informatie

### <a name="guests-vs-external-users"></a>Gasten versus externe gebruikers
In azure AD zijn gast en externe gebruikers hetzelfde. Het gebruikerstype voor beide gebruikers is gast. Gastgebruikers zijn B2B-gebruikers.

In Microsoft teams wordt onderscheid gemaakt tussen gastgebruikers en externe gebruikers binnen de app, maar dit zijn beide B2B-gebruikers bij het verifiëren. Zie voor meer informatie over team gast en externe gebruikers het artikel [gast en externe toegang inschakelen voor teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA vereisen altijd voor gast en externe gebruikers
Dit beleid vraagt bezoekers zich voor MFA aan te melden bij uw Tenant, ongeacht of ze zich voor MFA registreren in hun thuis Tenant. Bij het openen van bronnen in de Tenant zijn gasten en externe gebruikers verplicht MFA te gebruiken voor elke aanvraag. 

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

