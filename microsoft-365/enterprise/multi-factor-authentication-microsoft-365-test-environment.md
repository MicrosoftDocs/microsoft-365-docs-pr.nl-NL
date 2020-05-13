---
title: Meervoudige verificatie voor uw Microsoft 365 Enterprise-testomgeving
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
description: Multi-factor verificatie configureren met behulp van tekstberichten die naar een smartphone worden verzonden in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: ae8cab25a20cc75992eecc600219d9f1dd869b63
ms.sourcegitcommit: 8e655c6cbb91bfb97efda9a99c39fac33eaa974a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/13/2020
ms.locfileid: "44213138"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Meervoudige verificatie voor uw Microsoft 365 Enterprise-testomgeving

*Deze testlabrichtlijnen kunnen worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een service of toepassing die de Azure AD-tenant voor uw abonnement gebruikt, u Azure-multifactorverificatie inschakelen, waarvoor meer nodig is dan alleen een gebruikersnaam en wachtwoord om een account te verifiëren. 

Met meervoudige verificatie moeten gebruikers een telefoongesprek bevestigen, een verificatiecode typen die in een sms-bericht wordt verzonden of de verificatie verifiëren met een app op hun smartphones nadat ze hun wachtwoorden correct hebben ingevoerd. Ze kunnen zich pas aanmelden nadat aan deze tweede verificatiefactor is voldaan. 
  
In dit artikel wordt beschreven hoe u verificatie op basis van sms'en in- en test voor een specifiek gebruikersaccount.
  
Er zijn twee fasen voor het instellen van meervoudige verificatie voor een account in uw Microsoft 365 Enterprise-testomgeving:
  
1. Maak de Microsoft 365 Enterprise-testomgeving.
    
2. Multifactorverificatie voor het account Gebruiker 2 inschakelen en testen.

3. Multifactorverificatie inschakelen en testen met een beleid voor voorwaardelijke toegang (optioneel).

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart met alle artikelen in de stack met Microsoft 365 Enterprise-testlabrichtlijnen.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen multi-factor authenticatie op een lichtgewicht manier wilt testen met de minimale vereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u meervoudige verificatie in een gesimuleerde onderneming wilt testen, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van multi-factor-authenticatie is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het is hier als een optie, zodat u multi-factor authenticatie testen en experimenteren met het in een omgeving die een typische organisatie vertegenwoordigt. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Multi-factor authenticatie inschakelen en testen voor het User 2-account

Schakel multi-factor authenticatie in voor het User 2-account met de volgende stappen:
  
