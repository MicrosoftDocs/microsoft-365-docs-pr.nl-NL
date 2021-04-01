---
title: Een domein verwijderen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
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
ms.openlocfilehash: 916730975e9e17c42b01d9fa0ff55b3cb7078f66
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/31/2021
ms.locfileid: "51470963"
---
# <a name="remove-a-domain"></a>Een domein verwijderen
  
 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.yml)** als u niet kunt vinden wat u zoekt. 
  
Verwijdert u uw domein omdat u het wilt toevoegen aan een ander Microsoft 365-abonnement? Of wilt u uw abonnement gewoon opzeggen? U kunt [uw abonnement wijzigen](../../commerce/subscriptions/switch-to-a-different-plan.md) of [uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Stap 1: Gebruikers verplaatsen naar een ander domein

#### <a name="move-users"></a>Gebruikers verplaatsen

::: moniker range="o365-worldwide"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum.</a>

2. Selecteer **Gebruikers** > **Actieve gebruikers**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Selecteer **Meer opties** (**...**), boven aan de pagina en kies vervolgens **Domeinen wijzigen.**

5. Selecteer een **ander** domein in het deelvenster Domeinen wijzigen.

U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum.</a>  

2. Selecteer **Gebruikers** > **Actieve gebruikers**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Kies boven aan de pagina de optie **Meer** > **domeinen bewerken.**

5. Selecteer een **ander** domein in het deelvenster Domeinen bewerken.
  
U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum.</a>  

2. Selecteer **Gebruikers** > **Actieve gebruikers**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Kies boven aan de pagina de optie **Meer** > **domeinen bewerken.**

5. Selecteer een **ander** domein in het deelvenster Domeinen bewerken.
  
U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.

::: moniker-end

#### <a name="move-yourself"></a>Uzelf verplaatsen

::: moniker range="o365-worldwide"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum.</a>

2. Ga naar **Gebruikers** \> **Actieve gebruikers** en selecteer uw account in de lijst.

3. Selecteer op **het** tabblad Account de optie **Gebruikersnaam beheren** en kies vervolgens een ander domein.
  
4. Selecteer bovenaan de naam van uw account en selecteer vervolgens **Afloggen.**

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar **Gebruikers** \> **Actieve gebruikers** en selecteer uw naam in de lijst.

2. Selecteer in **de sectie Gebruikersnaam/e-mail** de optie **Bewerken** en kies vervolgens een ander domein.

3. Selecteer **Instellen als primaire** > **save** > **close**.
  
4. Selecteer bovenaan de naam van uw account en selecteer vervolgens **Afloggen.**

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar **Gebruikers** \> **Actieve gebruikers** en selecteer uw naam in de lijst.

2. Selecteer in **de sectie Gebruikersnaam/e-mail** de optie **Bewerken** en kies vervolgens een ander domein.

3. Selecteer **Instellen als primaire** > **save** > **close**.
  
4. Selecteer bovenaan de naam van uw account en selecteer vervolgens **Afloggen.**

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Stap 2: Groepen naar een ander domein verplaatsen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum  naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groepen groepen.</a>
  
2. Selecteer de groepsnaam en  selecteer op het tabblad Algemeen onder **E-mailadres primair** de optie **Bewerken.**

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">het beheercentrum</a>naar de pagina  > **Groepen groepen.**

2. Selecteer de groepsnaam en selecteer **vervolgens Bewerken** naast **Naam.**

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">het beheercentrum</a>naar de pagina  > **Groepen groepen.**

2. Selecteer de groepsnaam en selecteer **vervolgens Bewerken** naast **Naam.**

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Stap 3: Het oude domein verwijderen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de **pagina Domeinen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank"></a> instellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de **pagina Domeinen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank"></a> instellen.

::: moniker-end
  
2. Selecteer op **de pagina** Domeinen het domein dat u wilt verwijderen.

3. Selecteer verwijderen in het **rechterdeelvenster.**

4. Volg eventuele aanvullende aanwijzingen en selecteer **sluiten.**

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Hoe lang duurt het voordat een domein is verwijderd?

Het kan maar 5 minuten duren voordat Microsoft 365 een domein verwijdert als er niet naar wordt verwezen op veel plaatsen, zoals beveiligingsgroepen, distributielijsten, gebruikers en Microsoft 365-groepen. Als er veel verwijzingen zijn waarin het domein wordt gebruikt, kan het enkele uren (een dag) duren voordat het domein is verwijderd.
  
Als u honderden of duizenden gebruikers hebt, gebruikt u PowerShell om alle gebruikers te zoeken en ze vervolgens naar een ander domein te verplaatsen. Anders is het mogelijk dat een klein aantal gebruikers in de UI over het hoofd wordt gezien. Wanneer u het domein vervolgens wilt verwijderen, lukt dit niet en weet u niet waarom. Zie [Set-MsolUserPrincipalName](/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.
  
## <a name="still-need-help"></a>Meer hulp nodig?

::: moniker range="o365-worldwide"

> [!NOTE]
> U kunt het ['.onmicrosoft.com'](../setup/domains-faq.yml)-domein niet uit uw account verwijderen. Wanneer u een domein verwijdert, keren gebruikersaccounts terug naar het adres '.onmicrosoft.com' als primaire SMTP/UserprincipalName.
  
Werkt u nog steeds niet? Mogelijk moet uw domein handmatig worden verwijderd. [Bel ons en](../contact-support-for-business-products.md) wij helpen u om dit te doen.
  
::: moniker-end

## <a name="related-articles"></a>Verwante artikelen

[Veelgestelde vragen over domeinen](../setup/domains-faq.yml)

[Overstappen op een ander Microsoft 365 voor Bedrijven-abonnement](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md)