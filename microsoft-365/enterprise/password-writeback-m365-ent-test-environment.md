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
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487126"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a>Wachtwoord terugschrijven voor uw Microsoft 365-testomgeving

*Deze test lab-gids kan alleen worden gebruikt voor Microsoft 365 voor Enterprise test omgevingen.*

Gebruikers kunnen terugschrijven van wachtwoorden gebruiken om hun wachtwoord bij te werken via Azure Active Directory (Azure AD), dat vervolgens wordt gerepliceerd naar uw lokale Active Directory Domain Services (AD DS). Met het terugschrijven van wachtwoorden hoeven gebruikers hun wachtwoorden niet bij te werken via de on-premises AD DS, waar hun oorspronkelijke gebruikersaccounts zijn opgeslagen. Dit helpt u bij zwervende of externe gebruikers die geen verbinding hebben met het on-premises netwerk van een externe verbinding.

In dit artikel wordt uitgelegd hoe u uw Microsoft 365-testomgeving configureert voor het terugschrijven van wachtwoorden.

Het configureren van uw testomgeving voor het terugschrijven van wachtwoorden omvat twee fasen:
- [Fase 1: wachtwoord-hash-synchronisatie configureren voor uw Microsoft 365-testomgeving](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Testlabrichtlijnen voor de Microsoft-cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> Ga naar [Microsoft 365 for Enterprise test lab Guide](../downloads/Microsoft365EnterpriseTLGStack.pdf)van een visuele kaart voor alle artikelen in de stack microsoft 365 for Enterprise test lab Guide.

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a>Fase 1: configureer wachtwoord-hash-synchronisatie voor uw Microsoft 365-testomgeving

Volg eerst de instructies in [wachtwoord-hash-synchronisatie](password-hash-sync-m365-ent-test-environment.md). De uiteindelijke configuratie ziet er als volgt uit:
  
![De gesimuleerde onderneming in een testomgeving met wachtwoord-hash-synchronisatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
Deze configuratie bestaat uit:
  
- Een proef- of betaald abonnement op Microsoft 365 E5.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.
- Azure AD Connect wordt uitgevoerd op APP1 om het AD DS-domein TESTLAB te synchroniseren met de Azure AD-tenant van uw Microsoft 365-abonnement.

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a>Fase 2: schakel Wachtwoord terugschrijven in voor het domein TESTLAB AD DS.

Configureer eerst het account gebruiker 1 met de rol globale beheerder.

1. Meld u aan in het [Microsoft 365-beheercentrum](https://portal.microsoft.com) met uw globale beheerdersaccount.

2. Selecteer **actieve gebruikers**.
 
3. Selecteer op de pagina **actieve gebruikers** het account **gebruiker1** ,

4. Selecteer in het deelvenster **gebruiker1** de optie **bewerken** naast **rollen**.

5. Selecteer in het deelvenster **gebruikersrollen bewerken** voor gebruiker1 de optie **globale beheerder**, selecteer **Opslaan**en selecteer vervolgens **sluiten**.

Configureer vervolgens het account gebruiker 1 met de beveiligingsinstellingen waarmee wachtwoorden kunnen worden gewijzigd namens andere gebruikers in het domein TESTLAB AD DS.

1. Ga naar het [Azure-portal](https://portal.azure.com), meld u aan met uw globale beheerdersaccount en maak vervolgens verbinding met APP1 via het TESTLAB\Gebruiker1-account.

2. Selecteer op de desktopversie van APP1 de optie **Start**, Enter **Active**en selecteer vervolgens **Active Directory: gebruikers en computers**.

3. Selecteer op de menubalk de optie **weergeven**. Als **geavanceerde functies** niet is ingeschakeld, schakelt u deze optie in.

4. Selecteer in het deelvenster Structuur de optie uw domein (of klik er met de rechtermuisknop op), selecteer **Eigenschappen**en selecteer vervolgens het tabblad **beveiliging** .

5. Selecteer **Geavanceerd**.

6. Selecteer **toevoegen**op het tabblad **machtigingen** .

7. Selecteer **een principal selecteren**, typ **gebruiker1**en selecteer **OK**.

8. Selecteer in **Van toepassing op**, **Onderliggende gebruikersobjecten**.

9. Selecteer onder **Machtigingen** het volgende:

    - **Wachtwoord wijzigen**
    - **Wachtwoord opnieuw instellen**

10. Selecteer onder **Eigenschappen** het volgende:
    - **LockoutTime schrijven**
    - **pwdLastSet schrijven**

11. Klik driemaal op **OK** om de wijzigingen op te slaan.

12. Sluit **Active Directory-gebruikers en -computers**.

Configureer vervolgens Azure AD Connect op APP1 voor Wachtwoord terugschrijven.

1. Verbind indien nodig APP1 met het account TESTLAB\Gebruiker1.

2. Dubbelklik op het bureaublad van APP1 op **Azure AD Connect**.

3. Selecteer **configureren**op de **welkomstpagina**.

4. Selecteer op de pagina **extra taken** de optie **synchronisatieopties aanpassen**en selecteer **volgende**.

5. Voer op de pagina **verbinding maken met Azure AD** de referenties van uw globale beheerdersaccount in en selecteer **volgende**.

6. Selecteer **volgende**op de pagina's **Connect directory's** en **Domain/ou filtering** .

7. Selecteer op de pagina **optionele functies** de optie **wachtwoord terugschrijven**en selecteer **volgende**.

8. Selecteer op de pagina **gereed voor configureren** de optie **configureren** en wacht tot het proces is voltooid.

9. Wanneer de configuratie voltooien wordt weergegeven, selecteert u **Afsluiten**.

U kunt nu het terugschrijven van wachtwoorden voor gebruikers op computers die geen verbinding hebben met het virtuele netwerk van uw gesimuleerde intranet testen.

De uiteindelijke configuratie ziet er als volgt uit:

![De gesimuleerde onderneming met een testomgeving met pass-through-verificatie](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

Deze configuratie bestaat uit:

- Een Microsoft 365 E5-proefabonnement of betaalde abonnementen met de DNS-domein TESTLAB.\<*your domain name*> geregistreerd.
- Een eenvoudiger organisatie intranet, verbonden met internet, bestaande uit DC1-, APP1-en CLIENT1 virtuele machines op een subnet van een Azure virtueel netwerk.
- Azure AD Connect draait op APP1 om de lijst van accounts en groepen van de Azure AD-tenant van uw Microsoft 365-abonnement te synchroniseren met het TESTLAB AD DS-domein.
- Wachtwoord terugschrijven is ingeschakeld, zodat gebruikers hun wachtwoorden kunnen wijzigen via Azure AD, zonder te zijn verbonden met het vereenvoudigde intranet.

## <a name="next-step"></a>Volgende stap

Verken aanvullende [identiteits](m365-enterprise-test-lab-guides.md#identity)functies en -mogelijkheden in uw testomgeving.

## <a name="see-also"></a>Zie ook

[Microsoft 365 Enterprise-testlabrichtlijnen](m365-enterprise-test-lab-guides.md)

[Overzicht van Microsoft 365 voor ondernemingen](microsoft-365-overview.md)

[Documentatie voor Microsoft 365 for Enterprise](https://docs.microsoft.com/microsoft-365-enterprise/)


