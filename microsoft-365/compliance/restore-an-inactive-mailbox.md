---
title: Een inactief postvak terugzetten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 97e06a7a-ef9a-4ce8-baea-18b9e20449a3
description: Meer informatie over het herstellen (of samenvoegen) van de inhoud van een inactief postvak in een bestaand postvak in Office 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: bc9039d21f76affce7f58f1f83597dd9e5eb4ecf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52161900"
---
# <a name="restore-an-inactive-mailbox"></a>Een inactief postvak terugzetten

Een inactief postvak (een type postvak dat wordt verwijderd) wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat hij of zij uw organisatie heeft verlaat. Als een andere werknemer de taakverantwoordelijkheden van de overleden werknemer op zich neemt of als die werknemer terugkeert naar uw organisatie, zijn er twee manieren waarop u de inhoud van het inactieve postvak beschikbaar kunt maken voor een gebruiker:

- **Een inactief postvak herstellen** Als een andere werknemer de taakverantwoordelijkheden van de overleden werknemer op zich neemt of als een andere gebruiker toegang nodig heeft tot de inhoud van het inactieve postvak, kunt u de inhoud van het inactieve postvak herstellen (of samenvoegen) naar een bestaand postvak. U kunt het archief ook herstellen vanuit een inactief postvak. Nadat het is hersteld, blijft het inactieve postvak behouden en blijft het behouden als een inactief postvak. In dit onderwerp worden de procedures beschreven voor het herstellen van een inactief postvak.

- **Een inactief postvak herstellen** Als de overleden werknemer terugkeert naar uw organisatie of als een nieuwe werknemer wordt aangenomen om de taaktaken van de overleden werknemer op zich te nemen, kunt u de inhoud van het inactieve postvak herstellen. Met deze methode wordt het inactieve postvak ge converteerd naar een nieuw postvak dat de inhoud van het inactieve postvak bevat. Nadat het is hersteld, bestaat het inactieve postvak niet meer. Zie Een inactief postvak herstellen in Office 365 voor [de stapsgewijse procedures.](recover-an-inactive-mailbox.md)

Zie de [sectie Meer informatie](#more-information) in dit artikel voor meer informatie over de verschillen tussen het herstellen en herstellen van een inactief postvak.

> [!NOTE]
> U kunt een inactief postvak dat is geconfigureerd met een automatisch uitbreidend archief, niet herstellen of herstellen. Als u gegevens wilt herstellen uit een inactief postvak met een automatisch uitbreidend archief, gebruikt u inhoud zoeken om de gegevens uit het postvak te exporteren en vervolgens te importeren in een ander postvak. Zie de volgende onderwerpen voor instructies:
>
> - [Inhoud zoeken](content-search.md)
> - [Zoekresultaten voor inhoud exporteren](export-search-results.md)

## <a name="requirements-to-restore-an-inactive-mailbox"></a>Vereisten voor het herstellen van een inactief postvak

- U moet powershell Exchange Online gebruiken om een inactief postvak te herstellen. U kunt het beheercentrum Exchange (EAC) niet gebruiken. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.

- Voer de volgende opdracht uit in Exchange Online PowerShell om identiteitsgegevens op te halen voor de inactieve postvakken in uw organisatie.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Gebruik de gegevens die door deze opdracht worden geretourneerd om een specifiek inactief postvak te herstellen.

- Zie Inactieve postvakken in Office 365 voor meer informatie over inactieve [postvakken.](inactive-mailboxes-in-office-365.md)

## <a name="restore-inactive-mailboxes"></a>Inactieve postvakken herstellen

Gebruik de **cmdlet New-MailboxRestoreRequest** met de parameters  _SourceMailbox_ en  _TargetMailbox_ om de inhoud van een inactief postvak terug te zetten in een bestaand postvak. Zie [New-MailboxRestoreRequest](/powershell/module/exchange/new-mailboxrestorerequest)voor meer informatie over het gebruik van deze cmdlet.

1. Maak een variabele die de eigenschappen van het inactieve postvak bevat.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > Gebruik in de vorige opdracht de waarde van de eigenschap **DistinguishedName** of **ExchangeGUID** om het inactieve postvak te identificeren. Deze eigenschappen zijn uniek voor elk postvak in uw organisatie, terwijl het mogelijk is dat een actief en inactief postvak hetzelfde primaire SMTP-adres heeft.

2. Herstel de inhoud van het inactieve postvak in een bestaand postvak. De inhoud van het inactieve postvak (bronpostvak) wordt samengevoegd in de bijbehorende mappen in het bestaande postvak (doelpostvak).

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -AllowLegacyDNMismatch
   ```

   U kunt ook een map op het hoogste niveau opgeven in het doelpostvak waarin u de inhoud van het inactieve postvak wilt herstellen. Als de opgegeven doelmap of doelmapstructuur nog niet bestaat in het doelpostvak, wordt deze gemaakt tijdens het herstelproces.

   In dit voorbeeld worden postvakitems en submappen gekopieerd van een inactief postvak naar een map met de naam 'Inactief postvak' in de mapstructuur op het hoogste niveau van het doelpostvak.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -TargetMailbox newemployee@contoso.com -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
   ```

## <a name="restore-the-archive-from-an-inactive-mailbox"></a>Het archief herstellen vanuit een inactief postvak

Als een inactief postvak een archiefpostvak heeft, kunt u het ook terugzetten naar het archiefpostvak van een bestaand postvak. Als u het archief wilt herstellen vanuit een inactief postvak, moet u de switches _SourceIsArchive_ en _TargetIsArchive_ toevoegen aan de opdracht die wordt gebruikt om een inactief postvak te herstellen.

1. Maak een variabele die de eigenschappen van het inactieve postvak bevat.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!NOTE]
   > Gebruik in de vorige opdracht de waarde van de eigenschap **DistinguishedName** of **ExchangeGUID** om het inactieve postvak te identificeren. Deze eigenschappen zijn uniek voor elk postvak in uw organisatie, terwijl het mogelijk is dat een actief en inactief postvak hetzelfde primaire SMTP-adres heeft.

