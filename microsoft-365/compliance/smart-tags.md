---
title: Slimme tags instellen in Advanced eDiscovery
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
ROBOTS: NOINDEX, NOFOLLOW
description: Met slimme tags kunt u de mogelijkheden voor machine learning toepassen wanneer u inhoud in een Advanced eDiscovery bekijkt. Gebruik slimme taggroepen om de resultaten weer te geven van machine-learningdetectiemodellen, zoals het privilegemodel voor advocatenclient.
ms.openlocfilehash: 3d3852a13410a3aa57932e19031cc5d00ce52a96
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "52161441"
---
# <a name="set-up-smart-tags-in-advanced-ediscovery"></a>Slimme tags instellen in Advanced eDiscovery

Met machine learning (ML) in Advanced eDiscovery kunt u het beslissingsproces efficiënter maken bij het controleren van casedocumenten in een revisieset. Slimme tags zijn een manier om de ML te brengen waar de beslissingen worden opgenomen: bij het taggen van documenten tijdens de controle. Wanneer u een groep met slimme tags maakt, worden de beslissingen die het resultaat zijn van het ML-model dat u hebt gekoppeld aan de groep slimme tags, weergegeven in lijn met de tags in de taggroep. Zo kunt u de ML resultaten in de regel bekijken wanneer u specifieke documenten bekijkt.

## <a name="how-to-set-up-a-smart-tag-group"></a>Een groep met slimme tags instellen

1. Klik in een revisieset op **Controleset beheren** en klik vervolgens **op Tags beheren.**

2. Klik **op Taggroep toevoegen** en selecteer vervolgens Groep Slimme tag **toevoegen.**

3. Selecteer het ML model dat u wilt koppelen aan de taggroep.
    
   Hiermee worden een taggroep en *N-onderliggende* tags gemaakt, waarbij *N* het aantal mogelijke uitvoers van het model is. Het detectiemodel voor [advocaten-clientrechten](attorney-privilege-detection.md) heeft bijvoorbeeld twee mogelijke uitvoer: 

   - **Positief:** gebruik deze code om documenten te taggen die inhoud bevatten die is geprivilegieerd door een klant.
   
   - **Negatief:** gebruik deze code om documenten te taggen die geen bevoorrechte inhoud van de advocatenclient bevatten.
    
    Als u dit model selecteert, wordt er een taggroep met twee onderliggende tags gemaakt (een onderliggende tag met de naam **Positief** en de andere met de naam **Negatief)** voor de revisieset. In dit voorbeeld komt elke onderliggende tag overeen met een van de mogelijke uitvoer van het detectiemodel voor advocaten-clientvoorrechten.

4. Desgewenst kunt u de naam van de taggroep en de onderliggende tags wijzigen. U kunt bijvoorbeeld de naam van de tag **Positief** wijzigen in **Bevoorrecht** en negatieve **tag** in Niet **geprivilegieerd.**

## <a name="how-to-use-smart-tags"></a>Slimme tags gebruiken

Wanneer u een document controleert, worden de resultaten van het model weergegeven naast de juiste onderliggende tag. Als u bijvoorbeeld een smart tag-groep hebt voor detectie van advocaten-clientprivilege's en u een document bekijkt dat mogelijk is geprivilegieerd, wordt de reden voor die conclusie weergegeven naast de juiste tag. Het is belangrijk om te weten dat de tag niet automatisch wordt toegepast op het document. De revisor neemt de beslissing over het taggen van het document.
