---
title: Microsoft 365 voor ondernemingstestomgeving meervoudige verificatie
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
- seo-marvel-apr2020
description: Configureer meervoudige verificatie met tekstberichten die zijn verzonden naar een smartphone in uw Microsoft 365 voor bedrijfstestomgeving.
ms.openlocfilehash: aeb8940a9499909b8c568d1230f9aa45aee07b3d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923754"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Meervoudige verificatie voor uw Microsoft 365 voor bedrijfstestomgeving

*Deze testlaborator kan worden gebruikt voor zowel Microsoft 365 voor bedrijven als Office 365 Enterprise testomgevingen.*

Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een service of toepassing die gebruikmaakt van de Azure AD-tenant voor uw abonnement, kunt u Meervoudige verificatie van Azure AD inschakelen, waarvoor meer dan alleen een gebruikersnaam en wachtwoord nodig zijn om een account te verifiëren.

Bij meervoudige verificatie moeten gebruikers een telefoongesprek bevestigen, een verificatiecode typen die in een sms-bericht is verzonden of de verificatie verifiëren met een app op hun smartphone nadat ze hun wachtwoorden correct hebben invoeren. Ze kunnen zich alleen aanmelden nadat deze tweede verificatiefactor is voldaan.
  
In dit artikel wordt beschreven hoe u verificatie op basis van tekstberichten in- en test voor een specifiek gebruikersaccount.
  
Het instellen van meervoudige verificatie voor een account in uw Microsoft 365 voor ondernemingstestomgeving omvat twee fasen en een derde optionele fase:
- [Fase 1: uw Microsoft 365 voor bedrijfstestomgeving](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: Meervoudige verificatie in- en testen voor het Gebruikers 2-account](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: Meervoudige verificatie inschakelen en testen met een beleid voor voorwaardelijke toegang](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Voor een visuele kaart van alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide stack, gaat u naar Microsoft 365 voor [enterprise Test Lab Guide Stack.](../downloads/Microsoft365EnterpriseTLGStack.pdf)
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365 voor bedrijfstestomgeving

Als u alleen meervoudige verificatie op een lichtgewicht manier wilt testen met de minimumvereisten, volgt u de instructies in [de lichtgewicht basisconfiguratie.](lightweight-base-configuration-microsoft-365-enterprise.md)
  
Als u meervoudige verificatie wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-through-verificatie.](pass-through-auth-m365-ent-test-environment.md)
  
> [!NOTE]
> Voor het testen van meervoudige verificatie is geen gesimuleerde bedrijfstestomgeving vereist, waaronder een gesimuleerd intranet dat is verbonden met internet en adreslijstsynchronisatie voor een AD DS-forest (Active Directory Domain Services). Het is hier beschikbaar als een optie, zodat u meervoudige verificatie kunt testen en erop kunt experimenteren in een omgeving die een normale organisatie vertegenwoordigt.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: Meervoudige verificatie in- en testen voor het Gebruikers 2-account

Schakel meervoudige verificatie in voor het Gebruikers 2-account met de volgende stappen:
  
