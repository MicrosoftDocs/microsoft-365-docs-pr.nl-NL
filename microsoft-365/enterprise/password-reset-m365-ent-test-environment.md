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
ms.openlocfilehash: 98e6b8d8432c86e9d1c432128ed6d223da83610e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 08/14/2020
ms.locfileid: "46686534"
---
# <a name="password-reset-for-your-microsoft-365-test-environment"></a>Opnieuw instellen van het wachtwoord voor uw Microsoft 365-testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Met de Azure Active Directory (Azure AD) selfservice voor het opnieuw instellen van wachtwoorden (SSPR) kunnen gebruikers hun wachtwoorden of accounts opnieuw instellen of ontgrendelen. 

In dit artikel wordt beschreven hoe u wachtwoordinstellingen in uw Microsoft 365-testomgeving in drie fasen kunt configureren en testen:

1.    Maak de testomgeving Microsoft 365 for Enterprise.
2.  Wachtwoord terugschrijven inschakelen.
3.    Configureer en test het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.
    
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Klik op [Hier](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) voor een visuele kaart voor alle artikelen in de stack van Microsoft 365 voor Enterprise-testlabrichtlijnen.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md). Dit is de resulterende configuratie.
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit: 
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een vereenvoudigd intranet van de organisatie verbonden met internet en bestaande uit de virtuele machines DC1, APP1 en CLIENT1 op een subnet van een virtueel Azure-netwerk. 
- Azure AD Connect draait op APP1 om het TESTLAD AD DS-domein (Active Directory Domain Services) te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-enable-password-writeback"></a>Fase 2: wachtwoord terugschrijven inschakelen.

Volg de instructies in [Fase 2 van testlabrichtlijn Wachtwoord terugschrijven](password-writeback-m365-ent-test-environment.md#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain).

Voor het gebruik van wachtwoordherstel moet u een wachtwoord voor terugschrijven inschakelen.
  
## <a name="phase-3-configure-and-test-password-reset"></a>Fase 3: opnieuw instellen van wachtwoorden configureren en testen

In deze fase configureert u het opnieuw instellen van wachtwoorden in de Azure AD-Tenant via groepslidmaatschap. Controleer vervolgens of dit werkt.

Schakel eerst het opnieuw instellen van het wachtwoord in voor de accounts in een specifieke groep van Azure AD.

1. Open [https://portal.azure.com](https://portal.azure.com)in een privévenster van uw browser en meld u aan met de referenties van uw globale beheerdersaccount.
2. Klik in de Azure-portal op **Azure Active Directory > Nieuwe groep**.
3. Stel het **groepstype** in op **beveiliging**, **groepsnaam** op **PWReset** en het **lidmaatschapstype** op **toegewezen**. 
4. Klik op **leden**, zoek en selecteer **gebruiker 3**, klik op **selecteren**en klik vervolgens op **maken**.
5. Sluit het **deelvenster** groepen.
6. Klik in het deelvenster Azure Active Directory op **opnieuw instellen van wachtwoorden** in de linkernavigatiebalk.
7. Kies in het deelvenster **wachtwoordherstel-eigenschappen** onder de optie **selfservice wachtwoord opnieuw instellen ingeschakeld****geselecteerd**.
8. Klik op **groep selecteren**, selecteer de groep **PWReset** en klik vervolgens op **selecteren > opslaan**.
9. Sluit het privévenster in uw browser.

Configureer en test vervolgens het opnieuw instellen van het wachtwoord voor het gebruikersaccount 3.

1. Open een nieuwe privévenster in uw browser en blader naar [https://aka.ms/ssprsetup](https://aka.ms/ssprsetup).
2. Meld u aan met de referenties van het account gebruikers 3.
3. Klik in **meer informatie vereist**op **volgende**. 
5. Stel bij **Verlies geen toegang tot uw account**, uw mobiele telefoonnummer in als verificatienummer en uw werk- of persoonlijke e-mailaccount als verificatie-e-mailadres.
7. Nadat beide zijn geverifieerd, klikt u op **Ziet er goed uit** en sluit u de privévenster van de browser.
8. Open een nieuw privévenster en blader naar [https://aka.ms/sspr](https://aka.ms/sspr).
9. Typ de accountnaam van gebruiker 3, typ de tekens uit de CAPTCHA en klik vervolgens op **volgende**.
10. Klik voor **verificatiestap 1** op **Naar mijn alternatieve e-mail e-mailen** en klik vervolgens **op E-mail**. Wanneer u het e-mailbericht ontvangt, typt u de verificatiecode en klikt u op **volgende**.
11. Typ in **Ga terug naar uw account** een nieuw wachtwoord voor het account van Gebruiker 3 en klik vervolgens op **voltooien**. Noteer het gewijzigde wachtwoord van het account van gebruiker 3 en bewaar het op een veilige locatie.
12. Ga op een afzonderlijk tabblad van dezelfde browser naar [https://portal.office.com](https://portal.office.com), en meld u vervolgens aan met de naam van het account voor gebruikers 3 en het nieuwe wachtwoord. U zou de pagina van **Microsoft Office voor Thuisgebruik** moeten zien.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)
