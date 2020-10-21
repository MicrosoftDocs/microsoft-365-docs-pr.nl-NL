---
title: Doorsturen van e‑mail configureren
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: E-mail doorsturen naar een of meer e-mailaccounts via Office365.
ms.openlocfilehash: d19e2c533be6fac927bdf2aa65d72acab9fad6f6
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645525"
---
# <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren

::: moniker range="o365-21vianet"

> [!NOTE]
> Het beheercentrum wordt gewijzigd. Als de informatie die hier wordt weergegeven, niet overeenkomt met wat u gewend bent, raadpleegt u [Over het nieuwe Microsoft 365-beheercentrum](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
Als beheerder van een organisatie hebt u mogelijk een bedrijf nodig om het doorsturen van e-mail in te stellen voor het postvak van een gebruiker. Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.

  
## <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren

 Let op het volgende voordat u het doorsturen van e-mail instelt: 

- Wanneer u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mailberichten die worden verzonden naar het Postvak  *in*  doorgestuurd. 
    
- Voor het doorsturen van e-mail is vereist dat het  *van*  -account een licentie heeft. Als u het doorsturen van e-mail instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie [het postvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md). Op deze manier kunnen meerdere mensen er toegang toe krijgen. Een gedeeld postvak mag echter niet groter zijn dan 50 GB. 
    
U kunt deze stappen alleen uitvoeren als u een Exchange-beheerder of globale beheerder in Microsoft 365 bent. Voor meer informatie raadpleegt u het onderwerp [over beheerdersrollen](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
    
2. Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen. 
 
3. Selecteer op het tabblad **e-mail** de optie **doorsturen van e-mail beheren**. 
  
4. Selecteer op de pagina voor het doorsturen van e-mail **alle e-mail die naar dit postvak is verzonden**, voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen. Selecteer **Wijzigingen opslaan**.
    
    **Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen. Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.
    
5. Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.  Als u dat doet, wordt het doorsturen van e-mail gestopt. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen. 

3. Vouw **e-mailinstellingen**uit en selecteer vervolgens in het gedeelte voor het **doorsturen van E-mail** de optie **bewerken**.

4. Op de pagina voor het doorsturen van e-mail zet **u de**wisselknop op aan, voert u het doorstuuradres in en kiest u of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen. Kies **Opslaan**.
    
    **Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen. Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.
    
5. Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.  Als u dat doet, wordt het doorsturen van e-mail gestopt.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker van wie u het e-mailadres wilt doorsturen en klik op de pagina Eigenschappen. 

3. Vouw **e-mailinstellingen**uit en selecteer vervolgens in het gedeelte voor het **doorsturen van E-mail** de optie **bewerken**.

4. Op de pagina voor het doorsturen van e-mail zet **u de**wisselknop op aan, voert u het doorstuuradres in en kiest u of u een kopie van doorgestuurde e-mailberichten wilt bewaren. Als u deze optie niet ziet, controleert u of er een licentie aan het gebruikersaccount is toegewezen. Kies **Opslaan**.
    
    **Als u door wilt gaan naar meerdere e-mailadressen**, kunt u de gebruiker vragen een regel in Outlook in te stellen voor het doorsturen van de adressen. Zie [regels gebruiken om berichten automatisch door te sturen](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     U kunt ook [een distributiegroep maken](../setup/create-distribution-lists.md)in het Beheercentrum, [de adressen toevoegen aan](add-user-or-contact-to-distribution-list.md)de groep en vervolgens doorsturen instellen zodat ze verwijzen naar de DL met behulp van de instructies in dit artikel.
    
5. Verwijder niet het account van de gebruiker van wie u e-mail wilt doorsturen of verwijderen.  Als u dat doet, wordt het doorsturen van e-mail gestopt. 

::: moniker-end 
