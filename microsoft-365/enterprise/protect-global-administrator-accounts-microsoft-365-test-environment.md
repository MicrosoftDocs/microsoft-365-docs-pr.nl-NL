---
title: Wereldwijde beheerdersaccounts beveiligen in uw Microsoft 365 Enterprise-testomgeving
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
description: Gebruik deze stappen om wereldwijde beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving te beschermen.
ms.openlocfilehash: e6b93e3888873b6d78fec1802d179ed9624ffa63
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153866"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Wereldwijde beheerdersaccounts beveiligen in uw Microsoft 365 Enterprise-testomgeving

*Deze testlabrichtlijn kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

U digitale aanvallen op uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn. In dit artikel wordt beschreven hoe u azure active directory -beleid (Azure AD) voorwaardelijke toegang gebruikt om globale beheerdersaccounts te beschermen.

Er zijn twee fasen voor het beveiligen van algemene beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving:

1.  Maak de Microsoft 365 Enterprise-testomgeving.
2.  Bescherm uw toegewijde wereldwijde beheerdersaccount.

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen over de Microsoft 365 Enterprise-testlabrichtlijnen.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen de bescherming van wereldwijde beheerdersaccount op een lichtgewicht manier wilt testen met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u de bescherming van globale beheerdersaccount in een gesimuleerde onderneming wilt testen, volgt u de instructies in [pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van de globale beheerdersaccountbeveiliging is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS (Active Directory Domain Services). Het wordt hier als optie aangeboden, zodat u de bescherming van globale beheerdersaccount testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: Beleid voor voorwaardelijke toegang configureren

Maak eerst een nieuw gebruikersaccount aan als een toegewijde globale beheerder.

1. Open op een apart tabblad het [Microsoft 365-beheercentrum](https://admin.microsoft.com/).
2. Klik **op Gebruikers > Actieve gebruikers**en klik vervolgens op Een gebruiker **toevoegen**.
3. Typ **DedicatedAdmin** in **Voornaam,** **Weergavenaam**en **Gebruikersnaam**in het **deelvenster Gebruiker toevoegen** .
4. Klik op **Wachtwoord**, klik op **Laat me het wachtwoord maken**en typ een sterk wachtwoord. Neem het wachtwoord voor dit nieuwe account op een veilige locatie op.
5. Klik op **Volgende**.
6. Selecteer microsoft **365 E5** of Office **365 E5**in het deelvenster **Productlicenties toewijzen** en klik op **Volgende**.
7. Klik in het deelvenster **Optionele instellingen** op **Rollen**en selecteer vervolgens Toegang tot **het beheercentrum** en **globale beheerder**. Klik **op Volgende**.
8. Klik in het deelvenster **U bent bijna klaar** op Toevoegen **voltooien**en klik vervolgens op **Sluiten**.

Maak vervolgens een nieuwe groep met de naam GlobalAdmins en voeg het DedicatedAdmin-account eraan toe.

1. Klik op het tabblad **Microsoft 365-beheercentrum** op **Groepen** in de linkernavigatie en klik vervolgens op **Groepen**.
2. Klik **op Een groep toevoegen**.
3. Selecteer **beveiliging**in het **groepstypevenster kiezen** en klik op **Volgende**.
4. Klik in het deelvenster **Basisbasis instellen** op Groep **maken**en klik vervolgens op **Sluiten**.
5. Typ **GlobalAdmins**in het **groepsvenster controleren en voltooien** en klik op **Volgende**.
7. Klik in de lijst met groepen op de groep **GlobalAdmins.**
8. Klik in het deelvenster **GlobalAdmins** op **Leden**en klik vervolgens op **Alle weergeven en leden beheren.**
9. Klik in het deelvenster **GlobalAdmins** op **Leden toevoegen,** selecteer het **DedicatedAdmin-account** en uw globale beheerdersaccount en klik vervolgens op **Opslaan > sluiten > sluiten**.

Maak vervolgens beleid voor voorwaardelijke toegang om multifactorauthenticatie voor globale beheerdersaccounts te vereisen en verificatie te weigeren als het aanmeldingsrisico gemiddeld of hoog is.

Dit eerste beleid vereist dat alle accounts van globale beheerders MFA gebruiken.

1. Ga in een nieuw tabblad [https://portal.azure.com](https://portal.azure.com)van uw browser naar .
2. Klik op **Azure Active Directory > Beveiliging > voorwaardelijke toegang**.
3. Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op **Basislijnbeleid: MFA vereisen voor beheerders (voorbeeld)**.
4. Klik in het **beleidsvenster Basislijn** op **Beleid gebruiken onmiddellijk > Opslaan**.

Dit tweede beleid blokkeert de toegang tot globale verificatie van beheerdersaccount wanneer het aanmeldingsrisico gemiddeld of hoog is.

1. Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Nieuw **beleid**.
2. Typ **Globale beheerders** in **Naam**in het deelvenster **Nieuw** .
3. Klik in de sectie **Toewijzingen** op **Gebruikers en groepen**.
4. Klik op het tabblad **Opnemen** van het deelvenster **Gebruikers en groepen** op Gebruikers en groepen selecteren > gebruikers en groepen > **Selecteren**.
5. Klik **in** het deelvenster Selecteren op de groep **GlobalAdmins** en klik vervolgens op **> gereed selecteren**.
6. Klik in de sectie **Toewijzingen** op **Voorwaarden**.
7. Klik **in** het deelvenster Voorwaarden op **Aanmeldingsrisico**, klik op **Ja** voor **Configureren,** klik op **Hoog** en **Gemiddeld**en klik vervolgens op **Selecteren** en **Gereed**.
8. Klik in het gedeelte **Toegangsbesturingselementen** van het deelvenster **Nieuw** op **Verlenen**.
9. Klik **in** het deelvenster Subsidie op **Toegang blokkeren**en klik vervolgens op **Selecteren**.
10. Klik in het deelvenster **Nieuw** op **Beleid** **inschakelen**en klik vervolgens op **Maken**.
11. Sluit de tabbladen **Azure-portal** en **Microsoft 365-beheercentrum.**

Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich aan met het DedicatedAdmin-account. U moet worden gevraagd om MFA te configureren. Dit toont aan dat het eerste beleid wordt toegepast.

Zie de stap [Accounts voor globale beheerders beveiligen](identity-create-protect-global-admins.md#identity-global-admin) in de identiteitsfase voor informatie en koppelingen om uw wereldwijde beheerdersaccounts in productie te beschermen.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Fase 2: Identiteit](identity-infrastructure.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-implementatie](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
