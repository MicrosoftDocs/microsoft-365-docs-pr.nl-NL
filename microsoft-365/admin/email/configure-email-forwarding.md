---
title: Doorsturen van e‑mail configureren
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Het doorsturen van e-mail naar een of meer e-mailaccounts instellen met Office365.
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926640"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Doorsturen van e-mail configureren in Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Als beheerder van een organisatie hebt u misschien te maken met bedrijfsvereisten voor het instellen van het doorsturen van e-mail voor het postvak van een gebruiker. Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.

> [!IMPORTANT]
> U kunt uitgaand spamfilterbeleid gebruiken om automatische doorsturen naar externe geadresseerden te bepalen. Zie Automatische doorsturen van [externe e-mail instellen in Microsoft 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)voor meer informatie.

## <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren

Houd rekening met het volgende voordat u het doorsturen van e-mail in stelt:

- Wanneer u het doorsturen  van e-mail  hebt ingesteld, worden alleen nieuwe e-mailberichten doorgestuurd die naar het postvak van dat postvak worden verzonden.

- Voor het doorsturen van  *e-mail moet het*  account een licentie hebben. Als u het doorsturen van e-mail instelt omdat de gebruiker uw organisatie heeft verlaten, kunt u het postvak converteren naar [een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md) Op deze manier kunnen meerdere personen toegang krijgen tot de gegevens. Een gedeeld postvak mag echter niet groter zijn dan 50 GB.

U moet een Exchange-beheerder of globale beheerder in Microsoft 365 zijn om deze stappen uit te voeren. Zie het onderwerp Over beheerdersrollen [voor meer informatie.](../add-users/about-admin-roles.md)

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de **pagina Actieve** \> **[gebruikers van](https://go.microsoft.com/fwlink/p/?linkid=834822)** gebruikers.

2. Selecteer de naam van de gebruiker van wie u het e-mailbericht wilt doorsturen om de eigenschappenpagina te openen.

3. Selecteer Op het **tabblad E-mail** de optie **Doorsturen van e-mail beheren.**

4. Selecteer op de pagina Voor het doorsturen van e-mail alle e-mailberichten doorsturen die naar dit postvak zijn verzonden, voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, zorg er dan voor dat er een licentie is toegewezen aan het gebruikersaccount. Selecteer **Wijzigingen opslaan**.

    **Als u wilt doorsturen naar** meerdere e-mailadressen, kunt u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie Regels gebruiken om berichten automatisch door te sturen [voor meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

     Of maak in het beheercentrum een [](add-user-or-contact-to-distribution-list.md)distributiegroep, [](../setup/create-distribution-lists.md)voeg de adressen hieraan toe en stel doorsturen in om naar de distributiegroep te wijzen aan de hand van de instructies in dit artikel.

5. Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijder de licentie niet.  Als u dit doet, wordt het doorsturen van e-mail gestopt.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de **pagina Actieve** \> **[gebruikers van](https://go.microsoft.com/fwlink/p/?linkid=847686)** gebruikers.

2. Selecteer de naam van de gebruiker van wie u het e-mailbericht wilt doorsturen om de eigenschappenpagina te openen.

3. Vouw **E-mailinstellingen** uit en selecteer Bewerken in de **sectie** E-mail **doorsturen.**

4. Stel op de pagina voor het doorsturen van e-mail de optie Aan **in,** voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, zorg er dan voor dat er een licentie is toegewezen aan het gebruikersaccount. Klik op **Opslaan**.

   **Als u wilt doorsturen naar** meerdere e-mailadressen, kunt u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie Regels gebruiken om berichten automatisch door te sturen [voor meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   Of maak in het beheercentrum een [](add-user-or-contact-to-distribution-list.md)distributiegroep, [](../setup/create-distribution-lists.md)voeg de adressen hieraan toe en stel doorsturen in om naar de distributiegroep te wijzen aan de hand van de instructies in dit artikel.

5. Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijder de licentie niet.  Als u dit doet, wordt het doorsturen van e-mail gestopt.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de **pagina Actieve** \> **[gebruikers van](https://go.microsoft.com/fwlink/p/?linkid=850628)** gebruikers.

2. Selecteer de naam van de gebruiker van wie u het e-mailbericht wilt doorsturen om de eigenschappenpagina te openen.

3. Vouw **E-mailinstellingen** uit en selecteer Bewerken in de **sectie** E-mail **doorsturen.**

4. Stel op de pagina voor het doorsturen van e-mail de optie Aan **in,** voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, zorg er dan voor dat er een licentie is toegewezen aan het gebruikersaccount. Klik op **Opslaan**.

   **Als u wilt doorsturen naar** meerdere e-mailadressen, kunt u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie Regels gebruiken om berichten automatisch door te sturen [voor meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   Of maak in het beheercentrum een [](add-user-or-contact-to-distribution-list.md)distributiegroep, [](../setup/create-distribution-lists.md)voeg de adressen hieraan toe en stel doorsturen in om naar de distributiegroep te wijzen aan de hand van de instructies in dit artikel.

5. Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijder de licentie niet.  Als u dit doet, wordt het doorsturen van e-mail gestopt.

::: moniker-end
