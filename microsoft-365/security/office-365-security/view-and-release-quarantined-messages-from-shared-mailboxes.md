---
title: Geplaatste berichten van gedeelde postvakken weergeven en vrijgeven
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: Gebruikers kunnen informatie lezen over het weergeven van en werken met geplaatste berichten die zijn verzonden naar gedeelde postvakken waarnaar ze zijn gemachtigd.
ms.openlocfilehash: 0c165395edc3a3032ece603cb8d9aac875443d7d
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 12/04/2020
ms.locfileid: "49570940"
---
# <a name="view-and-release-quarantined-messages-from-shared-mailboxes"></a>Geplaatste berichten van gedeelde postvakken weergeven en vrijgeven

> [!NOTE]
> De functies die in dit artikel worden beschreven, zijn momenteel in de preview-versie, zijn niet beschikbaar voor iedereen en kunnen worden gewijzigd.

Gebruikers kunnen berichten in quarantaine plaatsen waar ze een van de geadresseerden zijn, zoals beschreven in [gequarantinee berichten in quarantaine plaatsen en vrijgeven als een gebruiker in EOP](find-and-release-quarantined-messages-as-a-user.md). Maar wat gebeurt er met gedeelde postvakken waarbij de gebruiker toegang heeft tot de machtigingen voor het postvak, zoals beschreven in [gedeelde postvakken in Exchange Online](https://docs.microsoft.com/exchange/collaboration-exo/shared-mailboxes)?

Eerder is de mogelijkheid om gebruikers te gebruiken voor het beheren van berichten die zijn verzonden naar een gedeeld postvak vereist beheerders om automatisch toewijzingen voor het gedeelde Postvak in te schakelen (deze optie is standaard ingeschakeld wanneer een beheerder een gebruiker toegang geeft tot een ander postvak). Afhankelijk van de grootte en het aantal postvakken waartoe de gebruiker toegang heeft, kan het echter even zijn voordat Outlook *alle* postvakken probeert te openen waartoe de gebruiker toegang heeft. Daarom kiezen een aantal beheerders om automatisch [toewijzen voor gedeelde postvakken te verwijderen](https://docs.microsoft.com/outlook/troubleshoot/profiles-and-accounts/remove-automapping-for-shared-mailbox).

Automatisch toewijzen is nu niet meer nodig voor gebruikers die quarantaine berichten beheren die naar gedeelde postvakken zijn verzonden. Het werkt gewoon. Er zijn twee verschillende manieren om toegang te krijgen tot in quarantaine geplaatste berichten die zijn verzonden naar een gedeeld postvak:

- Als de beheerder [meldingen voor spam van eindgebruikers heeft ingeschakeld](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-your-spam-filter-policies) in Antispambeleid, kan iedere gebruiker die toegang heeft tot de spam meldingen voor eindgebruikers in het gedeelde Postvak op de knop **controleren** klikken in de melding om naar Quarantine te gaan in het beveiligings & nalevings centrum. Met deze methode kunnen gebruikers alleen quarantaine berichten beheren die naar het gedeelde Postvak zijn verzonden. Gebruikers kunnen hun eigen Quarantine-berichten niet beheren in deze context.

- De gebruiker kan [naar de quarantaine gaan in het beveiligings & nalevings centrum](find-and-release-quarantined-messages-as-a-user.md). Standaard worden alleen de berichten weergegeven die naar de gebruiker zijn verzonden. De gebruiker kan de **sorteerresultaten** (standaard **bericht-id** standaard) wijzigen in het **e-mailadres** van de geadresseerde, het e-mailadres van het gedeelde Postvak opgeven en vervolgens op **vernieuwen** klikken om de berichten in quarantaine weer te geven die naar het gedeelde Postvak zijn verzonden.

  ![Berichten in quarantaine sorteren op het e-mailadres van de geadresseerde.](../../media/quarantine-sort-results-by-recipient-email-address.png)

Ongeacht de methode kunnen gebruikers verwarring voorkomen door de kolom **geadresseerden** voor berichten in quarantaine op te nemen. Het maximale aantal weer te geven kolommen is 7, dus de gebruiker moet op **kolommen wijzigen** klikken, een bestaande kolom verwijderen (bijvoorbeeld **type beleid**), selecteer **ontvanger** en klik vervolgens op **Opslaan** of **Opslaan als standaard**.

  ![Verwijder de kolomtype beleid en voeg de kolom geadresseerde toe aan Quarantine.](../../media/quarantine-add-recipient-column.png)

## <a name="things-to-keep-in-mind"></a>Zaken waaraan u moet denken

- De eerste gebruiker die in het gequarantined bericht moet handelen, bepaalt het gedrag van het bericht voor iedereen die het gedeelde Postvak gebruikt. Als een gebruiker een gedeeld postvak bijvoorbeeld opent door 10 gebruikers en een gebruiker besluit om het quarantaine bericht te verwijderen, wordt het bericht verwijderd voor alle tien gebruikers. Ook als een gebruiker besluit het bericht vrij te geven, wordt het vrijgegeven voor het gedeelde Postvak en is dit toegankelijk voor alle andere gebruikers van het gedeelde Postvak.

- Als een gebruiker op dit moment meerdere berichten in quarantaine selecteert die naar het gedeelde Postvak zijn verzonden, worden de volgende onjuiste fouten weergegeven wanneer de gebruiker klikt op **berichten vrijgeven** of **berichten verwijderen** in het vervolgmenu **bulk acties** :

  > U bent niet gemachtigd om alle geselecteerde berichten in quarantaine te brengen.
  >
  > U bent niet gemachtigd om alle geselecteerde berichten in quarantaine te verwijderen.

  Ongeacht de fout, wordt de actie uitgevoerd voor de berichten en kan de fout worden genegeerd.

  ![Fout: fout bij het bulksgewijs uitbrengen of verwijderen van quarantaine berichten die zijn verzonden naar een gedeeld postvak.](../../media/quarantine-bulk-action-error.png)

- De knop **afzender blokkeren** is op dit moment niet beschikbaar in de flyout **Details** voor berichten in quarantaine die naar het gedeelde Postvak zijn verzonden.

- Voor het beheren van berichten in quarantaine voor het gedeelde Postvak in [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)moet de eindgebruiker de cmdlet [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage) gebruiken met het gedeelde Postvak voor de waarde van de _RecipientAddress_ -parameter om de berichten te identificeren. Bijvoorbeeld:

  ```powershell
  Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com
  ```

  Vervolgens kan de eindgebruiker een in quarantaine geplaatste bericht selecteren in de lijst om op te geven of actie te ondernemen.

  In dit voorbeeld worden alle berichten in quarantaine weergegeven die naar het gedeelde Postvak zijn verzonden, en wordt het eerste bericht in de lijst uit quarantaine vrijgegeven (het eerste bericht in de lijst is 0, de tweede is 1, enzovoort).

  ```powershell
  $SharedMessages = Get-QuarantinedMessage -RecipientAddress officeparty@contoso.com | select -ExpandProperty Identity
  $SharedMessages
  Release-QuarantinedMessage -Identity $SharedMessages[0]
  ```

  Zie de volgende onderwerpen voor gedetailleerde syntaxis- en parameterinformatie:

  - [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)
  - [Get-QuarantineMessageHeader](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessageheader)
  - [Voorbeeld van QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage)
  - [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
