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
description: Er kunnen fouten optreden bij het instellen van gedeelde postvakken. Probeer deze oplossingen als u problemen hebt met gedeelde postvakken.
ms.openlocfilehash: 89cdfbe29ab035b1eb6c3a0183629eef59d67477
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706128"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Problemen met gedeelde postvakken oplossen

Als u foutberichten ziet bij het maken of gebruiken van een gedeeld postvak, probeert u deze mogelijke oplossingen. 

## <a name="error-when-creating-shared-mailboxes"></a>Fout bij het maken van gedeelde postvakken
<a name="bkmk_Fix"> </a>

Als u het foutbericht ziet, wordt het proxyadres 'smtp:<naam van gedeeld postvak' al gebruikt door de **\> proxyadressen of LegacyExchangeDN of ' \<name> '. Kies een ander proxyadres.** Dit betekent dat u probeert het gedeelde postvak een naam te geven die al in gebruik is. Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2. U kunt dit op twee manieren doen:

  - Gebruik Windows PowerShell. Zie dit blogbericht voor instructies: [Gedeelde postvakken maken met dezelfde alias bij verschillende domeinen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Noem het tweede gedeelde postvak een andere naam dan het begin om de fout te voorkomen. Wijzig vervolgens in het beheercentrum de naam van het gedeelde postvak in wat u wilt.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fout over het niet hebben van machtigingen voor verzenden bij het gebruik van een gedeeld postvak

Als u een gedeeld postvak hebt gemaakt en er vervolgens een bericht van probeert te verzenden, krijgt u mogelijk het volgende:

**Dit bericht kan niet worden verzonden. U hebt niet de machtiging om het bericht namens de opgegeven gebruiker te verzenden.**

Dit bericht wordt weergegeven wanneer Microsoft 365 een replicatielatentieprobleem ondervindt. De gegevens over uw nieuwe gedeelde postvak (of toegevoegde gebruiker) worden over een uur of zo gerepliceerd in al onze datacenters. Wacht een uur en probeer het opnieuw om een bericht te verzenden.

## <a name="related-content"></a>Verwante inhoud

[Info over gedeelde postvakken](about-shared-mailboxes.md) (artikel)\
[Een gedeeld postvak](create-a-shared-mailbox.md) maken (artikel)\
[Een gedeeld postvak configureren](configure-a-shared-mailbox.md) (artikel)\
[Het postvak van een gebruiker converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md) (artikel)\
[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md) (artikel)


    

