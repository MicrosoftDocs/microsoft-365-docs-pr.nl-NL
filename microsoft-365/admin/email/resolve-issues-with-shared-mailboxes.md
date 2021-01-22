---
title: Problemen met gedeelde postvakken oplossen
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Probeer deze oplossingen als u problemen hebt met gedeelde postvakken.
ms.openlocfilehash: ba62db76edff6e4ab3d738ed0af8db2a40c18394
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926484"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Problemen met gedeelde postvakken oplossen

Als u foutberichten ziet bij het maken of gebruiken van een gedeeld postvak, kunt u deze mogelijke oplossingen proberen. 

## <a name="error-when-creating-shared-mailboxes"></a>Fout bij het maken van gedeelde postvakken
<a name="bkmk_Fix"> </a>

Als u het foutbericht ziet, wordt het proxyadres 'smtp:<naam van het gedeelde postvak' al gebruikt door de **\> proxyadressen of LegacyExchangeDN van " \<name> " . Kies een ander proxyadres.** Dit betekent dat u probeert het gedeelde postvak een naam te geven die al in gebruik is. Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2. U kunt dit op twee manieren doen:

  - Gebruik Windows PowerShell. Zie dit blogbericht voor instructies: Gedeelde postvakken [met dezelfde alias maken op verschillende domeinen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Noem het tweede gedeelde postvak iets anders om de fout te voorkomen. Wijzig vervolgens in het beheercentrum de naam van het gedeelde postvak.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fout over het niet hebben van machtigingen voor verzenden bij het gebruik van een gedeeld postvak

Als u een gedeeld postvak hebt gemaakt en vervolgens probeert er een bericht van te verzenden, krijgt u mogelijk het volgende:

**Dit bericht kan niet worden verzonden. U bent niet machtigingen om het bericht te verzenden namens de opgegeven gebruiker.**

Dit bericht wordt weergegeven wanneer Microsoft 365 een replicatielatentieprobleem ondervindt. Het duurt ongeveer een uur voordat de informatie over het nieuwe gedeelde postvak (of de toegevoegde gebruiker) in al onze datacenters wordt gerepliceerd. Wacht een uur en probeer vervolgens opnieuw een bericht te verzenden.

## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)


    

