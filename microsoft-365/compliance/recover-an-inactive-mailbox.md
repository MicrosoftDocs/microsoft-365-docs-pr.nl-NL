---
title: Een inactief postvak herstellen
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
ms.assetid: 35d0ecdb-7cb0-44be-ad5c-69df2f8f8b25
ms.custom: seo-marvel-apr2020
description: Informatie over het herstellen van de inhoud van een inactief postvak in Office 365 door het te converteren naar een nieuw postvak met de inhoud van het inactieve postvak.
ms.openlocfilehash: e7f5ea9e3d47bf6b7ee6de495d2f5f47984cdf8f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/19/2021
ms.locfileid: "52162115"
---
# <a name="recover-an-inactive-mailbox"></a>Een inactief postvak herstellen

Een inactief postvak (een type postvak dat wordt verwijderd) wordt gebruikt om de e-mail van een voormalige werknemer te behouden nadat hij of zij uw organisatie heeft verlaat. Als die werknemer terugkeert naar uw organisatie of als een andere werknemer de taakverantwoordelijkheden van de voormalige werknemer op zich neemt, kunt u de inhoud van het inactieve postvak op twee manieren beschikbaar stellen aan een gebruiker:

- **Een inactief postvak herstellen.** Als de voormalige werknemer terugkeert naar uw organisatie of als een nieuwe werknemer wordt aangenomen om de taaktaken van de voormalige werknemer op zich te nemen, kunt u de inhoud van het inactieve postvak herstellen. Met deze methode wordt het inactieve postvak ge converteerd naar een nieuw, actief postvak dat de inhoud van het inactieve postvak bevat. Nadat het is hersteld, bestaat het inactieve postvak niet meer. In de procedures in dit onderwerp wordt deze methode beschreven.

- **Een inactief postvak herstellen.** Als een andere werknemer de taakverantwoordelijkheden van de voormalige werknemer op zich neemt of als een andere gebruiker toegang nodig heeft tot de inhoud van het inactieve postvak, kunt u de inhoud van het inactieve postvak herstellen (of samenvoegen) naar een bestaand postvak. U kunt het archief ook herstellen vanuit een inactief postvak. Zie Een inactief postvak terugzetten in Office 365 voor de procedures [voor deze methode.](restore-an-inactive-mailbox.md)

