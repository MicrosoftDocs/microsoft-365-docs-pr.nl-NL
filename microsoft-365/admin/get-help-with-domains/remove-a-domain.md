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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Meer informatie over het verwijderen van een oud domein uit Microsoft 365 en het verplaatsen van gebruikers en groepen naar een ander domein.
ms.openlocfilehash: b072a8f30d6b6a655441dec49ff9af9b4d0fdbe4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938634"
---
# <a name="remove-a-domain"></a>Een domein verwijderen
  
 **[Raadpleeg de veelgestelde vragen over domeinen](../setup/domains-faq.md)** als u niet kunt vinden wat u zoekt. 
  
Verwijdert u uw domein omdat u het wilt toevoegen aan een ander Microsoft 365-abonnement? Of wilt u uw abonnement gewoon opzeggen? U kunt [uw abonnement wijzigen](../../commerce/subscriptions/switch-to-a-different-plan.md) of [uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md).
  
### <a name="step-1-move-users-to-another-domain"></a>Stap 1: Gebruikers verplaatsen naar een ander domein

#### <a name="move-users"></a>Gebruikers verplaatsen

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">beheercentrum</a>.

2. Selecteer **Gebruikers** > **actieve gebruikers**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Selecteer **Meer opties** (**...**) boven aan de pagina en kies Domeinen **wijzigen**.

5. Selecteer **in** het deelvenster Domeinen wijzigen een ander domein.

U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>.  

2. Selecteer **Gebruikers** > **actieve gebruikers**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Kies boven aan de pagina **Meer** > **bewerkingsdomeinen**.

5. Selecteer in het deelvenster **Domeinen bewerken** een ander domein.
  
U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>.  

2. Selecteer **Gebruikers** > **actieve gebruikers**.

3. Selecteer de vakken naast de namen van alle gebruikers die u wilt verplaatsen.

4. Kies boven aan de pagina **Meer** > **bewerkingsdomeinen**.

5. Selecteer in het deelvenster **Domeinen bewerken** een ander domein.
  
U moet dit ook voor uzelf doen, als u zich in het domein bevindt dat u wilt verwijderen. Wanneer u het domein voor uw account bewerkt, moet u zich afmelden en weer aanmelden met het nieuwe domein dat u kiest om door te gaan.

::: moniker-end

#### <a name="move-yourself"></a>Beweeg jezelf

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>.

2. Ga naar **Gebruikers** \> **actieve gebruikers**en selecteer uw account in de lijst.

3. Selecteer op het tabblad **Account** de optie **Gebruikersnaam beheren**en kies vervolgens een ander domein.
  
4. Selecteer bovenaan uw accountnaam en selecteer **Afmelden.**

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga naar **Gebruikers** \> **actieve gebruikers**en selecteer uw naam in de lijst.

2. **Selecteer**bewerken en kies vervolgens een ander domein in de sectie Gebruikersnaam **/ e-mail.**

3. Selecteer **Instellen als primaire** > **Afsluiting** > **opslaan**.
  
4. Selecteer bovenaan uw accountnaam en selecteer **Afmelden.**

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga naar **Gebruikers** \> **actieve gebruikers**en selecteer uw naam in de lijst.

2. **Selecteer**bewerken en kies vervolgens een ander domein in de sectie Gebruikersnaam **/ e-mail.**

3. Selecteer **Instellen als primaire** > **Afsluiting** > **opslaan**.
  
4. Selecteer bovenaan uw accountnaam en selecteer **Afmelden.**

5. Meld u aan met het nieuwe domein en hetzelfde wachtwoord.

U kunt ook PowerShell gebruiken om gebruikers te verplaatsen naar een ander domein. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a>Stap 2: Groepen naar een ander domein verplaatsen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">groepen.</a>
  
2. Selecteer de groepsnaam en selecteer vervolgens op het tabblad **Algemeen** onder **E-mailadres Primair ,** Selecteer **Bewerken**.

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a>naar de pagina **Groepen** > **groepen.**

2. Selecteer de groepsnaam en selecteer **Bewerken** naast **Naam**.

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a>naar de pagina **Groepen** > **groepen.**

2. Selecteer de groepsnaam en selecteer **Bewerken** naast **Naam**.

3. Gebruik de vervolgkeuzelijst om een ander domein te kiezen.

4. Selecteer **Opslaan** en vervolgens **Sluiten**. Herhaal dit proces voor alle groepen of distributielijsten die zijn gekoppeld aan het domein dat u wilt verwijderen.

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a>Stap 3: Het oude domein verwijderen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar **Instellingen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domeinen</a>-pagina.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Setup-domeinen.</a> **Setup**

::: moniker-end
  
2. Selecteer **op** de pagina Domeinen het domein dat u wilt verwijderen.

3. Selecteer **Verwijderen**in het rechterdeelvenster .

4. Volg eventuele aanvullende aanwijzingen en selecteer **Sluiten**.

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a>Hoe lang duurt het voordat een domein is verwijderd?

Het kan slechts 5 minuten duren voordat Microsoft 365 een domein verwijdert als er niet naar wordt verwezen op veel plaatsen, zoals beveiligingsgroepen, distributielijsten, gebruikers en Microsoft 365-groepen. Als er veel verwijzingen zijn waarin het domein wordt gebruikt, kan het enkele uren (een dag) duren voordat het domein is verwijderd.
  
Als u honderden of duizenden gebruikers hebt, gebruikt u PowerShell om alle gebruikers te zoeken en ze vervolgens naar een ander domein te verplaatsen. Anders is het mogelijk dat een klein aantal gebruikers in de UI over het hoofd wordt gezien. Wanneer u het domein vervolgens wilt verwijderen, lukt dit niet en weet u niet waarom. Zie [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) voor meer informatie. Gebruik [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0) om het standaarddomein in te stellen.
  
## <a name="still-need-help"></a>Nog steeds hulp nodig?

::: moniker range="o365-worldwide"

> [!NOTE]
> U kunt het ['.onmicrosoft.com'](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx)-domein niet uit uw account verwijderen.
  
Werkt het nog steeds niet? Uw domein moet mogelijk handmatig worden verwijderd. [Bel ons gerust](../contact-support-for-business-products.md). We helpen u graag.
  
::: moniker-end

## <a name="related-articles"></a>Verwante artikelen

[Veelgestelde vragen over domeinen](../setup/domains-faq.md)

[Hulp krijgen bij Office 365-domeinen](get-help-with-domains.md)

[Overstappen op een ander Microsoft 365 voor Bedrijven-abonnement](../../commerce/subscriptions/switch-to-a-different-plan.md)

[Uw abonnement opzeggen](../../commerce/subscriptions/cancel-your-subscription.md)
