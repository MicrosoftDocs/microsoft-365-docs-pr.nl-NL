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
ms.openlocfilehash: 4ed50d37e0f4e73d5d1fc62e295df374c61b9786
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686272"
---
# <a name="multi-factor-authentication-for-your-microsoft-365-for-enterprise-test-environment"></a>Meervoudige verificatie voor uw Microsoft 365 voor Enterprise testomgeving

*U kunt deze test lab-handleiding gebruiken voor zowel Microsoft 365 voor Enterprise als Office 365 Enterprise test omgevingen.*

Voor een extra beveiligingsniveau voor het aanmelden bij Microsoft 365 of een willekeurige service of toepassing die de Azure AD-Tenant voor uw abonnement gebruikt, kunt u gebruikmaken van Azure multi-factor Authentication, waarvoor meer dan alleen een gebruikersnaam en wachtwoord voor de verificatie van een account is vereist. 

Met authenticatie via meerdere factoren zijn gebruikers verplicht een telefoongesprek te erkennen, typt u een verificatiecode die u in een SMS-bericht ontvangt, of controleert u de verificatie met een app op de smartphone nadat de juiste wachtwoorden zijn ingevoerd. Ze kunnen zich alleen aanmelden nadat aan deze tweede verificatie factor is voldaan. 
  
In dit artikel wordt beschreven hoe u op tekst gebaseerde verificatie voor een specifiek gebruikersaccount kunt inschakelen en testen.
  
Er zijn twee fasen voor het instellen van meervoudige verificatie voor een account in uw Microsoft 365 voor Enterprise testomgeving:
  
1. Maak de testomgeving Microsoft 365 for Enterprise.
    
2. Verificatie in meerdere factoren inschakelen en testen voor het account van de gebruiker 2.

3. Meervoudige verificatie inschakelen en testen met een voorwaardelijk toegangsbeleid (optioneel).

