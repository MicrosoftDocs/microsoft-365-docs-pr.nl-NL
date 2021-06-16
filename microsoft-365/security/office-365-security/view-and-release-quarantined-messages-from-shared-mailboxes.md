---
title: In quarantaine geplaatste berichten uit gedeelde postvakken weergeven en vrijgeven
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gebruikers kunnen leren hoe ze in quarantaine geplaatste berichten kunnen bekijken en handelen die zijn verzonden naar gedeelde postvakken waar ze machtigingen voor hebben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d6aed4a6e3bc725635558a5e8394b671d11f47c
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929849"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>In quarantaine geplaatste berichten uit gedeelde postvakken weergeven en vrijgeven

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn momenteel beschikbaar in Preview, zijn niet voor iedereen beschikbaar en kunnen worden gewijzigd.

Gebruikers kunnen berichten in quarantaine beheren waarbij ze een van de geadresseerden zijn, zoals beschreven in Berichten in quarantaine zoeken en vrijgeven als gebruiker [in EOP.](find-and-release-quarantined-messages-as-a-user.md) Maar hoe zit het met gedeelde postvakken waarin de gebruiker de machtigingen Volledige toegang en Verzenden als of Verzenden namens voor het postvak heeft, zoals beschreven in Gedeelde postvakken [in](/exchange/collaboration-exo/shared-mailboxes)Exchange Online?

Voorheen moesten beheerders door de mogelijkheid voor gebruikers om in quarantaine geplaatste berichten te beheren die naar een gedeeld postvak zijn verzonden, automapping ingeschakeld laten voor het gedeelde postvak (dit is standaard ingeschakeld wanneer een beheerder een gebruiker toegang geeft tot een ander postvak). Afhankelijk van de grootte en het aantal postvakken waar de gebruiker toegang toe heeft, kunnen de prestaties echter worden vertraagd wanneer Outlooks alle postvakken probeert te openen die de gebruiker heeft.  Daarom kiezen veel beheerders ervoor om automatisch maken voor gedeelde postvakken [te verwijderen.](/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox)

Automapping is nu niet meer vereist voor gebruikers die in quarantaine geplaatste berichten beheren die naar gedeelde postvakken zijn verzonden. Het werkt gewoon. Er zijn twee verschillende methoden om in quarantaine geplaatste berichten te openen die naar een gedeeld postvak zijn verzonden:

- Als de beheerder spammeldingen voor eindgebruikers heeft ingeschakeld [in antispambeleid,](configure-your-spam-filter-policies.md#configure-end-user-spam-notifications)kan elke gebruiker die toegang heeft  tot de spammeldingen van eindgebruikers in het gedeelde postvak op de knop Controleren in de melding klikken om naar quarantaine te gaan in de Microsoft 365 Defender-portal. Met deze methode kunnen gebruikers alleen in quarantaine geplaatste berichten beheren die naar het gedeelde postvak zijn verzonden. Gebruikers kunnen in deze context hun eigen quarantaineberichten niet beheren.

- De gebruiker kan [naar de quarantaine gaan in de Microsoft 365 Defender-portal.](find-and-release-quarantined-messages-as-a-user.md) Standaard worden alleen berichten weergegeven die naar de gebruiker zijn verzonden. De gebruiker kan echter de resultaten  **sorteren** (standaard de knop Bericht-id) wijzigen in het  e-mailadres van geadresseerde, het e-mailadres van het gedeelde postvak invoeren en vervolgens op Vernieuwen klikken om de in quarantaine geplaatste berichten weer te geven die naar het gedeelde postvak zijn verzonden.

  ![In quarantaine geplaatste berichten sorteren op e-mailadres van geadresseerde.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Ongeacht de methode kunnen gebruikers verwarring voorkomen door de kolom **Geadresseerde** op te nemen voor berichten in quarantaine. Het maximum aantal kolommen dat moet worden weergegeven, is 7, dus de gebruiker moet op Kolommen wijzigen **klikken,** een bestaande kolom verwijderen (bijvoorbeeld Beleidstype), geadresseerde selecteren en vervolgens op Opslaan of Opslaan **als** standaard klikken. 

  ![Verwijder de kolom Type Beleid en voeg de kolom Geadresseerde toe aan quarantaine.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Dingen waar u rekening mee moet houden

- De eerste gebruiker die het bericht in quarantaine heeft geplaatst, bepaalt het lot van het bericht voor iedereen die het gedeelde postvak gebruikt. Als een gedeeld postvak bijvoorbeeld wordt gebruikt door tien gebruikers en een gebruiker besluit het quarantainebericht te verwijderen, wordt het bericht voor alle tien gebruikers verwijderd. Als een gebruiker besluit het bericht vrij te geven, wordt het bericht ook uitgebracht in het gedeelde postvak en is het toegankelijk voor alle andere gebruikers van het gedeelde postvak.

- Momenteel is de **knop Afzender blokkeren** niet beschikbaar in de flyout **Details** voor berichten in quarantaine die naar het gedeelde postvak zijn verzonden.

- Als u geneste beveiligingsgroepen gebruikt om toegang te verlenen tot een gedeeld postvak, raden we ten aanzien van quarantainebewerkingen voor gedeelde postvakken niet meer dan twee niveaus van geneste groepen aan. Groep A is bijvoorbeeld lid van groep B, dat lid is van groep C. Als u machtigingen wilt toewijzen aan een gedeeld postvak, voegt u de gebruiker niet toe aan Groep A en wijst u vervolgens Groep C toe aan het gedeelde postvak.  

- Als u in quarantaine geplaatste berichten voor het gedeelde postvak in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)wilt beheren, moet de eindgebruiker de [cmdlet Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage) met het e-mailadres van het gedeelde postvak gebruiken voor de waarde van de _parameter RecipientAddress_ om de berichten te identificeren. Bijvoorbeeld:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Vervolgens kan de eindgebruiker een in quarantaine geplaatst bericht selecteren in de lijst om het weer te geven of actie te ondernemen.

  In dit voorbeeld worden alle in quarantaine geplaatste berichten weergegeven die naar het gedeelde postvak zijn verzonden en wordt het eerste bericht in de lijst uit quarantaine verwijderd (het eerste bericht in de lijst is 0, het tweede bericht is 1, en ga zo maar door).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Zie de volgende onderwerpen voor gedetailleerde syntaxis- en parameterinformatie:

  - [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](/powershell/module/exchange/get-quarantinemessageheader)
  - [Preview-QuarantineMessage](/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