2. Herstel de inhoud van het archief vanuit het inactieve postvak (bronarchief) naar het archief van een bestaand postvak (doelarchief). In dit voorbeeld wordt de inhoud uit het bronarchief gekopieerd naar een map met de naam 'Inactief postvakarchief' in het archief van het doelpostvak.

   ```powershell
   New-MailboxRestoreRequest -SourceMailbox $InactiveMailbox.DistinguishedName -SourceIsArchive -TargetMailbox newemployee@contoso.com -TargetIsArchive -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
   ```

## <a name="more-information"></a>Meer informatie

- **Wat is het belangrijkste verschil tussen het herstellen en herstellen van een inactief postvak?** Wanneer u een inactief postvak herstelt, wordt het postvak in feite geconverteerd naar een nieuw postvak, blijven de inhoud en mapstructuur van het inactieve postvak behouden en is het postvak gekoppeld aan een nieuw gebruikersaccount. Nadat het is hersteld, bestaat het inactieve postvak niet meer en zijn wijzigingen in de inhoud in het nieuwe postvak van invloed op de inhoud die oorspronkelijk in de wacht stond in het inactieve postvak. Wanneer u een inactief postvak herstelt, wordt de inhoud echter alleen gekopieerd naar een ander postvak. Het inactieve postvak blijft behouden en blijft een inactief postvak. Wijzigingen in de inhoud in het doelpostvak hebben geen invloed op de oorspronkelijke inhoud in het inactieve postvak. Het inactieve postvak kan nog steeds worden doorzocht met behulp van het hulpprogramma Inhoud [zoeken,](content-search.md)de inhoud ervan kan worden hersteld naar een ander postvak of op een later tijdstip worden hersteld of verwijderd.