![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar de proefversie van de [test lab](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de microsoft 365 voor Enterprise test lab Guide.
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a>Fase 1: uw Microsoft 365-omgeving voor Enterprise testomgeving maken

Als u de verificatie met meerdere factoren op een lichte manier wilt testen met de minimumvereisten, volgt u de instructies in de [Lightweight Base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).
  
Als u multi-factor Authentication wilt testen in een gesimuleerde onderneming, volgt u de instructies in [Pass-Through-verificatie](pass-through-auth-m365-ent-test-environment.md).
  
> [!NOTE]
> Bij het testen van meervoudige verificatie is de gesimuleerde Enterprise testomgeving niet vereist, dat een gesimuleerd intranet bevat dat verbonden is met internet en adreslijstsynchronisatie van een Active Directory Domain Services (AD DS)-forest. U kunt dit als optie gebruiken, zodat u meervoudige verificatie kunt testen en een proef kunt uitvoeren in een omgeving die een typische organisatie voorstelt. 
  
## <a name="phase-2-enable-and-test-multi-factor-authentication-for-the-user-2-account"></a>Fase 2: meervoudige verificatie inschakelen en testen voor de account van de gebruiker 2

Schakel meervoudige verificatie in voor de gebruiker 2-account door deze stappen uit te voeren:
  
1. Open een afzonderlijke, persoonlijke versie van uw browser, ga naar het Microsoft 365-Beheercentrum ( [https://portal.microsoft.com](https://portal.microsoft.com) ) en meld u aan met uw globale beheerdersaccount.
    
2. Selecteer **Gebruikers > Actieve gebruikers** op de linkernavigatiebalk.
    
3. Klik in het deelvenster actieve gebruikers op **multi-factor Authentication**.
    
4. Selecteer in de lijst de account **gebruiker 2** .
    
5. Klik in de sectie **gebruiker 2** onder **snelle stappen**op **inschakelen**.
    
6. Klik in het dialoogvenster **multi-factor Authentication** inschakelen op **multi-factor Authentication inschakelen**.
    
7. Klik in het dialoogvenster **updates voltooid** op **sluiten**.
    
8. Ga naar het tabblad **Microsoft 365-Beheercentrum** , klik in de rechterbovenhoek op het pictogram van het gebruikersaccount en klik vervolgens op **Afmelden**.
    
9. Sluit uw browser exemplaar.
   
Voltooi de configuratie van de gebruiker 2-account om een tekstbericht te valideren en te testen met behulp van de volgende stappen:
  
1. Open een nieuwe, persoonlijke instantie van uw browser.
    
2. Ga naar het [Microsoft 365-Beheercentrum](https://admin.microsoft.com) en meld u aan met de accountnaam en het wachtwoord van de gebruiker.
    
3. Nadat u zich hebt aangemeld, wordt u gevraagd of u het account wilt instellen voor meer informatie. Klik op **Volgende**.
    
4. Op de pagina **extra beveiligingsverificatie** :
    
   - Selecteer uw land of regio.
    
   - Typ het telefoonnummer van de smartphone waarop SMS-berichten worden ontvangen.
    
   - Klik bij **methode**op **code per SMS-bericht verzenden**.
    
5. Klik op **Volgende**.
    
6. Voer de verificatiecode in van het SMS-bericht dat op uw smartphone is ontvangen en klik op **verifiëren**.
    
7. Klik op de pagina **stap 3: de bestaande toepassingen bewaren** op **gereed**.
    
8. Als dit de eerste keer is dat u zich aanmeldt met het account van de gebruiker 2, wordt u gevraagd het wachtwoord te wijzigen. Typ tweemaal het oorspronkelijke wachtwoord en een nieuw wachtwoord en klik vervolgens op **wachtwoord bijwerken en meld u aan**. Neem het nieuwe wachtwoord op een veilige locatie op.
    
    U ziet nu de Office-portal voor gebruiker 2 op het tabblad **Start van Microsoft Office** in uw browser.

## <a name="phase-3-enable-and-test-multi-factor-authentication-with-a-conditional-access-policy"></a>Fase 3: multi-factor Authentication inschakelen en testen met een voorwaardelijk toegangsbeleid

*Deze fase kan alleen worden gebruikt voor een testomgeving van Microsoft 365 voor bedrijven.*

In deze fase schakelt u meervoudige verificatie in voor het account van de gebruiker 3 met behulp van een groep en een beleid voor voorwaardelijke toegang.

Vervolgens maakt u een nieuwe groep met de naam MFAUsers en voegt u de gebruikers 3-account toe aan de groep.

1. Ga naar het tabblad **Microsoft 365-Beheercentrum** , klik in het linker navigatiemenu op **groepen** en klik vervolgens op **groepen**.
2. Klik op **groep toevoegen**.
3. Selecteer in het deelvenster **een groepstype kiezen** de optie **beveiliging**en klik vervolgens op **volgende**.
4. Klik in het deelvenster **basisbeginselen instellen** op **groep maken**en klik vervolgens op **sluiten**.
5. In het deelvenster **groep controleren en voltooien** , typt u **MFAUsers**en klikt u op **volgende**.
6. Klik in de lijst met groepen op de groep **MFAUsers** .
7. Klik in het deelvenster **MFAUsers** op **leden**en klik op **AllesWeergeven en leden beheren**.
8. Klik in het deelvenster **MFAUsers** op **leden toevoegen**, selecteer het account van de **gebruiker 3** en klik op **Opslaan > sluiten > sluiten**.

Vervolgens maakt u een voorwaardelijk toegangsbeleid voor de verificatie van meervoudige authenticatie voor leden van de groep MFAUsers.

1. Ga op een nieuw tabblad van uw browser naar [https://portal.azure.com](https://portal.azure.com) .
2. Klik **> beveiligings > voorwaardelijke toegang op Azure Active Directory**.
3. Klik in het deelvenster **voorwaardelijke toegang – beleidsregels** op **Nieuw beleid**.
4. Typ MFA in het **nieuwe** deelvenster in **naam** **van gebruikersaccounts** .
5. Klik in de sectie **opdrachten** op **gebruikers en groepen**.
6. Klik op het tabblad **opnemen** van het deelvenster **gebruikers en groepen** op **gebruikers en groepen > gebruikers en groepen selecteren > selecteren**.
7. Klik in het **selectie** deelvenster op de groep **MFAUsers** en klik vervolgens op **selecteren > gereed**.
8. Klik in de sectie **Access-besturingselementen** van het **nieuwe** deelvenster op **toewijzen**.
9. Klik in het deelvenster **verlenen** op **Meervoudige verificatie vereisen**en klik vervolgens op **selecteren**.
10. Klik in het **nieuwe** deelvenster op **aan** voor inschakelen van het **beleid**en klik vervolgens op **maken**.
11. Sluit de tabbladen **Azure Portal** en **Microsoft 365-Beheercentrum** .

Als u dit beleid wilt testen, meldt u zich af en meldt u zich aan met het account van de gebruiker 3. U wordt gevraagd MFA te configureren. Dit demonstreert het toepassen van het MFAUsers-beleid.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Identiteitskaart](identity-roadmap-microsoft-365.md)

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
