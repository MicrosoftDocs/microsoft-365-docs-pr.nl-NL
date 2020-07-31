---
title: Het postvak van een gebruiker converteren naar een gedeeld postvak
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 2e122487-e1f5-4f26-ba41-5689249d93ba
description: 'Meer informatie over het converteren van een privépostvak naar een gedeeld postvak dat door meerdere gebruikers kan worden geopend. '
ms.openlocfilehash: a4b2e9ce53051feb07ea035adc0c959bbb1a0948
ms.sourcegitcommit: 0f71042edc7c3a7f10a7b92e1943abf51532cbf5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/29/2020
ms.locfileid: "46521027"
---
# <a name="convert-a-user-mailbox-to-a-shared-mailbox"></a>Het postvak van een gebruiker converteren naar een gedeeld postvak

Wanneer u het postvak van een gebruiker converteert naar een gedeeld postvak, blijven alle bestaande e-mailberichten en de agenda behouden. Het is nu alleen een gedeeld postvak waartoe meerdere personen toegang hebben in plaats van één persoon. Op een later tijdstip u een gedeeld postvak converteren naar een privépostvak van een gebruiker.

**Hier zijn een aantal echt belangrijke dingen die je moet weten:**

- Het gebruikerspostvak dat u converteert, heeft een licentie nodig die eraan is toegewezen voordat u deze converteert naar een gedeeld postvak. Anders wordt de optie om het postvak te converteren niet weergegeven. Als u de licentie hebt verwijderd, moet u deze opnieuw toevoegen om het postvak te kunnen converteren. Wanneer het postvak is geconverteerd naar een gedeeld postvak, kunt u de licentie weer verwijderen uit het gebruikersaccount.

- Gedeelde postvakken kunnen maximaal 50 GB aan gegevens hebben zonder dat er een licentie aan is toegewezen. Als u meer gegevens wilt opslaan, moet u een licentie aan het postvak toewijzen. Mogelijk moet u een reeks grote e-mailberichten (bijvoorbeeld berichten met bijlagen) uit het gedeelde postvak verwijderen, om het te verkleinen zodat u de licentie kunt verwijderen.

