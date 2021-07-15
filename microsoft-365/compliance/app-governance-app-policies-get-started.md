---
title: Aan de slag met app-beleid
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Aan de slag met Meer informatie over app-beleid.
ms.openlocfilehash: 3f80048835388e740ba64ac36d1aa19594bf7a9d
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: nl-NL
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420211"
---
# <a name="get-started-with-app-policies"></a>Aan de slag met app-beleid

>*[Richtlijnen voor Microsoft 365-licenties voor beveiliging en compliance](https://aka.ms/ComplianceSD).*

App-beleid voor Microsoft-app-beheer is de manier waarop u meer proactieve of reactieve voorwaarden kunt implementeren om waarschuwingen of automatisch herstel te creëren voor uw specifieke behoeften voor app-naleving in uw organisatie.

Als u de lijst met huidige app-beleidsregels wilt bekijken, gaat u naar **Microsoft 365-compliancecentrum > App-beveiliging & -beheer > Beleidsregels**.

![De overzichtspagina van MAPG-beleid in het Microsoft 365-compliancecentrum](..\media\manage-app-protection-governance\mapg-cc-policies.png)

## <a name="whats-available-on-the-app-policies-dashboard"></a>Wat is er beschikbaar op het dashboard voor app-beleid

U kunt het aantal actieve, inactieve en testbeleidsregels en de volgende informatie voor elk beleid bekijken:

- **Beleidsnaam**
- **Status**

  - **Actief**: alle beleidsevaluatie en -acties zijn actief.
  - **Inactief**: alle beleidsevaluatie en acties zijn uitgeschakeld.
  - **Auditmodus**: beleidsevaluatie bevindt zich in de auditmodus. Het beleid is actief, maar beleidsacties zijn uitgeschakeld.

- **Ernst**: het ernstniveau dat is ingesteld voor waarschuwingen die zijn geactiveerd omdat dit beleid als waar wordt beoordeeld, wat deel uitmaakt van de configuratie van het beleid.
- **Aantal actieve waarschuwingen**: waarschuwingen die worden gegenereerd door het beleid met de status **Wordt uitgevoerd** of **Nieuw**.
- **Totaal aantal waarschuwingen**: zowel actieve waarschuwingen als opgeloste waarschuwingen voor dit beleid.
- **Datum van laatste waarschuwing**: datum van de laatste gegenereerde waarschuwing vanwege dit beleid.
- **Laatst gewijzigd**: datum waarop dit beleid voor het laatst is gewijzigd.

De beleidslijst wordt standaard gesorteerd op **Laatst gewijzigd**. Selecteer de kenmerknaam om de lijst op een ander kenmerk te sorteren.

Wanneer u een beleid selecteert, krijgt u een gedetailleerd beleidsvenster met de volgende aanvullende details:

- **Beschrijving**: een gedetailleerdere uitleg van het doel van het beleid.
- **Gemaakt door**: user principal name (UPN) van het account waarmee het beleid is gemaakt.
- Een lijst met de actieve waarschuwingen die door dit beleid zijn gegenereerd.

U kunt een app-beleid bewerken of verwijderen door **Bewerken** of **Verwijderen** te selecteren in het gedetailleerde beleidsvenster of door het verticale beletselteken van het beleid in de beleidslijst te selecteren.

U kunt ook het volgende doen:

- Een nieuw beleid maken. U kunt beginnen met een app-gebruiksbeleid of een machtigingsbeleid.
- De beleidslijst exporteren naar een CSV-bestand (door komma's gescheiden waarden). U kunt bijvoorbeeld het CVS-bestand openen in Microsoft Excel en de beleidsregels sorteren op **Ernst** en vervolgens het **Totaal aantal waarschuwingen**.
- Zoeken in de beleidslijst.

## <a name="next-step"></a>Volgende stap

[Maak een app-beleid.](app-governance-app-policies-create.md)
