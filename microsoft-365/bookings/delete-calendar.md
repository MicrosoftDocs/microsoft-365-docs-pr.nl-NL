---
title: Een boekings agenda verwijderen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Gebruik het Microsoft 365-Beheercentrum of Windows PowerShell om boekings agenda's te verwijderen.
ms.openlocfilehash: 2fcb92cee18d709ef0e1fa3faa0246e622a9f9db
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126647"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Een boekings agenda verwijderen in Bookings

In dit artikel wordt uitgelegd hoe u een ongewenste boekings agenda kunt verwijderen. U kunt de boekings agenda verwijderen in het Microsoft 365-Beheercentrum of u kunt PowerShell gebruiken. De Bookings-agenda is een postvak in Exchange Online, zodat u het bijbehorende gebruikersaccount verwijdert om de boekings agenda te verwijderen.

> [!IMPORTANT]
> Alle boekings agenda's die u hebt gemaakt in 2017 of eerder, moeten worden verwijderd met behulp van de PowerShell-instructies in dit onderwerp. Alle boekings agenda's die zijn gemaakt in 2018 of na kunnen worden verwijderd in het Microsoft 365-Beheercentrum.

De boekings agenda is de plaats waar alle relevante informatie over deze boekings agenda en gegevens zijn opgeslagen, waaronder:

- Bedrijfsinformatie, logo en werkuren die zijn toegevoegd tijdens het maken van de boekings agenda
- Relevante medewerkers en services die zijn toegevoegd tijdens het maken van de boekings agenda
- Alle Bookings-en time-out-afspraken worden toegevoegd aan de boekings agenda nadat deze is gemaakt.

> [!WARNING]
> Wanneer een boekings agenda wordt verwijderd, wordt deze aanvullende informatie ook permanent verwijderd en kan deze niet meer worden hersteld.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Een boekings agenda verwijderen in het Microsoft 365-Beheercentrum

1. Ga naar het Microsoft 365-beheercentrum.

1. Selecteer **Gebruikers** in het beheercentrum.

   ![Afbeelding van gebruikersinterface in Microsoft 365-Beheercentrum](../media/bookings-admin-center-users.png)

1. Kies op de pagina **Actieve gebruikers** de namen van de gebruikers die u wilt verwijderen. Selecteer vervolgens **Gebruiker verwijderen**.

   ![Afbeelding van de gebruikersinterface voor verwijderen van de gebruiker in Microsoft 365-Beheercentrum](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Een boekings agenda verwijderen met Exchange Online PowerShell

Zie [verbinding maken met Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) voor vereisten en richtlijnen voor het maken van verbinding met Exchange Online PowerShell.

U kunt deze stappen alleen uitvoeren als u een actief Microsoft PowerShell-opdrachtvenster gebruikt dat u hebt uitgevoerd door de optie als beheerder uitvoeren te kiezen.

1. Voer de volgende opdracht in:

   ```PowerShell
    $user = get-credential
   ```

1. Wanneer u hierom wordt gevraagd, meldt u zich aan met de referenties van de tenantbeheerder voor de Microsoft 365-Tenant die de boekings agenda host die u definitief wilt verwijderen.

1. Voer de volgende opdracht uit op de PowerShell-opdrachtprompt:

   ```PowerShell
    $s = New-Pssession -ConnectionUri https://outlook.office365.com/powershell-liveid -Credential $user -Authentication basic -AllowRedirection -ConfigurationName Microsoft.Exchange
   ```

1. Voer de volgende opdracht in:

   ```PowerShell
    Import-PSSession $s
   ```

1. Als deze opdracht is verwerkt, voert u de volgende opdracht in om een lijst te krijgen met de boekingspostvakken in de tenant:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

1. Typ de volgende opdracht:

   ```PowerShell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Let erop dat u de exacte naam opgeeft van de alias van het reserve-postvak dat u definitief wilt verwijderen.

1. Voer de volgende opdracht uit om te controleren of de agenda is verwijderd:

   ```PowerShell
    get-mailbox -RecipientTypeDetails Scheduling
   ```

   De verwijderde agenda wordt niet weergegeven in de uitvoer.
