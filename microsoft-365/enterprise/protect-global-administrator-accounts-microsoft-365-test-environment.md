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
ms.openlocfilehash: 1ae04e4761ed86e087e647464ad522466ed6abef
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487634"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Algemene beheerdersaccounts in uw Microsoft 365 voor Enterprise testomgeving beschermen

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

U kunt digitale aanvallen van uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn. 

In dit artikel wordt uitgelegd hoe u een beleid voor voorwaardelijke toegang van Azure Active Directory (Azure AD) gebruikt om algemene beheerdersaccounts te beveiligen.

Het beveiligen van globale beheerdersaccounts in uw Microsoft 365 voor Enterprise-testomgeving bestaat uit twee fasen:
- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: voorwaardelijke toegangsbeleid configureren](#phase-2-configure-conditional-access-policies)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u de beveiliging van het account van de globale beheerder op een lichte manier wilt testen aan de minimumvereisten, volgt u de instructies in de [basisconfiguratie](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u de bescherming van een account van een globale beheerder in een gesimuleerde onderneming wilt testen, volgt u de instructies in de [Pass Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van de beveiliging van het account van een globale beheerder is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van Active Directory Domain Services (AD DS). U kunt dit hier als optie gebruiken, zodat u de beveiliging van het account van een globale beheerder kunt testen en een dergelijk account kunt gebruiken in een omgeving die een typische organisatie voorstelt. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: voorwaardelijke toegangsbeleid configureren

Maak eerst een nieuw gebruikersaccount als een speciale globale beheerder.

1. Open het [Microsoft 365-Beheercentrum](https://admin.microsoft.com/)op een apart tabblad.
2. Selecteer **gebruikers**  >  **actieve gebruikers**en selecteer vervolgens **een gebruiker toevoegen**.
3. Voer in het deelvenster **gebruiker toevoegen** **DedicatedAdmin** in de vakken **voornaam**, **weergavenaam**en **gebruikersnaam** in.
4. Selecteer **wachtwoord**, selecteer **Ik wil het wachtwoord maken**en voer vervolgens een sterk wachtwoord in. Neem het wachtwoord van dit nieuwe account op een veilige locatie op.
5. Selecteer **Volgende**.
6. Selecteer in het deelvenster **productlicenties toewijzen** de optie **Microsoft 365 E5**en selecteer vervolgens **volgende**.
7. Selecteer in het deelvenster **optionele instellingen** de optie globale beheerder voor **rollen**van  >  **Beheercentrum**  >  **Global admin**  >  **Next**.
8. Selecteer in het deelvenster **u bent bijna klaar** de optie **toevoeging voltooien**en selecteer vervolgens **sluiten**.

Vervolgens maakt u een nieuwe groep met de naam GlobalAdmins en voegt u het DedicatedAdmin-account toe.

1. Ga naar het tabblad **Microsoft 365-Beheercentrum** , selecteer **groepen** in het linker navigatieonderdeel en selecteer **groepen**.
2. Selecteer **een groep toevoegen**.
3. Selecteer in het deelvenster **een groepstype kiezen** de optie **beveiliging**en selecteer vervolgens **volgende**.
4. Selecteer **groep maken**in het deelvenster **basisbeginselen instellen** en selecteer vervolgens **sluiten**.
5. Voer in het deelvenster **groep toevoegen en voltooien** **GlobalAdmins**in en selecteer vervolgens **volgende**.
7. Selecteer in de lijst met groepen de groep **GlobalAdmins** .
8. Selecteer **leden**in het **GlobalAdmins** -deelvenster en selecteer vervolgens **AllesWeergeven en leden beheren**.
9. Selecteer **leden toevoegen**in het deelvenster **GlobalAdmins** , selecteer het **DedicatedAdmin** -account en uw globale beheerdersaccount **en selecteer vervolgens sluiten**  >  **sluiten**  >  **Close**.

Vervolgens maakt u beleidsregels voor voorwaardelijke toegang zodat u meervoudige verificatie voor algemene beheerdersaccounts en authenticatie weigert als het gebruik van het risico normaal of hoog is.

Voor dit eerste beleid moet u alle globale-beheerdersaccounts gebruikmaken van MFA.

1. Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .
2. Klik op de voorwaardelijke toegang van **Azure Active Directory**-  >  **beveiliging**  >  **Conditional Access**.
3. Selecteer in het deelvenster **voorwaardelijke toegang – beleidsregels** de optie **basisbeleid: MFA vereisen voor beheerders (preview)**.
4. Selecteer in het deelvenster **basislijn beleidsregels** de optie **beleid direct gebruiken > opslaan**.

Met dit tweede beleid wordt de toegang tot de accountverificatie van het globale beheerder blokkeren wanneer het aanmeldings risico normaal of hoog is.

1. Selecteer in het deelvenster **voorwaardelijke toegang – beleidsregels** de optie **nieuwe beleids**optie.
2. Voer in het **nieuwe** deelvenster **globale beheerders** **naam**in.
3. Selecteer in de sectie **opdrachten** de optie **gebruikers en groepen**.
4. Selecteer op het tabblad **opnemen** van het deelvenster **gebruikers en groepen** de optie **gebruikers en groepen**  >  **gebruikers en groepen**  >  **selecteren**.
5. In het **selectie** deelvenster selecteert u de groep **GlobalAdmins** **en selecteert u**vervolgens  >  **gereed**.
6. Selecteer in de sectie **opdrachten** de optie **voorwaarden**.
7. Selecteer in het deelvenster **voorwaarden** de optie **Aanmelden**, selecteer **Ja** voor **configureren**, selecteer **hoog** en **normaal**en selecteer vervolgens **selecteren** en **gereed**.
8. Selecteer in de sectie **Access-besturingselementen** van het **nieuwe** deelvenster de optie **verlenen**.
9. Selecteer in het deelvenster **verlenen** de optie **toegang blokkeren**en selecteer vervolgens **selecteren**.
10. Selecteer **in het** deelvenster **Nieuw** de optie inschakelen voor **beleidsinstelling**en selecteer **maken**.
11. Sluit de tabbladen **Azure Portal** en **Microsoft 365-Beheercentrum** .

Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich aan met het DedicatedAdmin-account. U wordt gevraagd MFA te configureren. Dit toont het toepassen van het eerste beleid.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
