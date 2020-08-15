---
title: Algemene beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving beschermen
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/12/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: Volg deze stappen voor het beveiligen van globale beheerdersaccounts in uw Microsoft 365 voor Enterprise test-omgeving.
ms.openlocfilehash: fff09ca41ff0b648d46b5c33f753affc01242264
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695180"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Algemene beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving beschermen

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

U kunt digitale aanvallen van uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn. In dit artikel wordt uitgelegd hoe u een beleid voor voorwaardelijke toegang van Azure Active Directory (Azure AD) gebruikt om algemene beheerdersaccounts te beveiligen.

Er zijn twee fasen voor het beschermen van globale beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving:

1.  Maak de testomgeving Microsoft 365 for Enterprise.
2.  Beveilig uw eigen account voor globale beheerders.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u alleen de beveiliging van het account van de globale beheerder op een lichte manier wilt testen met de minimumvereisten, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u de bescherming van een account van een globale beheerder in een gesimuleerde onderneming wilt testen, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van de beveiliging van het account van een globale beheerder is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van Active Directory Domain Services (AD DS). U kunt dit hier als optie gebruiken, zodat u de beveiliging van het account van een globale beheerder kunt testen en een dergelijk account kunt gebruiken in een omgeving die een typische organisatie voorstelt. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: voorwaardelijke toegangsbeleid configureren

Maak eerst een nieuw gebruikersaccount als een speciale globale beheerder.

1. Open het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/)op een apart tabblad.
2. Klik op **gebruikers > actieve gebruikers**en klik vervolgens op **een gebruiker toevoegen**.
3. Typ in het deelvenster **gebruiker toevoegen** **DedicatedAdmin** in **voornaam**, **weergavenaam**en **gebruikersnaam**.
4. Klik op **wachtwoord**, klik op **Ik wil het wachtwoord maken**en typ vervolgens een sterk wachtwoord. Neem het wachtwoord van dit nieuwe account op een veilige locatie op.
5. Klik op **Volgende**.
6. Selecteer in het deelvenster **productlicenties toewijzen** de optie **Microsoft 365 E5**en klik op **volgende**.
7. Klik in het deelvenster **optionele instellingen** op **rollen**en selecteer vervolgens **toegangsbeheer centrum** en **globale beheerder**. Klik op **volgende**.
8. Klik in het deelvenster **u bent bijna klaar** op **toevoegen voltooien**en klik vervolgens op **sluiten**.

Vervolgens maakt u een nieuwe groep met de naam GlobalAdmins en voegt u het DedicatedAdmin-account toe.

1. Ga naar het tabblad **Microsoft 365-Beheercentrum** , klik in het linker navigatiemenu op **groepen** en klik vervolgens op **groepen**.
2. Klik op **groep toevoegen**.
3. Selecteer in het deelvenster **een groepstype kiezen** de optie **beveiliging**en klik vervolgens op **volgende**.
4. Klik in het deelvenster **basisbeginselen instellen** op **groep maken**en klik vervolgens op **sluiten**.
5. In het deelvenster **groep controleren en voltooien** , typt u **GlobalAdmins**en klikt u op **volgende**.
7. Klik in de lijst met groepen op de groep **GlobalAdmins** .
8. Klik in het deelvenster **GlobalAdmins** op **leden**en klik op **AllesWeergeven en leden beheren**.
9. Klik in het deelvenster **GlobalAdmins** op **leden toevoegen**, selecteer het **DedicatedAdmin** -account en het account van de globale beheerder en klik vervolgens op **Opslaan > sluiten > sluiten**.

Vervolgens maakt u een beleid voor voorwaardelijke toegang voor de authenticatie van meervoudige beheerders, en om authenticatie te weigeren als het registratie risico normaal of hoog is.

Voor dit eerste beleid moet u alle globale-beheerdersaccounts gebruikmaken van MFA.

1. Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .
2. Klik **> beveiligings > voorwaardelijke toegang op Azure Active Directory**.
3. Klik in het deelvenster **voorwaardelijke toegang-beleidsregels** op **basislijn-beleid: MFA vereisen voor beheerders (preview)**.
4. Klik in het deelvenster **basislijn beleidsregels** **direct op beleid gebruiken > opslaan**.

Met dit tweede beleid wordt de toegang tot de accountverificatie van het globale beheerder blokkeren wanneer het aanmeldings risico normaal of hoog is.

1. Klik in het deelvenster **voorwaardelijke toegang – beleidsregels** op **Nieuw beleid**.
2. Typ in het **nieuwe** deelvenster de naam van een **globale beheerder** in de **naam**.
3. Klik in de sectie **opdrachten** op **gebruikers en groepen**.
4. Klik op het tabblad **opnemen** van het deelvenster **gebruikers en groepen** op **gebruikers en groepen > gebruikers en groepen selecteren > selecteren**.
5. Klik in het **selectie** deelvenster op de groep **GlobalAdmins** en klik vervolgens op **selecteren > gereed**.
6. Klik in de sectie **opdrachten** op **voorwaarden**.
7. Klik in het deelvenster **voorwaarden** op **aanmeld risico**, klik op **Ja** voor **configureren**, klik op **hoog** en **normaal**en klik vervolgens op **selecteren** en **Voltooien**.
8. Klik in de sectie **Access-besturingselementen** van het **nieuwe** deelvenster op **toewijzen**.
9. Klik in het deelvenster **subsidie** op **toegang blokkeren**en klik vervolgens op **selecteren**.
10. Klik in het **nieuwe** deelvenster op **aan** voor inschakelen van het **beleid**en klik vervolgens op **maken**.
11. Sluit de tabbladen **Azure Portal** en **Microsoft 365-Beheercentrum** .

Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich aan met het DedicatedAdmin-account. U wordt gevraagd MFA te configureren. Dit toont het toepassen van het eerste beleid.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
