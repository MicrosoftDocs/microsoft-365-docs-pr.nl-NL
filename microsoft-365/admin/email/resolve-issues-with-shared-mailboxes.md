---
title: Problemen oplossen met gedeelde postvakken
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Probeer deze oplossingen als u problemen ondervindt met gedeelde postvakken.
ms.openlocfilehash: b45c2eefa8cb4fb5fa34808223efbc1f0023161d
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/24/2020
ms.locfileid: "42806932"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Problemen oplossen met gedeelde postvakken

Als u foutmeldingen ziet bij het maken of gebruiken van een gedeeld postvak, probeert u deze mogelijke oplossingen. 

## <a name="error-when-creating-shared-mailboxes"></a>Fout bij het maken van gedeelde postvakken
<a name="bkmk_Fix"> </a>

Als u het foutbericht ziet, wordt het **proxyadres "smtp:<gedeelde postvaknaam"\>al gebruikt\<door de proxyadressen of LegacyExchangeDN van " naam>". Kies een ander proxyadres,** dit betekent dat u probeert het gedeelde postvak een naam te geven die al in gebruik is. Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2. U kunt dit op twee manieren doen:

  - Gebruik Windows PowerShell. Lees deze blogpost voor instructies: [Create Shared Mailboxes with Same Alias at Different Domains in Office 365](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365) (Gedeelde postvakken maken met dezelfde alias voor verschillende domeinen in Office 365)
    
  - Noem het tweede gedeelde postvak iets anders vanaf het begin om de fout te omzeilen. Wijzig vervolgens in het beheercentrum de naam van het gedeelde postvak in wat u wilt dat het is.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fout als u geen machtigingen hebt verzonden bij het gebruik van een gedeeld postvak

Als u een gedeeld postvak hebt gemaakt en vervolgens probeert een bericht hiervan te verzenden, u dit krijgen:

**Dit bericht kan niet worden verzonden. U hebt niet de toestemming om het bericht namens de opgegeven gebruiker te verzenden.**

Dit bericht wordt weergegeven wanneer Office 365 een probleem met de replicatielatentie ondervindt. Het moet verdwijnen in een uur of zo, wanneer de informatie over uw nieuwe gedeelde mailbox (of toegevoegde gebruiker) wordt gerepliceerd in al onze datacenters. Wacht een uur en probeer dan opnieuw om een bericht te sturen.

## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie verwijderen uit een gedeeld postvak](remove-license-from-shared-mailbox.md)


    

