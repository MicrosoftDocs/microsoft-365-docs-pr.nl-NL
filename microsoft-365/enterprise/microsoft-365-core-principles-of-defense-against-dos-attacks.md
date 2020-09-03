---
title: Microsoft 365 core-principes van verdediging tegen Denial-in-service-aanvallen
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: Hoe Microsoft gebruikmaakt van de kern beginselen van absorptie, detectie en vermindering van de verdediging tegen een denial-of-service (DoS)-aanval.
ms.openlocfilehash: fb3446570dd8e99ccdb3005a6a7c90ca90a81aee
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: nl-NL
ms.lasthandoff: 09/02/2020
ms.locfileid: "47331906"
---
# <a name="core-principles-of-defense-against-denial-of-service-attacks"></a>Belangrijke principes van bescherming tegen denial-of-service-aanvallen

De drie belangrijkste principes voor het verdedigen van bescherming tegen een netwerk, zijn absorptie, detectie en beperking. Absorptie vindt plaats vóór de detectie, en er vindt een detectie plaats vóór de beperking. Absorptie is de beste verdediging tegen een DoS-aanval. Als de aanval niet kan worden gedetecteerd, kan deze niet worden beperkt. Maar indien zelfs de kleinste aanval niet kan worden geabsorbeerd, blijven de services niet lang genoeg genoeg totdat de aanval wordt gedetecteerd.

Het is niet economisch haalbaar voor de meeste organisaties om extra capaciteit te kopen, aangezien dit een aanzienlijke investering in technologie en technische vaardigheden vergt. Dit is een overzicht van de beveiliging voordelen van het gebruik van Microsoft-cloudservices. De doorschijnende schaal van Microsoft-Services biedt een hoge beveiliging van de Cloud klanten voor Cloud klanten op een rendabele manier. Maar zelfs bij een grote schaal moet er een evenwicht zijn tussen absorptie, detectie en beperking. Om dit saldo te vinden, onderzoeken Microsoft de groei van aanvals percentages om te schatten hoeveel Microsoft moet absorberen.

Detectie is een Cat-en-muis spel. U dient voortdurend te zoeken naar nieuwe manieren waarop iemand een aanval aanmeldt en uw systemen te Defeat. Opsporen-> beperkt > detecteren-> beperkt, etc., is een permanente, permanente status die voor onbepaalde tijd wordt voortgezet.

## <a name="defending-against-dos-attacks"></a>Verdediging tegen DoS-aanvallen

Om te kunnen beginnen tegen een DoS-aanval, is een oudere detectie van essentieel belang. Door het detecteren van een aanval voordat het systeem is overspoeld, kunnen verdedigen een antwoord plan uitvoeren.

De volgende formule helpt bij het bezorgen van de tijd tot impact van een DoS-aanval:

   **Maximum capaciteit (in bytes/sec)/groeisnelheid (in bytes/sec) = tijd tot impact (in SEC)**

Als de tijd-na-impact voor de tijd na de tijd te laat treden, is de DoS-aanval waarschijnlijk wel gelukt. Als de tijd-na-impact vóór tijds impact plaatsvindt, moeten de gehacke services online en toegankelijk blijven als de beperkings strategieën worden gebruikt. Daarom zijn er slechts twee dingen die u kunt doen om een DoS-aanval te verdedigen:

- Verhoog de capaciteit voor het verhogen van de maximale capaciteit (die op zijn beurt meer tijd biedt voor het detecteren van een aanval); wel
- Minder tijd om te detecteren.

De verhoging van de capaciteit heeft een directe fiscale impact. Microsoft raadt klanten aan om ten minste een functie voor basis absorptie te ontwikkelen om ervoor te zorgen dat ze een zekere mate van DoS-aanval kunnen overleven. De werkelijke absorptiecapaciteit varieert van klant tot klant, aangezien elke klant hun eigen drempel voor blootstelling, risico en financiële outlay. Voor economische redenen zijn investeringen in onderzoek en tijd voor manieren om het detecteren van tijd te beperken, meestal de meest rendabele verdediging.
