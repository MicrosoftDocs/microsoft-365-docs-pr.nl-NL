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
search.appverid:
- BCS160
- MET150
- MOE150
description: Probeer deze oplossingen als u problemen ondervindt met gedeelde postvakken.
ms.openlocfilehash: c889d3aa2fab8c2dce4cc2a8a00ef49a905363a1
ms.sourcegitcommit: 9a764c2aed7338c37f6e92f5fb487f02b3c4dfa1
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 10/13/2020
ms.locfileid: "48445505"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Problemen met gedeelde postvakken oplossen

Als er foutberichten worden weergegeven wanneer u een gedeeld postvak maakt of gebruikt, kunt u deze oplossingen proberen. 

## <a name="error-when-creating-shared-mailboxes"></a>Fout bij het maken van gedeelde postvakken
<a name="bkmk_Fix"> </a>

Als u het foutbericht **' SMTP: <gedeelde postvaknaam ' ziet, wordt dit \> al gebruikt door de proxyadressen of LegacyExchangeDN van ' \<name> '. Kies een ander proxyadres**, dat betekent dat u het gedeelde Postvak probeert een naam te geven die al in gebruik is. Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2. U kunt dit op twee manieren doen:

  - Gebruik Windows PowerShell. Bekijk dit blogbericht voor instructies: [gedeelde postvakken met dezelfde alias voor verschillende domeinen maken](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Naam het tweede gedeelde Postvak iets anders dan de fout. Wijzig vervolgens in het Beheercentrum de naam van het gedeelde Postvak naar de gewenste waarde.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Foutmelding over het niet verzenden van machtigingen bij gebruik van een gedeeld postvak

Als u een gedeeld postvak hebt gemaakt en daarna een bericht verzendt, kunt u dit als volgt doen:

**Dit bericht kan niet worden verzonden. U bent niet gemachtigd om het bericht te verzenden namens de opgegeven gebruiker.**

Dit bericht wordt weergegeven wanneer Microsoft 365 een replicatielatentie probleem ondervindt. De werkstroom moet binnen een uur plaatsvinden, wanneer de informatie over uw nieuwe gedeelde Postvak (of een extra gebruiker) wordt gerepliceerd over al uw gegevenscentra. Wacht een uur en probeer het nogmaals met een bericht te verzenden.

## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)


    