1. Open een afzonderlijk, privé-exemplaar van uw browser, ga naar het Microsoft 365 beheercentrum ( ) en meld u aan [https://portal.microsoft.com](https://portal.microsoft.com) met uw globale beheerdersaccount.
    
2. Selecteer in de linkernavigatie de optie **Gebruikers**  >  **Actieve gebruikers.**
    
3. Selecteer in het deelvenster Actieve gebruikers de optie **Meervoudige verificatie**.
    
4. Selecteer in de lijst het **account Gebruiker 2.**
    
5. Selecteer in de sectie Gebruiker **2** onder **Snelle stappen** de optie **Inschakelen.**
    
6. Selecteer in het dialoogvenster Over het inschakelen van **multi-factor auth** de optie **Multi-factor auth inschakelen.**
    
7. Selecteer sluiten **in het** dialoogvenster Updates **succesvol.**
    
8. Selecteer op **Microsoft 365 tabblad Beheercentrum** het pictogram gebruikersaccount in de rechterbovenhoek en selecteer **vervolgens Uitloggen.**
    
9. Sluit het browserexe instance.
   
Voltooi de configuratie voor het Gebruikers 2-account om een tekstbericht te gebruiken voor validatie en test dit met de volgende stappen:
  
1. Open een nieuw, privé-exemplaar van uw browser.
    
2. Ga naar het [Microsoft 365 beheercentrum](https://admin.microsoft.com) en meld u aan met de accountnaam en het wachtwoord van gebruiker 2.
    
3. Nadat u zich hebt aanmelden, wordt u gevraagd het account in te stellen voor meer informatie. Selecteer **Volgende**.
    
4. Op de **pagina Extra beveiligingsverificatie:**
    
   - Selecteer uw land of regio.
    
   - Voer het telefoonnummer in van de smartphone die sms-berichten ontvangt.
    
   - Selecteer **in Methode** de optie Een code per sms **verzenden.**
    
5. Selecteer **Volgende**.
    
6. Voer de verificatiecode in van het sms-bericht dat u op uw smartphone hebt ontvangen en selecteer **controleren.**
    
7. Selecteer op **de pagina Stap 3: Uw bestaande toepassingen** behouden de optie **Klaar.**
    
8. Als dit de eerste keer is dat u zich hebt aangemeld met het account Gebruiker 2, wordt u gevraagd het wachtwoord te wijzigen. Voer tweemaal het oorspronkelijke wachtwoord en een nieuw wachtwoord in en selecteer **vervolgens Wachtwoord bijwerken en meld u aan.** Neem het nieuwe wachtwoord op een veilige locatie op.
    
    U ziet de Office portal voor gebruiker 2 op Microsoft Office **tabblad Start** van uw browser.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: Meervoudige verificatie inschakelen en testen met een beleid voor voorwaardelijke toegang

*Deze fase kan alleen worden gebruikt voor een Microsoft 365 voor ondernemingstestomgeving.*

In deze fase kunt u meervoudige verificatie voor het Gebruikers 3-account inschakelen met behulp van een groep en een beleid voor voorwaardelijke toegang.

Maak vervolgens een nieuwe groep met de naam MFAUsers en voeg het account Gebruiker 3 hieraan toe.

1. Selecteer op **Microsoft 365 tabblad Beheercentrum** de optie **Groepen** in de linkernavigatie en selecteer **vervolgens Groepen**.
2. Selecteer **Een groep toevoegen.**
3. Selecteer in **het deelvenster Een groeptype** kiezen de optie **Beveiliging** en selecteer vervolgens **Volgende.**
4. Selecteer in **het deelvenster De basisbeginselen** instellen de optie Groep **maken** en selecteer vervolgens **Sluiten.**
5. Voer in **het deelvenster Controleren en** voltooien groep toevoegen **MFAUsers** in en selecteer **volgende**.
6. Selecteer in de lijst met groepen de **groep MFAUsers.**
7. Selecteer leden in het deelvenster **MFAUsers** **en** selecteer vervolgens Alle leden weergeven **en beheren.**
8. Selecteer leden toevoegen in het deelvenster **MFAUsers,** selecteer het account **Gebruiker 3** en selecteer **sluiten**  >  **sluiten**  >  **opslaan.**

Maak vervolgens een beleid voor voorwaardelijke toegang om meervoudige verificatie voor leden van de groep MFAUsers te vereisen.

1. Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .
2. Selecteer **Azure Active Directory**  >    >  **Voorwaardelijke toegang voor beveiliging**.
3. Selecteer in **het deelvenster Voorwaardelijke** toegang – Beleid de optie **Nieuw beleid.**
4. Typ in **het** deelvenster Nieuw **MFA voor gebruikersaccounts** in **het vak Naam.**
5. Selecteer gebruikers en groepen in **de** sectie **Opdrachten.**
6. Selecteer op **het** tabblad Opnemen van het deelvenster Gebruikers **en groepen** de optie Gebruikers en **groepen** selecteren Gebruikers  >  **en groepen**  >  **Selecteren**.
7. Selecteer in **het** deelvenster Selecteren de **groep MFAUsers** en selecteer **vervolgens Done**  >  **selecteren.**
8. Selecteer in **de sectie Besturingselementen** van Access **van het** deelvenster Nieuw de optie **Grant**.
9. Selecteer in **het** deelvenster Verlenen de optie **Meervoudige verificatie vereisen** en selecteer vervolgens **Selecteren**.
10. Selecteer in **het** deelvenster Nieuw **de optie Aan** voor Beleid **inschakelen** en selecteer vervolgens **Maken.**
11. Sluit de **Azure-portal** en **Microsoft 365 tabbladen van het** beheercentrum.

Als u dit beleid wilt testen, meld u zich af en meld u aan met het account Gebruiker 3. U moet worden gevraagd om MFA te configureren. Dit toont aan dat het MFAUsers-beleid wordt toegepast.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Routekaart voor identiteit](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)