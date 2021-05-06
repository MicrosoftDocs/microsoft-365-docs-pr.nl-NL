---
title: Near duplicate detection - eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Gebruik near duplicate detection to group textually similar documents when analyzeing case data in Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 255531897a1706904005034c56cab00d0032b7f3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/26/2020
ms.locfileid: "52161539"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>Bijna dubbele detectie in Advanced eDiscovery

Overweeg een reeks documenten te herzien waarin een subset is gebaseerd op dezelfde sjabloon en meestal dezelfde standaardtaal heeft, met hier en daar enkele verschillen. Als een revisor deze subset kon identificeren, een van deze subsets grondig kon bekijken en de verschillen voor de rest kon bekijken, zouden ze geen unieke informatie hebben gemist terwijl ze slechts een fractie van de tijd hadden genomen om alle documenten te lezen. Near duplicate detection groups textually similar documents together to help you make your review process more efficient.

## <a name="how-does-it-work"></a>Hoe werkt dit?

Wanneer er bijna dubbele detectie wordt uitgevoerd, parseert het systeem elk document met tekst. Vervolgens wordt elk document met elkaar vergeleken om te bepalen of de overeenkomst groter is dan de ingesteld drempelwaarde. Als dat zo is, worden de documenten gegroepeerd. Wanneer alle documenten zijn vergeleken en gegroepeerd, wordt een document uit elke groep gemarkeerd als het 'draaipunt'. bij het controleren van uw documenten kunt u eerst een draaipunt bekijken en de andere documenten in dezelfde bijna dubbele set bekijken, waarbij u zich richt op het verschil tussen het draaitabel en het document dat wordt beoordeeld.