Zie de [sectie Meer](#more-information) informatie voor meer informatie over de verschillen tussen het herstellen en herstellen van een inactief postvak en voor een beschrijving van wat er gebeurt wanneer een inactief postvak wordt hersteld.

> [!NOTE]
> U kunt een inactief postvak dat is geconfigureerd met een automatisch uitbreidend archief, niet herstellen of herstellen. Als u gegevens wilt herstellen uit een inactief postvak met een automatisch uitbreidend archief, gebruikt u inhoud zoeken om de gegevens uit het postvak te exporteren en vervolgens te importeren in een ander postvak. Zie de volgende onderwerpen voor instructies:
>
> - [Inhoud zoeken](content-search.md)
> - [Zoekresultaten voor inhoud exporteren](export-search-results.md)

## <a name="requirements-to-recover-an-inactive-mailbox"></a>Vereisten voor het herstellen van een inactief postvak

- U moet powershell Exchange Online gebruiken om een inactief postvak te herstellen. U kunt het beheercentrum Exchange (EAC) niet gebruiken. Zie [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) (Verbinding maken met Exchange Online PowerShell) voor stapsgewijze instructies.

- Voer de volgende opdracht uit om identiteitsgegevens op te halen voor de inactieve postvakken in uw organisatie.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly | Format-List Name,DistinguishedName,ExchangeGuid,PrimarySmtpAddress
  ```

  Gebruik de gegevens die door deze opdracht worden geretourneerd om een specifiek inactief postvak te herstellen.

## <a name="recover-inactive-mailboxes"></a>Inactieve postvakken herstellen

Gebruik de **cmdlet Nieuw postvak** met de parameter  *InactiveMailbox*  om een inactief postvak te herstellen.

1. Maak een variabele die de eigenschappen van het inactieve postvak bevat.

   ```powershell
   $InactiveMailbox = Get-Mailbox -InactiveMailboxOnly -Identity <identity of inactive mailbox>
   ```

   > [!IMPORTANT]
   > Gebruik in de vorige opdracht de waarde van de eigenschap **DistinguishedName** of **ExchangeGUID** om het inactieve postvak te identificeren. Deze eigenschappen zijn uniek voor elk postvak in uw organisatie, terwijl het mogelijk is dat een actief en inactief postvak hetzelfde primaire SMTP-adres heeft.

2. In dit voorbeeld worden de eigenschappen gebruikt die zijn verkregen in de vorige opdracht en wordt het inactieve postvak hersteld naar een actief postvak voor de gebruiker Ann Beebe. Zorg ervoor dat de waarden die zijn opgegeven voor de parameters  *Naam*  en  *MicrosoftOnlineServicesID*  uniek zijn binnen uw organisatie.

   ```powershell
   New-Mailbox -InactiveMailbox $InactiveMailbox.DistinguishedName -Name annbeebe -FirstName Ann -LastName Beebe -DisplayName "Ann Beebe" -MicrosoftOnlineServicesID Ann.Beebe@contoso.com -Password (ConvertTo-SecureString -String 'P@ssw0rd' -AsPlainText -Force) -ResetPasswordOnNextLogon $true
   ```

   Het primaire SMTP-adres voor het herstelde inactieve postvak heeft dezelfde waarde als het adres dat is opgegeven door de *parameter MicrosoftOnlineServicesID.*

Nadat u een inactief postvak hebt hersteld, wordt er ook een nieuw gebruikersaccount gemaakt. U moet dit gebruikersaccount activeren door een licentie toe te wijzen. Als u een licentie wilt toewijzen in Microsoft 365 beheercentrum, zie Gebruikers toevoegen en tegelijkertijd licenties [toewijzen.](../admin/add-users/add-users.md)

## <a name="more-information"></a>Meer informatie

- **Wat is het belangrijkste verschil tussen het herstellen en herstellen van een inactief postvak?** Wanneer u een inactief postvak herstelt, wordt het postvak geconverteerd naar een nieuw postvak, blijven de inhoud en mapstructuur van het inactieve postvak behouden en is het postvak gekoppeld aan een nieuw gebruikersaccount. Nadat het is hersteld, bestaat het inactieve postvak niet meer en zijn wijzigingen in de inhoud in het nieuwe postvak van invloed op de inhoud die oorspronkelijk in de wacht stond in het inactieve postvak. Wanneer u een inactief postvak herstelt, wordt de inhoud echter alleen gekopieerd naar een ander postvak. Het inactieve postvak blijft behouden en blijft een inactief postvak. Wijzigingen in de inhoud in het doelpostvak hebben geen invloed op de oorspronkelijke inhoud in het inactieve postvak. Het inactieve postvak kan nog steeds worden doorzocht met In-Place eDiscovery, de inhoud ervan kan worden hersteld naar een ander postvak of op een later tijdstip worden hersteld of verwijderd.

- **Wat gebeurt er wanneer u een inactief postvak herstelt?** Wanneer u een inactief postvak herstelt, treden de volgende dingen op:

  - De wacht die is toegepast op een inactief postvak wordt gewijzigd of verwijderd op basis van het type wacht die is toegepast op het inactieve postvak voordat het werd hersteld.

    - **Procesvoering.** Als De procedure voor het inactief postvak is ingeschakeld, wordt het verwijderd uit het herstelde postvak.

    - **In-Place Hold In-Place** Holds worden verwijderd uit het herstelde postvak. Dit betekent dat het herstelde postvak wordt verwijderd als een bronpostvak uit In-Place eDiscoveryIn-Place zoeken.

    - **Microsoft 365 bewaarbeleid met Bewaringsvergrendeling.** Als het inactieve postvak is toegewezen aan een bewaarbeleid met Bewaringsvergrendeling (een vergrendeld bewaarbeleid *genoemd),* wordt het herstelde postvak toegewezen aan hetzelfde vergrendelde bewaarbeleid. Zie [ Bewaringsvergrendeling gebruiken om wijzigingen in bewaarbeleid en bewaarlabelbeleid te beperken voor meer informatie over vergrendeld[bewaarbeleid.](retention-preservation-lock.md)

    - **Microsoft 365 bewaarbeleid zonder Bewaringsvergrendeling.** Het inactieve postvak wordt verwijderd uit een ontgrendeld Microsoft 365 bewaarbeleid dat erop is toegepast. De bewaring van rechtszaken is echter ingeschakeld in het herstelde postvak om te voorkomen dat postvakinhoud wordt verwijderd op basis van een organisatiebreed bewaarbeleid dat inhoud verwijdert die ouder is dan een bepaalde leeftijd. U kunt de procedure in de wacht houden of verwijderen. Zie Een proces in de wacht [houden voor meer informatie.](create-a-litigation-hold.md)

  - De herstelperiode voor één item (die wordt gedefinieerd door de eigenschap **RetainDeletedItemsFor)** is ingesteld op 30 dagen. Wanneer een nieuw postvak wordt gemaakt in Exchange Online, wordt deze bewaarperiode ingesteld op 14 dagen. Als u dit instelt op de maximumwaarde van 30 dagen, hebt u meer tijd om gegevens te herstellen die permanent zijn verwijderd (of verwijderd) uit het inactieve postvak. U kunt ook het herstel van één item uitschakelen of de herstelperiode voor één item instellen op de standaardwaarde van 14 dagen. Zie Herstel van één item voor een postvak in- [of uitschakelen voor meer informatie.](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-single-item-recovery)

  - Bewaar bewaring is ingeschakeld en de duur van de bewaring is ingesteld op 30 dagen. Dit betekent dat het standaard bewaarbeleid Exchange de hele organisatie en alle Exchange-brede Microsoft 365 bewaarbeleidsregels die aan het nieuwe postvak zijn toegewezen, niet worden verwerkt voor 30 dagen. Dit geeft de terugkerende werknemer of de nieuwe eigenaar van het herstelde inactieve postvak de tijd om de oude berichten te beheren. Anders worden in het Exchange- of Microsoft 365-bewaarbeleid mogelijk oude postvakitems verwijderd (of items naar het archiefpostvak verplaatst als dit is ingeschakeld) die zijn verlopen op basis van de instellingen die zijn geconfigureerd voor het bewaarbeleid van Exchange of Microsoft 365. Na 30 dagen verloopt de bewaringstermijn, is de eigenschap **RetentionHoldEnabled** postvak ingesteld op Onwaar **en** begint de beheerde mapassistent met het verwerken van het beleid dat aan het postvak is toegewezen. Als u deze extra tijd niet nodig hebt, kunt u de bewaring gewoon verwijderen. U kunt ook de duur van de bewaring verlengen met de opdracht **Set-Mailbox -EndDateForRetentionHold.** Zie Een postvak in bewaring [plaatsen voor meer informatie.](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold)

- **Houd het herstelde postvak in de wacht als u de oorspronkelijke status van het inactieve postvak wilt behouden.** Als u wilt voorkomen dat de nieuwe eigenaar van het postvak of het bewaarbeleid berichten definitief uit het herstelde inactieve postvak verwijderd, kunt u het postvak in bewaring plaatsen. Zie Een proces in de wacht [houden voor meer informatie.](./create-a-litigation-hold.md)

- **Welke gebruikers-id kunt u gebruiken bij het herstellen van een inactief postvak?** Wanneer u een inactief postvak herstelt, kan de waarde die u opgeeft voor de  *parameter MicrosoftOnlineServicesID,*  verschillen van de oorspronkelijke waarde die is gekoppeld aan het inactieve postvak. U kunt ook de oorspronkelijke gebruikers-id gebruiken. Maar zoals eerder vermeld, moet u ervoor zorgen dat de waarden die worden gebruikt voor  *Naam*  en  *MicrosoftOnlineServicesID*  uniek zijn binnen uw organisatie wanneer u het inactieve postvak herstelt.

- **Wat gebeurt er als de bewaarperiode voor het postvak voor het inactieve postvak niet is verlopen?** Als een inactief postvak minder dan 30 dagen geleden is verwijderd, kunt u de opdracht **Nieuw-Postvak -InactiveMailbox** niet gebruiken om het te herstellen. U moet het herstellen door het bijbehorende gebruikersaccount te herstellen. Zie Een gebruiker uit uw organisatie [verwijderen voor meer informatie.](../admin/add-users/delete-a-user.md)

- **Hoe weet u of de bewaarperiode voor een postvak met een zacht verwijderd postvak voor een inactief postvak is verlopen?** Voer de volgende opdracht uit.

  ```powershell
  Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | Format-List ExternalDirectoryObjectId
  ```

  Als er geen waarde is voor de eigenschap **ExternalDirectoryObjectId,** is de bewaarperiode van het postvak verlopen en kunt u het inactieve postvak herstellen door de opdracht **Nieuw-Postvak -InactiveMailbox** uit te voeren. Als er een waarde is voor de eigenschap **ExternalDirectoryObjectId,** is de bewaarperiode van het postvak met een zachte verwijderde postvak niet verlopen en moet u het postvak herstellen door het gebruikersaccount te herstellen. Zie [Een gebruiker uit uw organisatie verwijderen.](../admin/add-users/delete-a-user.md)

- **Overweeg het archiefpostvak in te stellen nadat u een inactief postvak hebt hersteld.** Hierdoor kan de terugkerende gebruiker of nieuwe werknemer oude berichten naar het archiefpostvak verplaatsen. En wanneer de bewaring verloopt, worden items die twee jaar of ouder zijn, verplaatst met het archiefbeleid dat deel uitmaakt van het standaard bewaarbeleid Exchange dat is toegewezen aan Exchange Online-postvakken items die twee jaar of ouder zijn, naar het archiefpostvak. Als u het archiefpostvak niet inschakelen, blijven items ouder dan twee jaar in het primaire postvak van de gebruiker staan. Zie Archiefpostvakken [inschakelen voor](enable-archive-mailboxes.md)meer informatie.