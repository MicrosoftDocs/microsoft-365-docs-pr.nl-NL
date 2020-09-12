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
# <a name="microsoft-365-mailbox-migrations"></a><span data-ttu-id="6159e-103">Microsoft 365-postvak migraties</span><span class="sxs-lookup"><span data-stu-id="6159e-103">Microsoft 365 mailbox migrations</span></span>

<span data-ttu-id="6159e-104">Met een hybride implementatie van Exchange kunnen klanten ervoor kiezen om on-premises Exchange-postvakken te verplaatsen naar een [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) -organisatie of Exchange Online-postvakken te verplaatsen naar een [on-premises Exchange](https://docs.microsoft.com/Exchange/exchange-server) -organisatie.</span><span class="sxs-lookup"><span data-stu-id="6159e-104">With an Exchange-based hybrid deployment, customers can choose to either move on-premises Exchange mailboxes to an [Exchange Online](https://docs.microsoft.com/Exchange/exchange-online) organization or move Exchange Online mailboxes to an [Exchange on-premises](https://docs.microsoft.com/Exchange/exchange-server) organization.</span></span> <span data-ttu-id="6159e-105">Migratie batches worden gebruikt wanneer postvakken worden verplaatst tussen on-premises en Exchange Online-organisaties.</span><span class="sxs-lookup"><span data-stu-id="6159e-105">Migration batches are used when moving mailboxes between on-premises and Exchange Online organizations.</span></span>

<span data-ttu-id="6159e-106">Klanten kunnen statistieken en andere informatie over postvak migraties bekijken met de volgende cmdlets:</span><span class="sxs-lookup"><span data-stu-id="6159e-106">Customers can review statistics and other information about mailbox migrations with the following cmdlets:</span></span>

- <span data-ttu-id="6159e-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): geeft de standaard statistieken voor een gebruikerspostvak weer, waaronder de status, postvakgrootte, grootte van archief postvak en percentage voltooid.</span><span class="sxs-lookup"><span data-stu-id="6159e-107">[Get-MoveRequestStatistics](https://docs.microsoft.com/powershell/module/exchange/get-moverequeststatistics): Provides default statistics for a user mailbox, which includes the status, mailbox size, archive mailbox size, and percentage complete.</span></span>
- <span data-ttu-id="6159e-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): biedt een overzichtslijst met postvak objecten en kenmerken in de organisatie.</span><span class="sxs-lookup"><span data-stu-id="6159e-108">[Get-Mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/Get-Mailbox
): Provides a summary list of mailbox objects and attributes in the organization.</span></span>
- <span data-ttu-id="6159e-109">[Get-geadresseerde](https://docs.microsoft.com/powershell/module/exchange/get-recipient): biedt een lijst met bestaande objecten voor e-mail, zoals postvakken, e-mail gebruikers, contactpersonen en distributiegroepen.</span><span class="sxs-lookup"><span data-stu-id="6159e-109">[Get-Recipient](https://docs.microsoft.com/powershell/module/exchange/get-recipient): Provides a list of existing mail-enabled objects such as mailboxes, mail users, contacts, and distribution groups.</span></span>
- <span data-ttu-id="6159e-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): biedt een gedetailleerde status van een lopende postvak migratie.</span><span class="sxs-lookup"><span data-stu-id="6159e-110">[Get-MoveRequest](https://docs.microsoft.com/powershell/module/exchange/get-moverequest): Provides a detailed status of an ongoing mailbox migration.</span></span>
- <span data-ttu-id="6159e-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): Hier vindt u informatie over de gebruikers voor het migreren van postvakken.</span><span class="sxs-lookup"><span data-stu-id="6159e-111">[Get-MigrationUser](https://docs.microsoft.com/powershell/module/exchange/get-migrationuser): Provides information about the mailbox move and migration users.</span></span>
- <span data-ttu-id="6159e-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): geeft informatie over de status van de huidige migratie batch.</span><span class="sxs-lookup"><span data-stu-id="6159e-112">[Get-MigrationBatch](https://docs.microsoft.com/powershell/module/exchange/get-migrationbatch): Provides information on the status of current migration batch.</span></span>
- <span data-ttu-id="6159e-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): Hier vindt u gedetailleerde informatie over de migratiestatus voor een bepaalde gebruiker.</span><span class="sxs-lookup"><span data-stu-id="6159e-113">[Get-MigrationUserStatistics](https://docs.microsoft.com/powershell/module/exchange/get-migrationuserstatistics): Provides detailed information about the migration status for a specific user.</span></span>
- <span data-ttu-id="6159e-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): biedt informatie over postvakken, zoals de grootte, het aantal berichten en de tijd waarop het laatst is geopend.</span><span class="sxs-lookup"><span data-stu-id="6159e-114">[Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics): Provides information about mailboxes, such as size, the number of messages, and the last accessed time.</span></span>

<span data-ttu-id="6159e-115">Zie [cmdlets voor verplaatsen en migreren in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)voor meer informatie over cmdlets.</span><span class="sxs-lookup"><span data-stu-id="6159e-115">For more information about cmdlets, see [Move and Migration cmdlets in Exchange Online](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell).</span></span>
