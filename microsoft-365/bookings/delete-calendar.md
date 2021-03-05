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
description: Gebruik het Microsoft 365-beheercentrum of Windows PowerShell om boekingsagenda's te verwijderen.
ms.openlocfilehash: 1f8df15eafac7867f7ae852e344e1c5730362598
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/04/2021
ms.locfileid: "50454203"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Een boekingsagenda verwijderen in Bookings

In dit artikel wordt uitgelegd hoe u een ongewenste boekingsagenda kunt verwijderen. U kunt de boekingsagenda verwijderen in het Microsoft 365-beheercentrum of u kunt PowerShell gebruiken. De Bookings-agenda is een postvak in Exchange Online, dus u verwijdert het bijbehorende gebruikersaccount om de boekingsagenda te verwijderen.

> [!IMPORTANT]
> Alle boekingsagenda's die u in 2017 of eerder hebt gemaakt, moeten worden verwijderd volgens de PowerShell-instructies voor dit onderwerp. Alle boekingsagenda's die in 2018 of daarna zijn gemaakt, kunnen worden verwijderd in het Microsoft 365-beheercentrum.

In de boekingsagenda worden alle relevante informatie over de boekingsagenda en de gegevens opgeslagen, waaronder:

- Bedrijfsgegevens, logo en werkuren die zijn toegevoegd toen de boekingsagenda werd gemaakt
- Relevante medewerkers en services die zijn toegevoegd toen de boekingsagenda werd gemaakt
- Alle boekingen en afspraken met een time-off die zijn toegevoegd aan de boekingsagenda nadat deze is gemaakt.

> [!WARNING]
> Wanneer een boekingsagenda is verwijderd, wordt deze aanvullende informatie ook definitief verwijderd en kan deze niet meer worden hersteld.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Een boekingsagenda verwijderen in het Microsoft 365-beheercentrum

1. Ga naar het Microsoft 365-beheercentrum.

1. Selecteer **Gebruikers** in het beheercentrum.

   ![Afbeelding van de gebruikersinterface van gebruikers in het Microsoft 365-beheercentrum](../media/bookings-admin-center-users.png)

1. Kies op de pagina **Actieve gebruikers** de namen van de gebruikers die u wilt verwijderen. Selecteer vervolgens **Gebruiker verwijderen**.

   ![Afbeelding van de gebruikersinterface voor gebruikers verwijderen in het Microsoft 365-beheercentrum](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Een boekingsagenda verwijderen met Exchange Online PowerShell

Zie Connect to Exchange Online PowerShell for prerequisites and guidance for connecting to Exchange Online PowerShell (Verbinding maken met [Exchange Online PowerShell)](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps) voor vereisten en richtlijnen voor het maken van verbinding met Exchange Online PowerShell.

Als u deze stappen wilt uitvoeren, moet u een actief Microsoft PowerShell-opdrachtvenster gebruiken dat u hebt uitgevoerd door de optie Als administrator uitvoeren te kiezen.

1. Laad in een PowerShell-venster de EXO V2-module door de volgende opdracht uit te voeren:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > Als u de [EXO V2-module](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell-v2?view=exchange-ps#install-and-maintain-the-exo-v2-module)al hebt geïnstalleerd, werkt de vorige opdracht zoals geschreven.
   
2. Voor de opdracht die u moet uitvoeren, wordt de volgende syntaxis gebruikt:

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ is uw account in de notatie User Principal Name `john@contoso.com` (bijvoorbeeld).

3. Meld u aan met de referenties van de tenantbeheerder bij de Microsoft 365-tenant die als host de boekingsagenda bevat die u definitief wilt verwijderen.

4. Als deze opdracht is verwerkt, voert u de volgende opdracht in om een lijst te krijgen met de boekingspostvakken in de tenant:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

5. Typ de volgende opdracht:

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Let op dat u de exacte naam typt van de postvakalias van de reservering die u definitief wilt verwijderen.

6. Voer de volgende opdracht uit om te controleren of de agenda is verwijderd:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails Scheduling
   ```

   De verwijderde agenda wordt niet weergegeven in de uitvoer.
