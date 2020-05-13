---
title: Waarden voor bulkklachten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a5b03b3c-37dd-429e-8e9b-2c1b25031794
ms.collection:
- M365-security-compliance
description: Beheerders kunnen meer te weten komen over bcl-waarden (bulkcomplianceniveau) die worden gebruikt in Exchange Online Protection (EOP).
ms.openlocfilehash: 87ef0787aad12022d9034800c4ddc72e54445f5d
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209605"
---
# <a name="bulk-complaint-level-bcl-in-eop"></a>Bulkklachtenniveau (BCL) in EOP

In Microsoft 365-organisaties met postvakken in Exchange Online- of zelfstandige Exchange Online Protection-organisaties (EOP)-organisaties zonder Exchange Online-postvakken, wijst EOP een bulkcompliant niveau (BCL) toe aan binnenkomende berichten van bulkmailers. De BCL wordt toegevoegd aan het bericht in een X-header en is vergelijkbaar met het [spam vertrouwensniveau (SCL)](spam-confidence-levels.md) dat wordt gebruikt om berichten te identificeren als spam. Een hogere BCL geeft aan dat een bulkbericht meer kans heeft om klachten te genereren (en daarom meer kans heeft op spam). Microsoft gebruikt zowel interne als externe bronnen om bulkmail te identificeren en de juiste BCL te bepalen.

Bulkmailers variëren in hun verzendpatronen, het maken van inhoud en acquisitiepraktijken voor ontvangers. Goede bulk mailers sturen gewenste berichten met relevante inhoud naar hun abonnees. Deze berichten genereren weinig klachten van ontvangers. Andere bulkmailers sturen ongevraagde berichten die sterk op spam lijken en veel klachten van ontvangers genereren. Berichten van een bulkmailer worden bulkmail of grijze e-mail genoemd.

 Spamfiltering markeert berichten als **Bulk-e-mail** op basis van de BCL-drempelwaarde (de standaardwaarde of een waarde die u opgeeft) en neemt de opgegeven actie op het bericht (de standaardactie is het verzenden van het bericht naar de map Ongewenste e-mail van de ontvanger). Zie [Beleid voor antispam configureren](configure-your-spam-filter-policies.md) voor meer informatie en Wat is het verschil tussen ongewenste [e-mail en bulke-mail?](what-s-the-difference-between-junk-email-and-bulk-email.md)

De BCL-drempels worden beschreven in de volgende tabel.

|||
|:---:|---|
|**BCL**|**Beschrijving**|
|0|Het bericht is niet van een afzender in bulk.|
|1, 2, 3|Het bericht is van een bulk afzender die weinig klachten genereert.|
|4, 5, 6, 7|Het bericht is van een bulk afzender die een gemengd aantal klachten genereert.|
|8, 9|Het bericht is van een bulk afzender die een groot aantal klachten genereert.|
|
