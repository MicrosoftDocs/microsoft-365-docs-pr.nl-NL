---
title: Microsoft 365-postvak migraties
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Dit artikel bevat een beknopt overzicht van de migraties van Microsoft 365-postvakken en een lijst met cmdlets die worden gebruikt voor migraties.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63080643e4994d6b16e77298907725a827997cef
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546796"
---
# <a name="microsoft-365-mailbox-migrations"></a>Microsoft 365-postvak migraties

Met een hybride implementatie van Exchange kunnen klanten ervoor kiezen om on-premises Exchange-postvakken te verplaatsen naar een [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) -organisatie of Exchange Online-postvakken te verplaatsen naar een [on-premises Exchange](https://docs.microsoft.com/Exchange/exchange-server) -organisatie. Migratie batches worden gebruikt wanneer postvakken worden verplaatst tussen on-premises en Exchange Online-organisaties.

Klanten kunnen statistieken en andere informatie over postvak migraties bekijken met de volgende cmdlets:

- [Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): geeft de standaard statistieken voor een gebruikerspostvak weer, waaronder de status, postvakgrootte, grootte van archief postvak en percentage voltooid.
- [Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): biedt een overzichtslijst met postvak objecten en kenmerken in de organisatie.
- [Get-geadresseerde](https://docs.microsoft.com/powershell/module/exchange/get-recipient): biedt een lijst met bestaande objecten voor e-mail, zoals postvakken, e-mail gebruikers, contactpersonen en distributiegroepen.
- [Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): biedt een gedetailleerde status van een lopende postvak migratie.
- [Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): Hier vindt u informatie over de gebruikers voor het migreren van postvakken.
- [Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): geeft informatie over de status van de huidige migratie batch.
- [Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): Hier vindt u gedetailleerde informatie over de migratiestatus voor een bepaalde gebruiker.
- [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): biedt informatie over postvakken, zoals de grootte, het aantal berichten en de tijd waarop het laatst is geopend.

Zie [cmdlets voor verplaatsen en migreren in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)voor meer informatie over cmdlets.
