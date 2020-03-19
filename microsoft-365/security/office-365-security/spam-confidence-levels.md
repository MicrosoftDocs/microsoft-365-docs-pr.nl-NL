---
title: Vertrouwensniveaus voor spam
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 34681000-0022-4b92-b38a-e32b3ed96bf6
ms.collection:
- M365-security-compliance
description: Wanneer een e-mailbericht via spamfiltering gaat, krijgt het een spamscore toegewezen. Die score is in kaart gebracht aan een individuele Spam Confidence Level (SCL) rating en gestempeld in een X-header. De dienst onderneemt acties op de berichten, afhankelijk van de spam vertrouwen interpretatie van de SCL rating. In de volgende tabel ziet u hoe de verschillende SCL-classificaties worden geïnterpreteerd door de filters en de standaardactie die wordt uitgevoerd op binnenkomende berichten voor elke beoordeling.
ms.openlocfilehash: 65b6f51199e6d8f6ce17a05b28c5bad15d9d1760
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 02/15/2020
ms.locfileid: "42810443"
---
# <a name="spam-confidence-levels"></a>Vertrouwensniveaus voor spam

Wanneer een e-mailbericht via spamfiltering gaat, krijgt het een spamscore toegewezen. Die score is in kaart gebracht aan een individuele Spam Confidence Level (SCL) rating en gestempeld in een X-header. De dienst onderneemt acties op de berichten, afhankelijk van de spam vertrouwen interpretatie van de SCL rating. In de volgende tabel ziet u hoe de verschillende SCL-classificaties worden geïnterpreteerd door de filters en de standaardactie die wordt uitgevoerd op binnenkomende berichten voor elke beoordeling.
  
|**SCL-beoordeling**|**Spam vertrouwen interpretatie**|**Standaardactie**|
|:-----|:-----|:-----|
|-1|Niet-spam afkomstig van een veilige afzender, veilige ontvanger of veilig vermeld IP-adres (vertrouwde partner).|Lever het bericht af bij het postvak IN van de ontvangers.|
|0, 1|Niet-spam omdat het bericht is gescand en bepaald om schoon te zijn.|Lever het bericht af bij het postvak IN van de ontvangers.|
|5, 6|Spam|Lever het bericht af op de map Ongewenste e-mail van de geadresseerden.|
|7, 8, 9|Hoog vertrouwen spam|Lever het bericht af op de map Ongewenste e-mail van de geadresseerden.|
   
> [!TIP]
> SCL ratings van 2, 3, 4, 7 en 8 worden niet vastgesteld door de service. Een SCL rating van 5 of 6 wordt beschouwd als vermoedelijke spam, die minder zeker spam dan een SCL rating van 9, die wordt beschouwd als bepaalde spam. Verschillende acties voor spam en spam met een hoog vertrouwen kunnen worden geconfigureerd via uw beleid voor inhoudsfilter in het Exchange-beheercentrum. Zie [Uw spamfilterbeleid configureren](configure-your-spam-filter-policies.md)voor meer informatie. U ook de SCL-classificatie instellen voor berichten die overeenkomen met specifieke voorwaarden met behulp van e-mailstroomregels (ook wel transportregels genoemd), zoals beschreven in regels voor [de stroomstroom gebruiken om het spamvertrouwenniveau (SCL) in berichten in te stellen.](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md) Als u een e-mailstroomregel gebruikt om SCL van 7, 8 of 9 in te stellen, wordt het bericht behandeld als spam met een hoog vertrouwen. 
  
||
|:-----|
|![Het korte pictogram voor](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **Nieuw in Office 365?**         Ontdek gratis videocursussen voor **Office 365-beheerders en IT-professionals**, aangeboden via LinkedIn Learning.|
   

