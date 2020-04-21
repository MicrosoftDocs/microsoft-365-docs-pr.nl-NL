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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: E-mail doorsturen instellen voor een of meer e-mailaccounts met Office365.
ms.openlocfilehash: 5807649fa43d094fd8f05cf63e2905d7cdb6dd7d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628913"
---
# <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren
  
Als beheerder van een organisatie hebt u mogelijk bedrijfsvereisten om e-maildoorsturen in te stellen voor het postvak van een gebruiker. Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.

  
## <a name="configure-email-forwarding"></a>Doorsturen van e‑mail configureren

 Voordat u e-mail doorstuur instelt, moet u het volgende noteren: 

- Zodra u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mails die naar het *postvak worden* verzonden, verzonden. 
    
- E-mail doorsturen vereist dat het *van* account een licentie heeft. Als u e-mail doorsturen instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie om zijn postvak om te [zetten naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md) Op deze manier kunnen meerdere mensen er toegang toe krijgen. Een gedeeld postvak mag echter niet meer dan 50 GB bedragen. 
    
U moet exchange-beheerder of globale beheerder in Microsoft 365 zijn om deze stappen uit te voeren. Zie het onderwerp [Over beheerdersrollen](../add-users/about-admin-roles.md)voor meer informatie .

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen. 
 
3. Selecteer op het tabblad **E-mail** de optie **E-mail doorsturen beheren**. 
  
4. Selecteer op de pagina e-mail doorsturen **alle e-mails die naar dit postvak zijn verzonden,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount. Selecteer **Wijzigingen opslaan**.
    
    **Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!  Als u dit doet, stopt het doorsturen van e-mail. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen. 

3. Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.

4. Stel op de pagina e-mail doorsturen de schakel in **op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount. Kies **Opslaan**.
    
    **Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!  Als u dit doet, stopt het doorsturen van e-mail.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de eigenschappenpagina te openen. 

3. Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.

4. Stel op de pagina e-mail doorsturen de schakel in **op Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of er een licentie is toegewezen aan het gebruikersaccount. Kies **Opslaan**.
    
    **Als u naar meerdere e-mailadressen wilt doorsturen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om naar de DL te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder niet het account van de gebruiker die e-mail die u doorstuurt of hun licentie verwijdert!  Als u dit doet, stopt het doorsturen van e-mail. 

::: moniker-end 
