---
title: Doorsturen van e‑mail configureren
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
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: E-mail doorsturen naar een of meer e-mailaccounts instellen met Office365.
ms.openlocfilehash: 3ce82d514e1342ac6110ca74106477e3cf7820cb
ms.sourcegitcommit: a005395165db8896f4109674443b5e5e9209861d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/31/2020
ms.locfileid: "44432299"
---
# <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Als beheerder van een organisatie u bedrijfsvereisten hebben om e-mail doorsturen in te stellen voor het postvak van een gebruiker. Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.

  
## <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren

 Noteer het volgende voordat u e-mail doorstuurt: 

- Zodra u e-mail doorsturen, alleen **nieuwe** e-mails verzonden naar de *van* mailbox zal worden fowarded. 
    
- E-mail doorsturen vereist dat de *van* account heeft een licentie. Als u e-mail doorstuurt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie om het postvak om te [zetten naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md). Op deze manier hebben meerdere mensen er toegang toe. Een gedeeld postvak mag echter niet meer dan 50 GB bedragen. 
    
U moet een Exchange-beheerder of globale beheerder in Microsoft 365 zijn om deze stappen uit te voeren. Zie het onderwerp [Over beheerdersrollen voor](../add-users/about-admin-roles.md)meer informatie.

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina Eigenschappen te openen. 
 
3. Selecteer **e-mail doorsturen op**het tabblad **E-mail** beheren . 
  
4. Selecteer op de pagina e-mail doorsturen de optie **Alle e-mails die naar dit postvak worden verzonden,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount. Selecteer **Wijzigingen opslaan**.
    
    Als u **meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen voor](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder het account van de gebruiker die een e-mail stuurt en die u doorstuurt niet of verwijdert zijn licentie!  Als u dat doet, stopt e-mail doorsturen. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina Eigenschappen te openen. 

3. Vouw **E-mailinstellingen**uit en selecteer vervolgens in de sectie **E-maildoorschakeling** de optie **Bewerken**.

4. Stel op de pagina e-mail doorsturen de schakelaar **in op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount. Kies **Opslaan**.
    
    Als u **meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen voor](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder het account van de gebruiker die een e-mail stuurt en die u doorstuurt niet of verwijdert zijn licentie!  Als u dat doet, stopt e-mail doorsturen.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina Eigenschappen te openen. 

3. Vouw **E-mailinstellingen**uit en selecteer vervolgens in de sectie **E-maildoorschakeling** de optie **Bewerken**.

4. Stel op de pagina e-mail doorsturen de schakelaar **in op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount. Kies **Opslaan**.
    
    Als u **meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen voor](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder het account van de gebruiker die een e-mail stuurt en die u doorstuurt niet of verwijdert zijn licentie!  Als u dat doet, stopt e-mail doorsturen. 

::: moniker-end 
