---
title: Het postvak van een gebruiker converteren naar een gedeeld postvak
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Informatie over het converteren van een privépostvak naar een gedeeld postvak dat door meerdere personen kan worden gebruikt in plaats van door slechts één persoon. '
ms.openlocfilehash: 0beb85e5a69b72bcd244cd654c399e91ded06ba7
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/24/2021
ms.locfileid: "52635472"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Het postvak van een gebruiker converteren naar een gedeeld postvak

Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden. Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon. Op een later tijdstip kunt u een gedeeld postvak weer converteren naar een (privé)postvak van een gebruiker.

## <a name="before-you-begin"></a>Voordat u begint

**Hier vindt u enkele belangrijke dingen die u moet weten:**

- Het gebruikerspostvak dat u converteert, heeft een licentie nodig die aan het postvak is toegewezen voordat u het converteert naar een gedeeld postvak. Anders wordt de optie om het postvak te converteren niet weergegeven. Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren. Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.

- Gedeelde postvakken kunnen maximaal 50 GB aan gegevens bevatten zonder dat er een licentie aan is toegewezen. Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen. Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.

- Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).

- De regels zijn intact nadat het postvak is geconverteerd naar een gedeeld postvak.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Het beheercentrum Exchange een postvak converteren
 
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Selecteer **GeadresseerdenPostvakken.** \> 

3. Selecteer het postvak van de gebruiker. Selecteer **onder Converteren naar gedeeld postvak** de optie **Converteren.**

4. Als het postvak kleiner is dan 50 GB, kunt u de licentie van de gebruiker verwijderen [en](../manage/remove-licenses-from-users.md)stoppen met betalen. Verwijder het account van de gebruiker niet. Het gedeelde postvak moet blijven bestaan als anker. Als u het postvak van een werknemer converteert die uw organisatie verlaat, moet u extra stappen ondernemen om ervoor te zorgen dat ze zich niet meer kunnen aanmelden. Zie [Een voormalige werknemer verwijderen uit Microsoft 365.](../add-users/remove-former-employee.md)
    
> [!NOTE]
> Het is niet vereist om het wachtwoord van de gebruiker opnieuw in te stellen tijdens de conversie van het postvak. Als het wachtwoord echter niet opnieuw wordt **ingesteld,** blijven de oorspronkelijke gebruikersnaam en het oorspronkelijke wachtwoord werken nadat de postvakconversie is voltooid.

Zie Over gedeelde postvakken en Een [](about-shared-mailboxes.md) gedeeld postvak maken voor alles wat u moet weten over [gedeelde postvakken.](create-a-shared-mailbox.md)

> [!NOTE]
> Voor gedeelde postvakken is geen aparte licentie vereist. Als u echter In-Place Archive wilt inschakelen of een In-Place Hold of Een Geschil in de wacht wilt zetten op een gedeeld postvak, moet u een Exchange Online Plan 1 met Exchange Online Archiving- of Exchange Online Plan 2-licentie aan het postvak toewijzen.

## <a name="convert-the-mailbox-of-a-deleted-user"></a>Het postvak van een verwijderde gebruiker converteren

Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:

1. [Het account van de gebruiker herstellen.](../add-users/restore-user.md)

2. Zorg ervoor dat Microsoft 365 licentie is toegewezen.

3. Het wachtwoord van de gebruiker opnieuw instellen.
    
4. Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.
    
5. Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.
    
6. Nadat dat is gebeurd, kunt u de licentie verwijderen uit het postvak van de gebruiker. Verwijder het oude postvak van de gebruiker niet. Het gedeelde postvak moet blijven bestaan als anker.
    
7. Voeg leden toe aan het gedeeld postvak.

## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Een gedeeld postvak converteren naar het (privé)postvak van een gebruiker

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.
   
2. Selecteer **Geadresseerden** \> **gedeeld.**

3. Selecteer het gedeelde postvak. Selecteer **onder Converteren naar normaal postvak** de optie **Converteren.**

4. Ga terug naar het beheercentrum. Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak. Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.

   Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Het postvak van een gebruiker converteren in een hybride omgeving

Zie voor meer informatie over het converteren van een gebruikerspostvak naar een gedeeld postvak in Exchange hybride omgeving:

 - [Cmdlets voor het maken of wijzigen van een extern gedeeld postvak in een on-premises Exchange omgeving](https://support.microsoft.com/office/cmdlets-to-create-or-modify-a-remote-shared-mailbox-in-an-on-premises-exchange-environment-9e83fb59-c001-729c-a4c0-b2964c154b49)
 - [Gedeelde postvakken worden onverwacht geconverteerd naar gebruikerspostvakken nadat adreslijstsynchronisatie is uitgevoerd in een Exchange hybride implementatie](/exchange/troubleshoot/user-and-shared-mailboxes/shared-mailboxes-unexpectedly-converted-to-user-mailboxes)
 

> [!NOTE]
> Als u lid bent van de rollengroep Organisatiebeheer of Geadresseerdenbeheer, kunt u de Exchange Management Shell gebruiken om een gebruikerspostvak te wijzigen in een gedeeld postvak on-premises. Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.com -Type Shared`.

## <a name="related-content"></a>Verwante inhoud

[Info over gedeelde postvakken](about-shared-mailboxes.md) (artikel)\
[Een gedeeld postvak](create-a-shared-mailbox.md) maken (artikel)\
[Een gedeeld postvak configureren](configure-a-shared-mailbox.md) (artikel)\
[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md) (artikel)\
[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md) (artikel)