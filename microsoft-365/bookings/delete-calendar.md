---
title: Een reserveringsagenda verwijderen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Gebruik het Microsoft 365-beheercentrum of Windows PowerShell om Bookings-agenda's te verwijderen.
ms.openlocfilehash: 7b79628327797d2e315d31e1b1a2671f0b24e447
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913776"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Een boekingsagenda verwijderen in Bookings

In dit artikel wordt uitgelegd hoe u een ongewenste boekingsagenda kunt verwijderen. U kunt de boekingsagenda verwijderen in het Microsoft 365-beheercentrum of u kunt PowerShell gebruiken. De Bookings-agenda is een postvak in Exchange Online, dus u verwijdert het bijbehorende gebruikersaccount om de boekingsagenda te verwijderen.

> [!IMPORTANT]
> Alle boekingsagenda's die u in 2017 of eerder hebt gemaakt, moeten worden verwijderd met de PowerShell-instructies over dit onderwerp. Alle boekingsagenda's die in 2018 of daarna zijn gemaakt, kunnen worden verwijderd in het Microsoft 365-beheercentrum.

In de boekingskalender worden alle relevante informatie over die boekingsagenda en -gegevens opgeslagen, waaronder:

- Zakelijke gegevens, logo's en werkuren toegevoegd wanneer de boekingsagenda is gemaakt
- Relevante medewerkers en services toegevoegd bij het maken van de boekingsagenda
- Alle boekingen en vrijafafspraken die zijn toegevoegd aan de boekingsagenda nadat deze zijn gemaakt.

> [!WARNING]
> Wanneer een boekingsagenda is verwijderd, worden deze aanvullende gegevens ook permanent verwijderd en kunnen ze niet meer worden hersteld.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Een boekingsagenda verwijderen in het Microsoft 365-beheercentrum

1. Ga naar het Microsoft 365-beheercentrum.

1. Selecteer **Gebruikers** in het beheercentrum.

   ![Afbeelding van de gebruikersinterface van gebruikers in het Microsoft 365-beheercentrum](../media/bookings-admin-center-users.png)

1. Kies op de pagina **Actieve gebruikers** de namen van de gebruikers die u wilt verwijderen. Selecteer vervolgens **Gebruiker verwijderen**.

   ![Afbeelding van gebruikersgebruikersinterface verwijderen in microsoft 365-beheercentrum](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Een boekingsagenda verwijderen met Exchange Online PowerShell

Zie [Verbinding maken met Exchange Online PowerShell voor](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) vereisten en richtlijnen voor het maken van verbinding met Exchange Online PowerShell.

Als u deze stappen wilt uitvoeren, moet u een actief Microsoft PowerShell-opdrachtvenster gebruiken dat u hebt uitgevoerd door de optie Als beheerder uitvoeren te kiezen.

1. Laad in een PowerShell-venster de EXO V2-module door de volgende opdracht uit te voeren:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > Als u de [EXO V2-module](/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)al hebt geïnstalleerd, werkt de vorige opdracht zoals geschreven.
   
2. De opdracht die u moet uitvoeren, gebruikt de volgende syntaxis:

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ is uw account in de notatie van de gebruikersnaam `john@contoso.com` (bijvoorbeeld).

3. Wanneer u wordt gevraagd, meld u zich aan met de tenantbeheerderreferenties bij de Microsoft 365-tenant die de reserveringsagenda host die u permanent wilt verwijderen.

4. Als deze opdracht is verwerkt, voert u de volgende opdracht in om een lijst te krijgen met de boekingspostvakken in de tenant:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. Typ de volgende opdracht:

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Typ de exacte naam van de reserveringspostvakalias die u definitief wilt verwijderen.

6. Als u wilt controleren of de agenda is verwijderd, voert u de volgende opdracht in:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   De verwijderde agenda wordt niet weergegeven in de uitvoer.