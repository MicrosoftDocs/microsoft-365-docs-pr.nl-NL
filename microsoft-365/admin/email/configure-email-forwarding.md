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
description: Met e-mail doorsturen kunt u e-mailberichten doorsturen die zijn verzonden naar een Microsoft 365 postvak van een gebruiker naar een ander postvak binnen of buiten uw organisatie.
ms.openlocfilehash: eb72204211a8eff929c024fbcede66dfe1f4b879
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635484"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>E-mail doorsturen configureren in Microsoft 365

Als beheerder van een organisatie hebt u mogelijk bedrijfsvereisten voor het instellen van e-mail doorsturen voor het postvak van een gebruiker. Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.

> [!IMPORTANT]
> U kunt beleidsregels voor uitgaand spamfilter gebruiken om automatische doorsturen naar externe geadresseerden te controleren. Zie Automatische externe e-mail doorsturen [in](/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)Microsoft 365.

## <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren

Voordat u het doorsturen van e-mail in stelt, moet u het volgende doen:

- Nadat u het doorsturen van e-mail hebt ingesteld, worden alleen **nieuwe** e-mailberichten doorgestuurd die naar het  *postvak*  vandaan worden verzonden.

- Voor het doorsturen van  *e-mail moet het*  van account een licentie hebben. Als u e-mail doorsturen instelt omdat de gebruiker uw organisatie heeft verlaten, kunt u het postvak ook converteren [naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md) Op deze manier hebben meerdere personen toegang tot de toegang. Een gedeeld postvak mag echter niet groter zijn dan 50 GB.

U moet een beheerder Exchange globale beheerder in Microsoft 365 om deze stappen uit te voeren. Zie het onderwerp Over [beheerdersrollen voor meer informatie.](../add-users/about-admin-roles.md)

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> **[actieve gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=834822)**

2. Selecteer de naam van de gebruiker van wie u e-mail wilt doorsturen en open vervolgens de eigenschappenpagina.

3. Selecteer op **het** tabblad E-mail **de optie E-mail doorsturen beheren.**

4. Selecteer op de pagina e-mail doorsturen de optie Alle e-mailberichten doorsturen die naar dit postvak zijn verzonden, voer het doorgestuurde adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, moet u ervoor zorgen dat er een licentie is toegewezen aan het gebruikersaccount. Selecteer **Wijzigingen opslaan**.

    **Als u meerdere e-mailadressen** wilt doorsturen, kunt u de gebruiker vragen om een regel in te stellen in Outlook door te sturen naar de adressen. Zie Regels gebruiken om berichten automatisch door te sturen voor [meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

     Of maak in het [](../setup/create-distribution-lists.md)beheercentrum een distributiegroep, voeg de adressen hieraan toe [en](add-user-or-contact-to-distribution-list.md)stel doorsturen in om de DL aan te wijzen met de instructies in dit artikel.

5. Verwijder niet het account van de gebruiker die e-mail doorgestuurd heeft of verwijder zijn of haar licentie!  Als u dit doet, wordt het doorsturen van e-mail gestopt.

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> **[actieve gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=847686)**

2. Selecteer de naam van de gebruiker van wie u e-mail wilt doorsturen om de eigenschappenpagina te openen.

3. Vouw **E-mailinstellingen** uit en selecteer bewerken in de sectie **E-mail** **doorsturen.**

4. Stel op de pagina e-mail doorsturen de schakelknop in op **Aan,** voer het doorsturende adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, moet u ervoor zorgen dat er een licentie is toegewezen aan het gebruikersaccount. Selecteer **Opslaan**.

   **Als u meerdere e-mailadressen** wilt doorsturen, kunt u de gebruiker vragen om een regel in te stellen in Outlook door te sturen naar de adressen. Zie Regels gebruiken om berichten automatisch door te sturen voor [meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   Of maak in het [](../setup/create-distribution-lists.md)beheercentrum een distributiegroep, voeg de adressen hieraan toe [en](add-user-or-contact-to-distribution-list.md)stel doorsturen in om de DL aan te wijzen met de instructies in dit artikel.

5. Verwijder niet het account van de gebruiker die e-mail doorgestuurd heeft of verwijder zijn of haar licentie!  Als u dit doet, wordt het doorsturen van e-mail gestopt.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> **[actieve gebruikers.](https://go.microsoft.com/fwlink/p/?linkid=850628)**

2. Selecteer de naam van de gebruiker van wie u e-mail wilt doorsturen om de eigenschappenpagina te openen.

3. Vouw **E-mailinstellingen** uit en selecteer bewerken in de sectie **E-mail** **doorsturen.**

4. Stel op de pagina e-mail doorsturen de schakelknop in op **Aan,** voer het doorsturende adres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, moet u ervoor zorgen dat er een licentie is toegewezen aan het gebruikersaccount. Selecteer **Opslaan**.

   **Als u meerdere e-mailadressen** wilt doorsturen, kunt u de gebruiker vragen om een regel in te stellen in Outlook door te sturen naar de adressen. Zie Regels gebruiken om berichten automatisch door te sturen voor [meer informatie.](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   Of maak in het [](../setup/create-distribution-lists.md)beheercentrum een distributiegroep, voeg de adressen hieraan toe [en](add-user-or-contact-to-distribution-list.md)stel doorsturen in om de DL aan te wijzen met de instructies in dit artikel.

5. Verwijder niet het account van de gebruiker die e-mail doorgestuurd heeft of verwijder zijn of haar licentie! Als u dit doet, wordt het doorsturen van e-mail gestopt.

::: moniker-end

## <a name="related-content"></a>Verwante onderwerpen 

[Een gedeeld postvak](../email/create-a-shared-mailbox.md) maken (artikel)\
[E-mail verzenden vanaf een ander adres](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (artikel)\
[Een gebruikersnaam en e-mailadres wijzigen](../add-users/change-a-user-name-and-email-address.md) (artikel)

