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
ms.openlocfilehash: ad1203543db1c2bd0ea9e9bdd3433aad58db320b
ms.sourcegitcommit: 90efec455336b4cecc06a8cbf0ce287740433523
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/26/2020
ms.locfileid: "46898102"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Beleid voor het toestaan van toegang via gast en externe B2B
In dit artikel wordt uitgelegd hoe u de aanbevolen beleidsregels voor identiteiten en toegang tot toegangsrechten voor B2B-accounts (gast en externe gebruikers) kunt aanpassen. Deze richtlijnen zijn van toepassing op de [veelgebruikte beleidsregels voor identiteit en toegang tot apparaten](identity-access-policies.md).

Deze aanbevelingen zijn bedoeld om toe te passen op de **basis** niveau beveiliging. U kunt echter de aanbevelingen aanpassen op basis van de granulatie van uw behoeften voor **gevoelige** en **sterk gereguleerde** bescherming. 

Als u een pad opgeeft voor B2B-gebruikers die verificatie met de Azure AD-Tenant verlenen, bieden deze gebruikers geen toegang tot uw gehele omgeving. B2B-gebruikers hebben alleen toegang tot bronnen die met hen zijn gedeeld (zoals bestanden) binnen de services die in het beleid voor voorwaardelijke toegang zijn verleend.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Veelgebruikte beleidsregels bijwerken om gast en externe toegang toe te staan en te beschermen 

In het volgende diagram ziet u de veelgebruikte beleidsregels voor identiteits-en toegangsbeleid, en wordt aangegeven (met een potloodpictogram) welke beleidsregels u wilt toevoegen of bijwerken om gast en externe toegang te beschermen. 

![Overzicht van beleidsupdates voor de bescherming van gasttoegang](../media/identity-access-ruleset-guest.png)

In de volgende tabel vindt u een overzicht van de beleidsregels die u moet bijwerken of nieuw moet maken. De koppeling common policies naar de gekoppelde configuratie-instructies in het artikel [common Identity en Apparaattoegang-beleid](identity-access-policies.md) .

|Beveiligingsniveau|Lijnen|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA vereisen altijd voor gast en externe gebruikers](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Deze nieuwe regel maken en toepassen op gasten en externe gebruikers. Zorg dat onder aanmelden de optie alle opties niet is ingeschakeld, zodat u altijd MFA afdwingt.|
|        |[MFA vereisen wanneer het aanmeld risico *normaal* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Wijzig deze regel om gast en externe gebruikers uit te sluiten.|
|        |[Eis conforme pc’s](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Wijzig deze regel om gast en externe gebruikers uit te sluiten.|

Als u gasten en externe gebruikers in regels voor voorwaardelijke toegang wilt opnemen of uitsluiten, klikt u op het tabblad opnemen of uitsluiten en schakelt u **alle gasten en externe gebruikers**in.

![schermopname van besturingselementen voor exclusief gasten](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Meer informatie

### <a name="guests-vs-external-users"></a>Gasten versus externe gebruikers
In azure AD zijn gast en externe gebruikers hetzelfde. Het gebruikerstype voor beide gebruikers is gast. Gastgebruikers zijn B2B-gebruikers.

In Microsoft teams wordt onderscheid gemaakt tussen gastgebruikers en externe gebruikers binnen de app, maar dit zijn beide B2B-gebruikers bij het verifiëren. Zie voor meer informatie over team gast en externe gebruikers het artikel [gast en externe toegang inschakelen voor teams](teams-access-policies.md#enabling-guest-and-external-access-for-teams).

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA vereisen altijd voor gast en externe gebruikers
Met deze regel wordt een gastgebruiker gevraagd om zich aan te melden voor MFA in uw Tenant, ongeacht of ze zijn geregistreerd voor MFA in hun thuis Tenant. Bij het openen van bronnen in de Tenant zijn gasten en externe gebruikers verplicht MFA te gebruiken voor elke aanvraag. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Gast en externe gebruikers uitsluiten van MFA op basis van risico
Organisaties kunnen op basis van risico beveiliging op basis van gebruikers van identiteits bescherming ook beperkingen instellen voor de implementatie van identiteitsbeveiliging voor B2B-samenwerking-gebruikers in een resource directory, omdat hun identiteit in hun basismap is opgeslagen. Vanwege deze beperkingen adviseert Microsoft gastgebruikers uit te sluiten van op riskniveau MFA-beleidsregels en vragen deze gebruikers altijd MFA te gebruiken. 

Zie [beperkingen van identiteits bescherming voor B2B-samenwerkings gebruikers](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)voor meer informatie. 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Gebruikers van het beheer van apparaten zonder gast en externe gebruikers uitsluiten 
Er kan slechts één organisatie een apparaat beheren. Als u gast en externe gebruikers niet uitsluiten van beleidsregels waarvoor de naleving van een apparaat is vereist, blok keert dit beleid deze gebruikers. 

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over het inschakelen van voorwaardelijke toegang voor teams](teams-access-policies.md)

