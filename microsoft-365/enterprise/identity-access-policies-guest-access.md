---
title: Beleid voor identiteits- en apparaattoegangsbeleid voor het toestaan van gast- en externe B2B-toegang - Microsoft 365 Enterprise | Microsoft Documenten
description: Beschrijft de aanbevolen voorwaardelijke toegang en bijbehorende beleidsregels voor het beschermen van de toegang van gast- en externe gebruikers.
author: BrendaCarter
manager: johmar
ms.prod: microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: bcarter
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.openlocfilehash: 8276dcf85f6c5fd61e01e67deee4fea35c1a15c4
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42806858"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a>Beleid voor het toestaan van gast- en externe B2B-toegang
In dit artikel wordt beschreven hoe u het aanbevolen algemene beleid voor identiteits- en apparaattoegangsaan aanpassen om B2B-accounttoegang (gast- en externe gebruikers) toe te staan. Deze richtlijnen zijn voortgebouwd op het [beleid voor algemene identiteits- en apparaattoegangsbeleid](identity-access-policies.md).

Deze aanbevelingen zijn ontworpen om te worden toegepast op de **basislaag** van bescherming. U de aanbevelingen echter aanpassen op basis van de granulariteit van uw behoeften aan **gevoelige** en **sterk gereguleerde** bescherming. 

Als u B2B-gebruikers een pad biedt om te verifiëren met uw Azure AD-tenant, hebben deze gebruikers geen toegang tot uw hele omgeving. B2B-gebruikers hebben alleen toegang tot bronnen die met hen worden gedeeld (zoals bestanden) binnen de services die worden verleend in het beleid voor voorwaardelijke toegang.

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a>Het gemeenschappelijke beleid bijwerken om gast- en externe toegang toe te staan en te beschermen 

In het volgende diagram wordt het algemene beleid voor identiteits- en apparaattoegangs weergegeven en wordt (met een potloodpictogram) aangegeven welk beleid moet worden toegevoegd of bijgewerkt om gast- en externe toegang te beschermen. 

![Overzicht van beleidsupdates voor het beveiligen van gasttoegang](../media/identity-access-ruleset-guest.png)

In de volgende tabel worden de beleidsregels weergegeven die u moet bijwerken of nieuwe opties moet maken. De algemene beleidsregels zijn gekoppeld aan de bijbehorende configuratie-instructies in het artikel [Algemene identiteits- en apparaattoegangsbeleidsregels.](identity-access-policies.md)

|Beschermingsniveau|Beleid|Meer informatie|
|:---------------|:-------|:----------------|
|**Basislijn**|[MFA altijd vereisen voor gast- en externe gebruikers](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Maak deze nieuwe regel en pas deze alleen toe op gasten en externe gebruikers. Onder aanmeldingsrisico laat u alle opties ongecontroleerd om MFA altijd af te dwingen.|
|        |[MFA vereisen wanneer het aanmeldingsrisico *gemiddeld* of *hoog* is](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|Wijzig deze regel om gast- en externe gebruikers uit te sluiten.|
|        |[Compatibele pc's vereisen](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|Wijzig deze regel om gast- en externe gebruikers uit te sluiten.|

Als u gasten en externe gebruikers wilt opnemen of uitsluiten in regels voor voorwaardelijke toegang, klikt u op het tabblad Opnemen of uitsluiten en controleert **u Alle gasten en externe gebruikers.**

![schermopname van besturingselementen voor het uitsluiten van gasten](../media/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a>Meer informatie

### <a name="guests-vs-external-users"></a>Gasten versus externe gebruikers
In Azure AD zijn gast- en externe gebruikers hetzelfde. Het gebruikerstype voor beide is Gast. Gastgebruikers zijn B2B-gebruikers.

Microsoft Teams maakt onderscheid tussen gastgebruikers en externe gebruikers in de app, maar dit zijn beide B2B-gebruikers bij het verifiëren. Zie [Gast- en externe toegang inschakelen voor Teams voor](teams-access-policies.md#enabling-guest-and-external-access-for-teams)meer informatie over gast- en externe gebruikers van Teams.

### <a name="require-mfa-always-for-guest-and-external-users"></a>MFA altijd vereisen voor gast- en externe gebruikers
Deze regel vraagt gasten zich te registreren voor MFA in uw tenant, ongeacht of ze zijn geregistreerd voor MFA in hun woninghuurder. Wanneer u toegang krijgt tot bronnen in uw tenant, moeten gasten en externe gebruikers MFA voor elk verzoek gebruiken. 

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a>Gasten en externe gebruikers uitsluiten van op risico's gebaseerde MFA
Hoewel organisaties op risico's gebaseerd beleid kunnen afdwingen voor B2B-gebruikers met behulp van Identiteitsbescherming, zijn er beperkingen in de implementatie van gebruikers van Identiteitsbescherming voor B2B-samenwerkingsgebruikers in een bronmap vanwege hun identiteit die in hun huis bestaat Directory. Vanwege deze beperkingen raadt Microsoft u aan gastgebruikers uit te sluiten van een op risico gebaseerd MFA-beleid en deze gebruikers te verplichten mfa altijd te gebruiken. 

Zie [Beperkingen van identiteitsbescherming voor Gebruikers van B2B-samenwerkingsverbanden voor](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)meer informatie. 

### <a name="excluding-guest-and-external-users-from-device-management"></a>Gasten en externe gebruikers uitsluiten van apparaatbeheer 
Slechts één organisatie kan een apparaat beheren. Als u gast- en externe gebruikers niet uitsluit van beleid waarvoor apparaatnaleving vereist is, worden deze gebruikers met dit beleid geblokkeerd. 

## <a name="next-steps"></a>Volgende stappen

[Meer informatie over het inschakelen van voorwaardelijke toegang voor Teams](teams-access-policies.md)

