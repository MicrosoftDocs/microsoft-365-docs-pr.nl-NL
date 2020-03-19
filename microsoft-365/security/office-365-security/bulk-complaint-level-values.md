---
title: Bulk Complaint Level waarden, bulk mailers, BCL niveaus, hoe BCL werkt, BCL ratings, Antispam, Antispam header, bulk mail filtering, stop bulk mail
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/23/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Meer informatie over de BCL-waarden (Bulk Complain Level) in Office 365.
ms.openlocfilehash: b0eb922323421834eae77b8c5430f1bd8f48c8ee
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 01/29/2020
ms.locfileid: "42806099"
---
# <a name="bulk-complaint-level-values"></a>Waarden op bulkklachtenniveau

Bulkmailers variëren in hun verzendpatronen, het maken van inhoud en het maken van lijstacquisitiepraktijken. Sommige zijn goede bulk mailers die wilde berichten met relevante inhoud te sturen naar hun abonnees. Deze berichten genereren weinig klachten van ontvangers. Andere bulkmailers sturen ongevraagde berichten die sterk op spam lijken en veel klachten van ontvangers genereren.

Om onderscheid te maken tussen dit soort bulkmailers, krijgen berichten van bulkmailers een BCL-classificatie (Bulk Complaint Level) toegewezen. BCL ratings variëren van 1 tot 9, afhankelijk van hoe waarschijnlijk de bulk mailer is om klachten te genereren. Een afzender met een rating van BCL 9 zal waarschijnlijk veel klachten van ontvangers genereren, terwijl een rating van BCL 3 waarschijnlijk niet veel klachten zal genereren. Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen. Zie [Kopteksten voor antispamberichten](anti-spam-message-headers.md)voor meer informatie over deze berichtkoptekst.

Aangezien een bulkmailer met een rating van 9 waarschijnlijk klachten genereert, is de standaard BCL 7. Dit betekent dat bulkmails worden geaccepteerd totdat het klachtenniveau van 7 en e-mail daarna niet meer worden geaccepteerd. Hoe lager de beoordeling, hoe minder bulkpost wordt geaccepteerd. Als uw gebruikers zijn, en hun werk is, gevoelig voor bulk mail, en uw BCL is ingesteld op 4, dan is er geen bulk mail met een hogere BCL dan 4 zal worden geaccepteerd.

U BCL-waarden gebruiken om het gewenste niveau van bulkfiltering in te stellen die uw organisatie nodig heeft door de stappen te volgen in [Uw beleid voor spamfilters configureren.](configure-your-spam-filter-policies.md)

In de volgende tabel worden de BCL-waarden beschreven die momenteel worden gebruikt.

|||
|:-----|:-----|
|**BCL-waarde**|**Beschrijving**|
|0|Het bericht is niet van een afzender in bulk.|
|1, 2, 3|Het bericht is van een bulk afzender die weinig klachten genereert.|
|4, 5, 6, 7|Het bericht is van een bulk afzender die een gemengd aantal klachten genereert.|
|8, 9|Het bericht is van een bulk afzender die een groot aantal klachten genereert.|
