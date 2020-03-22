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
description: Meer informatie over bcl-waarden (bulkbomplain level) in Office 365.
ms.openlocfilehash: 6b90064db7dd9b27fdc729b65fb798dfbe756da7
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 03/21/2020
ms.locfileid: "42895391"
---
# <a name="bulk-complaint-level-bcl-in-office-365"></a>Bulkklachtenniveau (BCL) in Office 365

Bulkmailers variëren in hun verzendpatronen, het maken van inhoud en acquisitiepraktijken voor ontvangers. Sommige zijn goede bulk mailers die gewenste berichten met relevante inhoud te sturen naar hun abonnees. Deze berichten genereren weinig klachten van ontvangers. Andere bulkmailers sturen ongevraagde berichten die sterk op spam lijken en veel klachten van ontvangers genereren. Berichten van een bulkmailer staan bekend als bulkmail of grijze e-mail.

Als u berichten wilt onderscheiden van verschillende typen bulkmailers, krijgt binnenkomende e-mail van bulkmailers naar Office 365 (Exchange Online of zelfstandige Exchange Online Protection (EOP) zonder Exchange Online-postvakken) een bulkklachtenniveau (BCL) dat is toegevoegd aan het bericht in een X-header. De BCL is vergelijkbaar met het [spamvertrouwensniveau (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten als spam te identificeren. Een hogere BCL geeft aan dat een bulkbericht meer kans heeft om klachten te genereren (en daarom meer kans heeft op spam). Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.

 Spamfiltering markeert berichten als **Bulk-e-mail** op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en neemt de opgegeven actie op het bericht (de standaardactie is het verzenden van het bericht naar de map Ongewenste e-mail van de ontvanger). Zie [Beleid voor antispam configureren in Office 365](configure-your-spam-filter-policies.md) en [Wat is het verschil tussen ongewenste e-mail en bulke-mail configureren?](what-s-the-difference-between-junk-email-and-bulk-email.md)

De BCL-drempels worden beschreven in de volgende tabel.

|||
|:---:|---|
|**Bcl**|**Beschrijving**|
|0|Het bericht is niet van een afzender in bulk.|
|1, 2, 3|Het bericht is van een bulk afzender die weinig klachten genereert.|
|4, 5, 6, 7|Het bericht is van een bulk afzender die een gemengd aantal klachten genereert.|
|8, 9|Het bericht is van een bulk afzender die een groot aantal klachten genereert.|
|