- **Hoe vindt u inactieve postvakken?** Als u een lijst met de inactieve postvakken in uw organisatie wilt weergeven en informatie wilt weergeven die nuttig is voor het herstellen van een inactief postvak, kunt u deze opdracht uitvoeren.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,PrimarySMTPAddress,DistinguishedName,ExchangeGUID,LegacyExchangeDN,ArchiveStatus
  ```

- **Gebruik een bewaarbeleid voor juridische Microsoft 365 om inactieve postvakinhoud te behouden.** Als u de status van een inactief postvak wilt behouden nadat het [](create-a-litigation-hold.md) is hersteld, kunt u het doelpostvak in de bewaring van rechtszaken plaatsen of een Microsoft 365-bewaarbeleid toepassen voordat u het [inactieve](retention.md) postvak herstelt. Hiermee voorkomt u dat items definitief worden verwijderd uit het inactieve postvak nadat ze zijn hersteld in het doelpostvak.

- **Bewaar bewaring in het doelpostvak inschakelen voordat u een inactief postvak herstelt.** Omdat postvakitems uit een inactief postvak oud kunnen zijn, kunt u overwegen bewaring in te stellen voor het doelpostvak voordat u een inactief postvak herstelt. Wanneer u een postvak in bewaring houdt, wordt het bewaarbeleid dat aan het postvak is toegewezen, pas verwerkt nadat de bewaarperiode is verwijderd of totdat de bewaarperiode is verlopen. Hierdoor heeft de eigenaar van het doelpostvak de tijd om oude berichten uit het inactieve postvak te beheren. Anders kan het bewaarbeleid oude items verwijderen (of items verplaatsen naar het archiefpostvak, als dit is ingeschakeld) die zijn verlopen op basis van de bewaarinstellingen die zijn geconfigureerd voor het doelpostvak. Zie Een postvak in bewaring in bewaring [plaatsen in](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)Exchange Online.

- **Wat doet de switch AllowLegacyDNMismatch?** In de vorige voorbeelden om een inactief postvak te herstellen, wordt de **schakelknop AllowLegacyDNMismatch** gebruikt om het inactieve postvak te herstellen naar een ander doelpostvak. In een normaal herstelscenario is het doel om inhoud te herstellen waarbij de bron- en doelpostvakken hetzelfde postvak zijn. De cmdlet **New-MailboxRestoreRequest** controleert dus standaard of de waarde van de eigenschap **LegacyExchangeDN** op de bron- en doelpostvakken hetzelfde is. Hiermee voorkomt u dat u per ongeluk een bronpostvak in het verkeerde doelpostvak herstelt. Als u een inactief postvak probeert te herstellen zonder de **switch AllowLegacyDNMismatch** te gebruiken, kan de opdracht mislukken als de bron- en doelpostvakken verschillende waarden hebben voor de **eigenschap LegacyExchangeDN.**

- **U kunt andere parameters gebruiken met de New-MailboxRestoreRequest cmdlet om verschillende herstelscenario's voor inactieve postvakken te implementeren.** U kunt deze opdracht bijvoorbeeld uitvoeren om het archief vanuit het inactieve postvak terug te zetten in het primaire postvak van het doelpostvak.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -SourceIsArchive -TargetMailbox <target mailbox> -TargetRootFolder "Inactive Mailbox Archive" -AllowLegacyDNMismatch
  ```

  U kunt het inactieve primaire postvak ook herstellen in het archief van het doelpostvak door deze opdracht uit te voeren.

  ```powershell
  New-MailboxRestoreRequest -SourceMailbox <inactive mailbox> -TargetMailbox <target mailbox> -TargetIsArchive -TargetRootFolder "Inactive Mailbox" -AllowLegacyDNMismatch
  ```

- **Wat doet de parameter TargetRootFolder?** Zoals eerder uitgelegd, kunt u de parameter **TargetRootFolder** gebruiken om een map op te geven boven aan de mapstructuur (ook wel de hoofdmap genoemd) in het doelpostvak waarin u de inhoud van het inactieve postvak wilt herstellen. Als u deze parameter niet gebruikt, worden postvakitems uit het inactieve postvak samengevoegd in de bijbehorende standaardmappen van het doelpostvak en worden aangepaste mappen opnieuw gemaakt in de hoofdmap van het doelpostvak. In de volgende illustraties worden deze verschillen belicht tussen het niet gebruiken en gebruiken van de parameter **TargetRootFolder.**

  **Maphiërarchie in het doelpostvak wanneer de parameter TargetRootFolder niet wordt gebruikt**

  ![Schermafbeelding wanneer de parameter TargetRootFolder niet wordt gebruikt](../media/76a759af-f483-4d1c-8cc7-243435b5562e.png)

  **Maphiërarchie in het doelpostvak wanneer de parameter TargetRootFolder wordt gebruikt**

  ![Schermafbeelding wanneer de parameter TargetRootFolder wordt gebruikt](../media/300da592-7323-48db-b8a4-07012259d113.png)