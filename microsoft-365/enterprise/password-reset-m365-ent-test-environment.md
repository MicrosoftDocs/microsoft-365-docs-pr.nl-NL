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
ms.openlocfilehash: 5d98dcc50f16bc08da787a928beeeacf825201c9
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487422"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Met de Azure Active Directory (Azure AD) selfservice voor het opnieuw instellen van wachtwoorden (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen.

In dit artikel wordt uitgelegd hoe u het opnieuw instellen van wachtwoorden kunt configureren en testen in uw Microsoft 365-testomgeving.

Het instellen van SSPR omvat drie fasen:
- [Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: wachtwoord terugschrijven inschakelen.](#phase-2-enable-password-writeback)
- [Fase 3: opnieuw instellen van wachtwoorden configureren en testen](#phase-3-configure-and-test-password-reset)
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md). 

De uiteindelijke configuratie ziet er als volgt uit:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit:
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.
- Azure AD Connect draait op APP1 om het TESTLAD AD DS-domein (Active Directory Domain Services) te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: wachtwoord terugschrijven inschakelen.

Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Voor het gebruik van wachtwoordherstel moet u een wachtwoord voor terugschrijven inschakelen.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: opnieuw instellen van wachtwoorden configureren en testen

In deze stap configureert u het opnieuw instellen van wachtwoorden in de Azure AD-Tenant via groepslidmaatschap en controleert u vervolgens of dit werkt.

Schakel eerst het opnieuw instellen van het wachtwoord in voor de accounts in een specifieke groep van Azure AD.

1. Open [https://portal.azure.com](https://portal.azure.com)in een privévenster van uw browser en meld u aan met de referenties van uw globale beheerdersaccount.
2. Selecteer in de Azure-Portal nieuwe groep **Azure Active Directory**-  >  **groepen**  >  **New group**.
3. Stel het **groepstype** in op **beveiliging**, **groepsnaam** op **PWReset** en het **lidmaatschapstype** op **toegewezen**.
4. Selecteer **leden**, zoek en selecteer **gebruiker 3**, selecteer **selecteren**en klik vervolgens op **maken**.
5. Sluit het **deelvenster** groepen.
6. Selecteer in het deelvenster Azure Active Directory de optie **wachtwoord opnieuw instellen** in het linker navigatiedeelvenster.
7. Kies in het deelvenster **wachtwoordherstel-eigenschappen** onder de optie **selfservice wachtwoord opnieuw instellen ingeschakeld****geselecteerd**.
8. Selecteer **groep selecteren**, selecteer de groep **PWReset** **en selecteer vervolgens**  >  **Opslaan**.
9. Sluit het privévenster in uw browser.

Test vervolgens wachtwoord opnieuw instellen voor het account van de gebruiker 3.

1. Open een nieuwe privévenster in uw browser en blader naar [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
1. Meld u aan met de referenties van het account gebruikers 3.
1. Selecteer **volgende**voor **meer informatie**. 
1. Stel bij **Verlies geen toegang tot uw account**, uw mobiele telefoonnummer in als verificatienummer en uw werk- of persoonlijke e-mailaccount als verificatie-e-mailadres.
1. Wanneer beide zijn gecontroleerd, selecteert u **goed uitzien**en sluit u vervolgens het persoonlijke exemplaar van de browser.
1. Ga in een nieuw exemplaar van de persoonlijke browser naar [https://aka.ms/sspr](https://aka.ms/sspr) .
1. Voer de naam in van de gebruikersnaam van het account, voer de tekens van de CAPTCHA in en selecteer **volgende**.
1. Selecteer voor **verificatie stap 1** **e-mail mijn alternatieve e-mail verzenden**en selecteer vervolgens **e-mail**. Wanneer u het e-mailbericht ontvangt, voert u de verificatiecode in en selecteert u **volgende**.
1. Voer het nieuwe wachtwoord in voor het account van de gebruiker 3 en selecteer **Voltooien**in **uw account weer**geven. Noteer het gewijzigde wachtwoord van het account van gebruiker 3 en bewaar het op een veilige locatie.
1. Ga op een afzonderlijk tabblad van dezelfde browser naar [https://portal.office.com](https://portal.office.com), en meld u vervolgens aan met de naam van het account voor gebruikers 3 en het nieuwe wachtwoord. U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
