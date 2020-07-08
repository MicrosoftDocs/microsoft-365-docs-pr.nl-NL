---
title: Een domein verwijderen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Meer informatie over het verwijderen van een oud domein uit Microsoft 365 en het verplaatsen van gebruikers en groepen naar een ander domein.
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079759"
---
# <a name="remove-a-domain"></a>Een domein verwijderen

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Verwijdert u uw domein omdat u het wilt toevoegen aan een ander Microsoft 365-abonnement? Of wilt u uw abonnement gewoon opzeggen? U kunt [uw abonnement wijzigen](../../commerce/subscriptions/switch-to-a-different-plan.md) of [uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Stap 1: Gebruikers verplaatsen naar een ander domein

#### <a name="move-users"></a>Gebruikers verplaatsen

::: moniker range="o365-worldwide"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum</a>.

2. Selecteer **Actieve** gebruikers van Gebruikers > **Active users**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Selecteer **Meer opties** (**...**) boven aan de pagina en kies **Domeinen wijzigen**.

5. Selecteer in het deelvenster **Domeinen wijzigen** een ander domein.

You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>.  

2. Selecteer **Actieve** gebruikers van Gebruikers > **Active users**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Kies boven aan de pagina **Meer** > **domeinen bewerken**.

5. Selecteer in het deelvenster **Domeinen bewerken** een ander domein.
  
You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>.  

2. Selecteer **Actieve** gebruikers van Gebruikers > **Active users**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Kies boven aan de pagina **Meer** > **domeinen bewerken**.

5. Selecteer in het deelvenster **Domeinen bewerken** een ander domein.
  
You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.

::: moniker-end

#### <a name="move-yourself"></a>Beweeg jezelf

::: moniker range="o365-worldwide"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>.

2. Ga naar **Actieve** \> **gebruikers en**selecteer uw account in de lijst.

3. Selecteer **op** het tabblad Account de optie **Gebruikersnaam beheren**en kies vervolgens een ander domein.
  
4. Selecteer boven aan uw accountnaam en selecteer **Afmelden**.

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga **Users** naar \> **Actieve gebruikers**en selecteer uw naam in de lijst.

2. Selecteer **bewerken**in de sectie **Gebruikersnaam /E-mail** en kies vervolgens een ander domein.

3. Selecteer **Instellen als primair** sluiten > **Save** > **opslaan**.
  
4. Selecteer boven aan uw accountnaam en selecteer **Afmelden**.

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga **Users** naar \> **Actieve gebruikers**en selecteer uw naam in de lijst.

2. Selecteer **bewerken**in de sectie **Gebruikersnaam /E-mail** en kies vervolgens een ander domein.

3. Selecteer **Instellen als primair** sluiten > **Save** > **opslaan**.
  
4. Selecteer boven aan uw accountnaam en selecteer **Afmelden**.

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Stap 2: Groepen naar een ander domein verplaatsen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum **Groups** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a>
  
2. Selecteer de groepsnaam en selecteer vervolgens op het tabblad **Algemeen** onder **E-mailadres Primair**, selecteer **Bewerken**.

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>naar de pagina **Groups** > **Groepen groepen.**

2. Selecteer de groepsnaam en selecteer **Bewerken** naast **Naam**.

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>naar de pagina **Groups** > **Groepen groepen.**

2. Selecteer de groepsnaam en selecteer **Bewerken** naast **Naam**.

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Stap 3: Het oude domein verwijderen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum **Setup** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domeinen</a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum **Setup** naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domeinen</a> instellen.

::: moniker-end
  
2. Selecteer op de pagina **Domeinen** het domein dat u wilt verwijderen.

3. Selecteer **Verwijderen**in het rechterdeelvenster .

4. Volg eventuele aanvullende aanwijzingen en selecteer **Sluiten**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Hoe lang duurt het voordat een domein is verwijderd?

Het kan slechts 5 minuten duren voordat Microsoft 365 een domein verwijdert als er niet op veel plaatsen wordt verwezen, zoals beveiligingsgroepen, distributielijsten, gebruikers en Microsoft 365-groepen. Als er veel verwijzingen zijn waarin het domein wordt gebruikt, kan het enkele uren (een dag) duren voordat het domein is verwijderd.
  
If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).
  
## <a name="still-need-help"></a>Meer hulp nodig?

::: moniker range="o365-worldwide"

> [!NOTE]
> U kunt het ['.onmicrosoft.com'](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)-domein niet uit uw account verwijderen.
  
Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!
  
::: moniker-end

## <a name="related-articles"></a>Verwante artikelen

[Veelgestelde vragen over domeinen](../setup/domains-faq.md)

[Hulp krijgen bij Microsoft 365-domeinen](get-help-with-domains.md)

[Overstappen op een ander Microsoft 365 voor Bedrijven-abonnement](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md)