1. Open een afzonderlijk, privéexemplaar van uw browser, ga naar het Microsoft 365-beheercentrum ( [https://portal.microsoft.com](https://portal.microsoft.com) ) en meld u aan met uw globale beheerdersaccount.
    
2. Selecteer **Gebruikers > Actieve gebruikers** op de linkernavigatiebalk.
    
3. Klik in het deelvenster Actieve gebruikers op **Multifactorverificatie**.
    
4. Selecteer in de lijst het account **Gebruiker 2.**
    
5. Klik **in** de sectie Gebruiker 2 onder **Snelle stappen**op **Inschakelen**.
    
6. Klik in het dialoogvenster **Over inschakelen van multi-factor auth** op **Multifactor auth inschakelen**.
    
7. Klik in het dialoogvenster **Updates succesvol** op **Sluiten**.
    
8. Klik op het tabblad **Microsoft 365-beheercentrum** op het pictogram gebruikersaccount rechtsboven en klik vervolgens op **Afmelden**.
    
9. Sluit uw browserexemplaar.
   
Voer de configuratie in voor het account Gebruiker 2 om een sms-bericht te gebruiken voor validatie en test het met de volgende stappen:
  
1. Open een nieuw, privéexemplaar van uw browser.
    
2. Ga naar de Office 365-portal [https://portal.office.com](https://portal.office.com) () en meld u aan met de naam en het wachtwoord van het account Gebruiker 2.
    
3. Na het aanmelden wordt u gevraagd het account in te stellen voor meer informatie. Klik op **Volgende**.
    
4. Ga als het op de pagina **Aanvullende beveiligingsverificatie:**
    
   - Selecteer uw land of regio.
    
   - Typ telefoonnummer van de smartphone die sms-berichten ontvangt.
    
   - Klik **in Methode**op Mij een code per sms **verzenden**.
    
5. Klik op **Volgende**.
    
6. Voer de verificatiecode in van het sms-bericht dat op uw smartphone is ontvangen en klik op **Verifiëren**.
    
7. Klik op de **pagina Stap 3: Houd uw bestaande toepassingen** op **Gereed**.
    
8. Als dit de eerste keer is dat u zich hebt aangemeld met het account Gebruiker 2, wordt u gevraagd het wachtwoord te wijzigen. Typ het oorspronkelijke wachtwoord en een nieuw wachtwoord twee maal en klik op **Wachtwoord bijwerken en meld u aan.** Neem het nieuwe wachtwoord op een veilige locatie op.
    
    U ziet de Office-portal voor gebruiker 2 op het tabblad **Microsoft Office Start** van uw browser.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: Multifactorauthenticatie inschakelen en testen met een beleid voor voorwaardelijke toegang

*Deze fase kan alleen worden gebruikt voor een Microsoft 365 Enterprise-testomgeving.*

In deze fase schakelt u multi-factor authenticatie in voor het User 3-account met behulp van een groep en een beleid voor voorwaardelijke toegang.

Maak vervolgens een nieuwe groep met de naam MFAUsers en voeg het account Gebruiker 3 toe.

1. Klik op het tabblad **Microsoft 365-beheercentrum** op **Groepen** in de linkernavigatie en klik vervolgens op **Groepen**.
2. Klik **op Een groep toevoegen**.
3. Selecteer **beveiliging**in het **groepstypevenster kiezen** en klik op **Volgende**.
4. Klik in het deelvenster **Basisbasis instellen** op Groep **maken**en klik vervolgens op **Sluiten**.
5. Typ **MFAUsers**in **het groepsvenster controleren en voltooien** en klik op **Volgende**.
6. Klik in de lijst met groepen op de groep **MFAUsers.**
7. Klik in het deelvenster **MFAUsers** op **Leden**en klik vervolgens op **Alle weergeven en leden beheren.**
8. Klik in het deelvenster **MFAUsers** op **Leden toevoegen,** selecteer het account **Gebruiker 3** en klik vervolgens op > sluiten > **sluiten .**

Maak vervolgens een beleid voor voorwaardelijke toegang om multifactorauthenticatie voor leden van de groep MFAUsers te vereisen.

1. Ga in een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .
2. Klik op **Azure Active Directory > Beveiliging > voorwaardelijke toegang**.
3. Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Nieuw **beleid**.
4. Typ MFA voor **gebruikersaccounts** in **Het** nieuwe deelvenster in **Naam**.
5. Klik in de sectie **Toewijzingen** op **Gebruikers en groepen**.
6. Klik op het tabblad **Opnemen** van het deelvenster **Gebruikers en groepen** op Gebruikers en groepen selecteren > gebruikers en groepen > **Selecteren**.
7. Klik **in** het deelvenster Selecteren op de groep **MFAUsers** en klik vervolgens op **> gereed selecteren**.
8. Klik in het gedeelte **Toegangsbesturingselementen** van het deelvenster **Nieuw** op **Verlenen**.
9. Klik **in** het deelvenster Subsidie op **Meervoudige verificatie vereisen**en klik vervolgens op **Selecteren**.
10. Klik in het deelvenster **Nieuw** op **Beleid** **inschakelen**en klik vervolgens op **Maken**.
11. Sluit de tabbladen **Azure-portal** en **Microsoft 365-beheercentrum.**

Als u dit beleid wilt testen, meldt u zich af en meldt u zich aan met het account Gebruiker 3. U moet worden gevraagd om MFA te configureren. Dit toont aan dat het MFAUsers-beleid wordt toegepast.

Zie de stap [Multifactorverificatie instellen](identity-secure-user-sign-ins.md#identity-mfa) in de identiteitsfase voor informatie en koppelingen om meervoudige verificatie in productie te implementeren.
    
## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Fase 2: Identiteit](identity-infrastructure.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-implementatie](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
