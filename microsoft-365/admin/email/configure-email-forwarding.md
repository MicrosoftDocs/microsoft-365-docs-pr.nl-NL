---
title: Doorsturen van e-mail configureren in Office 365
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
description: Stel e-maildoorsturen in naar een of meer e-mailaccounts met Office365.
ms.openlocfilehash: b6ad4032748c35db8e8c18b609915aef4231cb6c
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806389"
---
# <a name="configure-email-forwarding-in-office-365"></a>Doorsturen van e-mail configureren in Office 365
  
Als beheerder van een Office 365-organisatie hebt u wellicht bedrijfsmatige verplichtingen om het doorsturen van e-mail naar het postvak van een gebruiker in te stellen. Dankzij de functie voor e-mail doorsturen kunt u e-mailberichten vanuit het postvak van een gebruiker doorsturen naar het postvak van een gebruiker binnen of buiten de organisatie.

  
## <a name="configure-email-forwarding"></a>Doorsturen van e-mail configureren

 Noteer het volgende voordat u e-maildoorstuur instelt: 

- Zodra u e-mail doorsturen hebt ingesteld, worden alleen **nieuwe** e-mails die vanuit *postvak* worden verzonden, opgedrongen. 
    
- E-mail doorsturen vereist dat het *account van* een account een licentie heeft. Als u e-maildoorstuur instelt omdat de gebruiker uw organisatie heeft verlaten, is een andere optie het [converteren van zijn postvak naar een gedeeld postvak.](convert-user-mailbox-to-shared-mailbox.md) Op deze manier hebben meerdere mensen er toegang toe. Een gedeeld postvak mag echter niet meer dan 50 GB bedragen. 
    
U moet een Exchange-beheerder of Globale beheerder in Office 365 zijn om deze stappen uit te voeren. Zie voor meer informatie het onderwerp [Over beheerdersrollen](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

> [!NOTE]
> Als u het nieuwe Microsoft 365-beheercentrum niet gebruikt, kunt u dit inschakelen door de wisselknop **Probeer het nieuwe beheercentrum** bovenaan de startpagina te selecteren.

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina eigenschappen te openen. 
 
3. Selecteer op het tabblad **E-mail** de optie **E-mail doorsturen beheren**. 
  
4. Selecteer op de pagina e-mail doorsturen de optie **Alle e-mails doorsturen die naar dit postvak zijn verzonden,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount. Selecteer **Wijzigingen opslaan**.
    
    Als u **wilt doorsturen naar meerdere e-mailadressen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om de DL aan te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder het account van de gebruiker die e-mail is die u doorstuurt of verwijder hun licentie niet!  Als u dat doet, stopt het doorsturen van e-mail. 

::: moniker-end

::: moniker range="o365-germany"
    
 1.   Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina eigenschappen te openen. 

3. Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.

4. Stel op de pagina e-mail doorsturen de schakelaar in op **Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount. Kies **Opslaan**.
    
    Als u **wilt doorsturen naar meerdere e-mailadressen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om de DL aan te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder het account van de gebruiker die e-mail is die u doorstuurt of verwijder hun licentie niet!  Als u dat doet, stopt het doorsturen van e-mail.    

::: moniker-end

::: moniker range="o365-21vianet"

 1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>. 
    
2. Selecteer de naam van de gebruiker wiens e-mail u wilt doorsturen om de pagina eigenschappen te openen. 

3. Vouw **e-mailinstellingen**uit en selecteer vervolgens in de sectie **E-mail doorsturen** de optie **Bewerken**.

4. Stel op de pagina e-mail doorsturen de schakelaar in op **Aan,** voer het doorstuuradres in en kies of u een kopie van doorgestuurde e-mails wilt bewaren. Als u deze optie niet ziet, controleert u of een licentie is toegewezen aan het gebruikersaccount. Kies **Opslaan**.
    
    Als u **wilt doorsturen naar meerdere e-mailadressen,** u de gebruiker vragen een regel in Outlook in te stellen om door te sturen naar de adressen. Zie [Regels gebruiken om berichten automatisch door te sturen](https://support.office.com/article/use-rules-to-automatically-forward-messages-45aa9664-4911-4f96-9663-ece42816d746)voor meer informatie. 
    
     Of maak in het beheercentrum [een distributiegroep,](../setup/create-distribution-lists.md) [voeg de adressen eraan toe](add-user-or-contact-to-distribution-list.md)en stel vervolgens doorsturen in om de DL aan te wijzen met behulp van de instructies in dit artikel.
    
5. Verwijder het account van de gebruiker die e-mail is die u doorstuurt of verwijder hun licentie niet!  Als u dat doet, stopt het doorsturen van e-mail. 

::: moniker-end 
