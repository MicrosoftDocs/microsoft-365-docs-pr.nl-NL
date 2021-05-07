---
title: Problemen met eDiscovery-bewaring oplossen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: Fouten met betrekking tot wettelijke bewaarnemingen oplossen die zijn toegepast op bewaarders en niet-bewaardergegevensbronnen in Core eDiscovery.
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 04/16/2021
ms.locfileid: "52162598"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a>Problemen met eDiscovery-bewaring oplossen

In dit artikel worden veelvoorkomende problemen beschreven die kunnen optreden met eDiscovery-in- en op te lossen. Het artikel bevat ook aanbevolen procedures om deze problemen te beperken of te voorkomen.

## <a name="recommended-practices"></a>Aanbevolen procedures

Als u het aantal fouten met betrekking tot eDiscovery-bezit wilt beperken, raden we de volgende procedures aan:

- Als een distributie van een wachtpositie nog in behandeling is, met een status van een van beide of , wacht u totdat de distributie van de wachtpositie is voltooid voordat u verdere `On (Pending)` updates aan het maken `Off (Pending)` bent.

- Voeg uw updates samen met een eDiscovery-hold in één bulkaanvraag in plaats van het holdbeleid herhaaldelijk bij te werken voor elke transactie. Als u bijvoorbeeld meerdere gebruikerspostvakken wilt toevoegen aan een bestaand wachtbeleid met de cmdlet [Set-CaseHoldPolicy,](/powershell/module/exchange/set-caseholdpolicy) voert u de opdracht uit (of voegt u deze toe als codeblok aan een script), zodat deze slechts eenmaal wordt uitgevoerd om meerdere gebruikers toe te voegen.

  **Correct**

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **Onjuist**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   In het vorige onjuiste voorbeeld wordt de cmdlet vijf afzonderlijke keren uitgevoerd om de taak te voltooien. Zie de sectie [Meer informatie](#more-information) voor meer informatie over de aanbevolen procedures voor het toevoegen van gebruikers aan een hold-beleid.

- Voordat u contact op neemt met Microsoft Support over eDiscovery-wachtproblemen, voert u de stappen uit in de sectie [Fout/probleem: Wacht](#errorissue-holds-dont-sync) niet synchroniseren om de distributie in de wacht te zetten. Dit proces lost vaak tijdelijke problemen op, waaronder interne serverfouten.

## <a name="errorissue-holds-dont-sync"></a>Fout/probleem: de synchronisatie van de in-en-uit-standen wordt niet gesynchroniseerd

Als u een van de volgende foutberichten ziet bij het in de wacht zetten van beheerders en gegevensbronnen, gebruikt u de oplossingsstappen om het probleem op te lossen.

> Resources: het implementeren van het beleid duurt langer dan verwacht. Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.

> Beleid kan niet worden geïmplementeerd in de inhoudsbron vanwege een tijdelijk probleem Office 365 datacenter. Het huidige beleid wordt niet toegepast op inhoud in de bron, dus de geblokkeerde implementatie heeft geen invloed. Als u dit probleem wilt oplossen, probeert u het beleid opnieuw te herschikken.

> Het is helaas niet mogelijk om de gevraagde wijzigingen in het beleid uit te voeren vanwege een tijdelijke interne serverfout. Probeer het over 30 minuten opnieuw.

### <a name="resolution"></a>Oplossing

1. Verbinding maken naar [Security & Compliance Center PowerShell en](/powershell/exchange/connect-to-scc-powershell) voer de volgende opdracht uit voor een eDiscovery-hold:

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. Bekijk de waarde in de *parameter DistributionDetail.* Zoek naar fouten zoals de volgende:

   > Fout: Resources: het implementeren van het beleid duurt langer dan verwacht. Het kan nog twee uur duren voordat de uiteindelijke implementatiestatus is bijgewerkt, dus kijk over een paar uur terug.

3. Probeer de opdracht **Set-CaseHoldPolicy -RetryDistribution** uit te voeren op het holdbeleid in kwestie; bijvoorbeeld:

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a>Meer informatie

- De richtlijnen voor het bijwerken van wachtbeleid voor meerdere gebruikers in de sectie Aanbevolen procedures zijn het gevolg van het feit dat het systeem gelijktijdige updates van een hold-beleid blokkeert. Dat betekent dat wanneer een bijgewerkt hold-beleid wordt toegepast op nieuwe inhoudslocaties en het holdbeleid in behandeling is, er geen extra inhoudslocaties kunnen worden toegevoegd aan het holdbeleid. Hier zijn enkele dingen die u in gedachten moet houden om u te helpen dit probleem te beperken:
  
  - Elke keer dat een bijgewerkte wachttijd wordt bijgewerkt, wordt deze onmiddellijk in een status in behandeling. De status in behandeling betekent dat de wachtpositie wordt toegepast op inhoudslocaties.
  
  - Als u een script hebt waarin een lus wordt uitgevoerd en locaties één voor één aan beleid worden toegevoegd (vergelijkbaar met het onjuiste voorbeeld dat wordt weergegeven in de sectie Aanbevolen procedures), wordt met de eerste inhoudslocatie (bijvoorbeeld een gebruikerspostvak) het synchronisatieproces gestart dat de status in behandeling activeert. Dat betekent dat de andere gebruikers die in volgende lusjes aan het beleid worden toegevoegd, een foutmelding geven.
  
  - Als uw organisatie een script gebruikt waarin een lus wordt uitgevoerd om de inhoudslocaties voor een hold-beleid bij te werken, moet u het script zo bijwerken dat locaties in één bulkbewerking worden bijgewerkt (zoals wordt weergegeven in het juiste voorbeeld in de sectie Aanbevolen procedures).
