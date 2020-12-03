---
title: Multi-factor Authentication voor Microsoft 365 voor Enterprise testomgeving
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
description: Configureer multi-factor Authentication met behulp van SMS-berichten die zijn verzonden naar een smartphone in uw Microsoft 365 voor Enterprise test environment.
ms.openlocfilehash: 4c59405c1ce59cafaf0309e2314e5cbfa4eb080a
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558440"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Meervoudige verificatie voor uw Microsoft 365 voor Enterprise testomgeving

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een willekeurige service of toepassing die de Azure AD-Tenant voor uw abonnement gebruikt, kunt u de multi-factor Authentication van Azure AD inschakelen, waarvoor meer dan alleen een gebruikersnaam en wachtwoord vereist zijn

Met authenticatie via meerdere factoren zijn gebruikers verplicht een telefoongesprek te erkennen, typt u een verificatiecode die u in een SMS-bericht ontvangt, of controleert u de verificatie met een app op de smartphone nadat de juiste wachtwoorden zijn ingevoerd. Ze kunnen zich alleen aanmelden nadat aan deze tweede verificatie factor is voldaan.
  
In dit artikel wordt beschreven hoe u op tekst gebaseerde verificatie voor een specifiek gebruikersaccount kunt inschakelen en testen.
  
Het instellen van multi-factor Authentication voor een account in uw Microsoft 365 voor Enterprise-testomgeving bestaat uit twee fasen en een derde optionele fase:
- [Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [Fase 2: meervoudige verificatie inschakelen en testen voor de account van de gebruiker 2](#phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account)
- [Fase 3: multi-factor Authentication inschakelen en testen met een voorwaardelijk toegangsbeleid](#phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy)

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u de verificatie met meerdere factoren op een lichte manier wilt testen met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u multi-factor Authentication wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Bij het testen van meervoudige verificatie is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit als optie gebruiken, zodat u meervoudige verificatie kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt.
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: meervoudige verificatie inschakelen en testen voor de account van de gebruiker 2

Schakel meervoudige verificatie in voor de gebruiker 2-account door deze stappen uit te voeren:
  
1. Open een afzonderlijke, persoonlijke versie van uw browser, ga naar het Microsoft 365-Beheercentrum ( [https://portal.microsoft.com](https://portal.microsoft.com) ) en meld u aan met uw globale beheerdersaccount.
    
2. Selecteer **gebruikers**  >  **actieve gebruikers** in het linker navigatie.
    
3. Selecteer in het deelvenster actieve gebruikers **Meervoudige verificatie**.
    
4. Selecteer in de lijst de account **gebruiker 2** .
    
5. Selecteer in de sectie **User 2** onder **snelle stappen** de optie **inschakelen**.
    
6. Selecteer in het dialoogvenster **voor het inschakelen van multi-factor Authentication** de optie **multi-factor Authentication inschakelen**.
    
7. Selecteer **sluiten** in het dialoogvenster **updates voltooid** .
    
8. Selecteer op het tabblad **Microsoft 365-Beheercentrum** het pictogram voor het gebruikersaccount in de rechterbovenhoek en selecteer **Afmelden**.
    
9. Sluit uw browser exemplaar.
   
Voltooi de configuratie van de gebruiker 2-account om een tekstbericht te valideren en te testen met behulp van de volgende stappen:
  
1. Open een nieuwe, persoonlijke instantie van uw browser.
    
2. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) en meld u aan met de accountnaam en het wachtwoord van de gebruiker.
    
3. Nadat u zich hebt aangemeld, wordt u gevraagd of u het account wilt instellen voor meer informatie. Selecteer **Volgende**.
    
4. Op de pagina **extra beveiligingsverificatie** :
    
   - Selecteer uw land of regio.
    
   - Voer het telefoonnummer in van de smartphone waarop SMS-berichten worden ontvangen.
    
   - Selecteer bij **methode** **een code per SMS-bericht verzenden**.
    
5. Selecteer **Volgende**.
    
6. Voer de verificatiecode in van het SMS-bericht dat op uw smartphone is ontvangen en selecteer vervolgens **verifiëren**.
    
7. Selecteer **gereed** op de pagina **stap 3: de bestaande toepassingen bewaren** .
    
8. Als dit de eerste keer is dat u zich aanmeldt met het account van de gebruiker 2, wordt u gevraagd het wachtwoord te wijzigen. Voer het oorspronkelijke wachtwoord en een nieuw wachtwoord twee keer in en selecteer vervolgens **wachtwoord bijwerken en meld u aan**. Neem het nieuwe wachtwoord op een veilige locatie op.
    
    U ziet nu de Office-portal voor gebruiker 2 op het tabblad **Start van Microsoft Office** in uw browser.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: multi-factor Authentication inschakelen en testen met een voorwaardelijk toegangsbeleid

*Deze fase kan alleen worden gebruikt voor een testomgeving van Microsoft 365 voor bedrijven.*

In deze fase schakelt u meervoudige verificatie in voor het account van de gebruiker 3 met behulp van een groep en een beleid voor voorwaardelijke toegang.

Vervolgens maakt u een nieuwe groep met de naam MFAUsers en voegt u de gebruikers 3-account toe aan de groep.

1. Ga naar het tabblad **Microsoft 365-Beheercentrum** , selecteer **groepen** in het linker navigatieonderdeel en selecteer **groepen**.
2. Selecteer **een groep toevoegen**.
3. Selecteer in het deelvenster **een groepstype kiezen** de optie **beveiliging** en selecteer vervolgens **volgende**.
4. Selecteer **groep maken** in het deelvenster **basisbeginselen instellen** en selecteer vervolgens **sluiten**.
5. Voer in het deelvenster **groep toevoegen en voltooien** **MFAUsers** in en selecteer vervolgens **volgende**.
6. Selecteer in de lijst met groepen de groep **MFAUsers** .
7. Selecteer **leden** in het **MFAUsers** -deelvenster en selecteer vervolgens **AllesWeergeven en leden beheren**.
8. Selecteer **leden toevoegen** in het deelvenster **MFAUsers** , selecteer het account van de **gebruiker 3** **en selecteer vervolgens sluiten**  >  **sluiten**  >  **Close**.

Vervolgens maakt u een voorwaardelijk toegangsbeleid voor de verificatie van meervoudige authenticatie voor leden van de groep MFAUsers.

1. Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .
2. Selecteer voorwaardelijke toegang van **Azure Active Directory**-  >  **beveiliging**  >  **Conditional Access**.
3. Selecteer in het deelvenster **voorwaardelijke toegang – beleidsregels** de optie **nieuwe beleids** optie.
4. Voer in het **nieuwe** deelvenster **MFA in voor gebruikersaccounts** in het vak **naam** .
5. Selecteer in de sectie **opdrachten** de optie **gebruikers en groepen**.
6. Selecteer op het tabblad **opnemen** van het deelvenster **gebruikers en groepen** de optie **gebruikers en groepen**  >  **gebruikers en groepen**  >  **selecteren**.
7. In het **selectie** deelvenster selecteert u de groep **MFAUsers** **en selecteert u** vervolgens  >  **gereed**.
8. Selecteer in de sectie **Access-besturingselementen** van het **nieuwe** deelvenster de optie **verlenen**.
9. Selecteer in het deelvenster **verlenen** de optie **Meervoudige verificatie vereisen** en selecteer vervolgens **selecteren**.
10. Selecteer **in het** deelvenster **Nieuw** de optie inschakelen voor **beleidsinstelling** en selecteer **maken**.
11. Sluit de tabbladen **Azure Portal** en **Microsoft 365-Beheercentrum** .

Als u dit beleid wilt testen, meldt u zich af en meldt u zich aan met het account van de gebruiker 3. U wordt gevraagd MFA te configureren. Dit demonstreert het toepassen van het MFAUsers-beleid.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
