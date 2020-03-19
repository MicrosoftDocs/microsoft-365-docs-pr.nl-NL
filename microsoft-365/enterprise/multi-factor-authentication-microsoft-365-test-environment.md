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
description: Configureer multi-factor authenticatie met behulp van tekstberichten die naar een smartphone worden verzonden in uw Microsoft 365 Enterprise-testomgeving.
ms.openlocfilehash: ea2041a463b224781df101251dab0f4d9f0e8753
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/13/2020
ms.locfileid: "42806280"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-enterprise-test-environment"></a>Meervoudige verificatie voor uw Microsoft 365 Enterprise-testomgeving

*Deze Test Lab Guide kan worden gebruikt voor zowel Microsoft 365 Enterprise- als Office 365 Enterprise-testomgevingen.*

Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een service of toepassing die de Azure AD-tenant voor uw abonnement gebruikt, u Azure-meervoudige verificatie inschakelen, waarvoor meer nodig is dan alleen een gebruikersnaam en wachtwoord om een Account. 

Met multi-factor authenticatie moeten gebruikers een telefoongesprek erkennen, een verificatiecode typen die in een sms-bericht wordt verzonden of een app-wachtwoord opgeven op hun smartphones nadat ze hun wachtwoorden correct hebben ingevoerd. Ze kunnen zich pas aanmelden nadat deze tweede verificatiefactor is voldaan. 
  
In dit artikel wordt beschreven hoe u verificatie op basis van sms'en inschakelt en test voor een specifiek gebruikersaccount.
  
Er zijn twee fasen voor het instellen van meervoudige verificatie voor een account in uw Microsoft 365 Enterprise-testomgeving:
  
1. Maak de Microsoft 365 Enterprise-testomgeving.
    
2. Multi-factor authenticatie inschakelen en testen voor het Gebruikers 2-account.

3. Multifactorauthenticatie inschakelen en testen met een beleid voor voorwaardelijke toegang (optioneel).

