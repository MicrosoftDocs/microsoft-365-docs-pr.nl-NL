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
description: Gebruik deze stappen om globale beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving te beschermen.
ms.openlocfilehash: 9452ac7bafec416833ece9cbcb645bd7eeee21cc
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810402"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-enterprise-test-environment"></a>Wereldwijde beheerdersaccounts beveiligen in uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan alleen worden gebruikt voor Microsoft 365 Enterprise-testomgevingen.*

U digitale aanvallen op uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn. In dit artikel wordt beschreven hoe u azure Active Directory (Azure AD) voorwaardelijke toegangsbeleid (Azure AD) gebruikt om globale beheerdersaccounts te beschermen.

Er zijn twee fasen om globale beheerdersaccounts in uw Microsoft 365 Enterprise-testomgeving te beschermen:

1.  Maak de Microsoft 365 Enterprise-testomgeving.
2.  Bescherm uw speciale wereldwijde beheerdersaccount.

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.

## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen de beveiliging van het wereldwijde beheerdersaccount op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u de beveiliging van een globale beheerdersaccount wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Voor het testen van globale beheerdersaccountbeveiliging is niet de gesimuleerde bedrijfstestomgeving vereist, die een gesimuleerd intranet bevat dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS (Active Directory Domain Services). Het wordt hier als optie geleverd, zodat u de beveiliging van het wereldwijde beheerdersaccount testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: Beleid voor voorwaardelijke toegang configureren

Maak eerst een nieuw gebruikersaccount als een speciale globale beheerder.

1. Open op een apart tabblad het [Microsoft 365-beheercentrum](https://admin.microsoft.com/).
2. Klik op **Gebruikers > Actieve gebruikers**en klik vervolgens op Een gebruiker **toevoegen**.
3. Typ In het **gebruikersvenster Toevoegen** **DedicatedAdmin** in **voornaam,** **weergavenaam**en **gebruikersnaam**.
4. Klik op **Wachtwoord,** klik op **Laat me het wachtwoord maken**en typ een sterk wachtwoord. Neem het wachtwoord voor dit nieuwe account op een veilige locatie op.
5. Klik op **Volgende**.
6. Selecteer in het deelvenster **Productlicenties toewijzen** de optie **Microsoft 365 E5** of **Office 365 E5**en klik vervolgens op **Volgende**.
7. Klik in het deelvenster **Optionele instellingen** op **Rollen**en selecteer vervolgens toegang **tot beheercentrum** en **globale beheerder**. Klik op **Volgende**.
8. Klik in het deelvenster **U bijna klaar** op Toevoegen **voltooien**en klik vervolgens op **Sluiten**.

Maak vervolgens een nieuwe groep met de naam GlobalAdmins en voeg er het DedicatedAdmin-account aan toe.

1. Klik op het tabblad **Microsoft 365-beheercentrum** op **Groepen** in de linkernavigatie en klik vervolgens op **Groepen**.
2. Klik op **Een groep toevoegen**.
3. Selecteer **Beveiliging**in het deelvenster **Een groepstype kiezen** en klik vervolgens op **Volgende**.
4. Klik in het deelvenster **Basisinstellingen** op **Groep maken**en klik vervolgens op **Sluiten**.
5. Typ **GlobalAdmins**in het **deelvenster Controleren en voltooien** en klik vervolgens op **Volgende**.
7. Klik in de lijst met groepen op de groep **GlobalAdmins.**
8. Klik in het deelvenster **Globalebeheerders** op **Leden**en klik vervolgens op **Alle weergeven en leden beheren**.
9. Klik in het deelvenster **Globalebeheerders** op **Leden toevoegen,** selecteer het **DedicatedAdmin-account** en uw globale beheerdersaccount en klik vervolgens op **Opslaan > sluiten > sluiten**.

Maak vervolgens een beleid voor voorwaardelijke toegang om meervoudige verificatie voor globale beheerdersaccounts te vereisen en om verificatie te weigeren als het aanmeldingsrisico gemiddeld of hoog is.

Dit eerste beleid vereist dat alle globale beheerdersaccounts MFA gebruiken.

1. Ga in een nieuw tabblad [https://portal.azure.com](https://portal.azure.com)van uw browser naar .
2. Klik **op Azure Active Directory > Beveiliging > voorwaardelijke toegang**.
3. Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Beleid **basislijn: MFA vereisen voor beheerders (voorbeeld).**
4. Klik in het deelvenster **Beleid basislijn** op Beleid gebruiken **> Opslaan**.

Dit tweede beleid blokkeert de toegang tot globale verificatie van beheerdersaccount wanneer het aanmeldingsrisico gemiddeld of hoog is.

1. Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Nieuw **beleid**.
2. Typ in het deelvenster **Nieuw** **Globale beheerders** in **Naam**.
3. Klik in de sectie **Toewijzingen** op **Gebruikers en groepen**.
4. Klik op het tabblad **Opnemen** van het deelvenster **Gebruikers en groepen** op Gebruikers selecteren en groepen > gebruikers en groepen > **Selecteren**.
5. Klik in het deelvenster **Selecteren** op de groep **Globalebeheerders** en klik vervolgens op **Selecteren > gedaan**.
6. Klik in de sectie **Toewijzingen** op **Voorwaarden**.
7. Klik in het deelvenster **Voorwaarden** op **Aanmeldingsrisico,** klik op **Ja** voor **Configureren**, klik op **Hoog** en **Gemiddeld**en klik vervolgens op **Selecteren** en **klaar**.
8. Klik in het gedeelte **Besturingselementen voor toegang** in het deelvenster **Nieuw** op **Grant**.
9. Klik in het **deelvenster Subsidie** op **Toegang blokkeren**en klik vervolgens op **Selecteren**.
10. Klik in het deelvenster **Nieuw** op **Aan** voor **Beleid inschakelen**en klik vervolgens op **Maken**.
11. Sluit de tabbladen **Azure-portal** en **Microsoft 365-beheercentrum.**

Als u het eerste beleid wilt testen, meldt u zich af en meldt u zich af met het DedicatedAdmin-account. U moet worden gevraagd mfa te configureren. Hieruit blijkt dat het eerste beleid wordt toegepast.

Bekijk de stap [Voor wereldwijde beheerdersaccounts beveiligen](identity-create-protect-global-admins.md#identity-global-admin) in de identiteitsfase voor informatie en koppelingen om uw wereldwijde beheerdersaccounts in productie te beschermen.

## <a name="next-step"></a>Volgende stap

Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Fase 2: Identiteit](identity-infrastructure.md)

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-implementatie](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
