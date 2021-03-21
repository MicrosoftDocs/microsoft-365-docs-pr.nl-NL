---
title: Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
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
description: 'Overzicht: Wachtwoord terugschrijven configureren voor uw Microsoft 365-testomgeving.'
ms.openlocfilehash: f1118c22ad1f65ea29bb14afacb7506a60d1fe1a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921478"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving

*Deze testlaborator kan alleen worden gebruikt voor Microsoft 365 voor testomgevingen voor ondernemingen.*

Gebruikers kunnen wachtwoord writeback gebruiken om hun wachtwoorden bij te werken via Azure Active Directory (Azure AD), dat vervolgens wordt gerepliceerd naar uw lokale Active Directory Domain Services (AD DS). Met wachtwoordschrijven hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS waar hun oorspronkelijke gebruikersaccounts zijn opgeslagen. Dit helpt roaming- of externe gebruikers die geen externe toegang hebben tot hun on-premises netwerk.

In dit artikel wordt beschreven hoe u uw Microsoft 365-testomgeving configureert voor het terugschrijven van wachtwoorden.

Het configureren van uw testomgeving voor het terugschrijven van wachtwoorden omvat twee fasen:
- [Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for enterprise Test Lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)Stack voor een visuele kaart voor alle artikelen in de Microsoft 365 voor enterprise Test Lab Guide Stack.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md). De resulterende configuratie ziet er als volgende uit:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit:
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.
- Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.

Configureer eerst het account gebruiker 1 met de rol globale beheerder.

1. Meld u aan in het [Microsoft 365-beheercentrum](https://portal.microsoft.com) met uw globale beheerdersaccount.

2. Selecteer **Actieve gebruikers.**
 
3. Selecteer op **de pagina** Actieve gebruikers het **gebruikers1-account,**

4. Selecteer bewerken naast **Rollen** in **het deelvenster gebruiker1.** 

5. Selecteer in **het deelvenster Gebruikersrollen bewerken** voor gebruiker1 de optie Globale **beheerder,** selecteer **Opslaan** en selecteer **vervolgens Sluiten.**

Configureer vervolgens het account gebruiker 1 met de beveiligingsinstellingen waarmee wachtwoorden kunnen worden gewijzigd namens andere gebruikers in het domein TESTLAB AD DS.

1. Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.

2. Selecteer op het bureaublad van APP1 **Start,** voer **actief in** en selecteer **vervolgens Active Directory-gebruikers en -computers.**

3. Selecteer weergeven op de **menubalk.** Als **Geavanceerde functies** niet zijn ingeschakeld, selecteert u deze om deze in te stellen.

4. Selecteer in het deelvenster Structuur uw domein en houd deze ingedrukt (of klik erop met de rechtermuisknop), selecteer **Eigenschappen** en selecteer vervolgens het **tabblad** Beveiliging.

5. Selecteer **Geavanceerd.**

6. Selecteer op **het tabblad** Machtigingen de optie **Toevoegen.**

7. Selecteer **Selecteer een principal,** voer **Gebruiker1** in en selecteer **OK.**

8. Selecteer in **Van toepassing op**, **Onderliggende gebruikersobjecten**.

9. Selecteer onder **Machtigingen** het volgende:

    - **Wachtwoord wijzigen**
    - **Wachtwoord opnieuw instellen**

10. Selecteer onder **Eigenschappen** het volgende:
    - **LockoutTime schrijven**
    - **pwdLastSet schrijven**

11. Selecteer **OK** drie keer om de wijzigingen op te slaan.

12. Sluit **Active Directory-gebruikers en -computers**.

Configureer vervolgens Azure AD Connect op APP1 voor Wachtwoord terugschrijven.

1. Verbind indien nodig APP1 met het account TESTLAB\Gebruiker1.

2. Dubbelklik op het bureaublad van APP1 op **Azure AD Connect**.

3. Selecteer **configureren op de** **welkomstpagina.**

4. Selecteer op **de pagina** Extra taken de **optie Synchronisatieopties aanpassen** en selecteer vervolgens **Volgende.**

5. Voer op **de pagina Verbinding maken met Azure AD** uw globale beheerdersaccountreferenties in en selecteer **volgende**.

6. Selecteer volgende **op de pagina's** Verbinding maken met directories en filterpagina's voor domeinen/ou's.  

7. Selecteer op **de pagina** Optionele functies de optie **Wachtwoordterugschrijven** en selecteer vervolgens **Volgende**.

8. Selecteer op **de pagina Gereed om te** configureren de optie **Configureren** en wacht totdat het proces is klaar.

9. Wanneer u de configuratie-afwerking ziet, selecteert u **Afsluiten.**

U bent nu klaar om wachtwoord writeback te testen voor gebruikers op computers die niet zijn verbonden met het virtuele netwerk van uw gesimuleerde intranet.

De resulterende configuratie ziet er als volgende uit:

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Deze configuratie bestaat uit:

- Een proefversie van Microsoft 365 E5 of betaalde abonnementen met het DNS-domein TESTLAB.\<*your domain name*> geregistreerd.
- Een vereenvoudigd intranet van de organisatie dat is verbonden met internet, bestaande uit de virtuele DC1-, APP1- en CLIENT1-machines op een subnet van een virtueel Azure-netwerk.
- Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.
- Wachtwoord terugschrijven is ingeschakeld, zodat gebruikers hun wachtwoorden kunnen wijzigen via Azure AD, zonder te zijn verbonden met het vereenvoudigde intranet.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Microsoft 365 enterprise-documentatie](/microsoft-365-enterprise/)