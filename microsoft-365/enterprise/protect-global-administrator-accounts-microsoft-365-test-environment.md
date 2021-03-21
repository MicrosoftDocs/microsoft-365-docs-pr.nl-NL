---
title: Globale beheerdersaccounts beveiligen in uw testomgeving van Microsoft 365 voor bedrijven
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
description: Gebruik deze stappen om globale beheerdersaccounts te beveiligen in uw testomgeving van Microsoft 365 voor ondernemingen.
ms.openlocfilehash: 3eab538b59e460857e2fa195aaacf51051f94d6b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918880"
---
# <a name="protect-global-administrator-accounts-in-your-microsoft-365-for-enterprise-test-environment"></a>Globale beheerdersaccounts beveiligen in uw testomgeving van Microsoft 365 voor bedrijven

*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*

U kunt digitale aanvallen op uw organisatie voorkomen door ervoor te zorgen dat uw beheerdersaccounts zo veilig mogelijk zijn. 

In dit artikel wordt beschreven hoe u beleid voor voorwaardelijke toegang van Azure Active Directory (Azure AD) gebruikt om globale beheerdersaccounts te beschermen.

Het beveiligen van globale beheerdersaccounts in uw testomgeving van Microsoft 365 voor ondernemingen bestaat uit twee fasen:
- [Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Beleid voor voorwaardelijke toegang configureren](#phase-2-configure-conditional-access-policies)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.

## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 voor ondernemingstestomgeving opbouwen

Als u de beveiliging van globale beheerdersaccounts op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [Lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u de beveiliging van globale beheerdersaccounts in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van globale beheerdersaccountbeveiliging is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS (Active Directory Domain Services). Het wordt hier als een optie aangeboden, zodat u de beveiliging van globale beheerdersaccounts kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt. 
  
## <a name="phase-2-configure-conditional-access-policies"></a>Fase 2: Beleid voor voorwaardelijke toegang configureren

Maak eerst een nieuw gebruikersaccount als een toegewezen globale beheerder.

1. Open op een apart tabblad het [Microsoft 365-beheercentrum.](https://admin.microsoft.com/)
2. Selecteer **Gebruikers**  >  **Actieve gebruikers** en selecteer vervolgens Een gebruiker **toevoegen.**
3. Voer in **het deelvenster** Gebruiker toevoegen **DedicatedAdmin** in de vakken **Voornaam,** **Weergavenaam** en **Gebruikersnaam** in.
4. Selecteer **Wachtwoord,** selecteer **Laat me het wachtwoord maken** en voer een sterk wachtwoord in. Neem het wachtwoord voor dit nieuwe account op een veilige locatie op.
5. Selecteer **Volgende**.
6. Selecteer in **het deelvenster Productlicenties** toewijzen de optie **Microsoft 365 E5** en selecteer **vervolgens Volgende**.
7. Selecteer in **het deelvenster Optionele** instellingen de optie   >  **Rollenbeheerder toegang tot** Globale  >  **beheerder**  >  **Volgende.**
8. Selecteer in **het deelvenster U bent bijna klaar** de optie Toevoegen **voltooien** en selecteer **vervolgens Sluiten.**

Maak vervolgens een nieuwe groep met de naam GlobalAdmins en voeg het DedicatedAdmin-account hieraan toe.

1. Selecteer Op **het tabblad Microsoft 365-beheercentrum** de optie **Groepen** in de linkernavigatie en selecteer vervolgens **Groepen**.
2. Selecteer **Een groep toevoegen.**
3. Selecteer in **het deelvenster Een groeptype** kiezen de optie **Beveiliging** en selecteer vervolgens **Volgende.**
4. Selecteer in **het deelvenster De basisbeginselen** instellen de optie Groep **maken** en selecteer vervolgens **Sluiten.**
5. Voer in **het deelvenster Controleren en** voltooien groep toevoegen **GlobalAdmins** in en selecteer **volgende**.
7. Selecteer in de lijst met groepen de **groep GlobalAdmins.**
8. Selecteer leden **in het deelvenster GlobalAdmins** **en** selecteer **vervolgens Alle leden weergeven en beheren.**
9. Selecteer in **het deelvenster GlobalAdmins** de optie **Leden** toevoegen, selecteer het **DedicatedAdmin-account** en uw globale beheerdersaccount en selecteer **vervolgens Sluiten**  >    >  **sluiten opslaan.**

Maak vervolgens beleid voor voorwaardelijke toegang om meervoudige verificatie voor globale beheerdersaccounts te vereisen en verificatie te weigeren als het aanmeldingsrisico gemiddeld of hoog is.

Dit eerste beleid vereist dat alle globale beheerdersaccounts MFA gebruiken.

1. Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .
2. Klik **op Azure Active Directory**  >  **Security** Conditional  >  **Access**.
3. Selecteer in **het deelvenster Voorwaardelijke** toegang - Beleid de optie **Basislijnbeleid: MFA vereisen voor beheerders (voorbeeld)**.
4. Selecteer in **het deelvenster** Basislijnbeleid de optie Beleid direct gebruiken **> Opslaan.**

Dit tweede beleid blokkeert de toegang tot globale verificatie van beheerdersaccounts wanneer het aanmeldingsrisico gemiddeld of hoog is.

1. Selecteer in **het deelvenster Voorwaardelijke** toegang – Beleid de optie **Nieuw beleid.**
2. Voer in **het** deelvenster Nieuw **globale beheerders** in **naam in.**
3. Selecteer gebruikers en groepen in **de** sectie **Opdrachten.**
4. Selecteer op **het** tabblad Opnemen van het deelvenster Gebruikers **en groepen** de optie Gebruikers en **groepen** selecteren Gebruikers  >  **en groepen**  >  **Selecteren**.
5. Selecteer in **het** deelvenster Selecteren de **groep GlobalAdmins** en selecteer **vervolgens Done**  >  **selecteren.**
6. Selecteer voorwaarden in **de** sectie **Opdrachten.**
7. Selecteer in **het** deelvenster Voorwaarden de optie Aanmeldingsrisico, selecteer **Ja** voor **configureren,** selecteer **Hoog** en **Gemiddeld** en selecteer vervolgens **Selecteren** en **Klaar.**
8. Selecteer in **de sectie Besturingselementen** van Access **van het** deelvenster Nieuw de optie **Grant**.
9. Selecteer in **het** deelvenster Verlenen de optie **Toegang blokkeren** en selecteer **vervolgens Selecteren**.
10. Selecteer in **het** deelvenster Nieuw **de optie Aan** voor Beleid **inschakelen** en selecteer vervolgens **Maken.**
11. Sluit de **tabbladen Azure Portal** en **Microsoft 365-beheercentrum.**

Als u het eerste beleid wilt testen, meld u zich af en meld u aan met het DedicatedAdmin-account. U moet worden gevraagd om MFA te configureren. Dit laat zien dat het eerste beleid wordt toegepast.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Routekaart voor identiteit](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)