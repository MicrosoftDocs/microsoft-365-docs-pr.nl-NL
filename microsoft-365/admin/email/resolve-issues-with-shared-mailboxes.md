---
title: Problemen met gedeelde postvakken oplossen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
search.appverid:
- BCS160
- MET150
- MOE150
description: Probeer deze oplossingen als u problemen ondervindt met gedeelde postvakken.
ms.openlocfilehash: 52aac8ab6936dfeba2ae4b5b7a80c45029ec6105
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628745"
---
# <a name="resolve-issues-with-shared-mailboxes"></a>Problemen met gedeelde postvakken oplossen

Als u foutmeldingen ziet bij het maken of gebruiken van een gedeeld postvak, probeert u deze mogelijke oplossingen. 

## <a name="error-when-creating-shared-mailboxes"></a>Fout bij het maken van gedeelde postvakken
<a name="bkmk_Fix"> </a>

Als u het foutbericht ziet, **wordt het proxyadres 'smtp:<gedeelde postvaknaam'\>al gebruikt\<door de proxyadressen of LegacyExchangeDN van "name>". Kies een ander proxyadres,** dit betekent dat u het gedeelde postvak een naam probeert te geven die al in gebruik is. Stel bijvoorbeeld dat u gedeelde postvakken wilt maken met de naam info@domein1 en info@domein2. U kunt dit op twee manieren doen:

  - Gebruik Windows PowerShell. Zie dit blogbericht voor instructies: [Gedeelde postvakken maken met dezelfde alias bij verschillende domeinen](https://www.cogmotive.com/blog/office-365-tips/create-shared-mailboxes-with-same-alias-at-different-domains-in-office-365)
    
  - Geef het tweede gedeelde postvak iets anders dan het begin om de fout te omzeilen. Wijzig vervolgens in het beheercentrum de naam van het gedeelde postvak naar wat u wilt dat het is.

## <a name="error-about-not-having-send-permissions-when-using-a-shared-mailbox"></a>Fout over het niet verzenden van machtigingen bij het gebruik van een gedeeld postvak

Als u een gedeeld postvak hebt gemaakt en vervolgens probeert er een bericht van te verzenden, krijgt u mogelijk het gewenste bericht:

**Dit bericht kan niet worden verzonden. U hebt geen toestemming om het bericht namens de opgegeven gebruiker te verzenden.**

Dit bericht wordt weergegeven wanneer Microsoft 365 een replicatielatentieprobleem ondervindt. Het moet verdwijnen in een uur of zo, wanneer de informatie over uw nieuwe gedeelde postvak (of toegevoegde gebruiker) wordt gerepliceerd in al onze datacenters. Wacht een uur en probeer dan opnieuw om een bericht te verzenden.

## <a name="related-articles"></a>Verwante artikelen

[Meer over gedeelde postvakken](about-shared-mailboxes.md)

[Een gedeeld postvak maken](create-a-shared-mailbox.md)

[Een gedeeld postvak configureren](configure-a-shared-mailbox.md)

[Een gebruikerspostvak converteren naar een gedeeld postvak](convert-user-mailbox-to-shared-mailbox.md)

[Een licentie uit een gedeeld postvak verwijderen](remove-license-from-shared-mailbox.md)


    

