---
title: Een gedeeld postvak configureren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Nadat u een gedeeld postvak hebt gemaakt, wilt u een aantal instellingen configureren voor de gebruikers, zoals het doorsturen van e-mail en automatische antwoorden. Later u andere instellingen wijzigen, zoals de naam van het postvak of de leden.
ms.openlocfilehash: 63d3d0a5867875344ff4635071bbbad69e02eadc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43629045"
---
# <a name="configure-a-shared-mailbox"></a>Een gedeeld postvak configureren

Nadat u een gedeeld postvak hebt [gemaakt,](create-a-shared-mailbox.md)wilt u een aantal instellingen configureren voor de gebruikers van het postvak, zoals het doorsturen van e-mail en automatische antwoorden. Later u andere instellingen wijzigen, zoals de naam van het postvak, de leden of de machtigingen voor leden. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>De naam of e-mailalias van een gedeeld postvak wijzigen of het primaire e-mailadres wijzigen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **vervolgens Bewerken** naast **Naam, E-mail, E-mailaliassen**.

3. Voer een nieuwe naam in of voeg een andere alias toe. Als u het primaire e-mailadres wilt wijzigen, moet uw postvak meer dan één e-mailalias hebben.

4. Kies **Opslaan**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>E-mailberichten doorsturen die zijn verzonden naar een gedeeld postvak

U hoeft geen licentie toe te wijzen aan het gedeelde postvak om e-mail door te sturen die naar het postvak is verzonden. U de berichten doorsturen naar een geldig e-mailadres of distributielijst.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **Vervolgens E-mail doorsturen** \> **Bewerken**.
    
3. Stel de schakelaar in **op Aan**en voer één e-mailadres in om de berichten naar door te sturen. Het kan elk geldig e-mailadres zijn. Als u naar meerdere adressen wilt doorsturen, moet u [een distributiegroep](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) voor de adressen maken en vervolgens de naam van de groep in dit vak invoeren.
    
4. Kies **Opslaan**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Automatische antwoorden verzenden vanuit een gedeeld postvak

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **Vervolgens Automatische antwoorden** \> **Bewerken**.
    
3. Zet de wisselknop op **Aan** en geef aan of u het antwoord wilt sturen naar personen binnen of buiten uw organisatie.

4. Voer het antwoord in dat u wilt verzenden naar personen binnen uw organisatie. U kunt geen afbeeldingen toevoegen, alleen tekst.

5. Als u *ook* een antwoord wilt sturen naar mensen buiten uw organisatie, schakelt u het selectievakje in, wie u het antwoord wilt ontvangen en typt u de tekst. Het is niet mogelijk om een bericht alleen naar personen buiten uw organisatie te verzenden, zonder datzelfde bericht ook naar personen binnen uw organisatie te verzenden.

6. Kies **Opslaan**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Iedereen toestaan Verzonden items (de antwoorden) te zien

Standaard worden berichten die vanuit het gedeelde postvak worden verzonden, niet opgeslagen in de map Verzonden items van het gedeelde postvak. In plaats daarvan worden ze opgeslagen in de map Verzonden Items van de persoon die het bericht heeft verzonden.

Als u wilt dat iedereen de verzonden e-mail kan zien, bewerkt u in het beheercentrum de instellingen van het gedeelde postvak en selecteert u **Verzonden items** \> **Bewerken**.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Kies de apps die een gedeeld postvak kan gebruiken om toegang te krijgen tot Microsoft-e-mail

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **vervolgens E-mailapps** \> **Bewerken**.

3. Stel de schakelaar in op **Aan** voor alle apps die leden moeten gebruiken om toegang te krijgen tot het gedeelde postvak. Stel de schakelaar in op **Uit** voor alle apps die u niet wilt dat ze gebruiken. 

4. Kies **Opslaan**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Een gedeeld postvak in de wachtstand van rechtszaken plaatsen

Zie [Een proceshouden](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold)voor meer informatie over het houden van geschillen.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **Procesvoering houd** \> **Bewerken .**

3. Stel de schakelaar in **op Aan**. 

4. Voer eventueel een duur, s-notitie over de wacht stand en een URL met meer informatie in.  

5. Kies **Opslaan**.


## <a name="add-or-remove-members"></a>Leden toevoegen of verwijderen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **Vervolgens Leden** \> **bewerken**.

3. Voer een van de volgende handelingen uit:
   - Als u leden wilt toevoegen, selecteert u **Leden toevoegen,** zoekt of selecteert u een lid dat u wilt toevoegen en selecteert u **Opslaan**.
   - Als u leden wilt verwijderen, gebruikt u het vak Zoeken om indien nodig naar het lid te zoeken, selecteert u de **X** naast de naam van het lid en selecteert u **Opslaan**. 

4. Selecteer Opnieuw **opslaan.**

## <a name="add-or-remove-permissions-of-members"></a>Machtigingen voor leden toevoegen of verwijderen

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **vervolgens Machtigingen** \> voor leden **aanpassen**.

3. Selecteer **Bewerken** naast de machtiging die u voor een lid wilt wijzigen. 

4. Voer een van de volgende handelingen uit:
   - Als u die toestemming wilt geven aan een extra lid, selecteert u **Machtigingen toevoegen,** zoekt of selecteert u een lid dat u wilt toevoegen en selecteert u **Opslaan**.
   - Als u de toestemming van een lid wilt verwijderen, gebruikt u het vak Zoeken om indien nodig naar het lid te zoeken, selecteert u de **X** naast de naam van het lid en selecteert u **Opslaan**. 

4. Selecteer Opnieuw **opslaan.**

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Een gedeeld postvak weergeven of verbergen in de algemene adreslijst

Als u ervoor kiest het gedeelde postvak niet weer te geven in de lijst met algemene adressen, wordt het postvak niet weergegeven in de adreslijst van uw organisatie, maar ontvangt het nog steeds e-mail die naar het postvak wordt verzonden. 

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Groepen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Gedeelde postvakken</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">beheercentrum</a> naar de pagina **Groepen** > **Gedeelde postvakken**. 

::: moniker-end

2. Selecteer het gedeelde postvak dat u wilt bewerken en selecteer **Weergeven in de algemene adreslijst** \> **Bewerken**.

3. Stel de schakelaar in **op Aan** of **Uit**. 

4. Kies **Opslaan**.

> [!NOTE]
> Als u een gedeeld postvak verbergt in de adreslijst, kunnen nieuwe leden van gedeelde postvaks het verborgen postvak niet toevoegen aan hun Outlook-profiel totdat het gedeelde postvak opnieuw in de adreslijst wordt weergegeven. 

## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)