![Test Lab-hulplijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik [hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de Microsoft 365 Enterprise Test Lab Guide stack.
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a>Fase 1: Uw Microsoft 365 Enterprise-testomgeving uitbouwen

Als u alleen multi-factor authenticatie op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u meervoudige verificatie wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Het testen van multi-factor authenticatie vereist niet de gesimuleerde bedrijfstestomgeving, die een gesimuleerd intranet bevat dat is verbonden met het internet en directorysynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het wordt hier als optie geleverd, zodat u multi-factor authenticatie testen en ermee experimenteren in een omgeving die een typische organisatie vertegenwoordigt. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Meervoudige verificatie inschakelen en testen voor het Gebruikers 2-account

Schakel multi-factor authenticatie in voor het Gebruikers 2-account met de volgende stappen:
  
1. Open een afzonderlijke, privé-instantie van uw browser, ga[https://portal.microsoft.com](https://portal.microsoft.com)naar het Microsoft 365-beheercentrum en meld u vervolgens aan met uw globale beheerdersaccount.
    
2. Klik in de linkernavigatie op **Gebruikers > Actieve gebruikers**.
    
3. Klik in het deelvenster Actieve gebruikers op **Meervoudige verificatie**.
    
4. Selecteer in de lijst het **account Gebruiker 2.**
    
5. Klik in de sectie **Gebruiker 2** onder **Snelle stappen**op **Inschakelen**.
    
6. Klik in het dialoogvenster Over het inschakelen van **multi-factor auth** op **Multifactor auth inschakelen.**
    
7. Klik in het dialoogvenster **Updates succesvol** op **Sluiten**.
    
8. Klik op het tabblad **Microsoft 365-beheercentrum** op het pictogram van het gebruikersaccount rechtsboven en klik vervolgens op **Afmelden**.
    
9. Sluit uw browserinstantie.
   
Voltooi de configuratie voor het Gebruikers 2-account om een sms-bericht te gebruiken voor validatie en test het met de volgende stappen:
  
1. Open een nieuw, privé-exemplaar van uw browser.
    
2. Ga naar de Office 365-portal[https://portal.office.com](https://portal.office.com)en meld u aan met de naam en het wachtwoord van het Gebruikers2-account.
    
3. Nadat u zich hebt aangemeld, wordt u gevraagd het account in te stellen voor meer informatie. Klik op **Volgende**.
    
4. Ga als op de pagina **Aanvullende beveiligingsverificatie:**
    
   - Selecteer uw land of regio.
    
   - Typ het telefoonnummer van de smartphone die sms-berichten ontvangt.
    
   - Klik in **Methode**op **Mij een code**per sms sturen .
    
5. Klik op **Volgende**.
    
6. Voer de verificatiecode in van het sms-bericht dat op uw smartphone is ontvangen en klik op **Verifiëren**.
    
7. Houd op de **pagina Stap 3: Houd de** pagina van uw bestaande toepassingen op en noteer het weergegeven app-wachtwoord voor het gebruikers2-account op een veilige locatie en klik vervolgens op **Gereed**.
    
8. Als dit de eerste keer is dat u zich aanmeldde bij het Gebruikers 2-account, wordt u gevraagd het wachtwoord te wijzigen. Typ het oorspronkelijke wachtwoord en een nieuw wachtwoord twee keer en klik op **Wachtwoord bijwerken en meld u aan.** Neem het nieuwe wachtwoord op een veilige locatie op.
    
    U ziet de Office-portal voor gebruiker 2 op het tabblad **Microsoft Office Start** van uw browser.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: Meervoudige verificatie inschakelen en testen met een beleid voor voorwaardelijke toegang

*Deze fase kan alleen worden gebruikt voor een Microsoft 365 Enterprise-testomgeving.*

In deze fase schakelt u multi-factor authenticatie in voor het Gebruikers 3-account met behulp van een groep en een beleid voor voorwaardelijke toegang.

Maak vervolgens een nieuwe groep met de naam MFAUsers en voeg er het Gebruikers 3-account aan toe.

1. Klik op het tabblad **Microsoft 365-beheercentrum** op **Groepen** in de linkernavigatie en klik vervolgens op **Groepen**.
2. Klik op **Een groep toevoegen**.
3. Selecteer **Beveiliging**in het deelvenster **Een groepstype kiezen** en klik vervolgens op **Volgende**.
4. Klik in het deelvenster **Basisinstellingen** op **Groep maken**en klik vervolgens op **Sluiten**.
5. Typ **MFAUsers**in het **deelvenster Controleren en voltooien** en klik vervolgens op **Volgende**.
6. Klik in de lijst met groepen op de groep **MFAUsers.**
7. Klik in het deelvenster **MFAUsers** op **Leden**en klik vervolgens op **Alle weergeven en leden beheren**.
8. Klik in het deelvenster **MFAUsers** op **Leden toevoegen,** selecteer het **gebruikers3-account** en klik vervolgens op **Opslaan > sluiten > sluiten**.

Maak vervolgens een beleid voor voorwaardelijke toegang om multifactorauthenticatie te vereisen voor leden van de MFAUsers-groep.

1. Ga in een nieuw tabblad [https://portal.azure.com](https://portal.azure.com)van uw browser naar .
2. Klik **op Azure Active Directory > Beveiliging > voorwaardelijke toegang**.
3. Klik in het deelvenster **Voorwaardelijke toegang – Beleid** op Nieuw **beleid**.
4. Typ MFA in het deelvenster **Nieuw** **voor gebruikersaccounts** in **Naam**.
5. Klik in de sectie **Toewijzingen** op **Gebruikers en groepen**.
6. Klik op het tabblad **Opnemen** van het deelvenster **Gebruikers en groepen** op Gebruikers selecteren en groepen > gebruikers en groepen > **Selecteren**.
7. Klik in het deelvenster **Selecteren** op de groep **MFAUsers** en klik vervolgens op **Selecteren > gedaan**.
8. Klik in het gedeelte **Besturingselementen voor toegang** in het deelvenster **Nieuw** op **Grant**.
9. Klik in het deelvenster **Subsidie** op **Meervoudige verificatie vereisen**en klik vervolgens op **Selecteren**.
10. Klik in het deelvenster **Nieuw** op **Aan** voor **Beleid inschakelen**en klik vervolgens op **Maken**.
11. Sluit de tabbladen **Azure-portal** en **Microsoft 365-beheercentrum.**

Als u dit beleid wilt testen, meldt u zich af en meldt u zich af met het Account 3 van gebruiker. U moet worden gevraagd mfa te configureren. Dit toont aan dat het MFAUsers-beleid wordt toegepast.

Zie de stap [Multi-factor authenticatie instellen](identity-secure-user-sign-ins.md#identity-mfa) in de identiteitsfase voor informatie en koppelingen om multi-factor authenticatie in productie te implementeren.
    
## <a name="next-step"></a>Volgende stap

Ontdek extra [identiteitsfuncties](m365-enterprise-test-lab-guides.md#identity) en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Fase 2: Identiteit](identity-infrastructure.md)

[Microsoft 365 Enterprise Test Lab-handleidingen](m365-enterprise-test-lab-guides.md)

[Microsoft 365 Enterprise-implementatie](deploy-microsoft-365-enterprise.md)

[Microsoft 365 Enterprise-documentatie](https://docs.microsoft.com/microsoft-365-enterprise/)