- Verwijder niet het account van de oude gebruiker. Dat hebt u nodig om het gedeelde postvak aan te verankeren. Als u het gebruikersaccount al hebt verwijderd, raadpleeg dan [Het postvak van een verwijderde gebruiker converteren](#convert-the-mailbox-of-a-deleted-user).

- De regels zijn intact nadat het postvak is geconverteerd naar een gedeeld postvak.

## <a name="use-the-exchange-admin-center-to-convert-a-mailbox"></a>Het Exchange-beheercentrum gebruiken om een postvak te converteren
 
1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.

2. Postvakken **geadresseerden** \> **selecteren**.

3. Selecteer het gebruikerspostvak. Selecteer **Onder Converteren naar gedeeld postvak**de optie **Converteren**.

4. Als het postvak kleiner is dan 50 GB, u de [licentie van de gebruiker](../manage/remove-licenses-from-users.md)verwijderen en er niet meer voor betalen. Verwijder het account van de gebruiker niet. Het gedeelde postvak moet blijven bestaan als anker. Als u het postvak converteert van een werknemer die uw organisatie verlaat, moet u extra stappen ondernemen om ervoor te zorgen dat deze niet meer kan inloggen. Zie [Een voormalige werknemer verwijderen uit Microsoft 365](../add-users/remove-former-employee.md).
    
5. Zie [Over gedeelde postvakken](about-shared-mailboxes.md) en [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor alles wat u moet weten over gedeelde postvakken.

## <a name="use-the-microsoft-365-admin-center-to-convert-a-mailbox"></a>Het Microsoft 365-beheercentrum gebruiken om een postvak te converteren

::: moniker range="o365-worldwide"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Actieve gebruikers</a>.

2. Selecteer de naam van de gebruiker wiens postvak u wilt converteren.

3. Het wachtwoord van de gebruiker opnieuw instellen.

   > [!NOTE]
   > Het is niet vereist om het wachtwoord van de gebruiker opnieuw in te stellen tijdens de conversie van het postvak. Als het wachtwoord echter niet opnieuw wordt ingesteld, **blijven de oorspronkelijke gebruikersnaam en het wachtwoord werken** nadat de conversie van het postvak is voltooid.

4. Selecteer op het tabblad **E-mail** onder **Meer acties**de optie **Converteren naar gedeeld postvak**. 

::: moniker-end

::: moniker range="o365-germany"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Actieve gebruikers</a>.

2. Selecteer de gebruiker wiens postvak u wilt converteren.

3. Vouw in het rechterdeelvenster **E-mailinstellingen uit**. Selecteer naast **Meer instellingen**de optie **Converteren naar gedeeld postvak**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Ga in het beheercentrum naar de pagina **Gebruikers** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Actieve gebruikers</a>.

2. Selecteer de gebruiker wiens postvak u wilt converteren.

3. Vouw in het rechterdeelvenster **E-mailinstellingen uit**. Selecteer naast **Meer instellingen**de optie **Converteren naar gedeeld postvak**.

::: moniker-end


Als het postvak kleiner is dan 50 GB, u [de licentie van de gebruiker verwijderen](../manage/remove-licenses-from-users.md)en er niet meer voor betalen. Verwijder het oude postvak van de gebruiker niet. Het gedeelde postvak moet blijven bestaan als anker. Als u het postvak converteert van een werknemer die uw organisatie verlaat, moet u extra stappen ondernemen om ervoor te zorgen dat deze niet meer kan inloggen. Zie [Een voormalige werknemer verwijderen uit Microsoft 365](../add-users/remove-former-employee.md).
    
Zie [Over gedeelde postvakken](about-shared-mailboxes.md) en [Een gedeeld postvak maken](create-a-shared-mailbox.md)voor alles wat u moet weten over gedeelde postvakken.

> [!NOTE]
> Gedeelde postvakken vereisen geen aparte licentie. Als u in-place archive wilt inschakelen of een in-place hold of een litigation hold op een gedeeld postvak wilt plaatsen, moet u een Exchange Online Plan 1 met Exchange Online Archiveing of Exchange Online Plan 2-licentie toewijzen aan het postvak.


## <a name="convert-the-mailbox-of-a-deleted-user"></a>Het postvak van een verwijderde gebruiker converteren

Stel dat u een gebruikersaccount hebt verwijderd en nu het oude postvak van dat account wilt converteren naar een gedeeld postvak. Hier leest u wat u kunt doen:

1. [Het account van de gebruiker herstellen](../add-users/restore-user.md).

2. Zorg ervoor dat er een Microsoft 365-licentie aan is toegewezen.

3. Het wachtwoord van de gebruiker opnieuw instellen.
    
4. Wacht twintig tot dertig minuten tot het postvak opnieuw is gemaakt.
    
5. Volg nu de instructies op deze pagina om het postvak te converteren naar een gedeeld postvak.
    
6. Nadat dat is gebeurd, u de licentie uit het postvak van de gebruiker verwijderen. Verwijder het oude postvak van de gebruiker niet. Het gedeelde postvak moet blijven bestaan als anker.
    
7. Voeg leden toe aan het gedeeld postvak.


## <a name="convert-a-shared-mailbox-back-to-a-users-private-mailbox"></a>Een gedeeld postvak converteren naar het (privé)postvak van een gebruiker

1. Ga naar het <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange-beheercentrum</a>.
   
2. Selecteer **Gedeelde geadresseerden** \> **Shared**.

3. Selecteer het gedeelde postvak. Selecteer **Onder Converteren naar normaal postvak**de optie **Converteren**.

4. Ga terug naar het beheercentrum. Kies onder **Gebruikers** het gebruikersaccount dat is gekoppeld aan het oude gedeeld postvak. Wijs een licentie toe aan het account en stel het wachtwoord opnieuw in.

   Het duurt enkele minuten voordat het postvak is ingesteld, maar daarna kan de persoon die dat account gaat gebruiken aan de slag. Wanneer deze gebruiker zich aanmeldt, worden de e-mail- en agenda-items weergegeven die anders in het gedeelde postvak stonden.

## <a name="convert-a-users-mailbox-in-a-hybrid-environment"></a>Het postvak van een gebruiker converteren in een hybride omgeving

Als dit gedeelde postvak zich in een hybride omgeving bevindt, raden we u **ten zeerste aan** (bijna nodig!) om het gebruikerspostvak terug te verplaatsen naar on-premises, het gebruikerspostvak om te zetten naar een gedeeld postvak en vervolgens het gedeelde postvak terug te verplaatsen naar de cloud. 

Hier is waarom: als u het postvak in de cloud converteert, kan het worden geconverteerd, maar on-premises denkt nog steeds dat het postvak het postvak van de gebruiker is, omdat de nieuwe realiteit niet wordt gesynchroniseerd met on-premises.

Meestal is dit geen probleem, maar er zijn enkele scenario's waarin de on-premises kenmerken (die denken dat het postvak het postvak van de gebruiker is) de nieuwe cloudversies van die kenmerken kunnen overschrijven en als gevolg daarvan het postvak kan worden omgeboekt. Dit is een probleem omdat gebruikerspostvakken licenties vereisen **of ze zijn zacht verwijderd na 30 dagen!**

We hebben de meeste redenen aangepakt waarom dit gebeurt, maar het kan nog steeds gebeuren, hoewel zelden. Het is het beste om veilig te zijn en het postvak terug te verplaatsen naar on-premises, om te zetten en vervolgens het gedeelde postvak terug te verplaatsen naar de cloud. Deze aanbevolen oplossing is niet in strijd met de licentieovereenkomst voor hybride omgevingen, omdat het bestaan van de gebruiker postvak on-premises is slechts tijdelijk. U zou in strijd zijn met uw licentie als u het gebruikerspostvak of het gedeelde postvak in uw on-premises organisatie hebt onderhouden en deze niet naar de cloud hebt verplaatst.

> [!NOTE]
> Als u lid bent van de rolgroep Organisatiebeheer of Organisatiebeheer, u de shell Exchange Management gebruiken om een gebruikerspostvak on-premises te wijzigen in een gedeeld postvak. Bijvoorbeeld `Set-Mailbox -Identity mailbox1@contoso.onmicrosoft.com -Type Shared`.

> [!TIP]
> Zie de tijdelijke oplossing in deze ondersteuningsoplossing voor voorbeelden waarin [gedeelde postvakken onverwacht worden geconverteerd naar postvakken van gebruikers.](https://support.microsoft.com/help/2710029/shared-mailboxes-are-unexpectedly-converted-to-user-mailboxes-after-di)
  
## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)

[Problemen oplossen met gedeelde postvakken](resolve-issues-with-shared-mailboxes.md)
