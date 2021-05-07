---
title: Module voor voorspellende codering voor Advanced eDiscovery (voorbeeld)
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: jefwan
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: De nieuwe module voor voorspellende codering in Advanced eDiscovery gebruikt machine learning om documenten te analyseren in een revisieset om te voorspellen welke documenten relevant zijn voor uw zaak of onderzoek.
ms.openlocfilehash: 6a3f3b502dfe9efedc785ac3b246f60f13466dcb
ms.sourcegitcommit: ef98b8a18d275e5b5961e63d2b0743d046321737
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/26/2021
ms.locfileid: "52162476"
---
# <a name="predictive-coding-module-for-advanced-ediscovery-preview"></a>Module voor voorspellende codering voor Advanced eDiscovery (voorbeeld)

Met de nieuwe module voor voorspellende codering in Advanced eDiscovery kunt u een model maken en maken om prioriteit te geven aan het controleren van documenten, te beginnen met de meest relevante documenten. Om aan de slag te gaan, kunt u een model maken, maar liefst 50 documenten labelen en vervolgens documenten filteren op modelvoorspellingsscores om relevante niet-relevante documenten te bekijken.

Hier is een kort overzicht van de werkstroom:

1. Open de module voorspellende codering in een revisieset.

   ![Klik in een revisie op de vervolgkeuzelijst Analyseren om naar de module Voorspellende codering te gaan](..\media\PredictiveCoding1.png)

2. Klik op **de pagina Voorspellende coderingsmodellen** op **Nieuw model** om een nieuw voorspellend coderingsmodel te maken.

   ![Een nieuw model maken](..\media\PredictiveCoding2.png)

3. Label ten minste 50 documenten als **Relevant** of **Niet relevant.** Deze labeling wordt gebruikt om het systeem te trainen.

   ![Documenten labelen als relevant of niet relevant voor het trainen van het systeem](..\media\PredictiveCoding3.png)

4. Pas het **filter Voorspellingsscore** voor uw model toe op de revisieset. Ga als volgende te werk:

   1. Klik in de revisieset op **Filters.**
   2. Vouw op **de** flyoutpagina Filters de sectie **Analyse/ML** uit en schakel vervolgens Het selectievakje Voorspellingsscore in voor het model dat u wilt toepassen. 
   3. Geef in **het filter Voorspellingsscore** een voorspellingsscore op. In het filter worden de documenten weergegeven in de revisieset die overeenkomen met de voorspellingsscore.

      ![Een voorspellingsscore opgeven om documenten te filteren](..\media\PredictiveCoding4.png)

5. Controleer de prestaties, status en stabiliteit van uw model.

   ![De prestaties, status en stabiliteit van uw model controleren](..\media\PredictiveCoding5.png)
