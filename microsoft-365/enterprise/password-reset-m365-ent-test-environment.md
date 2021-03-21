---
title: Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/13/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 'Samenvatting: configureer en test het opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: efcaaf9ed1873c0908bb0e64644b8e10de280a01
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921490"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving

*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*

Met de Azure Active Directory (Azure AD) selfservice voor het opnieuw instellen van wachtwoorden (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen.

In dit artikel wordt beschreven hoe u wachtwoordinstellingen configureert en test in uw Microsoft 365-testomgeving.

Het instellen van SSPR bestaat uit drie fasen:
- [Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: wachtwoord terugschrijven inschakelen.](#phase-2-enable-password-writeback)
- [Fase 3: opnieuw instellen van wachtwoorden configureren en testen](#phase-3-configure-and-test-password-reset)
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md). 

De resulterende configuratie ziet er als volgende uit:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit:
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.
- Azure AD Connect draait op APP1 om het TESTLAD AD DS-domein (Active Directory Domain Services) te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: wachtwoord terugschrijven inschakelen.

Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Voor het gebruik van wachtwoordherstel moet u een wachtwoord voor terugschrijven inschakelen.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: opnieuw instellen van wachtwoorden configureren en testen

Configureer in deze fase het opnieuw instellen van wachtwoorden in de Azure AD-tenant via groepslidmaatschap en controleer vervolgens of het werkt.

Schakel eerst het opnieuw instellen van het wachtwoord in voor de accounts in een specifieke groep van Azure AD.

1. Open [https://portal.azure.com](https://portal.azure.com)in een privévenster van uw browser en meld u aan met de referenties van uw globale beheerdersaccount.
2. Selecteer in de Azure-portal **de optie Nieuwe groep Azure Active Directory**  >  **Groups**  >  **New**.
3. Stel het **groepstype** in op **beveiliging**, **groepsnaam** op **PWReset** en het **lidmaatschapstype** op **toegewezen**.
4. Selecteer **Leden,** zoek en selecteer **Gebruiker 3,** **selecteer Selecteren** en selecteer vervolgens **Maken.**
5. Sluit het **deelvenster** groepen.
6. Selecteer in het deelvenster Azure Active Directory de optie **Wachtwoord opnieuw instellen** in de linkernavigatie.
7. Kies in het deelvenster **wachtwoordherstel-eigenschappen** onder de optie **selfservice wachtwoord opnieuw instellen ingeschakeld****geselecteerd**.
8. Selecteer **Groep selecteren,** selecteer de **groep PWReset** en selecteer **vervolgens Opslaan**  >  **selecteren.**
9. Sluit het privévenster in uw browser.

Test vervolgens het opnieuw instellen van het wachtwoord voor het account Gebruiker 3.

1. Open een nieuwe privévenster in uw browser en blader naar [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Meld u aan met de referenties van het account gebruikers 3.
1. Selecteer **Volgende in Meer informatie** **vereist.** 
1. Stel bij **Verlies geen toegang tot uw account**, uw mobiele telefoonnummer in als verificatienummer en uw werk- of persoonlijke e-mailaccount als verificatie-e-mailadres.
1. Nadat beide zijn geverifieerd, **selecteert** u Ziet er goed uit en sluit u het privé-exemplaar van de browser.
1. Ga in een nieuw privébrowser-exemplaar naar [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Voer de accountnaam gebruiker 3 in, voer de tekens in de CAPTCHA in en selecteer **Volgende**.
1. Voor **verificatie stap 1** selecteert u **Mijn alternatieve e-mail** en selecteert u vervolgens **E-mail**. Wanneer u de e-mail ontvangt, voert u de verificatiecode in en selecteert u **Volgende.**
1. Voer **in Terug naar uw account** een nieuw wachtwoord in voor het Gebruikers 3-account en selecteer **Voltooien.** Noteer het gewijzigde wachtwoord van het account van gebruiker 3 en bewaar het op een veilige locatie.
1. Ga op een afzonderlijk tabblad van dezelfde browser naar [https://portal.office.com](https://portal.office.com), en meld u vervolgens aan met de naam van het account voor gebruikers 3 en het nieuwe wachtwoord. U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)